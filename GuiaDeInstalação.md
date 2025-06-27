## ✅ Passo 1 – Baixar e instalar

1. Vá até a pasta onde está o arquivo baixado (`robocode-1.9.5.2-setup.jar`).
2. No terminal, execute:

```bash
java -jar robocode-1.9.5.2-setup.jar
```

3. Isso instala o Robocode em `~/robocode`.

---

## ✏️ Passo 2 – Editar `robocode.sh`

Abra o arquivo para edição:

```bash
gedit ~/robocode/robocode.sh
```

Você verá algo como:

```bash
# Run Robocode (UI)
./set_java_options.sh
...
if [ "$exit_code" -ne 100 ]; then
  java \
    -cp "libs/*" \
    -Xmx512M \
    -Xdock:name=Robocode \
    -Xdock:icon=robocode.ico \
    -XX:+IgnoreUnrecognizedVMOptions \
    "--add-opens=java.base/sun.net.www.protocol.jar=ALL-UNNAMED" \
    "--add-opens=java.base/java.lang.reflect=ALL-UNNAMED" \
    "--add-opens=java.desktop/javax.swing.text=ALL-UNNAMED" \
    "--add-opens=java.desktop/sun.awt=ALL-UNNAMED" \
    robocode.Robocode "$@"
fi
```

### 🔧 Ajuste necessário para Java 21

Modifique essa parte para incluir **`-Djava.security.manager=allow`**, como abaixo:

```bash
  java \
    -cp "libs/*" \
    -Xmx512M \
    -Xdock:name=Robocode \
    -Xdock:icon=robocode.ico \
    -XX:+IgnoreUnrecognizedVMOptions \
    "--add-opens=java.base/sun.net.www.protocol.jar=ALL-UNNAMED" \
    "--add-opens=java.base/java.lang.reflect=ALL-UNNAMED" \
    "--add-opens=java.desktop/javax.swing.text=ALL-UNNAMED" \
    "--add-opens=java.desktop/sun.awt=ALL-UNNAMED" \
    -Djava.security.manager=allow \
    robocode.Robocode "$@"
```

Essa mudança é recomendada e até automatizada pelas versões mais novas, mas é bom confirmar manualmente ([sourceforge.net][1], [robowiki.net][2]).

---

## 🛠️ Passo 3 – Salvar e executar

1. Salve as alterações no `robocode.sh` e feche o editor.
2. No terminal, execute:

```bash
~/robocode/robocode.sh
```

Isso deve abrir o Robocode com a interface gráfica.

* Se der erro do tipo **`UnsupportedOperationException`** ou **“Could not create SecurityManager”**, retorne ao script e revise a linha com `-Djava.security.manager=allow` ([groups.google.com][3], [cse.chalmers.se][4]).

---

## 🧠 Explicação técnica

* A partir do Java 12, o **Security Manager** só funciona se você permitir explicitamente com `-Djava.security.manager=allow` ([groups.google.com][3]).
* Versões do Robocode recentes já vêm com essa opção configurada, mas em alguns cenários (Linux) pode ser necessário editar manualmente ([sourceforge.net][1]).

---

### ✅ Resumo rápido

* **Java 21 (sua versão)** → use `-Djava.security.manager=allow`.
* Verifique que está após os `--add-opens`.
* Rode o `robocode.sh` novamente.

---
