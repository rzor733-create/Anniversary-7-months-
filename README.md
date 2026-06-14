<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Cozy Calico Cat - Kallita Room</title>
    <style>
        :root {
            --bg-color: #F0E6EF;
            --panel-color: rgba(255, 255, 255, 0.85);
            --text-color: #6C5B7B;
            --accent-color: #F8B195;
            --border-color: #C06C84;
        }
        * {
            box-sizing: border-box;
            user-select: none;
            -webkit-user-select: none;
            margin: 0;
            padding: 0;
        }
        body {
            background-color: var(--bg-color);
            font-family: 'Courier New', Courier, monospace;
            font-weight: bold;
            color: var(--text-color);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            height: 100vh;
            overflow: hidden;
            padding: 4px;
            transition: background-color 2s ease;
        }
        #game-container {
            position: relative;
            width: min(98vw, 96vh * 1.3333);
            max-width: 1200px;
            aspect-ratio: 4/3;
            background: #fff;
            border: 6px solid var(--border-color);
            border-radius: 12px;
            box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
            overflow: hidden;
        }
        canvas {
            width: 100%;
            height: 100%;
            display: block;
            image-rendering: pixelated;
            image-rendering: crisp-edges;
        }
        #ui-layer {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            padding: 8px;
        }
        .interactive {
            pointer-events: auto;
        }
        .top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
        }
        .btn {
            background: var(--panel-color);
            border: 3px solid var(--text-color);
            border-radius: 8px;
            color: var(--text-color);
            padding: 6px 12px;
            font-family: inherit;
            font-weight: bold;
            font-size: 14px;
            cursor: pointer;
            box-shadow: 0 4px 0 var(--text-color);
            transition: transform 0.1s, box-shadow 0.1s;
            display: flex;
            align-items: center;
            gap: 6px;
        }
        .btn:active {
            transform: translateY(4px);
            box-shadow: 0 0 0 var(--text-color);
        }
        #audio-toggle {
            padding: 3px 7px;
            font-size: 10px;
            border-width: 2px;
            box-shadow: 0 2px 0 var(--text-color);
            border-radius: 6px;
            gap: 3px;
            min-width: auto;
        }
        #audio-toggle:active {
            transform: translateY(2px);
            box-shadow: 0 0 0 var(--text-color);
        }
        .bottom-bar {
            display: flex;
            justify-content: center;
            gap: 10px;
            width: 100%;
            margin-bottom: 4px;
            flex-wrap: wrap;
        }
