

## Instalação

```
# Instalar Ollama
curl -fsSL https://ollama.com/install.sh | sh
sudo systemctl start ollama

# Baixar modelo de embeddings
ollama pull nomic-embed-text

# Configurar ambiente Python
python -m venv ollama-env
source venv/bin/activate
pip install -r requirements.txt
```

# Executar script

```
(ollama-env) alves@fedora:~/tsi$ python embedding_ollama.py
```

# Resultados

```
Texto: Ollama é incrível para gerar embeddings locais!

Tamanho do vetor: 768 dimensões

Primeiros 10 elementos do vetor:
[0.38265612721443176, 1.8112214803695679, -2.969672679901123, -1.9754486083984375, -0.14563100039958954, -0.6691678762435913, 0.14759887754917145, -0.3818332254886627, -1.1961286067962646, -0.015880636870861053]
```

# Script

```
import ollama

def embeddings_generator(string):
    # Gerar embeddings
    resultado = ollama.embeddings(
        model='nomic-embed-text',
        prompt=txt
    )

    # Extrair vetor
    vetor = resultado['embedding']

    # Exibir resultados
    print(f"Texto: {txt}")
    print(f"\nTamanho do vetor: {len(vetor)} dimensões")
    print("\nPrimeiros 10 elementos do vetor:")
    print(vetor[:10])

if __name__ == "__main__":
    texto = "Ollama é incrível para gerar embeddings locais!"
    embedding_generator(string)
```
## Ambiente

 Fedora 41
 Python 3
 32GB RAM
 Intel I5 Generation 10
