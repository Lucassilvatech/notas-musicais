![logo do projeto](assets/logo.png){width="300" .center}
# Notas musicais

Notas musicais é um CLI para ajudar na formação de escalas, acordes e campos harmônicos.

Toda a aplicação é baseade em um comando chamado `notas-musicais`. esse comando tem um subcomando relacionado a cada ação que a aplicação pode realizar. Como `escalas`,`acordes` e `campo-harmonico`

Temos dois comandos disponíveis `escala` e `acorde`

## Como usar?

### Escala

você pode chamar as escalas via linha de comando. Por exemplo:

```bash
poetry run notas-musicais escala
```

Retornando os graus e as notas correspondentes a essa escala:

```
┏━━━┳━━━━┳━━━━━┳━━━━┳━━━┳━━━━┳━━━━━┓
┃ I ┃ II ┃ III ┃ IV ┃ V ┃ VI ┃ VII ┃
┡━━━╇━━━━╇━━━━━╇━━━━╇━━━╇━━━━╇━━━━━┩
│ C │ D  │ E   │ F  │ G │ A  │ B   │
└───┴────┴─────┴────┴───┴────┴─────┘
```

#### Alteração da tônica da escala

O primeiro parâmetro do CLI é a tônica da escala que deseja exibir. Desta forma você pode alterar a escala retornada. Por exemplo, a escala de `F#`:

```bash
poetry run notas-musicais escala F#
```

Resultando em:

```
┏━━━━┳━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ I  ┃ II ┃ III ┃ IV ┃ V  ┃ VI ┃ VII ┃
┡━━━━╇━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ F# │ G# │ A#  │ B  │ C# │ D# │ F   │
└────┴────┴─────┴────┴────┴────┴─────┘
```

#### Alteração na tonalidade da escala

Você pode alterar a tonalidade da escala também! Esse é o segundo parametro da linha de comando. Por exemplo a escala de `D#` menor:

```bash
poetry run notas-musicais escala D# menor
```

Resultando em:

```
┏━━━━┳━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ I  ┃ II ┃ III ┃ IV ┃ V  ┃ VI ┃ VII ┃
┡━━━━╇━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ D# │ F  │ F#  │ G# │ A# │ B  │ C#  │
└────┴────┴─────┴────┴────┴────┴─────┘
```

### Acordes

Uso básico

```bash
poetry run notas-musicais acorde

┏━━━┳━━━━━┳━━━┓
┃ I ┃ III ┃ V ┃
┡━━━╇━━━━━╇━━━┩
│ C │ E   │ G │
└───┴─────┴───┘
```

#### Variações na cifra

```bash
poetry run notas-musicais acorde C+

┏━━━┳━━━━━┳━━━━┓
┃ I ┃ III ┃ V+ ┃
┡━━━╇━━━━━╇━━━━┩
│ C │ E   │ G# │
└───┴─────┴────┘
```

Até o momento você pode usar acordes maiores, menores(m), diminuto(°) e aumentados(+)

## campos harmonicos

Você pode chamar os comandos harmônicos via o subcomando `campos-harmonicos`. Por exemplo:

```bash
poetry run notas-musicais campos-harmonicos
```

```
┏━━━┳━━━━┳━━━━━┳━━━━┳━━━┳━━━━┳━━━━━━┓
┃ I ┃ ii ┃ iii ┃ IV ┃ V ┃ vi ┃ vii° ┃
┡━━━╇━━━━╇━━━━━╇━━━━╇━━━╇━━━━╇━━━━━━┩
│ C │ Dm │ Em  │ F  │ G │ Am │ B°   │
└───┴────┴─────┴────┴───┴────┴──────┘
```

Por padrão os parâmetros utilizados são a tônica de `C` e o campo harmônico `maior`.

### Alterações nos campos harmônicos

Você pode alterar os parâmetros da tônica e da tonalidade.

```bash
poetry notas-musicais campo-harmonico [TONICA] [TONALIDADE] 
```

#### Alteração da tônica do campo

```bash
poetry run notas-musicais campo-harmonico A
```

Um exemplo com o campo harmônico de `A`:

```
┏━━━┳━━━━┳━━━━━┳━━━━┳━━━┳━━━━━┳━━━━━━┓
┃ I ┃ ii ┃ iii ┃ IV ┃ V ┃ vi  ┃ vii° ┃
┡━━━╇━━━━╇━━━━━╇━━━━╇━━━╇━━━━━╇━━━━━━┩
│ A │ Bm │ C#m │ D  │ E │ F#m │ G#°  │
└───┴────┴─────┴────┴───┴─────┴──────┘
```

#### Alteração da tonalidade do campo

```bash
poetry run notas-musicais campo-harmonico A menor
```

Um exemplo utilizando o campo harmônico de `A` na tonalidade `menor`:

```
┏━━━━┳━━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ i  ┃ ii° ┃ III ┃ iv ┃ v  ┃ VI ┃ VII ┃
┡━━━━╇━━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ Am │ B°  │ C   │ Dm │ Em │ F  │ G   │
└────┴─────┴─────┴────┴────┴────┴─────┘
```

## Mais informações sobre o CLI

Para descobrir outras opções, você pode usar a flag `--help`:

```bash
poetry run notas-musicais --help
```

Resultando em:

```
Usage: notas-musicais [OPTIONS] COMMAND [ARGS]...

Commands:
    acorde
    campo-harmonico
    escala
```
### Mais imformações sobre os subcomandos

As informações sobre os subcomandos podem ser acessadas usando a flag `--help` após o nome do parâmetro. Um exemplo do uso do `help` nos campos harmônicos:

```bash
poetry run notas-musicais campo-harmonico --help

Usage: notas-musicais campo-harmonico [OPTIONS] [TONICA] [TONALIDADE]

Arguments:
    tonica       [TONICA]      Tônica do campo harmônico [default: c]
    tonalidade   [TONALIDADE]  Tonalidade do campo harmônico [default: maior]
```