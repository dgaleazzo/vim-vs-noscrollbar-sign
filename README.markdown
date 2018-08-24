# VIM Visual Studio noscrollbar Sign

![Noscrollbar demo](https://dgaleazzo.github.io/vim-vs-noscrollbar-sign/noscrollbar.gif)

This is a fork of Giovanni Cavallanti [vim-noscrollbar](https://github.com/gcavallanti/vim-noscrollbar).

The goal is to emulate Visual Studio Code scrollbar sign indicators for any
kind of plugins that use signs such as:
- vim-gitgutter
- syntastic
- ale
- vim-signify
etc..

## Installation

I recommend installing [pathogen.vim](https://github.com/tpope/vim-pathogen), and
then simply copy and paste:

    cd ~/.vim/bundle
    git clone https://github.com/gcavallanti/vim-noscrollbar.git

Once help tags have been generated, you can view the manual with
`:help noscrollbar`.

### How to use

Simply add `%{noscrollbar#statusline()}` to the `statusline` option and you are
done. Example:

    set statusline=%<%f\ %h%m%r%=%-14.(%l,%c%V%)\ %{noscrollbar#statusline()}

The default behavior returns a string of length 20 where the dash character '-'
is used to render the track of the scrollbar and the hash character '#' is used
to render the gripper.  The scrollbar look can be customized by passing the
length, the track character and the gripper character. For example the default
look is set by calling `%{noscrollbar#statusline(20,'-','#')}`.

### Powerline Integration

    function! Noscrollbar(...)
        let w:airline_section_z = '%{noscrollbar#statusline(50)}'
    endfunction
    call airline#add_statusline_func('Noscrollbar')

### High resolution mode

NoscrollBar comes with an high resolution mode.  Check `:help noscrollbar`
for details. 

## License

Copyright (c) Daniel Aurelio Galeazzo. Distributed under the same terms as [vim-noscrollbar](https://github.com/gcavallanti/vim-noscrollbar).

