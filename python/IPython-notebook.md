

IPython Notebook Cheat Sheet
============================


IPython's Rich Display System
-----------------------------

also see
- http://nbviewer.ipython.org/github/ipython/ipython/blob/2.x/examples/Notebook/Display%20System.ipynb


Display an bitmap image implicitly as last statement of a IPython notebook cell:

    from IPython.display import Image
    Image(filename='../images/ipython_logo.png')

Display a SVG image explicitly with the generic `display` function:

    from IPython.display import display
    from IPython.display import SVG
    x = SVG('<svg viewBox="0 0 10 10"><circle cx="4" cy="3" r="2" /></svg>')
    display(x)
    print "bye"
