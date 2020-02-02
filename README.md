# md-img-paste.vim
Yet simple tool to paste images into latex files

## Use Case
An image on the clipboard gets "pasted" into the .tex document being edited: the plugin hooks `<leader>p`, checks if a latex file is being edited, saves the image from the clipboard to the location  `Images/image1.png`, and inserts

```
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{Images/image1.png}
    \caption{image1}
    \label{fig:image1}
\end{figure}
```
into the file.

## Installation

Using VimPlug
```
Plug 'DedZago/latex-img-paste.vim'
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
Forked repository from [ferrine](https://github.com/ferrine/md-img-paste.vim) originally for Markdown, modified for LaTeX.
