#!/bin/bash

# Путь к файлу внутри дерева исходников Padavan
OPTION_FILE="/__w/padavan-builder/padavan-builder/padavan-ng/trunk/linux-3.4.x/drivers/usb/serial/option.c"

# Проверяем, существует ли файл (путь может зависеть от структуры репозитория в builder)
if [ -f "$OPTION_FILE" ]; then
    echo "Patching option.c for MEIG ML352-SM..."
    # Вставляем идентификатор после объявления структуры статическим массивом
    sed -i '/static const struct usb_device_id option_ids\[\] = {/a \	{ USB_DEVICE(0x1e0e, 0x9011) }, /* MEIG ML352-SM */' "$OPTION_FILE"
else
    echo "Error: option.c not found at $OPTION_FILE"
fi
