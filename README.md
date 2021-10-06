#### Versão em português abaixo / Portuguese version below

# English version

## Idea

Recently, I received a freelance-task in video editing. It consisted of two stages: to edit the audio, removing noises, and then, to segment the video in sections, according to the panels and sessions presented on each day of the recording. As an enthusiast of the [Free and Open Source Software (FOSS)](https://en.wikipedia.org/wiki/Free_and_open-source_software) movement, I decided to implement my solution by utilizing only free software whose source code is available.

For the second part, I needed to identify which were the best points for cutting, and then proceed with any video editing tool, such as [Lightworks](https://lwks.com/) or [LosslessCut](https://github.com/mifi/lossless-cut). The problem was, there were in total some 10 or 12 sections, and the clients and I changed our minds several times about what the best moment to cut the video would be. If the cut was too early, the video would be suddenly interrupted, with a late cut, the video would contain undesirable silence. Should we merge the opening ceremony with the first presentation, or cut them in two segments? Should we keep the teaser video for every clip, or only for the first one? To do all that several times by hand was cumbersome and error-prone.

To make my life easier, I decided to create an automatic manner to process the videos. In a text file, I could write down which video file should be cut, from where to where, and what that segment meant. In the end, I could process this text file with a script invoking [FFmpeg](https://ffmpeg.org/), and, in less than a minute, I would be able to check the result of the new partitioning of more than 10 hours of video.

## How to use

The basic dependency to use this library is **ffmpeg**. In Ubuntu, this software can be installed with the command **sudo apt install ffmpeg**.

Firstly, consider whether the file format you have at hand is the desired one. If desired, make use of the script **scripts/vidconvertmp4 YOUR_FILE** to convert your files to the MP4 format. In second place, make sure that all the video files are in the **media** directory, under the root folder of the project. Now, fill the file **scripts/instructions.txt** with instructions to section your videos (use the syntax of the given file as an example). To segment, execute **scripts/vidcrop scripts/instructions.txt**.

As a final consideration, if you want to merge two video sections, write your instructions to the file **scripts/merge.txt** (according to the given example), and execute **scripts/vidconcat scripts/merge.txt media/OUTPUT_FILE**.

# Versão em português

## A ideia

Recentemente, recebi um freela de edição de vídeo. Foram duas tarefas: editar o áudio, removendo ruídos, e depois segmentar o vídeo em trechos, de acordo com os painéis e sessões apresentados no dia da gravação. Como entusiasta do movimento [Free and Open Source Software (FOSS)](https://en.wikipedia.org/wiki/Free_and_open-source_software), resolvi implementar minha solução apenas com programas gratuitos e de código-fonte aberto.

Para a segunda parte, eu teria que identificar quais são os pontos mais propícios para o corte, e depois prosseguir com qualquer ferramenta de edição de vídeo, como o [Lightworks](https://lwks.com/) ou [LosslessCut](https://github.com/mifi/lossless-cut). O problema é que, no total, tratava-se de uns 10-12 segmentos, e os clientes e eu mudamos várias vezes de opinião quanto a qual seria o melhor momento para cortar. Cortando muito cedo, o vídeo é interrompido de forma brusca, cortando atrasado, o vídeo ficava com um silêncio inoportuno. Deveríamos fundir a cerimônia de abertura com a primeira apresentação, ou cortar em dois segmentos? Manter o vídeo teaser em cada um dos clipes, ou apenas no primeiro? Fazer tudo isso repetidas vezes manualmente era trabalhoso e tendia ao erro.

Para facilitar meu trabalho, resolvi criar uma maneira automática de processar os vídeos. Em um arquivo de texto, eu poderia registrar qual arquivo deveria ser cortado, de qual ponto até qual ponto, e o que aquele segmento significava. Ao final, eu processava o arquivo de texto com um script que invocava o software [FFmpeg](https://ffmpeg.org/
), e em menos de um minuto, poderia conferir o resultado com a nova segmentação das mais de dez horas de vídeo.

## Modo de usar

O requisito básico para utilizar esta biblioteca é o **ffmpeg**. No Ubuntu, este software pode ser baixado com o comando **sudo apt install ffmpeg**.

Primeiramente, considere se o formato do arquivo do qual você dispõe é o desejado. Caso seja propício, utilize o script **scripts/vidconvertmp4 SEU_ARQUIVO** para converter seus arquivos para o formato MP4. Em segundo lugar, certifique-se que todos os arquivos de vídeo se encontram na pasta **media**, abaixo do diretório raiz do projeto. Agora, preencha o arquivo **scripts/instructions.txt** com instruções para segmentar os vídeos (use a sintaxe do arquivo fornecido como exemplo). Para segmentar, execute **scripts/vidcrop scripts/instructions.txt**.

Por último, se for desejável fundir dois segmentos de vídeo, preencha o arquivo **scripts/merge.txt** com instruções (segundo o exemplo), e execute **scripts/vidconcat scripts/merge.txt media/ARQUIVO_DE_SAIDA**.


