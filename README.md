## 💻 Sobre o projeto

O projeto Trojan consiste em um malware desenvolvido em Python.

---

## ⚙️ Funcionalidades

- [x] Copiar o arquivo Trojan para a pasta de inicialização do usuário no Windows.
- [x] Criar um socket de cliente e tentar estabelecer uma conexão com o servidor de controle remoto.
- [x] Receber comandos do servidor de controle remoto e executá-los no sistema.
- [x] Iniciar automaticamente quando o sistema é inicializado.
- [x] Empacotamento do Trojan em um único executável chamado "trojan.exe" usando pyinstaller.
- [x] Inserir RAT (Remote Access Trojan) dentro de uma imagem.

---

## 🛠 Tecnologias

- **[Python](https://www.python.org)**
- **[Socket](https://docs.python.org/3/library/socket.html)**
- **[Subprocess](https://docs.python.org/3/library/subprocess.html)**
- **[Threading](https://docs.python.org/3/library/threading.html)**
- **[Time](https://docs.python.org/3/library/time.html)**
- **[OS](https://docs.python.org/3/library/os.html)**

---

## 🚀 Executando o Trojan

```shell script
pyinstaller -F --clean -w trojan.py
```

---

## 📑 Processo de Ataque

### Máquina do Atacante
Utilize o NetCat para ouvir por conexões recebidas.

### Máquina Alvo
Execute o código exportado garantindo que você insira o endereço IP correto para que a porta dos fundos funcione corretamente no computador da vítima. Estabeleça uma conexão de shell usando uma técnica de Shell Reverso.
