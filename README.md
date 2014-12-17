# PHP VIM XDebugger Client

This python script provides debugger interface to DBGp protocol.  
(but, only tested on Xdebug2.0 - http://www.xdebug.org/ )

## Requirements

 * DBGp protocol enabled debugging module. such as xdebug.
  ( I don't know there are free DBGp debugger except xdebug )

 * Vim 6.3 ( only tested on vim 6.3 )

 * Python 2.3+ interface , +sign feature

## Usage

 1. Setup xdebug 2.0 correctly. or other DBGp enabled server.
   (with proper remote debug option)

 2. Press <F5> and browse php file within 5 seconds.  
    If you did setup correctly, server will make connection to vim.  
    (you can change port by editing last line of xdebugger.vim)

    all the windows currently opened will be closed and debugger interface will be shown.

 3. **While debugging**  
    `<F1>` : resizing windows  
    `<F2>` : step into  
    `<F3>` : step over  
    `<F4>` : step out  

    `<F6>` : stop debugging  

    `<F11>` : shows all variables  
    `<F12>` : shows variable on current cursor   

    `,e` : evalute expression and display result. cursor is automatically move to watch window. type line and just press enter.  
    **VIM Commands**  
    `:Bp`    : toggle breakpoint on current line  
    `:Up`    : goto upper level of stack  
    `:Dn`    : goto lower level of stack  

## Notes

 > If you turn off syntax highlighting, it will be much faster.  

 * You will see python's exception message. almost of them occurred when connection is closed. 
   xdebug dosen't send message for last file/line information.
   just press <F6> to restore sesson. sometimes are xdebug's bug.
 
 * To use with a lot of people with same time, it may needs DBGp proxy. you may download 
   MIT licensed(?) version of it from activestate's komodo's evalution copy. and, you 
   have to change this script a little.

 * It doesn't have all features of DBGp. Only the essential parts.

