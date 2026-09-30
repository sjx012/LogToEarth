# LogToEarth

Turn a NavLog_v12 route into a Google Earth file in one click.

**Open the tool:** https://sjx012.github.io/LogToEarth/

Built by SJX12 for Starlux cadets flying at FTA.

---

## What it does

Paste the route code from your nav log and LogToEarth saves a `.kml` file you can open in Google Earth to inspect the route before you fly it.

The file can include:

| Option | What you get |
|---|---|
| Draw track at planned altitude | The route drawn in 3D at the altitudes from your nav log |
| Mark 10 NM inbound call | A marker 10 NM before each aerodrome. For YPPF it marks DMW or OHB instead, since YPPF is class D |
| Airspace | Class C steps and control zones around Adelaide, labelled VNC style (`C LL 2500`, `C 1500/SFC`) |
| Restricted and danger areas | Every restricted and danger area within 150 NM of YPPF, labelled with its designator and limits |

The file is named from your flight date, for example `NAV_1030.kml`, so saved files stay in order.

## How to use

1. In your nav log, copy the route code at the bottom of Table tab.
2. Open LogToEarth, paste the code, tick the options you want and click **Create KML file**.
3. Open [Google Earth on the web](https://earth.google.com/web/), go to **Projects**, then **New project**, then **Import KML file**, and choose the file you saved.

Works on Windows, macOS, iPad and Android in any modern browser.

## Route code format

The nav log builds this for you. You only need it if you want to write one by hand.

```
NAV1|YPPF-YPPF|0925|YPPF*,-34.78333,138.63333;SUB,-34.73667,138.71300,2500
```

| Part | Meaning |
|---|---|
| `NAV1` | Format version |
| `YPPF-YPPF` | Departure and destination |
| `0925` | Flight date as MMDD, used for the file name |
| `NAME,lat,lon,alt` | One waypoint. Altitude in feet is optional |
| `*` after a name | Marks an aerodrome, so it gets an inbound call marker |

Waypoints are separated by `;`.

## Privacy

Everything runs inside your own browser. Your route is never uploaded or stored anywhere, and the KML file is created on your computer.

## Airspace data

Airspace is based on the XcAustralia OpenAir file **valid 09 July 2026** and covers 150 NM around YPPF. It is simplified for planning and does not update itself. After each AIRAC change it may be out of date until this page is updated.

## Disclaimer

LogToEarth is a planning aid only. It is not an official source of aeronautical information and does not replace the current VTC, VNC, ERSA or NOTAMs. Always check every waypoint and airspace boundary against current official charts before flight.

## Credits

* Airspace data from XcAustralia (OpenAir format)
* Chart lettering drawn from Liberation Sans Bold, licensed under the SIL Open Font License 1.1
* Interface font: Fira Code, via Google Fonts
* Google Earth is a trademark of Google LLC. This project is not affiliated with or endorsed by Google.
