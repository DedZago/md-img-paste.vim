# md-img-paste.vim
Yet simple tool to paste images into latex files

## Use Case
You are editing a latex file and have an image on the clipboard and want to paste it into the document. Instead of first copying it to that directory, you want to do it with a single `<leader>p` key press in Vim. So it hooks `<leader>p`, checks if you are editing a latex file, saves the image from the clipboard to the location  `Images/image1.png`, and inserts
```
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{Images/image1.png}
    \caption{}
    \label{fig:}
\end{figure}
```
into the file.

## Installation

Using VimPlug
```
Plug 'DedZago/md-img-paste.vim'
```

## Usage
Add to .vimrc
```
autocmd FileType tex,latex nnoremap <silent> <leader>p :call mdip#MarkdownClipboardImage()<CR>
" there are some defaults for image directory and image name, you can change them
" let g:mdip_imgdir = 'Images'
" let g:mdip_imgname = 'image'
```

## Acknowledgements
Original from [ferrine](https://github.com/ferrine/md-img-paste.vim), modified for LaTeX.
