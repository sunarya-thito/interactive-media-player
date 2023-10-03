# interactive-media-player
Interactive Media Player adalah sebuah website
pemutar media yang mendukung interaksi user dengan
media yang sedang diputar.

## Fitur
- Media dihosting di YouTube jadi tidak perlu
  khawatir dengan kapasitas penyimpanan.
- Pemutar media menggunakan YouTube player yang
  sudah familiar.

## Cara Menggunakan
1. Clone repository ini.
2. Buka direktori `videos` di repository hasil clone.
3. Buat file json baru dengan format nama `video-<id>.json`.
   Video id bisa didapatkan dari url video YouTube. Contoh:
   `https://www.youtube.com/watch?v=<id>`.

## Demo
[Lihat Demo](https://sunarya-thito.github.io/interactive-media-player?v=SePNp6lxLWI)

## Skema JSON
```json
{
  "options": {
    "controls": "BOOLEAN",
    "rel": "NUMBER",
    "loopEnd": "NUMBER"
  },
  "layout": "BOTTOM|RIGHT|LEFT|TOP|FULL",
  "appearTime": "SECONDS",
  "buttons": [
    {
      "label": "STRING",
      "action": [
        {
          "type": "GO_TO|SEEK_TO",
          "value": "VIDEO_ID|SECONDS"
        }
      ],
      "action": {
        "type": "GO_TO|SEEK_TO",
        "value": "VIDEO_ID|SECONDS"
      }
    }
  ],
  "endAction": [
    {
      "type": "GO_TO|SEEK_TO",
      "value": "VIDEO_ID|SECONDS"
    }
  ],
    "endAction": {
        "type": "GO_TO|SEEK_TO",
        "value": "VIDEO_ID|SECONDS"
    }
}
```

### Options
#### controls
- Tipe: `BOOLEAN`
- Nilai: `true` atau `false`
- Deskripsi: Apakah video akan ditampilkan kontrolnya.
- Default: `true`

#### rel
- Tipe: `NUMBER`
- Nilai: `0` atau `1`
- Deskripsi: Apakah video yang direkomendasikan akan
  ditampilkan setelah video selesai diputar.
- Default: `0`

#### loopEnd
- Tipe: `NUMBER`
- Nilai: detik
- Deskripsi: Mundur berapa detik dari akhir video
  ketika video selesai diputar kemudian pause.
- Default: `0`

### Layout
- Tipe: `STRING`
- Nilai: `BOTTOM`, `RIGHT`, `LEFT`, `TOP`, atau `FULL`
- Deskripsi: Layout tombol-tombol yang ditampilkan.
- Default: `BOTTOM`

### Buttons
- Tipe: `ARRAY`
- Deskripsi: Tombol-tombol yang ditampilkan.
- Default: `[]`

#### Label
- Tipe: `STRING`
- Deskripsi: Label tombol.
- Default: `""`

#### Action
```json
{
  "type": "ACTION_TYPE",
  "value": "ACTION_VALUE"
}
```

##### Type
- Tipe: `STRING`
###### GO_TO
- Nilai: `GO_TO`
- Deskripsi: Pergi ke video lain.
- Value: `VIDEO_ID`
###### SEEK_TO
- Nilai: `SEEK_TO`
- Deskripsi: Mundur ke detik tertentu.
- Value: `SECONDS`

### End Action
- Tipe: `ARRAY`
- Deskripsi: Aksi yang dilakukan ketika video selesai diputar.
- Default: `[]`
