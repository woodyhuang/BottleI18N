bottle_i18n
============

A very simple I18N plugin for Bottle apps.

Here is an example:

::

    from bottle import Bottle, view
    from bottle_i18n import I18NPlugin

    myapp = Bottle()

    i18n = I18NPlugin(domain='myapp')
    myapp.install(i18n)


    @myapp.get('/')
    @view('index')
    def index():
        i18n_msg = myapp._('test i18n in python')
        return {'i18n_msg':i18n_msg, '_':myapp._}


You index.tpl may look like below:

::

    <p>
      {{ i18n_msg }}
    </p>
    <p>
      {{ _('test i18n in bottle template') }}
    </p>