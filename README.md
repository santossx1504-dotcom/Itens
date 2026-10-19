# Material Pack — projeto Fabric 1.21.11

Mod cliente para abrir um menu compacto com Right Shift e ler os materiais da schematic selecionada no Litematica, sem precisar abrir a janela Material List.

## Requisitos no Minecraft
- Minecraft Java 1.21.11
- Fabric Loader 0.18.1 ou mais recente
- Fabric API 0.141.6+1.21.11
- Litematica 0.26.12
- MaLiLib 0.27.16
- Java 21

## Tecla
`Right Shift` abre o menu. A tecla pode ser alterada em Opções → Controles → Teclas → Miscellaneous.

## Como compilar
É necessário um computador com Java 21 e acesso à internet para o Gradle baixar as dependências. Na pasta deste projeto, execute:

```bash
gradle build
```

O JAR será criado em `build/libs/`.

## Como funciona
O mod tenta consultar a schematic selecionada no `SchematicPlacementManager` do Litematica e obtém a lista por meio do objeto `MaterialList` da própria placement. Não precisa abrir a janela Material List. Se não houver schematic selecionada, o menu informa isso. A leitura usa reflexão para reduzir o acoplamento de compilação com as classes internas do Litematica.

## Estado do projeto
Este é o projeto-fonte inicial. Não foi possível compilar ou testar o JAR neste ambiente porque o Gradle e o acesso de rede às dependências não estão disponíveis aqui. Portanto, a integração precisa ser compilada e testada no ambiente Fabric 1.21.11 antes de considerar o mod pronto para uso.

## Build automático (opcional)
O projeto inclui `.github/workflows/build.yml`. Se você enviar a pasta para um repositório GitHub e executar a ação **Build Material Pack**, o GitHub Actions tentará compilar e anexará os JARs como artefato da execução. Isso ainda não substitui um teste dentro do Minecraft.
