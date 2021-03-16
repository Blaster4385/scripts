
#!/bin/bash
#
# Copyright (C) 2020 Blaster4385.
# All rights reserved.

# Telegram
CHATID="$CHANNEL_ID" # Group/channel chatid (use rose/userbot to get it)
TELEGRAM_TOKEN="${TG_TOKEN}"

Version=v7.5
Device=RMX1851
Magisk=No
Clog=https://github.com/Blaster4385/IllusionX_RMX1851/releases/${Version}

# Export Telegram.sh
TELEGRAM_FOLDER="${HOME}"/telegram
if ! [ -d "${TELEGRAM_FOLDER}" ]; then
    git clone https://github.com/fabianonline/telegram.sh/ "${TELEGRAM_FOLDER}"
fi

TELEGRAM="${TELEGRAM_FOLDER}"/telegram

mkdir download
cd download
wget  "https://github.com/Blaster4385/IllusionX_RMX1851/releases/download/${Version}/IllusionX_${Version}.zip"
cd ..
tg_ship()
{
"${TELEGRAM}" -f "download/IllusionX_${Version}.zip" -t "${TELEGRAM_TOKEN}" -c "${CHATID}" -H \
    "$(
                for POST in "${@}"; do
                        echo "${POST}"
                done
    )"
}

tg_ship "  <b>-------New Release For ${Device}-------</b>    " \
    "<b>Version-:</b> ${Version}" \
    "<b>Magisk Required-:</b> ${Magisk}" \
    "<b>Changelog-:</b> ${Clog}"
