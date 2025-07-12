
const util = require('util');
const fs = require('fs-extra');
const { zokou } = require(__dirname + "/../framework/zokou");
const { format } = require(__dirname + "/../framework/mesfonctions");
const os = require("os");
const moment = require("moment-timezone");
const s = require(__dirname + "/../set");

zokou({ nomCom: "menu", categorie: "General" }, async (dest, zk, commandeOptions) => {
    let { ms, repondre } = commandeOptions;
    let { cm } = require(__dirname + "/../framework//zokou");

    const mode = (s.MODE_PUBLIC && s.MODE_PUBLIC.toLowerCase() === "oui") ? "Public" : "Privé";
    const date = moment().tz("Africa/Bamako").format("DD/MM/YYYY");
    const temps = moment().tz("Africa/Bamako").format("HH:mm:ss");

    const memLibre = format(os.totalmem() - os.freemem());
    const memTotale = format(os.totalmem());
    const plateforme = os.platform();

    let menuMsg = `
╭───────[ ✰ ${s.BOT_NAME || "ZOKOU-MD"} ✰ ]───────
│
│  ✰ Date       : ${date}
│  ✰ Time       : ${temps}
│
│  ✰ Prefix     : ${s.PREFIX}
│  ✰ Owner      : ${s.OWNER_NAME}
│  ✰ Mode       : ${mode}
│  ✰ Theme      : ELIE
│  ✰ Commands   : ${cm.length}
│  ✰ Memory     : ${memLibre} / ${memTotale}
│  ✰ Platform   : ${plateforme}
╰──────────────────────────────

╭───────[ COMMAND MENU ]───────
│
│ IA
│ ⌦ dalle
│ ⌦ gpt
│
│ GENERAL
│ ⌦ mods
│ ⌦ fullpp
│ ⌦ dev
│ ⌦ fullgroupp
│ ⌦ support
│ ⌦ help
│ ⌦ menu
│ ⌦ test
│ ⌦ alive
│ ⌦ voir
│
│ MODS
│ ⌦ tgs
│ ⌦ save
│ ⌦ crew
│ ⌦ mention
│ ⌦ join
│ ⌦ clear
│ ⌦ jid
│ ⌦ afk
│ ⌦ block
│ ⌦ left
│ ⌦ unblock
│ ⌦ plugin
│ ⌦ ban
│ ⌦ restart
│ ⌦ bangroup
│ ⌦ update
│ ⌦ sudo
│
│ GROUP
│ ⌦ kickall
│ ⌦ del
│ ⌦ onlyadmin
│ ⌦ info
│ ⌦ welcome
│ ⌦ antilink
│ ⌦ goodbye
│ ⌦ antibot
│ ⌦ antipromote
│ ⌦ group
│ ⌦ antidemote
│ ⌦ gname
│ ⌦ setwelcome
│ ⌦ gdesc
│ ⌦ testwelcome
│ ⌦ gpp
│ ⌦ setgoodbye
│ ⌦ hidetag
│ ⌦ testgoodbye
│ ⌦ automute
│ ⌦ tagall
│ ⌦ autounmute
│ ⌦ link
│ ⌦ fkick
│ ⌦ promote
│ ⌦ nsfw
│ ⌦ demote
│ ⌦ antispam
│ ⌦ remove
│ ⌦ warn
│
│ FUN
│ ⌦ ranime
│ ⌦ quote
│ ⌦ fancy
│ ⌦ rank
│ ⌦ profile
│ ⌦ toprank
│
│ SEARCH
│ ⌦ imdb
│ ⌦ stickersearch
│ ⌦ apk
│ ⌦ song
│ ⌦ img
│ ⌦ video
│ ⌦ lyrics
│ ⌦ yts
│
│ CONVERSION
│ ⌦ emomix
│ ⌦ write
│ ⌦ sticker
│ ⌦ photo
│ ⌦ scrop
│ ⌦ url
│ ⌦ take
│
│ AUDIO-EDIT
│ ⌦ deep
│ ⌦ smooth
│ ⌦ bass
│ ⌦ tempo
│ ⌦ reverse
│ ⌦ nightcore
│ ⌦ slow
│
│ IMAGE-EDIT
│ ⌦ shit
│ ⌦ invert
│ ⌦ wasted
│ ⌦ jail
│ ⌦ wanted
│ ⌦ affect
│ ⌦ trigger
│ ⌦ beautiful
│ ⌦ trash
│ ⌦ blur
│ ⌦ rip
│ ⌦ circle
│ ⌦ sepia
│ ⌦ facepalm
│ ⌦ rainbow
│ ⌦ greyscale
│ ⌦ hitler
│ ⌦ joke
│
│ GAMES
│ ⌦ riddle
│ ⌦ wcg
│ ⌦ quizz
│
│ HENTAI
│ ⌦ hwaifu
│ ⌦ blowjob
│ ⌦ trap
│ ⌦ hentaivid
│ ⌦ hneko
│
│ DOWNLOAD
│ ⌦ igdl
│ ⌦ tiktokaudio
│ ⌦ fbdl
│ ⌦ ytmp4
│ ⌦ tiktokvideo
│ ⌦ ytmp3
│
│ LOGO
│ ⌦ hacker
│ ⌦ purple
│ ⌦ dragonball
│ ⌦ gold
│ ⌦ naruto
│ ⌦ arena
│ ⌦ boom
│ ⌦ incandescent
│ ⌦ water
│
│ PARAMS
│ ⌦ parrain
│ ⌦ getvar
│ ⌦ setvar
│ ⌦ settings
│ ⌦ getallvar
│
│ REACTION
│ ⌦ bully
│ ⌦ highfive
│ ⌦ cuddle
│ ⌦ handhold
│ ⌦ cry
│ ⌦ nom
│ ⌦ hug
│ ⌦ bite
│ ⌦ awoo
│ ⌦ glomp
│ ⌦ kiss
│ ⌦ slap
│ ⌦ lick
│ ⌦ kill
│ ⌦ pat
│ ⌦ kick
│ ⌦ smug
│ ⌦ happy
│ ⌦ bonk
│ ⌦ wink
│ ⌦ yeet
│ ⌦ poke
│ ⌦ blush
│ ⌦ dance
│ ⌦ smile
│ ⌦ cringe
│ ⌦ wave
│
│ STICKCMD
│ ⌦ setcmd
│ ⌦ allcmd
│ ⌦ delcmd
│
│ TTS
│ ⌦ dit
│ ⌦ say
│ ⌦ itta
│
│ ENV
│ ⌦ setprefix
│ ⌦ warncount
│ ⌦ theme
│ ⌦ botname
│
│ WEEB
│ ⌦ waifu
│ ⌦ megumin
│ ⌦ neko
│ ⌦ cosplay
│ ⌦ shinobu
│ ⌦ couplepp
╰──────────────────────────────

Usage : .[commande]
Exemple : .menu
`;

    const link = s.IMAGE_MENU;
    try {
        zk.sendMessage(dest, {
            image: { url: link },
            caption: menuMsg,
            footer: "by Djalega++"
        }, { quoted: ms });
    } catch (e) {
        console.log("🥵 Menu erreur " + e);
        repondre("🥵 Menu erreur " + e);
    }
});
