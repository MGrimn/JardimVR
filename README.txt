================================================================
  PROJETO: Meu Primeiro Ambiente VR
  Disciplina: Web 3 / Meta SDK - Atividade 1
  Data: 2026
================================================================

DESCRIÇÃO DO PROJETO
---------------------
Ambiente VR interativo criado com Unity e Meta XR SDK.
O ambiente simula um jardim externo com elementos 3D,
navegável via teclado/mouse no PC e compatível com
Meta Quest via Android build.

CENA: "Jardim VR"
------------------
O ambiente conta com os seguintes elementos 3D:
  1. Plano de Chão  - Base verde do jardim (50x50 unidades)
  2. Casa           - Estrutura principal com porta e janelas
  3. Árvores (x3)   - Vegetação com tronco e copa esférica
  4. Banco          - Mobiliário de jardim
  5. Rocha          - Elemento decorativo orgânico
  6. Poste de Luz   - Iluminação com ponto de luz dinâmico

HIERARQUIA DE OBJETOS
----------------------
Scene
├── _Ambiente
│   └── Chao_Principal
├── _Estruturas
│   └── Casa
│       ├── Casa_Corpo
│       ├── Casa_Telhado
│       ├── Casa_Porta
│       ├── Casa_Janela (x2)
├── _Vegetacao
│   ├── Arvore (x3)
│   │   ├── Arvore_Tronco
│   │   └── Arvore_Copa
├── _Mobiliario
│   ├── Banco_Jardim
│   │   ├── Banco_Assento
│   │   ├── Banco_Encosto
│   │   └── Banco_Pe (x2)
│   └── Poste_Luz
│       ├── Poste_Haste
│       └── Poste_Lampada (com PointLight)
├── _Decoracao
│   └── Rocha_Decorativa
└── Player
    ├── CameraHolder
    │   └── MainCamera
    └── [PCMovement, PlayerSetup, Rigidbody, CapsuleCollider]

CONTROLES (MODO PC)
--------------------
  W / Seta Cima    → Andar para frente
  S / Seta Baixo   → Andar para trás
  A / Seta Esq     → Mover para esquerda
  D / Seta Dir     → Mover para direita
  Shift (esquerdo) → Correr
  Espaço           → Pular
  Mouse            → Rotacionar câmera (olhar ao redor)
  ESC              → Liberar/travar o cursor

SCRIPTS INCLUÍDOS
------------------
  Assets/Scripts/PCMovement.cs
    → Controla movimentação WASD + mouse look no PC
    → Parâmetros configuráveis via Inspector

  Assets/Scripts/PlayerSetup.cs
    → Monta automaticamente a estrutura do Player
    → Cria câmera na altura correta dos olhos
    → Configura Rigidbody e CapsuleCollider

  Assets/Scripts/SceneBuilder.cs
    → Gera automaticamente todos os objetos 3D da cena
    → Organiza hierarquia em pastas (_Ambiente, _Estruturas, etc.)
    → Cores configuráveis via Inspector

CONFIGURAÇÃO META XR SDK
--------------------------
  1. Instalar via Package Manager:
     → com.unity.xr.management
     → Oculus XR Plugin (ou Meta XR SDK)

  2. Edit → Project Settings → XR Plug-in Management:
     → Ativar "Oculus" para Android E para PC/Standalone

  3. Edit → Project Settings → Player:
     → Android tab: Company Name, Package Name (com.seuNome.jardinVR)
     → Minimum API Level: Android 10 (API 29)

BUILD SETTINGS (ANDROID - META QUEST)
---------------------------------------
  File → Build Settings:
  → Platform: Android
  → Texture Compression: ASTC
  → Run Device: Meta Quest (conectado via USB)
  → Build And Run

TECNOLOGIAS UTILIZADAS
-----------------------
  - Unity (versão compatível com Meta SDK 60+)
  - Meta XR SDK (Oculus XR Plugin)
  - C# (Scripts de movimentação e construção de cena)
  - Unity Primitives (Cube, Sphere, Cylinder, Plane, Capsule)
  - Unity Lighting System (Point Light no poste)

REFLEXÃO DE APRENDIZADO
------------------------
Durante o desenvolvimento, aprendi:

  • Como configurar o Unity para desenvolvimento VR com Meta Quest
  • A diferença entre desenvolvimento para PC e para Android (Quest)
  • Como organizar hierarquia de objetos no Unity de forma profissional
  • Como criar scripts C# para controle de movimentação
  • A importância do Rigidbody e CapsuleCollider para física de player
  • Como usar o sistema de iluminação do Unity (Point Light)
  • Boas práticas de nomenclatura e organização de projeto

ESTRUTURA DE PASTAS
--------------------
Assets/
  ├── Scripts/
  │   ├── PCMovement.cs
  │   ├── PlayerSetup.cs
  │   └── SceneBuilder.cs
  ├── Scenes/
  │   └── JardimVR.unity
  └── (Assets importados, se houver)

ProjectSettings/
Packages/

AUTOR
------
[Seu Nome Aqui]
Curso: Web 3 / Realidade Virtual
Data de Entrega: [Data]

================================================================
