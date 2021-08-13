---
title: Multiverse
images:
    -
        title: 'Tile 1'
        thumbnail: tile.jpg
        description: 'Nunc blandit nisi ligula magna sodales lectus elementum non. Integer id venenatis velit.'
        designation: vertical
    -
        title: 'Tile 2'
        thumbnail: tile2.jpg
        description: 'Nunc blandit nisi ligula magna sodales lectus elementum non. Integer id venenatis velit.'
        designation: vertical
    -
        title: 'Tile 3'
        thumbnail: tile3.jpg
        description: 'Nunc blandit nisi ligula magna sodales lectus elementum non. Integer id venenatis velit.'
        designation: horizontal
    -
        title: Sunrise
        thumbnail: sunrise.jpg
        description: 'Nunc blandit nisi ligula magna sodales lectus elementum non. Integer id venenatis velit.'
        designation: horizontal
    -
        title: 'Tile 4'
        thumbnail: tile4.jpg
        description: 'Nunc blandit nisi ligula magna sodales lectus elementum non. Integer id venenatis velit.'
        designation: horizontal
    -
        title: 'Tile 5'
        thumbnail: tile5.jpg
        description: 'Nunc blandit nisi ligula magna sodales lectus elementum non. Integer id venenatis velit.'
        designation: horizontal
    -
        title: 'Tile 6'
        thumbnail: tile6.jpg
        description: 'Nunc blandit nisi ligula magna sodales lectus elementum non. Integer id venenatis velit.'
        designation: vertical
    -
        title: 'Tile 7'
        thumbnail: tile7.jpg
        description: 'Nunc blandit nisi ligula magna sodales lectus elementum non. Integer id venenatis velit.'
        designation: vertical
form:
    action: /home
    name: contact-form
    fields:
        -
            name: name
            label: Name
            placeholder: Name
            type: text
            validate:
                required: true
        -
            name: email
            label: Email
            placeholder: Email
            type: email
            validate:
                required: true
        -
            name: message
            label: Message
            placeholder: Message
            type: textarea
            rows: 4
            validate:
                required: true
    buttons:
        -
            type: submit
            value: Send
            classes: special
        -
            type: reset
            value: Reset
    process:
        -
            email:
                from: '{{ config.plugins.email.from }}'
                to:
                    - '{{ config.plugins.email.from }}'
                subject: '[Contact] Message from {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: contact-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            display: thank-you
content:
    items: '@self.modular'
---

