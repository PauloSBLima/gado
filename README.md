# 🧠 Projeto de VC(ML) - Detecção de Objetos (Rebanhos)
<br>
Bem-vindo(a) ao repositório do trabalho de construção de um pipeline de visão computacional.
Este espaço foi criado para centralizar os códigos, notebooks e materiais práticos desenvolvidos durante este projeto.<br>
<hr>

## 🟢 1. Título do Projeto e Descrição Geral
🌾 AgroTech Analytics | Sistema Inteligente de Contagem de Rebanhos com YOLO
O AgroTech Analytics é uma solução de visão computacional de ponta desenvolvida para o agronegócio. Utilizando modelos avançados de Inteligência Artificial da família YOLO (Ultralytics) — incluindo versões padrão, especializadas (OIV7), estado da arte (YOLO12, YOLO26) e de vocabulário aberto (YOLO-World) —, o sistema automatiza a detecção, contagem e o cruzamento de métricas de confiança de rebanhos a partir de imagens aéreas ou terrestres.

## 🚀 2. Principais Funcionalidades
Suporte a Múltiplas Arquiteturas YOLO: Permite escolher entre 41 variações de modelos (YOLOv5, YOLOv8, YOLOv8-OIV7, YOLOv9, YOLOv10, YOLO11, YOLO12, YOLO26 e YOLO-World).

Detecção Inteligente de Classes Agro: Mapeia automaticamente categorias de interesse (cattle, cow, bull, livestock, ox, horse, sheep) ou utiliza prompts textuais dinâmicos via YOLO-World.

HUD Profissional Integrado: Desenha um painel transparente com estatísticas em tempo real na imagem processada (latência em ms, contagem total e confiança média).

Geração de Laudos Visuais e Relatórios Estruturados: Salva automaticamente imagens anotadas na pasta laudos/ e metadados detalhados (com coordenadas de bounding boxes) em arquivos JSON na pasta contagem/.

Análise Gráfica de Confiança: Cria e salva gráficos de barras ordenados por ID com o limiar mínimo configurado na pasta graficos.

## 🛠️ 3. Tecnologias Utilizadas
* Python 3.8+
* Ultralytics YOLO (Visão Computacional e Deep Learning)
* OpenCV (cv2) (Processamento de imagem e interface gráfica)
* Matplotlib (Geração de gráficos analíticos)
* Pathlib / NumPy

## 📦 4. Instalação e Dependências
Certifique-se de ter o Python instalado em seu ambiente e instale as bibliotecas necessárias executando o comando abaixo no terminal:
=> *pip install ultralytics opencv-python matplotlib numpy*

## ⚙️ 5. Como Executar o Projeto
5.1 Clone o repositório ou salve o script principal em sua máquina (ex: main.py).
5.2 Execute o script através do terminal:
=> *python main.py*

5.3 O sistema limpará a tela e exibirá um menu interativo completo com *41 opções de modelos YOLO*:
=>
```text
===========================================================================
       SISTEMA DE CONTAGEM DE GADO - SELEÇÃO COMPLETA DE MODELOS YOLO
===========================================================================
 Selecione a família e variação do modelo desejado:
  --- YOLOv5 ---
  [1] yolov5n.pt   | [2] yolov5s.pt   | [3] yolov5m.pt   | [4] yolov5l.pt   | [5] yolov5x.pt
  --- YOLOv8 ---
  [6] yolov8n.pt   | [7] yolov8s.pt   | [8] yolov8m.pt   | [9] yolov8l.pt   | [10] yolov8x.pt
  --- YOLOv8 OIV7 (Específico p/ Agro/Objetos Complexos) ---
  [11] yolov8n-oiv7.pt | [12] yolov8s-oiv7.pt | [13] yolov8m-oiv7.pt | ...
  ...
```

5.4 Digite o número correspondente à opção desejada (ex: 13 para o yolov8m-oiv7.pt).
5.5 O sistema baixará automaticamente uma imagem de exemplo (caso não exista na pasta imagens/) e iniciará o pipeline de inferência, salvando os resultados.

## 🧱 6. Estrutura do Projeto
```text
├──gado/
│   ├── imagens/            # Diretório de armazenamento das imagens para seleção na entrada (ex: gado001.jpg)
│   ├── laudos/             # Diretório das imagens finais anotadas com o HUD profissional
│   ├── contagem/           # Diretório com os arquivos JSON estruturados com os dados de detecção
│   ├── graficos/           # Diretório com gráficos de barras salvos com as métricas de confiança
├── .gitignore              # Relação de arqs que não devem ser levados p/ o  GitHub
├── README.md               # Leia-me do projeto
├── requirements.txt        # Relação de bibliotecas e dependências
└── gado_v3.ipynb           # Módulo principal do pipeline
```

## 📊 7. Exemplo de Saída JSON (_dados_contagem.json)
JSON
```text
{
    "metadata_lote": {
        "timestamp_processamento": "2026-10-02T21:49:30Z",
        "modelo_utilizado": "yolov8m-oiv7.pt",
        "opcao_escolhida": "13",
        "total_cabecas_detectadas": 15,
        "confianca_media_lote": 88.45,
        "tempo_inferencia_ms": 142.5
    },
    "detalhamento_animais": [
        {
            "id_deteccao": 1,
            "classe": "cattle",
            "confianca_pct": 92.4,
            "geometria_bbox": {
                "x_min": 120,
                "y_min": 240,
                "x_max": 180,
                "y_max": 310
            }
        }
    ]
}
```

## 💡 8. Contribuição
Contribuições, melhorias de código ou sugestões de novos modelos são sempre bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.

## 📜 9. Licença
Este projeto é distribuído sob a licença MIT. Sinta-se livre para utilizá-lo em pesquisas, projetos acadêmicos ou soluções comerciais voltadas ao agronegócio.

## 👨‍🏫 Desenvolvido por 
Paulo Sérgio Barreiros Lima<br>
Bacharel em Ciências da Computação / Aperfeiçoamento em ML e Visão Computacional<br>
paulosergiobarreiroslima@gmail.com
