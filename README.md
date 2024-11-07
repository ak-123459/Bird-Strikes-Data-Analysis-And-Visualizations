<!DOCTYPE html>

<html lang="en">
<head><meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<title>BirdStrikeDataAnalysis</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<style type="text/css">
    pre { line-height: 125%; }
td.linenos .normal { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
span.linenos { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
td.linenos .special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
span.linenos.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
.highlight .hll { background-color: var(--jp-cell-editor-active-background) }
.highlight { background: var(--jp-cell-editor-background); color: var(--jp-mirror-editor-variable-color) }
.highlight .c { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment */
.highlight .err { color: var(--jp-mirror-editor-error-color) } /* Error */
.highlight .k { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword */
.highlight .o { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator */
.highlight .p { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation */
.highlight .ch { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Multiline */
.highlight .cp { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Preproc */
.highlight .cpf { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Single */
.highlight .cs { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Special */
.highlight .kc { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Pseudo */
.highlight .kr { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Type */
.highlight .m { color: var(--jp-mirror-editor-number-color) } /* Literal.Number */
.highlight .s { color: var(--jp-mirror-editor-string-color) } /* Literal.String */
.highlight .ow { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator.Word */
.highlight .pm { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation.Marker */
.highlight .w { color: var(--jp-mirror-editor-variable-color) } /* Text.Whitespace */
.highlight .mb { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Bin */
.highlight .mf { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Float */
.highlight .mh { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Hex */
.highlight .mi { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer */
.highlight .mo { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Oct */
.highlight .sa { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Affix */
.highlight .sb { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Backtick */
.highlight .sc { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Char */
.highlight .dl { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Delimiter */
.highlight .sd { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Doc */
.highlight .s2 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Double */
.highlight .se { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Escape */
.highlight .sh { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Heredoc */
.highlight .si { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Interpol */
.highlight .sx { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Other */
.highlight .sr { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Regex */
.highlight .s1 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Single */
.highlight .ss { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Symbol */
.highlight .il { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer.Long */
  </style>
<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
 * Mozilla scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */
[data-jp-theme-scrollbars='true'] {
  scrollbar-color: rgb(var(--jp-scrollbar-thumb-color))
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar. These selectors
 * will match lower in the tree, and so will override the above */
[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
}

/* tiny scrollbar */

.jp-scrollbar-tiny {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
  scrollbar-width: thin;
}

/* tiny scrollbar */

.jp-scrollbar-tiny::-webkit-scrollbar,
.jp-scrollbar-tiny::-webkit-scrollbar-corner {
  background-color: transparent;
  height: 4px;
  width: 4px;
}

.jp-scrollbar-tiny::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:horizontal {
  border-left: 0 solid transparent;
  border-right: 0 solid transparent;
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:vertical {
  border-top: 0 solid transparent;
  border-bottom: 0 solid transparent;
}

/*
 * Lumino
 */

.lm-ScrollBar[data-orientation='horizontal'] {
  min-height: 16px;
  max-height: 16px;
  min-width: 45px;
  border-top: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] {
  min-width: 16px;
  max-width: 16px;
  min-height: 45px;
  border-left: 1px solid #a0a0a0;
}

.lm-ScrollBar-button {
  background-color: #f0f0f0;
  background-position: center center;
  min-height: 15px;
  max-height: 15px;
  min-width: 15px;
  max-width: 15px;
}

.lm-ScrollBar-button:hover {
  background-color: #dadada;
}

.lm-ScrollBar-button.lm-mod-active {
  background-color: #cdcdcd;
}

.lm-ScrollBar-track {
  background: #f0f0f0;
}

.lm-ScrollBar-thumb {
  background: #cdcdcd;
}

.lm-ScrollBar-thumb:hover {
  background: #bababa;
}

.lm-ScrollBar-thumb.lm-mod-active {
  background: #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal'] .lm-ScrollBar-thumb {
  height: 100%;
  min-width: 15px;
  border-left: 1px solid #a0a0a0;
  border-right: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] .lm-ScrollBar-thumb {
  width: 100%;
  min-height: 15px;
  border-top: 1px solid #a0a0a0;
  border-bottom: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-left);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-right);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-up);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-down);
  background-size: 17px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
}

.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.lm-AccordionPanel[data-orientation='horizontal'] > .lm-AccordionPanel-title {
  /* Title is rotated for horizontal accordion panel using CSS */
  display: block;
  transform-origin: top left;
  transform: rotate(-90deg) translate(-100%);
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-CommandPalette-search {
  flex: 0 0 auto;
}

.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}

.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}

.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}

.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.lm-close-icon {
  border: 1px solid transparent;
  background-color: transparent;
  position: absolute;
  z-index: 1;
  right: 3%;
  top: 0;
  bottom: 0;
  margin: auto;
  padding: 7px 0;
  display: none;
  vertical-align: middle;
  outline: 0;
  cursor: pointer;
}
.lm-close-icon:after {
  content: 'X';
  display: block;
  width: 15px;
  height: 15px;
  text-align: center;
  color: #000;
  font-weight: normal;
  font-size: 12px;
  cursor: pointer;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-DockPanel {
  z-index: 0;
}

.lm-DockPanel-widget {
  z-index: 0;
}

.lm-DockPanel-tabBar {
  z-index: 1;
}

.lm-DockPanel-handle {
  z-index: 2;
}

.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}

.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}

.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}

.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}

.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}

.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}

.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-Menu {
  z-index: 10000;
  position: absolute;
  white-space: nowrap;
  overflow-x: hidden;
  overflow-y: auto;
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}

.lm-Menu-item {
  display: table-row;
}

.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}

.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}

.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}

.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}

.lm-MenuBar-item {
  box-sizing: border-box;
}

.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}

.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}

.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}

.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}

.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-SplitPanel-child {
  z-index: 0;
}

.lm-SplitPanel-handle {
  z-index: 1;
}

.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}

.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}

.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}

.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}

.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}

.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
  align-items: flex-end;
}

.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
  align-items: flex-end;
}

.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}

.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}

.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}

.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
  touch-action: none; /* Disable native Drag/Drop */
}

.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}

.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}

.lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing: border-box;
}

.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}

.lm-TabBar-addButton.lm-mod-hidden {
  display: none !important;
}

.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}

.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}

.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}

.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

.lm-TabBar-tabLabel .lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing: border-box;
  background: inherit;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-TabPanel-tabBar {
  z-index: 1;
}

.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
}

.jp-Collapse-header {
  padding: 1px 12px;
  background-color: var(--jp-layout-color1);
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  align-items: center;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  text-transform: uppercase;
  user-select: none;
}

.jp-Collapser-icon {
  height: 16px;
}

.jp-Collapse-header-collapsed .jp-Collapser-icon {
  transform: rotate(-90deg);
  margin: auto 0;
}

.jp-Collapser-title {
  line-height: 25px;
}

.jp-Collapse-contents {
  padding: 0 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensureUiComponents() in @jupyterlab/buildutils */

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

/* Icons urls */

:root {
  --jp-icon-add-above: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzEzN18xOTQ5MikiPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGQ9Ik00Ljc1IDQuOTMwNjZINi42MjVWNi44MDU2NkM2LjYyNSA3LjAxMTkxIDYuNzkzNzUgNy4xODA2NiA3IDcuMTgwNjZDNy4yMDYyNSA3LjE4MDY2IDcuMzc1IDcuMDExOTEgNy4zNzUgNi44MDU2NlY0LjkzMDY2SDkuMjVDOS40NTYyNSA0LjkzMDY2IDkuNjI1IDQuNzYxOTEgOS42MjUgNC41NTU2NkM5LjYyNSA0LjM0OTQxIDkuNDU2MjUgNC4xODA2NiA5LjI1IDQuMTgwNjZINy4zNzVWMi4zMDU2NkM3LjM3NSAyLjA5OTQxIDcuMjA2MjUgMS45MzA2NiA3IDEuOTMwNjZDNi43OTM3NSAxLjkzMDY2IDYuNjI1IDIuMDk5NDEgNi42MjUgMi4zMDU2NlY0LjE4MDY2SDQuNzVDNC41NDM3NSA0LjE4MDY2IDQuMzc1IDQuMzQ5NDEgNC4zNzUgNC41NTU2NkM0LjM3NSA0Ljc2MTkxIDQuNTQzNzUgNC45MzA2NiA0Ljc1IDQuOTMwNjZaIiBmaWxsPSIjNjE2MTYxIiBzdHJva2U9IiM2MTYxNjEiIHN0cm9rZS13aWR0aD0iMC43Ii8+CjwvZz4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTExLjUgOS41VjExLjVMMi41IDExLjVWOS41TDExLjUgOS41Wk0xMiA4QzEyLjU1MjMgOCAxMyA4LjQ0NzcyIDEzIDlWMTJDMTMgMTIuNTUyMyAxMi41NTIzIDEzIDEyIDEzTDIgMTNDMS40NDc3MiAxMyAxIDEyLjU1MjMgMSAxMlY5QzEgOC40NDc3MiAxLjQ0NzcxIDggMiA4TDEyIDhaIiBmaWxsPSIjNjE2MTYxIi8+CjxkZWZzPgo8Y2xpcFBhdGggaWQ9ImNsaXAwXzEzN18xOTQ5MiI+CjxyZWN0IGNsYXNzPSJqcC1pY29uMyIgd2lkdGg9IjYiIGhlaWdodD0iNiIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0ibWF0cml4KC0xIDAgMCAxIDEwIDEuNTU1NjYpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==);
  --jp-icon-add-below: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzEzN18xOTQ5OCkiPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGQ9Ik05LjI1IDEwLjA2OTNMNy4zNzUgMTAuMDY5M0w3LjM3NSA4LjE5NDM0QzcuMzc1IDcuOTg4MDkgNy4yMDYyNSA3LjgxOTM0IDcgNy44MTkzNEM2Ljc5Mzc1IDcuODE5MzQgNi42MjUgNy45ODgwOSA2LjYyNSA4LjE5NDM0TDYuNjI1IDEwLjA2OTNMNC43NSAxMC4wNjkzQzQuNTQzNzUgMTAuMDY5MyA0LjM3NSAxMC4yMzgxIDQuMzc1IDEwLjQ0NDNDNC4zNzUgMTAuNjUwNiA0LjU0Mzc1IDEwLjgxOTMgNC43NSAxMC44MTkzTDYuNjI1IDEwLjgxOTNMNi42MjUgMTIuNjk0M0M2LjYyNSAxMi45MDA2IDYuNzkzNzUgMTMuMDY5MyA3IDEzLjA2OTNDNy4yMDYyNSAxMy4wNjkzIDcuMzc1IDEyLjkwMDYgNy4zNzUgMTIuNjk0M0w3LjM3NSAxMC44MTkzTDkuMjUgMTAuODE5M0M5LjQ1NjI1IDEwLjgxOTMgOS42MjUgMTAuNjUwNiA5LjYyNSAxMC40NDQzQzkuNjI1IDEwLjIzODEgOS40NTYyNSAxMC4wNjkzIDkuMjUgMTAuMDY5M1oiIGZpbGw9IiM2MTYxNjEiIHN0cm9rZT0iIzYxNjE2MSIgc3Ryb2tlLXdpZHRoPSIwLjciLz4KPC9nPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGZpbGwtcnVsZT0iZXZlbm9kZCIgY2xpcC1ydWxlPSJldmVub2RkIiBkPSJNMi41IDUuNUwyLjUgMy41TDExLjUgMy41TDExLjUgNS41TDIuNSA1LjVaTTIgN0MxLjQ0NzcyIDcgMSA2LjU1MjI4IDEgNkwxIDNDMSAyLjQ0NzcyIDEuNDQ3NzIgMiAyIDJMMTIgMkMxMi41NTIzIDIgMTMgMi40NDc3MiAxMyAzTDEzIDZDMTMgNi41NTIyOSAxMi41NTIzIDcgMTIgN0wyIDdaIiBmaWxsPSIjNjE2MTYxIi8+CjxkZWZzPgo8Y2xpcFBhdGggaWQ9ImNsaXAwXzEzN18xOTQ5OCI+CjxyZWN0IGNsYXNzPSJqcC1pY29uMyIgd2lkdGg9IjYiIGhlaWdodD0iNiIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0ibWF0cml4KDEgMS43NDg0NmUtMDcgMS43NDg0NmUtMDcgLTEgNCAxMy40NDQzKSIvPgo8L2NsaXBQYXRoPgo8L2RlZnM+Cjwvc3ZnPgo=);
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bell: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE2IDE2IiB2ZXJzaW9uPSIxLjEiPgogICA8cGF0aCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMzMzMzMzIgogICAgICBkPSJtOCAwLjI5Yy0xLjQgMC0yLjcgMC43My0zLjYgMS44LTEuMiAxLjUtMS40IDMuNC0xLjUgNS4yLTAuMTggMi4yLTAuNDQgNC0yLjMgNS4zbDAuMjggMS4zaDVjMC4wMjYgMC42NiAwLjMyIDEuMSAwLjcxIDEuNSAwLjg0IDAuNjEgMiAwLjYxIDIuOCAwIDAuNTItMC40IDAuNi0xIDAuNzEtMS41aDVsMC4yOC0xLjNjLTEuOS0wLjk3LTIuMi0zLjMtMi4zLTUuMy0wLjEzLTEuOC0wLjI2LTMuNy0xLjUtNS4yLTAuODUtMS0yLjItMS44LTMuNi0xLjh6bTAgMS40YzAuODggMCAxLjkgMC41NSAyLjUgMS4zIDAuODggMS4xIDEuMSAyLjcgMS4yIDQuNCAwLjEzIDEuNyAwLjIzIDMuNiAxLjMgNS4yaC0xMGMxLjEtMS42IDEuMi0zLjQgMS4zLTUuMiAwLjEzLTEuNyAwLjMtMy4zIDEuMi00LjQgMC41OS0wLjcyIDEuNi0xLjMgMi41LTEuM3ptLTAuNzQgMTJoMS41Yy0wLjAwMTUgMC4yOCAwLjAxNSAwLjc5LTAuNzQgMC43OS0wLjczIDAuMDAxNi0wLjcyLTAuNTMtMC43NC0wLjc5eiIgLz4KPC9zdmc+Cg==);
  --jp-icon-bug-dot: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiPgogICAgICAgIDxwYXRoIGZpbGwtcnVsZT0iZXZlbm9kZCIgY2xpcC1ydWxlPSJldmVub2RkIiBkPSJNMTcuMTkgOEgyMFYxMEgxNy45MUMxNy45NiAxMC4zMyAxOCAxMC42NiAxOCAxMVYxMkgyMFYxNEgxOC41SDE4VjE0LjAyNzVDMTUuNzUgMTQuMjc2MiAxNCAxNi4xODM3IDE0IDE4LjVDMTQgMTkuMjA4IDE0LjE2MzUgMTkuODc3OSAxNC40NTQ5IDIwLjQ3MzlDMTMuNzA2MyAyMC44MTE3IDEyLjg3NTcgMjEgMTIgMjFDOS43OCAyMSA3Ljg1IDE5Ljc5IDYuODEgMThINFYxNkg2LjA5QzYuMDQgMTUuNjcgNiAxNS4zNCA2IDE1VjE0SDRWMTJINlYxMUM2IDEwLjY2IDYuMDQgMTAuMzMgNi4wOSAxMEg0VjhINi44MUM3LjI2IDcuMjIgNy44OCA2LjU1IDguNjIgNi4wNEw3IDQuNDFMOC40MSAzTDEwLjU5IDUuMTdDMTEuMDQgNS4wNiAxMS41MSA1IDEyIDVDMTIuNDkgNSAxMi45NiA1LjA2IDEzLjQyIDUuMTdMMTUuNTkgM0wxNyA0LjQxTDE1LjM3IDYuMDRDMTYuMTIgNi41NSAxNi43NCA3LjIyIDE3LjE5IDhaTTEwIDE2SDE0VjE0SDEwVjE2Wk0xMCAxMkgxNFYxMEgxMFYxMloiIGZpbGw9IiM2MTYxNjEiLz4KICAgICAgICA8cGF0aCBkPSJNMjIgMTguNUMyMiAyMC40MzMgMjAuNDMzIDIyIDE4LjUgMjJDMTYuNTY3IDIyIDE1IDIwLjQzMyAxNSAxOC41QzE1IDE2LjU2NyAxNi41NjcgMTUgMTguNSAxNUMyMC40MzMgMTUgMjIgMTYuNTY3IDIyIDE4LjVaIiBmaWxsPSIjNjE2MTYxIi8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yMCA4aC0yLjgxYy0uNDUtLjc4LTEuMDctMS40NS0xLjgyLTEuOTZMMTcgNC40MSAxNS41OSAzbC0yLjE3IDIuMTdDMTIuOTYgNS4wNiAxMi40OSA1IDEyIDVjLS40OSAwLS45Ni4wNi0xLjQxLjE3TDguNDEgMyA3IDQuNDFsMS42MiAxLjYzQzcuODggNi41NSA3LjI2IDcuMjIgNi44MSA4SDR2MmgyLjA5Yy0uMDUuMzMtLjA5LjY2LS4wOSAxdjFINHYyaDJ2MWMwIC4zNC4wNC42Ny4wOSAxSDR2MmgyLjgxYzEuMDQgMS43OSAyLjk3IDMgNS4xOSAzczQuMTUtMS4yMSA1LjE5LTNIMjB2LTJoLTIuMDljLjA1LS4zMy4wOS0uNjYuMDktMXYtMWgydi0yaC0ydi0xYzAtLjM0LS4wNC0uNjctLjA5LTFIMjBWOHptLTYgOGgtNHYtMmg0djJ6bTAtNGgtNHYtMmg0djJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik05IDE2LjE3TDQuODMgMTJsLTEuNDIgMS40MUw5IDE5IDIxIDdsLTEuNDEtMS40MXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBzaGFwZS1yZW5kZXJpbmc9Imdlb21ldHJpY1ByZWNpc2lvbiI+CiAgICA8cGF0aCBkPSJNNi41OSwzLjQxTDIsOEw2LjU5LDEyLjZMOCwxMS4xOEw0LjgyLDhMOCw0LjgyTDYuNTksMy40MU0xMi40MSwzLjQxTDExLDQuODJMMTQuMTgsOEwxMSwxMS4xOEwxMi40MSwxMi42TDE3LDhMMTIuNDEsMy40MU0yMS41OSwxMS41OUwxMy41LDE5LjY4TDkuODMsMTZMOC40MiwxNy40MUwxMy41LDIyLjVMMjMsMTNMMjEuNTksMTEuNTlaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTExLjQgMTguNkw2LjggMTRMMTEuNCA5LjRMMTAgOEw0IDE0TDEwIDIwTDExLjQgMTguNlpNMTYuNiAxOC42TDIxLjIgMTRMMTYuNiA5LjRMMTggOEwyNCAxNEwxOCAyMEwxNi42IDE4LjZWMTguNloiLz4KCTwvZz4KPC9zdmc+Cg==);
  --jp-icon-collapse-all: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTggMmMxIDAgMTEgMCAxMiAwczIgMSAyIDJjMCAxIDAgMTEgMCAxMnMwIDItMiAyQzIwIDE0IDIwIDQgMjAgNFMxMCA0IDYgNGMwLTIgMS0yIDItMnoiIC8+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTE4IDhjMC0xLTEtMi0yLTJTNSA2IDQgNnMtMiAxLTIgMmMwIDEgMCAxMSAwIDEyczEgMiAyIDJjMSAwIDExIDAgMTIgMHMyLTEgMi0yYzAtMSAwLTExIDAtMTJ6bS0yIDB2MTJINFY4eiIgLz4KICAgICAgICA8cGF0aCBkPSJNNiAxM3YyaDh2LTJ6IiAvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1jb25zb2xlLWljb24tYmFja2dyb3VuZC1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtY29uc29sZS1pY29uLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIj4KICAgIDxwYXRoIGQ9Ik0xMDUgMTI3LjNoNDB2MTIuOGgtNDB6TTUxLjEgNzdMNzQgOTkuOWwtMjMuMyAyMy4zIDEwLjUgMTAuNSAyMy4zLTIzLjNMOTUgOTkuOSA4NC41IDg5LjQgNjEuNiA2Ni41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copyright: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDI0IDI0IiBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCI+CiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0xMS44OCw5LjE0YzEuMjgsMC4wNiwxLjYxLDEuMTUsMS42MywxLjY2aDEuNzljLTAuMDgtMS45OC0xLjQ5LTMuMTktMy40NS0zLjE5QzkuNjQsNy42MSw4LDksOCwxMi4xNCBjMCwxLjk0LDAuOTMsNC4yNCwzLjg0LDQuMjRjMi4yMiwwLDMuNDEtMS42NSwzLjQ0LTIuOTVoLTEuNzljLTAuMDMsMC41OS0wLjQ1LDEuMzgtMS42MywxLjQ0QzEwLjU1LDE0LjgzLDEwLDEzLjgxLDEwLDEyLjE0IEMxMCw5LjI1LDExLjI4LDkuMTYsMTEuODgsOS4xNHogTTEyLDJDNi40OCwyLDIsNi40OCwyLDEyczQuNDgsMTAsMTAsMTBzMTAtNC40OCwxMC0xMFMxNy41MiwyLDEyLDJ6IE0xMiwyMGMtNC40MSwwLTgtMy41OS04LTggczMuNTktOCw4LThzOCwzLjU5LDgsOFMxNi40MSwyMCwxMiwyMHoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-delete: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2cHgiIGhlaWdodD0iMTZweCI+CiAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIiAvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjI2MjYyIiBkPSJNNiAxOWMwIDEuMS45IDIgMiAyaDhjMS4xIDAgMi0uOSAyLTJWN0g2djEyek0xOSA0aC0zLjVsLTEtMWgtNWwtMSAxSDV2MmgxNFY0eiIgLz4KPC9zdmc+Cg==);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-duplicate: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTIuNzk5OTggMC44NzVIOC44OTU4MkM5LjIwMDYxIDAuODc1IDkuNDQ5OTggMS4xMzkxNCA5LjQ0OTk4IDEuNDYxOThDOS40NDk5OCAxLjc4NDgyIDkuMjAwNjEgMi4wNDg5NiA4Ljg5NTgyIDIuMDQ4OTZIMy4zNTQxNUMzLjA0OTM2IDIuMDQ4OTYgMi43OTk5OCAyLjMxMzEgMi43OTk5OCAyLjYzNTk0VjkuNjc5NjlDMi43OTk5OCAxMC4wMDI1IDIuNTUwNjEgMTAuMjY2NyAyLjI0NTgyIDEwLjI2NjdDMS45NDEwMyAxMC4yNjY3IDEuNjkxNjUgMTAuMDAyNSAxLjY5MTY1IDkuNjc5NjlWMi4wNDg5NkMxLjY5MTY1IDEuNDAzMjggMi4xOTA0IDAuODc1IDIuNzk5OTggMC44NzVaTTUuMzY2NjUgMTEuOVY0LjU1SDExLjA4MzNWMTEuOUg1LjM2NjY1Wk00LjE0MTY1IDQuMTQxNjdDNC4xNDE2NSAzLjY5MDYzIDQuNTA3MjggMy4zMjUgNC45NTgzMiAzLjMyNUgxMS40OTE3QzExLjk0MjcgMy4zMjUgMTIuMzA4MyAzLjY5MDYzIDEyLjMwODMgNC4xNDE2N1YxMi4zMDgzQzEyLjMwODMgMTIuNzU5NCAxMS45NDI3IDEzLjEyNSAxMS40OTE3IDEzLjEyNUg0Ljk1ODMyQzQuNTA3MjggMTMuMTI1IDQuMTQxNjUgMTIuNzU5NCA0LjE0MTY1IDEyLjMwODNWNC4xNDE2N1oiIGZpbGw9IiM2MTYxNjEiLz4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNOS40MzU3NCA4LjI2NTA3SDguMzY0MzFWOS4zMzY1QzguMzY0MzEgOS40NTQzNSA4LjI2Nzg4IDkuNTUwNzggOC4xNTAwMiA5LjU1MDc4QzguMDMyMTcgOS41NTA3OCA3LjkzNTc0IDkuNDU0MzUgNy45MzU3NCA5LjMzNjVWOC4yNjUwN0g2Ljg2NDMxQzYuNzQ2NDUgOC4yNjUwNyA2LjY1MDAyIDguMTY4NjQgNi42NTAwMiA4LjA1MDc4QzYuNjUwMDIgNy45MzI5MiA2Ljc0NjQ1IDcuODM2NSA2Ljg2NDMxIDcuODM2NUg3LjkzNTc0VjYuNzY1MDdDNy45MzU3NCA2LjY0NzIxIDguMDMyMTcgNi41NTA3OCA4LjE1MDAyIDYuNTUwNzhDOC4yNjc4OCA2LjU1MDc4IDguMzY0MzEgNi42NDcyMSA4LjM2NDMxIDYuNzY1MDdWNy44MzY1SDkuNDM1NzRDOS41NTM2IDcuODM2NSA5LjY1MDAyIDcuOTMyOTIgOS42NTAwMiA4LjA1MDc4QzkuNjUwMDIgOC4xNjg2NCA5LjU1MzYgOC4yNjUwNyA5LjQzNTc0IDguMjY1MDdaIiBmaWxsPSIjNjE2MTYxIiBzdHJva2U9IiM2MTYxNjEiIHN0cm9rZS13aWR0aD0iMC41Ii8+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-error: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj48Y2lyY2xlIGN4PSIxMiIgY3k9IjE5IiByPSIyIi8+PHBhdGggZD0iTTEwIDNoNHYxMmgtNHoiLz48L2c+CjxwYXRoIGZpbGw9Im5vbmUiIGQ9Ik0wIDBoMjR2MjRIMHoiLz4KPC9zdmc+Cg==);
  --jp-icon-expand-all: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTggMmMxIDAgMTEgMCAxMiAwczIgMSAyIDJjMCAxIDAgMTEgMCAxMnMwIDItMiAyQzIwIDE0IDIwIDQgMjAgNFMxMCA0IDYgNGMwLTIgMS0yIDItMnoiIC8+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTE4IDhjMC0xLTEtMi0yLTJTNSA2IDQgNnMtMiAxLTIgMmMwIDEgMCAxMSAwIDEyczEgMiAyIDJjMSAwIDExIDAgMTIgMHMyLTEgMi0yYzAtMSAwLTExIDAtMTJ6bS0yIDB2MTJINFY4eiIgLz4KICAgICAgICA8cGF0aCBkPSJNMTEgMTBIOXYzSDZ2MmgzdjNoMnYtM2gzdi0yaC0zeiIgLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-dot: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTE0LDEyVjE5Ljg4QzE0LjA0LDIwLjE4IDEzLjk0LDIwLjUgMTMuNzEsMjAuNzFDMTMuMzIsMjEuMSAxMi42OSwyMS4xIDEyLjMsMjAuNzFMMTAuMjksMTguN0MxMC4wNiwxOC40NyA5Ljk2LDE4LjE2IDEwLDE3Ljg3VjEySDkuOTdMNC4yMSw0LjYyQzMuODcsNC4xOSAzLjk1LDMuNTYgNC4zOCwzLjIyQzQuNTcsMy4wOCA0Ljc4LDMgNSwzVjNIMTlWM0MxOS4yMiwzIDE5LjQzLDMuMDggMTkuNjIsMy4yMkMyMC4wNSwzLjU2IDIwLjEzLDQuMTkgMTkuNzksNC42MkwxNC4wMywxMkgxNFoiIC8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWRvdCIgZmlsbD0iI0ZGRiI+CiAgICA8Y2lyY2xlIGN4PSIxOCIgY3k9IjE3IiByPSIzIj48L2NpcmNsZT4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-filter: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTE0LDEyVjE5Ljg4QzE0LjA0LDIwLjE4IDEzLjk0LDIwLjUgMTMuNzEsMjAuNzFDMTMuMzIsMjEuMSAxMi42OSwyMS4xIDEyLjMsMjAuNzFMMTAuMjksMTguN0MxMC4wNiwxOC40NyA5Ljk2LDE4LjE2IDEwLDE3Ljg3VjEySDkuOTdMNC4yMSw0LjYyQzMuODcsNC4xOSAzLjk1LDMuNTYgNC4zOCwzLjIyQzQuNTcsMy4wOCA0Ljc4LDMgNSwzVjNIMTlWM0MxOS4yMiwzIDE5LjQzLDMuMDggMTkuNjIsMy4yMkMyMC4wNSwzLjU2IDIwLjEzLDQuMTkgMTkuNzksNC42MkwxNC4wMywxMkgxNFoiIC8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-folder-favorite: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjRweCIgdmlld0JveD0iMCAwIDI0IDI0IiB3aWR0aD0iMjRweCIgZmlsbD0iIzAwMDAwMCI+CiAgPHBhdGggZD0iTTAgMGgyNHYyNEgwVjB6IiBmaWxsPSJub25lIi8+PHBhdGggY2xhc3M9ImpwLWljb24zIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxNjE2MSIgZD0iTTIwIDZoLThsLTItMkg0Yy0xLjEgMC0yIC45LTIgMnYxMmMwIDEuMS45IDIgMiAyaDE2YzEuMSAwIDItLjkgMi0yVjhjMC0xLjEtLjktMi0yLTJ6bS0yLjA2IDExTDE1IDE1LjI4IDEyLjA2IDE3bC43OC0zLjMzLTIuNTktMi4yNCAzLjQxLS4yOUwxNSA4bDEuMzQgMy4xNCAzLjQxLjI5LTIuNTkgMi4yNC43OCAzLjMzeiIvPgo8L3N2Zz4K);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-home: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjRweCIgdmlld0JveD0iMCAwIDI0IDI0IiB3aWR0aD0iMjRweCIgZmlsbD0iIzAwMDAwMCI+CiAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPjxwYXRoIGNsYXNzPSJqcC1pY29uMyBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xMCAyMHYtNmg0djZoNXYtOGgzTDEyIDMgMiAxMmgzdjh6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-info: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUwLjk3OCA1MC45NzgiPgoJPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KCQk8cGF0aCBkPSJNNDMuNTIsNy40NThDMzguNzExLDIuNjQ4LDMyLjMwNywwLDI1LjQ4OSwwQzE4LjY3LDAsMTIuMjY2LDIuNjQ4LDcuNDU4LDcuNDU4CgkJCWMtOS45NDMsOS45NDEtOS45NDMsMjYuMTE5LDAsMzYuMDYyYzQuODA5LDQuODA5LDExLjIxMiw3LjQ1NiwxOC4wMzEsNy40NThjMCwwLDAuMDAxLDAsMC4wMDIsMAoJCQljNi44MTYsMCwxMy4yMjEtMi42NDgsMTguMDI5LTcuNDU4YzQuODA5LTQuODA5LDcuNDU3LTExLjIxMiw3LjQ1Ny0xOC4wM0M1MC45NzcsMTguNjcsNDguMzI4LDEyLjI2Niw0My41Miw3LjQ1OHoKCQkJIE00Mi4xMDYsNDIuMTA1Yy00LjQzMiw0LjQzMS0xMC4zMzIsNi44NzItMTYuNjE1LDYuODcyaC0wLjAwMmMtNi4yODUtMC4wMDEtMTIuMTg3LTIuNDQxLTE2LjYxNy02Ljg3MgoJCQljLTkuMTYyLTkuMTYzLTkuMTYyLTI0LjA3MSwwLTMzLjIzM0MxMy4zMDMsNC40NCwxOS4yMDQsMiwyNS40ODksMmM2LjI4NCwwLDEyLjE4NiwyLjQ0LDE2LjYxNyw2Ljg3MgoJCQljNC40MzEsNC40MzEsNi44NzEsMTAuMzMyLDYuODcxLDE2LjYxN0M0OC45NzcsMzEuNzcyLDQ2LjUzNiwzNy42NzUsNDIuMTA2LDQyLjEwNXoiLz4KCQk8cGF0aCBkPSJNMjMuNTc4LDMyLjIxOGMtMC4wMjMtMS43MzQsMC4xNDMtMy4wNTksMC40OTYtMy45NzJjMC4zNTMtMC45MTMsMS4xMS0xLjk5NywyLjI3Mi0zLjI1MwoJCQljMC40NjgtMC41MzYsMC45MjMtMS4wNjIsMS4zNjctMS41NzVjMC42MjYtMC43NTMsMS4xMDQtMS40NzgsMS40MzYtMi4xNzVjMC4zMzEtMC43MDcsMC40OTUtMS41NDEsMC40OTUtMi41CgkJCWMwLTEuMDk2LTAuMjYtMi4wODgtMC43NzktMi45NzljLTAuNTY1LTAuODc5LTEuNTAxLTEuMzM2LTIuODA2LTEuMzY5Yy0xLjgwMiwwLjA1Ny0yLjk4NSwwLjY2Ny0zLjU1LDEuODMyCgkJCWMtMC4zMDEsMC41MzUtMC41MDMsMS4xNDEtMC42MDcsMS44MTRjLTAuMTM5LDAuNzA3LTAuMjA3LDEuNDMyLTAuMjA3LDIuMTc0aC0yLjkzN2MtMC4wOTEtMi4yMDgsMC40MDctNC4xMTQsMS40OTMtNS43MTkKCQkJYzEuMDYyLTEuNjQsMi44NTUtMi40ODEsNS4zNzgtMi41MjdjMi4xNiwwLjAyMywzLjg3NCwwLjYwOCw1LjE0MSwxLjc1OGMxLjI3OCwxLjE2LDEuOTI5LDIuNzY0LDEuOTUsNC44MTEKCQkJYzAsMS4xNDItMC4xMzcsMi4xMTEtMC40MSwyLjkxMWMtMC4zMDksMC44NDUtMC43MzEsMS41OTMtMS4yNjgsMi4yNDNjLTAuNDkyLDAuNjUtMS4wNjgsMS4zMTgtMS43MywyLjAwMgoJCQljLTAuNjUsMC42OTctMS4zMTMsMS40NzktMS45ODcsMi4zNDZjLTAuMjM5LDAuMzc3LTAuNDI5LDAuNzc3LTAuNTY1LDEuMTk5Yy0wLjE2LDAuOTU5LTAuMjE3LDEuOTUxLTAuMTcxLDIuOTc5CgkJCUMyNi41ODksMzIuMjE4LDIzLjU3OCwzMi4yMTgsMjMuNTc4LDMyLjIxOHogTTIzLjU3OCwzOC4yMnYtMy40ODRoMy4wNzZ2My40ODRIMjMuNTc4eiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaW5zcGVjdG9yLWljb24tY29sb3IganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtanNvbi1pY29uLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0Y5QTgyNSI+CiAgICA8cGF0aCBkPSJNMjAuMiAxMS44Yy0xLjYgMC0xLjcuNS0xLjcgMSAwIC40LjEuOS4xIDEuMy4xLjUuMS45LjEgMS4zIDAgMS43LTEuNCAyLjMtMy41IDIuM2gtLjl2LTEuOWguNWMxLjEgMCAxLjQgMCAxLjQtLjggMC0uMyAwLS42LS4xLTEgMC0uNC0uMS0uOC0uMS0xLjIgMC0xLjMgMC0xLjggMS4zLTItMS4zLS4yLTEuMy0uNy0xLjMtMiAwLS40LjEtLjguMS0xLjIuMS0uNC4xLS43LjEtMSAwLS44LS40LS43LTEuNC0uOGgtLjVWNC4xaC45YzIuMiAwIDMuNS43IDMuNSAyLjMgMCAuNC0uMS45LS4xIDEuMy0uMS41LS4xLjktLjEgMS4zIDAgLjUuMiAxIDEuNyAxdjEuOHpNMS44IDEwLjFjMS42IDAgMS43LS41IDEuNy0xIDAtLjQtLjEtLjktLjEtMS4zLS4xLS41LS4xLS45LS4xLTEuMyAwLTEuNiAxLjQtMi4zIDMuNS0yLjNoLjl2MS45aC0uNWMtMSAwLTEuNCAwLTEuNC44IDAgLjMgMCAuNi4xIDEgMCAuMi4xLjYuMSAxIDAgMS4zIDAgMS44LTEuMyAyQzYgMTEuMiA2IDExLjcgNiAxM2MwIC40LS4xLjgtLjEgMS4yLS4xLjMtLjEuNy0uMSAxIDAgLjguMy44IDEuNC44aC41djEuOWgtLjljLTIuMSAwLTMuNS0uNi0zLjUtMi4zIDAtLjQuMS0uOS4xLTEuMy4xLS41LjEtLjkuMS0xLjMgMC0uNS0uMi0xLTEuNy0xdi0xLjl6Ii8+CiAgICA8Y2lyY2xlIGN4PSIxMSIgY3k9IjEzLjgiIHI9IjIuMSIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSI4LjIiIHI9IjIuMSIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-julia: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDMyNSAzMDAiPgogIDxnIGNsYXNzPSJqcC1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjY2IzYzMzIj4KICAgIDxwYXRoIGQ9Ik0gMTUwLjg5ODQzOCAyMjUgQyAxNTAuODk4NDM4IDI2Ni40MjE4NzUgMTE3LjMyMDMxMiAzMDAgNzUuODk4NDM4IDMwMCBDIDM0LjQ3NjU2MiAzMDAgMC44OTg0MzggMjY2LjQyMTg3NSAwLjg5ODQzOCAyMjUgQyAwLjg5ODQzOCAxODMuNTc4MTI1IDM0LjQ3NjU2MiAxNTAgNzUuODk4NDM4IDE1MCBDIDExNy4zMjAzMTIgMTUwIDE1MC44OTg0MzggMTgzLjU3ODEyNSAxNTAuODk4NDM4IDIyNSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzM4OTgyNiI+CiAgICA8cGF0aCBkPSJNIDIzNy41IDc1IEMgMjM3LjUgMTE2LjQyMTg3NSAyMDMuOTIxODc1IDE1MCAxNjIuNSAxNTAgQyAxMjEuMDc4MTI1IDE1MCA4Ny41IDExNi40MjE4NzUgODcuNSA3NSBDIDg3LjUgMzMuNTc4MTI1IDEyMS4wNzgxMjUgMCAxNjIuNSAwIEMgMjAzLjkyMTg3NSAwIDIzNy41IDMzLjU3ODEyNSAyMzcuNSA3NSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzk1NThiMiI+CiAgICA8cGF0aCBkPSJNIDMyNC4xMDE1NjIgMjI1IEMgMzI0LjEwMTU2MiAyNjYuNDIxODc1IDI5MC41MjM0MzggMzAwIDI0OS4xMDE1NjIgMzAwIEMgMjA3LjY3OTY4OCAzMDAgMTc0LjEwMTU2MiAyNjYuNDIxODc1IDE3NC4xMDE1NjIgMjI1IEMgMTc0LjEwMTU2MiAxODMuNTc4MTI1IDIwNy42Nzk2ODggMTUwIDI0OS4xMDE1NjIgMTUwIEMgMjkwLjUyMzQzOCAxNTAgMzI0LjEwMTU2MiAxODMuNTc4MTI1IDMyNC4xMDE1NjIgMjI1Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgPGcgY2xhc3M9ImpwLWp1cHl0ZXItaWNvbi1jb2xvciIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgIDxnIGNsYXNzPSJqcC1qdXB5dGVyLWljb24tY29sb3IiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launch: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMzIgMzIiIHdpZHRoPSIzMiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yNiwyOEg2YTIuMDAyNywyLjAwMjcsMCwwLDEtMi0yVjZBMi4wMDI3LDIuMDAyNywwLDAsMSw2LDRIMTZWNkg2VjI2SDI2VjE2aDJWMjZBMi4wMDI3LDIuMDAyNywwLDAsMSwyNiwyOFoiLz4KICAgIDxwb2x5Z29uIHBvaW50cz0iMjAgMiAyMCA0IDI2LjU4NiA0IDE4IDEyLjU4NiAxOS40MTQgMTQgMjggNS40MTQgMjggMTIgMzAgMTIgMzAgMiAyMCAyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4K);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-move-down: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNMTIuNDcxIDcuNTI4OTlDMTIuNzYzMiA3LjIzNjg0IDEyLjc2MzIgNi43NjMxNiAxMi40NzEgNi40NzEwMVY2LjQ3MTAxQzEyLjE3OSA2LjE3OTA1IDExLjcwNTcgNi4xNzg4NCAxMS40MTM1IDYuNDcwNTRMNy43NSAxMC4xMjc1VjEuNzVDNy43NSAxLjMzNTc5IDcuNDE0MjEgMSA3IDFWMUM2LjU4NTc5IDEgNi4yNSAxLjMzNTc5IDYuMjUgMS43NVYxMC4xMjc1TDIuNTk3MjYgNi40NjgyMkMyLjMwMzM4IDYuMTczODEgMS44MjY0MSA2LjE3MzU5IDEuNTMyMjYgNi40Njc3NFY2LjQ2Nzc0QzEuMjM4MyA2Ljc2MTcgMS4yMzgzIDcuMjM4MyAxLjUzMjI2IDcuNTMyMjZMNi4yOTI4OSAxMi4yOTI5QzYuNjgzNDIgMTIuNjgzNCA3LjMxNjU4IDEyLjY4MzQgNy43MDcxMSAxMi4yOTI5TDEyLjQ3MSA3LjUyODk5WiIgZmlsbD0iIzYxNjE2MSIvPgo8L3N2Zz4K);
  --jp-icon-move-up: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNMS41Mjg5OSA2LjQ3MTAxQzEuMjM2ODQgNi43NjMxNiAxLjIzNjg0IDcuMjM2ODQgMS41Mjg5OSA3LjUyODk5VjcuNTI4OTlDMS44MjA5NSA3LjgyMDk1IDIuMjk0MjYgNy44MjExNiAyLjU4NjQ5IDcuNTI5NDZMNi4yNSAzLjg3MjVWMTIuMjVDNi4yNSAxMi42NjQyIDYuNTg1NzkgMTMgNyAxM1YxM0M3LjQxNDIxIDEzIDcuNzUgMTIuNjY0MiA3Ljc1IDEyLjI1VjMuODcyNUwxMS40MDI3IDcuNTMxNzhDMTEuNjk2NiA3LjgyNjE5IDEyLjE3MzYgNy44MjY0MSAxMi40Njc3IDcuNTMyMjZWNy41MzIyNkMxMi43NjE3IDcuMjM4MyAxMi43NjE3IDYuNzYxNyAxMi40Njc3IDYuNDY3NzRMNy43MDcxMSAxLjcwNzExQzcuMzE2NTggMS4zMTY1OCA2LjY4MzQyIDEuMzE2NTggNi4yOTI4OSAxLjcwNzExTDEuNTI4OTkgNi40NzEwMVoiIGZpbGw9IiM2MTYxNjEiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtbm90ZWJvb2staWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-numbering: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTQgMTlINlYxOS41SDVWMjAuNUg2VjIxSDRWMjJIN1YxOEg0VjE5Wk01IDEwSDZWNkg0VjdINVYxMFpNNCAxM0g1LjhMNCAxNS4xVjE2SDdWMTVINS4yTDcgMTIuOVYxMkg0VjEzWk05IDdWOUgyM1Y3SDlaTTkgMjFIMjNWMTlIOVYyMVpNOSAxNUgyM1YxM0g5VjE1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-offline-bolt: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDIuMDJjLTUuNTEgMC05Ljk4IDQuNDctOS45OCA5Ljk4czQuNDcgOS45OCA5Ljk4IDkuOTggOS45OC00LjQ3IDkuOTgtOS45OFMxNy41MSAyLjAyIDEyIDIuMDJ6TTExLjQ4IDIwdi02LjI2SDhMMTMgNHY2LjI2aDMuMzVMMTEuNDggMjB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-pdf: url(data:image/svg+xml;base64,PHN2ZwogICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyMiAyMiIgd2lkdGg9IjE2Ij4KICAgIDxwYXRoIHRyYW5zZm9ybT0icm90YXRlKDQ1KSIgY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0ZGMkEyQSIKICAgICAgIGQ9Im0gMjIuMzQ0MzY5LC0zLjAxNjM2NDIgaCA1LjYzODYwNCB2IDEuNTc5MjQzMyBoIC0zLjU0OTIyNyB2IDEuNTA4NjkyOTkgaCAzLjMzNzU3NiBWIDEuNjUwODE1NCBoIC0zLjMzNzU3NiB2IDMuNDM1MjYxMyBoIC0yLjA4OTM3NyB6IG0gLTcuMTM2NDQ0LDEuNTc5MjQzMyB2IDQuOTQzOTU0MyBoIDAuNzQ4OTIgcSAxLjI4MDc2MSwwIDEuOTUzNzAzLC0wLjYzNDk1MzUgMC42NzgzNjksLTAuNjM0OTUzNSAwLjY3ODM2OSwtMS44NDUxNjQxIDAsLTEuMjA0NzgzNTUgLTAuNjcyOTQyLC0xLjgzNDMxMDExIC0wLjY3Mjk0MiwtMC42Mjk1MjY1OSAtMS45NTkxMywtMC42Mjk1MjY1OSB6IG0gLTIuMDg5Mzc3LC0xLjU3OTI0MzMgaCAyLjIwMzM0MyBxIDEuODQ1MTY0LDAgMi43NDYwMzksMC4yNjU5MjA3IDAuOTA2MzAxLDAuMjYwNDkzNyAxLjU1MjEwOCwwLjg5MDAyMDMgMC41Njk4MywwLjU0ODEyMjMgMC44NDY2MDUsMS4yNjQ0ODAwNiAwLjI3Njc3NCwwLjcxNjM1NzgxIDAuMjc2Nzc0LDEuNjIyNjU4OTQgMCwwLjkxNzE1NTEgLTAuMjc2Nzc0LDEuNjM4OTM5OSAtMC4yNzY3NzUsMC43MTYzNTc4IC0wLjg0NjYwNSwxLjI2NDQ4IC0wLjY1MTIzNCwwLjYyOTUyNjYgLTEuNTYyOTYyLDAuODk1NDQ3MyAtMC45MTE3MjgsMC4yNjA0OTM3IC0yLjczNTE4NSwwLjI2MDQ5MzcgaCAtMi4yMDMzNDMgeiBtIC04LjE0NTg1NjUsMCBoIDMuNDY3ODIzIHEgMS41NDY2ODE2LDAgMi4zNzE1Nzg1LDAuNjg5MjIzIDAuODMwMzI0LDAuNjgzNzk2MSAwLjgzMDMyNCwxLjk1MzcwMzE0IDAsMS4yNzUzMzM5NyAtMC44MzAzMjQsMS45NjQ1NTcwNiBRIDkuOTg3MTk2MSwyLjI3NDkxNSA4LjQ0MDUxNDUsMi4yNzQ5MTUgSCA3LjA2MjA2ODQgViA1LjA4NjA3NjcgSCA0Ljk3MjY5MTUgWiBtIDIuMDg5Mzc2OSwxLjUxNDExOTkgdiAyLjI2MzAzOTQzIGggMS4xNTU5NDEgcSAwLjYwNzgxODgsMCAwLjkzODg2MjksLTAuMjkzMDU1NDcgMC4zMzEwNDQxLC0wLjI5ODQ4MjQxIDAuMzMxMDQ0MSwtMC44NDExNzc3MiAwLC0wLjU0MjY5NTMxIC0wLjMzMTA0NDEsLTAuODM1NzUwNzQgLTAuMzMxMDQ0MSwtMC4yOTMwNTU1IC0wLjkzODg2MjksLTAuMjkzMDU1NSB6IgovPgo8L3N2Zz4K);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iLTEwIC0xMCAxMzEuMTYxMzYxNjk0MzM1OTQgMTMyLjM4ODk5OTkzODk2NDg0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMzA2OTk4IiBkPSJNIDU0LjkxODc4NSw5LjE5Mjc0MjFlLTQgQyA1MC4zMzUxMzIsMC4wMjIyMTcyNyA0NS45NTc4NDYsMC40MTMxMzY5NyA0Mi4xMDYyODUsMS4wOTQ2NjkzIDMwLjc2MDA2OSwzLjA5OTE3MzEgMjguNzAwMDM2LDcuMjk0NzcxNCAyOC43MDAwMzUsMTUuMDMyMTY5IHYgMTAuMjE4NzUgaCAyNi44MTI1IHYgMy40MDYyNSBoIC0yNi44MTI1IC0xMC4wNjI1IGMgLTcuNzkyNDU5LDAgLTE0LjYxNTc1ODgsNC42ODM3MTcgLTE2Ljc0OTk5OTgsMTMuNTkzNzUgLTIuNDYxODE5OTgsMTAuMjEyOTY2IC0yLjU3MTAxNTA4LDE2LjU4NjAyMyAwLDI3LjI1IDEuOTA1OTI4Myw3LjkzNzg1MiA2LjQ1NzU0MzIsMTMuNTkzNzQ4IDE0LjI0OTk5OTgsMTMuNTkzNzUgaCA5LjIxODc1IHYgLTEyLjI1IGMgMCwtOC44NDk5MDIgNy42NTcxNDQsLTE2LjY1NjI0OCAxNi43NSwtMTYuNjU2MjUgaCAyNi43ODEyNSBjIDcuNDU0OTUxLDAgMTMuNDA2MjUzLC02LjEzODE2NCAxMy40MDYyNSwtMTMuNjI1IHYgLTI1LjUzMTI1IGMgMCwtNy4yNjYzMzg2IC02LjEyOTk4LC0xMi43MjQ3NzcxIC0xMy40MDYyNSwtMTMuOTM3NDk5NyBDIDY0LjI4MTU0OCwwLjMyNzk0Mzk3IDU5LjUwMjQzOCwtMC4wMjAzNzkwMyA1NC45MTg3ODUsOS4xOTI3NDIxZS00IFogbSAtMTQuNSw4LjIxODc1MDEyNTc5IGMgMi43Njk1NDcsMCA1LjAzMTI1LDIuMjk4NjQ1NiA1LjAzMTI1LDUuMTI0OTk5NiAtMmUtNiwyLjgxNjMzNiAtMi4yNjE3MDMsNS4wOTM3NSAtNS4wMzEyNSw1LjA5Mzc1IC0yLjc3OTQ3NiwtMWUtNiAtNS4wMzEyNSwtMi4yNzc0MTUgLTUuMDMxMjUsLTUuMDkzNzUgLTEwZS03LC0yLjgyNjM1MyAyLjI1MTc3NCwtNS4xMjQ5OTk2IDUuMDMxMjUsLTUuMTI0OTk5NiB6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2ZmZDQzYiIgZD0ibSA4NS42Mzc1MzUsMjguNjU3MTY5IHYgMTEuOTA2MjUgYyAwLDkuMjMwNzU1IC03LjgyNTg5NSwxNi45OTk5OTkgLTE2Ljc1LDE3IGggLTI2Ljc4MTI1IGMgLTcuMzM1ODMzLDAgLTEzLjQwNjI0OSw2LjI3ODQ4MyAtMTMuNDA2MjUsMTMuNjI1IHYgMjUuNTMxMjQ3IGMgMCw3LjI2NjM0NCA2LjMxODU4OCwxMS41NDAzMjQgMTMuNDA2MjUsMTMuNjI1MDA0IDguNDg3MzMxLDIuNDk1NjEgMTYuNjI2MjM3LDIuOTQ2NjMgMjYuNzgxMjUsMCA2Ljc1MDE1NSwtMS45NTQzOSAxMy40MDYyNTMsLTUuODg3NjEgMTMuNDA2MjUsLTEzLjYyNTAwNCBWIDg2LjUwMDkxOSBoIC0yNi43ODEyNSB2IC0zLjQwNjI1IGggMjYuNzgxMjUgMTMuNDA2MjU0IGMgNy43OTI0NjEsMCAxMC42OTYyNTEsLTUuNDM1NDA4IDEzLjQwNjI0MSwtMTMuNTkzNzUgMi43OTkzMywtOC4zOTg4ODYgMi42ODAyMiwtMTYuNDc1Nzc2IDAsLTI3LjI1IC0xLjkyNTc4LC03Ljc1NzQ0MSAtNS42MDM4NywtMTMuNTkzNzUgLTEzLjQwNjI0MSwtMTMuNTkzNzUgeiBtIC0xNS4wNjI1LDY0LjY1NjI1IGMgMi43Nzk0NzgsM2UtNiA1LjAzMTI1LDIuMjc3NDE3IDUuMDMxMjUsNS4wOTM3NDcgLTJlLTYsMi44MjYzNTQgLTIuMjUxNzc1LDUuMTI1MDA0IC01LjAzMTI1LDUuMTI1MDA0IC0yLjc2OTU1LDAgLTUuMDMxMjUsLTIuMjk4NjUgLTUuMDMxMjUsLTUuMTI1MDA0IDJlLTYsLTIuODE2MzMgMi4yNjE2OTcsLTUuMDkzNzQ3IDUuMDMxMjUsLTUuMDkzNzQ3IHoiLz4KPC9zdmc+Cg==);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-redo: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIi8+PHBhdGggZD0iTTE4LjQgMTAuNkMxNi41NSA4Ljk5IDE0LjE1IDggMTEuNSA4Yy00LjY1IDAtOC41OCAzLjAzLTkuOTYgNy4yMkwzLjkgMTZjMS4wNS0zLjE5IDQuMDUtNS41IDcuNi01LjUgMS45NSAwIDMuNzMuNzIgNS4xMiAxLjg4TDEzIDE2aDlWN2wtMy42IDMuNnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-share: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTSAxOCAyIEMgMTYuMzU0OTkgMiAxNSAzLjM1NDk5MDQgMTUgNSBDIDE1IDUuMTkwOTUyOSAxNS4wMjE3OTEgNS4zNzcxMjI0IDE1LjA1NjY0MSA1LjU1ODU5MzggTCA3LjkyMTg3NSA5LjcyMDcwMzEgQyA3LjM5ODUzOTkgOS4yNzc4NTM5IDYuNzMyMDc3MSA5IDYgOSBDIDQuMzU0OTkwNCA5IDMgMTAuMzU0OTkgMyAxMiBDIDMgMTMuNjQ1MDEgNC4zNTQ5OTA0IDE1IDYgMTUgQyA2LjczMjA3NzEgMTUgNy4zOTg1Mzk5IDE0LjcyMjE0NiA3LjkyMTg3NSAxNC4yNzkyOTcgTCAxNS4wNTY2NDEgMTguNDM5NDUzIEMgMTUuMDIxNTU1IDE4LjYyMTUxNCAxNSAxOC44MDgzODYgMTUgMTkgQyAxNSAyMC42NDUwMSAxNi4zNTQ5OSAyMiAxOCAyMiBDIDE5LjY0NTAxIDIyIDIxIDIwLjY0NTAxIDIxIDE5IEMgMjEgMTcuMzU0OTkgMTkuNjQ1MDEgMTYgMTggMTYgQyAxNy4yNjc0OCAxNiAxNi42MDE1OTMgMTYuMjc5MzI4IDE2LjA3ODEyNSAxNi43MjI2NTYgTCA4Ljk0MzM1OTQgMTIuNTU4NTk0IEMgOC45NzgyMDk1IDEyLjM3NzEyMiA5IDEyLjE5MDk1MyA5IDEyIEMgOSAxMS44MDkwNDcgOC45NzgyMDk1IDExLjYyMjg3OCA4Ljk0MzM1OTQgMTEuNDQxNDA2IEwgMTYuMDc4MTI1IDcuMjc5Mjk2OSBDIDE2LjYwMTQ2IDcuNzIyMTQ2MSAxNy4yNjc5MjMgOCAxOCA4IEMgMTkuNjQ1MDEgOCAyMSA2LjY0NTAwOTYgMjEgNSBDIDIxIDMuMzU0OTkwNCAxOS42NDUwMSAyIDE4IDIgeiBNIDE4IDQgQyAxOC41NjQxMjkgNCAxOSA0LjQzNTg3MDYgMTkgNSBDIDE5IDUuNTY0MTI5NCAxOC41NjQxMjkgNiAxOCA2IEMgMTcuNDM1ODcxIDYgMTcgNS41NjQxMjk0IDE3IDUgQyAxNyA0LjQzNTg3MDYgMTcuNDM1ODcxIDQgMTggNCB6IE0gNiAxMSBDIDYuNTY0MTI5NCAxMSA3IDExLjQzNTg3MSA3IDEyIEMgNyAxMi41NjQxMjkgNi41NjQxMjk0IDEzIDYgMTMgQyA1LjQzNTg3MDYgMTMgNSAxMi41NjQxMjkgNSAxMiBDIDUgMTEuNDM1ODcxIDUuNDM1ODcwNiAxMSA2IDExIHogTSAxOCAxOCBDIDE4LjU2NDEyOSAxOCAxOSAxOC40MzU4NzEgMTkgMTkgQyAxOSAxOS41NjQxMjkgMTguNTY0MTI5IDIwIDE4IDIwIEMgMTcuNDM1ODcxIDIwIDE3IDE5LjU2NDEyOSAxNyAxOSBDIDE3IDE4LjQzNTg3MSAxNy40MzU4NzEgMTggMTggMTggeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-table-rows: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMSw4SDNWNGgxOFY4eiBNMjEsMTBIM3Y0aDE4VjEweiBNMjEsMTZIM3Y0aDE4VjE2eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-tag: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjgiIGhlaWdodD0iMjgiIHZpZXdCb3g9IjAgMCA0MyAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTI4LjgzMzIgMTIuMzM0TDMyLjk5OTggMTYuNTAwN0wzNy4xNjY1IDEyLjMzNEgyOC44MzMyWiIvPgoJCTxwYXRoIGQ9Ik0xNi4yMDk1IDIxLjYxMDRDMTUuNjg3MyAyMi4xMjk5IDE0Ljg0NDMgMjIuMTI5OSAxNC4zMjQ4IDIxLjYxMDRMNi45ODI5IDE0LjcyNDVDNi41NzI0IDE0LjMzOTQgNi4wODMxMyAxMy42MDk4IDYuMDQ3ODYgMTMuMDQ4MkM1Ljk1MzQ3IDExLjUyODggNi4wMjAwMiA4LjYxOTQ0IDYuMDY2MjEgNy4wNzY5NUM2LjA4MjgxIDYuNTE0NzcgNi41NTU0OCA2LjA0MzQ3IDcuMTE4MDQgNi4wMzA1NUM5LjA4ODYzIDUuOTg0NzMgMTMuMjYzOCA1LjkzNTc5IDEzLjY1MTggNi4zMjQyNUwyMS43MzY5IDEzLjYzOUMyMi4yNTYgMTQuMTU4NSAyMS43ODUxIDE1LjQ3MjQgMjEuMjYyIDE1Ljk5NDZMMTYuMjA5NSAyMS42MTA0Wk05Ljc3NTg1IDguMjY1QzkuMzM1NTEgNy44MjU2NiA4LjYyMzUxIDcuODI1NjYgOC4xODI4IDguMjY1QzcuNzQzNDYgOC43MDU3MSA3Ljc0MzQ2IDkuNDE3MzMgOC4xODI4IDkuODU2NjdDOC42MjM4MiAxMC4yOTY0IDkuMzM1ODIgMTAuMjk2NCA5Ljc3NTg1IDkuODU2NjdDMTAuMjE1NiA5LjQxNzMzIDEwLjIxNTYgOC43MDUzMyA5Ljc3NTg1IDguMjY1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtdGVybWluYWwtaWNvbi1iYWNrZ3JvdW5kLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZSIgd2lkdGg9IjIwIiBoZWlnaHQ9IjIwIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyIDIpIiBmaWxsPSIjMzMzMzMzIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtdGVybWluYWwtaWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUtaW52ZXJzZSIgZD0iTTUuMDU2NjQgOC43NjE3MkM1LjA1NjY0IDguNTk3NjYgNS4wMzEyNSA4LjQ1MzEyIDQuOTgwNDcgOC4zMjgxMkM0LjkzMzU5IDguMTk5MjIgNC44NTU0NyA4LjA4MjAzIDQuNzQ2MDkgNy45NzY1NkM0LjY0MDYyIDcuODcxMDkgNC41IDcuNzc1MzkgNC4zMjQyMiA3LjY4OTQ1QzQuMTUyMzQgNy41OTk2MSAzLjk0MzM2IDcuNTExNzIgMy42OTcyNyA3LjQyNTc4QzMuMzAyNzMgNy4yODUxNiAyLjk0MzM2IDcuMTM2NzIgMi42MTkxNCA2Ljk4MDQ3QzIuMjk0OTIgNi44MjQyMiAyLjAxNzU4IDYuNjQyNTggMS43ODcxMSA2LjQzNTU1QzEuNTYwNTUgNi4yMjg1MiAxLjM4NDc3IDUuOTg4MjggMS4yNTk3NyA1LjcxNDg0QzEuMTM0NzcgNS40Mzc1IDEuMDcyMjcgNS4xMDkzOCAxLjA3MjI3IDQuNzMwNDdDMS4wNzIyNyA0LjM5ODQ0IDEuMTI4OTEgNC4wOTU3IDEuMjQyMTkgMy44MjIyN0MxLjM1NTQ3IDMuNTQ0OTIgMS41MTU2MiAzLjMwNDY5IDEuNzIyNjYgMy4xMDE1NkMxLjkyOTY5IDIuODk4NDQgMi4xNzk2OSAyLjczNDM3IDIuNDcyNjYgMi42MDkzOEMyLjc2NTYyIDIuNDg0MzggMy4wOTE4IDIuNDA0MyAzLjQ1MTE3IDIuMzY5MTRWMS4xMDkzOEg0LjM4ODY3VjIuMzgwODZDNC43NDAyMyAyLjQyNzczIDUuMDU2NjQgMi41MjM0NCA1LjMzNzg5IDIuNjY3OTdDNS42MTkxNCAyLjgxMjUgNS44NTc0MiAzLjAwMTk1IDYuMDUyNzMgMy4yMzYzM0M2LjI1MTk1IDMuNDY2OCA2LjQwNDMgMy43NDAyMyA2LjUwOTc3IDQuMDU2NjRDNi42MTkxNCA0LjM2OTE0IDYuNjczODMgNC43MjA3IDYuNjczODMgNS4xMTEzM0g1LjA0NDkyQzUuMDQ0OTIgNC42Mzg2NyA0LjkzNzUgNC4yODEyNSA0LjcyMjY2IDQuMDM5MDZDNC41MDc4MSAzLjc5Mjk3IDQuMjE2OCAzLjY2OTkyIDMuODQ5NjEgMy42Njk5MkMzLjY1MDM5IDMuNjY5OTIgMy40NzY1NiAzLjY5NzI3IDMuMzI4MTIgMy43NTE5NUMzLjE4MzU5IDMuODAyNzMgMy4wNjQ0NSAzLjg3Njk1IDIuOTcwNyAzLjk3NDYxQzIuODc2OTUgNC4wNjgzNiAyLjgwNjY0IDQuMTc5NjkgMi43NTk3NyA0LjMwODU5QzIuNzE2OCA0LjQzNzUgMi42OTUzMSA0LjU3ODEyIDIuNjk1MzEgNC43MzA0N0MyLjY5NTMxIDQuODgyODEgMi43MTY4IDUuMDE5NTMgMi43NTk3NyA1LjE0MDYyQzIuODA2NjQgNS4yNTc4MSAyLjg4MjgxIDUuMzY3MTkgMi45ODgyOCA1LjQ2ODc1QzMuMDk3NjYgNS41NzAzMSAzLjI0MDIzIDUuNjY3OTcgMy40MTYwMiA1Ljc2MTcyQzMuNTkxOCA1Ljg1MTU2IDMuODEwNTUgNS45NDMzNiA0LjA3MjI3IDYuMDM3MTFDNC40NjY4IDYuMTg1NTUgNC44MjQyMiA2LjMzOTg0IDUuMTQ0NTMgNi41QzUuNDY0ODQgNi42NTYyNSA1LjczODI4IDYuODM5ODQgNS45NjQ4NCA3LjA1MDc4QzYuMTk1MzEgNy4yNTc4MSA2LjM3MTA5IDcuNSA2LjQ5MjE5IDcuNzc3MzRDNi42MTcxOSA4LjA1MDc4IDYuNjc5NjkgOC4zNzUgNi42Nzk2OSA4Ljc1QzYuNjc5NjkgOS4wOTM3NSA2LjYyMzA1IDkuNDA0MyA2LjUwOTc3IDkuNjgxNjRDNi4zOTY0OCA5Ljk1NTA4IDYuMjM0MzggMTAuMTkxNCA2LjAyMzQ0IDEwLjM5MDZDNS44MTI1IDEwLjU4OTggNS41NTg1OSAxMC43NSA1LjI2MTcyIDEwLjg3MTFDNC45NjQ4NCAxMC45ODgzIDQuNjMyODEgMTEuMDY0NSA0LjI2NTYyIDExLjA5OTZWMTIuMjQ4SDMuMzMzOThWMTEuMDk5NkMzLjAwMTk1IDExLjA2ODQgMi42Nzk2OSAxMC45OTYxIDIuMzY3MTkgMTAuODgyOEMyLjA1NDY5IDEwLjc2NTYgMS43NzczNCAxMC41OTc3IDEuNTM1MTYgMTAuMzc4OUMxLjI5Njg4IDEwLjE2MDIgMS4xMDU0NyA5Ljg4NDc3IDAuOTYwOTM4IDkuNTUyNzNDMC44MTY0MDYgOS4yMTY4IDAuNzQ0MTQxIDguODE0NDUgMC43NDQxNDEgOC4zNDU3SDIuMzc4OTFDMi4zNzg5MSA4LjYyNjk1IDIuNDE5OTIgOC44NjMyOCAyLjUwMTk1IDkuMDU0NjlDMi41ODM5OCA5LjI0MjE5IDIuNjg5NDUgOS4zOTI1OCAyLjgxODM2IDkuNTA1ODZDMi45NTExNyA5LjYxNTIzIDMuMTAxNTYgOS42OTMzNiAzLjI2OTUzIDkuNzQwMjNDMy40Mzc1IDkuNzg3MTEgMy42MDkzOCA5LjgxMDU1IDMuNzg1MTYgOS44MTA1NUM0LjIwMzEyIDkuODEwNTUgNC41MTk1MyA5LjcxMjg5IDQuNzM0MzggOS41MTc1OEM0Ljk0OTIyIDkuMzIyMjcgNS4wNTY2NCA5LjA3MDMxIDUuMDU2NjQgOC43NjE3MlpNMTMuNDE4IDEyLjI3MTVIOC4wNzQyMlYxMUgxMy40MThWMTIuMjcxNVoiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMuOTUyNjQgNikiIGZpbGw9IndoaXRlIi8+Cjwvc3ZnPgo=);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtdGV4dC1lZGl0b3ItaWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xNSAxNUgzdjJoMTJ2LTJ6bTAtOEgzdjJoMTJWN3pNMyAxM2gxOHYtMkgzdjJ6bTAgOGgxOHYtMkgzdjJ6TTMgM3YyaDE4VjNIM3oiLz4KPC9zdmc+Cg==);
  --jp-icon-toc: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik03LDVIMjFWN0g3VjVNNywxM1YxMUgyMVYxM0g3TTQsNC41QTEuNSwxLjUgMCAwLDEgNS41LDZBMS41LDEuNSAwIDAsMSA0LDcuNUExLjUsMS41IDAgMCwxIDIuNSw2QTEuNSwxLjUgMCAwLDEgNCw0LjVNNCwxMC41QTEuNSwxLjUgMCAwLDEgNS41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMy41QTEuNSwxLjUgMCAwLDEgMi41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMC41TTcsMTlWMTdIMjFWMTlIN000LDE2LjVBMS41LDEuNSAwIDAsMSA1LjUsMThBMS41LDEuNSAwIDAsMSA0LDE5LjVBMS41LDEuNSAwIDAsMSAyLjUsMThBMS41LDEuNSAwIDAsMSA0LDE2LjVaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tree-view: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMiAxMVYzaC03djNIOVYzSDJ2OGg3VjhoMnYxMGg0djNoN3YtOGgtN3YzaC0yVjhoMnYzeiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-user: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE2IDdhNCA0IDAgMTEtOCAwIDQgNCAwIDAxOCAwek0xMiAxNGE3IDcgMCAwMC03IDdoMTRhNyA3IDAgMDAtNy03eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-users: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZlcnNpb249IjEuMSIgdmlld0JveD0iMCAwIDM2IDI0IiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPgogPGcgY2xhc3M9ImpwLWljb24zIiB0cmFuc2Zvcm09Im1hdHJpeCgxLjczMjcgMCAwIDEuNzMyNyAtMy42MjgyIC4wOTk1NzcpIiBmaWxsPSIjNjE2MTYxIj4KICA8cGF0aCB0cmFuc2Zvcm09Im1hdHJpeCgxLjUsMCwwLDEuNSwwLC02KSIgZD0ibTEyLjE4NiA3LjUwOThjLTEuMDUzNSAwLTEuOTc1NyAwLjU2NjUtMi40Nzg1IDEuNDEwMiAwLjc1MDYxIDAuMzEyNzcgMS4zOTc0IDAuODI2NDggMS44NzMgMS40NzI3aDMuNDg2M2MwLTEuNTkyLTEuMjg4OS0yLjg4MjgtMi44ODA5LTIuODgyOHoiLz4KICA8cGF0aCBkPSJtMjAuNDY1IDIuMzg5NWEyLjE4ODUgMi4xODg1IDAgMCAxLTIuMTg4NCAyLjE4ODUgMi4xODg1IDIuMTg4NSAwIDAgMS0yLjE4ODUtMi4xODg1IDIuMTg4NSAyLjE4ODUgMCAwIDEgMi4xODg1LTIuMTg4NSAyLjE4ODUgMi4xODg1IDAgMCAxIDIuMTg4NCAyLjE4ODV6Ii8+CiAgPHBhdGggdHJhbnNmb3JtPSJtYXRyaXgoMS41LDAsMCwxLjUsMCwtNikiIGQ9Im0zLjU4OTggOC40MjE5Yy0xLjExMjYgMC0yLjAxMzcgMC45MDExMS0yLjAxMzcgMi4wMTM3aDIuODE0NWMwLjI2Nzk3LTAuMzczMDkgMC41OTA3LTAuNzA0MzUgMC45NTg5OC0wLjk3ODUyLTAuMzQ0MzMtMC42MTY4OC0xLjAwMzEtMS4wMzUyLTEuNzU5OC0xLjAzNTJ6Ii8+CiAgPHBhdGggZD0ibTYuOTE1NCA0LjYyM2ExLjUyOTQgMS41Mjk0IDAgMCAxLTEuNTI5NCAxLjUyOTQgMS41Mjk0IDEuNTI5NCAwIDAgMS0xLjUyOTQtMS41Mjk0IDEuNTI5NCAxLjUyOTQgMCAwIDEgMS41Mjk0LTEuNTI5NCAxLjUyOTQgMS41Mjk0IDAgMCAxIDEuNTI5NCAxLjUyOTR6Ii8+CiAgPHBhdGggZD0ibTYuMTM1IDEzLjUzNWMwLTMuMjM5MiAyLjYyNTktNS44NjUgNS44NjUtNS44NjUgMy4yMzkyIDAgNS44NjUgMi42MjU5IDUuODY1IDUuODY1eiIvPgogIDxjaXJjbGUgY3g9IjEyIiBjeT0iMy43Njg1IiByPSIyLjk2ODUiLz4KIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-word: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KIDxnIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzQxNDE0MSI+CiAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiA8L2c+CiA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSguNDMgLjA0MDEpIiBmaWxsPSIjZmZmIj4KICA8cGF0aCBkPSJtNC4xNCA4Ljc2cTAuMDY4Mi0xLjg5IDIuNDItMS44OSAxLjE2IDAgMS42OCAwLjQyIDAuNTY3IDAuNDEgMC41NjcgMS4xNnYzLjQ3cTAgMC40NjIgMC41MTQgMC40NjIgMC4xMDMgMCAwLjItMC4wMjMxdjAuNzE0cS0wLjM5OSAwLjEwMy0wLjY1MSAwLjEwMy0wLjQ1MiAwLTAuNjkzLTAuMjItMC4yMzEtMC4yLTAuMjg0LTAuNjYyLTAuOTU2IDAuODcyLTIgMC44NzItMC45MDMgMC0xLjQ3LTAuNDcyLTAuNTI1LTAuNDcyLTAuNTI1LTEuMjYgMC0wLjI2MiAwLjA0NTItMC40NzIgMC4wNTY3LTAuMjIgMC4xMTYtMC4zNzggMC4wNjgyLTAuMTY4IDAuMjMxLTAuMzA0IDAuMTU4LTAuMTQ3IDAuMjYyLTAuMjQyIDAuMTE2LTAuMDkxNCAwLjM2OC0wLjE2OCAwLjI2Mi0wLjA5MTQgMC4zOTktMC4xMjYgMC4xMzYtMC4wNDUyIDAuNDcyLTAuMTAzIDAuMzM2LTAuMDU3OCAwLjUwNC0wLjA3OTggMC4xNTgtMC4wMjMxIDAuNTY3LTAuMDc5OCAwLjU1Ni0wLjA2ODIgMC43NzctMC4yMjEgMC4yMi0wLjE1MiAwLjIyLTAuNDQxdi0wLjI1MnEwLTAuNDMtMC4zNTctMC42NjItMC4zMzYtMC4yMzEtMC45NzYtMC4yMzEtMC42NjIgMC0wLjk5OCAwLjI2Mi0wLjMzNiAwLjI1Mi0wLjM5OSAwLjc5OHptMS44OSAzLjY4cTAuNzg4IDAgMS4yNi0wLjQxIDAuNTA0LTAuNDIgMC41MDQtMC45MDN2LTEuMDVxLTAuMjg0IDAuMTM2LTAuODYxIDAuMjMxLTAuNTY3IDAuMDkxNC0wLjk4NyAwLjE1OC0wLjQyIDAuMDY4Mi0wLjc2NiAwLjMyNi0wLjMzNiAwLjI1Mi0wLjMzNiAwLjcwNHQwLjMwNCAwLjcwNCAwLjg2MSAwLjI1MnoiIHN0cm9rZS13aWR0aD0iMS4wNSIvPgogIDxwYXRoIGQ9Im0xMCA0LjU2aDAuOTQ1djMuMTVxMC42NTEtMC45NzYgMS44OS0wLjk3NiAxLjE2IDAgMS44OSAwLjg0IDAuNjgyIDAuODQgMC42ODIgMi4zMSAwIDEuNDctMC43MDQgMi40Mi0wLjcwNCAwLjg4Mi0xLjg5IDAuODgyLTEuMjYgMC0xLjg5LTEuMDJ2MC43NjZoLTAuODV6bTIuNjIgMy4wNHEtMC43NDYgMC0xLjE2IDAuNjQtMC40NTIgMC42My0wLjQ1MiAxLjY4IDAgMS4wNSAwLjQ1MiAxLjY4dDEuMTYgMC42M3EwLjc3NyAwIDEuMjYtMC42MyAwLjQ5NC0wLjY0IDAuNDk0LTEuNjggMC0xLjA1LTAuNDcyLTEuNjgtMC40NjItMC42NC0xLjI2LTAuNjR6IiBzdHJva2Utd2lkdGg9IjEuMDUiLz4KICA8cGF0aCBkPSJtMi43MyAxNS44IDEzLjYgMC4wMDgxYzAuMDA2OSAwIDAtMi42IDAtMi42IDAtMC4wMDc4LTEuMTUgMC0xLjE1IDAtMC4wMDY5IDAtMC4wMDgzIDEuNS0wLjAwODMgMS41LTJlLTMgLTAuMDAxNC0xMS4zLTAuMDAxNC0xMS4zLTAuMDAxNGwtMC4wMDU5Mi0xLjVjMC0wLjAwNzgtMS4xNyAwLjAwMTMtMS4xNyAwLjAwMTN6IiBzdHJva2Utd2lkdGg9Ii45NzUiLz4KIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddAboveIcon {
  background-image: var(--jp-icon-add-above);
}

.jp-AddBelowIcon {
  background-image: var(--jp-icon-add-below);
}

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}

.jp-BellIcon {
  background-image: var(--jp-icon-bell);
}

.jp-BugDotIcon {
  background-image: var(--jp-icon-bug-dot);
}

.jp-BugIcon {
  background-image: var(--jp-icon-bug);
}

.jp-BuildIcon {
  background-image: var(--jp-icon-build);
}

.jp-CaretDownEmptyIcon {
  background-image: var(--jp-icon-caret-down-empty);
}

.jp-CaretDownEmptyThinIcon {
  background-image: var(--jp-icon-caret-down-empty-thin);
}

.jp-CaretDownIcon {
  background-image: var(--jp-icon-caret-down);
}

.jp-CaretLeftIcon {
  background-image: var(--jp-icon-caret-left);
}

.jp-CaretRightIcon {
  background-image: var(--jp-icon-caret-right);
}

.jp-CaretUpEmptyThinIcon {
  background-image: var(--jp-icon-caret-up-empty-thin);
}

.jp-CaretUpIcon {
  background-image: var(--jp-icon-caret-up);
}

.jp-CaseSensitiveIcon {
  background-image: var(--jp-icon-case-sensitive);
}

.jp-CheckIcon {
  background-image: var(--jp-icon-check);
}

.jp-CircleEmptyIcon {
  background-image: var(--jp-icon-circle-empty);
}

.jp-CircleIcon {
  background-image: var(--jp-icon-circle);
}

.jp-ClearIcon {
  background-image: var(--jp-icon-clear);
}

.jp-CloseIcon {
  background-image: var(--jp-icon-close);
}

.jp-CodeCheckIcon {
  background-image: var(--jp-icon-code-check);
}

.jp-CodeIcon {
  background-image: var(--jp-icon-code);
}

.jp-CollapseAllIcon {
  background-image: var(--jp-icon-collapse-all);
}

.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}

.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}

.jp-CopyrightIcon {
  background-image: var(--jp-icon-copyright);
}

.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}

.jp-DeleteIcon {
  background-image: var(--jp-icon-delete);
}

.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}

.jp-DuplicateIcon {
  background-image: var(--jp-icon-duplicate);
}

.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}

.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}

.jp-ErrorIcon {
  background-image: var(--jp-icon-error);
}

.jp-ExpandAllIcon {
  background-image: var(--jp-icon-expand-all);
}

.jp-ExtensionIcon {
  background-image: var(--jp-icon-extension);
}

.jp-FastForwardIcon {
  background-image: var(--jp-icon-fast-forward);
}

.jp-FileIcon {
  background-image: var(--jp-icon-file);
}

.jp-FileUploadIcon {
  background-image: var(--jp-icon-file-upload);
}

.jp-FilterDotIcon {
  background-image: var(--jp-icon-filter-dot);
}

.jp-FilterIcon {
  background-image: var(--jp-icon-filter);
}

.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}

.jp-FolderFavoriteIcon {
  background-image: var(--jp-icon-folder-favorite);
}

.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}

.jp-HomeIcon {
  background-image: var(--jp-icon-home);
}

.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}

.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}

.jp-InfoIcon {
  background-image: var(--jp-icon-info);
}

.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}

.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}

.jp-JuliaIcon {
  background-image: var(--jp-icon-julia);
}

.jp-JupyterFaviconIcon {
  background-image: var(--jp-icon-jupyter-favicon);
}

.jp-JupyterIcon {
  background-image: var(--jp-icon-jupyter);
}

.jp-JupyterlabWordmarkIcon {
  background-image: var(--jp-icon-jupyterlab-wordmark);
}

.jp-KernelIcon {
  background-image: var(--jp-icon-kernel);
}

.jp-KeyboardIcon {
  background-image: var(--jp-icon-keyboard);
}

.jp-LaunchIcon {
  background-image: var(--jp-icon-launch);
}

.jp-LauncherIcon {
  background-image: var(--jp-icon-launcher);
}

.jp-LineFormIcon {
  background-image: var(--jp-icon-line-form);
}

.jp-LinkIcon {
  background-image: var(--jp-icon-link);
}

.jp-ListIcon {
  background-image: var(--jp-icon-list);
}

.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}

.jp-MoveDownIcon {
  background-image: var(--jp-icon-move-down);
}

.jp-MoveUpIcon {
  background-image: var(--jp-icon-move-up);
}

.jp-NewFolderIcon {
  background-image: var(--jp-icon-new-folder);
}

.jp-NotTrustedIcon {
  background-image: var(--jp-icon-not-trusted);
}

.jp-NotebookIcon {
  background-image: var(--jp-icon-notebook);
}

.jp-NumberingIcon {
  background-image: var(--jp-icon-numbering);
}

.jp-OfflineBoltIcon {
  background-image: var(--jp-icon-offline-bolt);
}

.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}

.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}

.jp-PdfIcon {
  background-image: var(--jp-icon-pdf);
}

.jp-PythonIcon {
  background-image: var(--jp-icon-python);
}

.jp-RKernelIcon {
  background-image: var(--jp-icon-r-kernel);
}

.jp-ReactIcon {
  background-image: var(--jp-icon-react);
}

.jp-RedoIcon {
  background-image: var(--jp-icon-redo);
}

.jp-RefreshIcon {
  background-image: var(--jp-icon-refresh);
}

.jp-RegexIcon {
  background-image: var(--jp-icon-regex);
}

.jp-RunIcon {
  background-image: var(--jp-icon-run);
}

.jp-RunningIcon {
  background-image: var(--jp-icon-running);
}

.jp-SaveIcon {
  background-image: var(--jp-icon-save);
}

.jp-SearchIcon {
  background-image: var(--jp-icon-search);
}

.jp-SettingsIcon {
  background-image: var(--jp-icon-settings);
}

.jp-ShareIcon {
  background-image: var(--jp-icon-share);
}

.jp-SpreadsheetIcon {
  background-image: var(--jp-icon-spreadsheet);
}

.jp-StopIcon {
  background-image: var(--jp-icon-stop);
}

.jp-TabIcon {
  background-image: var(--jp-icon-tab);
}

.jp-TableRowsIcon {
  background-image: var(--jp-icon-table-rows);
}

.jp-TagIcon {
  background-image: var(--jp-icon-tag);
}

.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}

.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}

.jp-TocIcon {
  background-image: var(--jp-icon-toc);
}

.jp-TreeViewIcon {
  background-image: var(--jp-icon-tree-view);
}

.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}

.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}

.jp-UserIcon {
  background-image: var(--jp-icon-user);
}

.jp-UsersIcon {
  background-image: var(--jp-icon-users);
}

.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}

.jp-WordIcon {
  background-image: var(--jp-icon-word);
}

.jp-YamlIcon {
  background-image: var(--jp-icon-yaml);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

.jp-Icon,
.jp-MaterialIcon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-cover {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

/**
 * (DEPRECATED) Support for specific CSS icon sizes
 */

.jp-Icon-16 {
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-18 {
  background-size: 18px;
  min-width: 18px;
  min-height: 18px;
}

.jp-Icon-20 {
  background-size: 20px;
  min-width: 20px;
  min-height: 20px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.lm-TabBar .lm-TabBar-addButton {
  align-items: center;
  display: flex;
  padding: 4px;
  padding-bottom: 5px;
  margin-right: 1px;
  background-color: var(--jp-layout-color2);
}

.lm-TabBar .lm-TabBar-addButton:hover {
  background-color: var(--jp-layout-color1);
}

.lm-DockPanel-tabBar .lm-TabBar-tab {
  width: var(--jp-private-horizontal-tab-width);
}

.lm-DockPanel-tabBar .lm-TabBar-content {
  flex: unset;
}

.lm-DockPanel-tabBar[data-orientation='horizontal'] {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for icons as inline SVG HTMLElements
 */

/* recolor the primary elements of an icon */
.jp-icon0[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon1[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon2[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon3[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-accent0[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-accent1[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-accent2[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-accent3[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-accent4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-accent0[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-accent1[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-accent2[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-accent3[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-accent4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-none[fill] {
  fill: none;
}

.jp-icon-none[stroke] {
  stroke: none;
}

/* brand icon colors. Same for light and dark */
.jp-icon-brand0[fill] {
  fill: var(--jp-brand-color0);
}

.jp-icon-brand1[fill] {
  fill: var(--jp-brand-color1);
}

.jp-icon-brand2[fill] {
  fill: var(--jp-brand-color2);
}

.jp-icon-brand3[fill] {
  fill: var(--jp-brand-color3);
}

.jp-icon-brand4[fill] {
  fill: var(--jp-brand-color4);
}

.jp-icon-brand0[stroke] {
  stroke: var(--jp-brand-color0);
}

.jp-icon-brand1[stroke] {
  stroke: var(--jp-brand-color1);
}

.jp-icon-brand2[stroke] {
  stroke: var(--jp-brand-color2);
}

.jp-icon-brand3[stroke] {
  stroke: var(--jp-brand-color3);
}

.jp-icon-brand4[stroke] {
  stroke: var(--jp-brand-color4);
}

/* warn icon colors. Same for light and dark */
.jp-icon-warn0[fill] {
  fill: var(--jp-warn-color0);
}

.jp-icon-warn1[fill] {
  fill: var(--jp-warn-color1);
}

.jp-icon-warn2[fill] {
  fill: var(--jp-warn-color2);
}

.jp-icon-warn3[fill] {
  fill: var(--jp-warn-color3);
}

.jp-icon-warn0[stroke] {
  stroke: var(--jp-warn-color0);
}

.jp-icon-warn1[stroke] {
  stroke: var(--jp-warn-color1);
}

.jp-icon-warn2[stroke] {
  stroke: var(--jp-warn-color2);
}

.jp-icon-warn3[stroke] {
  stroke: var(--jp-warn-color3);
}

/* icon colors that contrast well with each other and most backgrounds */
.jp-icon-contrast0[fill] {
  fill: var(--jp-icon-contrast-color0);
}

.jp-icon-contrast1[fill] {
  fill: var(--jp-icon-contrast-color1);
}

.jp-icon-contrast2[fill] {
  fill: var(--jp-icon-contrast-color2);
}

.jp-icon-contrast3[fill] {
  fill: var(--jp-icon-contrast-color3);
}

.jp-icon-contrast0[stroke] {
  stroke: var(--jp-icon-contrast-color0);
}

.jp-icon-contrast1[stroke] {
  stroke: var(--jp-icon-contrast-color1);
}

.jp-icon-contrast2[stroke] {
  stroke: var(--jp-icon-contrast-color2);
}

.jp-icon-contrast3[stroke] {
  stroke: var(--jp-icon-contrast-color3);
}

.jp-icon-dot[fill] {
  fill: var(--jp-warn-color0);
}

.jp-jupyter-icon-color[fill] {
  fill: var(--jp-jupyter-icon-color, var(--jp-warn-color0));
}

.jp-notebook-icon-color[fill] {
  fill: var(--jp-notebook-icon-color, var(--jp-warn-color0));
}

.jp-json-icon-color[fill] {
  fill: var(--jp-json-icon-color, var(--jp-warn-color1));
}

.jp-console-icon-color[fill] {
  fill: var(--jp-console-icon-color, white);
}

.jp-console-icon-background-color[fill] {
  fill: var(--jp-console-icon-background-color, var(--jp-brand-color1));
}

.jp-terminal-icon-color[fill] {
  fill: var(--jp-terminal-icon-color, var(--jp-layout-color2));
}

.jp-terminal-icon-background-color[fill] {
  fill: var(
    --jp-terminal-icon-background-color,
    var(--jp-inverse-layout-color2)
  );
}

.jp-text-editor-icon-color[fill] {
  fill: var(--jp-text-editor-icon-color, var(--jp-inverse-layout-color3));
}

.jp-inspector-icon-color[fill] {
  fill: var(--jp-inspector-icon-color, var(--jp-inverse-layout-color3));
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* stylelint-disable selector-max-class, selector-max-compound-selectors */

/**
* TODO: come up with non css-hack solution for showing the busy icon on top
*  of the close icon
* CSS for complex behavior of close icon of tabs in the main area tabbar
*/
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}

.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

/* stylelint-enable selector-max-class, selector-max-compound-selectors */

/* CSS for icons in status bar */
#jp-main-statusbar .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

#jp-main-statusbar .jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* special handling for splash icon CSS. While the theme CSS reloads during
   splash, the splash icon can loose theming. To prevent that, we set a
   default for its color variable */
:root {
  --jp-warn-color0: var(--md-orange-700);
}

/* not sure what to do with this one, used in filebrowser listing */
.jp-DragIcon {
  margin-right: 4px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for alt colors for icons as inline SVG HTMLElements
 */

/* alt recolor the primary elements of an icon */
.jp-icon-alt .jp-icon0[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-alt .jp-icon1[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-alt .jp-icon2[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-alt .jp-icon3[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-alt .jp-icon4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-alt .jp-icon0[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-alt .jp-icon1[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-alt .jp-icon2[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-alt .jp-icon3[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-alt .jp-icon4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* alt recolor the accent elements of an icon */
.jp-icon-alt .jp-icon-accent0[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon-alt .jp-icon-accent1[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon-alt .jp-icon-accent2[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon-alt .jp-icon-accent3[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon-alt .jp-icon-accent4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-alt .jp-icon-accent0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon-alt .jp-icon-accent1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon-alt .jp-icon-accent2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon-alt .jp-icon-accent3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon-alt .jp-icon-accent4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-icon-hoverShow:not(:hover) .jp-icon-hoverShow-content {
  display: none !important;
}

/**
 * Support for hover colors for icons as inline SVG HTMLElements
 */

/**
 * regular colors
 */

/* recolor the primary elements of an icon */
.jp-icon-hover :hover .jp-icon0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon-hover :hover .jp-icon1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon-hover :hover .jp-icon2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon-hover :hover .jp-icon3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon-hover :hover .jp-icon4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon-hover :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon-hover :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon-hover :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon-hover :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-hover :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-hover :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-hover :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-hover :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-hover :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-hover :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-hover :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-hover :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-hover :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-hover :hover .jp-icon-none-hover[fill] {
  fill: none;
}

.jp-icon-hover :hover .jp-icon-none-hover[stroke] {
  stroke: none;
}

/**
 * inverse colors
 */

/* inverse recolor the primary elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[fill] {
  fill: var(--jp-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[fill] {
  fill: var(--jp-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[fill] {
  fill: var(--jp-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[fill] {
  fill: var(--jp-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* inverse recolor the accent elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `lm-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-HoverBox {
  position: fixed;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FormGroup-content fieldset {
  border: none;
  padding: 0;
  min-width: 0;
  width: 100%;
}

/* stylelint-disable selector-max-type */

.jp-FormGroup-content fieldset .jp-inputFieldWrapper input,
.jp-FormGroup-content fieldset .jp-inputFieldWrapper select,
.jp-FormGroup-content fieldset .jp-inputFieldWrapper textarea {
  font-size: var(--jp-content-font-size2);
  border-color: var(--jp-input-border-color);
  border-style: solid;
  border-radius: var(--jp-border-radius);
  border-width: 1px;
  padding: 6px 8px;
  background: none;
  color: var(--jp-ui-font-color0);
  height: inherit;
}

.jp-FormGroup-content fieldset input[type='checkbox'] {
  position: relative;
  top: 2px;
  margin-left: 0;
}

.jp-FormGroup-content button.jp-mod-styled {
  cursor: pointer;
}

.jp-FormGroup-content .checkbox label {
  cursor: pointer;
  font-size: var(--jp-content-font-size1);
}

.jp-FormGroup-content .jp-root > fieldset > legend {
  display: none;
}

.jp-FormGroup-content .jp-root > fieldset > p {
  display: none;
}

/** copy of `input.jp-mod-styled:focus` style */
.jp-FormGroup-content fieldset input:focus,
.jp-FormGroup-content fieldset select:focus {
  -moz-outline-radius: unset;
  outline: var(--jp-border-width) solid var(--md-blue-500);
  outline-offset: -1px;
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-FormGroup-content fieldset input:hover:not(:focus),
.jp-FormGroup-content fieldset select:hover:not(:focus) {
  background-color: var(--jp-border-color2);
}

/* stylelint-enable selector-max-type */

.jp-FormGroup-content .checkbox .field-description {
  /* Disable default description field for checkbox:
   because other widgets do not have description fields,
   we add descriptions to each widget on the field level.
  */
  display: none;
}

.jp-FormGroup-content #root__description {
  display: none;
}

.jp-FormGroup-content .jp-modifiedIndicator {
  width: 5px;
  background-color: var(--jp-brand-color2);
  margin-top: 0;
  margin-left: calc(var(--jp-private-settingeditor-modifier-indent) * -1);
  flex-shrink: 0;
}

.jp-FormGroup-content .jp-modifiedIndicator.jp-errorIndicator {
  background-color: var(--jp-error-color0);
  margin-right: 0.5em;
}

/* RJSF ARRAY style */

.jp-arrayFieldWrapper legend {
  font-size: var(--jp-content-font-size2);
  color: var(--jp-ui-font-color0);
  flex-basis: 100%;
  padding: 4px 0;
  font-weight: var(--jp-content-heading-font-weight);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-arrayFieldWrapper .field-description {
  padding: 4px 0;
  white-space: pre-wrap;
}

.jp-arrayFieldWrapper .array-item {
  width: 100%;
  border: 1px solid var(--jp-border-color2);
  border-radius: 4px;
  margin: 4px;
}

.jp-ArrayOperations {
  display: flex;
  margin-left: 8px;
}

.jp-ArrayOperationsButton {
  margin: 2px;
}

.jp-ArrayOperationsButton .jp-icon3[fill] {
  fill: var(--jp-ui-font-color0);
}

button.jp-ArrayOperationsButton.jp-mod-styled:disabled {
  cursor: not-allowed;
  opacity: 0.5;
}

/* RJSF form validation error */

.jp-FormGroup-content .validationErrors {
  color: var(--jp-error-color0);
}

/* Hide panel level error as duplicated the field level error */
.jp-FormGroup-content .panel.errors {
  display: none;
}

/* RJSF normal content (settings-editor) */

.jp-FormGroup-contentNormal {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.jp-FormGroup-contentNormal .jp-FormGroup-contentItem {
  margin-left: 7px;
  color: var(--jp-ui-font-color0);
}

.jp-FormGroup-contentNormal .jp-FormGroup-description {
  flex-basis: 100%;
  padding: 4px 7px;
}

.jp-FormGroup-contentNormal .jp-FormGroup-default {
  flex-basis: 100%;
  padding: 4px 7px;
}

.jp-FormGroup-contentNormal .jp-FormGroup-fieldLabel {
  font-size: var(--jp-content-font-size1);
  font-weight: normal;
  min-width: 120px;
}

.jp-FormGroup-contentNormal fieldset:not(:first-child) {
  margin-left: 7px;
}

.jp-FormGroup-contentNormal .field-array-of-string .array-item {
  /* Display `jp-ArrayOperations` buttons side-by-side with content except
    for small screens where flex-wrap will place them one below the other.
  */
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.jp-FormGroup-contentNormal .jp-objectFieldWrapper .form-group {
  padding: 2px 8px 2px var(--jp-private-settingeditor-modifier-indent);
  margin-top: 2px;
}

/* RJSF compact content (metadata-form) */

.jp-FormGroup-content.jp-FormGroup-contentCompact {
  width: 100%;
}

.jp-FormGroup-contentCompact .form-group {
  display: flex;
  padding: 0.5em 0.2em 0.5em 0;
}

.jp-FormGroup-contentCompact
  .jp-FormGroup-compactTitle
  .jp-FormGroup-description {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color2);
}

.jp-FormGroup-contentCompact .jp-FormGroup-fieldLabel {
  padding-bottom: 0.3em;
}

.jp-FormGroup-contentCompact .jp-inputFieldWrapper .form-control {
  width: 100%;
  box-sizing: border-box;
}

.jp-FormGroup-contentCompact .jp-arrayFieldWrapper .jp-FormGroup-compactTitle {
  padding-bottom: 7px;
}

.jp-FormGroup-contentCompact
  .jp-objectFieldWrapper
  .jp-objectFieldWrapper
  .form-group {
  padding: 2px 8px 2px var(--jp-private-settingeditor-modifier-indent);
  margin-top: 2px;
}

.jp-FormGroup-contentCompact ul.error-detail {
  margin-block-start: 0.5em;
  margin-block-end: 0.5em;
  padding-inline-start: 1em;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-SidePanel {
  display: flex;
  flex-direction: column;
  min-width: var(--jp-sidebar-min-width);
  overflow-y: auto;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size1);
}

.jp-SidePanel-header {
  flex: 0 0 auto;
  display: flex;
  border-bottom: var(--jp-border-width) solid var(--jp-border-color2);
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin: 0;
  padding: 2px;
  text-transform: uppercase;
}

.jp-SidePanel-toolbar {
  flex: 0 0 auto;
}

.jp-SidePanel-content {
  flex: 1 1 auto;
}

.jp-SidePanel-toolbar,
.jp-AccordionPanel-toolbar {
  height: var(--jp-private-toolbar-height);
}

.jp-SidePanel-toolbar.jp-Toolbar-micro {
  display: none;
}

.lm-AccordionPanel .jp-AccordionPanel-title {
  box-sizing: border-box;
  line-height: 25px;
  margin: 0;
  display: flex;
  align-items: center;
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  font-size: var(--jp-ui-font-size0);
}

.jp-AccordionPanel-title {
  cursor: pointer;
  user-select: none;
  -moz-user-select: none;
  -webkit-user-select: none;
  text-transform: uppercase;
}

.lm-AccordionPanel[data-orientation='horizontal'] > .jp-AccordionPanel-title {
  /* Title is rotated for horizontal accordion panel using CSS */
  display: block;
  transform-origin: top left;
  transform: rotate(-90deg) translate(-100%);
}

.jp-AccordionPanel-title .lm-AccordionPanel-titleLabel {
  user-select: none;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}

.jp-AccordionPanel-title .lm-AccordionPanel-titleCollapser {
  transform: rotate(-90deg);
  margin: auto 0;
  height: 16px;
}

.jp-AccordionPanel-title.lm-mod-expanded .lm-AccordionPanel-titleCollapser {
  transform: rotate(0deg);
}

.lm-AccordionPanel .jp-AccordionPanel-toolbar {
  background: none;
  box-shadow: none;
  border: none;
  margin-left: auto;
}

.lm-AccordionPanel .lm-SplitPanel-handle:hover {
  background: var(--jp-layout-color3);
}

.jp-text-truncated {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Spinner {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-layout-color0);
  outline: none;
}

.jp-SpinnerContent {
  font-size: 10px;
  margin: 50px auto;
  text-indent: -9999em;
  width: 3em;
  height: 3em;
  border-radius: 50%;
  background: var(--jp-brand-color3);
  background: linear-gradient(
    to right,
    #f37626 10%,
    rgba(255, 255, 255, 0) 42%
  );
  position: relative;
  animation: load3 1s infinite linear, fadeIn 1s;
}

.jp-SpinnerContent::before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent::after {
  background: var(--jp-layout-color0);
  width: 75%;
  height: 75%;
  border-radius: 50%;
  content: '';
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}

@keyframes load3 {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

button.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: none;
  box-sizing: border-box;
  text-align: center;
  line-height: 32px;
  height: 32px;
  padding: 0 12px;
  letter-spacing: 0.8px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled {
  background: var(--jp-input-background);
  height: 28px;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color1);
  padding-left: 7px;
  padding-right: 7px;
  font-size: var(--jp-ui-font-size2);
  color: var(--jp-ui-font-color0);
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input[type='checkbox'].jp-mod-styled {
  appearance: checkbox;
  -webkit-appearance: checkbox;
  -moz-appearance: checkbox;
  height: auto;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-select-wrapper {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 1px;
  background-color: var(--jp-layout-color1);
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper:not(.multiple) {
  height: 28px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

select.jp-mod-styled:not([multiple]) {
  height: 32px;
}

select.jp-mod-styled[multiple] {
  max-height: 200px;
  overflow-y: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-switch {
  display: flex;
  align-items: center;
  padding-left: 4px;
  padding-right: 4px;
  font-size: var(--jp-ui-font-size1);
  background-color: transparent;
  color: var(--jp-ui-font-color1);
  border: none;
  height: 20px;
}

.jp-switch:hover {
  background-color: var(--jp-layout-color2);
}

.jp-switch-label {
  margin-right: 5px;
  font-family: var(--jp-ui-font-family);
}

.jp-switch-track {
  cursor: pointer;
  background-color: var(--jp-switch-color, var(--jp-border-color1));
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 34px;
  height: 16px;
  width: 35px;
  position: relative;
}

.jp-switch-track::before {
  content: '';
  position: absolute;
  height: 10px;
  width: 10px;
  margin: 3px;
  left: 0;
  background-color: var(--jp-ui-inverse-font-color1);
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 50%;
}

.jp-switch[aria-checked='true'] .jp-switch-track {
  background-color: var(--jp-switch-true-position-color, var(--jp-warn-color0));
}

.jp-switch[aria-checked='true'] .jp-switch-track::before {
  /* track width (35) - margins (3 + 3) - thumb width (10) */
  left: 19px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toolbar-height: calc(
    28px + var(--jp-border-width)
  ); /* leave 28px for content */
}

.jp-Toolbar {
  color: var(--jp-ui-font-color1);
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: 2px;
  z-index: 8;
  overflow-x: hidden;
}

/* Toolbar items */

.jp-Toolbar > .jp-Toolbar-item.jp-Toolbar-spacer {
  flex-grow: 1;
  flex-shrink: 1;
}

.jp-Toolbar-item.jp-Toolbar-kernelStatus {
  display: inline-block;
  width: 32px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px;
}

.jp-Toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  display: flex;
  padding-left: 1px;
  padding-right: 1px;
  font-size: var(--jp-ui-font-size1);
  line-height: var(--jp-private-toolbar-height);
  height: 100%;
}

/* Toolbar buttons */

/* This is the div we use to wrap the react component into a Widget */
div.jp-ToolbarButton {
  color: transparent;
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0;
  margin: 0;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0 6px;
  margin: 0;
  height: 24px;
  border-radius: var(--jp-border-radius);
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  min-width: unset;
  min-height: unset;
}

button.jp-ToolbarButtonComponent:disabled {
  opacity: 0.4;
}

button.jp-ToolbarButtonComponent > span {
  padding: 0;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
  font-family: var(--jp-ui-font-family);
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar.jp-Toolbar-micro {
  padding: 0;
  min-height: 0;
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar {
  border: none;
  box-shadow: none;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-WindowedPanel-outer {
  position: relative;
  overflow-y: auto;
}

.jp-WindowedPanel-inner {
  position: relative;
}

.jp-WindowedPanel-window {
  position: absolute;
  left: 0;
  right: 0;
  overflow: visible;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

body {
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
}

/* Disable native link decoration styles everywhere outside of dialog boxes */
a {
  text-decoration: unset;
  color: unset;
}

a:hover {
  text-decoration: unset;
  color: unset;
}

/* Accessibility for links inside dialog box text */
.jp-Dialog-content a {
  text-decoration: revert;
  color: var(--jp-content-link-color);
}

.jp-Dialog-content a:hover {
  text-decoration: revert;
}

/* Styles for ui-components */
.jp-Button {
  color: var(--jp-ui-font-color2);
  border-radius: var(--jp-border-radius);
  padding: 0 12px;
  font-size: var(--jp-ui-font-size1);

  /* Copy from blueprint 3 */
  display: inline-flex;
  flex-direction: row;
  border: none;
  cursor: pointer;
  align-items: center;
  justify-content: center;
  text-align: left;
  vertical-align: middle;
  min-height: 30px;
  min-width: 30px;
}

.jp-Button:disabled {
  cursor: not-allowed;
}

.jp-Button:empty {
  padding: 0 !important;
}

.jp-Button.jp-mod-small {
  min-height: 24px;
  min-width: 24px;
  font-size: 12px;
  padding: 0 7px;
}

/* Use our own theme for hover styles */
.jp-Button.jp-mod-minimal:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Button.jp-mod-minimal {
  background: none;
}

.jp-InputGroup {
  display: block;
  position: relative;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border: none;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
  padding-bottom: 0;
  padding-top: 0;
  padding-left: 10px;
  padding-right: 28px;
  position: relative;
  width: 100%;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  font-size: 14px;
  font-weight: 400;
  height: 30px;
  line-height: 30px;
  outline: none;
  vertical-align: middle;
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input:disabled {
  cursor: not-allowed;
  resize: block;
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color2);
}

.jp-InputGroup input:disabled ~ span {
  cursor: not-allowed;
  color: var(--jp-ui-font-color2);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color2);
}

.jp-InputGroupAction {
  position: absolute;
  bottom: 1px;
  right: 0;
  padding: 6px;
}

.jp-HTMLSelect.jp-DefaultStyle select {
  background-color: initial;
  border: none;
  border-radius: 0;
  box-shadow: none;
  color: var(--jp-ui-font-color0);
  display: block;
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

.jp-HTMLSelect.jp-DefaultStyle select:disabled {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color2);
  cursor: not-allowed;
  resize: block;
}

.jp-HTMLSelect.jp-DefaultStyle select:disabled ~ span {
  cursor: not-allowed;
}

/* Use our own theme for hover and option styles */
/* stylelint-disable-next-line selector-max-type */
.jp-HTMLSelect.jp-DefaultStyle select:hover,
.jp-HTMLSelect.jp-DefaultStyle select > option {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color0);
}

select {
  box-sizing: border-box;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-StatusBar-Widget {
  display: flex;
  align-items: center;
  background: var(--jp-layout-color2);
  min-height: var(--jp-statusbar-height);
  justify-content: space-between;
  padding: 0 10px;
}

.jp-StatusBar-Left {
  display: flex;
  align-items: center;
  flex-direction: row;
}

.jp-StatusBar-Middle {
  display: flex;
  align-items: center;
}

.jp-StatusBar-Right {
  display: flex;
  align-items: center;
  flex-direction: row-reverse;
}

.jp-StatusBar-Item {
  max-height: var(--jp-statusbar-height);
  margin: 0 2px;
  height: var(--jp-statusbar-height);
  white-space: nowrap;
  text-overflow: ellipsis;
  color: var(--jp-ui-font-color1);
  padding: 0 6px;
}

.jp-mod-highlighted:hover {
  background-color: var(--jp-layout-color3);
}

.jp-mod-clicked {
  background-color: var(--jp-brand-color1);
}

.jp-mod-clicked:hover {
  background-color: var(--jp-brand-color0);
}

.jp-mod-clicked .jp-StatusBar-TextItem {
  color: var(--jp-ui-inverse-font-color1);
}

.jp-StatusBar-HoverItem {
  box-shadow: '0px 4px 4px rgba(0, 0, 0, 0.25)';
}

.jp-StatusBar-TextItem {
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  line-height: 24px;
  color: var(--jp-ui-font-color1);
}

.jp-StatusBar-GroupItem {
  display: flex;
  align-items: center;
  flex-direction: row;
}

.jp-Statusbar-ProgressCircle svg {
  display: block;
  margin: 0 auto;
  width: 16px;
  height: 24px;
  align-self: normal;
}

.jp-Statusbar-ProgressCircle path {
  fill: var(--jp-inverse-layout-color3);
}

.jp-Statusbar-ProgressBar-progress-bar {
  height: 10px;
  width: 100px;
  border: solid 0.25px var(--jp-brand-color2);
  border-radius: 3px;
  overflow: hidden;
  align-self: center;
}

.jp-Statusbar-ProgressBar-progress-bar > div {
  background-color: var(--jp-brand-color2);
  background-image: linear-gradient(
    -45deg,
    rgba(255, 255, 255, 0.2) 25%,
    transparent 25%,
    transparent 50%,
    rgba(255, 255, 255, 0.2) 50%,
    rgba(255, 255, 255, 0.2) 75%,
    transparent 75%,
    transparent
  );
  background-size: 40px 40px;
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 14px;
  color: #fff;
  text-align: center;
  animation: jp-Statusbar-ExecutionTime-progress-bar 2s linear infinite;
}

.jp-Statusbar-ProgressBar-progress-bar p {
  color: var(--jp-ui-font-color1);
  font-family: var(--jp-ui-font-family);
  font-size: var(--jp-ui-font-size1);
  line-height: 10px;
  width: 100px;
}

@keyframes jp-Statusbar-ExecutionTime-progress-bar {
  0% {
    background-position: 0 0;
  }

  100% {
    background-position: 40px 40px;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-commandpalette-search-height: 28px;
}

/*-----------------------------------------------------------------------------
| Overall styles
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  padding-bottom: 0;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);

  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Modal variant
|----------------------------------------------------------------------------*/

.jp-ModalCommandPalette {
  position: absolute;
  z-index: 10000;
  top: 38px;
  left: 30%;
  margin: 0;
  padding: 4px;
  width: 40%;
  box-shadow: var(--jp-elevation-z4);
  border-radius: 4px;
  background: var(--jp-layout-color0);
}

.jp-ModalCommandPalette .lm-CommandPalette {
  max-height: 40vh;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-close-icon::after {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-header {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-item {
  margin-left: 4px;
  margin-right: 4px;
}

.jp-ModalCommandPalette
  .lm-CommandPalette
  .lm-CommandPalette-item.lm-mod-disabled {
  display: none;
}

/*-----------------------------------------------------------------------------
| Search
|----------------------------------------------------------------------------*/

.lm-CommandPalette-search {
  padding: 4px;
  background-color: var(--jp-layout-color1);
  z-index: 2;
}

.lm-CommandPalette-wrapper {
  overflow: overlay;
  padding: 0 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-SearchIconGroup {
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  padding: 5px 5px 1px;
}

.jp-SearchIconGroup svg {
  height: 20px;
  width: 20px;
}

.jp-SearchIconGroup .jp-icon3[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-input {
  background: transparent;
  width: calc(100% - 18px);
  float: left;
  border: none;
  outline: none;
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  line-height: var(--jp-private-commandpalette-search-height);
}

.lm-CommandPalette-input::-webkit-input-placeholder,
.lm-CommandPalette-input::-moz-placeholder,
.lm-CommandPalette-input:-ms-input-placeholder {
  color: var(--jp-ui-font-color2);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0;
}

.lm-CommandPalette-header {
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 8px;
  padding: 8px 0 8px 12px;
  text-transform: uppercase;
}

.lm-CommandPalette-header.lm-mod-active {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-header > mark {
  background-color: transparent;
  font-weight: bold;
  color: var(--jp-ui-font-color1);
}

.lm-CommandPalette-item {
  padding: 4px 12px 4px 4px;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  font-weight: 400;
  display: flex;
}

.lm-CommandPalette-item.lm-mod-disabled {
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item.lm-mod-active {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item.lm-mod-active .lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-inverse-font-color0);
}

.lm-CommandPalette-item.lm-mod-active .jp-icon-selectable[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item:hover:not(.lm-mod-active):not(.lm-mod-disabled) {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-itemContent {
  overflow: hidden;
}

.lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.lm-CommandPalette-item.lm-mod-disabled mark {
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.6;
}

.lm-CommandPalette-item .lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemCaption {
  display: none;
}

.lm-CommandPalette-content {
  background-color: var(--jp-layout-color1);
}

.lm-CommandPalette-content:empty::after {
  content: 'No results';
  margin: auto;
  margin-top: 20px;
  width: 100px;
  display: block;
  font-size: var(--jp-ui-font-size2);
  font-family: var(--jp-ui-font-family);
  font-weight: lighter;
}

.lm-CommandPalette-emptyMessage {
  text-align: center;
  margin-top: 24px;
  line-height: 1.32;
  padding: 0 8px;
  color: var(--jp-content-font-color3);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Dialog {
  position: absolute;
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  top: 0;
  left: 0;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-dialog-background);
}

.jp-Dialog-content {
  display: flex;
  flex-direction: column;
  margin-left: auto;
  margin-right: auto;
  background: var(--jp-layout-color1);
  padding: 24px 24px 12px;
  min-width: 300px;
  min-height: 150px;
  max-width: 1000px;
  max-height: 500px;
  box-sizing: border-box;
  box-shadow: var(--jp-elevation-z20);
  word-wrap: break-word;
  border-radius: var(--jp-border-radius);

  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color1);
  resize: both;
}

.jp-Dialog-content.jp-Dialog-content-small {
  max-width: 500px;
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-accept:focus,
button.jp-Dialog-button.jp-mod-styled.jp-mod-warn:focus,
button.jp-Dialog-button.jp-mod-styled.jp-mod-reject:focus {
  outline-offset: 4px;
  -moz-outline-radius: 0;
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-accept:focus {
  outline: 1px solid var(--jp-accept-color-normal, var(--jp-brand-color1));
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-warn:focus {
  outline: 1px solid var(--jp-warn-color-normal, var(--jp-error-color1));
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-reject:focus {
  outline: 1px solid var(--jp-reject-color-normal, var(--md-grey-600));
}

button.jp-Dialog-close-button {
  padding: 0;
  height: 100%;
  min-width: unset;
  min-height: unset;
}

.jp-Dialog-header {
  display: flex;
  justify-content: space-between;
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color1);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-checkbox {
  padding-right: 5px;
}

.jp-Dialog-checkbox > input:focus-visible {
  outline: 1px solid var(--jp-input-active-border-color);
  outline-offset: 1px;
}

.jp-Dialog-spacer {
  flex: 1 1 auto;
}

.jp-Dialog-title {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.jp-Dialog-body > .jp-select-wrapper {
  width: 100%;
}

.jp-Dialog-body > button {
  padding: 0 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-Input-Boolean-Dialog {
  flex-direction: row-reverse;
  align-items: end;
  width: 100%;
}

.jp-Input-Boolean-Dialog > label {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

.jp-MainAreaWidget .jp-MainAreaWidget-error {
  padding: 6px;
}

.jp-MainAreaWidget .jp-MainAreaWidget-error > pre {
  width: auto;
  padding: 10px;
  background: var(--jp-error-color3);
  border: var(--jp-border-width) solid var(--jp-error-color1);
  border-radius: var(--jp-border-radius);
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  white-space: pre-wrap;
  word-wrap: break-word;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/**
 * google-material-color v1.2.6
 * https://github.com/danlevan/google-material-color
 */
:root {
  --md-red-50: #ffebee;
  --md-red-100: #ffcdd2;
  --md-red-200: #ef9a9a;
  --md-red-300: #e57373;
  --md-red-400: #ef5350;
  --md-red-500: #f44336;
  --md-red-600: #e53935;
  --md-red-700: #d32f2f;
  --md-red-800: #c62828;
  --md-red-900: #b71c1c;
  --md-red-A100: #ff8a80;
  --md-red-A200: #ff5252;
  --md-red-A400: #ff1744;
  --md-red-A700: #d50000;
  --md-pink-50: #fce4ec;
  --md-pink-100: #f8bbd0;
  --md-pink-200: #f48fb1;
  --md-pink-300: #f06292;
  --md-pink-400: #ec407a;
  --md-pink-500: #e91e63;
  --md-pink-600: #d81b60;
  --md-pink-700: #c2185b;
  --md-pink-800: #ad1457;
  --md-pink-900: #880e4f;
  --md-pink-A100: #ff80ab;
  --md-pink-A200: #ff4081;
  --md-pink-A400: #f50057;
  --md-pink-A700: #c51162;
  --md-purple-50: #f3e5f5;
  --md-purple-100: #e1bee7;
  --md-purple-200: #ce93d8;
  --md-purple-300: #ba68c8;
  --md-purple-400: #ab47bc;
  --md-purple-500: #9c27b0;
  --md-purple-600: #8e24aa;
  --md-purple-700: #7b1fa2;
  --md-purple-800: #6a1b9a;
  --md-purple-900: #4a148c;
  --md-purple-A100: #ea80fc;
  --md-purple-A200: #e040fb;
  --md-purple-A400: #d500f9;
  --md-purple-A700: #a0f;
  --md-deep-purple-50: #ede7f6;
  --md-deep-purple-100: #d1c4e9;
  --md-deep-purple-200: #b39ddb;
  --md-deep-purple-300: #9575cd;
  --md-deep-purple-400: #7e57c2;
  --md-deep-purple-500: #673ab7;
  --md-deep-purple-600: #5e35b1;
  --md-deep-purple-700: #512da8;
  --md-deep-purple-800: #4527a0;
  --md-deep-purple-900: #311b92;
  --md-deep-purple-A100: #b388ff;
  --md-deep-purple-A200: #7c4dff;
  --md-deep-purple-A400: #651fff;
  --md-deep-purple-A700: #6200ea;
  --md-indigo-50: #e8eaf6;
  --md-indigo-100: #c5cae9;
  --md-indigo-200: #9fa8da;
  --md-indigo-300: #7986cb;
  --md-indigo-400: #5c6bc0;
  --md-indigo-500: #3f51b5;
  --md-indigo-600: #3949ab;
  --md-indigo-700: #303f9f;
  --md-indigo-800: #283593;
  --md-indigo-900: #1a237e;
  --md-indigo-A100: #8c9eff;
  --md-indigo-A200: #536dfe;
  --md-indigo-A400: #3d5afe;
  --md-indigo-A700: #304ffe;
  --md-blue-50: #e3f2fd;
  --md-blue-100: #bbdefb;
  --md-blue-200: #90caf9;
  --md-blue-300: #64b5f6;
  --md-blue-400: #42a5f5;
  --md-blue-500: #2196f3;
  --md-blue-600: #1e88e5;
  --md-blue-700: #1976d2;
  --md-blue-800: #1565c0;
  --md-blue-900: #0d47a1;
  --md-blue-A100: #82b1ff;
  --md-blue-A200: #448aff;
  --md-blue-A400: #2979ff;
  --md-blue-A700: #2962ff;
  --md-light-blue-50: #e1f5fe;
  --md-light-blue-100: #b3e5fc;
  --md-light-blue-200: #81d4fa;
  --md-light-blue-300: #4fc3f7;
  --md-light-blue-400: #29b6f6;
  --md-light-blue-500: #03a9f4;
  --md-light-blue-600: #039be5;
  --md-light-blue-700: #0288d1;
  --md-light-blue-800: #0277bd;
  --md-light-blue-900: #01579b;
  --md-light-blue-A100: #80d8ff;
  --md-light-blue-A200: #40c4ff;
  --md-light-blue-A400: #00b0ff;
  --md-light-blue-A700: #0091ea;
  --md-cyan-50: #e0f7fa;
  --md-cyan-100: #b2ebf2;
  --md-cyan-200: #80deea;
  --md-cyan-300: #4dd0e1;
  --md-cyan-400: #26c6da;
  --md-cyan-500: #00bcd4;
  --md-cyan-600: #00acc1;
  --md-cyan-700: #0097a7;
  --md-cyan-800: #00838f;
  --md-cyan-900: #006064;
  --md-cyan-A100: #84ffff;
  --md-cyan-A200: #18ffff;
  --md-cyan-A400: #00e5ff;
  --md-cyan-A700: #00b8d4;
  --md-teal-50: #e0f2f1;
  --md-teal-100: #b2dfdb;
  --md-teal-200: #80cbc4;
  --md-teal-300: #4db6ac;
  --md-teal-400: #26a69a;
  --md-teal-500: #009688;
  --md-teal-600: #00897b;
  --md-teal-700: #00796b;
  --md-teal-800: #00695c;
  --md-teal-900: #004d40;
  --md-teal-A100: #a7ffeb;
  --md-teal-A200: #64ffda;
  --md-teal-A400: #1de9b6;
  --md-teal-A700: #00bfa5;
  --md-green-50: #e8f5e9;
  --md-green-100: #c8e6c9;
  --md-green-200: #a5d6a7;
  --md-green-300: #81c784;
  --md-green-400: #66bb6a;
  --md-green-500: #4caf50;
  --md-green-600: #43a047;
  --md-green-700: #388e3c;
  --md-green-800: #2e7d32;
  --md-green-900: #1b5e20;
  --md-green-A100: #b9f6ca;
  --md-green-A200: #69f0ae;
  --md-green-A400: #00e676;
  --md-green-A700: #00c853;
  --md-light-green-50: #f1f8e9;
  --md-light-green-100: #dcedc8;
  --md-light-green-200: #c5e1a5;
  --md-light-green-300: #aed581;
  --md-light-green-400: #9ccc65;
  --md-light-green-500: #8bc34a;
  --md-light-green-600: #7cb342;
  --md-light-green-700: #689f38;
  --md-light-green-800: #558b2f;
  --md-light-green-900: #33691e;
  --md-light-green-A100: #ccff90;
  --md-light-green-A200: #b2ff59;
  --md-light-green-A400: #76ff03;
  --md-light-green-A700: #64dd17;
  --md-lime-50: #f9fbe7;
  --md-lime-100: #f0f4c3;
  --md-lime-200: #e6ee9c;
  --md-lime-300: #dce775;
  --md-lime-400: #d4e157;
  --md-lime-500: #cddc39;
  --md-lime-600: #c0ca33;
  --md-lime-700: #afb42b;
  --md-lime-800: #9e9d24;
  --md-lime-900: #827717;
  --md-lime-A100: #f4ff81;
  --md-lime-A200: #eeff41;
  --md-lime-A400: #c6ff00;
  --md-lime-A700: #aeea00;
  --md-yellow-50: #fffde7;
  --md-yellow-100: #fff9c4;
  --md-yellow-200: #fff59d;
  --md-yellow-300: #fff176;
  --md-yellow-400: #ffee58;
  --md-yellow-500: #ffeb3b;
  --md-yellow-600: #fdd835;
  --md-yellow-700: #fbc02d;
  --md-yellow-800: #f9a825;
  --md-yellow-900: #f57f17;
  --md-yellow-A100: #ffff8d;
  --md-yellow-A200: #ff0;
  --md-yellow-A400: #ffea00;
  --md-yellow-A700: #ffd600;
  --md-amber-50: #fff8e1;
  --md-amber-100: #ffecb3;
  --md-amber-200: #ffe082;
  --md-amber-300: #ffd54f;
  --md-amber-400: #ffca28;
  --md-amber-500: #ffc107;
  --md-amber-600: #ffb300;
  --md-amber-700: #ffa000;
  --md-amber-800: #ff8f00;
  --md-amber-900: #ff6f00;
  --md-amber-A100: #ffe57f;
  --md-amber-A200: #ffd740;
  --md-amber-A400: #ffc400;
  --md-amber-A700: #ffab00;
  --md-orange-50: #fff3e0;
  --md-orange-100: #ffe0b2;
  --md-orange-200: #ffcc80;
  --md-orange-300: #ffb74d;
  --md-orange-400: #ffa726;
  --md-orange-500: #ff9800;
  --md-orange-600: #fb8c00;
  --md-orange-700: #f57c00;
  --md-orange-800: #ef6c00;
  --md-orange-900: #e65100;
  --md-orange-A100: #ffd180;
  --md-orange-A200: #ffab40;
  --md-orange-A400: #ff9100;
  --md-orange-A700: #ff6d00;
  --md-deep-orange-50: #fbe9e7;
  --md-deep-orange-100: #ffccbc;
  --md-deep-orange-200: #ffab91;
  --md-deep-orange-300: #ff8a65;
  --md-deep-orange-400: #ff7043;
  --md-deep-orange-500: #ff5722;
  --md-deep-orange-600: #f4511e;
  --md-deep-orange-700: #e64a19;
  --md-deep-orange-800: #d84315;
  --md-deep-orange-900: #bf360c;
  --md-deep-orange-A100: #ff9e80;
  --md-deep-orange-A200: #ff6e40;
  --md-deep-orange-A400: #ff3d00;
  --md-deep-orange-A700: #dd2c00;
  --md-brown-50: #efebe9;
  --md-brown-100: #d7ccc8;
  --md-brown-200: #bcaaa4;
  --md-brown-300: #a1887f;
  --md-brown-400: #8d6e63;
  --md-brown-500: #795548;
  --md-brown-600: #6d4c41;
  --md-brown-700: #5d4037;
  --md-brown-800: #4e342e;
  --md-brown-900: #3e2723;
  --md-grey-50: #fafafa;
  --md-grey-100: #f5f5f5;
  --md-grey-200: #eee;
  --md-grey-300: #e0e0e0;
  --md-grey-400: #bdbdbd;
  --md-grey-500: #9e9e9e;
  --md-grey-600: #757575;
  --md-grey-700: #616161;
  --md-grey-800: #424242;
  --md-grey-900: #212121;
  --md-blue-grey-50: #eceff1;
  --md-blue-grey-100: #cfd8dc;
  --md-blue-grey-200: #b0bec5;
  --md-blue-grey-300: #90a4ae;
  --md-blue-grey-400: #78909c;
  --md-blue-grey-500: #607d8b;
  --md-blue-grey-600: #546e7a;
  --md-blue-grey-700: #455a64;
  --md-blue-grey-800: #37474f;
  --md-blue-grey-900: #263238;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

:root {
  /* This is the padding value to fill the gaps between lines containing spans with background color. */
  --jp-private-code-span-padding: calc(
    (var(--jp-code-line-height) - 1) * var(--jp-code-font-size) / 2
  );
}

.jp-RenderedText {
  text-align: left;
  padding-left: var(--jp-code-padding);
  line-height: var(--jp-code-line-height);
  font-family: var(--jp-code-font-family);
}

.jp-RenderedText pre,
.jp-RenderedJavaScript pre,
.jp-RenderedHTMLCommon pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
  border: none;
  margin: 0;
  padding: 0;
}

.jp-RenderedText pre a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedText pre a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedText pre a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* console foregrounds and backgrounds */
.jp-RenderedText pre .ansi-black-fg {
  color: #3e424d;
}

.jp-RenderedText pre .ansi-red-fg {
  color: #e75c58;
}

.jp-RenderedText pre .ansi-green-fg {
  color: #00a250;
}

.jp-RenderedText pre .ansi-yellow-fg {
  color: #ddb62b;
}

.jp-RenderedText pre .ansi-blue-fg {
  color: #208ffb;
}

.jp-RenderedText pre .ansi-magenta-fg {
  color: #d160c4;
}

.jp-RenderedText pre .ansi-cyan-fg {
  color: #60c6c8;
}

.jp-RenderedText pre .ansi-white-fg {
  color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-bg {
  background-color: #3e424d;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-black-intense-fg {
  color: #282c36;
}

.jp-RenderedText pre .ansi-red-intense-fg {
  color: #b22b31;
}

.jp-RenderedText pre .ansi-green-intense-fg {
  color: #007427;
}

.jp-RenderedText pre .ansi-yellow-intense-fg {
  color: #b27d12;
}

.jp-RenderedText pre .ansi-blue-intense-fg {
  color: #0065ca;
}

.jp-RenderedText pre .ansi-magenta-intense-fg {
  color: #a03196;
}

.jp-RenderedText pre .ansi-cyan-intense-fg {
  color: #258f8f;
}

.jp-RenderedText pre .ansi-white-intense-fg {
  color: #a1a6b2;
}

.jp-RenderedText pre .ansi-black-intense-bg {
  background-color: #282c36;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}

.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-bold {
  font-weight: bold;
}

.jp-RenderedText pre .ansi-underline {
  text-decoration: underline;
}

.jp-RenderedText[data-mime-type='application/vnd.jupyter.stderr'] {
  background: var(--jp-rendermime-error-background);
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| RenderedLatex
|----------------------------------------------------------------------------*/

.jp-RenderedLatex {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
}

/* Left-justify outputs.*/
.jp-OutputArea-output.jp-RenderedLatex {
  padding: var(--jp-code-padding);
  text-align: left;
}

/*-----------------------------------------------------------------------------
| RenderedHTML
|----------------------------------------------------------------------------*/

.jp-RenderedHTMLCommon {
  color: var(--jp-content-font-color1);
  font-family: var(--jp-content-font-family);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);

  /* Give a bit more R padding on Markdown text to keep line lengths reasonable */
  padding-right: 20px;
}

.jp-RenderedHTMLCommon em {
  font-style: italic;
}

.jp-RenderedHTMLCommon strong {
  font-weight: bold;
}

.jp-RenderedHTMLCommon u {
  text-decoration: underline;
}

.jp-RenderedHTMLCommon a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* Headings */

.jp-RenderedHTMLCommon h1,
.jp-RenderedHTMLCommon h2,
.jp-RenderedHTMLCommon h3,
.jp-RenderedHTMLCommon h4,
.jp-RenderedHTMLCommon h5,
.jp-RenderedHTMLCommon h6 {
  line-height: var(--jp-content-heading-line-height);
  font-weight: var(--jp-content-heading-font-weight);
  font-style: normal;
  margin: var(--jp-content-heading-margin-top) 0
    var(--jp-content-heading-margin-bottom) 0;
}

.jp-RenderedHTMLCommon h1:first-child,
.jp-RenderedHTMLCommon h2:first-child,
.jp-RenderedHTMLCommon h3:first-child,
.jp-RenderedHTMLCommon h4:first-child,
.jp-RenderedHTMLCommon h5:first-child,
.jp-RenderedHTMLCommon h6:first-child {
  margin-top: calc(0.5 * var(--jp-content-heading-margin-top));
}

.jp-RenderedHTMLCommon h1:last-child,
.jp-RenderedHTMLCommon h2:last-child,
.jp-RenderedHTMLCommon h3:last-child,
.jp-RenderedHTMLCommon h4:last-child,
.jp-RenderedHTMLCommon h5:last-child,
.jp-RenderedHTMLCommon h6:last-child {
  margin-bottom: calc(0.5 * var(--jp-content-heading-margin-bottom));
}

.jp-RenderedHTMLCommon h1 {
  font-size: var(--jp-content-font-size5);
}

.jp-RenderedHTMLCommon h2 {
  font-size: var(--jp-content-font-size4);
}

.jp-RenderedHTMLCommon h3 {
  font-size: var(--jp-content-font-size3);
}

.jp-RenderedHTMLCommon h4 {
  font-size: var(--jp-content-font-size2);
}

.jp-RenderedHTMLCommon h5 {
  font-size: var(--jp-content-font-size1);
}

.jp-RenderedHTMLCommon h6 {
  font-size: var(--jp-content-font-size0);
}

/* Lists */

/* stylelint-disable selector-max-type, selector-max-compound-selectors */

.jp-RenderedHTMLCommon ul:not(.list-inline),
.jp-RenderedHTMLCommon ol:not(.list-inline) {
  padding-left: 2em;
}

.jp-RenderedHTMLCommon ul {
  list-style: disc;
}

.jp-RenderedHTMLCommon ul ul {
  list-style: square;
}

.jp-RenderedHTMLCommon ul ul ul {
  list-style: circle;
}

.jp-RenderedHTMLCommon ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol ol {
  list-style: upper-alpha;
}

.jp-RenderedHTMLCommon ol ol ol {
  list-style: lower-alpha;
}

.jp-RenderedHTMLCommon ol ol ol ol {
  list-style: lower-roman;
}

.jp-RenderedHTMLCommon ol ol ol ol ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol,
.jp-RenderedHTMLCommon ul {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon ul ul,
.jp-RenderedHTMLCommon ul ol,
.jp-RenderedHTMLCommon ol ul,
.jp-RenderedHTMLCommon ol ol {
  margin-bottom: 0;
}

/* stylelint-enable selector-max-type, selector-max-compound-selectors */

.jp-RenderedHTMLCommon hr {
  color: var(--jp-border-color2);
  background-color: var(--jp-border-color1);
  margin-top: 1em;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon > pre {
  margin: 1.5em 2em;
}

.jp-RenderedHTMLCommon pre,
.jp-RenderedHTMLCommon code {
  border: 0;
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  line-height: var(--jp-code-line-height);
  padding: 0;
  white-space: pre-wrap;
}

.jp-RenderedHTMLCommon :not(pre) > code {
  background-color: var(--jp-layout-color2);
  padding: 1px 5px;
}

/* Tables */

.jp-RenderedHTMLCommon table {
  border-collapse: collapse;
  border-spacing: 0;
  border: none;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  table-layout: fixed;
  margin-left: auto;
  margin-bottom: 1em;
  margin-right: auto;
}

.jp-RenderedHTMLCommon thead {
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  vertical-align: bottom;
}

.jp-RenderedHTMLCommon td,
.jp-RenderedHTMLCommon th,
.jp-RenderedHTMLCommon tr {
  vertical-align: middle;
  padding: 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}

.jp-RenderedMarkdown.jp-RenderedHTMLCommon td,
.jp-RenderedMarkdown.jp-RenderedHTMLCommon th {
  max-width: none;
}

:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon td,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon th,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon tr {
  text-align: right;
}

.jp-RenderedHTMLCommon th {
  font-weight: bold;
}

.jp-RenderedHTMLCommon tbody tr:nth-child(odd) {
  background: var(--jp-layout-color0);
}

.jp-RenderedHTMLCommon tbody tr:nth-child(even) {
  background: var(--jp-rendermime-table-row-background);
}

.jp-RenderedHTMLCommon tbody tr:hover {
  background: var(--jp-rendermime-table-row-hover-background);
}

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon img {
  -moz-force-broken-image-icon: 1;
}

/* Restrict to direct children as other images could be nested in other content. */
.jp-RenderedHTMLCommon > img {
  display: block;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 1em;
}

/* Change color behind transparent images if they need it... */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-light-background {
  background-color: var(--jp-inverse-layout-color1);
}

[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-dark-background {
  background-color: var(--jp-inverse-layout-color1);
}

.jp-RenderedHTMLCommon img,
.jp-RenderedImage img,
.jp-RenderedHTMLCommon svg,
.jp-RenderedSVG svg {
  max-width: 100%;
  height: auto;
}

.jp-RenderedHTMLCommon img.jp-mod-unconfined,
.jp-RenderedImage img.jp-mod-unconfined,
.jp-RenderedHTMLCommon svg.jp-mod-unconfined,
.jp-RenderedSVG svg.jp-mod-unconfined {
  max-width: none;
}

.jp-RenderedHTMLCommon .alert {
  padding: var(--jp-notebook-padding);
  border: var(--jp-border-width) solid transparent;
  border-radius: var(--jp-border-radius);
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon .alert-info {
  color: var(--jp-info-color0);
  background-color: var(--jp-info-color3);
  border-color: var(--jp-info-color2);
}

.jp-RenderedHTMLCommon .alert-info hr {
  border-color: var(--jp-info-color3);
}

.jp-RenderedHTMLCommon .alert-info > p:last-child,
.jp-RenderedHTMLCommon .alert-info > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-warning {
  color: var(--jp-warn-color0);
  background-color: var(--jp-warn-color3);
  border-color: var(--jp-warn-color2);
}

.jp-RenderedHTMLCommon .alert-warning hr {
  border-color: var(--jp-warn-color3);
}

.jp-RenderedHTMLCommon .alert-warning > p:last-child,
.jp-RenderedHTMLCommon .alert-warning > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-success {
  color: var(--jp-success-color0);
  background-color: var(--jp-success-color3);
  border-color: var(--jp-success-color2);
}

.jp-RenderedHTMLCommon .alert-success hr {
  border-color: var(--jp-success-color3);
}

.jp-RenderedHTMLCommon .alert-success > p:last-child,
.jp-RenderedHTMLCommon .alert-success > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-danger {
  color: var(--jp-error-color0);
  background-color: var(--jp-error-color3);
  border-color: var(--jp-error-color2);
}

.jp-RenderedHTMLCommon .alert-danger hr {
  border-color: var(--jp-error-color3);
}

.jp-RenderedHTMLCommon .alert-danger > p:last-child,
.jp-RenderedHTMLCommon .alert-danger > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon blockquote {
  margin: 1em 2em;
  padding: 0 1em;
  border-left: 5px solid var(--jp-border-color2);
}

a.jp-InternalAnchorLink {
  visibility: hidden;
  margin-left: 8px;
  color: var(--md-blue-800);
}

h1:hover .jp-InternalAnchorLink,
h2:hover .jp-InternalAnchorLink,
h3:hover .jp-InternalAnchorLink,
h4:hover .jp-InternalAnchorLink,
h5:hover .jp-InternalAnchorLink,
h6:hover .jp-InternalAnchorLink {
  visibility: visible;
}

.jp-RenderedHTMLCommon kbd {
  background-color: var(--jp-rendermime-table-row-background);
  border: 1px solid var(--jp-border-color0);
  border-bottom-color: var(--jp-border-color2);
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
  display: inline-block;
  font-size: var(--jp-ui-font-size0);
  line-height: 1em;
  padding: 0.2em 0.5em;
}

/* Most direct children of .jp-RenderedHTMLCommon have a margin-bottom of 1.0.
 * At the bottom of cells this is a bit too much as there is also spacing
 * between cells. Going all the way to 0 gets too tight between markdown and
 * code cells.
 */
.jp-RenderedHTMLCommon > *:last-child {
  margin-bottom: 0.5em;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-cursor-backdrop {
  position: fixed;
  width: 200px;
  height: 200px;
  margin-top: -100px;
  margin-left: -100px;
  will-change: transform;
  z-index: 100;
}

.lm-mod-drag-image {
  will-change: transform;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-lineFormSearch {
  padding: 4px 12px;
  background-color: var(--jp-layout-color2);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
  font-size: var(--jp-ui-font-size1);
}

.jp-lineFormCaption {
  font-size: var(--jp-ui-font-size0);
  line-height: var(--jp-ui-font-size1);
  margin-top: 4px;
  color: var(--jp-ui-font-color0);
}

.jp-baseLineForm {
  border: none;
  border-radius: 0;
  position: absolute;
  background-size: 16px;
  background-repeat: no-repeat;
  background-position: center;
  outline: none;
}

.jp-lineFormButtonContainer {
  top: 4px;
  right: 8px;
  height: 24px;
  padding: 0 12px;
  width: 12px;
}

.jp-lineFormButtonIcon {
  top: 0;
  right: 0;
  background-color: var(--jp-brand-color1);
  height: 100%;
  width: 100%;
  box-sizing: border-box;
  padding: 4px 6px;
}

.jp-lineFormButton {
  top: 0;
  right: 0;
  background-color: transparent;
  height: 100%;
  width: 100%;
  box-sizing: border-box;
}

.jp-lineFormWrapper {
  overflow: hidden;
  padding: 0 8px;
  border: 1px solid var(--jp-border-color0);
  background-color: var(--jp-input-active-background);
  height: 22px;
}

.jp-lineFormWrapperFocusWithin {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-lineFormInput {
  background: transparent;
  width: 200px;
  height: 100%;
  border: none;
  outline: none;
  color: var(--jp-ui-font-color0);
  line-height: 28px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-JSONEditor {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.jp-JSONEditor-host {
  flex: 1 1 auto;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0;
  background: var(--jp-layout-color0);
  min-height: 50px;
  padding: 1px;
}

.jp-JSONEditor.jp-mod-error .jp-JSONEditor-host {
  border-color: red;
  outline-color: red;
}

.jp-JSONEditor-header {
  display: flex;
  flex: 1 0 auto;
  padding: 0 0 0 12px;
}

.jp-JSONEditor-header label {
  flex: 0 0 auto;
}

.jp-JSONEditor-commitButton {
  height: 16px;
  width: 16px;
  background-size: 18px;
  background-repeat: no-repeat;
  background-position: center;
}

.jp-JSONEditor-host.jp-mod-focused {
  background-color: var(--jp-input-active-background);
  border: 1px solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

.jp-Editor.jp-mod-dropTarget {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/
.jp-DocumentSearch-input {
  border: none;
  outline: none;
  color: var(--jp-ui-font-color0);
  font-size: var(--jp-ui-font-size1);
  background-color: var(--jp-layout-color0);
  font-family: var(--jp-ui-font-family);
  padding: 2px 1px;
  resize: none;
}

.jp-DocumentSearch-overlay {
  position: absolute;
  background-color: var(--jp-toolbar-background);
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  border-left: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  top: 0;
  right: 0;
  z-index: 7;
  min-width: 405px;
  padding: 2px;
  font-size: var(--jp-ui-font-size1);

  --jp-private-document-search-button-height: 20px;
}

.jp-DocumentSearch-overlay button {
  background-color: var(--jp-toolbar-background);
  outline: 0;
}

.jp-DocumentSearch-overlay button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-overlay button:active {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-overlay-row {
  display: flex;
  align-items: center;
  margin-bottom: 2px;
}

.jp-DocumentSearch-button-content {
  display: inline-block;
  cursor: pointer;
  box-sizing: border-box;
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-button-content svg {
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-input-wrapper {
  border: var(--jp-border-width) solid var(--jp-border-color0);
  display: flex;
  background-color: var(--jp-layout-color0);
  margin: 2px;
}

.jp-DocumentSearch-input-wrapper:focus-within {
  border-color: var(--jp-cell-editor-active-border-color);
}

.jp-DocumentSearch-toggle-wrapper,
.jp-DocumentSearch-button-wrapper {
  all: initial;
  overflow: hidden;
  display: inline-block;
  border: none;
  box-sizing: border-box;
}

.jp-DocumentSearch-toggle-wrapper {
  width: 14px;
  height: 14px;
}

.jp-DocumentSearch-button-wrapper {
  width: var(--jp-private-document-search-button-height);
  height: var(--jp-private-document-search-button-height);
}

.jp-DocumentSearch-toggle-wrapper:focus,
.jp-DocumentSearch-button-wrapper:focus {
  outline: var(--jp-border-width) solid
    var(--jp-cell-editor-active-border-color);
  outline-offset: -1px;
}

.jp-DocumentSearch-toggle-wrapper,
.jp-DocumentSearch-button-wrapper,
.jp-DocumentSearch-button-content:focus {
  outline: none;
}

.jp-DocumentSearch-toggle-placeholder {
  width: 5px;
}

.jp-DocumentSearch-input-button::before {
  display: block;
  padding-top: 100%;
}

.jp-DocumentSearch-input-button-off {
  opacity: var(--jp-search-toggle-off-opacity);
}

.jp-DocumentSearch-input-button-off:hover {
  opacity: var(--jp-search-toggle-hover-opacity);
}

.jp-DocumentSearch-input-button-on {
  opacity: var(--jp-search-toggle-on-opacity);
}

.jp-DocumentSearch-index-counter {
  padding-left: 10px;
  padding-right: 10px;
  user-select: none;
  min-width: 35px;
  display: inline-block;
}

.jp-DocumentSearch-up-down-wrapper {
  display: inline-block;
  padding-right: 2px;
  margin-left: auto;
  white-space: nowrap;
}

.jp-DocumentSearch-spacer {
  margin-left: auto;
}

.jp-DocumentSearch-up-down-wrapper button {
  outline: 0;
  border: none;
  width: var(--jp-private-document-search-button-height);
  height: var(--jp-private-document-search-button-height);
  vertical-align: middle;
  margin: 1px 5px 2px;
}

.jp-DocumentSearch-up-down-button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-up-down-button:active {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-filter-button {
  border-radius: var(--jp-border-radius);
}

.jp-DocumentSearch-filter-button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-filter-button-enabled {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-filter-button-enabled:hover {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-search-options {
  padding: 0 8px;
  margin-left: 3px;
  width: 100%;
  display: grid;
  justify-content: start;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  justify-items: stretch;
}

.jp-DocumentSearch-search-filter-disabled {
  color: var(--jp-ui-font-color2);
}

.jp-DocumentSearch-search-filter {
  display: flex;
  align-items: center;
  user-select: none;
}

.jp-DocumentSearch-regex-error {
  color: var(--jp-error-color0);
}

.jp-DocumentSearch-replace-button-wrapper {
  overflow: hidden;
  display: inline-block;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color0);
  margin: auto 2px;
  padding: 1px 4px;
  height: calc(var(--jp-private-document-search-button-height) + 2px);
}

.jp-DocumentSearch-replace-button-wrapper:focus {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
}

.jp-DocumentSearch-replace-button {
  display: inline-block;
  text-align: center;
  cursor: pointer;
  box-sizing: border-box;
  color: var(--jp-ui-font-color1);

  /* height - 2 * (padding of wrapper) */
  line-height: calc(var(--jp-private-document-search-button-height) - 2px);
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-replace-button:focus {
  outline: none;
}

.jp-DocumentSearch-replace-wrapper-class {
  margin-left: 14px;
  display: flex;
}

.jp-DocumentSearch-replace-toggle {
  border: none;
  background-color: var(--jp-toolbar-background);
  border-radius: var(--jp-border-radius);
}

.jp-DocumentSearch-replace-toggle:hover {
  background-color: var(--jp-layout-color2);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.cm-editor {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;

  /* Changed to auto to autogrow */
}

.cm-editor pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .cm-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

.jp-CodeMirrorEditor {
  cursor: text;
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .cm-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .cm-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.cm-editor.jp-mod-readOnly .cm-cursor {
  display: none;
}

.jp-CollaboratorCursor {
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: none;
  border-bottom: 3px solid;
  background-clip: content-box;
  margin-left: -5px;
  margin-right: -5px;
}

.cm-searching,
.cm-searching span {
  /* `.cm-searching span`: we need to override syntax highlighting */
  background-color: var(--jp-search-unselected-match-background-color);
  color: var(--jp-search-unselected-match-color);
}

.cm-searching::selection,
.cm-searching span::selection {
  background-color: var(--jp-search-unselected-match-background-color);
  color: var(--jp-search-unselected-match-color);
}

.jp-current-match > .cm-searching,
.jp-current-match > .cm-searching span,
.cm-searching > .jp-current-match,
.cm-searching > .jp-current-match span {
  background-color: var(--jp-search-selected-match-background-color);
  color: var(--jp-search-selected-match-color);
}

.jp-current-match > .cm-searching::selection,
.cm-searching > .jp-current-match::selection,
.jp-current-match > .cm-searching span::selection {
  background-color: var(--jp-search-selected-match-background-color);
  color: var(--jp-search-selected-match-color);
}

.cm-trailingspace {
  background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAFCAYAAAB4ka1VAAAAsElEQVQIHQGlAFr/AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA7+r3zKmT0/+pk9P/7+r3zAAAAAAAAAAABAAAAAAAAAAA6OPzM+/q9wAAAAAA6OPzMwAAAAAAAAAAAgAAAAAAAAAAGR8NiRQaCgAZIA0AGR8NiQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQyoYJ/SY80UAAAAASUVORK5CYII=);
  background-position: center left;
  background-repeat: repeat-x;
}

.jp-CollaboratorCursor-hover {
  position: absolute;
  z-index: 1;
  transform: translateX(-50%);
  color: white;
  border-radius: 3px;
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 1px;
  padding-bottom: 1px;
  text-align: center;
  font-size: var(--jp-ui-font-size1);
  white-space: nowrap;
}

.jp-CodeMirror-ruler {
  border-left: 1px dashed var(--jp-border-color2);
}

/* Styles for shared cursors (remote cursor locations and selected ranges) */
.jp-CodeMirrorEditor .cm-ySelectionCaret {
  position: relative;
  border-left: 1px solid black;
  margin-left: -1px;
  margin-right: -1px;
  box-sizing: border-box;
}

.jp-CodeMirrorEditor .cm-ySelectionCaret > .cm-ySelectionInfo {
  white-space: nowrap;
  position: absolute;
  top: -1.15em;
  padding-bottom: 0.05em;
  left: -1px;
  font-size: 0.95em;
  font-family: var(--jp-ui-font-family);
  font-weight: bold;
  line-height: normal;
  user-select: none;
  color: white;
  padding-left: 2px;
  padding-right: 2px;
  z-index: 101;
  transition: opacity 0.3s ease-in-out;
}

.jp-CodeMirrorEditor .cm-ySelectionInfo {
  transition-delay: 0.7s;
  opacity: 0;
}

.jp-CodeMirrorEditor .cm-ySelectionCaret:hover > .cm-ySelectionInfo {
  opacity: 1;
  transition-delay: 0s;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MimeDocument {
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-filebrowser-button-height: 28px;
  --jp-private-filebrowser-button-width: 48px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FileBrowser .jp-SidePanel-content {
  display: flex;
  flex-direction: column;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  flex-wrap: wrap;
  row-gap: 12px;
  border-bottom: none;
  height: auto;
  margin: 8px 12px 0;
  box-shadow: none;
  padding: 0;
  justify-content: flex-start;
}

.jp-FileBrowser-Panel {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 8px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0 2px;
  padding: 0 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  padding-left: 0;
  padding-right: 2px;
  align-items: center;
  height: unset;
}

.jp-FileBrowser-toolbar > .jp-Toolbar-item .jp-ToolbarButtonComponent {
  width: 40px;
}

/*-----------------------------------------------------------------------------
| Other styles
|----------------------------------------------------------------------------*/

.jp-FileDialog.jp-mod-conflict input {
  color: var(--jp-error-color1);
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

.jp-LastModified-hidden {
  display: none;
}

.jp-FileSize-hidden {
  display: none;
}

.jp-FileBrowser .lm-AccordionPanel > h3:first-child {
  display: none;
}

/*-----------------------------------------------------------------------------
| DirListing
|----------------------------------------------------------------------------*/

.jp-DirListing {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  outline: 0;
}

.jp-DirListing-header {
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  align-items: center;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px;
  font-weight: 500;
}

.jp-DirListing-headerItem:hover {
  background: var(--jp-layout-color2);
}

.jp-DirListing-headerItem.jp-id-name {
  flex: 1 0 84px;
}

.jp-DirListing-headerItem.jp-id-modified {
  flex: 0 0 112px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-DirListing-headerItem.jp-id-filesize {
  flex: 0 0 75px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-id-narrow {
  display: none;
  flex: 0 0 5px;
  padding: 4px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
  color: var(--jp-border-color2);
}

.jp-DirListing-narrow .jp-id-narrow {
  display: block;
}

.jp-DirListing-narrow .jp-id-modified,
.jp-DirListing-narrow .jp-DirListing-itemModified {
  display: none;
}

.jp-DirListing-headerItem.jp-mod-selected {
  font-weight: 600;
}

/* increase specificity to override bundled default */
.jp-DirListing-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-DirListing-content mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.jp-DirListing-content .jp-DirListing-item.jp-mod-selected mark {
  color: var(--jp-ui-inverse-font-color0);
}

/* Style the directory listing content when a user drops a file to upload */
.jp-DirListing.jp-mod-native-drop .jp-DirListing-content {
  outline: 5px dashed rgba(128, 128, 128, 0.5);
  outline-offset: -10px;
  cursor: copy;
}

.jp-DirListing-item {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-checkboxWrapper {
  /* Increases hit area of checkbox. */
  padding: 4px;
}

.jp-DirListing-header
  .jp-DirListing-checkboxWrapper
  + .jp-DirListing-headerItem {
  padding-left: 4px;
}

.jp-DirListing-content .jp-DirListing-checkboxWrapper {
  position: relative;
  left: -4px;
  margin: -4px 0 -4px -8px;
}

.jp-DirListing-checkboxWrapper.jp-mod-visible {
  visibility: visible;
}

/* For devices that support hovering, hide checkboxes until hovered, selected...
*/
@media (hover: hover) {
  .jp-DirListing-checkboxWrapper {
    visibility: hidden;
  }

  .jp-DirListing-item:hover .jp-DirListing-checkboxWrapper,
  .jp-DirListing-item.jp-mod-selected .jp-DirListing-checkboxWrapper {
    visibility: visible;
  }
}

.jp-DirListing-item[data-is-dot] {
  opacity: 75%;
}

.jp-DirListing-item.jp-mod-selected {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.jp-DirListing-item.jp-mod-dropTarget {
  background: var(--jp-brand-color3);
}

.jp-DirListing-item:hover:not(.jp-mod-selected) {
  background: var(--jp-layout-color2);
}

.jp-DirListing-itemIcon {
  flex: 0 0 20px;
  margin-right: 4px;
}

.jp-DirListing-itemText {
  flex: 1 0 64px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  user-select: none;
}

.jp-DirListing-itemText:focus {
  outline-width: 2px;
  outline-color: var(--jp-inverse-layout-color1);
  outline-style: solid;
  outline-offset: 1px;
}

.jp-DirListing-item.jp-mod-selected .jp-DirListing-itemText:focus {
  outline-color: var(--jp-layout-color1);
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-itemFileSize {
  flex: 0 0 90px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon::before {
  color: var(--jp-success-color1);
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.jp-mod-running.jp-mod-selected
  .jp-DirListing-itemIcon::before {
  color: var(--jp-ui-inverse-font-color1);
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: table;
  table-layout: fixed;
  width: 100%;
  overflow: hidden;
}

.jp-OutputPrompt {
  width: var(--jp-cell-prompt-width);
  color: var(--jp-cell-outprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);

  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;

  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-OutputArea-prompt {
  display: table-cell;
  vertical-align: top;
}

.jp-OutputArea-output {
  display: table-cell;
  width: 100%;
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea .jp-RenderedText {
  padding-left: 1ch;
}

/**
 * Prompt overlay.
 */

.jp-OutputArea-promptOverlay {
  position: absolute;
  top: 0;
  width: var(--jp-cell-prompt-width);
  height: 100%;
  opacity: 0.5;
}

.jp-OutputArea-promptOverlay:hover {
  background: var(--jp-layout-color2);
  box-shadow: inset 0 0 1px var(--jp-inverse-layout-color0);
  cursor: zoom-out;
}

.jp-mod-outputsScrolled .jp-OutputArea-promptOverlay:hover {
  cursor: zoom-in;
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `lm-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/* pre */

.jp-OutputArea-output pre {
  border: none;
  margin: 0;
  padding: 0;
  overflow-x: auto;
  overflow-y: auto;
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}

/* tables */

.jp-OutputArea-output.jp-RenderedHTMLCommon table {
  margin-left: 0;
  margin-right: 0;
}

/* description lists */

.jp-OutputArea-output dl,
.jp-OutputArea-output dt,
.jp-OutputArea-output dd {
  display: block;
}

.jp-OutputArea-output dl {
  width: 100%;
  overflow: hidden;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dt {
  font-weight: bold;
  float: left;
  width: 20%;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dd {
  float: left;
  width: 80%;
  padding: 0;
  margin: 0;
}

.jp-TrimmedOutputs pre {
  background: var(--jp-layout-color3);
  font-size: calc(var(--jp-code-font-size) * 1.4);
  text-align: center;
  text-transform: uppercase;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/* Hide empty lines in the output area, for instance due to cleared widgets */
.jp-OutputArea-prompt:empty {
  padding: 0;
  border: 0;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0;
  width: 100%;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
  border-top: var(--jp-border-width) solid transparent;
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

.jp-Stdin-prompt {
  color: var(--jp-content-font-color0);
  padding-right: var(--jp-code-padding);
  vertical-align: baseline;
  flex: 0 0 auto;
}

.jp-Stdin-input {
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  color: inherit;
  background-color: inherit;
  width: 42%;
  min-width: 200px;

  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;

  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0 0.25em;
  margin: 0 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input::placeholder {
  opacity: 0;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

.jp-Stdin-input:focus::placeholder {
  opacity: 1;
}

/*-----------------------------------------------------------------------------
| Output Area View
|----------------------------------------------------------------------------*/

.jp-LinkedOutputView .jp-OutputArea {
  height: 100%;
  display: block;
}

.jp-LinkedOutputView .jp-OutputArea-output:only-child {
  height: 100%;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

@media print {
  .jp-OutputArea-child {
    break-inside: avoid-page;
  }
}

/*-----------------------------------------------------------------------------
| Mobile
|----------------------------------------------------------------------------*/
@media only screen and (max-width: 760px) {
  .jp-OutputPrompt {
    display: table-row;
    text-align: left;
  }

  .jp-OutputArea-child .jp-OutputArea-output {
    display: table-row;
    margin-left: var(--jp-notebook-padding);
  }
}

/* Trimmed outputs warning */
.jp-TrimmedOutputs > a {
  margin: 10px;
  text-decoration: none;
  cursor: pointer;
}

.jp-TrimmedOutputs > a:hover {
  text-decoration: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Table of Contents
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toc-active-width: 4px;
}

.jp-TableOfContents {
  display: flex;
  flex-direction: column;
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  height: 100%;
}

.jp-TableOfContents-placeholder {
  text-align: center;
}

.jp-TableOfContents-placeholderContent {
  color: var(--jp-content-font-color2);
  padding: 8px;
}

.jp-TableOfContents-placeholderContent > h3 {
  margin-bottom: var(--jp-content-heading-margin-bottom);
}

.jp-TableOfContents .jp-SidePanel-content {
  overflow-y: auto;
}

.jp-TableOfContents-tree {
  margin: 4px;
}

.jp-TableOfContents ol {
  list-style-type: none;
}

/* stylelint-disable-next-line selector-max-type */
.jp-TableOfContents li > ol {
  /* Align left border with triangle icon center */
  padding-left: 11px;
}

.jp-TableOfContents-content {
  /* left margin for the active heading indicator */
  margin: 0 0 0 var(--jp-private-toc-active-width);
  padding: 0;
  background-color: var(--jp-layout-color1);
}

.jp-tocItem {
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-tocItem-heading {
  display: flex;
  cursor: pointer;
}

.jp-tocItem-heading:hover {
  background-color: var(--jp-layout-color2);
}

.jp-tocItem-content {
  display: block;
  padding: 4px 0;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow-x: hidden;
}

.jp-tocItem-collapser {
  height: 20px;
  margin: 2px 2px 0;
  padding: 0;
  background: none;
  border: none;
  cursor: pointer;
}

.jp-tocItem-collapser:hover {
  background-color: var(--jp-layout-color3);
}

/* Active heading indicator */

.jp-tocItem-heading::before {
  content: ' ';
  background: transparent;
  width: var(--jp-private-toc-active-width);
  height: 24px;
  position: absolute;
  left: 0;
  border-radius: var(--jp-border-radius);
}

.jp-tocItem-heading.jp-tocItem-active::before {
  background-color: var(--jp-brand-color1);
}

.jp-tocItem-heading:hover.jp-tocItem-active::before {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0;
  margin: 0;
  border: none;
  outline: none;
  background: transparent;
  border-radius: var(--jp-border-radius);
  opacity: 1;
}

.jp-Collapser-child {
  display: block;
  width: 100%;
  box-sizing: border-box;

  /* height: 100% doesn't work because the height of its parent is computed from content */
  position: absolute;
  top: 0;
  bottom: 0;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

/*
Hiding collapsers in print mode.

Note: input and output wrappers have "display: block" propery in print mode.
*/

@media print {
  .jp-Collapser {
    display: none;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Header/Footer
|----------------------------------------------------------------------------*/

/* Hidden by zero height by default */
.jp-CellHeader,
.jp-CellFooter {
  height: 0;
  width: 100%;
  padding: 0;
  margin: 0;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Input
|----------------------------------------------------------------------------*/

/* All input areas */
.jp-InputArea {
  display: table;
  table-layout: fixed;
  width: 100%;
  overflow: hidden;
}

.jp-InputArea-editor {
  display: table-cell;
  overflow: hidden;
  vertical-align: top;

  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0;
  background: var(--jp-cell-editor-background);
}

.jp-InputPrompt {
  display: table-cell;
  vertical-align: top;
  width: var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;

  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;

  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/*-----------------------------------------------------------------------------
| Mobile
|----------------------------------------------------------------------------*/
@media only screen and (max-width: 760px) {
  .jp-InputArea-editor {
    display: table-row;
    margin-left: var(--jp-notebook-padding);
  }

  .jp-InputPrompt {
    display: table-row;
    text-align: left;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: table;
  table-layout: fixed;
  width: 100%;
}

.jp-Placeholder-prompt {
  display: table-cell;
  box-sizing: border-box;
}

.jp-Placeholder-content {
  display: table-cell;
  padding: 4px 6px;
  border: 1px solid transparent;
  border-radius: 0;
  background: none;
  box-sizing: border-box;
  cursor: pointer;
}

.jp-Placeholder-contentContainer {
  display: flex;
}

.jp-Placeholder-content:hover,
.jp-InputPlaceholder > .jp-Placeholder-content:hover {
  border-color: var(--jp-layout-color3);
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0 0 2px 0 rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

.jp-PlaceholderText {
  white-space: nowrap;
  overflow-x: hidden;
  color: var(--jp-inverse-layout-color3);
  font-family: var(--jp-code-font-family);
}

.jp-InputPlaceholder > .jp-Placeholder-content {
  border-color: var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-cell-scrolling-output-offset: 5px;
}

/*-----------------------------------------------------------------------------
| Cell
|----------------------------------------------------------------------------*/

.jp-Cell {
  padding: var(--jp-cell-padding);
  margin: 0;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Common input/output
|----------------------------------------------------------------------------*/

.jp-Cell-inputWrapper,
.jp-Cell-outputWrapper {
  display: flex;
  flex-direction: row;
  padding: 0;
  margin: 0;

  /* Added to reveal the box-shadow on the input and output collapsers. */
  overflow: visible;
}

/* Only input/output areas inside cells */
.jp-Cell-inputArea,
.jp-Cell-outputArea {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Collapser
|----------------------------------------------------------------------------*/

/* Make the output collapser disappear when there is not output, but do so
 * in a manner that leaves it in the layout and preserves its width.
 */
.jp-Cell.jp-mod-noOutputs .jp-Cell-outputCollapser {
  border: none !important;
  background: transparent !important;
}

.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputCollapser {
  min-height: var(--jp-cell-collapser-min-height);
}

/*-----------------------------------------------------------------------------
| Output
|----------------------------------------------------------------------------*/

/* Put a space between input and output when there IS output */
.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputWrapper {
  margin-top: 5px;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 24em;
  margin-left: var(--jp-private-cell-scrolling-output-offset);
  resize: vertical;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea[style*='height'] {
  max-height: unset;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea::after {
  content: ' ';
  box-shadow: inset 0 0 6px 2px rgb(0 0 0 / 30%);
  width: 100%;
  height: 100%;
  position: sticky;
  bottom: 0;
  top: 0;
  margin-top: -50%;
  float: left;
  display: block;
  pointer-events: none;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-child {
  padding-top: 6px;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  width: calc(
    var(--jp-cell-prompt-width) - var(--jp-private-cell-scrolling-output-offset)
  );
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-promptOverlay {
  left: calc(-1 * var(--jp-private-cell-scrolling-output-offset));
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  display: table-cell;
  width: 100%;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

/* collapseHeadingButton (show always if hiddenCellsButton is _not_ shown) */
.jp-collapseHeadingButton {
  display: flex;
  min-height: var(--jp-cell-collapser-min-height);
  font-size: var(--jp-code-font-size);
  position: absolute;
  background-color: transparent;
  background-size: 25px;
  background-repeat: no-repeat;
  background-position-x: center;
  background-position-y: top;
  background-image: var(--jp-icon-caret-down);
  right: 0;
  top: 0;
  bottom: 0;
}

.jp-collapseHeadingButton.jp-mod-collapsed {
  background-image: var(--jp-icon-caret-right);
}

/*
 set the container font size to match that of content
 so that the nested collapse buttons have the right size
*/
.jp-MarkdownCell .jp-InputPrompt {
  font-size: var(--jp-content-font-size1);
}

/*
  Align collapseHeadingButton with cell top header
  The font sizes are identical to the ones in packages/rendermime/style/base.css
*/
.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='1'] {
  font-size: var(--jp-content-font-size5);
  background-position-y: calc(0.3 * var(--jp-content-font-size5));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='2'] {
  font-size: var(--jp-content-font-size4);
  background-position-y: calc(0.3 * var(--jp-content-font-size4));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='3'] {
  font-size: var(--jp-content-font-size3);
  background-position-y: calc(0.3 * var(--jp-content-font-size3));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='4'] {
  font-size: var(--jp-content-font-size2);
  background-position-y: calc(0.3 * var(--jp-content-font-size2));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='5'] {
  font-size: var(--jp-content-font-size1);
  background-position-y: top;
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='6'] {
  font-size: var(--jp-content-font-size0);
  background-position-y: top;
}

/* collapseHeadingButton (show only on (hover,active) if hiddenCellsButton is shown) */
.jp-Notebook.jp-mod-showHiddenCellsButton .jp-collapseHeadingButton {
  display: none;
}

.jp-Notebook.jp-mod-showHiddenCellsButton
  :is(.jp-MarkdownCell:hover, .jp-mod-active)
  .jp-collapseHeadingButton {
  display: flex;
}

/* showHiddenCellsButton (only show if jp-mod-showHiddenCellsButton is set, which
is a consequence of the showHiddenCellsButton option in Notebook Settings)*/
.jp-Notebook.jp-mod-showHiddenCellsButton .jp-showHiddenCellsButton {
  margin-left: calc(var(--jp-cell-prompt-width) + 2 * var(--jp-code-padding));
  margin-top: var(--jp-code-padding);
  border: 1px solid var(--jp-border-color2);
  background-color: var(--jp-border-color3) !important;
  color: var(--jp-content-font-color0) !important;
  display: flex;
}

.jp-Notebook.jp-mod-showHiddenCellsButton .jp-showHiddenCellsButton:hover {
  background-color: var(--jp-border-color2) !important;
}

.jp-showHiddenCellsButton {
  display: none;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

/*
Using block instead of flex to allow the use of the break-inside CSS property for
cell outputs.
*/

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-notebook-toolbar-padding: 2px 5px 2px 2px;
}

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: var(--jp-notebook-toolbar-padding);

  /* disable paint containment from lumino 2.0 default strict CSS containment */
  contain: style size !important;
}

.jp-Toolbar-item.jp-Notebook-toolbarCellType .jp-select-wrapper.jp-mod-focused {
  border: none;
  box-shadow: none;
}

.jp-Notebook-toolbarCellTypeDropdown select {
  height: 24px;
  font-size: var(--jp-ui-font-size1);
  line-height: 14px;
  border-radius: 0;
  display: block;
}

.jp-Notebook-toolbarCellTypeDropdown span {
  top: 5px !important;
}

.jp-Toolbar-responsive-popup {
  position: absolute;
  height: fit-content;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: flex-end;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: var(--jp-notebook-toolbar-padding);
  z-index: 1;
  right: 0;
  top: 0;
}

.jp-Toolbar > .jp-Toolbar-responsive-opener {
  margin-left: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-Notebook-ExecutionIndicator {
  position: relative;
  display: inline-block;
  height: 100%;
  z-index: 9997;
}

.jp-Notebook-ExecutionIndicator-tooltip {
  visibility: hidden;
  height: auto;
  width: max-content;
  width: -moz-max-content;
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color1);
  text-align: justify;
  border-radius: 6px;
  padding: 0 5px;
  position: fixed;
  display: table;
}

.jp-Notebook-ExecutionIndicator-tooltip.up {
  transform: translateX(-50%) translateY(-100%) translateY(-32px);
}

.jp-Notebook-ExecutionIndicator-tooltip.down {
  transform: translateX(calc(-100% + 16px)) translateY(5px);
}

.jp-Notebook-ExecutionIndicator-tooltip.hidden {
  display: none;
}

.jp-Notebook-ExecutionIndicator:hover .jp-Notebook-ExecutionIndicator-tooltip {
  visibility: visible;
}

.jp-Notebook-ExecutionIndicator span {
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  color: var(--jp-ui-font-color1);
  line-height: 24px;
  display: block;
}

.jp-Notebook-ExecutionIndicator-progress-bar {
  display: flex;
  justify-content: center;
  height: 100%;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*
 * Execution indicator
 */
.jp-tocItem-content::after {
  content: '';

  /* Must be identical to form a circle */
  width: 12px;
  height: 12px;
  background: none;
  border: none;
  position: absolute;
  right: 0;
}

.jp-tocItem-content[data-running='0']::after {
  border-radius: 50%;
  border: var(--jp-border-width) solid var(--jp-inverse-layout-color3);
  background: none;
}

.jp-tocItem-content[data-running='1']::after {
  border-radius: 50%;
  border: var(--jp-border-width) solid var(--jp-inverse-layout-color3);
  background-color: var(--jp-inverse-layout-color3);
}

.jp-tocItem-content[data-running='0'],
.jp-tocItem-content[data-running='1'] {
  margin-right: 12px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-Notebook-footer {
  height: 27px;
  margin-left: calc(
    var(--jp-cell-prompt-width) + var(--jp-cell-collapser-width) +
      var(--jp-cell-padding)
  );
  width: calc(
    100% -
      (
        var(--jp-cell-prompt-width) + var(--jp-cell-collapser-width) +
          var(--jp-cell-padding) + var(--jp-cell-padding)
      )
  );
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  color: var(--jp-ui-font-color3);
  margin-top: 6px;
  background: none;
  cursor: pointer;
}

.jp-Notebook-footer:focus {
  border-color: var(--jp-cell-editor-active-border-color);
}

/* For devices that support hovering, hide footer until hover */
@media (hover: hover) {
  .jp-Notebook-footer {
    opacity: 0;
  }

  .jp-Notebook-footer:focus,
  .jp-Notebook-footer:hover {
    opacity: 1;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-side-by-side-output-size: 1fr;
  --jp-side-by-side-resized-cell: var(--jp-side-by-side-output-size);
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

/* stylelint-disable selector-max-class */

.jp-NotebookPanel {
  display: block;
  height: 100%;
}

.jp-NotebookPanel.jp-Document {
  min-width: 240px;
  min-height: 120px;
}

.jp-Notebook {
  padding: var(--jp-notebook-padding);
  outline: none;
  overflow: auto;
  background: var(--jp-layout-color0);
}

.jp-Notebook.jp-mod-scrollPastEnd::after {
  display: block;
  content: '';
  min-height: var(--jp-notebook-scroll-padding);
}

.jp-MainAreaWidget-ContainStrict .jp-Notebook * {
  contain: strict;
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
}

/*-----------------------------------------------------------------------------
| Notebook state related styling
|
| The notebook and cells each have states, here are the possibilities:
|
| - Notebook
|   - Command
|   - Edit
| - Cell
|   - None
|   - Active (only one can be active)
|   - Selected (the cells actions are applied to)
|   - Multiselected (when multiple selected, the cursor)
|   - No outputs
|----------------------------------------------------------------------------*/

/* Command or edit modes */

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-InputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-OutputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

/* cell is active */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser {
  background: var(--jp-brand-color1);
}

/* cell is dirty */
.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt {
  color: var(--jp-warn-color1);
}

.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt::before {
  color: var(--jp-warn-color1);
  content: '•';
}

.jp-Notebook .jp-Cell.jp-mod-active.jp-mod-dirty .jp-Collapser {
  background: var(--jp-warn-color1);
}

/* collapser is hovered */
.jp-Notebook .jp-Cell .jp-Collapser:hover {
  box-shadow: var(--jp-elevation-z2);
  background: var(--jp-brand-color1);
  opacity: var(--jp-cell-collapser-not-active-hover-opacity);
}

/* cell is active and collapser is hovered */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser:hover {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/* Command mode */

.jp-Notebook.jp-mod-commandMode .jp-Cell.jp-mod-selected {
  background: var(--jp-notebook-multiselected-color);
}

.jp-Notebook.jp-mod-commandMode
  .jp-Cell.jp-mod-active.jp-mod-selected:not(.jp-mod-multiSelected) {
  background: transparent;
}

/* Edit mode */

.jp-Notebook.jp-mod-editMode .jp-Cell.jp-mod-active .jp-InputArea-editor {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-cell-editor-active-background);
}

/*-----------------------------------------------------------------------------
| Notebook drag and drop
|----------------------------------------------------------------------------*/

.jp-Notebook-cell.jp-mod-dropSource {
  opacity: 0.5;
}

.jp-Notebook-cell.jp-mod-dropTarget,
.jp-Notebook.jp-mod-commandMode
  .jp-Notebook-cell.jp-mod-active.jp-mod-selected.jp-mod-dropTarget {
  border-top-color: var(--jp-private-notebook-selected-color);
  border-top-style: solid;
  border-top-width: 2px;
}

.jp-dragImage {
  display: block;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0 rgba(0, 0, 0, 0.12);
}

.jp-dragImage .jp-dragImage-content {
  flex: 1 1 auto;
  z-index: 2;
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  line-height: var(--jp-code-line-height);
  padding: var(--jp-code-padding);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background-color);
  color: var(--jp-content-font-color3);
  text-align: left;
  margin: 4px 4px 4px 0;
}

.jp-dragImage .jp-dragImage-prompt {
  flex: 0 0 auto;
  min-width: 36px;
  color: var(--jp-cell-inprompt-font-color);
  padding: var(--jp-code-padding);
  padding-left: 12px;
  font-family: var(--jp-cell-prompt-font-family);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: 1.9;
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
}

.jp-dragImage-multipleBack {
  z-index: -1;
  position: absolute;
  height: 32px;
  width: 300px;
  top: 8px;
  left: 8px;
  background: var(--jp-layout-color2);
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  box-shadow: 2px 2px 4px 0 rgba(0, 0, 0, 0.12);
}

/*-----------------------------------------------------------------------------
| Cell toolbar
|----------------------------------------------------------------------------*/

.jp-NotebookTools {
  display: block;
  min-width: var(--jp-sidebar-min-width);
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);

  /* This is needed so that all font sizing of children done in ems is
    * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  overflow: auto;
}

.jp-ActiveCellTool {
  padding: 12px 0;
  display: flex;
}

.jp-ActiveCellTool-Content {
  flex: 1 1 auto;
}

.jp-ActiveCellTool .jp-ActiveCellTool-CellContent {
  background: var(--jp-cell-editor-background);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0;
  min-height: 29px;
}

.jp-ActiveCellTool .jp-InputPrompt {
  min-width: calc(var(--jp-cell-prompt-width) * 0.75);
}

.jp-ActiveCellTool-CellContent > pre {
  padding: 5px 4px;
  margin: 0;
  white-space: normal;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0;
}

.jp-RankedPanel > :not(:first-child) {
  margin-top: 12px;
}

.jp-KeySelector select.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: var(--jp-border-width) solid var(--jp-border-color1);
}

.jp-KeySelector label,
.jp-MetadataEditorTool label,
.jp-NumberSetter label {
  line-height: 1.4;
}

.jp-NotebookTools .jp-select-wrapper {
  margin-top: 4px;
  margin-bottom: 0;
}

.jp-NumberSetter input {
  width: 100%;
  margin-top: 4px;
}

.jp-NotebookTools .jp-Collapse {
  margin-top: 16px;
}

/*-----------------------------------------------------------------------------
| Presentation Mode (.jp-mod-presentationMode)
|----------------------------------------------------------------------------*/

.jp-mod-presentationMode .jp-Notebook {
  --jp-content-font-size1: var(--jp-content-presentation-font-size1);
  --jp-code-font-size: var(--jp-code-presentation-font-size);
}

.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-InputPrompt,
.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-OutputPrompt {
  flex: 0 0 110px;
}

/*-----------------------------------------------------------------------------
| Side-by-side Mode (.jp-mod-sideBySide)
|----------------------------------------------------------------------------*/
.jp-mod-sideBySide.jp-Notebook .jp-Notebook-cell {
  margin-top: 3em;
  margin-bottom: 3em;
  margin-left: 5%;
  margin-right: 5%;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell {
  display: grid;
  grid-template-columns: minmax(0, 1fr) min-content minmax(
      0,
      var(--jp-side-by-side-output-size)
    );
  grid-template-rows: auto minmax(0, 1fr) auto;
  grid-template-areas:
    'header header header'
    'input handle output'
    'footer footer footer';
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell.jp-mod-resizedCell {
  grid-template-columns: minmax(0, 1fr) min-content minmax(
      0,
      var(--jp-side-by-side-resized-cell)
    );
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellHeader {
  grid-area: header;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-Cell-inputWrapper {
  grid-area: input;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-Cell-outputWrapper {
  /* overwrite the default margin (no vertical separation needed in side by side move */
  margin-top: 0;
  grid-area: output;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellFooter {
  grid-area: footer;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellResizeHandle {
  grid-area: handle;
  user-select: none;
  display: block;
  height: 100%;
  cursor: ew-resize;
  padding: 0 var(--jp-cell-padding);
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellResizeHandle::after {
  content: '';
  display: block;
  background: var(--jp-border-color2);
  height: 100%;
  width: 5px;
}

.jp-mod-sideBySide.jp-Notebook
  .jp-CodeCell.jp-mod-resizedCell
  .jp-CellResizeHandle::after {
  background: var(--jp-border-color0);
}

.jp-CellResizeHandle {
  display: none;
}

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Cell-Placeholder {
  padding-left: 55px;
}

.jp-Cell-Placeholder-wrapper {
  background: #fff;
  border: 1px solid;
  border-color: #e5e6e9 #dfe0e4 #d0d1d5;
  border-radius: 4px;
  -webkit-border-radius: 4px;
  margin: 10px 15px;
}

.jp-Cell-Placeholder-wrapper-inner {
  padding: 15px;
  position: relative;
}

.jp-Cell-Placeholder-wrapper-body {
  background-repeat: repeat;
  background-size: 50% auto;
}

.jp-Cell-Placeholder-wrapper-body div {
  background: #f6f7f8;
  background-image: -webkit-linear-gradient(
    left,
    #f6f7f8 0%,
    #edeef1 20%,
    #f6f7f8 40%,
    #f6f7f8 100%
  );
  background-repeat: no-repeat;
  background-size: 800px 104px;
  height: 104px;
  position: absolute;
  right: 15px;
  left: 15px;
  top: 15px;
}

div.jp-Cell-Placeholder-h1 {
  top: 20px;
  height: 20px;
  left: 15px;
  width: 150px;
}

div.jp-Cell-Placeholder-h2 {
  left: 15px;
  top: 50px;
  height: 10px;
  width: 100px;
}

div.jp-Cell-Placeholder-content-1,
div.jp-Cell-Placeholder-content-2,
div.jp-Cell-Placeholder-content-3 {
  left: 15px;
  right: 15px;
  height: 10px;
}

div.jp-Cell-Placeholder-content-1 {
  top: 100px;
}

div.jp-Cell-Placeholder-content-2 {
  top: 120px;
}

div.jp-Cell-Placeholder-content-3 {
  top: 140px;
}

</style>
<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
The following CSS variables define the main, public API for styling JupyterLab.
These variables should be used by all plugins wherever possible. In other
words, plugins should not define custom colors, sizes, etc unless absolutely
necessary. This enables users to change the visual theme of JupyterLab
by changing these variables.

Many variables appear in an ordered sequence (0,1,2,3). These sequences
are designed to work well together, so for example, `--jp-border-color1` should
be used with `--jp-layout-color1`. The numbers have the following meanings:

* 0: super-primary, reserved for special emphasis
* 1: primary, most important under normal situations
* 2: secondary, next most important under normal situations
* 3: tertiary, next most important under normal situations

Throughout JupyterLab, we are mostly following principles from Google's
Material Design when selecting colors. We are not, however, following
all of MD as it is not optimized for dense, information rich UIs.
*/

:root {
  /* Elevation
   *
   * We style box-shadows using Material Design's idea of elevation. These particular numbers are taken from here:
   *
   * https://github.com/material-components/material-components-web
   * https://material-components-web.appspot.com/elevation.html
   */

  --jp-shadow-base-lightness: 0;
  --jp-shadow-umbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.2
  );
  --jp-shadow-penumbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.14
  );
  --jp-shadow-ambient-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.12
  );
  --jp-elevation-z0: none;
  --jp-elevation-z1: 0 2px 1px -1px var(--jp-shadow-umbra-color),
    0 1px 1px 0 var(--jp-shadow-penumbra-color),
    0 1px 3px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0 3px 1px -2px var(--jp-shadow-umbra-color),
    0 2px 2px 0 var(--jp-shadow-penumbra-color),
    0 1px 5px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0 2px 4px -1px var(--jp-shadow-umbra-color),
    0 4px 5px 0 var(--jp-shadow-penumbra-color),
    0 1px 10px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0 3px 5px -1px var(--jp-shadow-umbra-color),
    0 6px 10px 0 var(--jp-shadow-penumbra-color),
    0 1px 18px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0 5px 5px -3px var(--jp-shadow-umbra-color),
    0 8px 10px 1px var(--jp-shadow-penumbra-color),
    0 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0 7px 8px -4px var(--jp-shadow-umbra-color),
    0 12px 17px 2px var(--jp-shadow-penumbra-color),
    0 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0 8px 10px -5px var(--jp-shadow-umbra-color),
    0 16px 24px 2px var(--jp-shadow-penumbra-color),
    0 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0 10px 13px -6px var(--jp-shadow-umbra-color),
    0 20px 31px 3px var(--jp-shadow-penumbra-color),
    0 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0 11px 15px -7px var(--jp-shadow-umbra-color),
    0 24px 38px 3px var(--jp-shadow-penumbra-color),
    0 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-inverse-border-color: var(--md-grey-600);
  --jp-border-radius: 2px;

  /* UI Fonts
   *
   * The UI font CSS variables are used for the typography all of the JupyterLab
   * user interface elements that are not directly user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-ui-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-ui-font-scale-factor: 1.2;
  --jp-ui-font-size0: 0.83333em;
  --jp-ui-font-size1: 13px; /* Base font size */
  --jp-ui-font-size2: 1.2em;
  --jp-ui-font-size3: 1.44em;
  --jp-ui-font-family: system-ui, -apple-system, blinkmacsystemfont, 'Segoe UI',
    helvetica, arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

  /*
   * Use these font colors against the corresponding main layout colors.
   * In a light theme, these go from dark to light.
   */

  /* Defaults use Material Design specification */
  --jp-ui-font-color0: rgba(0, 0, 0, 1);
  --jp-ui-font-color1: rgba(0, 0, 0, 0.87);
  --jp-ui-font-color2: rgba(0, 0, 0, 0.54);
  --jp-ui-font-color3: rgba(0, 0, 0, 0.38);

  /*
   * Use these against the brand/accent/warn/error colors.
   * These will typically go from light to darker, in both a dark and light theme.
   */

  --jp-ui-inverse-font-color0: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color1: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color2: rgba(255, 255, 255, 0.7);
  --jp-ui-inverse-font-color3: rgba(255, 255, 255, 0.5);

  /* Content Fonts
   *
   * Content font variables are used for typography of user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-content-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-content-line-height: 1.6;
  --jp-content-font-scale-factor: 1.2;
  --jp-content-font-size0: 0.83333em;
  --jp-content-font-size1: 14px; /* Base font size */
  --jp-content-font-size2: 1.2em;
  --jp-content-font-size3: 1.44em;
  --jp-content-font-size4: 1.728em;
  --jp-content-font-size5: 2.0736em;

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-content-presentation-font-size1: 17px;
  --jp-content-heading-line-height: 1;
  --jp-content-heading-margin-top: 1.2em;
  --jp-content-heading-margin-bottom: 0.8em;
  --jp-content-heading-font-weight: 500;

  /* Defaults use Material Design specification */
  --jp-content-font-color0: rgba(0, 0, 0, 1);
  --jp-content-font-color1: rgba(0, 0, 0, 0.87);
  --jp-content-font-color2: rgba(0, 0, 0, 0.54);
  --jp-content-font-color3: rgba(0, 0, 0, 0.38);
  --jp-content-link-color: var(--md-blue-900);
  --jp-content-font-family: system-ui, -apple-system, blinkmacsystemfont,
    'Segoe UI', helvetica, arial, sans-serif, 'Apple Color Emoji',
    'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: menlo, consolas, 'DejaVu Sans Mono', monospace;
  --jp-code-font-family: var(--jp-code-font-family-default);

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-code-presentation-font-size: 16px;

  /* may need to tweak cursor width if you change font size */
  --jp-code-cursor-width0: 1.4px;
  --jp-code-cursor-width1: 2px;
  --jp-code-cursor-width2: 4px;

  /* Layout
   *
   * The following are the main layout colors use in JupyterLab. In a light
   * theme these would go from light to dark.
   */

  --jp-layout-color0: white;
  --jp-layout-color1: white;
  --jp-layout-color2: var(--md-grey-200);
  --jp-layout-color3: var(--md-grey-400);
  --jp-layout-color4: var(--md-grey-600);

  /* Inverse Layout
   *
   * The following are the inverse layout colors use in JupyterLab. In a light
   * theme these would go from dark to light.
   */

  --jp-inverse-layout-color0: #111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-900);
  --jp-brand-color1: var(--md-blue-700);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);
  --jp-accent-color0: var(--md-green-900);
  --jp-accent-color1: var(--md-green-700);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-900);
  --jp-warn-color1: var(--md-orange-700);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);
  --jp-error-color0: var(--md-red-900);
  --jp-error-color1: var(--md-red-700);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);
  --jp-success-color0: var(--md-green-900);
  --jp-success-color1: var(--md-green-700);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);
  --jp-info-color0: var(--md-cyan-900);
  --jp-info-color1: var(--md-cyan-700);
  --jp-info-color2: var(--md-cyan-300);
  --jp-info-color3: var(--md-cyan-100);

  /* Cell specific styles */

  --jp-cell-padding: 5px;
  --jp-cell-collapser-width: 8px;
  --jp-cell-collapser-min-height: 20px;
  --jp-cell-collapser-not-active-hover-opacity: 0.6;
  --jp-cell-editor-background: var(--md-grey-100);
  --jp-cell-editor-border-color: var(--md-grey-300);
  --jp-cell-editor-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-cell-editor-active-background: var(--jp-layout-color0);
  --jp-cell-editor-active-border-color: var(--jp-brand-color1);
  --jp-cell-prompt-width: 64px;
  --jp-cell-prompt-font-family: var(--jp-code-font-family-default);
  --jp-cell-prompt-letter-spacing: 0;
  --jp-cell-prompt-opacity: 1;
  --jp-cell-prompt-not-active-opacity: 0.5;
  --jp-cell-prompt-not-active-font-color: var(--md-grey-700);

  /* A custom blend of MD grey and blue 600
   * See https://meyerweb.com/eric/tools/color-blend/#546E7A:1E88E5:5:hex */
  --jp-cell-inprompt-font-color: #307fc1;

  /* A custom blend of MD grey and orange 600
   * https://meyerweb.com/eric/tools/color-blend/#546E7A:F4511E:5:hex */
  --jp-cell-outprompt-font-color: #bf5b3d;

  /* Notebook specific styles */

  --jp-notebook-padding: 10px;
  --jp-notebook-select-background: var(--jp-layout-color1);
  --jp-notebook-multiselected-color: var(--md-blue-50);

  /* The scroll padding is calculated to fill enough space at the bottom of the
  notebook to show one single-line cell (with appropriate padding) at the top
  when the notebook is scrolled all the way to the bottom. We also subtract one
  pixel so that no scrollbar appears if we have just one single-line cell in the
  notebook. This padding is to enable a 'scroll past end' feature in a notebook.
  */
  --jp-notebook-scroll-padding: calc(
    100% - var(--jp-code-font-size) * var(--jp-code-line-height) -
      var(--jp-code-padding) - var(--jp-cell-padding) - 1px
  );

  /* Rendermime styles */

  --jp-rendermime-error-background: #fdd;
  --jp-rendermime-table-row-background: var(--md-grey-100);
  --jp-rendermime-table-row-hover-background: var(--md-light-blue-50);

  /* Dialog specific styles */

  --jp-dialog-background: rgba(0, 0, 0, 0.25);

  /* Console specific styles */

  --jp-console-padding: 10px;

  /* Toolbar specific styles */

  --jp-toolbar-border-color: var(--jp-border-color1);
  --jp-toolbar-micro-height: 8px;
  --jp-toolbar-background: var(--jp-layout-color1);
  --jp-toolbar-box-shadow: 0 0 2px 0 rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Statusbar specific styles */

  --jp-statusbar-height: 24px;

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-inverse-border-color);
  --jp-input-active-border-color: var(--jp-brand-color1);
  --jp-input-active-box-shadow-color: rgba(19, 124, 189, 0.3);

  /* General editor styles */

  --jp-editor-selected-background: #d9d9d9;
  --jp-editor-selected-focused-background: #d7d4f0;
  --jp-editor-cursor-color: var(--jp-ui-font-color0);

  /* Code mirror specific styles */

  --jp-mirror-editor-keyword-color: #008000;
  --jp-mirror-editor-atom-color: #88f;
  --jp-mirror-editor-number-color: #080;
  --jp-mirror-editor-def-color: #00f;
  --jp-mirror-editor-variable-color: var(--md-grey-900);
  --jp-mirror-editor-variable-2-color: rgb(0, 54, 109);
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #a2f;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #a2f;
  --jp-mirror-editor-qualifier-color: #555;
  --jp-mirror-editor-builtin-color: #008000;
  --jp-mirror-editor-bracket-color: #997;
  --jp-mirror-editor-tag-color: #170;
  --jp-mirror-editor-attribute-color: #00c;
  --jp-mirror-editor-header-color: blue;
  --jp-mirror-editor-quote-color: #090;
  --jp-mirror-editor-link-color: #00c;
  --jp-mirror-editor-error-color: #f00;
  --jp-mirror-editor-hr-color: #999;

  /*
    RTC user specific colors.
    These colors are used for the cursor, username in the editor,
    and the icon of the user.
  */

  --jp-collaborator-color1: #ffad8e;
  --jp-collaborator-color2: #dac83d;
  --jp-collaborator-color3: #72dd76;
  --jp-collaborator-color4: #00e4d0;
  --jp-collaborator-color5: #45d4ff;
  --jp-collaborator-color6: #e2b1ff;
  --jp-collaborator-color7: #ff9de6;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 250px;

  /* Search-related styles */

  --jp-search-toggle-off-opacity: 0.5;
  --jp-search-toggle-hover-opacity: 0.8;
  --jp-search-toggle-on-opacity: 1;
  --jp-search-selected-match-background-color: rgb(245, 200, 0);
  --jp-search-selected-match-color: black;
  --jp-search-unselected-match-background-color: var(
    --jp-inverse-layout-color0
  );
  --jp-search-unselected-match-color: var(--jp-ui-inverse-font-color0);

  /* Icon colors that work well with light or dark backgrounds */
  --jp-icon-contrast-color0: var(--md-purple-600);
  --jp-icon-contrast-color1: var(--md-green-600);
  --jp-icon-contrast-color2: var(--md-pink-600);
  --jp-icon-contrast-color3: var(--md-blue-600);

  /* Button colors */
  --jp-accept-color-normal: var(--md-blue-700);
  --jp-accept-color-hover: var(--md-blue-800);
  --jp-accept-color-active: var(--md-blue-900);
  --jp-warn-color-normal: var(--md-red-700);
  --jp-warn-color-hover: var(--md-red-800);
  --jp-warn-color-active: var(--md-red-900);
  --jp-reject-color-normal: var(--md-grey-600);
  --jp-reject-color-hover: var(--md-grey-700);
  --jp-reject-color-active: var(--md-grey-800);

  /* File or activity icons and switch semantic variables */
  --jp-jupyter-icon-color: #f37626;
  --jp-notebook-icon-color: #f37626;
  --jp-json-icon-color: var(--md-orange-700);
  --jp-console-icon-background-color: var(--md-blue-700);
  --jp-console-icon-color: white;
  --jp-terminal-icon-background-color: var(--md-grey-800);
  --jp-terminal-icon-color: var(--md-grey-200);
  --jp-text-editor-icon-color: var(--md-grey-700);
  --jp-inspector-icon-color: var(--md-grey-700);
  --jp-switch-color: var(--md-grey-400);
  --jp-switch-true-position-color: var(--md-orange-900);
}
</style>
<style type="text/css">
/* Force rendering true colors when outputing to pdf */
* {
  -webkit-print-color-adjust: exact;
}

/* Misc */
a.anchor-link {
  display: none;
}

/* Input area styling */
.jp-InputArea {
  overflow: hidden;
}

.jp-InputArea-editor {
  overflow: hidden;
}

.cm-editor.cm-s-jupyter .highlight pre {
/* weird, but --jp-code-padding defined to be 5px but 4px horizontal padding is hardcoded for pre.cm-line */
  padding: var(--jp-code-padding) 4px;
  margin: 0;

  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
  color: inherit;

}

.jp-OutputArea-output pre {
  line-height: inherit;
  font-family: inherit;
}

.jp-RenderedText pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
}

/* Hiding the collapser by default */
.jp-Collapser {
  display: none;
}

@page {
    margin: 0.5in; /* Margin for each printed piece of paper */
}

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }
}
</style>
<!-- Load mathjax -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-AMS_CHTML-full,Safe"> </script>
<!-- MathJax configuration -->
<script type="text/x-mathjax-config">
    init_mathjax = function() {
        if (window.MathJax) {
        // MathJax loaded
            MathJax.Hub.Config({
                TeX: {
                    equationNumbers: {
                    autoNumber: "AMS",
                    useLabelIds: true
                    }
                },
                tex2jax: {
                    inlineMath: [ ['$','$'], ["\\(","\\)"] ],
                    displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
                    processEscapes: true,
                    processEnvironments: true
                },
                displayAlign: 'center',
                CommonHTML: {
                    linebreaks: {
                    automatic: true
                    }
                }
            });

            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
<!-- End of mathjax configuration --><script type="module">
  document.addEventListener("DOMContentLoaded", async () => {
    const diagrams = document.querySelectorAll(".jp-Mermaid > pre.mermaid");
    // do not load mermaidjs if not needed
    if (!diagrams.length) {
      return;
    }
    const mermaid = (await import("https://cdnjs.cloudflare.com/ajax/libs/mermaid/10.6.0/mermaid.esm.min.mjs")).default;
    const parser = new DOMParser();

    mermaid.initialize({
      maxTextSize: 100000,
      startOnLoad: false,
      fontFamily: window
        .getComputedStyle(document.body)
        .getPropertyValue("--jp-ui-font-family"),
      theme: document.querySelector("body[data-jp-theme-light='true']")
        ? "default"
        : "dark",
    });

    let _nextMermaidId = 0;

    function makeMermaidImage(svg) {
      const img = document.createElement("img");
      const doc = parser.parseFromString(svg, "image/svg+xml");
      const svgEl = doc.querySelector("svg");
      const { maxWidth } = svgEl?.style || {};
      const firstTitle = doc.querySelector("title");
      const firstDesc = doc.querySelector("desc");

      img.setAttribute("src", `data:image/svg+xml,${encodeURIComponent(svg)}`);
      if (maxWidth) {
        img.width = parseInt(maxWidth);
      }
      if (firstTitle) {
        img.setAttribute("alt", firstTitle.textContent);
      }
      if (firstDesc) {
        const caption = document.createElement("figcaption");
        caption.className = "sr-only";
        caption.textContent = firstDesc.textContent;
        return [img, caption];
      }
      return [img];
    }

    async function makeMermaidError(text) {
      let errorMessage = "";
      try {
        await mermaid.parse(text);
      } catch (err) {
        errorMessage = `${err}`;
      }

      const result = document.createElement("details");
      result.className = 'jp-RenderedMermaid-Details';
      const summary = document.createElement("summary");
      summary.className = 'jp-RenderedMermaid-Summary';
      const pre = document.createElement("pre");
      const code = document.createElement("code");
      code.innerText = text;
      pre.appendChild(code);
      summary.appendChild(pre);
      result.appendChild(summary);

      const warning = document.createElement("pre");
      warning.innerText = errorMessage;
      result.appendChild(warning);
      return [result];
    }

    async function renderOneMarmaid(src) {
      const id = `jp-mermaid-${_nextMermaidId++}`;
      const parent = src.parentNode;
      let raw = src.textContent.trim();
      const el = document.createElement("div");
      el.style.visibility = "hidden";
      document.body.appendChild(el);
      let results = null;
      let output = null;
      try {
        const { svg } = await mermaid.render(id, raw, el);
        results = makeMermaidImage(svg);
        output = document.createElement("figure");
        results.map(output.appendChild, output);
      } catch (err) {
        parent.classList.add("jp-mod-warning");
        results = await makeMermaidError(raw);
        output = results[0];
      } finally {
        el.remove();
      }
      parent.classList.add("jp-RenderedMermaid");
      parent.appendChild(output);
    }

    void Promise.all([...diagrams].map(renderOneMarmaid));
  });
</script>
<style>
  .jp-Mermaid:not(.jp-RenderedMermaid) {
    display: none;
  }

  .jp-RenderedMermaid {
    overflow: auto;
    display: flex;
  }

  .jp-RenderedMermaid.jp-mod-warning {
    width: auto;
    padding: 0.5em;
    margin-top: 0.5em;
    border: var(--jp-border-width) solid var(--jp-warn-color2);
    border-radius: var(--jp-border-radius);
    color: var(--jp-ui-font-color1);
    font-size: var(--jp-ui-font-size1);
    white-space: pre-wrap;
    word-wrap: break-word;
  }

  .jp-RenderedMermaid figure {
    margin: 0;
    overflow: auto;
    max-width: 100%;
  }

  .jp-RenderedMermaid img {
    max-width: 100%;
  }

  .jp-RenderedMermaid-Details > pre {
    margin-top: 1em;
  }

  .jp-RenderedMermaid-Summary {
    color: var(--jp-warn-color2);
  }

  .jp-RenderedMermaid:not(.jp-mod-warning) pre {
    display: none;
  }

  .jp-RenderedMermaid-Summary > pre {
    display: inline-block;
    white-space: normal;
  }
</style>
<!-- End of mermaid configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">
<main>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=7d045f1d-e924-4315-8bc1-ce818a25c3a7">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Objective :-  Analyze the bird strikes during phase of flight between year 2000 to 2011  and study the some cases.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=9b902188-1676-48d1-aeca-23cb1cb388db">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%3E%3E-Requirements">&gt;&gt; Requirements<a class="anchor-link" href="#%3E%3E-Requirements">¶</a></h1>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=71f5368e-91f5-459a-88c3-c1b6361bd4ce">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Programming language:- python version 3.7.0 or greater</p>
<p>Code Editor/IDE:- Jupyter Notebook</p>
<p>System :- windows 32bit/64bit</p>
<p>software and libraries :- plolty,seaborn,matplotlib,pandas,numpy</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=76c7d67b-a775-4303-b863-c51ca684de03">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [10]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Firstly You Have Install necessary libraries that we will use in this data analysis project</span>
<span class="sd">"""Install Libraries Using pip"""</span>
<span class="c1"># pip install plotly</span>
<span class="c1"># pip install seaborn</span>
<span class="c1"># pip install matplotlib</span>
<span class="c1"># pip install pandas</span>
<span class="c1"># pip install numpy</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[10]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>'Install Libraries Using pip'</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=6a2775b8-936c-4d89-86a7-de13549de973">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Import necessary libraries</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=cfe3c97d-f6ec-4fb6-b08c-c7e4324ae9ce">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [11]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">plotly.express</span> <span class="k">as</span> <span class="nn">px</span> 
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sb</span>
<span class="kn">import</span> <span class="nn">plotly.graph_objects</span> <span class="k">as</span> <span class="nn">go</span>
<span class="kn">from</span> <span class="nn">plotly.subplots</span> <span class="kn">import</span> <span class="n">make_subplots</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=dd99c042-0a7c-489f-8c9a-48f16bed5b72">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%3E%3E-Data-Collection">&gt;&gt; Data Collection<a class="anchor-link" href="#%3E%3E-Data-Collection">¶</a></h1>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=4bd187d3-1762-4fc4-9930-b0aaa4990ca1">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Load The Dataset</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=c67839e5-16ff-4002-8966-990e1bd9a31c">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>We Already have bird_strike_dataset_2000_2011. we will load this dataset directly in our notebook using pandas</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=7acd4a69-9827-43af-b888-b8f06ea00c98">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [12]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Load Amazon Sales DataSet Using pandas</span>
<span class="c1"># Replace with the original path of your dataset</span>
<span class="n">BirdStrike</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s2">"D:</span><span class="se">\\</span><span class="s2">UnifiedMentorInternship\Bird Strikes data.xlsx - Bird Strikes.csv"</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=ddcee187-cfb9-4559-9bd0-5a3a2d2b136a">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [13]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#  Show first 5 values of Dataset</span>
<span class="n">BirdStrike</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">5</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[13]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Record ID</th>
<th>Aircraft: Type</th>
<th>Airport: Name</th>
<th>Altitude bin</th>
<th>Aircraft: Make/Model</th>
<th>Wildlife: Number struck</th>
<th>Wildlife: Number Struck Actual</th>
<th>Effect: Impact to flight</th>
<th>FlightDate</th>
<th>Effect: Indicated Damage</th>
<th>...</th>
<th>Remains of wildlife sent to Smithsonian</th>
<th>Remarks</th>
<th>Wildlife: Size</th>
<th>Conditions: Sky</th>
<th>Wildlife: Species</th>
<th>Pilot warned of birds or wildlife?</th>
<th>Cost: Total $</th>
<th>Feet above ground</th>
<th>Number of people injured</th>
<th>Is Aircraft Large?</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>202152</td>
<td>Airplane</td>
<td>LAGUARDIA NY</td>
<td>&gt; 1000 ft</td>
<td>B-737-400</td>
<td>Over 100</td>
<td>859</td>
<td>Engine Shut Down</td>
<td>11/23/00 0:00</td>
<td>Caused damage</td>
<td>...</td>
<td>False</td>
<td>FLT 753. PILOT REPTD A HUNDRED BIRDS ON UNKN T...</td>
<td>Medium</td>
<td>No Cloud</td>
<td>Unknown bird - medium</td>
<td>N</td>
<td>30,736</td>
<td>1,500</td>
<td>0</td>
<td>Yes</td>
</tr>
<tr>
<th>1</th>
<td>208159</td>
<td>Airplane</td>
<td>DALLAS/FORT WORTH INTL ARPT</td>
<td>&lt; 1000 ft</td>
<td>MD-80</td>
<td>Over 100</td>
<td>424</td>
<td>NaN</td>
<td>7/25/01 0:00</td>
<td>Caused damage</td>
<td>...</td>
<td>False</td>
<td>102 CARCASSES FOUND. 1 LDG LIGHT ON NOSE GEAR ...</td>
<td>Small</td>
<td>Some Cloud</td>
<td>Rock pigeon</td>
<td>Y</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>No</td>
</tr>
<tr>
<th>2</th>
<td>207601</td>
<td>Airplane</td>
<td>LAKEFRONT AIRPORT</td>
<td>&lt; 1000 ft</td>
<td>C-500</td>
<td>Over 100</td>
<td>261</td>
<td>NaN</td>
<td>9/14/01 0:00</td>
<td>No damage</td>
<td>...</td>
<td>False</td>
<td>FLEW UNDER A VERY LARGE FLOCK OF BIRDS OVER AP...</td>
<td>Small</td>
<td>No Cloud</td>
<td>European starling</td>
<td>N</td>
<td>0</td>
<td>50</td>
<td>0</td>
<td>No</td>
</tr>
<tr>
<th>3</th>
<td>215953</td>
<td>Airplane</td>
<td>SEATTLE-TACOMA INTL</td>
<td>&lt; 1000 ft</td>
<td>B-737-400</td>
<td>Over 100</td>
<td>806</td>
<td>Precautionary Landing</td>
<td>9/5/02 0:00</td>
<td>No damage</td>
<td>...</td>
<td>False</td>
<td>NOTAM WARNING. 26 BIRDS HIT THE A/C, FORCING A...</td>
<td>Small</td>
<td>Some Cloud</td>
<td>European starling</td>
<td>Y</td>
<td>0</td>
<td>50</td>
<td>0</td>
<td>Yes</td>
</tr>
<tr>
<th>4</th>
<td>219878</td>
<td>Airplane</td>
<td>NORFOLK INTL</td>
<td>&lt; 1000 ft</td>
<td>CL-RJ100/200</td>
<td>Over 100</td>
<td>942</td>
<td>NaN</td>
<td>6/23/03 0:00</td>
<td>No damage</td>
<td>...</td>
<td>False</td>
<td>NO DMG REPTD.</td>
<td>Small</td>
<td>No Cloud</td>
<td>European starling</td>
<td>N</td>
<td>0</td>
<td>50</td>
<td>0</td>
<td>No</td>
</tr>
</tbody>
</table>
<p>5 rows × 26 columns</p>
</div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=6593cce8-6d15-480d-aad6-65c1afebffb7">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [14]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Show Columns Of DataFrame</span>
<span class="n">BirdStrike</span><span class="o">.</span><span class="n">columns</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[14]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>Index(['Record ID', 'Aircraft: Type', 'Airport: Name', 'Altitude bin',
       'Aircraft: Make/Model', 'Wildlife: Number struck',
       'Wildlife: Number Struck Actual', 'Effect: Impact to flight',
       'FlightDate', 'Effect: Indicated Damage',
       'Aircraft: Number of engines?', 'Aircraft: Airline/Operator',
       'Origin State', 'When: Phase of flight', 'Conditions: Precipitation',
       'Remains of wildlife collected?',
       'Remains of wildlife sent to Smithsonian', 'Remarks', 'Wildlife: Size',
       'Conditions: Sky', 'Wildlife: Species',
       'Pilot warned of birds or wildlife?', 'Cost: Total $',
       'Feet above ground', 'Number of people injured', 'Is Aircraft Large?'],
      dtype='object')</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=ce1099b2-cc82-4d60-83f9-326af1c38081">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [15]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span> <span class="c1"># Check DataType of every column to understand the structure of our DataFrame  </span>
<span class="n">BirdStrike</span><span class="o">.</span><span class="n">info</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>&lt;class 'pandas.core.frame.DataFrame'&gt;
RangeIndex: 25558 entries, 0 to 25557
Data columns (total 26 columns):
 #   Column                                   Non-Null Count  Dtype 
---  ------                                   --------------  ----- 
 0   Record ID                                25558 non-null  int64 
 1   Aircraft: Type                           25429 non-null  object
 2   Airport: Name                            25429 non-null  object
 3   Altitude bin                             25429 non-null  object
 4   Aircraft: Make/Model                     25558 non-null  object
 5   Wildlife: Number struck                  25429 non-null  object
 6   Wildlife: Number Struck Actual           25558 non-null  int64 
 7   Effect: Impact to flight                 2078 non-null   object
 8   FlightDate                               25429 non-null  object
 9   Effect: Indicated Damage                 25558 non-null  object
 10  Aircraft: Number of engines?             25291 non-null  object
 11  Aircraft: Airline/Operator               25429 non-null  object
 12  Origin State                             25109 non-null  object
 13  When: Phase of flight                    25429 non-null  object
 14  Conditions: Precipitation                2015 non-null   object
 15  Remains of wildlife collected?           25558 non-null  bool  
 16  Remains of wildlife sent to Smithsonian  25558 non-null  bool  
 17  Remarks                                  20787 non-null  object
 18  Wildlife: Size                           25429 non-null  object
 19  Conditions: Sky                          25558 non-null  object
 20  Wildlife: Species                        25558 non-null  object
 21  Pilot warned of birds or wildlife?       25429 non-null  object
 22  Cost: Total $                            25558 non-null  object
 23  Feet above ground                        25429 non-null  object
 24  Number of people injured                 25558 non-null  int64 
 25  Is Aircraft Large?                       25429 non-null  object
dtypes: bool(2), int64(3), object(21)
memory usage: 4.7+ MB
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=426a51e2-92f6-4053-93af-41b3db80b8e6">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [16]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span> <span class="c1"># Take A look on dataFrame  numerical columns to understand basics Summery like count,mean,min,max  of each column etc.</span>
<span class="n">BirdStrike</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[16]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Record ID</th>
<th>Wildlife: Number Struck Actual</th>
<th>Number of people injured</th>
</tr>
</thead>
<tbody>
<tr>
<th>count</th>
<td>25558.000000</td>
<td>25558.000000</td>
<td>25558.000000</td>
</tr>
<tr>
<th>mean</th>
<td>253916.085609</td>
<td>2.691525</td>
<td>0.001056</td>
</tr>
<tr>
<th>std</th>
<td>38510.453382</td>
<td>12.793975</td>
<td>0.050420</td>
</tr>
<tr>
<th>min</th>
<td>1195.000000</td>
<td>1.000000</td>
<td>0.000000</td>
</tr>
<tr>
<th>25%</th>
<td>225783.750000</td>
<td>1.000000</td>
<td>0.000000</td>
</tr>
<tr>
<th>50%</th>
<td>248749.000000</td>
<td>1.000000</td>
<td>0.000000</td>
</tr>
<tr>
<th>75%</th>
<td>269168.750000</td>
<td>1.000000</td>
<td>0.000000</td>
</tr>
<tr>
<th>max</th>
<td>321909.000000</td>
<td>942.000000</td>
<td>6.000000</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=1f0211a5-a5b5-4d7b-a16b-edc484690747">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%3E%3E-Data-Preprocessing">&gt;&gt; Data Preprocessing<a class="anchor-link" href="#%3E%3E-Data-Preprocessing">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=0f8948c7-da49-4f46-b389-abc36104c633">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [17]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span> <span class="c1"># Check nan Values</span>
 <span class="nb">print</span><span class="p">(</span><span class="s2">"nan values In All Coulmn:-"</span><span class="p">,</span><span class="n">BirdStrike</span><span class="o">.</span><span class="n">isna</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">())</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>nan values In All Coulmn:- Record ID                                      0
Aircraft: Type                               129
Airport: Name                                129
Altitude bin                                 129
Aircraft: Make/Model                           0
Wildlife: Number struck                      129
Wildlife: Number Struck Actual                 0
Effect: Impact to flight                   23480
FlightDate                                   129
Effect: Indicated Damage                       0
Aircraft: Number of engines?                 267
Aircraft: Airline/Operator                   129
Origin State                                 449
When: Phase of flight                        129
Conditions: Precipitation                  23543
Remains of wildlife collected?                 0
Remains of wildlife sent to Smithsonian        0
Remarks                                     4771
Wildlife: Size                               129
Conditions: Sky                                0
Wildlife: Species                              0
Pilot warned of birds or wildlife?           129
Cost: Total $                                  0
Feet above ground                            129
Number of people injured                       0
Is Aircraft Large?                           129
dtype: int64
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=8d0456fb-7e45-48d2-86bf-ee16f315bd5b">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>In Above Dataset We can Clearly see that 4 columns (Effect: Impact to flight,Conditions: Precipitation,Remarks,Origin State) contain too much nan values so for now we will excludes this columns and process other data.In Above some columns also have total 129 nan in same row comapre to other some columns we will drop that row.</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=2f0a8f58-20cc-4891-a0db-15b755df7a93">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [18]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Assign All Dataset To New variable</span>
<span class="n">BirdStrikeOrg</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=c6dc7305-1f49-45bf-a188-75b247c8c852">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [19]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Drop 4 Columns because they have alot of nan values that can impact on our analysis</span>
<span class="n">BirdStrike</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">'Remarks'</span><span class="p">,</span><span class="s1">'Effect: Impact to flight'</span><span class="p">,</span><span class="s1">'Conditions: Precipitation'</span><span class="p">],</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=ff2e72d5-83fa-41eb-bc95-5bafe9fbb5b5">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [20]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">]</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[20]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>0        1,500
1            0
2           50
3           50
4           50
         ...  
25553    1,500
25554        0
25555      NaN
25556        0
25557        0
Name: Feet above ground, Length: 25558, dtype: object</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=3ecc0317-ff4e-44ee-b412-86da3350ae93">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [21]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Print the dataset after droping columns</span>
<span class="n">BirdStrike</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">5</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[21]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Record ID</th>
<th>Aircraft: Type</th>
<th>Airport: Name</th>
<th>Altitude bin</th>
<th>Aircraft: Make/Model</th>
<th>Wildlife: Number struck</th>
<th>Wildlife: Number Struck Actual</th>
<th>FlightDate</th>
<th>Effect: Indicated Damage</th>
<th>Aircraft: Number of engines?</th>
<th>...</th>
<th>Remains of wildlife collected?</th>
<th>Remains of wildlife sent to Smithsonian</th>
<th>Wildlife: Size</th>
<th>Conditions: Sky</th>
<th>Wildlife: Species</th>
<th>Pilot warned of birds or wildlife?</th>
<th>Cost: Total $</th>
<th>Feet above ground</th>
<th>Number of people injured</th>
<th>Is Aircraft Large?</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>202152</td>
<td>Airplane</td>
<td>LAGUARDIA NY</td>
<td>&gt; 1000 ft</td>
<td>B-737-400</td>
<td>Over 100</td>
<td>859</td>
<td>11/23/00 0:00</td>
<td>Caused damage</td>
<td>2</td>
<td>...</td>
<td>False</td>
<td>False</td>
<td>Medium</td>
<td>No Cloud</td>
<td>Unknown bird - medium</td>
<td>N</td>
<td>30,736</td>
<td>1,500</td>
<td>0</td>
<td>Yes</td>
</tr>
<tr>
<th>1</th>
<td>208159</td>
<td>Airplane</td>
<td>DALLAS/FORT WORTH INTL ARPT</td>
<td>&lt; 1000 ft</td>
<td>MD-80</td>
<td>Over 100</td>
<td>424</td>
<td>7/25/01 0:00</td>
<td>Caused damage</td>
<td>2</td>
<td>...</td>
<td>False</td>
<td>False</td>
<td>Small</td>
<td>Some Cloud</td>
<td>Rock pigeon</td>
<td>Y</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>No</td>
</tr>
<tr>
<th>2</th>
<td>207601</td>
<td>Airplane</td>
<td>LAKEFRONT AIRPORT</td>
<td>&lt; 1000 ft</td>
<td>C-500</td>
<td>Over 100</td>
<td>261</td>
<td>9/14/01 0:00</td>
<td>No damage</td>
<td>2</td>
<td>...</td>
<td>False</td>
<td>False</td>
<td>Small</td>
<td>No Cloud</td>
<td>European starling</td>
<td>N</td>
<td>0</td>
<td>50</td>
<td>0</td>
<td>No</td>
</tr>
<tr>
<th>3</th>
<td>215953</td>
<td>Airplane</td>
<td>SEATTLE-TACOMA INTL</td>
<td>&lt; 1000 ft</td>
<td>B-737-400</td>
<td>Over 100</td>
<td>806</td>
<td>9/5/02 0:00</td>
<td>No damage</td>
<td>2</td>
<td>...</td>
<td>True</td>
<td>False</td>
<td>Small</td>
<td>Some Cloud</td>
<td>European starling</td>
<td>Y</td>
<td>0</td>
<td>50</td>
<td>0</td>
<td>Yes</td>
</tr>
<tr>
<th>4</th>
<td>219878</td>
<td>Airplane</td>
<td>NORFOLK INTL</td>
<td>&lt; 1000 ft</td>
<td>CL-RJ100/200</td>
<td>Over 100</td>
<td>942</td>
<td>6/23/03 0:00</td>
<td>No damage</td>
<td>2</td>
<td>...</td>
<td>False</td>
<td>False</td>
<td>Small</td>
<td>No Cloud</td>
<td>European starling</td>
<td>N</td>
<td>0</td>
<td>50</td>
<td>0</td>
<td>No</td>
</tr>
</tbody>
</table>
<p>5 rows × 23 columns</p>
</div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=d4f1eedb-c501-44f1-aeda-db2f57a41357">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [22]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># drop nan from all columns</span>
<span class="n">BirdStrike</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=9e30e4bf-6db3-4c24-bf3c-ab4570913d14">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [23]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Check For Nan Values</span>
<span class="n">BirdStrike</span><span class="o">.</span><span class="n">isna</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>

<span class="c1"># Check  Now we Have drop All row contains nan</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[23]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>Record ID                                  0
Aircraft: Type                             0
Airport: Name                              0
Altitude bin                               0
Aircraft: Make/Model                       0
Wildlife: Number struck                    0
Wildlife: Number Struck Actual             0
FlightDate                                 0
Effect: Indicated Damage                   0
Aircraft: Number of engines?               0
Aircraft: Airline/Operator                 0
Origin State                               0
When: Phase of flight                      0
Remains of wildlife collected?             0
Remains of wildlife sent to Smithsonian    0
Wildlife: Size                             0
Conditions: Sky                            0
Wildlife: Species                          0
Pilot warned of birds or wildlife?         0
Cost: Total $                              0
Feet above ground                          0
Number of people injured                   0
Is Aircraft Large?                         0
dtype: int64</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=9b0e6ce6-ffb0-4db7-b943-53fe976384b2">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [24]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span> <span class="c1"># Check null Values</span>
 <span class="nb">print</span><span class="p">(</span><span class="s2">"Null values In All Coulmns:-"</span><span class="p">,</span><span class="n">BirdStrike</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">())</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Null values In All Coulmns:- Record ID                                  0
Aircraft: Type                             0
Airport: Name                              0
Altitude bin                               0
Aircraft: Make/Model                       0
Wildlife: Number struck                    0
Wildlife: Number Struck Actual             0
FlightDate                                 0
Effect: Indicated Damage                   0
Aircraft: Number of engines?               0
Aircraft: Airline/Operator                 0
Origin State                               0
When: Phase of flight                      0
Remains of wildlife collected?             0
Remains of wildlife sent to Smithsonian    0
Wildlife: Size                             0
Conditions: Sky                            0
Wildlife: Species                          0
Pilot warned of birds or wildlife?         0
Cost: Total $                              0
Feet above ground                          0
Number of people injured                   0
Is Aircraft Large?                         0
dtype: int64
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=43917065-a9d5-4eb9-9267-4a91a761c661">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [25]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Add new columns year and month from column FlightDate</span>

<span class="c1"># Convert  FlightDate column to datetime </span>

<span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'FlightDate'</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'FlightDate'</span><span class="p">])</span>
<span class="c1"># Now We will Create Three New Columns of Year, Month and yearMonth</span>
<span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'year'</span><span class="p">]</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'FlightDate'</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">year</span>
<span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'month'</span><span class="p">]</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'FlightDate'</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">month</span>
<span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'year_month'</span><span class="p">]</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'FlightDate'</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">to_period</span><span class="p">(</span><span class="s1">'M'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr" tabindex="0">
<pre>C:\Users\mishr\AppData\Local\Temp\ipykernel_25804\275944927.py:5: UserWarning: Could not infer format, so each element will be parsed individually, falling back to `dateutil`. To ensure parsing is consistent and as-expected, please specify a format.
  BirdStrike['FlightDate'] = pd.to_datetime(BirdStrike['FlightDate'])
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=3dec6d6d-d2ff-4ccc-aaaa-568cc149cc02">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Note:- In the above cell avoid the warning.</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=b7e9b0a4-65b2-4e40-9afb-2597f1a1d02a">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [26]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">"Toatl Columns:- "</span><span class="p">,</span><span class="nb">len</span><span class="p">(</span><span class="n">BirdStrike</span><span class="o">.</span><span class="n">columns</span><span class="p">))</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Toatl Columns:-  26
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=fedb2754-7c23-48b0-9980-bfd543e313b7">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [27]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Convert month number to month name</span>

<span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'month'</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'month'</span><span class="p">],</span> <span class="nb">format</span><span class="o">=</span><span class="s1">'%m'</span><span class="p">)</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">month_name</span><span class="p">()</span><span class="o">.</span><span class="n">str</span><span class="p">[:</span><span class="mi">3</span><span class="p">]</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=eee354da-68cd-401e-ab05-8d21cbb798f2">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [28]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Change Object data type to String </span>
<span class="n">BirdStrikeOrg</span><span class="p">[</span><span class="s1">'Aircraft: Airline/Operator'</span><span class="p">]</span> <span class="o">=</span> <span class="n">BirdStrikeOrg</span><span class="p">[</span><span class="s1">'Aircraft: Airline/Operator'</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">str</span><span class="p">)</span>

<span class="c1"># Change object to float</span>
<span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Cost: Total $'</span><span class="p">]</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Cost: Total $'</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">str</span><span class="p">)</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s2">","</span><span class="p">,</span><span class="s2">""</span><span class="p">)</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>

<span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">]</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">str</span><span class="p">)</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s2">","</span><span class="p">,</span><span class="s2">""</span><span class="p">)</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=24c4f03b-10d7-48cd-bc74-d116ca37181e">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%3E%3EData-Analysis-and-visualization">&gt;&gt;Data Analysis and visualization<a class="anchor-link" href="#%3E%3EData-Analysis-and-visualization">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=04590a0d-eb96-43b7-8ede-6320d475a009">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [101]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Count the frequency of each month</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"Average bird strikes in US in each month over all the years :- "</span><span class="p">,</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'month'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">mean</span><span class="p">())</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Average bird strikes in US in each month over all the years :-  2062.25
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=39d27996-f24a-48b5-9f5a-4ecf8b6a7719">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F-Month-vise-birdstrikes-in-US-flight">● Month-vise birdstrikes in US flight<a class="anchor-link" href="#%E2%97%8F-Month-vise-birdstrikes-in-US-flight">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=111f24ef-bf8e-4783-9756-3005f63d485b">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [102]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#  value_counts() function will count the each month frequncy and month_vise will store data in dict. type</span>

<span class="n">month_vise</span> <span class="o">=</span> <span class="p">{</span><span class="s1">'month'</span><span class="p">:</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'month'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">keys</span><span class="p">(),</span><span class="s1">'BirdStrikes'</span><span class="p">:</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'month'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">values</span><span class="p">}</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=62a2de9a-887a-459e-8c3e-99e31de9245b">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [103]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># set color to all markers</span>
<span class="n">colors</span> <span class="o">=</span> <span class="p">[</span><span class="s1">'#FFBF78'</span><span class="p">,]</span> <span class="o">*</span> <span class="mi">12</span>

<span class="c1"># set Colors To loweset markers</span>
<span class="n">colors</span><span class="p">[</span><span class="mi">8</span><span class="p">:]</span> <span class="o">=</span> <span class="p">[</span><span class="s1">'#3ABEF9'</span><span class="p">]</span><span class="o">*</span><span class="mi">4</span>

<span class="c1"># create bar chart</span>

<span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">month_vise</span><span class="p">,</span><span class="n">x</span><span class="o">=</span> <span class="s1">'month'</span><span class="p">,</span><span class="n">y</span><span class="o">=</span> <span class="s1">'BirdStrikes'</span><span class="p">,</span><span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span> <span class="n">text</span> <span class="o">=</span> <span class="s1">'BirdStrikes'</span><span class="p">,</span><span class="n">title</span><span class="o">=</span><span class="s1">'BirdStrikes in US flights in each month over years'</span><span class="p">)</span>

<span class="c1"># update text</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_traces</span><span class="p">(</span><span class="n">textfont_size</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span> <span class="n">textangle</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">textposition</span><span class="o">=</span><span class="s2">"outside"</span><span class="p">,</span> <span class="n">cliponaxis</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span><span class="n">textfont</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'red'</span><span class="p">),</span><span class="n">marker_color</span><span class="o">=</span><span class="n">colors</span><span class="p">)</span>
<span class="c1"># update layout</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span><span class="n">paper_bgcolor</span> <span class="o">=</span> <span class="s1">'#dff2fa'</span><span class="p">,</span><span class="n">plot_bgcolor</span><span class="o">=</span><span class="s1">'rgba(100, 100, 50, 0)'</span><span class="p">,</span><span class="n">title_font_color</span><span class="o">=</span><span class="s2">"red"</span><span class="p">)</span>


<span class="c1"># show Chart</span>
<span class="n">fig</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output" data-mime-type="text/html" tabindex="0">
<div> <div class="plotly-graph-div" id="e126a23d-4c7a-4891-bb2a-398c03a6e6f5" style="height:500px; width:100%;"></div> <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("e126a23d-4c7a-4891-bb2a-398c03a6e6f5")) {                    Plotly.newPlot(                        "e126a23d-4c7a-4891-bb2a-398c03a6e6f5",                        [{"alignmentgroup":"True","hovertemplate":"month=%{x}<br>BirdStrikes=%{text}<extra></extra>","legendgroup":"","marker":{"color":["#FFBF78","#FFBF78","#FFBF78","#FFBF78","#FFBF78","#FFBF78","#FFBF78","#FFBF78","#3ABEF9","#3ABEF9","#3ABEF9","#3ABEF9"],"pattern":{"shape":""}},"name":"","offsetgroup":"","orientation":"v","showlegend":false,"text":[3631.0,3357.0,3167.0,2964.0,2268.0,1999.0,1764.0,1751.0,1190.0,992.0,915.0,749.0],"textposition":"outside","x":["Aug","Sep","Jul","Oct","May","Jun","Apr","Nov","Mar","Dec","Jan","Feb"],"xaxis":"x","y":[3631,3357,3167,2964,2268,1999,1764,1751,1190,992,915,749],"yaxis":"y","type":"bar","textfont":{"color":"red","size":12},"cliponaxis":false,"textangle":0}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"month"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"BirdStrikes"}},"legend":{"tracegroupgap":0},"title":{"text":"BirdStrikes in US flights in each month over years","font":{"color":"red"}},"barmode":"relative","height":500,"paper_bgcolor":"#dff2fa","plot_bgcolor":"rgba(100, 100, 50, 0)"},                        {"responsive": true}                    ).then(function(){
                            
var gd = document.getElementById('e126a23d-4c7a-4891-bb2a-398c03a6e6f5');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script> </div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=e37546f0-6963-4fb7-9c5f-d91976e32ac8">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>KeyInsights :-  these months(Nov,dec,january,februery,march,april)  contain  less cases of birdstrikes.mostly bird strikes occur during the  month (may,june,july,august,septempber,october) there is a seasonal changes in birdstrikes.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=bf91dfda-8235-44fc-9d38-e4b686ea3ae4">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F-Year-Wise-BirdStrikes-in-US">● Year-Wise BirdStrikes in US<a class="anchor-link" href="#%E2%97%8F-Year-Wise-BirdStrikes-in-US">¶</a></h1>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=bd73a782-dd97-4500-8512-971c6f1f16b3">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Count The frequency year to understand number of birdStrikes on that each year</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=c7d298c2-0dd9-45fd-9b00-87282a1e47fa">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [32]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># This Function Will update the color according threshold.</span>

<span class="c1"># Function will take two parameters value and threshold</span>
<span class="k">def</span> <span class="nf">ChangeColors</span><span class="p">(</span><span class="n">values</span><span class="p">:</span><span class="nb">list</span><span class="p">,</span><span class="n">threshold</span><span class="p">):</span>
    
    <span class="c1"># strike=0</span>
    
    <span class="c1"># index=0</span>
    
    <span class="n">colors</span> <span class="o">=</span> <span class="p">[]</span>
    
    <span class="n">check_std</span> <span class="o">=</span> <span class="p">[]</span>

    <span class="n">mean</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">values</span><span class="p">)</span>

    <span class="n">index</span><span class="o">=</span><span class="mi">0</span>
    
    <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="p">(</span><span class="n">values</span><span class="p">):</span>
    

        
        <span class="k">if</span><span class="p">((</span><span class="n">mean</span><span class="o">-</span><span class="n">i</span><span class="p">)</span> <span class="o">&gt;</span><span class="n">threshold</span><span class="p">):</span>

            <span class="n">colors</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s1">'#30E3DF'</span><span class="p">)</span>
            
             
        <span class="k">elif</span><span class="p">((</span><span class="n">mean</span><span class="o">-</span><span class="n">i</span><span class="p">)</span> <span class="o">&lt;-</span><span class="n">threshold</span><span class="p">):</span>
            
            
                   <span class="n">colors</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s1">'#FF6969'</span><span class="p">)</span>
            
        <span class="k">else</span> <span class="p">:</span>
            
             <span class="n">colors</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s1">'#F6EEC9'</span><span class="p">)</span>


        <span class="n">index</span><span class="o">+=</span><span class="mi">1</span>

    <span class="k">return</span> <span class="n">colors</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=f8645011-53e6-4561-afc2-76ce566922d2">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [104]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Count the frequency of each year</span>

<span class="nb">print</span><span class="p">(</span><span class="s2">"Average bird Strikes in US between year 2000-2011:- "</span><span class="p">,</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'year'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">mean</span><span class="p">())</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Average bird Strikes in US between year 2000-2011:-  2062.25
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=f1b6074f-f19b-4a4d-abb7-3e20dafa4d60">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [82]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#  value_counts() function will count the each year  frequncy </span>
<span class="n">Year_dict</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'year'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">to_dict</span><span class="p">()</span>
<span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="nb">list</span><span class="p">(</span><span class="n">Year_dict</span><span class="o">.</span><span class="n">values</span><span class="p">()))</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[82]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>2062.25</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=34b2398c-f3f9-4a8c-9a49-1bc6595e0c6d">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [35]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># use Year_dict keys and values in dict. year_wise</span>
<span class="n">year_wise</span> <span class="o">=</span> <span class="p">{</span><span class="s1">'year'</span><span class="p">:</span><span class="n">Year_dict</span><span class="o">.</span><span class="n">keys</span><span class="p">(),</span><span class="s1">'BirdStrikes'</span><span class="p">:</span><span class="n">Year_dict</span><span class="o">.</span><span class="n">values</span><span class="p">()}</span>

<span class="c1"># Chnge The color of marker on threshold </span>
<span class="n">colors</span> <span class="o">=</span> <span class="n">ChangeColors</span><span class="p">(</span><span class="nb">list</span><span class="p">(</span><span class="n">Year_dict</span><span class="o">.</span><span class="n">values</span><span class="p">()),</span><span class="mi">1000</span><span class="p">)</span>

<span class="c1"># Create bar chart</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">year_wise</span><span class="p">,</span><span class="n">x</span><span class="o">=</span><span class="s1">'year'</span><span class="p">,</span><span class="n">y</span><span class="o">=</span><span class="s1">'BirdStrikes'</span><span class="p">,</span><span class="n">height</span> <span class="o">=</span> <span class="mi">500</span><span class="p">,</span><span class="n">title</span> <span class="o">=</span> <span class="s1">'BirdStrikes in US flights over the all years'</span><span class="p">,</span><span class="n">text</span><span class="o">=</span><span class="s1">'BirdStrikes'</span><span class="p">)</span>

<span class="c1"># Update text</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_traces</span><span class="p">(</span><span class="n">textfont_size</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span> <span class="n">textangle</span> <span class="o">=</span> <span class="mi">0</span><span class="p">,</span> <span class="n">textposition</span><span class="o">=</span><span class="s1">'outside'</span><span class="p">,</span><span class="n">cliponaxis</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span><span class="n">textfont</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'white'</span><span class="p">),</span><span class="n">marker_color</span><span class="o">=</span><span class="n">colors</span><span class="p">)</span>

<span class="c1"># Update layout</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span><span class="n">paper_bgcolor</span> <span class="o">=</span> <span class="s1">'rgba(200, 0, 100, 222)'</span><span class="p">,</span><span class="n">title_font_color</span><span class="o">=</span><span class="s2">"#F9F5F6"</span><span class="p">,</span><span class="n">plot_bgcolor</span> <span class="o">=</span> <span class="s1">'rgba(0, 0, 100, 222)'</span><span class="p">,</span><span class="n">legend_title_font_color</span><span class="o">=</span><span class="s1">'rgba(200, 200, 50, 222)'</span><span class="p">,</span><span class="n">font_color</span><span class="o">=</span><span class="s1">'#FFE194'</span><span class="p">,</span><span class="n">hoverlabel_grouptitlefont_color</span><span class="o">=</span><span class="s1">'#5755FE'</span>
                  <span class="p">,</span><span class="n">font_size</span><span class="o">=</span><span class="mi">13</span><span class="p">)</span>
<span class="c1"># Show Chart</span>
<span class="n">fig</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output" data-mime-type="text/html" tabindex="0">
<div> <div class="plotly-graph-div" id="e4ef5100-8edd-402e-96fe-6188e051f905" style="height:500px; width:100%;"></div> <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("e4ef5100-8edd-402e-96fe-6188e051f905")) {                    Plotly.newPlot(                        "e4ef5100-8edd-402e-96fe-6188e051f905",                        [{"alignmentgroup":"True","hovertemplate":"year=%{x}<br>BirdStrikes=%{text}<extra></extra>","legendgroup":"","marker":{"color":["#FF6969","#F6EEC9","#F6EEC9","#F6EEC9","#F6EEC9","#F6EEC9","#F6EEC9","#F6EEC9","#F6EEC9","#F6EEC9","#F6EEC9","#F6EEC9"],"pattern":{"shape":""}},"name":"","offsetgroup":"","orientation":"v","showlegend":false,"text":[3152.0,3026.0,2860.0,2249.0,2207.0,2111.0,1815.0,1671.0,1619.0,1541.0,1321.0,1175.0],"textposition":"outside","x":[2009,2010,2011,2007,2008,2006,2005,2004,2002,2003,2000,2001],"xaxis":"x","y":[3152,3026,2860,2249,2207,2111,1815,1671,1619,1541,1321,1175],"yaxis":"y","type":"bar","textfont":{"color":"white","size":12},"cliponaxis":false,"textangle":0}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"year"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"BirdStrikes"}},"legend":{"tracegroupgap":0,"title":{"font":{"color":"rgba(200, 200, 50, 222)"}}},"title":{"text":"BirdStrikes in US flights over the all years","font":{"color":"#F9F5F6"}},"barmode":"relative","height":500,"font":{"color":"#FFE194","size":13},"hoverlabel":{"grouptitlefont":{"color":"#5755FE"}},"paper_bgcolor":"rgba(200, 0, 100, 222)","plot_bgcolor":"rgba(0, 0, 100, 222)"},                        {"responsive": true}                    ).then(function(){
                            
var gd = document.getElementById('e4ef5100-8edd-402e-96fe-6188e051f905');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script> </div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=208de5a4-c1bb-42c3-b7f5-d5a1012cfd18">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>KeyInsights :-  In above chart we can see that between year 2000-2008 little bit differences on numbers of birdstrikes but after year 2008 in 2009(red marker) there around 1000 bird strikes increased that usually we have not seen in past years.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=dc2407b6-ba54-4309-9b2a-82cb18adeaaa">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F-Top-10-US-Airlines-in-terms-of-having-encountered-bird-strikes">● Top 10 US Airlines in terms of having encountered bird strikes<a class="anchor-link" href="#%E2%97%8F-Top-10-US-Airlines-in-terms-of-having-encountered-bird-strikes">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=8e938e62-90d6-4674-bb69-a85e2a60f272">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [36]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">"Top 10 US airlines in terms of having encountered bird strikes:-"</span><span class="p">)</span>
<span class="n">Top10US</span> <span class="o">=</span> <span class="n">BirdStrikeOrg</span><span class="p">[</span><span class="s1">'Aircraft: Airline/Operator'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>

<span class="n">Top10US</span><span class="p">[:</span><span class="mi">10</span><span class="p">]</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Top 10 US airlines in terms of having encountered bird strikes:-
</pre>
</div>
</div>
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[36]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>Aircraft: Airline/Operator
SOUTHWEST AIRLINES         4628
BUSINESS                   3074
AMERICAN AIRLINES          2058
DELTA AIR LINES            1349
AMERICAN EAGLE AIRLINES     932
SKYWEST AIRLINES            891
US AIRWAYS*                 797
JETBLUE AIRWAYS             708
UPS AIRLINES                590
US AIRWAYS                  540
Name: count, dtype: int64</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=8768bcc7-2af4-4abc-a7bd-e3b10942af45">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [37]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">Top10US</span> <span class="o">=</span> <span class="n">Top10US</span><span class="p">[:</span><span class="mi">10</span><span class="p">]</span><span class="o">.</span><span class="n">to_dict</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=4b0f2ad1-f44b-4df3-b5ca-ecadc68b08bf">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [2]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># use Year_dict keys and values in dict. Top10US</span>
<span class="n">Top10US</span> <span class="o">=</span><span class="p">{</span><span class="s1">'airline'</span><span class="p">:</span><span class="nb">list</span><span class="p">(</span><span class="n">Top10US</span><span class="o">.</span><span class="n">keys</span><span class="p">()),</span><span class="s1">'BirdStrikes'</span><span class="p">:</span><span class="nb">list</span><span class="p">(</span><span class="n">Top10US</span><span class="o">.</span><span class="n">values</span><span class="p">())}</span>

<span class="c1"># Create bar chart with Plotly Express</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">Top10US</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">'airline'</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">'BirdStrikes'</span><span class="p">,</span> <span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span> <span class="n">title</span><span class="o">=</span><span class="s1">'Top 10 US airlines in terms of having encountered bird strikes'</span><span class="p">,</span> <span class="n">text</span><span class="o">=</span><span class="s1">'BirdStrikes'</span><span class="p">)</span>

<span class="c1"># URL of a image</span>
<span class="n">image_url</span> <span class="o">=</span> <span class="s1">'https://upload.wikimedia.org/wikipedia/commons/thumb/9/91/N24976%40PEK_</span><span class="si">%2820200421150836%</span><span class="s1">29.jpg/1200px-N24976%40PEK_</span><span class="si">%2820200421150836%</span><span class="s1">29.jpg'</span>


<span class="c1"># set color to all markers</span>
<span class="n">colors</span> <span class="o">=</span> <span class="p">[</span><span class="s1">'#B3E2A7'</span><span class="p">]</span> <span class="o">*</span> <span class="nb">len</span><span class="p">(</span><span class="n">Top10US</span><span class="p">[</span><span class="s1">'airline'</span><span class="p">])</span>


<span class="c1"># Add image as background</span>
<span class="n">fig</span><span class="o">.</span><span class="n">add_layout_image</span><span class="p">(</span>
    <span class="nb">dict</span><span class="p">(</span>
        <span class="n">source</span><span class="o">=</span><span class="n">image_url</span><span class="p">,</span>
        <span class="n">xref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">yref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">x</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
        <span class="n">y</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizex</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>  <span class="c1"># Adjust width</span>
        <span class="n">sizey</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span>  <span class="c1"># Adjust height</span>
        <span class="n">sizing</span><span class="o">=</span><span class="s2">"stretch"</span><span class="p">,</span>
        <span class="n">opacity</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span>
        <span class="n">layer</span><span class="o">=</span><span class="s2">"below"</span>
    <span class="p">)</span>
<span class="p">)</span>

<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span><span class="n">paper_bgcolor</span> <span class="o">=</span> <span class="s1">'#5C88C4'</span><span class="p">,</span><span class="n">title_font_color</span><span class="o">=</span><span class="s2">"#F9F5F6"</span><span class="p">,</span><span class="n">plot_bgcolor</span> <span class="o">=</span> <span class="s1">'rgba(0, 0, 100, 100)'</span><span class="p">,</span><span class="n">legend_title_font_color</span><span class="o">=</span><span class="s1">'rgba(200, 200, 50, 222)'</span><span class="p">,</span><span class="n">font_color</span><span class="o">=</span><span class="s1">'#C3FF93'</span><span class="p">,</span><span class="n">hoverlabel_grouptitlefont_color</span><span class="o">=</span><span class="s1">'#FF8F00'</span>
                  <span class="p">,</span><span class="n">font_size</span><span class="o">=</span><span class="mi">13</span><span class="p">)</span>



<span class="c1"># Update layout to ensure the image covers the full background</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span>
    <span class="n">template</span><span class="o">=</span><span class="s2">"plotly_white"</span><span class="p">,</span>
    <span class="n">images</span><span class="o">=</span><span class="p">[</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">source</span><span class="o">=</span><span class="n">image_url</span><span class="p">,</span>
        <span class="n">xref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">yref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">x</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
        <span class="n">y</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizex</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizey</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span>
        <span class="n">sizing</span><span class="o">=</span><span class="s2">"stretch"</span><span class="p">,</span>
        <span class="n">opacity</span><span class="o">=</span><span class="mf">0.4</span><span class="p">,</span>
        <span class="n">layer</span><span class="o">=</span><span class="s2">"below"</span>
    <span class="p">)],</span>
    <span class="n">margin</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">l</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">r</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">t</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">b</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>  <span class="p">)</span>

<span class="c1"># Update text</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_traces</span><span class="p">(</span><span class="n">textfont_size</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span> <span class="n">textangle</span> <span class="o">=</span> <span class="mi">0</span><span class="p">,</span> <span class="n">textposition</span><span class="o">=</span><span class="s1">'outside'</span><span class="p">,</span><span class="n">cliponaxis</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span><span class="n">textfont</span><span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'white'</span><span class="p">),</span><span class="n">marker_color</span><span class="o">=</span><span class="n">colors</span><span class="p">)</span>

<span class="c1"># Show chart</span>

<span class="n">fig</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr" tabindex="0">
<pre>
<span class="ansi-red-intense-fg ansi-bold">---------------------------------------------------------------------------</span>
<span class="ansi-red-intense-fg ansi-bold">NameError</span>                                 Traceback (most recent call last)
Cell <span class="ansi-green-intense-fg ansi-bold">In[2], line 2</span>
<span class="ansi-green-fg">      1</span> <span style="color: rgb(95,135,135)"># use Year_dict keys and values in dict. Top10US</span>
<span class="ansi-green-intense-fg ansi-bold">----&gt; 2</span> Top10US <span style="color: rgb(98,98,98)">=</span>{<span style="color: rgb(175,0,0)">'</span><span style="color: rgb(175,0,0)">airline</span><span style="color: rgb(175,0,0)">'</span>:<span style="color: rgb(0,135,0)">list</span>(Top10US<span style="color: rgb(98,98,98)">.</span>keys()),<span style="color: rgb(175,0,0)">'</span><span style="color: rgb(175,0,0)">BirdStrikes</span><span style="color: rgb(175,0,0)">'</span>:<span style="color: rgb(0,135,0)">list</span>(Top10US<span style="color: rgb(98,98,98)">.</span>values())}
<span class="ansi-green-fg">      4</span> <span style="color: rgb(95,135,135)"># Create bar chart with Plotly Express</span>
<span class="ansi-green-fg">      5</span> fig <span style="color: rgb(98,98,98)">=</span> px<span style="color: rgb(98,98,98)">.</span>bar(Top10US, x<span style="color: rgb(98,98,98)">=</span><span style="color: rgb(175,0,0)">'</span><span style="color: rgb(175,0,0)">airline</span><span style="color: rgb(175,0,0)">'</span>, y<span style="color: rgb(98,98,98)">=</span><span style="color: rgb(175,0,0)">'</span><span style="color: rgb(175,0,0)">BirdStrikes</span><span style="color: rgb(175,0,0)">'</span>, height<span style="color: rgb(98,98,98)">=</span><span style="color: rgb(98,98,98)">500</span>, title<span style="color: rgb(98,98,98)">=</span><span style="color: rgb(175,0,0)">'</span><span style="color: rgb(175,0,0)">Top 10 US airlines in terms of having encountered bird strikes</span><span style="color: rgb(175,0,0)">'</span>, text<span style="color: rgb(98,98,98)">=</span><span style="color: rgb(175,0,0)">'</span><span style="color: rgb(175,0,0)">BirdStrikes</span><span style="color: rgb(175,0,0)">'</span>)

<span class="ansi-red-intense-fg ansi-bold">NameError</span>: name 'Top10US' is not defined</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=b1c47986-a966-4da5-8c2a-00ca104fd6ec">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F--Top-50-Airports-with-most-incidents-of-bird-strikes">●  Top 50 Airports with most incidents of bird strikes<a class="anchor-link" href="#%E2%97%8F--Top-50-Airports-with-most-incidents-of-bird-strikes">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=aedf3b36-3493-4e03-9a01-bd95fbadb97a">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [39]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">"Top 50 Airports with most incidents of bird strikes:-"</span><span class="p">)</span>
<span class="n">Top50Airport</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Airport: Name'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()[:</span><span class="mi">50</span><span class="p">]</span>

<span class="nb">print</span><span class="p">(</span><span class="n">Top50Airport</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Top 50 Airports with most incidents of bird strikes:-
Airport: Name
DALLAS/FORT WORTH INTL ARPT               802
SACRAMENTO INTL                           676
SALT LAKE CITY INTL                       479
DENVER INTL AIRPORT                       476
KANSAS CITY INTL                          452
PHILADELPHIA INTL                         442
ORLANDO INTL                              408
BALTIMORE WASH INTL                       401
LOUISVILLE INTL ARPT                      394
JOHN F KENNEDY INTL                       389
CHARLOTTE/DOUGLAS INTL ARPT               367
NASHVILLE INTL                            364
LAMBERT-ST LOUIS INTL                     363
CHICAGO O'HARE INTL ARPT                  331
PORTLAND INTL (OR)                        313
NEWARK LIBERTY INTL ARPT                  305
CINCINNATI/NORTHERN KENTUCKY INTL ARPT    302
ATLANTA INTL                              296
CHICAGO MIDWAY INTL ARPT                  295
HOUSTON-HOBBY                             293
DETROIT METRO WAYNE COUNTY ARPT           281
FORT LAUDERDALE/HOLLYWOOD INTL            277
WASHINGTON DULLES INTL ARPT               269
EPPLEY AIRFIELD                           269
LAGUARDIA NY                              263
LOGAN INTL                                254
DALLAS LOVE FIELD ARPT                    253
METRO OAKLAND INTL                        251
MINNEAPOLIS-ST PAUL INTL                  244
GREATER PITTSBURGH                        237
AUSTIN-BERGSTROM INTL                     236
SAN FRANCISCO INTL ARPT                   226
NEW ORLEANS INTL                          219
LOS ANGELES INTL                          216
SOUTHWEST FLORIDA INTL ARPT               215
CLEVELAND-HOPKINS INTL ARPT               212
BIRMINGHAM-SHUTTLESWORTH INTL             209
MIAMI INTL                                202
MINETA SAN JOSE INTL                      201
GEORGE BUSH INTERCONTINENTAL              199
PHOENIX SKY HARBOR                        196
LIHUE ARPT                                195
SAN ANTONIO INTL                          194
BUFFALO-NIAGARA INTL                      182
HONOLULU INTL ARPT                        169
PORT COLUMBUS INTL                        166
RALEIGH-DURHAM INTL                       164
RONALD REAGAN WASHINGTON NATL             162
INDIANAPOLIS INTL                         160
JACKSONVILLE INTL                         155
Name: count, dtype: int64
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=01a15fe8-84db-4fe6-b605-7e6b61c2a197">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [40]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">Top50Airport</span> <span class="o">=</span> <span class="n">Top50Airport</span><span class="o">.</span><span class="n">to_dict</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=2374c773-227b-4836-b444-f292baa35436">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [41]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># use Year_dict keys and values in dict. Top10US</span>
<span class="n">TopAirport</span> <span class="o">=</span><span class="p">{</span><span class="s1">'airport'</span><span class="p">:</span><span class="nb">list</span><span class="p">(</span><span class="n">Top50Airport</span><span class="o">.</span><span class="n">keys</span><span class="p">()),</span><span class="s1">'BirdStrikes'</span><span class="p">:</span><span class="nb">list</span><span class="p">(</span><span class="n">Top50Airport</span><span class="o">.</span><span class="n">values</span><span class="p">())}</span>

<span class="c1"># Create bar chart with Plotly Express</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">TopAirport</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">'airport'</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">'BirdStrikes'</span><span class="p">,</span> <span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span> <span class="n">title</span><span class="o">=</span><span class="s1">'Top 50 Airports with most incidents of bird strikes'</span><span class="p">,</span> <span class="n">text</span><span class="o">=</span><span class="s1">'BirdStrikes'</span><span class="p">)</span>

<span class="c1"># URL of a image</span>
<span class="n">image_url</span> <span class="o">=</span> <span class="s1">'https://images.pexels.com/photos/358319/pexels-photo-358319.jpeg?auto=compress&amp;cs=tinysrgb&amp;w=1260&amp;h=750&amp;dpr=1'</span>


<span class="c1"># set color to all markers</span>
<span class="n">colors</span> <span class="o">=</span> <span class="p">[</span><span class="s1">'#FF5580'</span><span class="p">]</span> <span class="o">*</span> <span class="nb">len</span><span class="p">(</span><span class="n">TopAirport</span><span class="p">[</span><span class="s1">'airport'</span><span class="p">])</span>


<span class="c1"># Add image as background</span>
<span class="n">fig</span><span class="o">.</span><span class="n">add_layout_image</span><span class="p">(</span>
    <span class="nb">dict</span><span class="p">(</span>
        <span class="n">source</span><span class="o">=</span><span class="n">image_url</span><span class="p">,</span>
        <span class="n">xref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">yref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">x</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
        <span class="n">y</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizex</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>  <span class="c1"># Adjust width</span>
        <span class="n">sizey</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span>  <span class="c1"># Adjust height</span>
        <span class="n">sizing</span><span class="o">=</span><span class="s2">"stretch"</span><span class="p">,</span>
        <span class="n">opacity</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span>
        <span class="n">layer</span><span class="o">=</span><span class="s2">"below"</span>   <span class="p">))</span>


<span class="c1"># Update outer layout</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span><span class="n">width</span><span class="o">=</span><span class="mi">1000</span><span class="p">,</span>
    <span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span><span class="n">legend_borderwidth</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span><span class="n">margin</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">l</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span>
        <span class="n">r</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span>
        <span class="n">b</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">t</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">pad</span><span class="o">=</span><span class="mi">4</span>
    <span class="p">),</span><span class="n">font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'#F5DAD2'</span><span class="p">),</span><span class="n">paper_bgcolor</span> <span class="o">=</span> <span class="s1">'#5C88C4'</span><span class="p">,</span><span class="n">legend_bgcolor</span><span class="o">=</span><span class="s1">'#FFDB00'</span><span class="p">,</span><span class="n">title_font_color</span><span class="o">=</span><span class="s2">"#F9F5F6"</span><span class="p">,</span><span class="n">plot_bgcolor</span> <span class="o">=</span> <span class="s1">'rgba(100, 100, 100, 100)'</span><span class="p">,</span><span class="n">legend_title_font_color</span><span class="o">=</span><span class="s1">'rgba(1, 1, 50, 222)'</span><span class="p">,</span><span class="n">hoverlabel_grouptitlefont_color</span><span class="o">=</span><span class="s1">'#FF8F00'</span>
                  <span class="p">,</span><span class="n">font_size</span><span class="o">=</span><span class="mi">10</span><span class="p">)</span>






<span class="c1"># Update layout to ensure the image covers the full background</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span>
    <span class="n">template</span><span class="o">=</span><span class="s2">"plotly_white"</span><span class="p">,</span>
    <span class="n">images</span><span class="o">=</span><span class="p">[</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">source</span><span class="o">=</span><span class="n">image_url</span><span class="p">,</span>
        <span class="n">xref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">yref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">x</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
        <span class="n">y</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizex</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizey</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span>
        <span class="n">sizing</span><span class="o">=</span><span class="s2">"stretch"</span><span class="p">,</span>
        <span class="n">opacity</span><span class="o">=</span><span class="mf">0.2</span><span class="p">,</span>
        <span class="n">layer</span><span class="o">=</span><span class="s2">"below"</span>
    <span class="p">)],</span>
    <span class="n">margin</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">l</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">r</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">t</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">b</span><span class="o">=</span><span class="mi">5</span><span class="p">)</span>  <span class="p">)</span>

<span class="c1"># Update text</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_traces</span><span class="p">(</span><span class="n">textfont_size</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span> <span class="n">textangle</span> <span class="o">=</span> <span class="mi">0</span><span class="p">,</span> <span class="n">marker</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">line</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s2">"#FFFBDA"</span><span class="p">,</span> <span class="n">width</span><span class="o">=</span><span class="mi">1</span><span class="p">)),</span><span class="n">textposition</span><span class="o">=</span><span class="s1">'outside'</span><span class="p">,</span><span class="n">cliponaxis</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span><span class="n">textfont</span><span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'white'</span><span class="p">),</span><span class="n">marker_color</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">marker_line_width</span><span class="o">=</span><span class="mi">2</span><span class="p">)</span>

<span class="c1"># Show chart</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_xaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"Airport"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#FFC700"</span><span class="p">),</span><span class="n">tickfont</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">family</span><span class="o">=</span><span class="s2">"sans-serif"</span><span class="p">,</span>
        <span class="n">size</span><span class="o">=</span><span class="mi">7</span><span class="p">,</span>
        <span class="n">color</span><span class="o">=</span><span class="s2">"white"</span>  <span class="p">,</span>
    <span class="c1"># Change the color of the x-axis category labels</span>
    <span class="p">))</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_yaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"BirdStrikes"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#FFC700"</span> <span class="p">))</span>


<span class="n">fig</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output" data-mime-type="text/html" tabindex="0">
<div> <div class="plotly-graph-div" id="7eb45ab8-8b4f-4fef-b6f4-e7ba442b8fc6" style="height:500px; width:1000px;"></div> <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("7eb45ab8-8b4f-4fef-b6f4-e7ba442b8fc6")) {                    Plotly.newPlot(                        "7eb45ab8-8b4f-4fef-b6f4-e7ba442b8fc6",                        [{"alignmentgroup":"True","hovertemplate":"airport=%{x}<br>BirdStrikes=%{text}<extra></extra>","legendgroup":"","marker":{"color":["#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580"],"pattern":{"shape":""},"line":{"color":"#FFFBDA","width":2}},"name":"","offsetgroup":"","orientation":"v","showlegend":false,"text":[802.0,676.0,479.0,476.0,452.0,442.0,408.0,401.0,394.0,389.0,367.0,364.0,363.0,331.0,313.0,305.0,302.0,296.0,295.0,293.0,281.0,277.0,269.0,269.0,263.0,254.0,253.0,251.0,244.0,237.0,236.0,226.0,219.0,216.0,215.0,212.0,209.0,202.0,201.0,199.0,196.0,195.0,194.0,182.0,169.0,166.0,164.0,162.0,160.0,155.0],"textposition":"outside","x":["DALLAS/FORT WORTH INTL ARPT","SACRAMENTO INTL","SALT LAKE CITY INTL","DENVER INTL AIRPORT","KANSAS CITY INTL","PHILADELPHIA INTL","ORLANDO INTL","BALTIMORE WASH INTL","LOUISVILLE INTL ARPT","JOHN F KENNEDY INTL","CHARLOTTE/DOUGLAS INTL ARPT","NASHVILLE INTL","LAMBERT-ST LOUIS INTL","CHICAGO O'HARE INTL ARPT","PORTLAND INTL (OR)","NEWARK LIBERTY INTL ARPT","CINCINNATI/NORTHERN KENTUCKY INTL ARPT","ATLANTA INTL","CHICAGO MIDWAY INTL ARPT","HOUSTON-HOBBY","DETROIT METRO WAYNE COUNTY ARPT","FORT LAUDERDALE/HOLLYWOOD INTL","WASHINGTON DULLES INTL ARPT","EPPLEY AIRFIELD","LAGUARDIA NY","LOGAN INTL","DALLAS LOVE FIELD ARPT","METRO OAKLAND INTL","MINNEAPOLIS-ST PAUL INTL","GREATER PITTSBURGH","AUSTIN-BERGSTROM INTL","SAN FRANCISCO INTL ARPT","NEW ORLEANS INTL","LOS ANGELES INTL","SOUTHWEST FLORIDA INTL ARPT","CLEVELAND-HOPKINS INTL ARPT","BIRMINGHAM-SHUTTLESWORTH INTL","MIAMI INTL","MINETA SAN JOSE INTL","GEORGE BUSH INTERCONTINENTAL","PHOENIX SKY HARBOR","LIHUE ARPT","SAN ANTONIO INTL","BUFFALO-NIAGARA INTL","HONOLULU INTL ARPT","PORT COLUMBUS INTL","RALEIGH-DURHAM INTL","RONALD REAGAN WASHINGTON NATL","INDIANAPOLIS INTL","JACKSONVILLE INTL"],"xaxis":"x","y":[802,676,479,476,452,442,408,401,394,389,367,364,363,331,313,305,302,296,295,293,281,277,269,269,263,254,253,251,244,237,236,226,219,216,215,212,209,202,201,199,196,195,194,182,169,166,164,162,160,155],"yaxis":"y","type":"bar","textfont":{"color":"white","size":12},"cliponaxis":false,"textangle":0}],                        {"template":{"data":{"barpolar":[{"marker":{"line":{"color":"white","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"white","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"#C8D4E3","linecolor":"#C8D4E3","minorgridcolor":"#C8D4E3","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"#C8D4E3","linecolor":"#C8D4E3","minorgridcolor":"#C8D4E3","startlinecolor":"#2a3f5f"},"type":"carpet"}],"choropleth":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"choropleth"}],"contourcarpet":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"contourcarpet"}],"contour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"contour"}],"heatmapgl":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmapgl"}],"heatmap":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmap"}],"histogram2dcontour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2dcontour"}],"histogram2d":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2d"}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"mesh3d":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"mesh3d"}],"parcoords":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"parcoords"}],"pie":[{"automargin":true,"type":"pie"}],"scatter3d":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatter3d"}],"scattercarpet":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattercarpet"}],"scattergeo":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergeo"}],"scattergl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergl"}],"scattermapbox":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattermapbox"}],"scatterpolargl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolargl"}],"scatterpolar":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolar"}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"scatterternary":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterternary"}],"surface":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"surface"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}]},"layout":{"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"autotypenumbers":"strict","coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]],"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]},"colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"geo":{"bgcolor":"white","lakecolor":"white","landcolor":"white","showlakes":true,"showland":true,"subunitcolor":"#C8D4E3"},"hoverlabel":{"align":"left"},"hovermode":"closest","mapbox":{"style":"light"},"paper_bgcolor":"white","plot_bgcolor":"white","polar":{"angularaxis":{"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":""},"bgcolor":"white","radialaxis":{"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":""}},"scene":{"xaxis":{"backgroundcolor":"white","gridcolor":"#DFE8F3","gridwidth":2,"linecolor":"#EBF0F8","showbackground":true,"ticks":"","zerolinecolor":"#EBF0F8"},"yaxis":{"backgroundcolor":"white","gridcolor":"#DFE8F3","gridwidth":2,"linecolor":"#EBF0F8","showbackground":true,"ticks":"","zerolinecolor":"#EBF0F8"},"zaxis":{"backgroundcolor":"white","gridcolor":"#DFE8F3","gridwidth":2,"linecolor":"#EBF0F8","showbackground":true,"ticks":"","zerolinecolor":"#EBF0F8"}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"ternary":{"aaxis":{"gridcolor":"#DFE8F3","linecolor":"#A2B1C6","ticks":""},"baxis":{"gridcolor":"#DFE8F3","linecolor":"#A2B1C6","ticks":""},"bgcolor":"white","caxis":{"gridcolor":"#DFE8F3","linecolor":"#A2B1C6","ticks":""}},"title":{"x":0.05},"xaxis":{"automargin":true,"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":"","title":{"standoff":15},"zerolinecolor":"#EBF0F8","zerolinewidth":2},"yaxis":{"automargin":true,"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":"","title":{"standoff":15},"zerolinecolor":"#EBF0F8","zerolinewidth":2}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Airport","font":{"family":"Arial","size":18,"color":"#FFC700"}},"tickfont":{"family":"sans-serif","size":7,"color":"white"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"BirdStrikes","font":{"family":"Arial","size":18,"color":"#FFC700"}}},"legend":{"tracegroupgap":0,"title":{"font":{"color":"rgba(1, 1, 50, 222)"}},"borderwidth":10,"bgcolor":"#FFDB00"},"title":{"text":"Top 50 Airports with most incidents of bird strikes","font":{"color":"#F9F5F6"}},"barmode":"relative","height":500,"images":[{"layer":"below","opacity":0.2,"sizex":1,"sizey":2,"sizing":"stretch","source":"https://images.pexels.com/photos/358319/pexels-photo-358319.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1","x":0,"xref":"paper","y":1,"yref":"paper"}],"margin":{"l":10,"r":0,"b":5,"t":50,"pad":4},"font":{"color":"#F5DAD2","size":10},"hoverlabel":{"grouptitlefont":{"color":"#FF8F00"}},"width":1000,"paper_bgcolor":"#5C88C4","plot_bgcolor":"rgba(100, 100, 100, 100)"},                        {"responsive": true}                    ).then(function(){
                            
var gd = document.getElementById('7eb45ab8-8b4f-4fef-b6f4-e7ba442b8fc6');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script> </div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=b443c346-243b-4871-8133-34f9d92dea70">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F--Yearly-Cost-Incurred-due-to-Bird-Strikes">●  Yearly Cost Incurred due to Bird Strikes<a class="anchor-link" href="#%E2%97%8F--Yearly-Cost-Incurred-due-to-Bird-Strikes">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=bb6287cf-c163-4a5b-9223-d58c20123bcb">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [42]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Calcualte the Year from here and add in a dictionary</span>

<span class="n">Year</span> <span class="o">=</span> <span class="p">[]</span>

<span class="n">Cost</span> <span class="o">=</span> <span class="p">[]</span>

<span class="k">for</span> <span class="n">year</span> <span class="ow">in</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'year'</span><span class="p">]</span><span class="o">.</span><span class="n">unique</span><span class="p">():</span>

    <span class="n">CostByYear</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'year'</span><span class="p">]</span><span class="o">==</span><span class="n">year</span><span class="p">][</span><span class="s1">'Cost: Total $'</span><span class="p">]</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>
    
    <span class="n">Year</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">year</span><span class="p">)</span>
    
    <span class="n">Cost</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">CostByYear</span><span class="p">)</span>
    
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=752addb2-7896-4001-b65e-24166e988acd">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [43]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># use Year_dict keys and values in dict. Top10US</span>
<span class="n">YearCost</span> <span class="o">=</span><span class="p">{</span><span class="s1">'year'</span><span class="p">:</span><span class="n">Year</span><span class="p">,</span><span class="s1">'cost'</span><span class="p">:</span><span class="n">Cost</span><span class="p">}</span>

<span class="c1"># Create bar chart with Plotly Express</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">YearCost</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">'year'</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">'cost'</span><span class="p">,</span> <span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span> <span class="n">title</span><span class="o">=</span><span class="s1">'Yearly Cost Incurred due to Bird Strikes'</span><span class="p">,</span> <span class="n">text</span><span class="o">=</span><span class="s1">'cost'</span><span class="p">)</span>

<span class="c1"># URL of a image</span>
<span class="n">image_url</span> <span class="o">=</span> <span class="s1">'https://images.pexels.com/photos/912050/pexels-photo-912050.jpeg?auto=compress&amp;cs=tinysrgb&amp;w=1260&amp;h=750&amp;dpr=1'</span>


<span class="c1"># set color to all markers</span>
<span class="n">colors</span> <span class="o">=</span> <span class="p">[</span><span class="s1">'#FF5580'</span><span class="p">]</span> <span class="o">*</span> <span class="nb">len</span><span class="p">(</span><span class="n">YearCost</span><span class="p">[</span><span class="s1">'year'</span><span class="p">])</span>


<span class="c1"># Add image as background</span>
<span class="n">fig</span><span class="o">.</span><span class="n">add_layout_image</span><span class="p">(</span>
    <span class="nb">dict</span><span class="p">(</span>
        <span class="n">source</span><span class="o">=</span><span class="n">image_url</span><span class="p">,</span>
        <span class="n">xref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">yref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">x</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
        <span class="n">y</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizex</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>  <span class="c1"># Adjust width</span>
        <span class="n">sizey</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span>  <span class="c1"># Adjust height</span>
        <span class="n">sizing</span><span class="o">=</span><span class="s2">"stretch"</span><span class="p">,</span>
        <span class="n">opacity</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span>
        <span class="n">layer</span><span class="o">=</span><span class="s2">"below"</span>   <span class="p">))</span>


<span class="c1"># Update outer layout</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span><span class="n">width</span><span class="o">=</span><span class="mi">1000</span><span class="p">,</span>
    <span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span><span class="n">legend_borderwidth</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span><span class="n">margin</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">l</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span>
        <span class="n">r</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span>
        <span class="n">b</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">t</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">pad</span><span class="o">=</span><span class="mi">4</span>
    <span class="p">),</span><span class="n">font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'#F5DAD2'</span><span class="p">),</span><span class="n">paper_bgcolor</span> <span class="o">=</span> <span class="s1">'#1A2130'</span><span class="p">,</span><span class="n">legend_bgcolor</span><span class="o">=</span><span class="s1">'#FFDB00'</span><span class="p">,</span><span class="n">title_font_color</span><span class="o">=</span><span class="s2">"#F9F5F6"</span><span class="p">,</span><span class="n">plot_bgcolor</span> <span class="o">=</span> <span class="s1">'rgba(0, 0,100, 200)'</span><span class="p">,</span><span class="n">legend_title_font_color</span><span class="o">=</span><span class="s1">'rgba(1, 1, 50, 222)'</span><span class="p">,</span><span class="n">hoverlabel_grouptitlefont_color</span><span class="o">=</span><span class="s1">'#FF8F00'</span>
                  <span class="p">,</span><span class="n">font_size</span><span class="o">=</span><span class="mi">15</span><span class="p">)</span>






<span class="c1"># Update layout to ensure the image covers the full background</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span>
    <span class="n">template</span><span class="o">=</span><span class="s2">"plotly_white"</span><span class="p">,</span>
    <span class="n">images</span><span class="o">=</span><span class="p">[</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">source</span><span class="o">=</span><span class="n">image_url</span><span class="p">,</span>
        <span class="n">xref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">yref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">x</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
        <span class="n">y</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizex</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizey</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span>
        <span class="n">sizing</span><span class="o">=</span><span class="s2">"stretch"</span><span class="p">,</span>
        <span class="n">opacity</span><span class="o">=</span><span class="mf">0.4</span><span class="p">,</span>
        <span class="n">layer</span><span class="o">=</span><span class="s2">"below"</span>
    <span class="p">)],</span>
    <span class="n">margin</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">l</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">r</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">t</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">b</span><span class="o">=</span><span class="mi">5</span><span class="p">)</span>  <span class="p">)</span>

<span class="c1"># Update text</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_traces</span><span class="p">(</span><span class="n">textfont_size</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span> <span class="n">textangle</span> <span class="o">=</span> <span class="mi">0</span><span class="p">,</span> <span class="n">marker</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">line</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s2">"#FFBF00"</span><span class="p">,</span> <span class="n">width</span><span class="o">=</span><span class="mi">1</span><span class="p">)),</span><span class="n">textposition</span><span class="o">=</span><span class="s1">'outside'</span><span class="p">,</span><span class="n">cliponaxis</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span><span class="n">textfont</span><span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'#FFF67E'</span><span class="p">),</span><span class="n">marker_color</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">marker_line_width</span><span class="o">=</span><span class="mi">2</span><span class="p">)</span>

<span class="c1"># Show chart</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_xaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"Year"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#FFC700"</span><span class="p">),</span><span class="n">tickfont</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">family</span><span class="o">=</span><span class="s2">"sans-serif"</span><span class="p">,</span>
        <span class="n">size</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span>
        <span class="n">color</span><span class="o">=</span><span class="s2">"white"</span>  <span class="p">,</span>
    <span class="c1"># Change the color of the x-axis category labels</span>
    <span class="p">))</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_yaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"Cost (in milllions $)"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#FFC700"</span> <span class="p">))</span>


<span class="n">fig</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output" data-mime-type="text/html" tabindex="0">
<div> <div class="plotly-graph-div" id="5cdbc4c4-5c46-4719-842a-28083ed85451" style="height:500px; width:1000px;"></div> <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("5cdbc4c4-5c46-4719-842a-28083ed85451")) {                    Plotly.newPlot(                        "5cdbc4c4-5c46-4719-842a-28083ed85451",                        [{"alignmentgroup":"True","hovertemplate":"year=%{x}<br>cost=%{text}<extra></extra>","legendgroup":"","marker":{"color":["#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580"],"pattern":{"shape":""},"line":{"color":"#FFBF00","width":2}},"name":"","offsetgroup":"","orientation":"v","showlegend":false,"text":[5041825.0,21860525.0,8919504.0,13174490.0,18228216.0,8086573.0,7025996.0,8641474.0,11803009.0,9258223.0,10686111.0,13015223.0],"textposition":"outside","x":[2000,2001,2002,2003,2006,2004,2005,2007,2008,2009,2010,2011],"xaxis":"x","y":[5041825,21860525,8919504,13174490,18228216,8086573,7025996,8641474,11803009,9258223,10686111,13015223],"yaxis":"y","type":"bar","textfont":{"color":"#FFF67E","size":12},"cliponaxis":false,"textangle":0}],                        {"template":{"data":{"barpolar":[{"marker":{"line":{"color":"white","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"white","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"#C8D4E3","linecolor":"#C8D4E3","minorgridcolor":"#C8D4E3","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"#C8D4E3","linecolor":"#C8D4E3","minorgridcolor":"#C8D4E3","startlinecolor":"#2a3f5f"},"type":"carpet"}],"choropleth":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"choropleth"}],"contourcarpet":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"contourcarpet"}],"contour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"contour"}],"heatmapgl":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmapgl"}],"heatmap":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmap"}],"histogram2dcontour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2dcontour"}],"histogram2d":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2d"}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"mesh3d":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"mesh3d"}],"parcoords":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"parcoords"}],"pie":[{"automargin":true,"type":"pie"}],"scatter3d":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatter3d"}],"scattercarpet":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattercarpet"}],"scattergeo":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergeo"}],"scattergl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergl"}],"scattermapbox":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattermapbox"}],"scatterpolargl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolargl"}],"scatterpolar":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolar"}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"scatterternary":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterternary"}],"surface":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"surface"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}]},"layout":{"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"autotypenumbers":"strict","coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]],"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]},"colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"geo":{"bgcolor":"white","lakecolor":"white","landcolor":"white","showlakes":true,"showland":true,"subunitcolor":"#C8D4E3"},"hoverlabel":{"align":"left"},"hovermode":"closest","mapbox":{"style":"light"},"paper_bgcolor":"white","plot_bgcolor":"white","polar":{"angularaxis":{"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":""},"bgcolor":"white","radialaxis":{"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":""}},"scene":{"xaxis":{"backgroundcolor":"white","gridcolor":"#DFE8F3","gridwidth":2,"linecolor":"#EBF0F8","showbackground":true,"ticks":"","zerolinecolor":"#EBF0F8"},"yaxis":{"backgroundcolor":"white","gridcolor":"#DFE8F3","gridwidth":2,"linecolor":"#EBF0F8","showbackground":true,"ticks":"","zerolinecolor":"#EBF0F8"},"zaxis":{"backgroundcolor":"white","gridcolor":"#DFE8F3","gridwidth":2,"linecolor":"#EBF0F8","showbackground":true,"ticks":"","zerolinecolor":"#EBF0F8"}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"ternary":{"aaxis":{"gridcolor":"#DFE8F3","linecolor":"#A2B1C6","ticks":""},"baxis":{"gridcolor":"#DFE8F3","linecolor":"#A2B1C6","ticks":""},"bgcolor":"white","caxis":{"gridcolor":"#DFE8F3","linecolor":"#A2B1C6","ticks":""}},"title":{"x":0.05},"xaxis":{"automargin":true,"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":"","title":{"standoff":15},"zerolinecolor":"#EBF0F8","zerolinewidth":2},"yaxis":{"automargin":true,"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":"","title":{"standoff":15},"zerolinecolor":"#EBF0F8","zerolinewidth":2}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Year","font":{"family":"Arial","size":18,"color":"#FFC700"}},"tickfont":{"family":"sans-serif","size":12,"color":"white"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"Cost (in milllions $)","font":{"family":"Arial","size":18,"color":"#FFC700"}}},"legend":{"tracegroupgap":0,"title":{"font":{"color":"rgba(1, 1, 50, 222)"}},"borderwidth":10,"bgcolor":"#FFDB00"},"title":{"text":"Yearly Cost Incurred due to Bird Strikes","font":{"color":"#F9F5F6"}},"barmode":"relative","height":500,"images":[{"layer":"below","opacity":0.4,"sizex":1,"sizey":2,"sizing":"stretch","source":"https://images.pexels.com/photos/912050/pexels-photo-912050.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1","x":0,"xref":"paper","y":1,"yref":"paper"}],"margin":{"l":10,"r":0,"b":5,"t":50,"pad":4},"font":{"color":"#F5DAD2","size":15},"hoverlabel":{"grouptitlefont":{"color":"#FF8F00"}},"width":1000,"paper_bgcolor":"#1A2130","plot_bgcolor":"rgba(0, 0,100, 200)"},                        {"responsive": true}                    ).then(function(){
                            
var gd = document.getElementById('5cdbc4c4-5c46-4719-842a-28083ed85451');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script> </div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=3b44e7dc-6e11-410a-8162-5c4738272b70">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Key Insights :- year 2001 and 2006 is too costly incurred due to birdstrikes and year 2000 is less costly.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=703db268-3ebe-4db3-8bfa-1e45ea01c350">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F-Altitude-of-aeroplanes-at-the-time-of-strike">● Altitude of aeroplanes at the time of strike<a class="anchor-link" href="#%E2%97%8F-Altitude-of-aeroplanes-at-the-time-of-strike">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=331234b1-28cc-441c-b685-eff189f6a908">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [44]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># use Year_dict keys and values in dict. Top10US</span>
<span class="n">Altitude</span> <span class="o">=</span><span class="p">{</span><span class="s1">'Feet above ground'</span><span class="p">:</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">],</span><span class="s1">'BirdStrike'</span><span class="p">:[</span><span class="n">i</span> <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">]))]</span> <span class="p">}</span>

<span class="c1"># Create bar chart with Plotly Express</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">Altitude</span><span class="p">,</span><span class="n">height</span><span class="o">=</span><span class="mi">600</span><span class="p">,</span><span class="n">x</span><span class="o">=</span><span class="s1">'Feet above ground'</span><span class="p">,</span><span class="n">y</span><span class="o">=</span><span class="s1">'BirdStrike'</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">'Feet above ground'</span><span class="p">,</span><span class="n">title</span><span class="o">=</span><span class="s1">'Altitude of aeroplanes at the time of strike.'</span><span class="p">)</span>

<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_xaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"Feet above ground (in thousands)"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#EE4266"</span><span class="p">),</span><span class="n">tickfont</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">family</span><span class="o">=</span><span class="s2">"sans-serif"</span><span class="p">,</span>
        <span class="n">size</span><span class="o">=</span><span class="mi">20</span><span class="p">,</span>
        <span class="n">color</span><span class="o">=</span><span class="s2">"#B7C9F2"</span>  <span class="p">,</span>
    <span class="c1"># Change the color of the x-axis category labels</span>
    <span class="p">))</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_yaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"BirdStrikes"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#EE4266"</span> <span class="p">))</span>



<span class="c1"># Update outer layout</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span><span class="n">width</span><span class="o">=</span><span class="mi">1000</span><span class="p">,</span>
    <span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span><span class="n">legend_borderwidth</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span><span class="n">margin</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">l</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span>
        <span class="n">r</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span>
        <span class="n">b</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">t</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">pad</span><span class="o">=</span><span class="mi">4</span>
    <span class="p">),</span><span class="n">font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'#F5DAD2'</span><span class="p">),</span><span class="n">paper_bgcolor</span> <span class="o">=</span> <span class="s1">'#1A2130'</span><span class="p">,</span><span class="n">legend_bgcolor</span><span class="o">=</span><span class="s1">'#FFDB00'</span><span class="p">,</span><span class="n">title_font_color</span><span class="o">=</span><span class="s2">"#F9F5F6"</span><span class="p">,</span><span class="n">plot_bgcolor</span> <span class="o">=</span> <span class="s1">'rgba(255, 255,255, 200)'</span><span class="p">,</span><span class="n">legend_title_font_color</span><span class="o">=</span><span class="s1">'rgba(1, 1, 50, 222)'</span><span class="p">,</span><span class="n">hoverlabel_grouptitlefont_color</span><span class="o">=</span><span class="s1">'#FF8F00'</span>
                  <span class="p">,</span><span class="n">font_size</span><span class="o">=</span><span class="mi">15</span><span class="p">)</span>



<span class="n">fig</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output" data-mime-type="text/html" tabindex="0">
<div> <div class="plotly-graph-div" id="23475b21-cd69-47b8-9815-9deb828a3919" style="height:500px; width:1000px;"></div> <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("23475b21-cd69-47b8-9815-9deb828a3919")) {                    Plotly.newPlot(                        "23475b21-cd69-47b8-9815-9deb828a3919",                        [{"hovertemplate":"Feet above ground=%{marker.color}<br>BirdStrike=%{y}<extra></extra>","legendgroup":"","marker":{"color":[1500,0,50,50,50,150,100,0,0,200,1700,0,1800,50,500,0,0,800,500,5000,1500,0,2000,0,20,200,75,10,10,5000,1000,1300,0,0,800,1000,1500,1000,0,50,100,100,50,0,0,500,0,3500,1000,30,2000,1800,0,0,75,0,50,0,0,850,30,0,1000,0,500,150,0,0,10,0,800,500,0,40,0,0,0,20,0,5100,0,100,0,0,20,100,100,10,0,0,0,0,0,100,0,0,20,0,0,0,350,0,200,50,0,50,0,0,0,100,0,0,0,0,0,100,0,0,150,100,2500,0,0,100,30,0,40,0,5,25,0,0,0,10,300,15,0,0,50,0,1000,20,0,0,0,0,500,0,30,200,0,0,40,2500,0,0,2200,150,100,0,100,0,3200,100,0,0,2500,0,1400,20,100,2000,0,0,400,300,0,0,0,1500,200,0,3400,250,2000,1000,0,50,0,0,3500,0,2000,4000,50,0,9000,0,20,50,0,1800,100,400,400,25,0,0,30,0,400,50,0,0,20,0,100,1400,0,200,0,50,0,200,0,2000,100,100,50,0,200,10,100,1000,0,0,0,400,0,300,0,200,8000,1000,0,0,0,1200,2000,0,1000,200,1200,55,100,0,0,20,200,50,1500,10,0,700,0,20,2000,0,0,50,700,200,0,150,0,0,0,0,50,700,1500,0,0,0,30,0,25,10,50,50,1000,0,10,0,1000,50,50,30,0,300,0,10,50,2600,15,0,0,0,20,0,0,0,50,0,50,0,20,0,0,100,0,0,150,500,0,500,0,10,0,0,0,50,10,50,0,400,0,0,0,0,10,0,50,0,0,0,150,0,250,0,0,0,0,5,200,0,0,50,0,4500,10,0,0,0,50,100,300,0,0,100,40,0,0,0,50,0,50,0,0,100,0,5000,0,3500,0,0,4700,0,0,0,100,1000,0,0,800,200,3000,500,50,1600,10,2700,700,75,500,0,10,0,0,75,500,0,0,150,0,100,0,0,50,0,200,0,200,400,100,0,0,0,500,50,0,272,0,100,20,100,50,0,2000,800,2000,200,5,0,100,1500,200,400,0,0,50,100,50,0,100,7000,0,0,200,0,0,2400,700,25,7500,1200,50,50,750,0,0,3000,0,0,0,2500,6200,0,1000,0,50,400,0,100,2500,0,0,380,0,0,100,10000,2000,0,20,8000,0,1800,0,100,0,1000,300,150,0,35,0,50,0,100,50,0,50,200,0,10,0,0,500,50,1000,0,0,50,0,150,200,40,0,0,20,0,20,0,10,0,0,0,0,5,0,0,0,0,0,0,0,200,210,30,12,0,0,100,0,100,35,0,4600,0,0,20,10,0,200,0,0,0,0,0,0,0,0,0,10,0,500,0,0,0,0,0,0,10,0,0,0,0,2,10,20,0,50,200,50,0,1000,10,0,0,300,5000,0,0,50,0,10800,15,0,600,25,0,2300,7000,0,0,0,0,0,0,30,3000,0,0,0,3000,0,0,8000,0,20,0,0,0,0,50,5,0,40,50,0,14000,0,0,300,1300,1200,1500,1200,10,3000,600,0,10,0,5,1750,2200,10,150,0,50,10,4000,0,0,0,6,75,0,2300,0,0,750,0,15,0,0,5000,0,0,800,0,2000,20,200,0,200,0,0,100,0,2000,0,0,150,0,0,100,2100,1500,5,0,0,100,0,0,0,0,2800,400,1500,0,800,0,0,0,0,0,0,35,5000,720,0,500,3500,1000,0,20,800,10,150,300,350,10,350,1000,1000,350,0,500,400,0,100,5,1900,0,20,0,200,250,50,1700,0,10,0,600,800,0,0,500,0,4700,300,500,100,30,500,2400,0,0,0,0,200,0,2000,400,500,4300,1000,0,5,300,2700,0,0,2,0,40,50,50,50,15,1700,200,100,30,400,100,20,20,80,350,15,15,0,0,0,0,0,90,5,0,0,0,50,0,0,50,0,50,1160,0,0,0,0,10,0,0,0,0,0,20,0,0,0,10,50,0,2500,200,20,0,0,0,0,0,0,1500,0,0,100,0,0,0,0,0,200,0,0,0,150,0,0,10,30,0,50,50,20,0,100,10,0,50,200,5,120,0,0,25,0,25,1000,0,400,0,1600,400,100,50,1500,0,20,0,5000,0,0,0,0,50,150,1000,1500,0,6,0,0,5,300,0,10,100,400,0,500,0,0,0,0,0,0,0,0,0,0,0,350,0,300,100,9000,2200,0,1200,2200,0,5,25,25,8500,0,0,0,0,1000,0,0,800,1000,0,0,0,0,100,500,50,0,0,0,0,0,0,0,50,1900,0,20,100,2500,50,100,2500,250,50,500,0,800,4000,3000,0,1000,0,4000,500,0,300,0,1500,40,300,0,0,0,50,0,300,0,0,7000,0,0,50,400,4800,0,1200,20,100,0,50,500,0,0,0,0,0,2900,3000,500,0,20,0,0,0,500,0,25,0,1500,50,0,0,0,100,0,200,0,0,100,25,20,0,0,0,100,0,700,50,20,50,500,0,500,200,2500,0,4000,1600,1600,8000,300,0,0,800,0,0,0,3000,10,4500,1000,0,5000,0,200,0,80,1500,200,50,0,100,300,10,10,200,0,5,0,0,0,0,5,0,200,5700,0,0,100,0,0,0,125,0,0,0,0,0,600,0,300,90,0,0,300,0,0,200,10,0,0,5,0,0,10,0,500,0,0,0,0,600,0,0,0,0,0,0,10,0,0,0,0,200,0,5,5,100,1500,0,0,0,0,200,0,2,25,20,0,0,400,0,200,200,50,200,0,1500,0,0,0,0,0,0,0,25,0,0,0,0,150,0,0,5,0,0,20,7000,0,1200,0,0,10,0,0,300,0,10,100,0,4800,20,300,0,0,0,100,0,75,0,580,0,50,0,10,100,0,100,0,0,0,0,0,0,0,100,0,200,250,200,0,15,3400,200,20,0,0,300,0,1000,10,0,500,200,3000,100,50,1000,500,0,0,0,10,100,0,50,0,50,10,0,0,0,3000,0,100,30,1000,0,0,60,5,0,2000,500,200,3000,75,10000,50,2300,0,0,100,150,0,300,100,0,400,1500,20,0,0,3400,300,150,5,200,50,150,50,5500,20,100,100,9000,0,500,600,0,0,500,100,700,0,35,200,400,1500,1500,1000,50,0,0,0,1300,0,100,0,50,300,0,150,60,100,0,15,50,20,1200,0,1000,400,1500,5200,100,1500,0,500,0,0,50,400,0,1500,0,3200,0,0,2000,0,2000,300,0,6200,1000,4000,200,0,0,50,20,200,10,7000,0,0,500,0,0,20,100,0,0,50,100,0,500,0,0,30,50,0,0,5,0,10,0,0,0,0,20,0,50,0,550,10,0,0,0,0,0,0,0,0,0,0,0,200,0,0,20,0,50,60,0,150,0,0,0,20,0,0,30,0,0,0,0,0,0,0,0,0,0,0,10,0,0,0,0,0,0,0,15,0,0,200,10,0,100,150,200,0,0,20,0,300,200,0,100,1500,0,100,3000,1000,0,0,0,300,0,1000,0,400,30,50,0,7400,200,600,0,0,200,0,0,30,50,5000,0,100,2500,100,0,0,0,0,100,25,0,0,100,0,0,3000,500,0,500,4000,1300,10,2500,800,0,50,0,0,100,0,50,0,400,0,500,20,1400,0,2,3000,0,500,0,0,0,150,0,300,100,200,350,700,10,100,100,2000,0,400,0,0,0,1000,800,4000,1200,500,0,0,0,50,0,100,0,2700,300,2500,800,0,50,10,0,0,0,10,0,150,5,1200,0,0,300,2,4000,1500,40,100,0,1800,0,200,8,100,200,800,0,0,2500,0,1000,150,20,5,1800,0,10,20,0,0,0,2500,0,0,0,0,0,800,0,10,1000,1000,0,0,10,0,300,100,0,0,0,0,200,70,500,0,0,10,0,5000,0,0,10,0,0,3,0,700,50,200,0,15,0,0,1500,5000,7000,0,1000,400,400,5,200,0,0,0,200,15,0,6000,0,10,0,0,0,100,150,0,3000,100,0,120,400,175,50,200,0,0,100,1200,300,0,0,80,0,10,0,0,5,0,0,50,0,50,0,10,200,0,0,0,0,0,250,30,0,0,0,10,0,800,0,0,500,0,5,800,30,200,0,0,0,0,0,0,0,50,10,20,30,0,0,0,5,0,4,0,50,0,100,1200,0,3000,10,0,0,70,100,0,10,0,0,20,0,0,10,0,0,500,25,10000,0,0,20,5,0,100,0,0,0,0,37,700,20,0,0,0,0,0,0,0,0,0,0,0,0,0,10,100,500,0,0,0,400,0,0,200,0,0,100,700,0,0,100,40,2000,0,0,8000,0,10,0,50,50,10,5000,0,1200,1000,200,400,7,0,100,90,300,250,0,0,400,0,15000,0,100,2500,2,1300,3500,0,0,3000,4000,50,0,0,0,50,1800,0,0,1000,50,300,300,0,0,0,0,0,100,0,0,0,0,300,0,200,400,50,0,100,0,500,0,1150,0,0,0,0,0,40,0,5000,1000,20,1300,0,0,3000,0,400,0,1000,0,1700,300,100,200,2500,100,1000,580,0,0,0,3000,0,3000,0,900,0,10,5000,200,0,100,10,800,20,500,0,0,50,100,0,10,100,2000,800,0,750,1300,200,0,200,0,0,800,0,200,450,10,0,50,0,650,0,0,30,0,0,0,5,10,100,50,0,0,0,0,2500,0,0,0,0,0,0,50,0,0,75,50,0,200,500,0,400,3000,200,0,0,0,75,3000,0,0,0,600,0,0,0,0,50,15,10,0,40,3000,500,0,0,75,500,0,0,300,50,26,5000,0,0,0,30,1500,3000,0,200,0,1500,1700,50,4000,200,0,0,20,2500,1000,1200,5200,200,11000,0,0,0,100,0,0,50,0,100,700,0,0,0,0,0,0,3500,700,0,7000,15,50,0,300,0,0,50,15,0,10,20,0,10,0,0,0,0,0,0,0,0,50,0,0,50,0,50,20,1200,0,15,0,0,0,0,20,15,0,800,0,10,0,0,0,100,6000,10,25,50,50,0,0,0,0,90,0,0,0,50,0,0,0,0,150,100,0,0,5,0,50,150,0,100,0,100,0,0,0,25,0,0,5,150,1000,0,0,30,0,0,100,10,1000,100,0,0,0,5,0,2,1000,0,0,0,0,1800,5,0,0,0,10,3500,0,100,0,100,200,250,0,0,400,0,0,100,100,20,0,0,0,0,2100,5000,0,0,0,5500,500,0,0,0,2000,0,0,0,0,400,1500,0,0,0,120,0,100,0,500,100,800,0,0,0,0,0,0,0,0,0,0,100,5000,0,50,900,12800,3000,10,3500,100,6500,0,0,0,0,50,10000,0,50,7500,50,4000,100,0,0,10,3000,0,0,0,150,500,0,0,1500,0,1500,200,0,0,0,1800,0,0,0,200,50,50,0,0,0,10,200,0,10,1000,0,0,0,200,2000,0,200,400,0,1000,0,0,200,4000,0,0,50,3000,1000,3000,0,1600,0,3000,0,0,0,10,300,800,1500,0,30,50,2900,500,100,10,1500,0,50,10,50,50,15,300,0,1000,0,500,0,300,0,4000,900,100,100,8000,0,0,150,374,0,0,0,0,10,0,0,100,50,0,900,400,0,200,50,0,100,50,1000,350,100,500,1000,2400,3000,0,100,1800,500,0,0,0,10,200,30,0,500,7000,3000,1200,600,200,100,1500,0,4000,0,10,0,0,10,0,0,350,4000,1000,500,50,0,0,800,400,0,1500,15,0,600,5,400,4000,5000,0,0,0,10,500,30,0,0,50,0,0,0,0,0,0,50,500,50,400,0,40,20,0,0,0,50,0,0,5,1,10,0,100,60,1000,1000,800,0,10,100,50,0,300,10,2,10,20,150,75,0,50,0,0,0,0,0,200,100,0,0,0,0,0,0,20,0,0,0,100,60,10,0,0,50,15,0,0,50,70,5,0,0,100,10,0,0,5,0,0,10,0,0,200,100,0,50,500,300,75,300,0,0,0,100,0,50,400,0,0,150,0,200,0,50,0,8000,0,0,0,0,0,0,0,0,0,0,4000,0,0,100,10,0,2000,0,0,5,0,300,0,0,0,0,0,0,3000,500,400,2500,0,1200,0,0,8000,0,2500,400,1800,3000,0,50,0,0,100,0,0,3000,0,2000,10,15,500,300,0,0,800,4500,20,150,550,30,0,500,2300,2300,0,1000,0,0,0,0,0,25,100,250,1000,6000,1100,0,25,50,100,2000,500,0,0,600,0,0,1600,2400,0,30,0,5000,100,100,1000,200,10,0,7000,200,1000,500,5,0,0,200,40,0,600,1000,200,500,7000,200,50,0,50,20,700,25,0,0,150,0,0,2000,50,100,0,20,0,10,0,400,0,1000,0,400,0,200,1000,5,1500,0,100,100,10,400,0,0,2000,600,700,0,0,20,100,0,65,0,600,0,100,10,8500,0,0,0,600,0,1000,0,100,700,0,1500,0,0,500,100,3900,0,1000,0,10,2500,8000,300,0,2000,0,300,1400,1300,2400,0,90,0,25,400,0,30,0,5,2000,120,800,100,200,2600,0,0,0,0,0,0,2000,400,0,0,1000,6000,10,0,350,50,1000,0,250,50,500,0,3000,5000,200,400,3000,0,0,150,2000,8000,900,50,100,500,40,0,0,0,0,50,0,0,0,75,100,0,100,100,10,0,37,0,0,50,0,0,1000,0,0,0,0,0,100,100,0,0,0,100,4500,0,0,150,10,80,30,0,20,0,200,0,10,10,0,0,500,20,0,0,50,0,0,0,800,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,10,0,100,150,10,200,0,0,0,600,15,0,12,50,100,100,50,500,0,100,20,0,0,0,150,1200,0,200,0,0,0,0,0,0,0,0,0,0,0,0,0,0,10,0,200,50,35,0,0,25,10,0,25,0,100,0,0,0,10,30,1500,20,250,3,50,0,350,0,25,11000,0,1000,0,0,200,0,0,0,0,0,300,1300,0,20,50,0,0,50,5,0,0,10,10,0,0,0,3000,0,0,0,0,11,0,100,30,100,20,0,0,0,0,50,0,100,0,100,500,30,0,0,0,0,50,0,0,0,0,0,0,0,10,0,0,0,200,0,0,2000,10,0,0,0,0,500,0,0,0,0,0,600,0,0,100,10,700,50,200,4000,0,0,0,0,6500,0,0,0,2000,0,10,100,0,75,200,4000,50,0,1000,200,1500,200,0,100,2000,0,6000,2000,50,0,0,25,700,4500,0,0,0,500,0,20,0,0,0,0,300,50,30,5,1000,50,0,8000,0,200,0,200,0,0,0,400,0,300,0,0,0,100,1100,100,75,0,150,0,0,0,0,0,10,0,63,100,0,0,100,2500,0,50,100,5500,3000,0,0,0,0,0,50,0,0,200,400,0,100,2000,3000,4400,1000,200,9300,0,800,0,250,600,1800,0,0,0,0,0,200,100,3500,4260,2500,300,3000,3000,100,0,0,0,50,0,4000,0,4000,500,2200,0,500,100,50,550,0,0,0,0,0,800,0,1500,50,2000,0,2000,7,1200,0,30,1500,2000,2500,0,0,0,0,800,0,600,1500,2000,0,200,3500,0,30,10,0,1000,0,400,50,50,20,50,0,50,0,0,0,150,0,1800,3000,0,150,0,10,5,0,20,0,0,0,0,200,0,0,0,0,10,100,200,6000,0,50,50,0,4000,0,1700,300,2000,1500,0,700,750,0,200,100,900,10,20,100,0,200,0,0,50,0,100,50,200,15,0,1000,0,1500,500,30,100,50,200,1200,200,100,0,150,1000,0,0,75,50,0,2000,100,0,600,0,0,0,1700,0,200,0,0,10,0,0,0,800,20,2550,150,5,100,0,600,100,0,0,800,10,10,0,0,0,0,0,0,0,0,0,300,0,20,25,0,0,0,1000,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,100,0,0,0,0,0,10,0,0,0,0,0,30,200,50,0,0,0,0,3000,0,0,50,300,50,50,0,25,0,0,0,0,20,0,0,10,0,100,10,0,10,200,10,15,200,30,0,700,0,40,100,0,0,0,50,0,0,0,0,25,300,0,10,0,10,300,0,0,0,0,0,0,0,500,0,5,50,0,100,10,5,0,700,0,0,0,0,20,100,30,400,0,0,0,0,0,0,0,50,50,6800,0,0,0,0,10,20,20,0,100,0,0,0,0,50,55,0,100,0,0,0,5,20,0,0,0,0,0,150,0,0,0,0,10,0,0,0,0,1500,0,0,30,5000,0,50,200,50,0,0,0,0,0,0,300,0,0,0,100,100,0,30,0,0,0,200,0,10,0,0,800,10,0,5,20,0,1200,3400,0,50,100,25,0,0,200,200,0,10,0,0,1500,0,0,450,0,500,1000,1000,500,0,20,20,700,10,0,0,0,500,0,1000,200,0,3500,3500,1000,100,100,0,50,0,0,0,10,0,0,20,0,0,0,0,0,2100,400,0,0,0,100,25,700,50,0,15,10,0,200,0,60,5000,150,800,0,0,0,0,3000,10,0,0,10,0,0,200,0,0,1000,200,4000,0,30,0,0,0,500,0,30,1100,0,6000,300,2500,3000,200,6600,150,500,200,10,0,2000,200,200,0,0,100,0,2000,3000,5000,0,10,800,0,1,25,0,0,3,650,0,0,0,5,1500,0,0,0,0,0,4000,1000,200,0,100,100,100,1500,2000,5000,0,2,500,1200,50,100,400,0,0,50,0,0,0,300,300,50,600,300,500,3000,0,10,400,600,1200,1300,0,0,2000,0,0,1200,700,300,0,0,0,1000,300,0,2000,100,200,0,0,0,1000,10,1000,50,150,150,2000,0,1900,2000,2000,0,0,1800,0,50,0,1000,0,2000,100,90,50,100,800,50,3000,1400,10,400,2000,100,0,0,0,0,200,0,0,0,0,2000,0,0,0,1,400,0,1200,0,0,25,0,400,0,3000,0,0,0,0,400,75,27,40,0,0,400,150,10,0,100,0,400,80,500,0,1000,20,80,3000,5,0,0,0,300,5000,0,300,0,45,0,0,20,0,0,300,0,300,9000,10,500,0,100,0,0,0,0,0,400,1800,1500,0,1500,4000,900,0,0,0,5,4000,0,2000,2,4500,700,100,50,0,500,0,30,0,0,20,0,0,25,0,20,50,20,50,20,0,200,200,2,100,0,0,0,50,0,13,0,750,0,20,200,0,9,50,150,0,0,0,100,300,0,0,0,0,300,0,0,0,0,0,15,0,0,0,50,0,0,500,5,0,100,10,5,100,0,0,20,0,5,100,10,0,300,3000,0,0,0,900,0,0,0,0,1,50,0,20,10,20,50,0,0,200,0,150,0,10,10,0,0,15,0,0,150,0,0,0,5,0,0,5,0,50,0,25,0,0,2500,0,50,50,1150,0,0,5,0,0,0,0,0,200,10,50,0,0,10,0,0,0,0,0,0,0,30,1500,0,500,0,0,500,0,6700,0,0,0,0,50,200,1600,700,50,0,300,100,200,0,150,20,0,0,100,0,0,10,20,0,0,0,0,0,0,100,0,3000,100,100,0,3000,0,0,300,6000,1800,0,10,0,0,20,0,3500,20,1300,0,1000,50,0,0,0,1600,1000,0,0,10000,0,1900,25,500,0,0,0,10,0,150,2200,400,0,8000,10,0,0,5500,20,0,15,0,0,10,3000,10,0,4000,50,0,1200,0,0,0,0,0,0,0,0,250,0,0,0,50,0,100,0,0,0,0,4400,0,200,0,0,400,1800,0,5,20,2200,0,100,30,10,100,0,0,400,0,500,0,50,0,0,500,3800,0,600,0,0,50,100,0,3000,0,400,1800,200,700,0,10,0,0,0,5,0,0,0,0,100,0,425,25,1500,4000,0,19,1900,100,100,0,50,800,0,0,0,1000,100,900,200,10,500,10,10,0,200,150,1000,0,0,10,100,10,50,0,0,500,0,0,300,0,0,50,0,100,0,95,1000,800,3000,400,20,200,0,350,0,200,100,2500,0,85,10,0,0,10,0,0,0,0,0,200,0,5,0,0,0,100,0,15,0,0,0,0,600,5,0,30,0,0,0,0,0,700,0,0,0,100,0,0,0,0,0,200,100,15,30,0,500,0,75,0,20,10,50,0,100,50,50,0,0,50,0,10,100,0,20,0,20,10,0,2300,0,20,0,0,0,0,10,100,60,0,20,15,25,800,0,500,0,0,0,0,50,200,150,10,0,50,50,0,0,10,0,0,0,0,0,1980,50,0,0,1250,100,0,0,10,0,50,0,600,300,50,600,6000,0,10,0,0,100,100,20,0,0,0,100,150,15,0,0,150,0,25,100,50,40,150,0,0,0,50,10,150,0,0,20,0,0,0,0,250,450,20,0,0,10,50,35,0,5,0,100,10,0,0,50,200,50,10,10,0,0,0,300,200,50,1800,20,10,100,400,60,100,0,0,0,0,20,0,0,0,100,0,0,0,50,0,0,20,10,0,200,20,200,0,100,100,0,4000,35,1000,50,50,0,200,10,0,50,0,0,50,150,0,0,10,10,3000,100,100,350,0,200,0,200,100,0,5,5,0,50,500,0,20,0,0,0,75,0,100,300,30,70,0,100,0,500,0,50,0,0,0,0,200,500,0,0,1000,10,12000,0,0,20,0,50,0,30,0,30,0,0,50,2,200,100,200,0,100,30,500,0,0,0,2000,200,800,1800,100,50,100,0,0,100,800,5,700,0,0,1300,1000,3,10,40,2000,10,0,100,400,300,50,50,100,100,300,200,200,1500,3000,400,200,0,50,300,5,7000,10,400,0,0,300,100,30,20,800,300,0,100,10,0,100,0,3,1600,0,10,50,800,1200,75,500,2300,0,0,50,50,0,100,1600,0,500,2000,0,2300,1000,0,75,3000,0,10,30,100,1500,500,0,2000,700,5000,300,1500,1000,400,0,400,0,500,4000,5000,2000,0,100,0,0,0,0,100,150,1000,3000,2000,7000,300,0,3000,300,1000,5,500,0,50,10,0,450,3000,400,200,0,2500,300,7000,30,200,2,1200,3000,50,1000,2400,300,0,300,1800,6000,0,50,1500,0,2000,10,15,0,75,0,30,0,0,7000,0,5,0,0,0,3500,5000,400,300,300,0,5000,100,700,1000,0,0,50,7000,100,0,0,8000,6500,6000,10,3,1200,6200,5000,8000,100,800,0,200,50,5,300,2100,5600,3000,0,800,150,2500,2400,3000,3500,1000,0,2500,5000,3000,10,150,3000,500,1500,400,6000,200,9500,50,0,1900,3000,0,100,0,50,3500,10,7000,100,1000,100,2500,1200,3000,150,3500,3400,0,1500,200,200,100,1800,2000,100,8000,200,100,1500,1500,500,500,400,7000,1000,1000,2900,10,500,4000,30,100,8300,4000,1000,1900,10,1000,50,0,3,1000,0,900,1200,100,50,300,20,50,3000,200,0,75,5000,0,10,50,4000,0,0,50,100,0,0,8000,300,50,0,12000,0,200,0,0,10,0,0,0,0,0,20,200,40,1000,0,300,200,2000,500,0,300,100,0,2000,600,800,200,2500,1500,0,0,0,800,50,50,0,300,0,105,0,0,400,0,0,0,2500,50,400,0,1500,3000,0,300,100,0,50,300,0,0,0,1600,0,0,1000,0,300,10,1400,800,20,400,100,0,500,400,0,0,0,2100,4000,0,100,1000,0,0,0,0,0,0,50,0,4000,10,7000,30,100,3,0,800,100,100,20,0,50,0,500,2000,0,200,0,0,100,0,0,0,100,5,10,100,7000,50,75,13000,300,0,0,700,15,1200,0,0,0,100,100,0,0,50,0,0,0,75,0,2000,0,0,20,0,300,50,0,0,800,1500,200,40,500,0,0,800,5,1200,400,0,0,10,0,0,0,600,500,0,3500,1500,0,0,20,0,10,0,9,900,400,100,50,20,0,0,100,20,100,500,50,100,0,0,0,15,0,30,20,0,0,0,1500,0,11000,0,50,0,800,0,100,0,200,0,0,1200,200,0,150,400,0,100,0,0,250,200,0,400,0,0,0,0,0,0,0,50,0,20,10,0,5,20,200,0,0,6000,20,0,0,0,0,300,800,100,0,0,0,0,0,0,25,7,100,0,0,10,0,0,400,1000,50,200,8000,2800,10800,100,100,1500,100,7,1500,500,0,200,1000,1700,0,0,0,20,0,0,300,0,0,0,20,20,200,800,40,150,500,20,0,2500,2300,0,0,100,9650,300,300,50,200,0,0,0,2000,2300,6300,0,300,2600,50,0,0,10,3000,60,0,800,50,100,50,50,100,300,200,100,0,100,10,7000,0,0,5500,0,0,9000,700,750,750,10,1500,300,15,0,3000,3200,3300,600,0,1500,7700,5500,760,1000,0,20,2000,400,100,2,100,100,0,0,100,950,3500,10000,1500,0,500,500,1500,1700,0,500,500,0,1500,0,50,0,3000,100,300,20,50,100,0,0,20,10,10,0,1100,0,600,0,200,0,200,0,200,0,0,2000,30,0,0,0,0,0,0,3300,0,7200,300,1500,2,0,2200,500,800,0,500,0,0,300,1100,0,6000,10,900,2700,0,500,2600,1600,50,3000,2600,30,0,0,0,1000,10,1200,0,0,0,10,0,0,100,0,100,7000,20,3000,0,1000,50,3000,0,0,3000,2500,100,1100,0,0,0,1200,50,100,0,400,1200,4700,0,1500,300,1000,0,0,800,1000,0,2000,1800,3000,0,10,400,0,300,90,500,1000,0,500,50,2000,7000,0,1900,0,100,200,1500,50,1500,3000,0,0,1000,600,2400,7000,110,0,200,700,1200,4000,200,3100,3500,400,0,2000,200,0,150,2500,800,2800,0,0,4000,4100,0,400,2000,100,5100,1500,200,1000,1300,2000,500,3000,4000,0,0,100,4300,1600,12000,1500,1000,4000,0,1350,200,0,500,1400,0,0,1800,10000,100,17000,0,1000,3000,3000,300,3000,150,0,100,5600,100,100,400,2000,0,1000,3000,500,3000,3600,0,400,400,2300,800,2000,2000,800,0,800,12300,1400,1265,0,0,1500,200,0,0,20,1000,1000,0,0,4000,0,100,3000,0,1000,5000,0,800,5000,0,0,0,0,1000,400,800,1800,500,100,300,0,7500,4500,300,2000,7,4500,6000,0,8000,8000,1500,800,0,200,400,2000,0,3000,200,6400,1800,400,500,0,1000,3500,0,1200,200,2000,0,2700,3500,0,3500,8000,5000,2300,2000,30,90,3000,1500,1500,0,6300,0,50,0,1000,0,100,0,4000,0,0,2000,0,2000,3000,400,500,100,1000,800,700,4000,2000,2000,200,0,50,500,0,0,20,300,500,200,0,0,500,0,0,300,0,0,1000,200,0,0,6000,0,3400,0,0,0,800,0,4400,500,300,300,2500,0,15,0,300,100,400,0,500,2000,0,0,0,0,1100,0,0,0,500,0,0,0,100,0,3500,0,10,50,400,0,3500,0,0,0,100,700,5,100,0,0,800,1000,0,3000,20,4500,0,20,150,0,30,400,0,0,100,10,400,0,5500,0,200,50,200,0,0,25,3000,5,0,0,0,0,0,0,3000,400,2000,150,100,2500,700,5,0,100,700,0,0,0,100,30,1500,12000,3000,2500,500,400,0,3000,0,100,1000,10,0,2400,600,1000,50,1000,100,4400,10,0,5500,0,200,200,10000,1500,1000,50,0,7000,20,15,2000,800,0,600,5000,5400,700,800,5,30,10,2800,800,1200,100,1400,4500,10,5500,400,330,4400,10000,1000,50,500,500,2000,0,1600,3500,50,0,1500,100,4000,1200,0,0,0,100,0,0,7000,0,0,0,200,40,200,0,750,1000,50,0,800,25,5300,500,500,0,0,800,2100,5000,1000,0,1500,100,3500,500,3000,1000,0,300,1000,100,1000,150,100,1200,2500,0,0,3000,50,1600,2000,1000,800,3000,300,4000,100,1500,70,0,600,0,10,300,2000,0,1200,3000,0,0,0,2500,0,2000,0,100,500,50,0,1000,1000,150,100,5,1400,800,10,1000,3000,3000,10,6000,200,1000,100,0,0,0,400,0,1200,50,500,300,0,500,1800,0,0,700,9000,0,6000,0,20,0,7000,6000,400,10,8,100,2500,6600,0,0,0,3000,13000,0,100,0,0,50,0,400,0,90,0,10,90,600,0,100,1600,0,0,0,0,500,50,0,1300,100,6000,600,0,2,100,100,50,0,0,20,0,40,0,5,0,4000,0,0,2000,100,500,7000,0,600,1500,600,300,500,0,0,0,1000,0,0,10,30,25,0,200,1500,200,0,0,100,27,1000,0,0,0,0,0,150,0,0,20,0,0,0,0,150,0,1000,0,90,20,300,0,0,0,100,0,10,1500,0,20,0,50,10,1000,1000,300,50,50,30,40,50,500,200,0,5,15,0,0,4900,0,0,0,0,50,0,0,500,1500,0,0,3000,0,0,40,10,50,50,50,50,500,0,30,0,0,3000,200,0,0,300,100,0,0,1000,0,10,500,2000,0,0,0,0,6000,0,1500,50,0,0,0,1400,0,400,0,0,200,300,0,10,0,0,0,0,150,1000,0,0,800,0,200,0,0,500,0,100,0,500,0,640,20,5,0,0,300,0,0,100,1000,0,0,100,0,800,0,0,400,50,0,1000,50,0,300,0,0,250,0,0,0,0,0,0,0,0,2700,0,200,100,400,0,1500,0,0,0,3000,0,1200,0,1000,1100,4,0,200,0,20,0,300,200,6800,0,0,300,0,0,200,2500,0,15,15,0,1000,50,0,0,150,0,2100,1000,10,4000,4200,100,50,0,0,5000,2500,0,0,400,6000,0,150,0,100,100,1000,0,0,3000,0,0,50,20,300,700,100,0,0,200,400,50,300,0,75,100,0,300,0,1500,2000,0,0,50,50,0,0,1400,0,1000,20,0,10,0,300,150,0,0,0,500,3000,100,0,100,0,500,3000,0,0,133,0,500,20,30,300,3000,5000,500,3300,100,0,0,300,15,0,0,0,40,2500,20,0,3600,800,200,500,50,5,4000,900,200,0,0,500,50,1000,7000,50,0,1500,0,20,2500,2000,500,0,200,0,400,0,0,350,200,0,5400,0,0,1500,0,0,400,1500,0,100,2000,700,0,0,50,20,1500,0,300,0,5800,600,800,200,6000,30,0,0,2200,6000,0,0,3000,400,0,500,350,0,75,1200,600,5,3500,1900,1500,5000,2000,0,30,100,1800,50,35,0,0,0,4000,2000,500,0,1000,1300,600,300,1700,2000,1000,2600,1000,500,50,1000,500,7000,0,300,450,800,800,400,0,2000,200,0,1000,4500,1000,1200,15,150,50,500,8000,30,2000,5500,0,4000,520,5000,5000,1000,2500,0,0,300,1700,700,0,0,1300,0,1400,0,2400,10,5000,300,0,200,1600,4000,0,200,400,1600,700,0,2500,1200,1600,100,800,0,10000,0,700,10,200,6000,0,6000,6000,0,2000,2000,1500,4000,1200,0,100,3400,2000,2000,3000,800,0,2000,100,0,600,8000,2700,0,0,50,600,500,300,1000,300,0,50,1000,100,7000,0,1500,0,2800,3000,10,4000,2500,0,50,100,1500,0,1800,0,0,700,300,1000,4000,700,2500,8000,1000,2500,100,400,0,2000,20,200,0,0,0,0,500,0,2600,5000,0,0,7000,0,1000,900,0,800,180,0,0,300,5,0,0,20,300,0,200,75,400,2000,400,250,20,500,0,300,2000,50,0,900,0,1500,400,100,200,0,10,20,300,1200,2000,30,0,1300,0,1000,0,100,2800,0,2800,0,300,0,0,0,200,20,1400,200,0,500,0,0,0,5000,0,0,500,0,0,0,20,0,0,500,500,2000,0,0,800,0,200,150,50,400,20,0,500,2000,300,0,1900,0,700,100,10,50,250,300,500,500,3000,0,0,500,0,50,16500,800,6,0,0,4500,10,50,300,8500,0,800,100,100,100,200,150,0,3000,6000,4000,800,100,4500,1500,4500,50,0,10,0,0,0,1500,0,0,200,50,0,30,2300,200,0,0,20,0,100,1200,500,250,300,0,800,1000,0,1000,1300,1500,50,1400,350,6500,1000,0,3000,5000,700,150,2500,1200,0,2900,3000,300,0,500,700,100,800,75,0,0,8000,2000,4300,100,3400,900,1500,5,2000,0,50,50,100,20,400,4500,1800,0,5500,0,1100,0,1500,10,6000,0,3000,0,3000,100,400,0,1800,1500,100,4000,3000,1700,5500,100,3000,4000,0,1600,3000,50,100,0,0,100,1800,3000,6800,30,50,0,1500,6000,10,0,2200,1800,500,100,1000,30,0,0,100,3000,2000,100,1000,2500,8900,300,5000,150,2500,0,200,0,200,200,0,1800,0,0,5000,500,2000,0,50,5000,0,4000,100,50,700,800,200,6517,0,0,0,100,15,800,4000,5200,5500,1070,3500,0,500,0,7000,50,1500,7,0,700,0,300,0,400,900,500,2500,1500,50,500,3500,1000,1000,500,2500,10000,7500,3000,2000,2500,1500,0,11000,0,0,0,6000,2000,0,800,0,1200,2000,25,7000,2000,100,100,50,1400,5,1500,300,0,300,50,2000,0,0,100,150,3000,7000,7000,0,1500,1200,2000,900,0,0,0,3000,350,2000,200,14000,0,500,1500,50,0,500,7000,10,0,100,800,0,50,0,0,5000,7700,3000,0,0,2000,0,1000,500,6000,0,600,0,0,0,2100,0,400,50,25,20,8000,3000,3400,3000,10,10,300,0,0,800,0,5600,3000,0,50,7200,1500,50,50,9000,3000,200,4000,100,200,100,2500,3700,10,0,3000,3800,500,500,0,1000,1900,0,0,100,1000,0,0,200,0,10,0,100,100,200,0,1000,0,0,2000,200,0,15,400,100,1000,100,15,0,600,0,5,100,2000,10,0,0,0,0,1200,0,0,2500,0,0,1500,2800,20,0,0,0,0,100,0,0,150,50,50,0,0,0,0,6,5,3000,0,0,0,0,50,2,0,0,4000,200,10000,0,200,0,150,0,0,0,100,0,50,0,0,0,0,50,0,50,0,0,0,3500,600,30,0,0,50,0,0,100,500,6,0,400,0,0,100,1400,0,0,0,200,200,0,0,850,0,1500,0,0,0,1500,400,0,20,500,0,100,100,0,2000,1000,0,500,300,0,50,0,300,200,0,10,0,0,0,150,0,50,1000,0,100,6000,0,30,0,0,0,200,10,2400,800,200,0,500,5000,50,350,100,100,0,0,700,0,10,0,0,30,0,0,0,0,150,10,0,0,11000,300,0,20,0,1500,0,0,0,200,10,0,0,200,50,0,0,0,0,50,100,3000,2000,20,0,0,0,0,10,250,75,50,0,0,0,20,6000,100,100,100,0,50,15,0,0,0,0,0,0,500,10500,300,0,500,0,20,0,300,0,0,100,200,20,0,50,100,2,0,0,0,1500,5,100,400,6,0,0,0,100,0,50,0,30,0,300,300,0,12000,100,500,0,12,20,1500,0,0,1500,0,0,0,0,0,5000,150,100,1700,20,0,0,0,900,0,10,0,0,10000,0,0,0,400,75,300,0,50,0,2500,0,0,200,200,0,0,10500,50,0,1000,400,0,4500,200,0,0,200,6,5400,0,150,300,10,30,20,50,600,0,3,0,0,100,50,0,0,0,700,0,0,20,0,100,2000,100,0,0,0,0,0,0,150,150,250,500,0,20,0,0,0,0,0,10,0,0,20,0,0,0,0,300,50,75,10,500,0,0,100,5,6000,500,11000,0,400,0,0,0,2500,0,1000,0,0,0,0,5000,5000,450,100,500,500,0,10000,800,0,35,0,1500,1500,100,50,2200,0,3000,0,7000,0,0,50,100,0,0,300,1000,0,0,0,0,12000,6000,100,0,1000,0,3500,300,300,300,100,3500,200,7500,10,1500,3000,50,100,6500,50,0,50,150,5,100,300,5,0,0,0,200,2000,50,2000,500,1500,5700,0,1500,300,4500,0,100,0,5000,300,800,0,0,1000,1000,20,11000,0,0,400,0,0,2000,3900,9000,0,15,0,0,200,0,7000,2300,4000,0,200,2000,0,10,2000,0,200,700,0,0,0,200,0,15,0,100,50,2000,0,0,2000,6500,100,0,0,100,2200,1200,6000,0,50,8000,3500,300,50,500,0,2000,4000,300,0,1000,0,0,0,0,1000,0,9500,7000,0,20,0,0,800,4000,100,50,0,2500,0,3000,100,3000,2000,0,4500,0,0,250,5000,50,4000,1500,200,5000,0,2500,6000,4000,4500,10,3000,0,10000,300,0,100,1200,500,700,300,50,400,600,1500,3400,200,5,75,300,1500,0,0,500,1300,4000,200,400,1500,3800,0,700,0,30,0,9000,0,0,0,10000,3000,3000,6800,1600,5,4000,400,700,400,250,0,12000,2200,2500,1500,1000,0,10,0,1100,5000,0,500,20,3000,0,4000,4000,500,900,400,300,0,100,0,500,4000,1500,1500,0,300,0,450,3100,1900,500,1000,0,3000,900,2000,75,40,0,2000,5000,0,3000,0,0,2000,300,500,1000,1500,200,0,200,3000,0,0,100,200,0,400,2000,2200,10,0,4500,1500,1000,0,0,100,2700,10,0,0,300,600,800,1500,100,0,400,3700,0,0,1000,0,0,900,500,1200,0,3000,12000,2000,0,3000,1700,2500,2500,1000,0,0,1000,0,1500,1000,1500,0,500,0,2000,2000,500,0,1200,1500,50,0,200,50,3000,0,0,0,10,50,0,150,5,0,2000,4000,0,1200,7500,0,0,1200,200,3000,0,20,0,0,800,800,500,600,1000,20,1000,3000,1000,100,100,1000,25,5500,0,3900,150,0,3500,900,500,0,0,0,1500,10,0,0,400,800,0,2500,6000,0,300,0,200,6000,0,300,10,500,4600,0,0,500,2000,2,20,2000,0,0,4000,400,0,3000,0,7000,100,25,0,100,0,30,50,25,0,400,10,0,2500,50,5,0,100,2,50,800,15,200,0,300,200,0,0,0,300,50,100,150,100,20,0,10,150,0,2000,30,300,20,1700,2500,0,0,2000,0,1500,0,0,300,4300,0,100,1500,500,15,0,10,300,0,1300,0,0,150,0,500,0,300,1000,0,50,800,30,1000,2000,1000,200,350,5,250,500,2500,200,1500,50,0,25,5,0,150,10,800,0,1200,50,1500,13,0,50,400,0,0,100,50,0,0,0,1500,500,400,2000,0,100,300,0,10,150,300,0,1000,60,6000,50,200,0,400,0,7000,700,0,150,2100,0,0,10,5,200,350,1200,1000,2000,800,300,700,2000,4000,200,0,3000,200,150,10,3,700,500,800,6000,800,8000,1500,400,200,0,150,10,900,0,75,1200,0,10,0,1500,1000,0,0,1000,300,800,3500,0,700,0,1500,3000,0,10,0,0,0,2400,20,0,400,20,100,10,0,10,0,50,0,500,1000,1700,300,0,0,700,3000,20,3000,1600,130,0,3000,15,2500,600,1200,2,600,700,75,300,5200,5000,10,200,800,300,150,300,200,50,500,1700,250,1000,0,5,5000,6000,1600,5,500,0,0,200,2000,8000,0,0,100,0,0,0,2800,5000,3000,0,25,50,25,1700,0,0,0,500,2000,0,200,800,7600,0,30,0,2000,2200,2000,0,600,150,25,50,3100,8500,1500,5000,3000,0,300,6000,50,100,2500,3000,0,50,500,200,5,1200,3000,50,10000,0,600,100,1000,0,0,800,2500,400,0,0,3000,0,0,5800,1500,1500,800,100,10,5500,1300,0,500,400,500,0,0,0,0,1600,1000,0,500,4000,0,10,9000,0,11000,0,200,500,5000,1700,100,0,2500,0,100,3000,1200,0,900,20,100,0,0,100,0,800,100,0,4000,2000,300,0,50,400,0,0,1100,20,1000,0,0,0,300,10,0,300,10,12000,100,4000,0,0,0,10,0,0,0,0,0,0,0,1000,20,100,2,0,10,0,1500,0,0,300,5,0,0,500,0,90,125,6,600,0,0,5,200,100,10,0,0,3000,0,2000,0,15,15,0,0,100,0,100,10,130,1500,0,20,0,5,0,0,50,500,0,0,5,0,1500,2300,100,0,500,10,0,1000,75,400,4,40,1800,0,0,0,0,0,0,0,2500,1000,0,500,200,200,0,0,0,100,30,400,200,0,0,0,100,0,0,10,0,0,20,0,0,0,0,0,50,0,0,150,100,0,0,0,0,0,0,0,0,0,0,100,400,1000,0,0,3000,0,500,0,0,200,0,0,0,300,1000,0,10,0,0,0,50,15,5500,0,10,0,50,0,50,0,0,0,0,400,5,0,0,0,0,0,0,60,3000,0,2,0,40,200,200,100,200,50,10,100,0,0,0,1400,0,5,0,0,150,100,0,0,0,400,2000,50,500,0,50,500,20,0,1500,15000,0,0,5,40,400,75,10,0,0,0,0,0,300,0,0,0,0,0,5,300,0,20,0,0,0,0,0,0,800,5,0,0,0,50,10,0,10,25,400,500,0,200,0,20,10,0,500,50,50,0,0,1000,0,800,0,1000,4000,100,0,300,0,0,0,0,0,0,500,50,200,0,0,0,0,0,200,1800,50,200,0,0,1500,380,1100,50,5000,1500,600,1200,0,2500,50,1600,100,150,10,200,900,0,0,3000,300,800,600,400,50,0,0,0,0,0,0,200,100,1000,0,0,500,200,500,15,0,50,100,0,10,0,200,10,20,0,0,0,3400,0,100,100,50,250,250,3000,2000,2000,200,0,0,10,100,0,0,1000,0,800,0,0,0,2000,0,3,50,4000,0,75,0,100,75,120,2000,0,500,2000,400,0,0,100,50,0,10,150,800,0,1700,5000,11000,0,0,0,5,10,2000,2000,0,0,10,2500,0,0,4000,8000,0,300,300,3000,3000,0,5000,1500,1000,13000,0,0,0,50,1000,4500,500,0,0,0,200,1700,200,10,0,4000,100,0,2000,2500,0,300,20,1000,200,1500,0,4500,50,0,0,400,0,1000,300,3100,300,2000,10,0,0,500,0,20,0,0,1200,1000,0,1500,1500,100,4000,1850,2200,0,0,0,2500,0,1500,2200,300,1000,1000,13000,2200,0,3000,0,1500,700,600,6500,0,0,3500,1500,0,0,1600,400,0,6500,0,14000,600,2000,2100,750,0,800,200,0,3,0,200,1000,0,5000,5000,50,300,300,0,20,300,1500,0,0,0,1700,500,0,2300,3000,5000,1500,13000,2300,200,0,0,800,4000,1400,4000,800,6000,20,0,300,0,0,1000,3000,500,20,4000,700,4000,1500,1400,2500,2000,0,500,30,0,545,500,0,400,100,0,0,1000,3500,200,4000,5000,5000,5000,2700,1100,10,4000,1700,5000,2500,50,0,0,0,50,0,1500,800,2,1000,1500,500,0,0,0,800,0,20,0,10,600,0,5500,400,0,100,2000,1800,600,50,350,250,5000,1300,300,1600,1500,1000,3000,2000,0,400,0,1600,200,500,1000,600,0,3700,300,0,0,3000,3700,1300,100,2800,0,0,0,600,0,800,200,1050,3000,100,0,7000,3000,2000,0,800,0,2300,0,2000,6400,0,6000,1500,6000,0,200,4900,0,1200,1000,300,0,100,2500,800,300,1850,800,150,1000,1000,5000,4000,3000,50,1000,11000,25,0,0,0,0,10,4000,0,2000,0,0,3000,50,300,100,400,0,20,200,800,3000,0,50,150,1500,4000,0,300,0,4000,0,0,0,0,0,50,0,0,700,0,700,0,2600,5,2000,300,0,2,1500,2000,0,0,1500,100,2000,10,2100,100,0,1800,0,800,1900,4,200,0,50,0,400,2000,600,0,1200,800,500,5000,0,100,300,0,10,4000,800,0,2000,0,0,0,450,3000,0,3000,2000,5000,6500,0,100,25,0,0,0,3,5000,200,0,10,95,500,0,400,0,4000,2000,0,1000,0,100,500,600,250,2000,500,0,20,1500,0,500,3500,2000,100,50,100,0,300,0,0,10,600,70,25,0,0,3000,800,0,10,0,1400,200,0,500,2400,500,5000,50,0,600,2800,0,0,0,0,800,0,0,150,0,1500,0,4000,0,50,15,0,800,20,0,0,100,0,200,0,0,0,500,0,50,700,0,30,0,400,0,500,20,0,0,0,0,0,300,1900,50,0,350,0,0,100,150,2000,0,20,200,200,0,1000,300,100,50,0,350,600,50,100,100,300,0,0,1500,100,0,0,0,300,0,500,300,0,1300,0,10,0,5,0,75,500,0,500,4500,6000,100,200,0,0,10,500,100,0,0,0,400,100,11000,300,50,1000,0,0,0,0,0,0,300,500,500,400,1500,500,50,3000,0,0,400,10,0,0,300,100,3500,0,0,0,500,800,300,1200,5,100,40,2000,500,700,50,500,6000,0,50,4000,0,0,1000,50,100,0,0,0,450,0,0,15,500,0,8000,25,1200,2000,0,0,2000,1000,500,0,10000,0,5000,0,5,10,0,25,3000,0,1000,4000,200,800,200,0,3000,5500,0,0,0,1500,5500,300,100,6000,1500,500,0,4000,1700,20,0,15,6000,200,10,50,1000,2500,0,6000,0,800,1700,1500,2000,1700,0,0,0,600,1500,3500,15,800,1000,0,300,2000,3500,5,1500,1000,6000,400,0,900,1600,0,0,100,200,4500,0,0,1600,400,50,2500,400,5000,500,200,4400,10,1600,150,0,0,10000,0,0,0,20,250,400,20,0,200,800,200,0,0,0,30,200,1900,1000,500,50,700,0,60,1100,50,0,300,100,2600,3000,5000,700,0,600,1200,2000,1000,5000,0,0,1000,400,500,0,0,0,30,0,10,300,1500,0,0,50,0,0,10,100,50,0,0,800,10,100,0,0,3500,4000,10,30,175,0,0,1000,0,0,1000,0,200,800,2000,0,4500,20,0,0,0,0,0,0,150,80,200,600,1000,100,0,20,4700,25,0,0,30,200,200,100,1000,4300,100,0,500,200,0,0,0,0,500,200,0,20,200,1600,50,0,0,10,500,400,800,50,0,0,15,2000,0,2400,30,50,0,200,0,0,0,0,800,0,10,0,0,0,100,400,450,500,0,0,500,0,0,1500,0,0,0,0,0,50,200,5,0,0,500,0,0,23,15,0,300,0,0,1000,0,200,100,0,300,0,500,500,5000,20,1500,1000,0,50,0,100,0,1000,200,100,6500,1000,1000,0,0,25,200,150,60,900,4,0,0,0,400,5500,50,20,200,2200,800,300,1000,100,0,1400,3500,0,0,0,0,0,5,0,0,100,0,0,0,0,0,0,500,0,0,0,100,50,0,50,0,100,0,0,1000,0,0,0,0,800,0,0,1000,5,30,0,0,20,0,0,0,0,0,300,6000,0,0,800,0,0,0,200,0,100,0,500,0,2,300,0,0,10,0,0,200,50,1,0,50,8,50,20,400,0,50,100,0,0,20,0,0,0,10,100,20,100,0,1000,50,0,0,0,500,75,0,0,0,25,0,0,0,0,10,500,3000,0,200,0,100,0,20,500,0,0,0,20,13000,0,0,0,0,0,0,0,50,0,0,5,500,0,0,1500,0,10,0,100,500,0,5,0,200,0,0,0,20,150,0,800,0,0,75,100,0,0,0,0,150,0,2800,6000,300,15,50,0,0,50,0,0,600,0,3000,0,0,0,0,0,300,0,80,0,100,0,0,0,1200,0,0,0,100,50,100,0,0,100,800,0,50,4000,0,120,0,4000,20,0,15,0,0,0,25,0,800,2000,30,3500,180,50,500,300,0,3000,0,0,400,0,2500,600,20,200,0,0,30,30,4700,1500,100,0,0,2,3000,4900,0,0,5700,2500,2500,200,400,0,200,27,500,5000,100,150,0,0,800,0,10,10,500,0,0,100,100,0,200,0,500,0,0,1000,0,1000,0,0,0,0,200,200,900,20,100,0,400,400,0,0,150,1000,100,0,0,0,0,100,1000,200,0,500,0,0,50,0,0,0,0,0,200,0,50,0,0,3000,300,0,500,20,100,500,7000,10,30,600,0,0,0,9000,0,0,1500,50,10,1000,10,3500,400,0,0,0,6000,50,0,500,0,400,20,200,600,0,100,50,0,0,0,0,200,20,50,4000,750,50,0,0,50,0,0,0,4000,100,2000,300,700,0,0,200,2000,0,1100,1200,0,10,0,0,1500,800,5000,8000,1500,10,0,2000,10,10,300,0,50,0,0,800,100,0,0,0,0,1200,200,3500,500,0,0,0,50,10,500,0,3000,100,400,0,0,0,0,700,2500,200,0,200,1100,0,0,0,300,350,1000,5000,4000,3000,40,500,800,4000,3000,0,0,0,3000,1700,20,800,1000,500,1800,0,5,20,600,8600,10,0,300,1500,800,6000,0,0,0,10,0,50,800,0,0,800,10,400,1000,0,50,600,0,2000,0,100,1500,3000,700,150,6000,0,0,2000,1500,4000,800,100,0,400,2800,300,250,10,20,1800,1300,0,0,0,1600,10,0,100,0,10,100,700,200,4000,1000,400,0,0,0,0,0,300,5500,0,30,10,10,200,10000,300,1000,25,100,500,10,0,0,7000,0,0,500,0,10,700,0,10,15,200,0,1500,1,0,0,1400,1600,1500,10,3000,350,2000,200,0,3100,2000,0,20,0,200,0,0,0,500,400,5000,3000,2000,7,100,2000,300,0,100,0,6000,2500,300,1500,0,300,1300,1500,1000,75,0,900,50,4000,2500,500,1600,0,400,0,0,20,700,0,0,100,300,3600,0,2000,0,5,800,100,2900,1500,500,0,200,4800,4000,0,6000,200,500,0,300,3000,30,2000,1000,500,8500,600,200,400,2600,1800,0,3000,0,4000,5000,4000,1800,500,0,10,50,0,0,0,50,10,0,1300,800,90,0,500,5000,4000,1500,0,30,1300,30,0,20,2000,1100,800,1000,100,200,7000,10,300,1200,1700,2500,0,0,4700,3500,1500,200,0,700,700,1500,4500,14000,4000,400,0,200,300,1000,6000,4500,0,0,6000,4500,2500,0,10000,100,2500,1000,4200,2400,100,0,0,4000,0,150,0,1500,400,0,0,10,9500,100,100,0,20,150,1000,3000,200,500,3850,200,700,1000,1800,600,3300,1000,3000,0,8000,4300,3000,0,200,0,2000,2500,1500,30,0,0,500,0,0,1650,20,0,8000,2500,1000,0,1600,50,600,0,100,50,0,8500,0,800,15,25,500,1800,1000,150,3000,1260,10,1000,10000,300,200,0,10,0,100,300,2000,100,0,0,10,5,0,1500,10000,50,0,0,0,5,300,0,800,1,0,1700,2500,1000,3600,0,2400,3400,0,4100,600,5500,500,300,10,0,600,0,0,1700,0,0,200,200,0,10,1200,100,0,0,4000,0,500,200,0,0,1500,0,500,750,200,1000,0,0,30,300,20,100,100,0,7000,100,800,0,400,160,10,0,150,0,0,20,0,0,0,1850,2000,5,0,0,0,2800,1500,600,0,700,100,0,3400,1000,100,0,1000,400,2000,2000,75,0,0,0,100,100,0,200,5000,550,0,0,50,1200,0,0,2500,0,90,20,0,75,40,0,400,50,40,50,0,400,0,150,10,100,0,600,100,6000,50,0,100,1000,50,0,0,0,0,50,0,15,0,0,150,150,0,500,1000,500,800,0,1000,50,0,5,0,0,100,5500,15,50,2200,0,1500,0,150,5000,5000,10,6000,0,4000,10,0,0,10,500,0,200,0,0,0,100,1600,1000,2000,0,2000,0,50,300,500,3000,0,0,460,1300,1000,0,900,400,2400,1500,200,0,3000,0,450,6500,0,2000,300,0,50,200,1300,10,1000,0,0,100,0,1500,0,100,600,10,5000,7000,200,500,10,4000,0,6400,0,0,0,0,0,0,3000,0,0,600,0,6000,1500,1000,1500,55,0,2,5,0,30,0,0,1500,30,0,0,0,2000,7000,0,7500,0,0,2000,500,3200,0,500,0,1000,1200,0,8000,0,5000,1000,300,0,0,600,200,2000,0,0,200,200,3000,0,3500,400,0,275,500,1000,0,800,2000,3000,0,5,2000,0,100,0,0,0,4000,1500,1100,10,500,0,1100,3000,4300,0,0,0,100,100,0,70,8000,0,2000,3000,0,300,5000,100,900,2500,1000,20,0,100,2000,1000,70,0,2500,1000,300,2000,1700,2500,500,1500,10,0,700,1000,1000,0,2000,2000,50,0,20,500,600,30,0,3000,1500,50,7500,2500,3000,0,200,500,0,0,500,0,50,7000,1500,10,0,3000,2300,0,30,900,20,300,2000,4000,150,300,1000,2000,2000,2700,300,0,0,30,8500,2000,7000,0,2000,200,10,1800,5000,0,800,5,500,400,100,0,3000,50,50,10,10000,6500,0,2500,2500,0,50,0,2500,2000,300,0,0,2500,75,50,3500,20,0,1500,200,200,0,4000,0,0,0,0,50,10,2000,10,0,0,0,900,1200,25,400,900,1000,300,800,800,100,5000,10,0,400,0,0,0,50,100,0,0,0,10,200,75,3500,0,500,0,0,10,2000,500,100,0,500,4500,1500,50,400,0,0,200,0,400,0,9500,0,0,400,1000,0,0,5,100,50,0,0,1000,0,0,350,50,15,150,50,0,500,50,0,0,800,1500,0,0,100,400,100,0,2,200,50,0,20,0,0,50,0,0,0,1500,0,10,15,0,10,0,300,0,50,500,0,1000,0,50,500,0,0,300,100,100,1500,500,1500,20,400,30,50,2500,0,0,0,2400,10,30,200,0,25,0,500,0,200,0,350,4500,400,300,1000,2500,0,0,1000,0,0,1000,0,80,300,10,0,100,0,200,8,0,30,10,800,1000,0,0,0,350,20,0,20,0,0,0,500,0,0,0,10000,1000,10,50,0,0,0,5,200,10,0,0,1000,2200,0,10,5,0,0,1000,0,800,0,0,0,20,0,0,0,200,0,200,0,20,250,50,20,300,0,0,0,0,50,0,100,0,0,1500,75,0,0,40,10,200,0,50,0,100,10,70,200,0,0,10,30,0,200,5,0,10,50,150,0,0,0,2000,10,0,0,25,40,50,0,5400,0,200,0,10000,50,0,0,0,0,400,0,5,0,6000,0,100,1000,0,100,0,0,10,300,0,0,100,100,20,200,1200,0,0,0,600,0,0,300,3000,0,0,800,800,0,10,50,3000,100,50,50,0,0,0,5,0,150,6000,0,20,0,0,0,0,16500,0,50,600,0,300,1500,20,200,0,200,0,0,0,500,0,0,0,200,3000,50,6500,50,500,0,500,10,1200,800,0,0,10,0,4000,0,0,100,0,40,0,50,50,75,0,25,200,0,0,0,0,0,0,10,0,50,2500,0,10,0,0,4000,0,5500,50,0,0,50,0,0,0,0,0,2000,600,100,25,200,1500,0,50,0,0,50,1500,0,4850,0,40,500,0,0,100,0,50,10,10,0,30,3,2500,800,0,0,250,50,0,25,200,75,4500,0,0,125,7000,200,20,300,50,0,0,0,200,2500,0,1600,8000,10000,30,600,0,0,0,11000,2,0,10,0,0,0,0,0,4500,0,0,0,20,0,0,125,1500,0,100,3000,200,0,3000,150,1200,4000,20,1800,100,100,0,10,600,30,100,35,1,0,20,800,0,250,0,0,300,5000,1200,50,500,0,500,0,7000,2000,0,2000,1000,7000,2,100,50,2500,1300,0,100,0,3000,3000,300,2500,3000,600,100,3000,11000,50,3500,0,2000,5500,2500,2000,0,0,400,0,700,0,0,0,700,6000,0,100,0,0,0,5000,0,500,100,0,2,0,200,0,0,12000,0,50,3500,0,0,100,0,300,100,0,0,800,1200,5,20,0,10000,200,150,0,3000,0,20,0,1700,6000,30,0,2500,0,250,200,4000,4500,0,5,50,7250,0,0,0,4500,2000,9000,0,0,50,200,3000,50,0,8500,15,100,0,6000,4200,600,1500,4500,0,0,10,0,600,5000,2300,3500,0,0,1000,100,200,0,1200,7000,200,5000,4000,0,100,7000,200,2000,3000,0,0,20,1000,1200,400,0,0,200,1000,150,0,0,900,5000,0,0,800,7000,500,10000,420,6000,200,30,6000,0,9000,400,50,0,1500,10,1000,1000,700,0,1500,500,0,1000,15,3000,0,10000,0,1000,250,10000,0,1700,0,2000,1500,0,400,200,150,700,50,50,3500,0,2000,0,0,100,10,1000,3000,3000,1000,1000,400,50,0,1000,8000,0,200,0,0,4000,15000,1500,3000,6000,0,7000,1500,500,1000,0,4300,0,1000,300,1000,1100,8,0,6100,1000,200,100,100,50,500,20,2000,2300,2700,500,2400,2400,0,2500,1900,500,5000,3000,0,800,4000,0,4000,2500,1200,1,0,650,0,1000,0,0,1400,2000,1000,0,12000,1500,0,0,500,100,800,2000,1500,2500,5,200,0,200,3000,1500,4000,0,0,0,300,100,800,400,0,1200,500,2000,2000,200,0,2300,300,100,500,0,1000,5,0,5000,4500,9000,2000,1000,1300,0,3000,5000,50,20,0,0,4000,100,1500,400,200,2500,5,0,100,500,1200,20,1800,0,500,7500,750,0,2500,0,8000,0,5,300,4000,150,1000,2000,200,34,100,3000,2000,2000,4000,4000,0,1700,9000,1000,3000,1000,2100,100,0,4000,2000,0,0,0,0,700,0,2400,1500,20,6000,100,0,0,0,7000,5000,150,1300,6000,5000,1200,100,0,2500,100,6000,2200,0,500,50,200,0,5000,1500,5000,6000,500,1500,50,4000,0,600,5000,4000,800,100,0,6000,3000,10,0,2000,50,74,60,800,0,0,0,1400,0,50,0,900,600,300,2000,0,2000,10,1000,10,500,2300,6400,1500,300,0,40,1000,0,1200,0,30,500,1000,500,300,600,3300,8000,4500,300,5,0,50,400,1000,500,4000,400,1500,1500,0,300,1600,5,0,50,0,100,0,400,0,0,0,2000,0,200,100,0,0,1000,0,20,0,500,0,0,600,0,200,20,50,0,10,0,300,0,2000,0,0,600,500,0,0,0,1000,30,0,0,500,500,25,25,0,1500,800,900,0,5,0,10,0,0,1000,5,400,0,400,0,200,200,0,0,150,0,0,2500,0,0,600,350,0,0,50,10,50,0,0,800,400,400,100,0,1400,0,0,200,0,0,1500,750,10,0,0,1000,400,200,0,0,150,0,150,0,0,1500,50,100,1200,820,5000,0,0,1000,0,0,0,100,0,0,0,0,0,0,1500,0,0,0,500,10,5,2000,20,0,40,20,200,0,0,150,1500,300,0,0,3,1000,0,0,0,100,0,20,30,1000,10,1500,200,0,100,50,1000,200,300,0,0,0,10,900,1000,400,10,1000,1500,0,15,20,300,0,900,300,0,0,100,0,0,0,0,300,200,100,800,0,1000,0,0,100,200,0,10,150,300,1500,400,200,0,3000,100,1000,50,250,0,600,1500,50,3000,900,50,30,3000,1700,800,0,200,0,10,0,100,3000,1000,500,50,0,2000,2000,1000,20,2000,10,900,4800,3000,100,0,0,1750,0,0,10,0,3000,200,0,0,100,15000,0,300,0,5100,700,50,6000,6000,20,0,300,100,0,500,100,1500,500,2500,0,1000,0,0,700,0,40,40,1500,3000,200,5000,0,1000,300,2000,1500,100,50,200,900,500,1000,0,560,0,0,3000,3000,30,0,0,100,800,0,0,50,2000,200,3000,0,0,50,0,0,800,2500,0,40,500,0,1500,40,3000,350,4200,850,1000,2700,1750,3000,0,0,0,2000,0,400,200,200,0,7000,300,2500,200,0,0,0,0,0,2200,1500,50,10000,50,0,1000,50,50,10,0,20,4000,6600,600,0,3000,0,30,0,200,4500,500,4000,5000,0,3000,2000,0,25,600,7000,1000,1,1350,3550,1500,50,0,10,800,3700,50,0,0,300,0,800,500,1700,1300,0,500,1000,300,1300,1500,0,500,0,100,0,10400,300,2500,50,0,2500,1700,1500,0,0,10000,1200,1500,1500,1300,2000,7000,50,1500,50,5600,2000,50,7200,800,3000,10000,0,4000,3000,5000,10,0,800,0,0,0,0,0,20,800,15,0,2000,1600,3600,2000,100,50,0,0,60,800,4000,3000,500,450,1800,9000,2500,1000,1000,1400,0,500,600,700,1000,0,1200,3000,0,10,100,1000,1000,6000,30,11000,0,500,0,0,0,5000,0,3000,20,4000,2800,0,100,900,500,100,200,400,20,2000,50,7000,0,50,400,0,35,10000,10,4000,0,300,7000,10,100,8,50,1500,0,300,500,3300,0,0,4000,50,400,380,400,1400,5000,0,0,60,2400,6800,0,0,0,4500,50,20,50,4000,3,800,0,0,0,100,0,50,0,0,0,100,1000,4000,3800,3500,0,10,0,200,0,0,4500,300,0,0,10000,0,0,400,0,100,0,0,200,50,3900,50,0,100,2500,0,0,50,3000,0,100,30,5,10,200,0,100,6000,0,0,1500,600,0,0,1000,0,10,2500,75,0,5,0,50,150,100,25,0,1200,250,200,300,0,100,50,0,25,1200,1900,600,0,1000,6500,50,20,2,200,50,0,2000,200,100,600,0,0,0,50,100,50,800,500,1500,0,200,0,0,15,0,0,5000,10,500,0,0,0,600,0,0,1100,50,0,20,100,200,200,300,500,0,300,50,50,300,150,0,0,0,2500,75,200,0,0,150,0,200,0,2000,0,0,4500,0,0,0,12000,0,1500,20,100,10,0,300,0,0,10,20,20,6000,0,200,100,15,0,0,0,0,0,40,0,50,0,0,1000,100,0,20,0,0,0,3000,2000,20,10,2400,0,0,0,0,0,0,150,0,0,0,10,50,0,0,50,0,0,0,0,0,0,0,1000,0,0,15,100,0,0,0,5,5,0,20,0,10,0,10,0,0,200,0,0,600,0,9500,2000,0,0,500,0,0,1400,0,0,0,0,0,0,0,0,0,20,5,5,0,0,0,0,10,10,200,50,100,200,30,0,10,0,0,600,0,10,0,0,0,300,0,10,500,0,0,0,0,20,0,0,3000,0,0,0,0,0,500,1400,500,0,25,0,10,0,200,500,350,0,800,20,0,50,50,0,0,50,500,40,0,1000,0,0,100,150,0,0,0,0,0,100,0,0,0,50,0,20,100,0,0,1200,150,30,200,300,60,0,500,10,0,0,11400,0,0,50,0,1000,0,300,30,50,0,0,0,0,0,0,10,0,50,800,0,50,0,0,0,0,0,500,0,5000,100,3000,100,200,0,500,700,50,0,20,7500,0,900,0,0,0,5,0,0,30,1500,0,200,0,0,0,0,10,0,600,0,0,0,5500,50,0,0,0,0,0,5,0,0,0,0,10,0,0,3000,0,8,0,0,0,0,800,100,0,0,0,0,0,13,250,100,0,0,1800,10,0,0,9000,150,300,0,0,1300,300,150,1500,200,0,0,35,0,100,125,50,500,80,2500,250,0,100,0,0,20,15,0,20,1000,30,0,50,0,3000,20,0,800,0,25,1200,800,0,0,0,0,0,0,0,0,1500,500,5,100,0,50,0,50,800,20,500,0,0,0,5,500,150,0,100,50,600,0,20,0,2400,5000,0,0,0,0,20,7000,0,0,0,0,0,0,0,0,2500,100,0,500,0,50,300,100,1000,0,300,700,0,1900,0,10000,25,200,0,100,0,50,0,500,50,0,0,0,1000,2400,10,1000,2000,0,0,0,200,500,1000,10,0,0,0,0,0,100,20,0,0,30,0,100,0,0,0,1500,0,100,25,1500,0,100,100,0,2000,0,25,200,0,2448,0,2500,3500,150,6100,0,0,300,0,3000,0,0,0,0,50,0,0,0,200,0,3000,0,0,0,300,800,50,200,800,50,10,400,0,100,0,0,1500,0,15,850,1100,25,0,300,0,6000,0,100,5,20,10,50,1000,0,500,50,0,800,900,3500,700,3800,0,3000,0,300,0,600,2130,0,7000,50,0,200,150,500,0,20,1000,0,0,0,800,15,0,0,2500,200,0,0,15,3500,1000,0,0,50,500,10,0,1000,100,1500,1000,4300,50,0,5000,1980,10,200,0,0,8700,5,1000,0,0,1800,4000,2800,4000,500,400,15,300,500,800,500,1500,2500,1500,2500,1200,0,2500,500,1500,2200,2700,0,0,0,20,3500,300,800,65,2000,4500,0,0,10,900,75,700,0,9000,4000,1500,0,350,3400,800,400,500,3000,1000,4000,3300,2200,0,3300,3000,0,1000,50,50,0,10,2000,1700,1500,400,100,50,0,100,100,15,0,2000,10,500,15,50,150,0,0,50,200,0,300,0,1500,0,75,10,0,0,1800,2200,0,300,9500,0,500,1000,500,3000,0,0,5500,1350,4000,2500,1500,2000,4500,0,9000,270,500,300,900,2500,0,5,0,350,200,700,1500,8000,2100,260,300,1000,1000,5400,0,350,1000,2500,2000,1500,50,0,30,1000,1000,400,300,1000,2000,3000,0,200,450,8000,4000,1200,1200,10,4000,0,400,10,0,7200,0,1000,0,0,0,0,2000,200,0,800,0,0,200,800,2500,3300,3300,700,0,800,0,900,6200,5500,3300,0,0,1500,200,4500,1000,1000,400,4000,5000,1500,200,700,300,7500,2000,500,2500,0,0,400,50,500,50,1000,50,100,7000,50,3000,3740,2530,100,1000,0,1200,6500,6000,30,1000,1000,0,3,500,100,2600,1540,1500,100,2000,200,0,3400,5000,3000,10,400,0,3700,50,0,100,3000,0,1500,4000,6000,0,700,700,300,7500,0,2200,0,3000,400,100,0,800,500,0,4000,8000,1000,0,30,900,3,0,0,50,0,500,15,2000,0,450,7000,1500,0,200,0,1000,13000,5000,0,500,8,0,300,900,400,500,500,900,7000,2200,1200,0,0,4000,1900,2000,0,150,0,30,0,1000,500,1900,25,250,0,4000,500,900,3000,2500,8000,0,1500,0,4000,0,200,0,1000,3000,0,0,0,500,150,400,150,700,4000,4500,50,800,1000,200,0,5500,1800,50,6000,300,900,2000,3000,0,4000,2200,5000,0,100,1200,10,3000,2850,0,0,100,2000,4000,0,0,400,200,700,0,50,0,100,50,5000,1000,0,25,0,100,14,50,5500,0,0,100,1000,7100,600,1000,500,1200,50,0,500,200,2300,1000,100,0,0,200,3000,250,500,10000,0,20,300,0,4000,0,100,2000,100,75,2000,0,1000,300,500,3000,0,500,3000,2000,1500,0,5000,3000,3000,0,50,20,2000,2000,200,200,2000,0,0,200,3000,3800,0,0,0,500,0,0,10,250,200,30,50,500,70,10,600,0,0,300,300,0,2000,50,350,12000,0,6000,300,0,3500,0,0,2000,1000,650,200,0,0,0,20,1200,200,0,700,0,500,100,8000,2700,0,100,0,0,0,3000,0,700,1500,200,0,30,300,50,0,100,300,1200,200,0,1000,0,5,0,0,0,0,0,0,3000,200,0,0,0,200,0,0,10,30,520,1000,2000,0,100,0,15,1000,25,100,0,0,0,0,75,0,50,0,0,0,0,0,700,0,400,0,100,0,0,50,10,800,1000,200,1200,0,300,1300,0,0,50,0,500,50,30,400,50,75,50,40,100,50,0,0,100,0,0,10,200,0,100,3000,300,0,10,50,0,0,200,0,0,0,0,15,10,0,0,200,0,50,0,100,0,0,100,100,50,0,3000,2000,0,250,100,200,0,0,400,10,0,100,0,0,500,200,1500,0,0,2000,0,500,3000,1000,0,200,100,100,9500,6000,2500,0,1000,0,800,0,1000,0,200,800,100,3000,0,300,100,50,4100,7000,50,4000,0,1000,0,5000,0,0,8000,2200,1400,2800,2000,2000,6000,10,100,5,100,0,16000,10,5500,5,300,1000,0,3000,0,3000,0,10,0,2000,0,0,75,6000,5,10,0,6800,4000,0,2000,10,0,0,3000,440,1200,4000,4000,100,100,0,1000,1000,150,100,0,600,0,0,0,10,7500,50,0,1000,0,1500,0,0,500,2700,0,1500,400,1000,0,0,7000,3000,750,0,100,2000,0,0,0,0,0,1000,200,0,200,50,5,500,5000,0,0,300,0,0,500,500,0,0,100,20,0,50,30,300,1200,0,500,0,3000,0,30,700,0,4300,2000,6500,1500,2000,800,10,250,1800,14000,1000,20,200,25,200,0,0,0,3000,200,200,25,0,75,500,0,400,6000,3000,0,400,400,7500,5400,0,0,150,3300,5000,6000,50,300,50,5,3000,20,0,40,0,500,25,0,2500,4500,2000,3000,300,0,2000,2600,1400,0,500,6700,200,500,25,50,0,100,1400,0,0,0,20,0,4300,200,0,1000,400,3100,3000,500,400,4000,1800,400,0,500,100,0,1200,2000,0,3500,3700,200,50,4000,2500,10,200,10,3000,2500,4000,0,3000,400,2000,600,2000,10000,2000,3500,3000,50,500,4000,1500,3200,4500,1500,0,4400,4500,0,10,3800,1700,1200,3000,5000,2100,1000,10,0,0,0,6000,3000,2500,0,500,0,3000,0,1800,2500,0,3000,0,20,50,5200,2500,8000,3100,5000,5500,3500,4500,3000,1300,100,800,900,150,500,0,1300,2000,400,0,20,20,150,3000,4300,2500,0,25,0,400,4100,1500,150,0,0,0,50,1000,2200,500,0,100,0,0,100,50,0,500,8000,10,0,1800,5000,700,100,100,50,2300,2000,2800,2000,0,300,0,1400,2500,0,10,0,200,300,0,11000,100,0,0,300,50,1000,0,800,3000,0,8000,2000,1500,1800,0,30,0,100,7000,0,50,0,100,6500,2000,400,0,800,200,0,50,50,0,400,1800,0,0,10,50,0,1000,4000,0,0,0,200,1800,0,5000,0,10,10,100,800,4000,100,0,2000,3000,400,0,200,5,0,1000,2000,50,450,2000,0,0,2500,3600,0,0,1000,0,30,10,10000,0,500,50,10,900,0,0,0,150,100,3000,700,15,0,300,500,0,500,0,0,7500,6000,0,25,5,1000,0,300,0,0,15,25,50,0,0,0,0,0,0,10,10,10,0,0,0,20,0,5,0,0,0,100,0,0,0,10,100,2500,0,1600,400,50,1450,0,50,2500,100,4000,0,200,500,100,300,0,8000,3500,3000,0,100,0,1200,0,800,0,4240,190,0,2600,0,0,1500,0,0,200,30,400,0,5,0,0,4000,200,100,0,50,0,500,0,50,400,5,0,10,5,0,10,0,1200,0,0,0,400,0,1000,0,100,0,10,100,0,100,300,700,0,14400,300,0,0,0,0,0,0,0,100,1000,0,0,50,0,0,0,30,0,20,25,300,50,0,0,0,0,300,1500,0,0,1000,0,0,300,0,0,0,0,0,500,0,10,200,0,0,50,50,3000,0,400,1000,0,0,800,0,0,0,500,100,5,0,0,500,100,0,10,50,0,650,0,0,0,0,50,0,0,100,100,100,300,300,0,3000,50,0,0,0,100,0,0,0,0,0,0,0,0,15,0,500,0,0,0,0,0,30,0,50,50,0,50,90,50,500,50,0,0,1500,50,10,50,0,0,0,0,0,1500,0,0,0,100,11000,0,0,0,0,0,0,20,400,1600,10,0,0,300,0,1500,30,0,20,0,2700,800,0,1750,0,0,0,0,0,0,0,500,0,500,60,0,0,50,0,100,0,0,0,0,30,10,2,0,0,10,0,0,20,10,0,0,10,0,10,100,450,0,0,0,2500,200,1500,0,100,0,500,0,0,0,0,0,10,50,0,0,0,2000,0,0,1500,0,150,300,8,30,10,25,0,15,50,300,150,100,500,0,0,50,0,0,0,500,50,0,600,300,1000,0,50,0,0,0,0,0,800,0,0,4000,0,100,200,0,0,0,0,15,0,0,0,0,100,10,0,10,0,0,2000,0,100,0,300,400,0,1000,0,500,100,550,0,0,100,0,600,100,0,0,350,0,0,100,0,5,0,100,700,300,450,500,8800,5,400,0,0,0,0,0,0,100,200,0,0,0,0,1000,15,10,0,50,0,30,2000,12000,0,5,0,170,3500,0,0,0,0,50,3500,5000,0,0,1800,583,0,0,0,0,0,0,50,300,0,0,3400,0,0,10500,250,0,50,200,200,90,7600,1000,50,20,2000,50,0,0,200,0,50,13400,100,10,0,0,100,0,0,20,0,0,0,8000,3000,400,10,1500,4000,0,0,300,100,40,0,7000,3000,20,0,0,20,0,90,200,0,200,0,0,25,500,50,0,21,0,500,2000,0,100,0,50,400,0,5,0,400,0,0,0,0,50,150,0,50,4000,0,0,100,0,0,10,200,0,0,0,100,0,300,0,50,0,1000,3000,0,0,200,15,0,0,50,0,2400,0,0,2000,0,0,900,10,0,2000,0,0,1500,12000,500,0,0,0,6500,0,0,500,4000,0,500,3000,500,0,20,0,0,150,0,0,0,0,300,300,2500,2000,10,0,3000,300,0,11400,100,0,6000,15,20,0,6000,0,50,900,0,0,0,0,0,10,10000,0,0,10,0,0,4000,50,0,1110,500,0,0,9500,2200,0,0,100,5200,75,0,0,2000,4000,0,300,0,50,500,30,50,0,300,0,50,50,0,0,0,0,10,0,800,500,0,1,0,150,400,0,0,300,15,0,5,30,1000,400,2300,300,300,0,0,50,20,50,2000,2100,0,200,0,3000,10000,500,0,500,75,0,250,8000,3500,0,2500,0,0,0,300,3000,0,0,10,20,0,200,500,20,20,400,0,0,3000,10,100,0,2000,2100,300,2000,0,50,6000,2100,0,15,0,15,1100,0,500,500,1500,1500,0,50,750,500,2300,6800,0,0,3500,4000,0,0,50,800,10,1800,2000,50,0,0,0,50,0,2900,300,1500,3000,0,10,4000,0,0,600,3000,200,500,100,200,0,3,11000,50,50,0,0,0,0,800,0,0,0,0,15,3000,0,0,100,0,1000,0,300,300,1300,3000,4000,0,0,150,2000,1000,1000,6000,1500,3000,0,5000,1200,2500,2500,50,20,100,500,800,5500,0,0,0,0,3500,0,2000,0,300,0,1000,8000,1500,1200,3500,2300,0,0,100,200,4000,4000,0,3500,1000,3000,50,2500,1700,4000,500,0,100,3200,2900,1400,11000,2250,3000,800,300,400,3000,1000,0,200,1400,5,0,400,0,2500,50,50,1000,0,0,1000,800,50,3900,10,100,50,2000,0,5500,1000,400,0,300,0,500,0,500,700,3000,2000,1000,0,2500,6000,0,0,4000,500,5000,4500,700,0,0,0,0,8000,4000,300,800,2200,3000,3500,0,0,5000,1600,100,11000,400,3000,6000,0,4000,250,0,1000,400,15,12000,2000,2700,1000,200,0,8000,2000,8000,0,3000,2400,11000,6000,300,0,0,0,1500,100,10,500,1000,900,0,5,1500,400,3000,1000,50,3000,0,0,4000,10,0,0,50,1500,20,1000,0,200,5,0,1000,600,400,700,0,500,1500,0,0,4500,0,0,0,1000,0,2000,0,25,0,200,0,1500,500,0,200,300,7500,1500,2300,0,500,1700,0,0,40,0,100,3500,3000,0,3000,1000,0,0,700,0,1500,0,0,4000,0,0,400,7000,50,2000,0,500,0,4500,500,3900,2500,100,1000,200,20,1000,500,0,200,0,900,0,0,20,0,700,300,0,2000,0,0,0,100,560,2000,7000,150,500,10,500,1300,5000,0,50,0,300,600,6000,500,0,75,10,2000,1600,0,20,0,2900,0,2400,1500,50,400,0,300,200,1500,1500,1500,4000,2000,2500,200,10,6000,100,5500,2000,400,400,3000,0,400,100,1000,0,7000,50,0,10,0,6000,200,1000,0,1500,4500,0,50,0,2000,150,0,1200,2000,0,0,75,0,0,0,400,20,200,5500,0,800,10,0,0,50,10,2500,0,100,0,0,0,700,0,0,50,0,1500,0,0,100,0,0,0,1000,90,0,100,0,6000,200,100,2000,0,0,500,5,0,0,500,0,0,900,500,1500,6000,0,300,0,0,0,50,150,0,0,2000,0,0,2000,0,0,0,10,800,250,1250,20,0,1000,0,1000,0,1,0,0,0,0,0,100,0,100,20,0,0,0,0,0,3000,100,100,0,0,1000,0,0,25,0,10,5,500,0,400,0,0,0,0,0,150,0,10,0,200,0,1000,300,1000,0,200,50,400,0,100,400,0,5,100,1000,0,300,500,0,4000,4,0,1000,200,100,50,1000,0,0,500,0,400,0,900,0,0,50,0,1100,0,75,50,1500,100,0,0,150,0,0,0,700,0,400,30,0,500,0,0,2200,10,0,10,1800,1500,500,0,1500,0,200,0,300,0,0,3500,0,100,50,500,2000,200,0,1200,1200,0,0,7300,3000,0,3000,400,0,1400,300,0,8,250,50,30,400,0,100,0,25,2200,0,30,2000,0,800,6000,7000,3000,50,80,75,150,50,0,2000,50,0,1000,1000,0,50,0,1000,50,800,100,20,300,0,5800,500,7500,0,2600,20,0,2100,2800,800,2500,30,100,2000,0,1500,3500,50,0,0,0,0,0,50,0,2600,0,500,0,0,3000,1500,300,30,100,600,0,4500,1300,2500,200,0,900,50,0,0,400,0,100,0,0,0,4800,4000,1000,400,50,1300,15,5000,100,300,12000,0,2000,3000,60,800,0,10,6000,10,50,700,0,0,2000,200,50,0,8000,0,6000,300,1000,100,200,0,3000,1250,0,400,90,8000,0,6500,8000,100,0,4000,5000,0,200,10,0,2000,0,3000,3600,5000,3000,25,10,10,15,200,8000,0,20,2400,350,4000,0,6000,6000,4000,0,1000,1200,1200,300,0,3000,8000,0,0,300,2000,3000,1500,0,0,1000,500,8500,50,25,7000,7000,2400,0,10,1500,10000,0,300,0,4500,1500,1500,0,900,0,200,10,0,150,100,900,50,100,6000,3500,7000,0,3500,5800,100,0,3000,1500,0,50,300,0,0,0,1300,5000,2500,40,900,200,13,300,100,11000,200,0,0,5500,1500,2000,0,25,0,4500,5,800,0,400,1000,100,200,1500,200,300,0,100,150,0,500,4000,6000,200,0,200,300,1000,250,50,100,200,3000,0,0,7500,600,0,500,200,100,50,600,20,2000,30,5,0,30,50,2200,200,20,200,50,600,7400,3500,2500,3500,50,300,2500,3000,50,0,3000,6000,3000,0,0,0,200,50,200,3000,50,9000,800,400,9000,0,0,50,200,4000,3000,500,10,3000,1000,7200,50,10,2000,200,2500,0,100,7400,500,0,200,0,300,1200,0,1000,1000,0,0,200,2000,50,0,0,800,0,3000,300,0,300,0,0,0,2000,5000,0,200,1500,100,0,800,15,4000,300,2900,0,6500,250,0,20,4000,500,0,460,100,30,0,0,1800,200,500,200,20,0,0,200,700,0,30,0,1900,10000,0,20,5,400,400,100,50,20,0,50,50,0,0,0,50,15,3000,0,0,600,0,40,5,5,0,0,0,0,1000,0,0,0,0,100,0,400,0,2000,800,0,0,0,0,0,0,0,700,0,100,500,0,0,0,100,50,0,0,0,0,0,0,0,800,10,0,100,0,50,50,40,0,0,0,0,20,0,0,500,10,0,0,20,700,0,700,3000,200,40,0,0,0,200,0,0,2500,0,0,0,0,0,0,0,0,10,500,0,2500,10,0,0,0,0,0,50,0,500,5,0,0,50,0,10,0,0,0,50,20,8,1500,0,0,200,50,100,100,0,200,0,0,0,2000,100,0,4,2100,0,300,500,50,0,100,0,0,0,200,0,0,200,2700,0,0,2000,0,2000,0,0,50,0,500,400,0,0,0,0,0,0,700,0,1,0,8000,0,0,0,200,0,0,0,0,0,500,0,0,3000,0,20,0,0,0,0,50,15,0,0,0,1,100,100,150,0,1500,0,20,30,70,0,200,500,2500,0,0,0,75,0,400,0,10,0,0,0,10,0,50,15,1000,50,200,0,1200,100,3400,50,0,35,500,100,20,50,0,100,100,0,0,0,200,20,0,1000,100,3000,200,0,0,0,0,0,0,10,100,50,0,0,0,50,100,200,0,15,0,5500,100,0,0,0,10,100,50,0,0,500,5,0,0,0,50,0,10,0,1000,50,400,75,50,800,300,100,200,0,0,0,10,0,200,0,0,150,0,0,0,0,0,0,0,600,0,50,600,16000,7,0,300,0,30,350,0,500,200,500,0,0,0,0,0,0,50,55,300,0,0,200,0,5,0,0,2000,400,0,0,0,0,0,400,2000,0,0,0,0,0,40,300,200,10,0,100,300,100,0,0,0,0,1000,0,700,0,0,10,0,50,0,0,800,50,10,10,0,100,10,100,400,100,0,10,0,0,0,0,2500,2500,0,0,100,0,200,1250,5,600,0,2000,0,0,5500,0,0,400,0,0,0,5000,0,0,0,0,800,50,3000,25,0,0,10,0,500,3000,0,0,75,0,200,50,13000,0,0,0,1800,500,800,0,0,0,0,0,0,0,0,0,0,0,3800,0,10,0,0,6000,0,200,0,5,2300,400,200,0,10,0,2700,0,1200,1700,0,50,2500,50,0,300,5,500,100,0,0,0,50,300,300,4000,0,0,100,10,50,0,0,0,5000,0,0,0,1022,20,10,0,0,300,100,10,0,0,0,0,0,0,50,50,0,0,0,6000,7000,0,0,0,75,0,0,50,8000,300,50,0,15,100,25,0,0,300,10,150,30,200,1000,200,200,200,1800,0,50,1,0,0,0,0,5000,0,0,30,0,1000,0,0,10,300,0,200,500,0,800,500,200,0,0,5000,2000,0,0,1500,500,0,0,10,200,200,4800,2600,0,0,0,400,0,0,0,0,2000,1600,0,8500,2000,10000,15,0,0,100,0,10,1000,0,50,200,0,3400,5400,6000,2000,50,1300,200,0,0,0,300,3000,0,15,500,4000,7000,20,0,30,4500,0,0,0,1500,0,25,11000,0,0,1300,500,0,0,800,6500,1500,0,0,0,300,1600,0,0,300,0,300,12000,0,50,500,40,50,70,0,0,0,100,1000,200,100,8,2300,2000,3000,500,1000,0,0,20,0,300,2000,0,0,0,0,0,75,2000,100,0,2000,0,400,100,300,500,50,4000,5500,2500,3500,20,0,0,300,1000,800,0,10,0,10,10,0,1000,200,0,0,6000,0,0,50,500,50,5000,4000,0,10,5000,100,0,100,100,100,1000,0,1000,100,100,1200,4000,7000,3000,2000,0,4000,3000,150,1800,500,1000,1000,200,0,0,5800,2600,2200,3000,200,0,6000,0,0,250,1500,800,2500,300,1000,500,0,2000,2000,100,5,800,300,0,10,0,9000,0,1000,0,1200,100,0,0,0,3500,2000,40,0,40,4000,0,50,0,0,800,3500,1300,100,100,3000,3000,11000,50,0,0,0,500,10,500,1500,3500,5700,0,0,0,35,1000,2000,2000,10,0,700,100,3000,0,0,0,1500,3500,400,100,550,8000,6000,10,2500,700,0,500,2400,3000,10,0,10,0,0,4000,0,0,0,0,200,0,5000,2000,3400,0,20,0,5,0,500,500,7000,50,1000,20,500,0,0,3500,50,1000,0,2000,100,0,50,0,1000,1500,2100,3600,2000,2200,800,5000,1500,4000,3000,4000,8000,0,4000,350,400,800,0,0,2500,1500,10000,8000,7000,0,100,5000,1200,3600,0,50,10000,10000,8000,500,300,300,0,1600,2200,1500,0,0,0,50,75,700,3000,2500,2500,3000,200,0,10,0,50,100,1000,0,5000,200,8800,8000,3000,1200,2,0,100,10,300,0,1500,3000,0,1500,0,500,500,0,0,6000,0,0,800,4500,2000,0,200,800,500,11000,1500,6000,5000,3000,2000,1500,2500,100,3000,3500,0,800,2000,7500,800,300,1000,1500,1000,300,20,400,1500,500,1000,0,4000,20,150,400,0,4000,1000,1500,1900,2400,0,0,0,0,1000,20,0,30,75,5000,0,0,1350,0,0,0,200,200,400,0,0,4000,0,200,3000,1500,1200,850,1000,500,1000,100,300,1000,75,1800,1900,500,500,0,10,20,300,0,0,40,4500,3000,2000,4000,6000,5000,7000,1500,3000,0,0,50,0,2850,0,600,500,2000,2000,2000,5000,10,800,500,4500,5000,0,0,0,1000,0,4500,0,15,10,0,4000,0,8300,250,20,50,12000,4000,2000,0,5900,10,0,0,0,650,1500,5000,2400,3500,800,0,200,0,0,4500,700,0,0,20,100,0,3000,0,1000,1700,0,0,0,0,0,300,0,0,1200,25,500,200,0,6,1500,1500,10000,100,0,4000,0,800,4000,400,400,1100,5000,0,0,600,2500,1500,5000,800,2500,100,0,100,0,0,0,2200,85,0,2000,0,1050,0,0,1500,0,100,500,0,0,0,10,0,1800,10,0,300,30,0,0,500,150,250,0,800,300,1800,0,50,400,50,10,0,500,0,1500,300,1800,2300,60,0,1000,11000,200,350,100,2500,100,6,270,3000,1500,2200,450,0,0,0,500,0,0,0,525,0,0,0,0,0,2000,300,0,1200,0,1200,0,0,0,100,50,0,100,0,750,200,0,0,400,200,5,0,0,0,140,10000,100,0,50,0,5,10,0,100,0,0,0,50,20,0,0,700,1,0,0,6,50,0,5,500,100,0,150,0,3000,0,0,6000,800,10,1300,3000,100,700,400,0,300,200,50,2000,200,0,0,0,0,1300,0,0,20,0,0,200,200,50,1000,5,0,10,100,200,0,0,700,0,0,0,0,10,50,0,75,10,700,500,10,1000,10,500,10,50,0,75,300,300,2,1000,0,0,0,5,25,50,0,10,0,10,0,50,1000,0,0,5,0,0,200,300,1000,200,0,0,430,0,200,800,200,1000,900,2200,5,800,0,20,0,200,0,50,1000,50,0,0,20,20,50,0,0,0,5,0,300,0,2400,75,15,0,2000,30,200,50,4000,0,50,0,0,200,200,0,500,0,0,0,500,100,5,300,0,0,0,500,50,0,0,0,40,400,2,0,0,0,900,200,1000,0,300,0,2700,1100,2500,1500,4000,1000,500,0,5,0,500,100,900,400,500,500,0,0,50,0,20,0,0,50,0,15,0,1500,4000,30,1000,0,500,5000,100,100,0,0,0,5000,0,0,50,6000,2000,2000,1000,300,900,0,6000,2000,1000,0,0,8000,0,100,10000,3000,1200,0,0,300,0,0,0,520,0,100,200,400,400,2400,0,200,2000,3000,0,20,200,200,1000,1000,10,1500,50,750,4000,3500,7000,0,40,500,9000,75,1800,100,0,3000,0,6500,50,0,0,350,1000,5000,700,1300,0,5,0,6000,1300,2500,100,4000,0,300,2000,500,0,3500,2000,3000,100,100,2000,0,6000,10,800,0,0,0,25,0,100,300,900,2000,0,14000,8500,100,0,500,150,0,0,1000,0,0,0,1000,200,10,5000,0,1000,200,3500,0,10,1500,8000,6000,100,50,2500,2000,10,0,500,300,0,1500,500,4,500,800,0,100,1000,1560,400,100,11500,800,10,500,4000,4000,0,5450,8000,2000,500,200,200,1700,1300,1800,200,200,1000,600,4000,8500,7000,4000,20,0,200,0,0,750,50,0,0,1200,9000,1200,0,0,1000,1000,50,300,3000,9000,100,0,3000,500,3200,850,400,500,100,6000,0,2000,0,75,6000,75,10,0,50,50,0,0,50,2000,200,700,400,10,4000,5000,7000,1500,1700,2000,2500,500,20,1000,400,2600,2000,4500,3000,0,0,3000,3000,0,20,2,200,0,0,2500,5200,4000,0,0,700,800,200,0,1000,0,0,500,2400,100,0,0,400,0,0,0,0,6200,2000,50,500,1000,300,2600,0,0,0,3000,30,600,200,7400,6000,7000,7800,5200,1200,3500,0,0,0,1000,500,50,0,20,0,0,3000,0,10,5,5000,4000,634,2500,1800,7000,20,10,0,0,800,1500,7600,2000,10,200,0,600,700,0,500,11000,5000,2000,2000,6000,3400,10,3000,0,600,1000,350,0,20,300,0,600,5000,700,200,10,0,1000,3000,0,0,60,700,50,1,150,1500,800,600,1000,0,0,0,5000,0,0,500,3800,0,15,200,3000,2000,3500,0,0,0,1800,11000,3500,1000,0,2000,0,100,0,2000,100,1000,3500,3000,5000,700,0,3000,50,0,400,2000,1800,1500,0,20,0,7200,6000,1500,1400,3000,0,100,0,10,0,500,0,0,0,1500,10,10500,0,0,400,250,50,11000,4800,5000,2800,0,0,3000,4000,0,5,200,2000,300,200,0,6000,1200,1900,3000,2500,500,0,2500,1100,3500,50,50,1000,200,0,10,0,5,0,0,5000,2500,50,0,0,0,0,0,300,1500,5000,100,0,800,2600,0,0,100,10000,0,200,0,0,10,10,5000,0,100,0,200,10,0,500,0,0,0,0,0,0,0,100,3,100,0,50,0,1500,2000,0,0,0,0,0,1000,0,0,200,0,5,0,0,1100,150,0,100,0,20,0,0,50,0,3000,100,0,0,0,0,0,0,0,0,200,0,0,4000,50,50,0,250,0,1000,0,150,0,200,5000,0,0,2,1126,800,0,0,0,15,50,3500,40,0,400,150,1200,0,0,400,1000,1000,0,0,0,10,0,8000,200,0,20,0,0,6,100,10,0,200,200,0,0,0,0,300,0,0,600,0,0,0,50,50,100,1000,0,0,0,0,0,100,0,15,0,0,0,100,0,0,5,5,100,0,0,0,800,0,10,50,0,20,0,0,700,400,1000,3700,100,100,0,200,100,0,3000,50,0,1200,150,300,100,0,300,5,600,1500,7500,0,50,0,0,300,0,0,0,0,300,0,10,0,0,300,0,2500,35,0,0,150,0,500,0,0,0,0,30,0,0,100,0,400,400,100,0,0,0,1500,0,10,0,0,500,100,500,200,700,100,0,50,1500,1300,2500,70,650,0,10,500,1500,3000,0,75,550,1000,50,0,0,75,0,0,0,3,0,50,2200,0,0,50,500,100,0,100,0,100,0,0,0,900,0,50,0,0,300,0,200,300,4,20,0,0,600,0,0,50,1000,4,300,0,150,0,8000,50,0,0,0,2600,0,0,0,0,1200,200,1000,0,500,0,0,100,0,0,20,30,50,750,3700,0,50,0,100,400,0,0,30,0,0,0,0,600,0,200,75,0,50,700,20,0,0,0,0,700,0,0,6500,0,0,50,300,30,0,9980,2200,200,0,450,0,400,0,200,6000,0,0,0,10,0,0,0,10,0,0,0,500,0,0,0,0,3000,0,0,0,0,0,0,8000,0,0,0,0,0,10,1900,50,0,200,500,0,20,550,20,500,0,0,10,0,0,5,0,0,0,0,700,20,20,500,0,0,3000,100,0,1200,0,50,0,0,0,0,0,180,100,0,0,0,100,0,6000,0,10,0,0,0,0,0,0,0,0,0,0,30,0,200,2500,0,0,1800,4500,40,0,10,0,10,0,0,100,300,50,1000,5,0,0,0,0,0,100,2000,6000,3500,0,20,0,300,300,0,0,0,0,0,0,0,0,0,10,0,0,0,0,650,50,2000,0,15,0,1500,0,0,0,400,0,5,200,0,10,500,1000,0,0,0,20,100,100,3000,1500,0,0,0,3,1500,5,1000,0,100,1000,0,1000,500,50,10,2000,0,0,0,1000,0,0,30,0,10,0,300,400,0,50,12,0,0,20,50,0,0,0,0,300,500,10,0,50,0,5,0,0,0,10,100,0,0,0,250,0,0,200,0,0,0,0,50,10,0,0,0,100,0,150,9000,5000,20,0,50,0,1100,0,250,0,0,100,0,700,0,3000,50,0,0,100,0,200,1000,0,20,10,0,0,0,0,1000,2600,0,0,30,0,0,400,100,1500,3000,10,0,0,0,5,0,0,0,0,1000,7000,5,0,50,0,50,0,800,25,0,100,0,1000,0,0,0,0,0,30,100,0,0,0,1000,0,0,1500,0,200,800,0,0,50,50,200,100,300,3000,0,0,0,0,0,2500,0,50,0,6000,700,0,0,300,200,100,400,0,30,3500,0,0,0,1000,0,0,0,0,1800,0,10,50,0,0,0,1000,0,500,15,200,0,200,0,0,0,0,0,50,0,200,200,15,0,0,0,1,0,0,50,1800,3000,200,300,0,0,0,25,0,0,0,2400,0,0,0,0,0,0,3000,1000,8000,300,0,200,4000,0,0,0,0,0,0,0,0,0,100,1000,600,3000,8000,0,0,1000,0,800,0,600,0,0,50,50,3,150,0,1500,0,0,0,50,0,0,0,50,0,0,200,0,50,400,1200,0,50,0,0,0,150,10,0,50,1000,500,2,0,0,0,4000,0,0,0,0,0,0,50,0,0,5000,0,300,0,100,50,0,0,0,200,500,9000,5000,0,0,50,0,0,0,0,2,30,0,0,100,100,3000,3000,100,0,0,10,400,10,0,1100,1200,5000,3400,3000,0,0,0,0,0,500,3000,1000,0,50,2500,0,25,0,300,0,0,100,200,250,300,50,1000,500,1000,0,20,0,0,0,800,400,0,0,0,2500,50,0,0,50,1000,0,0,1000,500,35,0,100,8500,1500,25,0,0,0,0,0,0,500,75,0,400,20,0,0,2600,0,0,0,0,5900,83,1500,100,500,175,200,100,3000,1250,2000,3000,100,0,0,0,200,0,25,700,0,0,250,0,0,13500,3000,0,0,5,500,10,10,0,350,200,800,0,300,1000,100,150,50,6000,2000,4000,4000,0,0,0,0,0,800,10000,100,0,100,0,0,0,0,550,4500,6000,2000,6000,3000,0,0,10,10,0,900,150,50,200,3000,6000,0,300,200,0,22,0,0,5,800,0,1500,50,0,75,200,0,3500,0,0,0,1000,1000,200,120,50,0,7400,0,500,100,100,60,0,600,300,1000,800,2000,0,10,0,500,0,100,0,0,50,200,3000,3000,20,0,250,20,0,1000,0,1200,5000,0,50,1200,1500,10,100,200,0,1000,4800,1300,0,0,100,11000,0,500,1000,700,500,4300,1300,50,0,100,65,3000,0,800,10,0,0,5000,0,0,0,0,500,100,10,1200,100,1000,0,0,800,50,200,0,11000,2800,2500,1200,0,0,0,0,0,50,100,0,2000,8500,10,0,0,0,70,100,16000,200,400,0,100,0,1000,300,2900,2000,2300,3000,3000,50,500,0,10,0,20,0,200,550,2000,3400,1500,1500,200,0,0,500,0,7000,1500,1200,1500,0,0,0,0,0,100,0,0,50,0,0,25,1000,50,2000,3500,11000,1000,0,0,0,0,700,6000,0,0,9000,550,25,0,4200,300,150,0,400,300,800,0,5000,50,4000,0,0,0,500,300,0,2440,900,0,600,1200,2500,3000,0,0,0,1200,0,400,0,1000,2500,100,30,0,0,2500,4500,0,3000,1500,0,5,1000,0,0,200,340,1600,3000,3000,2500,4000,5300,1900,20,0,2400,1500,600,1000,800,200,200,0,0,0,2500,8000,3000,2000,1500,2000,0,0,2000,0,1100,2700,1000,1000,400,7500,20,10,50,0,100,190,1000,1000,0,900,7000,2500,4000,3000,2500,8000,0,10,0,0,1200,5000,0,200,500,0,1000,300,500,500,20,0,5000,5500,5000,2200,1300,4000,3200,0,4000,5000,7600,1000,3000,3000,200,1000,500,100,3000,2000,50,50,600,7000,500,1000,150,100,0,800,4500,3700,2000,400,200,2000,3000,0,2000,3000,400,5,5,2000,2900,4000,500,200,0,1500,1100,0,0,0,0,200,50,300,20,500,0,1750,0,0,1500,300,200,0,3000,3000,0,200,100,10,700,750,10,100,500,100,1800,0,200,0,500,50,1500,0,100,500,20,0,400,50,300,400,30,5500,3000,8,200,10,300,0,2000,2000,0,200,800,1000,0,7000,1500,600,0,3500,0,8000,3000,4300,20,100,2700,100,3000,10000,8700,6000,10000,8500,200,8300,7000,400,2,3500,1500,45,75,1100,1500,800,100,50,0,9500,1800,3500,0,0,35,560,0,1000,200,200,10,4000,5000,2500,1500,3000,1500,5,0,0,1000,100,0,0,0,100,100,500,50,800,3000,100,0,0,130,5,500,0,0,800,1100,0,10,500,100,800,100,200,3750,4600,2000,1800,300,500,50,800,0,6000,5000,2500,1200,800,0,0,400,300,1000,0,1000,0,2600,6000,4400,4000,3000,2000,0,0,500,10,0,0,500,800,0,400,100,0,0,10,0,7000,5000,800,1000,3500,1800,0,0,0,0,0,2000,4000,4000,2500,0,5000,6200,3500,126,1500,0,9000,1200,0,5,0,9000,8000,100,300,1000,300,2000,0,0,20,500,3000,2000,4000,1200,20,300,400,1,200,0,0,0,0,700,0,0,1000,750,1500,8000,100,50,37,4000,0,500,1000,0,0,13500,2200,6000,2400,50,1600,500,10,0,200,850,3500,7600,4000,2500,4000,3000,3700,15,0,900,50,7000,50,400,15,500,100,30,200,4000,2000,100,10,0,1500,0,0,0,7500,75,400,200,500,350,0,0,10,0,50,0,900,0,0,5,2800,6000,3000,0,0,0,0,0,1200,50,700,600,400,0,0,0,0,50,900,100,0,4900,3500,10,2000,10,3000,5000,200,5,20,0,1000,6000,3000,4500,3500,3000,6500,1100,3000,2800,4000,3600,1500,3000,0,500,1500,4000,4000,3500,1000,1500,0,1600,1000,5000,0,1000,0,5000,200,50,200,4200,800,1000,200,5500,0,0,0,200,2500,6000,0,0,100,0,2000,1000,1500,3000,1500,0,0,500,750,120,3500,0,0,5000,500,100,4400,1000,1500,5,300,200,800,1000,0,0,1200,0,0,300,1500,0,30,600,200,150,0,300,350,300,0,500,50,400,0,150,600,0,20,0,300,1100,1500,0,500,500,500,1000,10,200,0,100,0,100,1000,2800,5,50,0,500,500,10200,200,100,900,75,6500,7000,0,200,10,0,50,150,300,300,0,0,0,5,200,300,0,0,0,500,100,2500,0,0,100,10000,10,400,25,500,0,20,0,200,0,300,0,0,300,0,0,300,0,50,0,100,700,0,5700,2000,800,10,4300,125,1500,1900,3000,1700,1000,100,0,500,50,0,0,2500,1200,300,5,50,200,5,9000,0,30,1000,0,200,65,50,0,100,100,0,0,0,5000,0,800,150,0,1250,100,50,100,200,3000,1000,500,0,200,0,0,20,20,700,3000,1200,0,1500,0,1300,800,0,300,2000,8600,600,0,0,10,1850,0,0,0,600,600,1800,100,0,0,0,75,20,1200,0,800,200,100,500,0,300,3000,0,600,300,50,0,300,0,35,50,0,0,2500,1200,0,3000,150,500,200,100,100,0,40,0,1200,0,0,300,0,100,0,1000,1500,150,1000,0,4000,200,50,300,0,100,0,50,0,300,5,700,3000,0,50,10,0,0,50,1500,5,50,0,0,0,0,0,250,50,0,2000,20,0,0,400,400,75,0,5,500,0,0,0,0,1000,1000,0,0,0,200,0,1400,600,4000,0,0,0,7000,300,500,300,500,0,40,8,4000,0,1500,100,150,5,100,0,600,0,400,700,400,50,400,100,3000,10000,25,0,0,0,200,2800,0,3800,600,0,0,4000,1300,0,0,500,200,0,500,5000,1000,0,1000,0,3000,0,0,0,3000,1500,10,50,100,3500,3000,2500,900,200,7500,200,0,1000,1500,63,500,20,1200,10,0,6000,3500,0,50,0,0,4000,0,0,1000,900,200,500,10,0,5000,5,0,5000,3500,25,9000,15,2000,2500,5500,6500,100,0,2700,2000,0,0,0,100,20,10,1000,100,500,150,0,200,100,500,3000,50,0,0,100,100,0,50,0,300,0,200,2000,0,0,100,3000,500,30,700,500,7000,3000,800,7000,0,300,600,1250,0,900,15,200,500,2500,2000,2500,400,0,800,400,3000,4000,0,1500,200,0,0,20,0,0,8000,0,0,10,2400,0,50,0,1500,4000,100,0,0,0,0,0,8500,50,0,0,0,5,0,30,300,2800,400,4000,1400,3000,0,50,0,500,0,200,100,500,500,0,8000,1200,0,0,0,0,1500,5000,50,0,4000,200,8500,10,0,60,5000,10000,3500,50,0,550,200,0,1000,1500,0,200,20,2500,7000,3000,1500,50,0,500,300,0,5000,1900,4900,10,750,2600,3000,1800,3000,5000,5000,5,10,0,9000,5,400,3150,4500,1100,100,0,0,1000,3000,2000,100,0,7000,3000,600,100,0,6500,5400,8000,0,700,0,0,100,200,3000,1700,0,1500,0,10000,0,900,1000,1000,100,20,20,0,5000,1700,2000,0,0,400,1000,0,600,1300,4000,0,0,7500,0,0,1000,400,0,200,2000,500,1500,50,50,100,0,800,3000,10000,200,30,0,2000,2000,400,100,500,0,200,7000,1000,150,3000,100,20,0,2000,3000,0,30,450,300,0,200,2000,2500,10,0,50,2000,300,2100,0,0,1000,4800,1500,1100,0,500,20,1000,50,0,0,1200,100,0,6800,1400,0,0,50,10,0,1500,200,0,1800,2500,1,10,50,0,15,25,8000,3500,0,0,300,300,7000,100,0,5,50,500,50,500,300,10,0,0,2000,4000,3200,10000,0,100,0,0,0,10000,3000,5000,2300,0,0,0,500,0,300,2500,20,2500,0,400,300,500,0,50,0,0,1500,0,10,0,3000,10,2000,0,0,0,0,50,100,400,200,100,1200,0,0,1000,400,600,3200,0,0,0,3000,300,300,0,300,250,50,25,1800,0,3200,0,3000,0,800,100,1000,20,300,0,10,2000,800,75,45,0,2000,20,50,5000,3800,0,0,150,0,0,0,0,600,50,0,50,4000,0,0,0,4000,0,2300,4000,2500,500,500,0,500,150,0,400,0,300,2500,0,0,50,0,2000,100,0,0,0,0,3000,0,0,0,0,0,50,500,100,10,3000,4000,50,0,40,50,100,40,200,0,400,0,0,0,0,10,50,1400,150,200,3000,0,0,0,3700,0,200,0,1000,50,0,0,100,300,7500,1700,0,20,200,10,0,50,1000,20,0,0,0,0,0,0,40,0,3000,0,200,300,50,200,0,2000,200,0,0,100,10,10,7,800,0,9000,3,0,30,0,0,100,0,0,0,2200,15,0,100,0,0,50,5000,0,0,2,0,200,150,400,0,20,1500,0,30,50,100,0,0,500,2400,1500,1300,20,200,15,0,10,0,2100,0,50,0,0,0,0,0,0,600,0,0,2000,0,0,0,0,0,300,25,50,1200,0,0,0,0,0,0,10,1000,200,10,4000,50,100,1000,100,100,100,100,0,0,0,0,500,10,300,100,0,300,0,20,0,50,200,0,150,0,800,0,0,0,50,100,0,20,0,0,10,0,0,0,0,0,0,15000,0,20,1100,0,10,0,100,1000,0,200,100,0,1500,100,0,100,100,0,0,0,37,0,0,100,0,50,0,5000,0,5000,0,0,0,0,0,0,30,200,0,100,10,40,1000,100,0,0,0,1500,20,0,0,0,100,100,6,50,0,0,0,1000,75,100,100,500,0,300,0,5,0,0,1000,0,1,0,100,0,3000,2000,0,0,0,0,0,0,100,0,100,0,0,2000,0,100,0,50,0,0,0,50,0,0,0,0,0,0,0,300,0,0,0,0,0,0,0,0,0,0,200,1500,1500,0,0,0,0,0,0,0,0,20,20,0,700,100,0,0,0,0,10,100,100,500,1000,200,35,10,0,0,6000,10,200,30,0,0,0,0,0,75,500,0,200,0,1500,0,0,0,0,0,0,3,0,200,500,0,20,1500,0,0,10,300,200,100,0,0,200,0,0,300,200,0,0,100,0,0,0,0,20,0,0,0,0,10,0,0,0,150,20,0,50,0,0,100,0,175,150,500,0,0,5,100,0,300,0,0,50,50,200,0,0,0,0,0,0,100,0,0,0,0,0,0,0,0,75,0,0,100,1200,0,1000,0,0,0,0,0,600,150,200,200,190,1000,600,0,3500,0,25,0,0,0,300,0,0,0,0,0,0,0,0,0,50,0,10,200,200,0,0,200,9000,0,0,0,0,0,50,0,0,0,75,0,10,15,7000,0,75,0,0,0,10,1000,800,0,50,400,0,0,200,0,20,0,0,0,0,1000,0,0,300,0,100,0,0,0,0,11300,11000,50,0,0,2000,20,0,0,0,200,0,0,50,500,50,0,0,300,0,0,0,20,2200,0,500,0,0,1000,0,0,0,300,0,10,0,0,0,3300,1500,0,10,500,10,0,11000,5000,3000,0,100,50,0,50,0,500,800,100,800,55,0,0,2000,10,0,0,0,0,0,100,0,50,0,50,0,0,0,0,50,0,200,0,500,0,0,200,0,0,0,0,0,0,50,0,500,4400,200,0,0,10,0,0,100,0,0,0,0,0,0,250,0,300,0,0,0,50,0,50,0,0,800,0,50,20,400,0,0,1000,2000,0,0,0,100,5,0,30,200,5,25,20,1000,0,0,100,0,0,20,10,25,400,0,0,0,600,3000,2200,0,100,0,0,0,0,3000,100,100,50,0,0,0,0,1500,600,10,0,50,50,0,30,30,400,100,50,200,0,100,50,0,0,7000,0,0,200,0,0,0,700,0,40,500,0,0,50,0,50,0,0,500,0,600,10,0,150,300,0,87,0,1740,0,10,0,0,0,2900,0,0,0,0,50,100,800,11000,500,450,0,0,0,400,50,50,200,100,50,300,50,5000,0,0,20,0,8000,0,0,300,0,200,5000,0,0,0,2400,0,300,100,0,150,0,13000,100,0,0,1500,0,20,600,200,5,10,0,1020,4400,100,200,10000,0,600,50,0,0,1000,3000,0,1400,1500,0,0,0,5,0,400,500,6000,0,50,0,600,100,2300,0,40,0,3500,4000,3000,10,50,0,0,0,0,0,100,0,50,0,1000,0,1900,200,100,500,40,0,100,100,1500,6,50,50,0,0,0,200,5,0,50,200,100,0,10,20,20,100,0,300,250,700,0,400,4000,0,0,0,0,0,1000,0,200,0,0,0,40,700,0,0,0,0,100,0,0,0,0,0,300,1600,600,1000,2800,0,0,50,100,0,3000,50,100,0,0,0,15,0,2,600,100,2500,4000,1800,0,20,500,1200,10,10,200,100,30,3000,5,30,0,0,500,50,30,1000,0,300,1200,20,0,0,500,200,0,3000,2500,2000,100,0,0,3000,150,1000,50,1800,0,35,300,100,1000,0,0,2500,0,100,50,0,0,0,1,0,50,5500,800,10,0,0,0,0,5,100,200,4000,4,250,300,0,0,3000,0,0,0,600,20,50,0,100,0,1800,0,0,0,0,500,1500,0,50,1,1500,3000,1500,10,800,0,1500,0,50,500,0,0,600,0,500,3000,1000,5,0,0,100,0,6000,600,2000,2000,9000,6000,0,1500,1000,4000,5000,300,200,75,2000,3500,0,0,0,40,0,450,500,0,5000,1600,0,0,800,2000,3000,0,400,1000,0,200,50,0,150,600,0,3000,11000,3000,0,800,10,200,800,10,200,500,0,200,500,0,200,2600,4000,0,500,200,50,0,10000,100,0,100,3500,2500,100,25,400,400,100,0,1000,5,0,2000,700,10,800,1800,0,100,300,0,0,0,2200,4000,4000,0,100,0,0,0,4000,400,1000,200,500,1500,6600,0,50,1200,10,50,0,0,0,50,30,0,500,5,500,20,100,4500,7500,3000,5000,10,0,100,50,1000,300,20,800,0,50,50,0,0,400,2500,0,250,100,100,3500,200,10,20,650,3200,5000,0,20,3000,20,150,500,0,0,5000,10,800,0,1400,3000,1600,0,4000,1000,0,75,0,1000,5000,2500,30,0,50,0,0,0,0,0,10,5,50,2000,10,0,2000,0,0,1500,50,800,1500,10400,0,0,0,100,800,0,2500,550,500,800,100,1800,4000,3000,0,150,0,0,300,3000,1600,100,0,100,50,200,4000,3000,0,100,3000,1500,0,2500,7,2500,2500,3000,1500,2500,0,500,150,400,250,0,5000,6100,0,0,5,0,20,1000,1000,2600,0,400,0,0,50,0,10,3000,200,0,0,10,250,200,0,10,400,200,0,0,300,20,1000,25,100,2,100,1000,500,500,200,0,10,15,0,0,20,1000,2500,600,3000,500,0,800,100,0,0,0,0,0,0,300,100,300,800,0,1000,3000,1500,1500,6000,0,10,400,30,5,50,900,1000,300,0,2000,3500,4600,2000,0,0,0,0,0,1500,1100,0,600,3000,1200,0,10,20,3000,600,3000,2000,20,0,0,16,100,10,0,10,4500,3500,2000,0,15,0,0,25,0,8000,300,30,2100,100,500,0,0,0,800,100,3000,1300,800,0,2000,0,0,3400,100,1500,500,100,3000,2000,0,800,0,100,0,800,0,8000,0,500,300,200,0,500,0,5000,4000,3000,2800,0,0,100,175,3000,600,100,0,100,470,0,1000,2000,200,1200,0,1000,0,200,0,0,0,0,2000,0,4500,4000,50,250,20,1200,0,0,0,4700,0,2400,250,300,400,2500,4000,3000,2000,4000,1300,0,25,0,250,200,900,2000,2000,3000,2500,0,3000,5000,1800,2600,1000,1000,1000,11000,4000,4000,4000,5000,25,0,400,3000,25,4700,100,4000,500,0,3000,1200,3000,0,3000,3000,2000,1500,500,0,0,0,300,3000,2000,200,0,1500,5000,1500,7000,4500,50,100,0,500,1000,7000,1400,3000,4000,5000,3000,1100,50,2500,1000,0,4000,8000,1700,2000,3600,20,2500,300,4000,200,500,2500,0,0,0,400,0,1800,20,900,7000,4000,50,10,100,200,5000,0,8300,0,7500,600,0,500,0,1000,0,2500,0,0,50,1500,7000,0,0,50,3000,400,150,500,0,5000,4000,200,0,0,0,0,5500,3000,400,0,300,100,0,0,100,400,700,1200,0,0,1000,100,200,0,8000,0,300,900,0,200,50,5000,800,100,0,5000,0,0,0,300,7000,200,100,50,150,2200,400,0,0,300,0,800,0,1000,10,1400,30,300,1000,0,0,300,0,3500,400,400,0,800,500,30,500,100,2500,10,0,1000,0,10,2400,100,100,80,500,400,400,100,0,0,0,600,600,0,0,500,50,150,800,7000,50,55,0,0,100,0,50,200,0,10,1000,0,100,0,0,10,0,600,0,100,400,800,20,10,300,100,300,200,0,0,0,1000,0,1200,10,0,500,4000,0,0,1800,4000,0,50,0,0,3000,0,25,0,200,200,10,500,0,0,50,500,50,200,5,5,10,300,0,0,0,20,200,300,500,200,100,5,0,200,0,0,1800,3000,1200,1800,250,1300,1800,10,20,1200,2000,150,200,0,0,500,650,0,500,100,0,500,0,200,1200,250,0,0,50,80,0,0,50,0,600,300,0,2000,75,1000,500,300,0,200,50,250,100,200,0,400,0,0,0,1500,0,1800,100,0,500,2500,0,0,0,50,0,0,200,25,1200,20,0,20,300,5,500,900,0,10,200,0,0,200,10,800,0,0,0,50,15,6000,200,500,500,0,0,200,100,0,50,0,50,0,0,1800,600,0,10,450,200,0,200,500,6500,50,200,0,10000,20,80,0,100,250,0,1100,15,400,0,800,3000,0,100,0,0,0,0,300,0,0,0,0,800,10,200,150,1000,0,0,0,1600,0,100,2300,200,0,800,0,0,450,1400,500,200,2000,35,150,1900,1000,0,0,400,20,1000,400,100,1300,0,0,0,0,0,800,100,3000,200,0,500,1,0,0,2000,3500,1000,0,10,0,0,37,1000,1200,0,0,100,100,30,400,500,0,0,0,20,50,100,150,200,0,0,0,0,800,2000,1100,0,5,100,200,2,0,75,0,200,50,150,100,150,2200,0,0,15,3000,0,0,0,200,0,2000,0,200,500,500,10200,0,6000,0,500,3000,2500,1000,0,800,3000,6,50,50,500,3000,2500,0,0,0,1000,75,6700,0,10,0,10000,10,2500,10,10,0,20,0,100,0,0,1200,3000,0,0,4000,0,0,0,200,2200,0,5000,300,200,1900,3500,3000,0,0,0,0,0,50,30,200,100,5500,2500,400,2000,0,1000,800,0,500,0,2000,3400,500,0,5,10,400,7000,600,100,1800,0,2000,2700,2000,1000,5700,3000,4000,0,100,0,800,200,4000,200,0,40,0,0,0,3000,100,3000,10,500,4000,0,0,0,95,5000,20,10,0,450,3000,3000,0,0,0,50,400,100,3200,2000,0,1000,5,10,5000,75,10,0,0,5000,4000,1000,0,3000,100,100,400,1880,1500,2000,50,0,5000,0,250,0,10,200,200,7000,60,200,0,1000,4800,10,25,755,1500,100,20,0,1000,50,1500,50,200,10,4000,0,0,300,0,500,1500,2300,10000,5000,8000,300,6000,200,500,1000,10,4200,1800,1000,800,4000,2000,0,100,4000,2000,0,10,20,1000,0,0,2100,3500,0,800,0,0,0,2000,0,0,0,0,200,450,500,0,0,4000,200,4000,800,5000,0,0,30,800,200,3000,0,0,300,5000,5000,10000,100,0,10100,200,2800,0,500,500,0,0,1000,100,300,0,2000,1500,0,0,0,0,2000,500,150,1000,100,0,2500,5600,2000,100,2500,500,1500,3000,700,100,0,200,0,2800,0,1000,0,0,0,1,0,800,0,500,700,0,30,0,0,0,0,50,200,0,0,0,700,50,0,0,0,0,15000,1200,0,0,0,200,10,4,0,0,0,1000,2500,0,2500,0,50,0,50,0,50,100,9500,4000,3000,200,2200,4000,1000,200,1500,100,100,50,800,500,20,100,300,0,0,50,5000,900,0,2000,0,0,0,100,0,0,1000,0,0,0,0,800,500,125,200,100,50,3000,0,0,1200,0,0,10,0,0,0,0,1400,0,40,1000,500,10,0,0,0,0,0,0,10,800,7000,0,0,15,50,0,0,0,50,100,10,0,4000,100,50,10,1,0,10,400,10,0,800,1000,0,10,20,100,0,100,100,5000,2200,3100,1500,0,300,100,1000,0,0,900,0,4000,0,0,200,0,0,0,50,50,0,0,6000,0,0,0,500,150,0,4500,10,0,5200,25,200,0,0,200,0,12,0,100,1,100,13000,0,0,0,0,500,0,1000,0,2200,0,7000,50,200,0,0,1200,200,0,2000,400,20,0,0,0,0,10,30,3500,0,0,30,0,0,200,0,1000,500,0,0,0,800,50,0,0,0,0,0,0,0,100,0,0,500,3000,1,15,0,400,0,500,20,0,10,500,5,100,0,0,3,600,20,0,0,0,0,11000,1800,0,20,10,12,0,0,10,0,0,0,10,0,0,100,50,8,10,0,1200,0,0,0,0,1000,200,0,0,0,100,0,0,0,100,0,10,0,0,0,20,0,400,50,100,0,50,1000,0,1500,2000,25,0,500,500,300,500,0,0,0,200,400,0,4000,20,0,0,0,14,0,1100,500,200,50,5,500,0,0,50,0,1500,0,0,0,12,0,100,0,200,0,2000,0,200,500,1700,0,0,0,0,500,300,30,0,100,0,0,300,2000,20,0,0,0,0,100,0,0,3500,0,0,0,100,0,500,200,2000,1500,0,50,0,200,0,0,0,1500,0,500,0,50,0,0,10,0,10,0,0,0,10,0,0,0,0,300,200,50,0,5,0,1000,0,50,0,50,50,100,0,0,0,0,0,20,10,25,0,0,50,400,7500,0,700,0,3,0,20,500,0,0,50,0,0,10,0,0,75,800,50,50,600,30,0,2,5,0,0,0,0,0,20,3000,50,5,100,0,0,200,100,20,0,0,0,0,0,40,0,0,100,50,100,0,150,0,0,80,0,10,0,150,0,0,100,0,0,50,0,20,0,0,10000,1400,0,0,0,20,25,200,50,500,500,50,0,10,11000,2000,0,0,0,400,0,500,1000,5,800,10,0,0,0,9700,30,100,25,20,0,0,0,0,0,10,0,0,10,1000,0,0,0,50,10,0,0,2400,0,50,400,300,0,10,0,400,0,2000,0,0,0,0,500,0,50,10,7000,500,100,0,0,0,0,0,0,6000,0,500,5,0,0,50,1500,500,100,50,110,100,9000,25,0,0,5,150,15,0,0,35,0,0,10,0,0,25,0,10,100,0,0,0,0,500,0,1000,0,200,0,0,0,0,300,6200,0,20,700,10,3500,30,0,2000,1200,0,30,0,0,2300,3000,50,100,0,0,0,0,0,0,0,1000,500,0,1500,0,0,50,0,500,7000,0,25,1000,0,0,0,0,10,0,0,0,100,0,0,0,2000,0,50,0,0,0,0,0,0,0,700,3000,10,100,0,500,1000,0,200,300,0,0,0,50,0,5,10,0,50,0,400,50,0,0,10,0,300,200,50,0,0,0,50,25,20,0,1200,30,0,0,25,100,0,500,200,3000,0,0,25,0,50,30,0,300,0,0,0,0,0,0,0,2500,0,100,0,100,20,600,300,0,0,10,0,0,10,0,100,0,7000,4000,6000,300,0,10,1000,1000,500,3000,0,0,25,0,30,150,0,500,0,1000,200,1200,100,0,0,2200,0,4000,0,3000,0,2000,0,200,500,0,5,50,0,75,5,1000,0,70,1000,0,0,1300,0,40,200,400,0,0,30,0,150,0,300,1000,0,4500,40,700,50,2000,0,800,20,0,20,500,200,4000,0,0,800,0,200,0,0,0,100,1700,15,20,600,0,3000,0,250,0,800,200,0,350,150,3500,5000,20,20,100,0,1400,1500,50,200,700,10,30,0,10,50,600,2500,2400,100,0,4000,0,500,100,100,550,100,150,350,1700,1500,0,0,0,0,0,20,300,0,30,10,8500,5000,50,0,0,1200,100,400,500,10,11000,1000,0,100,800,0,50,100,100,500,35,0,2000,1000,1000,0,300,4500,5000,1500,0,100,0,12000,700,40,0,0,500,300,200,5000,3000,0,0,0,0,0,100,1000,500,0,0,0,0,0,0,300,0,700,5,1500,3500,2500,1800,0,5,400,2000,1500,0,0,3000,500,1000,0,500,450,300,300,300,1200,6000,2000,1800,4000,0,0,0,0,500,0,500,1060,3700,1700,0,300,10,300,1500,1300,800,800,0,0,0,200,7000,500,800,20,300,1500,2000,0,50,50,600,100,10,0,700,600,1300,5000,3500,4500,2500,50,3500,800,1200,5000,500,100,0,0,1200,0,0,5,10,300,50,0,75,11000,1400,10,1000,1500,0,5,3700,0,2000,800,70,1500,6800,500,0,15,0,100,0,350,300,460,2500,175,200,0,0,20,1400,60,400,10,500,0,4000,200,10000,5000,20,2500,2000,5000,400,1500,0,500,15,500,800,3000,3200,0,4000,250,5,0,10,5400,4000,2000,8000,1300,0,0,0,0,500,3000,2500,0,0,200,500,0,0,100,0,2000,1000,1000,0,35,0,0,300,2500,3500,900,900,0,500,300,20,2500,400,50,0,50,0,1800,0,1100,0,0,200,5,1000,50,900,1600,3500,1500,0,0,0,15,0,300,1000,75,1600,2000,10000,1800,9000,500,5,1000,20,400,50,5000,18000,3000,900,0,2000,900,480,300,2500,150,300,200,200,1500,1100,4500,2000,5000,2500,0,20,0,0,500,0,1500,1000,50,0,50,1000,2250,1675,5000,1800,1000,500,0,90,0,1000,14000,6000,400,25,500,0,20,500,700,2000,0,15,300,0,150,1000,20,300,1000,0,0,20,500,3000,0,0,800,300,0,2500,1650,4000,2300,0,0,450,2500,0,100,10,0,200,200,2000,2300,0,2700,7400,1500,4000,200,0,1000,1500,1500,0,50,2700,500,3000,500,480,10,200,0,300,0,0,0,2550,1000,500,1400,100,0,500,4000,4000,2500,2000,1900,4,0,0,0,0,0,0,2000,1200,2200,0,10,7000,500,1000,4000,3000,1500,25,1400,1800,10,0,1000,0,0,0,0,6000,3500,1000,1850,10,1500,1500,1500,1500,100,400,0,11000,7000,20,750,800,3000,100,500,2000,2000,2500,0,0,0,0,0,0,200,0,0,500,3500,0,400,200,700,5000,2200,10,0,0,7500,1000,1400,0,900,1000,800,0,1200,7080,7000,1000,1000,1000,0,200,400,500,2000,2000,1500,0,50,0,1000,800,75,800,1000,1000,1000,0,400,350,10200,1300,0,0,2000,50,3000,3000,2000,800,1500,10,50,0,500,10,200,800,500,3000,2000,0,0,0,1200,40,4000,0,3000,10,0,0,4000,10,800,1900,200,4000,100,400,6000,5000,1400,2500,0,100,0,0,1000,35,4000,0,400,7000,5000,0,0,0,0,3000,10,3000,2500,1500,0,700,50,5000,0,0,200,0,0,0,500,0,50,100,2500,100,1000,4000,0,0,500,2000,250,7500,1500,4000,3800,3500,0,8,3000,2500,5000,2650,0,50,500,0,30,0,0,50,0,25,2700,2000,1500,2000,4000,5500,0,2000,50,50,0,0,0,25,25,1000,6000,1000,500,0,1000,5300,3500,0,0,1500,300,0,400,0,0,3000,0,100,0,100,150,0,0,1500,0,0,1000,0,50,1800,6000,0,0,300,2600,142,0,2500,4000,5000,1000,50,25,0,0,100,20,1500,100,300,800,0,0,0,0,100,1800,0,0,0,1000,2000,10,500,200,0,50,0,0,7000,100,10,0,1500,600,0,300,3000,0,100,250,4000,0,0,1200,0,300,1000,0,100,800,0,1300,7000,5400,0,0,500,2000,20,700,4000,800,0,10,300,5000,2000,1000,500,10,1500,0,2500,0,200,500,0,800,0,600,10,2000,100,30,4000,1000,1000,5,10,4000,15,25,0,1300,20,500,1300,200,3000,0,20,1100,500,10,100,1500,1000,1000,50,0,0,0,0,3000,0,30,500,700,10,600,0,0,500,1200,700,0,0,0,0,300,50,0,0,50,1200,0,0,2300,300,400,0,100,0,5,800,0,2200,800,10,0,200,2000,100,100,200,50,0,0,0,200,0,4000,0,300,0,30,0,0,0,7500,0,0,0,0,80,50,2,0,300,500,150,50,0,250,10,0,3000,0,0,0,50,10,1500,0,0,0],"coloraxis":"coloraxis","symbol":"circle"},"mode":"markers","name":"","showlegend":false,"x":[1500,0,50,50,50,150,100,0,0,200,1700,0,1800,50,500,0,0,800,500,5000,1500,0,2000,0,20,200,75,10,10,5000,1000,1300,0,0,800,1000,1500,1000,0,50,100,100,50,0,0,500,0,3500,1000,30,2000,1800,0,0,75,0,50,0,0,850,30,0,1000,0,500,150,0,0,10,0,800,500,0,40,0,0,0,20,0,5100,0,100,0,0,20,100,100,10,0,0,0,0,0,100,0,0,20,0,0,0,350,0,200,50,0,50,0,0,0,100,0,0,0,0,0,100,0,0,150,100,2500,0,0,100,30,0,40,0,5,25,0,0,0,10,300,15,0,0,50,0,1000,20,0,0,0,0,500,0,30,200,0,0,40,2500,0,0,2200,150,100,0,100,0,3200,100,0,0,2500,0,1400,20,100,2000,0,0,400,300,0,0,0,1500,200,0,3400,250,2000,1000,0,50,0,0,3500,0,2000,4000,50,0,9000,0,20,50,0,1800,100,400,400,25,0,0,30,0,400,50,0,0,20,0,100,1400,0,200,0,50,0,200,0,2000,100,100,50,0,200,10,100,1000,0,0,0,400,0,300,0,200,8000,1000,0,0,0,1200,2000,0,1000,200,1200,55,100,0,0,20,200,50,1500,10,0,700,0,20,2000,0,0,50,700,200,0,150,0,0,0,0,50,700,1500,0,0,0,30,0,25,10,50,50,1000,0,10,0,1000,50,50,30,0,300,0,10,50,2600,15,0,0,0,20,0,0,0,50,0,50,0,20,0,0,100,0,0,150,500,0,500,0,10,0,0,0,50,10,50,0,400,0,0,0,0,10,0,50,0,0,0,150,0,250,0,0,0,0,5,200,0,0,50,0,4500,10,0,0,0,50,100,300,0,0,100,40,0,0,0,50,0,50,0,0,100,0,5000,0,3500,0,0,4700,0,0,0,100,1000,0,0,800,200,3000,500,50,1600,10,2700,700,75,500,0,10,0,0,75,500,0,0,150,0,100,0,0,50,0,200,0,200,400,100,0,0,0,500,50,0,272,0,100,20,100,50,0,2000,800,2000,200,5,0,100,1500,200,400,0,0,50,100,50,0,100,7000,0,0,200,0,0,2400,700,25,7500,1200,50,50,750,0,0,3000,0,0,0,2500,6200,0,1000,0,50,400,0,100,2500,0,0,380,0,0,100,10000,2000,0,20,8000,0,1800,0,100,0,1000,300,150,0,35,0,50,0,100,50,0,50,200,0,10,0,0,500,50,1000,0,0,50,0,150,200,40,0,0,20,0,20,0,10,0,0,0,0,5,0,0,0,0,0,0,0,200,210,30,12,0,0,100,0,100,35,0,4600,0,0,20,10,0,200,0,0,0,0,0,0,0,0,0,10,0,500,0,0,0,0,0,0,10,0,0,0,0,2,10,20,0,50,200,50,0,1000,10,0,0,300,5000,0,0,50,0,10800,15,0,600,25,0,2300,7000,0,0,0,0,0,0,30,3000,0,0,0,3000,0,0,8000,0,20,0,0,0,0,50,5,0,40,50,0,14000,0,0,300,1300,1200,1500,1200,10,3000,600,0,10,0,5,1750,2200,10,150,0,50,10,4000,0,0,0,6,75,0,2300,0,0,750,0,15,0,0,5000,0,0,800,0,2000,20,200,0,200,0,0,100,0,2000,0,0,150,0,0,100,2100,1500,5,0,0,100,0,0,0,0,2800,400,1500,0,800,0,0,0,0,0,0,35,5000,720,0,500,3500,1000,0,20,800,10,150,300,350,10,350,1000,1000,350,0,500,400,0,100,5,1900,0,20,0,200,250,50,1700,0,10,0,600,800,0,0,500,0,4700,300,500,100,30,500,2400,0,0,0,0,200,0,2000,400,500,4300,1000,0,5,300,2700,0,0,2,0,40,50,50,50,15,1700,200,100,30,400,100,20,20,80,350,15,15,0,0,0,0,0,90,5,0,0,0,50,0,0,50,0,50,1160,0,0,0,0,10,0,0,0,0,0,20,0,0,0,10,50,0,2500,200,20,0,0,0,0,0,0,1500,0,0,100,0,0,0,0,0,200,0,0,0,150,0,0,10,30,0,50,50,20,0,100,10,0,50,200,5,120,0,0,25,0,25,1000,0,400,0,1600,400,100,50,1500,0,20,0,5000,0,0,0,0,50,150,1000,1500,0,6,0,0,5,300,0,10,100,400,0,500,0,0,0,0,0,0,0,0,0,0,0,350,0,300,100,9000,2200,0,1200,2200,0,5,25,25,8500,0,0,0,0,1000,0,0,800,1000,0,0,0,0,100,500,50,0,0,0,0,0,0,0,50,1900,0,20,100,2500,50,100,2500,250,50,500,0,800,4000,3000,0,1000,0,4000,500,0,300,0,1500,40,300,0,0,0,50,0,300,0,0,7000,0,0,50,400,4800,0,1200,20,100,0,50,500,0,0,0,0,0,2900,3000,500,0,20,0,0,0,500,0,25,0,1500,50,0,0,0,100,0,200,0,0,100,25,20,0,0,0,100,0,700,50,20,50,500,0,500,200,2500,0,4000,1600,1600,8000,300,0,0,800,0,0,0,3000,10,4500,1000,0,5000,0,200,0,80,1500,200,50,0,100,300,10,10,200,0,5,0,0,0,0,5,0,200,5700,0,0,100,0,0,0,125,0,0,0,0,0,600,0,300,90,0,0,300,0,0,200,10,0,0,5,0,0,10,0,500,0,0,0,0,600,0,0,0,0,0,0,10,0,0,0,0,200,0,5,5,100,1500,0,0,0,0,200,0,2,25,20,0,0,400,0,200,200,50,200,0,1500,0,0,0,0,0,0,0,25,0,0,0,0,150,0,0,5,0,0,20,7000,0,1200,0,0,10,0,0,300,0,10,100,0,4800,20,300,0,0,0,100,0,75,0,580,0,50,0,10,100,0,100,0,0,0,0,0,0,0,100,0,200,250,200,0,15,3400,200,20,0,0,300,0,1000,10,0,500,200,3000,100,50,1000,500,0,0,0,10,100,0,50,0,50,10,0,0,0,3000,0,100,30,1000,0,0,60,5,0,2000,500,200,3000,75,10000,50,2300,0,0,100,150,0,300,100,0,400,1500,20,0,0,3400,300,150,5,200,50,150,50,5500,20,100,100,9000,0,500,600,0,0,500,100,700,0,35,200,400,1500,1500,1000,50,0,0,0,1300,0,100,0,50,300,0,150,60,100,0,15,50,20,1200,0,1000,400,1500,5200,100,1500,0,500,0,0,50,400,0,1500,0,3200,0,0,2000,0,2000,300,0,6200,1000,4000,200,0,0,50,20,200,10,7000,0,0,500,0,0,20,100,0,0,50,100,0,500,0,0,30,50,0,0,5,0,10,0,0,0,0,20,0,50,0,550,10,0,0,0,0,0,0,0,0,0,0,0,200,0,0,20,0,50,60,0,150,0,0,0,20,0,0,30,0,0,0,0,0,0,0,0,0,0,0,10,0,0,0,0,0,0,0,15,0,0,200,10,0,100,150,200,0,0,20,0,300,200,0,100,1500,0,100,3000,1000,0,0,0,300,0,1000,0,400,30,50,0,7400,200,600,0,0,200,0,0,30,50,5000,0,100,2500,100,0,0,0,0,100,25,0,0,100,0,0,3000,500,0,500,4000,1300,10,2500,800,0,50,0,0,100,0,50,0,400,0,500,20,1400,0,2,3000,0,500,0,0,0,150,0,300,100,200,350,700,10,100,100,2000,0,400,0,0,0,1000,800,4000,1200,500,0,0,0,50,0,100,0,2700,300,2500,800,0,50,10,0,0,0,10,0,150,5,1200,0,0,300,2,4000,1500,40,100,0,1800,0,200,8,100,200,800,0,0,2500,0,1000,150,20,5,1800,0,10,20,0,0,0,2500,0,0,0,0,0,800,0,10,1000,1000,0,0,10,0,300,100,0,0,0,0,200,70,500,0,0,10,0,5000,0,0,10,0,0,3,0,700,50,200,0,15,0,0,1500,5000,7000,0,1000,400,400,5,200,0,0,0,200,15,0,6000,0,10,0,0,0,100,150,0,3000,100,0,120,400,175,50,200,0,0,100,1200,300,0,0,80,0,10,0,0,5,0,0,50,0,50,0,10,200,0,0,0,0,0,250,30,0,0,0,10,0,800,0,0,500,0,5,800,30,200,0,0,0,0,0,0,0,50,10,20,30,0,0,0,5,0,4,0,50,0,100,1200,0,3000,10,0,0,70,100,0,10,0,0,20,0,0,10,0,0,500,25,10000,0,0,20,5,0,100,0,0,0,0,37,700,20,0,0,0,0,0,0,0,0,0,0,0,0,0,10,100,500,0,0,0,400,0,0,200,0,0,100,700,0,0,100,40,2000,0,0,8000,0,10,0,50,50,10,5000,0,1200,1000,200,400,7,0,100,90,300,250,0,0,400,0,15000,0,100,2500,2,1300,3500,0,0,3000,4000,50,0,0,0,50,1800,0,0,1000,50,300,300,0,0,0,0,0,100,0,0,0,0,300,0,200,400,50,0,100,0,500,0,1150,0,0,0,0,0,40,0,5000,1000,20,1300,0,0,3000,0,400,0,1000,0,1700,300,100,200,2500,100,1000,580,0,0,0,3000,0,3000,0,900,0,10,5000,200,0,100,10,800,20,500,0,0,50,100,0,10,100,2000,800,0,750,1300,200,0,200,0,0,800,0,200,450,10,0,50,0,650,0,0,30,0,0,0,5,10,100,50,0,0,0,0,2500,0,0,0,0,0,0,50,0,0,75,50,0,200,500,0,400,3000,200,0,0,0,75,3000,0,0,0,600,0,0,0,0,50,15,10,0,40,3000,500,0,0,75,500,0,0,300,50,26,5000,0,0,0,30,1500,3000,0,200,0,1500,1700,50,4000,200,0,0,20,2500,1000,1200,5200,200,11000,0,0,0,100,0,0,50,0,100,700,0,0,0,0,0,0,3500,700,0,7000,15,50,0,300,0,0,50,15,0,10,20,0,10,0,0,0,0,0,0,0,0,50,0,0,50,0,50,20,1200,0,15,0,0,0,0,20,15,0,800,0,10,0,0,0,100,6000,10,25,50,50,0,0,0,0,90,0,0,0,50,0,0,0,0,150,100,0,0,5,0,50,150,0,100,0,100,0,0,0,25,0,0,5,150,1000,0,0,30,0,0,100,10,1000,100,0,0,0,5,0,2,1000,0,0,0,0,1800,5,0,0,0,10,3500,0,100,0,100,200,250,0,0,400,0,0,100,100,20,0,0,0,0,2100,5000,0,0,0,5500,500,0,0,0,2000,0,0,0,0,400,1500,0,0,0,120,0,100,0,500,100,800,0,0,0,0,0,0,0,0,0,0,100,5000,0,50,900,12800,3000,10,3500,100,6500,0,0,0,0,50,10000,0,50,7500,50,4000,100,0,0,10,3000,0,0,0,150,500,0,0,1500,0,1500,200,0,0,0,1800,0,0,0,200,50,50,0,0,0,10,200,0,10,1000,0,0,0,200,2000,0,200,400,0,1000,0,0,200,4000,0,0,50,3000,1000,3000,0,1600,0,3000,0,0,0,10,300,800,1500,0,30,50,2900,500,100,10,1500,0,50,10,50,50,15,300,0,1000,0,500,0,300,0,4000,900,100,100,8000,0,0,150,374,0,0,0,0,10,0,0,100,50,0,900,400,0,200,50,0,100,50,1000,350,100,500,1000,2400,3000,0,100,1800,500,0,0,0,10,200,30,0,500,7000,3000,1200,600,200,100,1500,0,4000,0,10,0,0,10,0,0,350,4000,1000,500,50,0,0,800,400,0,1500,15,0,600,5,400,4000,5000,0,0,0,10,500,30,0,0,50,0,0,0,0,0,0,50,500,50,400,0,40,20,0,0,0,50,0,0,5,1,10,0,100,60,1000,1000,800,0,10,100,50,0,300,10,2,10,20,150,75,0,50,0,0,0,0,0,200,100,0,0,0,0,0,0,20,0,0,0,100,60,10,0,0,50,15,0,0,50,70,5,0,0,100,10,0,0,5,0,0,10,0,0,200,100,0,50,500,300,75,300,0,0,0,100,0,50,400,0,0,150,0,200,0,50,0,8000,0,0,0,0,0,0,0,0,0,0,4000,0,0,100,10,0,2000,0,0,5,0,300,0,0,0,0,0,0,3000,500,400,2500,0,1200,0,0,8000,0,2500,400,1800,3000,0,50,0,0,100,0,0,3000,0,2000,10,15,500,300,0,0,800,4500,20,150,550,30,0,500,2300,2300,0,1000,0,0,0,0,0,25,100,250,1000,6000,1100,0,25,50,100,2000,500,0,0,600,0,0,1600,2400,0,30,0,5000,100,100,1000,200,10,0,7000,200,1000,500,5,0,0,200,40,0,600,1000,200,500,7000,200,50,0,50,20,700,25,0,0,150,0,0,2000,50,100,0,20,0,10,0,400,0,1000,0,400,0,200,1000,5,1500,0,100,100,10,400,0,0,2000,600,700,0,0,20,100,0,65,0,600,0,100,10,8500,0,0,0,600,0,1000,0,100,700,0,1500,0,0,500,100,3900,0,1000,0,10,2500,8000,300,0,2000,0,300,1400,1300,2400,0,90,0,25,400,0,30,0,5,2000,120,800,100,200,2600,0,0,0,0,0,0,2000,400,0,0,1000,6000,10,0,350,50,1000,0,250,50,500,0,3000,5000,200,400,3000,0,0,150,2000,8000,900,50,100,500,40,0,0,0,0,50,0,0,0,75,100,0,100,100,10,0,37,0,0,50,0,0,1000,0,0,0,0,0,100,100,0,0,0,100,4500,0,0,150,10,80,30,0,20,0,200,0,10,10,0,0,500,20,0,0,50,0,0,0,800,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,10,0,100,150,10,200,0,0,0,600,15,0,12,50,100,100,50,500,0,100,20,0,0,0,150,1200,0,200,0,0,0,0,0,0,0,0,0,0,0,0,0,0,10,0,200,50,35,0,0,25,10,0,25,0,100,0,0,0,10,30,1500,20,250,3,50,0,350,0,25,11000,0,1000,0,0,200,0,0,0,0,0,300,1300,0,20,50,0,0,50,5,0,0,10,10,0,0,0,3000,0,0,0,0,11,0,100,30,100,20,0,0,0,0,50,0,100,0,100,500,30,0,0,0,0,50,0,0,0,0,0,0,0,10,0,0,0,200,0,0,2000,10,0,0,0,0,500,0,0,0,0,0,600,0,0,100,10,700,50,200,4000,0,0,0,0,6500,0,0,0,2000,0,10,100,0,75,200,4000,50,0,1000,200,1500,200,0,100,2000,0,6000,2000,50,0,0,25,700,4500,0,0,0,500,0,20,0,0,0,0,300,50,30,5,1000,50,0,8000,0,200,0,200,0,0,0,400,0,300,0,0,0,100,1100,100,75,0,150,0,0,0,0,0,10,0,63,100,0,0,100,2500,0,50,100,5500,3000,0,0,0,0,0,50,0,0,200,400,0,100,2000,3000,4400,1000,200,9300,0,800,0,250,600,1800,0,0,0,0,0,200,100,3500,4260,2500,300,3000,3000,100,0,0,0,50,0,4000,0,4000,500,2200,0,500,100,50,550,0,0,0,0,0,800,0,1500,50,2000,0,2000,7,1200,0,30,1500,2000,2500,0,0,0,0,800,0,600,1500,2000,0,200,3500,0,30,10,0,1000,0,400,50,50,20,50,0,50,0,0,0,150,0,1800,3000,0,150,0,10,5,0,20,0,0,0,0,200,0,0,0,0,10,100,200,6000,0,50,50,0,4000,0,1700,300,2000,1500,0,700,750,0,200,100,900,10,20,100,0,200,0,0,50,0,100,50,200,15,0,1000,0,1500,500,30,100,50,200,1200,200,100,0,150,1000,0,0,75,50,0,2000,100,0,600,0,0,0,1700,0,200,0,0,10,0,0,0,800,20,2550,150,5,100,0,600,100,0,0,800,10,10,0,0,0,0,0,0,0,0,0,300,0,20,25,0,0,0,1000,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,100,0,0,0,0,0,10,0,0,0,0,0,30,200,50,0,0,0,0,3000,0,0,50,300,50,50,0,25,0,0,0,0,20,0,0,10,0,100,10,0,10,200,10,15,200,30,0,700,0,40,100,0,0,0,50,0,0,0,0,25,300,0,10,0,10,300,0,0,0,0,0,0,0,500,0,5,50,0,100,10,5,0,700,0,0,0,0,20,100,30,400,0,0,0,0,0,0,0,50,50,6800,0,0,0,0,10,20,20,0,100,0,0,0,0,50,55,0,100,0,0,0,5,20,0,0,0,0,0,150,0,0,0,0,10,0,0,0,0,1500,0,0,30,5000,0,50,200,50,0,0,0,0,0,0,300,0,0,0,100,100,0,30,0,0,0,200,0,10,0,0,800,10,0,5,20,0,1200,3400,0,50,100,25,0,0,200,200,0,10,0,0,1500,0,0,450,0,500,1000,1000,500,0,20,20,700,10,0,0,0,500,0,1000,200,0,3500,3500,1000,100,100,0,50,0,0,0,10,0,0,20,0,0,0,0,0,2100,400,0,0,0,100,25,700,50,0,15,10,0,200,0,60,5000,150,800,0,0,0,0,3000,10,0,0,10,0,0,200,0,0,1000,200,4000,0,30,0,0,0,500,0,30,1100,0,6000,300,2500,3000,200,6600,150,500,200,10,0,2000,200,200,0,0,100,0,2000,3000,5000,0,10,800,0,1,25,0,0,3,650,0,0,0,5,1500,0,0,0,0,0,4000,1000,200,0,100,100,100,1500,2000,5000,0,2,500,1200,50,100,400,0,0,50,0,0,0,300,300,50,600,300,500,3000,0,10,400,600,1200,1300,0,0,2000,0,0,1200,700,300,0,0,0,1000,300,0,2000,100,200,0,0,0,1000,10,1000,50,150,150,2000,0,1900,2000,2000,0,0,1800,0,50,0,1000,0,2000,100,90,50,100,800,50,3000,1400,10,400,2000,100,0,0,0,0,200,0,0,0,0,2000,0,0,0,1,400,0,1200,0,0,25,0,400,0,3000,0,0,0,0,400,75,27,40,0,0,400,150,10,0,100,0,400,80,500,0,1000,20,80,3000,5,0,0,0,300,5000,0,300,0,45,0,0,20,0,0,300,0,300,9000,10,500,0,100,0,0,0,0,0,400,1800,1500,0,1500,4000,900,0,0,0,5,4000,0,2000,2,4500,700,100,50,0,500,0,30,0,0,20,0,0,25,0,20,50,20,50,20,0,200,200,2,100,0,0,0,50,0,13,0,750,0,20,200,0,9,50,150,0,0,0,100,300,0,0,0,0,300,0,0,0,0,0,15,0,0,0,50,0,0,500,5,0,100,10,5,100,0,0,20,0,5,100,10,0,300,3000,0,0,0,900,0,0,0,0,1,50,0,20,10,20,50,0,0,200,0,150,0,10,10,0,0,15,0,0,150,0,0,0,5,0,0,5,0,50,0,25,0,0,2500,0,50,50,1150,0,0,5,0,0,0,0,0,200,10,50,0,0,10,0,0,0,0,0,0,0,30,1500,0,500,0,0,500,0,6700,0,0,0,0,50,200,1600,700,50,0,300,100,200,0,150,20,0,0,100,0,0,10,20,0,0,0,0,0,0,100,0,3000,100,100,0,3000,0,0,300,6000,1800,0,10,0,0,20,0,3500,20,1300,0,1000,50,0,0,0,1600,1000,0,0,10000,0,1900,25,500,0,0,0,10,0,150,2200,400,0,8000,10,0,0,5500,20,0,15,0,0,10,3000,10,0,4000,50,0,1200,0,0,0,0,0,0,0,0,250,0,0,0,50,0,100,0,0,0,0,4400,0,200,0,0,400,1800,0,5,20,2200,0,100,30,10,100,0,0,400,0,500,0,50,0,0,500,3800,0,600,0,0,50,100,0,3000,0,400,1800,200,700,0,10,0,0,0,5,0,0,0,0,100,0,425,25,1500,4000,0,19,1900,100,100,0,50,800,0,0,0,1000,100,900,200,10,500,10,10,0,200,150,1000,0,0,10,100,10,50,0,0,500,0,0,300,0,0,50,0,100,0,95,1000,800,3000,400,20,200,0,350,0,200,100,2500,0,85,10,0,0,10,0,0,0,0,0,200,0,5,0,0,0,100,0,15,0,0,0,0,600,5,0,30,0,0,0,0,0,700,0,0,0,100,0,0,0,0,0,200,100,15,30,0,500,0,75,0,20,10,50,0,100,50,50,0,0,50,0,10,100,0,20,0,20,10,0,2300,0,20,0,0,0,0,10,100,60,0,20,15,25,800,0,500,0,0,0,0,50,200,150,10,0,50,50,0,0,10,0,0,0,0,0,1980,50,0,0,1250,100,0,0,10,0,50,0,600,300,50,600,6000,0,10,0,0,100,100,20,0,0,0,100,150,15,0,0,150,0,25,100,50,40,150,0,0,0,50,10,150,0,0,20,0,0,0,0,250,450,20,0,0,10,50,35,0,5,0,100,10,0,0,50,200,50,10,10,0,0,0,300,200,50,1800,20,10,100,400,60,100,0,0,0,0,20,0,0,0,100,0,0,0,50,0,0,20,10,0,200,20,200,0,100,100,0,4000,35,1000,50,50,0,200,10,0,50,0,0,50,150,0,0,10,10,3000,100,100,350,0,200,0,200,100,0,5,5,0,50,500,0,20,0,0,0,75,0,100,300,30,70,0,100,0,500,0,50,0,0,0,0,200,500,0,0,1000,10,12000,0,0,20,0,50,0,30,0,30,0,0,50,2,200,100,200,0,100,30,500,0,0,0,2000,200,800,1800,100,50,100,0,0,100,800,5,700,0,0,1300,1000,3,10,40,2000,10,0,100,400,300,50,50,100,100,300,200,200,1500,3000,400,200,0,50,300,5,7000,10,400,0,0,300,100,30,20,800,300,0,100,10,0,100,0,3,1600,0,10,50,800,1200,75,500,2300,0,0,50,50,0,100,1600,0,500,2000,0,2300,1000,0,75,3000,0,10,30,100,1500,500,0,2000,700,5000,300,1500,1000,400,0,400,0,500,4000,5000,2000,0,100,0,0,0,0,100,150,1000,3000,2000,7000,300,0,3000,300,1000,5,500,0,50,10,0,450,3000,400,200,0,2500,300,7000,30,200,2,1200,3000,50,1000,2400,300,0,300,1800,6000,0,50,1500,0,2000,10,15,0,75,0,30,0,0,7000,0,5,0,0,0,3500,5000,400,300,300,0,5000,100,700,1000,0,0,50,7000,100,0,0,8000,6500,6000,10,3,1200,6200,5000,8000,100,800,0,200,50,5,300,2100,5600,3000,0,800,150,2500,2400,3000,3500,1000,0,2500,5000,3000,10,150,3000,500,1500,400,6000,200,9500,50,0,1900,3000,0,100,0,50,3500,10,7000,100,1000,100,2500,1200,3000,150,3500,3400,0,1500,200,200,100,1800,2000,100,8000,200,100,1500,1500,500,500,400,7000,1000,1000,2900,10,500,4000,30,100,8300,4000,1000,1900,10,1000,50,0,3,1000,0,900,1200,100,50,300,20,50,3000,200,0,75,5000,0,10,50,4000,0,0,50,100,0,0,8000,300,50,0,12000,0,200,0,0,10,0,0,0,0,0,20,200,40,1000,0,300,200,2000,500,0,300,100,0,2000,600,800,200,2500,1500,0,0,0,800,50,50,0,300,0,105,0,0,400,0,0,0,2500,50,400,0,1500,3000,0,300,100,0,50,300,0,0,0,1600,0,0,1000,0,300,10,1400,800,20,400,100,0,500,400,0,0,0,2100,4000,0,100,1000,0,0,0,0,0,0,50,0,4000,10,7000,30,100,3,0,800,100,100,20,0,50,0,500,2000,0,200,0,0,100,0,0,0,100,5,10,100,7000,50,75,13000,300,0,0,700,15,1200,0,0,0,100,100,0,0,50,0,0,0,75,0,2000,0,0,20,0,300,50,0,0,800,1500,200,40,500,0,0,800,5,1200,400,0,0,10,0,0,0,600,500,0,3500,1500,0,0,20,0,10,0,9,900,400,100,50,20,0,0,100,20,100,500,50,100,0,0,0,15,0,30,20,0,0,0,1500,0,11000,0,50,0,800,0,100,0,200,0,0,1200,200,0,150,400,0,100,0,0,250,200,0,400,0,0,0,0,0,0,0,50,0,20,10,0,5,20,200,0,0,6000,20,0,0,0,0,300,800,100,0,0,0,0,0,0,25,7,100,0,0,10,0,0,400,1000,50,200,8000,2800,10800,100,100,1500,100,7,1500,500,0,200,1000,1700,0,0,0,20,0,0,300,0,0,0,20,20,200,800,40,150,500,20,0,2500,2300,0,0,100,9650,300,300,50,200,0,0,0,2000,2300,6300,0,300,2600,50,0,0,10,3000,60,0,800,50,100,50,50,100,300,200,100,0,100,10,7000,0,0,5500,0,0,9000,700,750,750,10,1500,300,15,0,3000,3200,3300,600,0,1500,7700,5500,760,1000,0,20,2000,400,100,2,100,100,0,0,100,950,3500,10000,1500,0,500,500,1500,1700,0,500,500,0,1500,0,50,0,3000,100,300,20,50,100,0,0,20,10,10,0,1100,0,600,0,200,0,200,0,200,0,0,2000,30,0,0,0,0,0,0,3300,0,7200,300,1500,2,0,2200,500,800,0,500,0,0,300,1100,0,6000,10,900,2700,0,500,2600,1600,50,3000,2600,30,0,0,0,1000,10,1200,0,0,0,10,0,0,100,0,100,7000,20,3000,0,1000,50,3000,0,0,3000,2500,100,1100,0,0,0,1200,50,100,0,400,1200,4700,0,1500,300,1000,0,0,800,1000,0,2000,1800,3000,0,10,400,0,300,90,500,1000,0,500,50,2000,7000,0,1900,0,100,200,1500,50,1500,3000,0,0,1000,600,2400,7000,110,0,200,700,1200,4000,200,3100,3500,400,0,2000,200,0,150,2500,800,2800,0,0,4000,4100,0,400,2000,100,5100,1500,200,1000,1300,2000,500,3000,4000,0,0,100,4300,1600,12000,1500,1000,4000,0,1350,200,0,500,1400,0,0,1800,10000,100,17000,0,1000,3000,3000,300,3000,150,0,100,5600,100,100,400,2000,0,1000,3000,500,3000,3600,0,400,400,2300,800,2000,2000,800,0,800,12300,1400,1265,0,0,1500,200,0,0,20,1000,1000,0,0,4000,0,100,3000,0,1000,5000,0,800,5000,0,0,0,0,1000,400,800,1800,500,100,300,0,7500,4500,300,2000,7,4500,6000,0,8000,8000,1500,800,0,200,400,2000,0,3000,200,6400,1800,400,500,0,1000,3500,0,1200,200,2000,0,2700,3500,0,3500,8000,5000,2300,2000,30,90,3000,1500,1500,0,6300,0,50,0,1000,0,100,0,4000,0,0,2000,0,2000,3000,400,500,100,1000,800,700,4000,2000,2000,200,0,50,500,0,0,20,300,500,200,0,0,500,0,0,300,0,0,1000,200,0,0,6000,0,3400,0,0,0,800,0,4400,500,300,300,2500,0,15,0,300,100,400,0,500,2000,0,0,0,0,1100,0,0,0,500,0,0,0,100,0,3500,0,10,50,400,0,3500,0,0,0,100,700,5,100,0,0,800,1000,0,3000,20,4500,0,20,150,0,30,400,0,0,100,10,400,0,5500,0,200,50,200,0,0,25,3000,5,0,0,0,0,0,0,3000,400,2000,150,100,2500,700,5,0,100,700,0,0,0,100,30,1500,12000,3000,2500,500,400,0,3000,0,100,1000,10,0,2400,600,1000,50,1000,100,4400,10,0,5500,0,200,200,10000,1500,1000,50,0,7000,20,15,2000,800,0,600,5000,5400,700,800,5,30,10,2800,800,1200,100,1400,4500,10,5500,400,330,4400,10000,1000,50,500,500,2000,0,1600,3500,50,0,1500,100,4000,1200,0,0,0,100,0,0,7000,0,0,0,200,40,200,0,750,1000,50,0,800,25,5300,500,500,0,0,800,2100,5000,1000,0,1500,100,3500,500,3000,1000,0,300,1000,100,1000,150,100,1200,2500,0,0,3000,50,1600,2000,1000,800,3000,300,4000,100,1500,70,0,600,0,10,300,2000,0,1200,3000,0,0,0,2500,0,2000,0,100,500,50,0,1000,1000,150,100,5,1400,800,10,1000,3000,3000,10,6000,200,1000,100,0,0,0,400,0,1200,50,500,300,0,500,1800,0,0,700,9000,0,6000,0,20,0,7000,6000,400,10,8,100,2500,6600,0,0,0,3000,13000,0,100,0,0,50,0,400,0,90,0,10,90,600,0,100,1600,0,0,0,0,500,50,0,1300,100,6000,600,0,2,100,100,50,0,0,20,0,40,0,5,0,4000,0,0,2000,100,500,7000,0,600,1500,600,300,500,0,0,0,1000,0,0,10,30,25,0,200,1500,200,0,0,100,27,1000,0,0,0,0,0,150,0,0,20,0,0,0,0,150,0,1000,0,90,20,300,0,0,0,100,0,10,1500,0,20,0,50,10,1000,1000,300,50,50,30,40,50,500,200,0,5,15,0,0,4900,0,0,0,0,50,0,0,500,1500,0,0,3000,0,0,40,10,50,50,50,50,500,0,30,0,0,3000,200,0,0,300,100,0,0,1000,0,10,500,2000,0,0,0,0,6000,0,1500,50,0,0,0,1400,0,400,0,0,200,300,0,10,0,0,0,0,150,1000,0,0,800,0,200,0,0,500,0,100,0,500,0,640,20,5,0,0,300,0,0,100,1000,0,0,100,0,800,0,0,400,50,0,1000,50,0,300,0,0,250,0,0,0,0,0,0,0,0,2700,0,200,100,400,0,1500,0,0,0,3000,0,1200,0,1000,1100,4,0,200,0,20,0,300,200,6800,0,0,300,0,0,200,2500,0,15,15,0,1000,50,0,0,150,0,2100,1000,10,4000,4200,100,50,0,0,5000,2500,0,0,400,6000,0,150,0,100,100,1000,0,0,3000,0,0,50,20,300,700,100,0,0,200,400,50,300,0,75,100,0,300,0,1500,2000,0,0,50,50,0,0,1400,0,1000,20,0,10,0,300,150,0,0,0,500,3000,100,0,100,0,500,3000,0,0,133,0,500,20,30,300,3000,5000,500,3300,100,0,0,300,15,0,0,0,40,2500,20,0,3600,800,200,500,50,5,4000,900,200,0,0,500,50,1000,7000,50,0,1500,0,20,2500,2000,500,0,200,0,400,0,0,350,200,0,5400,0,0,1500,0,0,400,1500,0,100,2000,700,0,0,50,20,1500,0,300,0,5800,600,800,200,6000,30,0,0,2200,6000,0,0,3000,400,0,500,350,0,75,1200,600,5,3500,1900,1500,5000,2000,0,30,100,1800,50,35,0,0,0,4000,2000,500,0,1000,1300,600,300,1700,2000,1000,2600,1000,500,50,1000,500,7000,0,300,450,800,800,400,0,2000,200,0,1000,4500,1000,1200,15,150,50,500,8000,30,2000,5500,0,4000,520,5000,5000,1000,2500,0,0,300,1700,700,0,0,1300,0,1400,0,2400,10,5000,300,0,200,1600,4000,0,200,400,1600,700,0,2500,1200,1600,100,800,0,10000,0,700,10,200,6000,0,6000,6000,0,2000,2000,1500,4000,1200,0,100,3400,2000,2000,3000,800,0,2000,100,0,600,8000,2700,0,0,50,600,500,300,1000,300,0,50,1000,100,7000,0,1500,0,2800,3000,10,4000,2500,0,50,100,1500,0,1800,0,0,700,300,1000,4000,700,2500,8000,1000,2500,100,400,0,2000,20,200,0,0,0,0,500,0,2600,5000,0,0,7000,0,1000,900,0,800,180,0,0,300,5,0,0,20,300,0,200,75,400,2000,400,250,20,500,0,300,2000,50,0,900,0,1500,400,100,200,0,10,20,300,1200,2000,30,0,1300,0,1000,0,100,2800,0,2800,0,300,0,0,0,200,20,1400,200,0,500,0,0,0,5000,0,0,500,0,0,0,20,0,0,500,500,2000,0,0,800,0,200,150,50,400,20,0,500,2000,300,0,1900,0,700,100,10,50,250,300,500,500,3000,0,0,500,0,50,16500,800,6,0,0,4500,10,50,300,8500,0,800,100,100,100,200,150,0,3000,6000,4000,800,100,4500,1500,4500,50,0,10,0,0,0,1500,0,0,200,50,0,30,2300,200,0,0,20,0,100,1200,500,250,300,0,800,1000,0,1000,1300,1500,50,1400,350,6500,1000,0,3000,5000,700,150,2500,1200,0,2900,3000,300,0,500,700,100,800,75,0,0,8000,2000,4300,100,3400,900,1500,5,2000,0,50,50,100,20,400,4500,1800,0,5500,0,1100,0,1500,10,6000,0,3000,0,3000,100,400,0,1800,1500,100,4000,3000,1700,5500,100,3000,4000,0,1600,3000,50,100,0,0,100,1800,3000,6800,30,50,0,1500,6000,10,0,2200,1800,500,100,1000,30,0,0,100,3000,2000,100,1000,2500,8900,300,5000,150,2500,0,200,0,200,200,0,1800,0,0,5000,500,2000,0,50,5000,0,4000,100,50,700,800,200,6517,0,0,0,100,15,800,4000,5200,5500,1070,3500,0,500,0,7000,50,1500,7,0,700,0,300,0,400,900,500,2500,1500,50,500,3500,1000,1000,500,2500,10000,7500,3000,2000,2500,1500,0,11000,0,0,0,6000,2000,0,800,0,1200,2000,25,7000,2000,100,100,50,1400,5,1500,300,0,300,50,2000,0,0,100,150,3000,7000,7000,0,1500,1200,2000,900,0,0,0,3000,350,2000,200,14000,0,500,1500,50,0,500,7000,10,0,100,800,0,50,0,0,5000,7700,3000,0,0,2000,0,1000,500,6000,0,600,0,0,0,2100,0,400,50,25,20,8000,3000,3400,3000,10,10,300,0,0,800,0,5600,3000,0,50,7200,1500,50,50,9000,3000,200,4000,100,200,100,2500,3700,10,0,3000,3800,500,500,0,1000,1900,0,0,100,1000,0,0,200,0,10,0,100,100,200,0,1000,0,0,2000,200,0,15,400,100,1000,100,15,0,600,0,5,100,2000,10,0,0,0,0,1200,0,0,2500,0,0,1500,2800,20,0,0,0,0,100,0,0,150,50,50,0,0,0,0,6,5,3000,0,0,0,0,50,2,0,0,4000,200,10000,0,200,0,150,0,0,0,100,0,50,0,0,0,0,50,0,50,0,0,0,3500,600,30,0,0,50,0,0,100,500,6,0,400,0,0,100,1400,0,0,0,200,200,0,0,850,0,1500,0,0,0,1500,400,0,20,500,0,100,100,0,2000,1000,0,500,300,0,50,0,300,200,0,10,0,0,0,150,0,50,1000,0,100,6000,0,30,0,0,0,200,10,2400,800,200,0,500,5000,50,350,100,100,0,0,700,0,10,0,0,30,0,0,0,0,150,10,0,0,11000,300,0,20,0,1500,0,0,0,200,10,0,0,200,50,0,0,0,0,50,100,3000,2000,20,0,0,0,0,10,250,75,50,0,0,0,20,6000,100,100,100,0,50,15,0,0,0,0,0,0,500,10500,300,0,500,0,20,0,300,0,0,100,200,20,0,50,100,2,0,0,0,1500,5,100,400,6,0,0,0,100,0,50,0,30,0,300,300,0,12000,100,500,0,12,20,1500,0,0,1500,0,0,0,0,0,5000,150,100,1700,20,0,0,0,900,0,10,0,0,10000,0,0,0,400,75,300,0,50,0,2500,0,0,200,200,0,0,10500,50,0,1000,400,0,4500,200,0,0,200,6,5400,0,150,300,10,30,20,50,600,0,3,0,0,100,50,0,0,0,700,0,0,20,0,100,2000,100,0,0,0,0,0,0,150,150,250,500,0,20,0,0,0,0,0,10,0,0,20,0,0,0,0,300,50,75,10,500,0,0,100,5,6000,500,11000,0,400,0,0,0,2500,0,1000,0,0,0,0,5000,5000,450,100,500,500,0,10000,800,0,35,0,1500,1500,100,50,2200,0,3000,0,7000,0,0,50,100,0,0,300,1000,0,0,0,0,12000,6000,100,0,1000,0,3500,300,300,300,100,3500,200,7500,10,1500,3000,50,100,6500,50,0,50,150,5,100,300,5,0,0,0,200,2000,50,2000,500,1500,5700,0,1500,300,4500,0,100,0,5000,300,800,0,0,1000,1000,20,11000,0,0,400,0,0,2000,3900,9000,0,15,0,0,200,0,7000,2300,4000,0,200,2000,0,10,2000,0,200,700,0,0,0,200,0,15,0,100,50,2000,0,0,2000,6500,100,0,0,100,2200,1200,6000,0,50,8000,3500,300,50,500,0,2000,4000,300,0,1000,0,0,0,0,1000,0,9500,7000,0,20,0,0,800,4000,100,50,0,2500,0,3000,100,3000,2000,0,4500,0,0,250,5000,50,4000,1500,200,5000,0,2500,6000,4000,4500,10,3000,0,10000,300,0,100,1200,500,700,300,50,400,600,1500,3400,200,5,75,300,1500,0,0,500,1300,4000,200,400,1500,3800,0,700,0,30,0,9000,0,0,0,10000,3000,3000,6800,1600,5,4000,400,700,400,250,0,12000,2200,2500,1500,1000,0,10,0,1100,5000,0,500,20,3000,0,4000,4000,500,900,400,300,0,100,0,500,4000,1500,1500,0,300,0,450,3100,1900,500,1000,0,3000,900,2000,75,40,0,2000,5000,0,3000,0,0,2000,300,500,1000,1500,200,0,200,3000,0,0,100,200,0,400,2000,2200,10,0,4500,1500,1000,0,0,100,2700,10,0,0,300,600,800,1500,100,0,400,3700,0,0,1000,0,0,900,500,1200,0,3000,12000,2000,0,3000,1700,2500,2500,1000,0,0,1000,0,1500,1000,1500,0,500,0,2000,2000,500,0,1200,1500,50,0,200,50,3000,0,0,0,10,50,0,150,5,0,2000,4000,0,1200,7500,0,0,1200,200,3000,0,20,0,0,800,800,500,600,1000,20,1000,3000,1000,100,100,1000,25,5500,0,3900,150,0,3500,900,500,0,0,0,1500,10,0,0,400,800,0,2500,6000,0,300,0,200,6000,0,300,10,500,4600,0,0,500,2000,2,20,2000,0,0,4000,400,0,3000,0,7000,100,25,0,100,0,30,50,25,0,400,10,0,2500,50,5,0,100,2,50,800,15,200,0,300,200,0,0,0,300,50,100,150,100,20,0,10,150,0,2000,30,300,20,1700,2500,0,0,2000,0,1500,0,0,300,4300,0,100,1500,500,15,0,10,300,0,1300,0,0,150,0,500,0,300,1000,0,50,800,30,1000,2000,1000,200,350,5,250,500,2500,200,1500,50,0,25,5,0,150,10,800,0,1200,50,1500,13,0,50,400,0,0,100,50,0,0,0,1500,500,400,2000,0,100,300,0,10,150,300,0,1000,60,6000,50,200,0,400,0,7000,700,0,150,2100,0,0,10,5,200,350,1200,1000,2000,800,300,700,2000,4000,200,0,3000,200,150,10,3,700,500,800,6000,800,8000,1500,400,200,0,150,10,900,0,75,1200,0,10,0,1500,1000,0,0,1000,300,800,3500,0,700,0,1500,3000,0,10,0,0,0,2400,20,0,400,20,100,10,0,10,0,50,0,500,1000,1700,300,0,0,700,3000,20,3000,1600,130,0,3000,15,2500,600,1200,2,600,700,75,300,5200,5000,10,200,800,300,150,300,200,50,500,1700,250,1000,0,5,5000,6000,1600,5,500,0,0,200,2000,8000,0,0,100,0,0,0,2800,5000,3000,0,25,50,25,1700,0,0,0,500,2000,0,200,800,7600,0,30,0,2000,2200,2000,0,600,150,25,50,3100,8500,1500,5000,3000,0,300,6000,50,100,2500,3000,0,50,500,200,5,1200,3000,50,10000,0,600,100,1000,0,0,800,2500,400,0,0,3000,0,0,5800,1500,1500,800,100,10,5500,1300,0,500,400,500,0,0,0,0,1600,1000,0,500,4000,0,10,9000,0,11000,0,200,500,5000,1700,100,0,2500,0,100,3000,1200,0,900,20,100,0,0,100,0,800,100,0,4000,2000,300,0,50,400,0,0,1100,20,1000,0,0,0,300,10,0,300,10,12000,100,4000,0,0,0,10,0,0,0,0,0,0,0,1000,20,100,2,0,10,0,1500,0,0,300,5,0,0,500,0,90,125,6,600,0,0,5,200,100,10,0,0,3000,0,2000,0,15,15,0,0,100,0,100,10,130,1500,0,20,0,5,0,0,50,500,0,0,5,0,1500,2300,100,0,500,10,0,1000,75,400,4,40,1800,0,0,0,0,0,0,0,2500,1000,0,500,200,200,0,0,0,100,30,400,200,0,0,0,100,0,0,10,0,0,20,0,0,0,0,0,50,0,0,150,100,0,0,0,0,0,0,0,0,0,0,100,400,1000,0,0,3000,0,500,0,0,200,0,0,0,300,1000,0,10,0,0,0,50,15,5500,0,10,0,50,0,50,0,0,0,0,400,5,0,0,0,0,0,0,60,3000,0,2,0,40,200,200,100,200,50,10,100,0,0,0,1400,0,5,0,0,150,100,0,0,0,400,2000,50,500,0,50,500,20,0,1500,15000,0,0,5,40,400,75,10,0,0,0,0,0,300,0,0,0,0,0,5,300,0,20,0,0,0,0,0,0,800,5,0,0,0,50,10,0,10,25,400,500,0,200,0,20,10,0,500,50,50,0,0,1000,0,800,0,1000,4000,100,0,300,0,0,0,0,0,0,500,50,200,0,0,0,0,0,200,1800,50,200,0,0,1500,380,1100,50,5000,1500,600,1200,0,2500,50,1600,100,150,10,200,900,0,0,3000,300,800,600,400,50,0,0,0,0,0,0,200,100,1000,0,0,500,200,500,15,0,50,100,0,10,0,200,10,20,0,0,0,3400,0,100,100,50,250,250,3000,2000,2000,200,0,0,10,100,0,0,1000,0,800,0,0,0,2000,0,3,50,4000,0,75,0,100,75,120,2000,0,500,2000,400,0,0,100,50,0,10,150,800,0,1700,5000,11000,0,0,0,5,10,2000,2000,0,0,10,2500,0,0,4000,8000,0,300,300,3000,3000,0,5000,1500,1000,13000,0,0,0,50,1000,4500,500,0,0,0,200,1700,200,10,0,4000,100,0,2000,2500,0,300,20,1000,200,1500,0,4500,50,0,0,400,0,1000,300,3100,300,2000,10,0,0,500,0,20,0,0,1200,1000,0,1500,1500,100,4000,1850,2200,0,0,0,2500,0,1500,2200,300,1000,1000,13000,2200,0,3000,0,1500,700,600,6500,0,0,3500,1500,0,0,1600,400,0,6500,0,14000,600,2000,2100,750,0,800,200,0,3,0,200,1000,0,5000,5000,50,300,300,0,20,300,1500,0,0,0,1700,500,0,2300,3000,5000,1500,13000,2300,200,0,0,800,4000,1400,4000,800,6000,20,0,300,0,0,1000,3000,500,20,4000,700,4000,1500,1400,2500,2000,0,500,30,0,545,500,0,400,100,0,0,1000,3500,200,4000,5000,5000,5000,2700,1100,10,4000,1700,5000,2500,50,0,0,0,50,0,1500,800,2,1000,1500,500,0,0,0,800,0,20,0,10,600,0,5500,400,0,100,2000,1800,600,50,350,250,5000,1300,300,1600,1500,1000,3000,2000,0,400,0,1600,200,500,1000,600,0,3700,300,0,0,3000,3700,1300,100,2800,0,0,0,600,0,800,200,1050,3000,100,0,7000,3000,2000,0,800,0,2300,0,2000,6400,0,6000,1500,6000,0,200,4900,0,1200,1000,300,0,100,2500,800,300,1850,800,150,1000,1000,5000,4000,3000,50,1000,11000,25,0,0,0,0,10,4000,0,2000,0,0,3000,50,300,100,400,0,20,200,800,3000,0,50,150,1500,4000,0,300,0,4000,0,0,0,0,0,50,0,0,700,0,700,0,2600,5,2000,300,0,2,1500,2000,0,0,1500,100,2000,10,2100,100,0,1800,0,800,1900,4,200,0,50,0,400,2000,600,0,1200,800,500,5000,0,100,300,0,10,4000,800,0,2000,0,0,0,450,3000,0,3000,2000,5000,6500,0,100,25,0,0,0,3,5000,200,0,10,95,500,0,400,0,4000,2000,0,1000,0,100,500,600,250,2000,500,0,20,1500,0,500,3500,2000,100,50,100,0,300,0,0,10,600,70,25,0,0,3000,800,0,10,0,1400,200,0,500,2400,500,5000,50,0,600,2800,0,0,0,0,800,0,0,150,0,1500,0,4000,0,50,15,0,800,20,0,0,100,0,200,0,0,0,500,0,50,700,0,30,0,400,0,500,20,0,0,0,0,0,300,1900,50,0,350,0,0,100,150,2000,0,20,200,200,0,1000,300,100,50,0,350,600,50,100,100,300,0,0,1500,100,0,0,0,300,0,500,300,0,1300,0,10,0,5,0,75,500,0,500,4500,6000,100,200,0,0,10,500,100,0,0,0,400,100,11000,300,50,1000,0,0,0,0,0,0,300,500,500,400,1500,500,50,3000,0,0,400,10,0,0,300,100,3500,0,0,0,500,800,300,1200,5,100,40,2000,500,700,50,500,6000,0,50,4000,0,0,1000,50,100,0,0,0,450,0,0,15,500,0,8000,25,1200,2000,0,0,2000,1000,500,0,10000,0,5000,0,5,10,0,25,3000,0,1000,4000,200,800,200,0,3000,5500,0,0,0,1500,5500,300,100,6000,1500,500,0,4000,1700,20,0,15,6000,200,10,50,1000,2500,0,6000,0,800,1700,1500,2000,1700,0,0,0,600,1500,3500,15,800,1000,0,300,2000,3500,5,1500,1000,6000,400,0,900,1600,0,0,100,200,4500,0,0,1600,400,50,2500,400,5000,500,200,4400,10,1600,150,0,0,10000,0,0,0,20,250,400,20,0,200,800,200,0,0,0,30,200,1900,1000,500,50,700,0,60,1100,50,0,300,100,2600,3000,5000,700,0,600,1200,2000,1000,5000,0,0,1000,400,500,0,0,0,30,0,10,300,1500,0,0,50,0,0,10,100,50,0,0,800,10,100,0,0,3500,4000,10,30,175,0,0,1000,0,0,1000,0,200,800,2000,0,4500,20,0,0,0,0,0,0,150,80,200,600,1000,100,0,20,4700,25,0,0,30,200,200,100,1000,4300,100,0,500,200,0,0,0,0,500,200,0,20,200,1600,50,0,0,10,500,400,800,50,0,0,15,2000,0,2400,30,50,0,200,0,0,0,0,800,0,10,0,0,0,100,400,450,500,0,0,500,0,0,1500,0,0,0,0,0,50,200,5,0,0,500,0,0,23,15,0,300,0,0,1000,0,200,100,0,300,0,500,500,5000,20,1500,1000,0,50,0,100,0,1000,200,100,6500,1000,1000,0,0,25,200,150,60,900,4,0,0,0,400,5500,50,20,200,2200,800,300,1000,100,0,1400,3500,0,0,0,0,0,5,0,0,100,0,0,0,0,0,0,500,0,0,0,100,50,0,50,0,100,0,0,1000,0,0,0,0,800,0,0,1000,5,30,0,0,20,0,0,0,0,0,300,6000,0,0,800,0,0,0,200,0,100,0,500,0,2,300,0,0,10,0,0,200,50,1,0,50,8,50,20,400,0,50,100,0,0,20,0,0,0,10,100,20,100,0,1000,50,0,0,0,500,75,0,0,0,25,0,0,0,0,10,500,3000,0,200,0,100,0,20,500,0,0,0,20,13000,0,0,0,0,0,0,0,50,0,0,5,500,0,0,1500,0,10,0,100,500,0,5,0,200,0,0,0,20,150,0,800,0,0,75,100,0,0,0,0,150,0,2800,6000,300,15,50,0,0,50,0,0,600,0,3000,0,0,0,0,0,300,0,80,0,100,0,0,0,1200,0,0,0,100,50,100,0,0,100,800,0,50,4000,0,120,0,4000,20,0,15,0,0,0,25,0,800,2000,30,3500,180,50,500,300,0,3000,0,0,400,0,2500,600,20,200,0,0,30,30,4700,1500,100,0,0,2,3000,4900,0,0,5700,2500,2500,200,400,0,200,27,500,5000,100,150,0,0,800,0,10,10,500,0,0,100,100,0,200,0,500,0,0,1000,0,1000,0,0,0,0,200,200,900,20,100,0,400,400,0,0,150,1000,100,0,0,0,0,100,1000,200,0,500,0,0,50,0,0,0,0,0,200,0,50,0,0,3000,300,0,500,20,100,500,7000,10,30,600,0,0,0,9000,0,0,1500,50,10,1000,10,3500,400,0,0,0,6000,50,0,500,0,400,20,200,600,0,100,50,0,0,0,0,200,20,50,4000,750,50,0,0,50,0,0,0,4000,100,2000,300,700,0,0,200,2000,0,1100,1200,0,10,0,0,1500,800,5000,8000,1500,10,0,2000,10,10,300,0,50,0,0,800,100,0,0,0,0,1200,200,3500,500,0,0,0,50,10,500,0,3000,100,400,0,0,0,0,700,2500,200,0,200,1100,0,0,0,300,350,1000,5000,4000,3000,40,500,800,4000,3000,0,0,0,3000,1700,20,800,1000,500,1800,0,5,20,600,8600,10,0,300,1500,800,6000,0,0,0,10,0,50,800,0,0,800,10,400,1000,0,50,600,0,2000,0,100,1500,3000,700,150,6000,0,0,2000,1500,4000,800,100,0,400,2800,300,250,10,20,1800,1300,0,0,0,1600,10,0,100,0,10,100,700,200,4000,1000,400,0,0,0,0,0,300,5500,0,30,10,10,200,10000,300,1000,25,100,500,10,0,0,7000,0,0,500,0,10,700,0,10,15,200,0,1500,1,0,0,1400,1600,1500,10,3000,350,2000,200,0,3100,2000,0,20,0,200,0,0,0,500,400,5000,3000,2000,7,100,2000,300,0,100,0,6000,2500,300,1500,0,300,1300,1500,1000,75,0,900,50,4000,2500,500,1600,0,400,0,0,20,700,0,0,100,300,3600,0,2000,0,5,800,100,2900,1500,500,0,200,4800,4000,0,6000,200,500,0,300,3000,30,2000,1000,500,8500,600,200,400,2600,1800,0,3000,0,4000,5000,4000,1800,500,0,10,50,0,0,0,50,10,0,1300,800,90,0,500,5000,4000,1500,0,30,1300,30,0,20,2000,1100,800,1000,100,200,7000,10,300,1200,1700,2500,0,0,4700,3500,1500,200,0,700,700,1500,4500,14000,4000,400,0,200,300,1000,6000,4500,0,0,6000,4500,2500,0,10000,100,2500,1000,4200,2400,100,0,0,4000,0,150,0,1500,400,0,0,10,9500,100,100,0,20,150,1000,3000,200,500,3850,200,700,1000,1800,600,3300,1000,3000,0,8000,4300,3000,0,200,0,2000,2500,1500,30,0,0,500,0,0,1650,20,0,8000,2500,1000,0,1600,50,600,0,100,50,0,8500,0,800,15,25,500,1800,1000,150,3000,1260,10,1000,10000,300,200,0,10,0,100,300,2000,100,0,0,10,5,0,1500,10000,50,0,0,0,5,300,0,800,1,0,1700,2500,1000,3600,0,2400,3400,0,4100,600,5500,500,300,10,0,600,0,0,1700,0,0,200,200,0,10,1200,100,0,0,4000,0,500,200,0,0,1500,0,500,750,200,1000,0,0,30,300,20,100,100,0,7000,100,800,0,400,160,10,0,150,0,0,20,0,0,0,1850,2000,5,0,0,0,2800,1500,600,0,700,100,0,3400,1000,100,0,1000,400,2000,2000,75,0,0,0,100,100,0,200,5000,550,0,0,50,1200,0,0,2500,0,90,20,0,75,40,0,400,50,40,50,0,400,0,150,10,100,0,600,100,6000,50,0,100,1000,50,0,0,0,0,50,0,15,0,0,150,150,0,500,1000,500,800,0,1000,50,0,5,0,0,100,5500,15,50,2200,0,1500,0,150,5000,5000,10,6000,0,4000,10,0,0,10,500,0,200,0,0,0,100,1600,1000,2000,0,2000,0,50,300,500,3000,0,0,460,1300,1000,0,900,400,2400,1500,200,0,3000,0,450,6500,0,2000,300,0,50,200,1300,10,1000,0,0,100,0,1500,0,100,600,10,5000,7000,200,500,10,4000,0,6400,0,0,0,0,0,0,3000,0,0,600,0,6000,1500,1000,1500,55,0,2,5,0,30,0,0,1500,30,0,0,0,2000,7000,0,7500,0,0,2000,500,3200,0,500,0,1000,1200,0,8000,0,5000,1000,300,0,0,600,200,2000,0,0,200,200,3000,0,3500,400,0,275,500,1000,0,800,2000,3000,0,5,2000,0,100,0,0,0,4000,1500,1100,10,500,0,1100,3000,4300,0,0,0,100,100,0,70,8000,0,2000,3000,0,300,5000,100,900,2500,1000,20,0,100,2000,1000,70,0,2500,1000,300,2000,1700,2500,500,1500,10,0,700,1000,1000,0,2000,2000,50,0,20,500,600,30,0,3000,1500,50,7500,2500,3000,0,200,500,0,0,500,0,50,7000,1500,10,0,3000,2300,0,30,900,20,300,2000,4000,150,300,1000,2000,2000,2700,300,0,0,30,8500,2000,7000,0,2000,200,10,1800,5000,0,800,5,500,400,100,0,3000,50,50,10,10000,6500,0,2500,2500,0,50,0,2500,2000,300,0,0,2500,75,50,3500,20,0,1500,200,200,0,4000,0,0,0,0,50,10,2000,10,0,0,0,900,1200,25,400,900,1000,300,800,800,100,5000,10,0,400,0,0,0,50,100,0,0,0,10,200,75,3500,0,500,0,0,10,2000,500,100,0,500,4500,1500,50,400,0,0,200,0,400,0,9500,0,0,400,1000,0,0,5,100,50,0,0,1000,0,0,350,50,15,150,50,0,500,50,0,0,800,1500,0,0,100,400,100,0,2,200,50,0,20,0,0,50,0,0,0,1500,0,10,15,0,10,0,300,0,50,500,0,1000,0,50,500,0,0,300,100,100,1500,500,1500,20,400,30,50,2500,0,0,0,2400,10,30,200,0,25,0,500,0,200,0,350,4500,400,300,1000,2500,0,0,1000,0,0,1000,0,80,300,10,0,100,0,200,8,0,30,10,800,1000,0,0,0,350,20,0,20,0,0,0,500,0,0,0,10000,1000,10,50,0,0,0,5,200,10,0,0,1000,2200,0,10,5,0,0,1000,0,800,0,0,0,20,0,0,0,200,0,200,0,20,250,50,20,300,0,0,0,0,50,0,100,0,0,1500,75,0,0,40,10,200,0,50,0,100,10,70,200,0,0,10,30,0,200,5,0,10,50,150,0,0,0,2000,10,0,0,25,40,50,0,5400,0,200,0,10000,50,0,0,0,0,400,0,5,0,6000,0,100,1000,0,100,0,0,10,300,0,0,100,100,20,200,1200,0,0,0,600,0,0,300,3000,0,0,800,800,0,10,50,3000,100,50,50,0,0,0,5,0,150,6000,0,20,0,0,0,0,16500,0,50,600,0,300,1500,20,200,0,200,0,0,0,500,0,0,0,200,3000,50,6500,50,500,0,500,10,1200,800,0,0,10,0,4000,0,0,100,0,40,0,50,50,75,0,25,200,0,0,0,0,0,0,10,0,50,2500,0,10,0,0,4000,0,5500,50,0,0,50,0,0,0,0,0,2000,600,100,25,200,1500,0,50,0,0,50,1500,0,4850,0,40,500,0,0,100,0,50,10,10,0,30,3,2500,800,0,0,250,50,0,25,200,75,4500,0,0,125,7000,200,20,300,50,0,0,0,200,2500,0,1600,8000,10000,30,600,0,0,0,11000,2,0,10,0,0,0,0,0,4500,0,0,0,20,0,0,125,1500,0,100,3000,200,0,3000,150,1200,4000,20,1800,100,100,0,10,600,30,100,35,1,0,20,800,0,250,0,0,300,5000,1200,50,500,0,500,0,7000,2000,0,2000,1000,7000,2,100,50,2500,1300,0,100,0,3000,3000,300,2500,3000,600,100,3000,11000,50,3500,0,2000,5500,2500,2000,0,0,400,0,700,0,0,0,700,6000,0,100,0,0,0,5000,0,500,100,0,2,0,200,0,0,12000,0,50,3500,0,0,100,0,300,100,0,0,800,1200,5,20,0,10000,200,150,0,3000,0,20,0,1700,6000,30,0,2500,0,250,200,4000,4500,0,5,50,7250,0,0,0,4500,2000,9000,0,0,50,200,3000,50,0,8500,15,100,0,6000,4200,600,1500,4500,0,0,10,0,600,5000,2300,3500,0,0,1000,100,200,0,1200,7000,200,5000,4000,0,100,7000,200,2000,3000,0,0,20,1000,1200,400,0,0,200,1000,150,0,0,900,5000,0,0,800,7000,500,10000,420,6000,200,30,6000,0,9000,400,50,0,1500,10,1000,1000,700,0,1500,500,0,1000,15,3000,0,10000,0,1000,250,10000,0,1700,0,2000,1500,0,400,200,150,700,50,50,3500,0,2000,0,0,100,10,1000,3000,3000,1000,1000,400,50,0,1000,8000,0,200,0,0,4000,15000,1500,3000,6000,0,7000,1500,500,1000,0,4300,0,1000,300,1000,1100,8,0,6100,1000,200,100,100,50,500,20,2000,2300,2700,500,2400,2400,0,2500,1900,500,5000,3000,0,800,4000,0,4000,2500,1200,1,0,650,0,1000,0,0,1400,2000,1000,0,12000,1500,0,0,500,100,800,2000,1500,2500,5,200,0,200,3000,1500,4000,0,0,0,300,100,800,400,0,1200,500,2000,2000,200,0,2300,300,100,500,0,1000,5,0,5000,4500,9000,2000,1000,1300,0,3000,5000,50,20,0,0,4000,100,1500,400,200,2500,5,0,100,500,1200,20,1800,0,500,7500,750,0,2500,0,8000,0,5,300,4000,150,1000,2000,200,34,100,3000,2000,2000,4000,4000,0,1700,9000,1000,3000,1000,2100,100,0,4000,2000,0,0,0,0,700,0,2400,1500,20,6000,100,0,0,0,7000,5000,150,1300,6000,5000,1200,100,0,2500,100,6000,2200,0,500,50,200,0,5000,1500,5000,6000,500,1500,50,4000,0,600,5000,4000,800,100,0,6000,3000,10,0,2000,50,74,60,800,0,0,0,1400,0,50,0,900,600,300,2000,0,2000,10,1000,10,500,2300,6400,1500,300,0,40,1000,0,1200,0,30,500,1000,500,300,600,3300,8000,4500,300,5,0,50,400,1000,500,4000,400,1500,1500,0,300,1600,5,0,50,0,100,0,400,0,0,0,2000,0,200,100,0,0,1000,0,20,0,500,0,0,600,0,200,20,50,0,10,0,300,0,2000,0,0,600,500,0,0,0,1000,30,0,0,500,500,25,25,0,1500,800,900,0,5,0,10,0,0,1000,5,400,0,400,0,200,200,0,0,150,0,0,2500,0,0,600,350,0,0,50,10,50,0,0,800,400,400,100,0,1400,0,0,200,0,0,1500,750,10,0,0,1000,400,200,0,0,150,0,150,0,0,1500,50,100,1200,820,5000,0,0,1000,0,0,0,100,0,0,0,0,0,0,1500,0,0,0,500,10,5,2000,20,0,40,20,200,0,0,150,1500,300,0,0,3,1000,0,0,0,100,0,20,30,1000,10,1500,200,0,100,50,1000,200,300,0,0,0,10,900,1000,400,10,1000,1500,0,15,20,300,0,900,300,0,0,100,0,0,0,0,300,200,100,800,0,1000,0,0,100,200,0,10,150,300,1500,400,200,0,3000,100,1000,50,250,0,600,1500,50,3000,900,50,30,3000,1700,800,0,200,0,10,0,100,3000,1000,500,50,0,2000,2000,1000,20,2000,10,900,4800,3000,100,0,0,1750,0,0,10,0,3000,200,0,0,100,15000,0,300,0,5100,700,50,6000,6000,20,0,300,100,0,500,100,1500,500,2500,0,1000,0,0,700,0,40,40,1500,3000,200,5000,0,1000,300,2000,1500,100,50,200,900,500,1000,0,560,0,0,3000,3000,30,0,0,100,800,0,0,50,2000,200,3000,0,0,50,0,0,800,2500,0,40,500,0,1500,40,3000,350,4200,850,1000,2700,1750,3000,0,0,0,2000,0,400,200,200,0,7000,300,2500,200,0,0,0,0,0,2200,1500,50,10000,50,0,1000,50,50,10,0,20,4000,6600,600,0,3000,0,30,0,200,4500,500,4000,5000,0,3000,2000,0,25,600,7000,1000,1,1350,3550,1500,50,0,10,800,3700,50,0,0,300,0,800,500,1700,1300,0,500,1000,300,1300,1500,0,500,0,100,0,10400,300,2500,50,0,2500,1700,1500,0,0,10000,1200,1500,1500,1300,2000,7000,50,1500,50,5600,2000,50,7200,800,3000,10000,0,4000,3000,5000,10,0,800,0,0,0,0,0,20,800,15,0,2000,1600,3600,2000,100,50,0,0,60,800,4000,3000,500,450,1800,9000,2500,1000,1000,1400,0,500,600,700,1000,0,1200,3000,0,10,100,1000,1000,6000,30,11000,0,500,0,0,0,5000,0,3000,20,4000,2800,0,100,900,500,100,200,400,20,2000,50,7000,0,50,400,0,35,10000,10,4000,0,300,7000,10,100,8,50,1500,0,300,500,3300,0,0,4000,50,400,380,400,1400,5000,0,0,60,2400,6800,0,0,0,4500,50,20,50,4000,3,800,0,0,0,100,0,50,0,0,0,100,1000,4000,3800,3500,0,10,0,200,0,0,4500,300,0,0,10000,0,0,400,0,100,0,0,200,50,3900,50,0,100,2500,0,0,50,3000,0,100,30,5,10,200,0,100,6000,0,0,1500,600,0,0,1000,0,10,2500,75,0,5,0,50,150,100,25,0,1200,250,200,300,0,100,50,0,25,1200,1900,600,0,1000,6500,50,20,2,200,50,0,2000,200,100,600,0,0,0,50,100,50,800,500,1500,0,200,0,0,15,0,0,5000,10,500,0,0,0,600,0,0,1100,50,0,20,100,200,200,300,500,0,300,50,50,300,150,0,0,0,2500,75,200,0,0,150,0,200,0,2000,0,0,4500,0,0,0,12000,0,1500,20,100,10,0,300,0,0,10,20,20,6000,0,200,100,15,0,0,0,0,0,40,0,50,0,0,1000,100,0,20,0,0,0,3000,2000,20,10,2400,0,0,0,0,0,0,150,0,0,0,10,50,0,0,50,0,0,0,0,0,0,0,1000,0,0,15,100,0,0,0,5,5,0,20,0,10,0,10,0,0,200,0,0,600,0,9500,2000,0,0,500,0,0,1400,0,0,0,0,0,0,0,0,0,20,5,5,0,0,0,0,10,10,200,50,100,200,30,0,10,0,0,600,0,10,0,0,0,300,0,10,500,0,0,0,0,20,0,0,3000,0,0,0,0,0,500,1400,500,0,25,0,10,0,200,500,350,0,800,20,0,50,50,0,0,50,500,40,0,1000,0,0,100,150,0,0,0,0,0,100,0,0,0,50,0,20,100,0,0,1200,150,30,200,300,60,0,500,10,0,0,11400,0,0,50,0,1000,0,300,30,50,0,0,0,0,0,0,10,0,50,800,0,50,0,0,0,0,0,500,0,5000,100,3000,100,200,0,500,700,50,0,20,7500,0,900,0,0,0,5,0,0,30,1500,0,200,0,0,0,0,10,0,600,0,0,0,5500,50,0,0,0,0,0,5,0,0,0,0,10,0,0,3000,0,8,0,0,0,0,800,100,0,0,0,0,0,13,250,100,0,0,1800,10,0,0,9000,150,300,0,0,1300,300,150,1500,200,0,0,35,0,100,125,50,500,80,2500,250,0,100,0,0,20,15,0,20,1000,30,0,50,0,3000,20,0,800,0,25,1200,800,0,0,0,0,0,0,0,0,1500,500,5,100,0,50,0,50,800,20,500,0,0,0,5,500,150,0,100,50,600,0,20,0,2400,5000,0,0,0,0,20,7000,0,0,0,0,0,0,0,0,2500,100,0,500,0,50,300,100,1000,0,300,700,0,1900,0,10000,25,200,0,100,0,50,0,500,50,0,0,0,1000,2400,10,1000,2000,0,0,0,200,500,1000,10,0,0,0,0,0,100,20,0,0,30,0,100,0,0,0,1500,0,100,25,1500,0,100,100,0,2000,0,25,200,0,2448,0,2500,3500,150,6100,0,0,300,0,3000,0,0,0,0,50,0,0,0,200,0,3000,0,0,0,300,800,50,200,800,50,10,400,0,100,0,0,1500,0,15,850,1100,25,0,300,0,6000,0,100,5,20,10,50,1000,0,500,50,0,800,900,3500,700,3800,0,3000,0,300,0,600,2130,0,7000,50,0,200,150,500,0,20,1000,0,0,0,800,15,0,0,2500,200,0,0,15,3500,1000,0,0,50,500,10,0,1000,100,1500,1000,4300,50,0,5000,1980,10,200,0,0,8700,5,1000,0,0,1800,4000,2800,4000,500,400,15,300,500,800,500,1500,2500,1500,2500,1200,0,2500,500,1500,2200,2700,0,0,0,20,3500,300,800,65,2000,4500,0,0,10,900,75,700,0,9000,4000,1500,0,350,3400,800,400,500,3000,1000,4000,3300,2200,0,3300,3000,0,1000,50,50,0,10,2000,1700,1500,400,100,50,0,100,100,15,0,2000,10,500,15,50,150,0,0,50,200,0,300,0,1500,0,75,10,0,0,1800,2200,0,300,9500,0,500,1000,500,3000,0,0,5500,1350,4000,2500,1500,2000,4500,0,9000,270,500,300,900,2500,0,5,0,350,200,700,1500,8000,2100,260,300,1000,1000,5400,0,350,1000,2500,2000,1500,50,0,30,1000,1000,400,300,1000,2000,3000,0,200,450,8000,4000,1200,1200,10,4000,0,400,10,0,7200,0,1000,0,0,0,0,2000,200,0,800,0,0,200,800,2500,3300,3300,700,0,800,0,900,6200,5500,3300,0,0,1500,200,4500,1000,1000,400,4000,5000,1500,200,700,300,7500,2000,500,2500,0,0,400,50,500,50,1000,50,100,7000,50,3000,3740,2530,100,1000,0,1200,6500,6000,30,1000,1000,0,3,500,100,2600,1540,1500,100,2000,200,0,3400,5000,3000,10,400,0,3700,50,0,100,3000,0,1500,4000,6000,0,700,700,300,7500,0,2200,0,3000,400,100,0,800,500,0,4000,8000,1000,0,30,900,3,0,0,50,0,500,15,2000,0,450,7000,1500,0,200,0,1000,13000,5000,0,500,8,0,300,900,400,500,500,900,7000,2200,1200,0,0,4000,1900,2000,0,150,0,30,0,1000,500,1900,25,250,0,4000,500,900,3000,2500,8000,0,1500,0,4000,0,200,0,1000,3000,0,0,0,500,150,400,150,700,4000,4500,50,800,1000,200,0,5500,1800,50,6000,300,900,2000,3000,0,4000,2200,5000,0,100,1200,10,3000,2850,0,0,100,2000,4000,0,0,400,200,700,0,50,0,100,50,5000,1000,0,25,0,100,14,50,5500,0,0,100,1000,7100,600,1000,500,1200,50,0,500,200,2300,1000,100,0,0,200,3000,250,500,10000,0,20,300,0,4000,0,100,2000,100,75,2000,0,1000,300,500,3000,0,500,3000,2000,1500,0,5000,3000,3000,0,50,20,2000,2000,200,200,2000,0,0,200,3000,3800,0,0,0,500,0,0,10,250,200,30,50,500,70,10,600,0,0,300,300,0,2000,50,350,12000,0,6000,300,0,3500,0,0,2000,1000,650,200,0,0,0,20,1200,200,0,700,0,500,100,8000,2700,0,100,0,0,0,3000,0,700,1500,200,0,30,300,50,0,100,300,1200,200,0,1000,0,5,0,0,0,0,0,0,3000,200,0,0,0,200,0,0,10,30,520,1000,2000,0,100,0,15,1000,25,100,0,0,0,0,75,0,50,0,0,0,0,0,700,0,400,0,100,0,0,50,10,800,1000,200,1200,0,300,1300,0,0,50,0,500,50,30,400,50,75,50,40,100,50,0,0,100,0,0,10,200,0,100,3000,300,0,10,50,0,0,200,0,0,0,0,15,10,0,0,200,0,50,0,100,0,0,100,100,50,0,3000,2000,0,250,100,200,0,0,400,10,0,100,0,0,500,200,1500,0,0,2000,0,500,3000,1000,0,200,100,100,9500,6000,2500,0,1000,0,800,0,1000,0,200,800,100,3000,0,300,100,50,4100,7000,50,4000,0,1000,0,5000,0,0,8000,2200,1400,2800,2000,2000,6000,10,100,5,100,0,16000,10,5500,5,300,1000,0,3000,0,3000,0,10,0,2000,0,0,75,6000,5,10,0,6800,4000,0,2000,10,0,0,3000,440,1200,4000,4000,100,100,0,1000,1000,150,100,0,600,0,0,0,10,7500,50,0,1000,0,1500,0,0,500,2700,0,1500,400,1000,0,0,7000,3000,750,0,100,2000,0,0,0,0,0,1000,200,0,200,50,5,500,5000,0,0,300,0,0,500,500,0,0,100,20,0,50,30,300,1200,0,500,0,3000,0,30,700,0,4300,2000,6500,1500,2000,800,10,250,1800,14000,1000,20,200,25,200,0,0,0,3000,200,200,25,0,75,500,0,400,6000,3000,0,400,400,7500,5400,0,0,150,3300,5000,6000,50,300,50,5,3000,20,0,40,0,500,25,0,2500,4500,2000,3000,300,0,2000,2600,1400,0,500,6700,200,500,25,50,0,100,1400,0,0,0,20,0,4300,200,0,1000,400,3100,3000,500,400,4000,1800,400,0,500,100,0,1200,2000,0,3500,3700,200,50,4000,2500,10,200,10,3000,2500,4000,0,3000,400,2000,600,2000,10000,2000,3500,3000,50,500,4000,1500,3200,4500,1500,0,4400,4500,0,10,3800,1700,1200,3000,5000,2100,1000,10,0,0,0,6000,3000,2500,0,500,0,3000,0,1800,2500,0,3000,0,20,50,5200,2500,8000,3100,5000,5500,3500,4500,3000,1300,100,800,900,150,500,0,1300,2000,400,0,20,20,150,3000,4300,2500,0,25,0,400,4100,1500,150,0,0,0,50,1000,2200,500,0,100,0,0,100,50,0,500,8000,10,0,1800,5000,700,100,100,50,2300,2000,2800,2000,0,300,0,1400,2500,0,10,0,200,300,0,11000,100,0,0,300,50,1000,0,800,3000,0,8000,2000,1500,1800,0,30,0,100,7000,0,50,0,100,6500,2000,400,0,800,200,0,50,50,0,400,1800,0,0,10,50,0,1000,4000,0,0,0,200,1800,0,5000,0,10,10,100,800,4000,100,0,2000,3000,400,0,200,5,0,1000,2000,50,450,2000,0,0,2500,3600,0,0,1000,0,30,10,10000,0,500,50,10,900,0,0,0,150,100,3000,700,15,0,300,500,0,500,0,0,7500,6000,0,25,5,1000,0,300,0,0,15,25,50,0,0,0,0,0,0,10,10,10,0,0,0,20,0,5,0,0,0,100,0,0,0,10,100,2500,0,1600,400,50,1450,0,50,2500,100,4000,0,200,500,100,300,0,8000,3500,3000,0,100,0,1200,0,800,0,4240,190,0,2600,0,0,1500,0,0,200,30,400,0,5,0,0,4000,200,100,0,50,0,500,0,50,400,5,0,10,5,0,10,0,1200,0,0,0,400,0,1000,0,100,0,10,100,0,100,300,700,0,14400,300,0,0,0,0,0,0,0,100,1000,0,0,50,0,0,0,30,0,20,25,300,50,0,0,0,0,300,1500,0,0,1000,0,0,300,0,0,0,0,0,500,0,10,200,0,0,50,50,3000,0,400,1000,0,0,800,0,0,0,500,100,5,0,0,500,100,0,10,50,0,650,0,0,0,0,50,0,0,100,100,100,300,300,0,3000,50,0,0,0,100,0,0,0,0,0,0,0,0,15,0,500,0,0,0,0,0,30,0,50,50,0,50,90,50,500,50,0,0,1500,50,10,50,0,0,0,0,0,1500,0,0,0,100,11000,0,0,0,0,0,0,20,400,1600,10,0,0,300,0,1500,30,0,20,0,2700,800,0,1750,0,0,0,0,0,0,0,500,0,500,60,0,0,50,0,100,0,0,0,0,30,10,2,0,0,10,0,0,20,10,0,0,10,0,10,100,450,0,0,0,2500,200,1500,0,100,0,500,0,0,0,0,0,10,50,0,0,0,2000,0,0,1500,0,150,300,8,30,10,25,0,15,50,300,150,100,500,0,0,50,0,0,0,500,50,0,600,300,1000,0,50,0,0,0,0,0,800,0,0,4000,0,100,200,0,0,0,0,15,0,0,0,0,100,10,0,10,0,0,2000,0,100,0,300,400,0,1000,0,500,100,550,0,0,100,0,600,100,0,0,350,0,0,100,0,5,0,100,700,300,450,500,8800,5,400,0,0,0,0,0,0,100,200,0,0,0,0,1000,15,10,0,50,0,30,2000,12000,0,5,0,170,3500,0,0,0,0,50,3500,5000,0,0,1800,583,0,0,0,0,0,0,50,300,0,0,3400,0,0,10500,250,0,50,200,200,90,7600,1000,50,20,2000,50,0,0,200,0,50,13400,100,10,0,0,100,0,0,20,0,0,0,8000,3000,400,10,1500,4000,0,0,300,100,40,0,7000,3000,20,0,0,20,0,90,200,0,200,0,0,25,500,50,0,21,0,500,2000,0,100,0,50,400,0,5,0,400,0,0,0,0,50,150,0,50,4000,0,0,100,0,0,10,200,0,0,0,100,0,300,0,50,0,1000,3000,0,0,200,15,0,0,50,0,2400,0,0,2000,0,0,900,10,0,2000,0,0,1500,12000,500,0,0,0,6500,0,0,500,4000,0,500,3000,500,0,20,0,0,150,0,0,0,0,300,300,2500,2000,10,0,3000,300,0,11400,100,0,6000,15,20,0,6000,0,50,900,0,0,0,0,0,10,10000,0,0,10,0,0,4000,50,0,1110,500,0,0,9500,2200,0,0,100,5200,75,0,0,2000,4000,0,300,0,50,500,30,50,0,300,0,50,50,0,0,0,0,10,0,800,500,0,1,0,150,400,0,0,300,15,0,5,30,1000,400,2300,300,300,0,0,50,20,50,2000,2100,0,200,0,3000,10000,500,0,500,75,0,250,8000,3500,0,2500,0,0,0,300,3000,0,0,10,20,0,200,500,20,20,400,0,0,3000,10,100,0,2000,2100,300,2000,0,50,6000,2100,0,15,0,15,1100,0,500,500,1500,1500,0,50,750,500,2300,6800,0,0,3500,4000,0,0,50,800,10,1800,2000,50,0,0,0,50,0,2900,300,1500,3000,0,10,4000,0,0,600,3000,200,500,100,200,0,3,11000,50,50,0,0,0,0,800,0,0,0,0,15,3000,0,0,100,0,1000,0,300,300,1300,3000,4000,0,0,150,2000,1000,1000,6000,1500,3000,0,5000,1200,2500,2500,50,20,100,500,800,5500,0,0,0,0,3500,0,2000,0,300,0,1000,8000,1500,1200,3500,2300,0,0,100,200,4000,4000,0,3500,1000,3000,50,2500,1700,4000,500,0,100,3200,2900,1400,11000,2250,3000,800,300,400,3000,1000,0,200,1400,5,0,400,0,2500,50,50,1000,0,0,1000,800,50,3900,10,100,50,2000,0,5500,1000,400,0,300,0,500,0,500,700,3000,2000,1000,0,2500,6000,0,0,4000,500,5000,4500,700,0,0,0,0,8000,4000,300,800,2200,3000,3500,0,0,5000,1600,100,11000,400,3000,6000,0,4000,250,0,1000,400,15,12000,2000,2700,1000,200,0,8000,2000,8000,0,3000,2400,11000,6000,300,0,0,0,1500,100,10,500,1000,900,0,5,1500,400,3000,1000,50,3000,0,0,4000,10,0,0,50,1500,20,1000,0,200,5,0,1000,600,400,700,0,500,1500,0,0,4500,0,0,0,1000,0,2000,0,25,0,200,0,1500,500,0,200,300,7500,1500,2300,0,500,1700,0,0,40,0,100,3500,3000,0,3000,1000,0,0,700,0,1500,0,0,4000,0,0,400,7000,50,2000,0,500,0,4500,500,3900,2500,100,1000,200,20,1000,500,0,200,0,900,0,0,20,0,700,300,0,2000,0,0,0,100,560,2000,7000,150,500,10,500,1300,5000,0,50,0,300,600,6000,500,0,75,10,2000,1600,0,20,0,2900,0,2400,1500,50,400,0,300,200,1500,1500,1500,4000,2000,2500,200,10,6000,100,5500,2000,400,400,3000,0,400,100,1000,0,7000,50,0,10,0,6000,200,1000,0,1500,4500,0,50,0,2000,150,0,1200,2000,0,0,75,0,0,0,400,20,200,5500,0,800,10,0,0,50,10,2500,0,100,0,0,0,700,0,0,50,0,1500,0,0,100,0,0,0,1000,90,0,100,0,6000,200,100,2000,0,0,500,5,0,0,500,0,0,900,500,1500,6000,0,300,0,0,0,50,150,0,0,2000,0,0,2000,0,0,0,10,800,250,1250,20,0,1000,0,1000,0,1,0,0,0,0,0,100,0,100,20,0,0,0,0,0,3000,100,100,0,0,1000,0,0,25,0,10,5,500,0,400,0,0,0,0,0,150,0,10,0,200,0,1000,300,1000,0,200,50,400,0,100,400,0,5,100,1000,0,300,500,0,4000,4,0,1000,200,100,50,1000,0,0,500,0,400,0,900,0,0,50,0,1100,0,75,50,1500,100,0,0,150,0,0,0,700,0,400,30,0,500,0,0,2200,10,0,10,1800,1500,500,0,1500,0,200,0,300,0,0,3500,0,100,50,500,2000,200,0,1200,1200,0,0,7300,3000,0,3000,400,0,1400,300,0,8,250,50,30,400,0,100,0,25,2200,0,30,2000,0,800,6000,7000,3000,50,80,75,150,50,0,2000,50,0,1000,1000,0,50,0,1000,50,800,100,20,300,0,5800,500,7500,0,2600,20,0,2100,2800,800,2500,30,100,2000,0,1500,3500,50,0,0,0,0,0,50,0,2600,0,500,0,0,3000,1500,300,30,100,600,0,4500,1300,2500,200,0,900,50,0,0,400,0,100,0,0,0,4800,4000,1000,400,50,1300,15,5000,100,300,12000,0,2000,3000,60,800,0,10,6000,10,50,700,0,0,2000,200,50,0,8000,0,6000,300,1000,100,200,0,3000,1250,0,400,90,8000,0,6500,8000,100,0,4000,5000,0,200,10,0,2000,0,3000,3600,5000,3000,25,10,10,15,200,8000,0,20,2400,350,4000,0,6000,6000,4000,0,1000,1200,1200,300,0,3000,8000,0,0,300,2000,3000,1500,0,0,1000,500,8500,50,25,7000,7000,2400,0,10,1500,10000,0,300,0,4500,1500,1500,0,900,0,200,10,0,150,100,900,50,100,6000,3500,7000,0,3500,5800,100,0,3000,1500,0,50,300,0,0,0,1300,5000,2500,40,900,200,13,300,100,11000,200,0,0,5500,1500,2000,0,25,0,4500,5,800,0,400,1000,100,200,1500,200,300,0,100,150,0,500,4000,6000,200,0,200,300,1000,250,50,100,200,3000,0,0,7500,600,0,500,200,100,50,600,20,2000,30,5,0,30,50,2200,200,20,200,50,600,7400,3500,2500,3500,50,300,2500,3000,50,0,3000,6000,3000,0,0,0,200,50,200,3000,50,9000,800,400,9000,0,0,50,200,4000,3000,500,10,3000,1000,7200,50,10,2000,200,2500,0,100,7400,500,0,200,0,300,1200,0,1000,1000,0,0,200,2000,50,0,0,800,0,3000,300,0,300,0,0,0,2000,5000,0,200,1500,100,0,800,15,4000,300,2900,0,6500,250,0,20,4000,500,0,460,100,30,0,0,1800,200,500,200,20,0,0,200,700,0,30,0,1900,10000,0,20,5,400,400,100,50,20,0,50,50,0,0,0,50,15,3000,0,0,600,0,40,5,5,0,0,0,0,1000,0,0,0,0,100,0,400,0,2000,800,0,0,0,0,0,0,0,700,0,100,500,0,0,0,100,50,0,0,0,0,0,0,0,800,10,0,100,0,50,50,40,0,0,0,0,20,0,0,500,10,0,0,20,700,0,700,3000,200,40,0,0,0,200,0,0,2500,0,0,0,0,0,0,0,0,10,500,0,2500,10,0,0,0,0,0,50,0,500,5,0,0,50,0,10,0,0,0,50,20,8,1500,0,0,200,50,100,100,0,200,0,0,0,2000,100,0,4,2100,0,300,500,50,0,100,0,0,0,200,0,0,200,2700,0,0,2000,0,2000,0,0,50,0,500,400,0,0,0,0,0,0,700,0,1,0,8000,0,0,0,200,0,0,0,0,0,500,0,0,3000,0,20,0,0,0,0,50,15,0,0,0,1,100,100,150,0,1500,0,20,30,70,0,200,500,2500,0,0,0,75,0,400,0,10,0,0,0,10,0,50,15,1000,50,200,0,1200,100,3400,50,0,35,500,100,20,50,0,100,100,0,0,0,200,20,0,1000,100,3000,200,0,0,0,0,0,0,10,100,50,0,0,0,50,100,200,0,15,0,5500,100,0,0,0,10,100,50,0,0,500,5,0,0,0,50,0,10,0,1000,50,400,75,50,800,300,100,200,0,0,0,10,0,200,0,0,150,0,0,0,0,0,0,0,600,0,50,600,16000,7,0,300,0,30,350,0,500,200,500,0,0,0,0,0,0,50,55,300,0,0,200,0,5,0,0,2000,400,0,0,0,0,0,400,2000,0,0,0,0,0,40,300,200,10,0,100,300,100,0,0,0,0,1000,0,700,0,0,10,0,50,0,0,800,50,10,10,0,100,10,100,400,100,0,10,0,0,0,0,2500,2500,0,0,100,0,200,1250,5,600,0,2000,0,0,5500,0,0,400,0,0,0,5000,0,0,0,0,800,50,3000,25,0,0,10,0,500,3000,0,0,75,0,200,50,13000,0,0,0,1800,500,800,0,0,0,0,0,0,0,0,0,0,0,3800,0,10,0,0,6000,0,200,0,5,2300,400,200,0,10,0,2700,0,1200,1700,0,50,2500,50,0,300,5,500,100,0,0,0,50,300,300,4000,0,0,100,10,50,0,0,0,5000,0,0,0,1022,20,10,0,0,300,100,10,0,0,0,0,0,0,50,50,0,0,0,6000,7000,0,0,0,75,0,0,50,8000,300,50,0,15,100,25,0,0,300,10,150,30,200,1000,200,200,200,1800,0,50,1,0,0,0,0,5000,0,0,30,0,1000,0,0,10,300,0,200,500,0,800,500,200,0,0,5000,2000,0,0,1500,500,0,0,10,200,200,4800,2600,0,0,0,400,0,0,0,0,2000,1600,0,8500,2000,10000,15,0,0,100,0,10,1000,0,50,200,0,3400,5400,6000,2000,50,1300,200,0,0,0,300,3000,0,15,500,4000,7000,20,0,30,4500,0,0,0,1500,0,25,11000,0,0,1300,500,0,0,800,6500,1500,0,0,0,300,1600,0,0,300,0,300,12000,0,50,500,40,50,70,0,0,0,100,1000,200,100,8,2300,2000,3000,500,1000,0,0,20,0,300,2000,0,0,0,0,0,75,2000,100,0,2000,0,400,100,300,500,50,4000,5500,2500,3500,20,0,0,300,1000,800,0,10,0,10,10,0,1000,200,0,0,6000,0,0,50,500,50,5000,4000,0,10,5000,100,0,100,100,100,1000,0,1000,100,100,1200,4000,7000,3000,2000,0,4000,3000,150,1800,500,1000,1000,200,0,0,5800,2600,2200,3000,200,0,6000,0,0,250,1500,800,2500,300,1000,500,0,2000,2000,100,5,800,300,0,10,0,9000,0,1000,0,1200,100,0,0,0,3500,2000,40,0,40,4000,0,50,0,0,800,3500,1300,100,100,3000,3000,11000,50,0,0,0,500,10,500,1500,3500,5700,0,0,0,35,1000,2000,2000,10,0,700,100,3000,0,0,0,1500,3500,400,100,550,8000,6000,10,2500,700,0,500,2400,3000,10,0,10,0,0,4000,0,0,0,0,200,0,5000,2000,3400,0,20,0,5,0,500,500,7000,50,1000,20,500,0,0,3500,50,1000,0,2000,100,0,50,0,1000,1500,2100,3600,2000,2200,800,5000,1500,4000,3000,4000,8000,0,4000,350,400,800,0,0,2500,1500,10000,8000,7000,0,100,5000,1200,3600,0,50,10000,10000,8000,500,300,300,0,1600,2200,1500,0,0,0,50,75,700,3000,2500,2500,3000,200,0,10,0,50,100,1000,0,5000,200,8800,8000,3000,1200,2,0,100,10,300,0,1500,3000,0,1500,0,500,500,0,0,6000,0,0,800,4500,2000,0,200,800,500,11000,1500,6000,5000,3000,2000,1500,2500,100,3000,3500,0,800,2000,7500,800,300,1000,1500,1000,300,20,400,1500,500,1000,0,4000,20,150,400,0,4000,1000,1500,1900,2400,0,0,0,0,1000,20,0,30,75,5000,0,0,1350,0,0,0,200,200,400,0,0,4000,0,200,3000,1500,1200,850,1000,500,1000,100,300,1000,75,1800,1900,500,500,0,10,20,300,0,0,40,4500,3000,2000,4000,6000,5000,7000,1500,3000,0,0,50,0,2850,0,600,500,2000,2000,2000,5000,10,800,500,4500,5000,0,0,0,1000,0,4500,0,15,10,0,4000,0,8300,250,20,50,12000,4000,2000,0,5900,10,0,0,0,650,1500,5000,2400,3500,800,0,200,0,0,4500,700,0,0,20,100,0,3000,0,1000,1700,0,0,0,0,0,300,0,0,1200,25,500,200,0,6,1500,1500,10000,100,0,4000,0,800,4000,400,400,1100,5000,0,0,600,2500,1500,5000,800,2500,100,0,100,0,0,0,2200,85,0,2000,0,1050,0,0,1500,0,100,500,0,0,0,10,0,1800,10,0,300,30,0,0,500,150,250,0,800,300,1800,0,50,400,50,10,0,500,0,1500,300,1800,2300,60,0,1000,11000,200,350,100,2500,100,6,270,3000,1500,2200,450,0,0,0,500,0,0,0,525,0,0,0,0,0,2000,300,0,1200,0,1200,0,0,0,100,50,0,100,0,750,200,0,0,400,200,5,0,0,0,140,10000,100,0,50,0,5,10,0,100,0,0,0,50,20,0,0,700,1,0,0,6,50,0,5,500,100,0,150,0,3000,0,0,6000,800,10,1300,3000,100,700,400,0,300,200,50,2000,200,0,0,0,0,1300,0,0,20,0,0,200,200,50,1000,5,0,10,100,200,0,0,700,0,0,0,0,10,50,0,75,10,700,500,10,1000,10,500,10,50,0,75,300,300,2,1000,0,0,0,5,25,50,0,10,0,10,0,50,1000,0,0,5,0,0,200,300,1000,200,0,0,430,0,200,800,200,1000,900,2200,5,800,0,20,0,200,0,50,1000,50,0,0,20,20,50,0,0,0,5,0,300,0,2400,75,15,0,2000,30,200,50,4000,0,50,0,0,200,200,0,500,0,0,0,500,100,5,300,0,0,0,500,50,0,0,0,40,400,2,0,0,0,900,200,1000,0,300,0,2700,1100,2500,1500,4000,1000,500,0,5,0,500,100,900,400,500,500,0,0,50,0,20,0,0,50,0,15,0,1500,4000,30,1000,0,500,5000,100,100,0,0,0,5000,0,0,50,6000,2000,2000,1000,300,900,0,6000,2000,1000,0,0,8000,0,100,10000,3000,1200,0,0,300,0,0,0,520,0,100,200,400,400,2400,0,200,2000,3000,0,20,200,200,1000,1000,10,1500,50,750,4000,3500,7000,0,40,500,9000,75,1800,100,0,3000,0,6500,50,0,0,350,1000,5000,700,1300,0,5,0,6000,1300,2500,100,4000,0,300,2000,500,0,3500,2000,3000,100,100,2000,0,6000,10,800,0,0,0,25,0,100,300,900,2000,0,14000,8500,100,0,500,150,0,0,1000,0,0,0,1000,200,10,5000,0,1000,200,3500,0,10,1500,8000,6000,100,50,2500,2000,10,0,500,300,0,1500,500,4,500,800,0,100,1000,1560,400,100,11500,800,10,500,4000,4000,0,5450,8000,2000,500,200,200,1700,1300,1800,200,200,1000,600,4000,8500,7000,4000,20,0,200,0,0,750,50,0,0,1200,9000,1200,0,0,1000,1000,50,300,3000,9000,100,0,3000,500,3200,850,400,500,100,6000,0,2000,0,75,6000,75,10,0,50,50,0,0,50,2000,200,700,400,10,4000,5000,7000,1500,1700,2000,2500,500,20,1000,400,2600,2000,4500,3000,0,0,3000,3000,0,20,2,200,0,0,2500,5200,4000,0,0,700,800,200,0,1000,0,0,500,2400,100,0,0,400,0,0,0,0,6200,2000,50,500,1000,300,2600,0,0,0,3000,30,600,200,7400,6000,7000,7800,5200,1200,3500,0,0,0,1000,500,50,0,20,0,0,3000,0,10,5,5000,4000,634,2500,1800,7000,20,10,0,0,800,1500,7600,2000,10,200,0,600,700,0,500,11000,5000,2000,2000,6000,3400,10,3000,0,600,1000,350,0,20,300,0,600,5000,700,200,10,0,1000,3000,0,0,60,700,50,1,150,1500,800,600,1000,0,0,0,5000,0,0,500,3800,0,15,200,3000,2000,3500,0,0,0,1800,11000,3500,1000,0,2000,0,100,0,2000,100,1000,3500,3000,5000,700,0,3000,50,0,400,2000,1800,1500,0,20,0,7200,6000,1500,1400,3000,0,100,0,10,0,500,0,0,0,1500,10,10500,0,0,400,250,50,11000,4800,5000,2800,0,0,3000,4000,0,5,200,2000,300,200,0,6000,1200,1900,3000,2500,500,0,2500,1100,3500,50,50,1000,200,0,10,0,5,0,0,5000,2500,50,0,0,0,0,0,300,1500,5000,100,0,800,2600,0,0,100,10000,0,200,0,0,10,10,5000,0,100,0,200,10,0,500,0,0,0,0,0,0,0,100,3,100,0,50,0,1500,2000,0,0,0,0,0,1000,0,0,200,0,5,0,0,1100,150,0,100,0,20,0,0,50,0,3000,100,0,0,0,0,0,0,0,0,200,0,0,4000,50,50,0,250,0,1000,0,150,0,200,5000,0,0,2,1126,800,0,0,0,15,50,3500,40,0,400,150,1200,0,0,400,1000,1000,0,0,0,10,0,8000,200,0,20,0,0,6,100,10,0,200,200,0,0,0,0,300,0,0,600,0,0,0,50,50,100,1000,0,0,0,0,0,100,0,15,0,0,0,100,0,0,5,5,100,0,0,0,800,0,10,50,0,20,0,0,700,400,1000,3700,100,100,0,200,100,0,3000,50,0,1200,150,300,100,0,300,5,600,1500,7500,0,50,0,0,300,0,0,0,0,300,0,10,0,0,300,0,2500,35,0,0,150,0,500,0,0,0,0,30,0,0,100,0,400,400,100,0,0,0,1500,0,10,0,0,500,100,500,200,700,100,0,50,1500,1300,2500,70,650,0,10,500,1500,3000,0,75,550,1000,50,0,0,75,0,0,0,3,0,50,2200,0,0,50,500,100,0,100,0,100,0,0,0,900,0,50,0,0,300,0,200,300,4,20,0,0,600,0,0,50,1000,4,300,0,150,0,8000,50,0,0,0,2600,0,0,0,0,1200,200,1000,0,500,0,0,100,0,0,20,30,50,750,3700,0,50,0,100,400,0,0,30,0,0,0,0,600,0,200,75,0,50,700,20,0,0,0,0,700,0,0,6500,0,0,50,300,30,0,9980,2200,200,0,450,0,400,0,200,6000,0,0,0,10,0,0,0,10,0,0,0,500,0,0,0,0,3000,0,0,0,0,0,0,8000,0,0,0,0,0,10,1900,50,0,200,500,0,20,550,20,500,0,0,10,0,0,5,0,0,0,0,700,20,20,500,0,0,3000,100,0,1200,0,50,0,0,0,0,0,180,100,0,0,0,100,0,6000,0,10,0,0,0,0,0,0,0,0,0,0,30,0,200,2500,0,0,1800,4500,40,0,10,0,10,0,0,100,300,50,1000,5,0,0,0,0,0,100,2000,6000,3500,0,20,0,300,300,0,0,0,0,0,0,0,0,0,10,0,0,0,0,650,50,2000,0,15,0,1500,0,0,0,400,0,5,200,0,10,500,1000,0,0,0,20,100,100,3000,1500,0,0,0,3,1500,5,1000,0,100,1000,0,1000,500,50,10,2000,0,0,0,1000,0,0,30,0,10,0,300,400,0,50,12,0,0,20,50,0,0,0,0,300,500,10,0,50,0,5,0,0,0,10,100,0,0,0,250,0,0,200,0,0,0,0,50,10,0,0,0,100,0,150,9000,5000,20,0,50,0,1100,0,250,0,0,100,0,700,0,3000,50,0,0,100,0,200,1000,0,20,10,0,0,0,0,1000,2600,0,0,30,0,0,400,100,1500,3000,10,0,0,0,5,0,0,0,0,1000,7000,5,0,50,0,50,0,800,25,0,100,0,1000,0,0,0,0,0,30,100,0,0,0,1000,0,0,1500,0,200,800,0,0,50,50,200,100,300,3000,0,0,0,0,0,2500,0,50,0,6000,700,0,0,300,200,100,400,0,30,3500,0,0,0,1000,0,0,0,0,1800,0,10,50,0,0,0,1000,0,500,15,200,0,200,0,0,0,0,0,50,0,200,200,15,0,0,0,1,0,0,50,1800,3000,200,300,0,0,0,25,0,0,0,2400,0,0,0,0,0,0,3000,1000,8000,300,0,200,4000,0,0,0,0,0,0,0,0,0,100,1000,600,3000,8000,0,0,1000,0,800,0,600,0,0,50,50,3,150,0,1500,0,0,0,50,0,0,0,50,0,0,200,0,50,400,1200,0,50,0,0,0,150,10,0,50,1000,500,2,0,0,0,4000,0,0,0,0,0,0,50,0,0,5000,0,300,0,100,50,0,0,0,200,500,9000,5000,0,0,50,0,0,0,0,2,30,0,0,100,100,3000,3000,100,0,0,10,400,10,0,1100,1200,5000,3400,3000,0,0,0,0,0,500,3000,1000,0,50,2500,0,25,0,300,0,0,100,200,250,300,50,1000,500,1000,0,20,0,0,0,800,400,0,0,0,2500,50,0,0,50,1000,0,0,1000,500,35,0,100,8500,1500,25,0,0,0,0,0,0,500,75,0,400,20,0,0,2600,0,0,0,0,5900,83,1500,100,500,175,200,100,3000,1250,2000,3000,100,0,0,0,200,0,25,700,0,0,250,0,0,13500,3000,0,0,5,500,10,10,0,350,200,800,0,300,1000,100,150,50,6000,2000,4000,4000,0,0,0,0,0,800,10000,100,0,100,0,0,0,0,550,4500,6000,2000,6000,3000,0,0,10,10,0,900,150,50,200,3000,6000,0,300,200,0,22,0,0,5,800,0,1500,50,0,75,200,0,3500,0,0,0,1000,1000,200,120,50,0,7400,0,500,100,100,60,0,600,300,1000,800,2000,0,10,0,500,0,100,0,0,50,200,3000,3000,20,0,250,20,0,1000,0,1200,5000,0,50,1200,1500,10,100,200,0,1000,4800,1300,0,0,100,11000,0,500,1000,700,500,4300,1300,50,0,100,65,3000,0,800,10,0,0,5000,0,0,0,0,500,100,10,1200,100,1000,0,0,800,50,200,0,11000,2800,2500,1200,0,0,0,0,0,50,100,0,2000,8500,10,0,0,0,70,100,16000,200,400,0,100,0,1000,300,2900,2000,2300,3000,3000,50,500,0,10,0,20,0,200,550,2000,3400,1500,1500,200,0,0,500,0,7000,1500,1200,1500,0,0,0,0,0,100,0,0,50,0,0,25,1000,50,2000,3500,11000,1000,0,0,0,0,700,6000,0,0,9000,550,25,0,4200,300,150,0,400,300,800,0,5000,50,4000,0,0,0,500,300,0,2440,900,0,600,1200,2500,3000,0,0,0,1200,0,400,0,1000,2500,100,30,0,0,2500,4500,0,3000,1500,0,5,1000,0,0,200,340,1600,3000,3000,2500,4000,5300,1900,20,0,2400,1500,600,1000,800,200,200,0,0,0,2500,8000,3000,2000,1500,2000,0,0,2000,0,1100,2700,1000,1000,400,7500,20,10,50,0,100,190,1000,1000,0,900,7000,2500,4000,3000,2500,8000,0,10,0,0,1200,5000,0,200,500,0,1000,300,500,500,20,0,5000,5500,5000,2200,1300,4000,3200,0,4000,5000,7600,1000,3000,3000,200,1000,500,100,3000,2000,50,50,600,7000,500,1000,150,100,0,800,4500,3700,2000,400,200,2000,3000,0,2000,3000,400,5,5,2000,2900,4000,500,200,0,1500,1100,0,0,0,0,200,50,300,20,500,0,1750,0,0,1500,300,200,0,3000,3000,0,200,100,10,700,750,10,100,500,100,1800,0,200,0,500,50,1500,0,100,500,20,0,400,50,300,400,30,5500,3000,8,200,10,300,0,2000,2000,0,200,800,1000,0,7000,1500,600,0,3500,0,8000,3000,4300,20,100,2700,100,3000,10000,8700,6000,10000,8500,200,8300,7000,400,2,3500,1500,45,75,1100,1500,800,100,50,0,9500,1800,3500,0,0,35,560,0,1000,200,200,10,4000,5000,2500,1500,3000,1500,5,0,0,1000,100,0,0,0,100,100,500,50,800,3000,100,0,0,130,5,500,0,0,800,1100,0,10,500,100,800,100,200,3750,4600,2000,1800,300,500,50,800,0,6000,5000,2500,1200,800,0,0,400,300,1000,0,1000,0,2600,6000,4400,4000,3000,2000,0,0,500,10,0,0,500,800,0,400,100,0,0,10,0,7000,5000,800,1000,3500,1800,0,0,0,0,0,2000,4000,4000,2500,0,5000,6200,3500,126,1500,0,9000,1200,0,5,0,9000,8000,100,300,1000,300,2000,0,0,20,500,3000,2000,4000,1200,20,300,400,1,200,0,0,0,0,700,0,0,1000,750,1500,8000,100,50,37,4000,0,500,1000,0,0,13500,2200,6000,2400,50,1600,500,10,0,200,850,3500,7600,4000,2500,4000,3000,3700,15,0,900,50,7000,50,400,15,500,100,30,200,4000,2000,100,10,0,1500,0,0,0,7500,75,400,200,500,350,0,0,10,0,50,0,900,0,0,5,2800,6000,3000,0,0,0,0,0,1200,50,700,600,400,0,0,0,0,50,900,100,0,4900,3500,10,2000,10,3000,5000,200,5,20,0,1000,6000,3000,4500,3500,3000,6500,1100,3000,2800,4000,3600,1500,3000,0,500,1500,4000,4000,3500,1000,1500,0,1600,1000,5000,0,1000,0,5000,200,50,200,4200,800,1000,200,5500,0,0,0,200,2500,6000,0,0,100,0,2000,1000,1500,3000,1500,0,0,500,750,120,3500,0,0,5000,500,100,4400,1000,1500,5,300,200,800,1000,0,0,1200,0,0,300,1500,0,30,600,200,150,0,300,350,300,0,500,50,400,0,150,600,0,20,0,300,1100,1500,0,500,500,500,1000,10,200,0,100,0,100,1000,2800,5,50,0,500,500,10200,200,100,900,75,6500,7000,0,200,10,0,50,150,300,300,0,0,0,5,200,300,0,0,0,500,100,2500,0,0,100,10000,10,400,25,500,0,20,0,200,0,300,0,0,300,0,0,300,0,50,0,100,700,0,5700,2000,800,10,4300,125,1500,1900,3000,1700,1000,100,0,500,50,0,0,2500,1200,300,5,50,200,5,9000,0,30,1000,0,200,65,50,0,100,100,0,0,0,5000,0,800,150,0,1250,100,50,100,200,3000,1000,500,0,200,0,0,20,20,700,3000,1200,0,1500,0,1300,800,0,300,2000,8600,600,0,0,10,1850,0,0,0,600,600,1800,100,0,0,0,75,20,1200,0,800,200,100,500,0,300,3000,0,600,300,50,0,300,0,35,50,0,0,2500,1200,0,3000,150,500,200,100,100,0,40,0,1200,0,0,300,0,100,0,1000,1500,150,1000,0,4000,200,50,300,0,100,0,50,0,300,5,700,3000,0,50,10,0,0,50,1500,5,50,0,0,0,0,0,250,50,0,2000,20,0,0,400,400,75,0,5,500,0,0,0,0,1000,1000,0,0,0,200,0,1400,600,4000,0,0,0,7000,300,500,300,500,0,40,8,4000,0,1500,100,150,5,100,0,600,0,400,700,400,50,400,100,3000,10000,25,0,0,0,200,2800,0,3800,600,0,0,4000,1300,0,0,500,200,0,500,5000,1000,0,1000,0,3000,0,0,0,3000,1500,10,50,100,3500,3000,2500,900,200,7500,200,0,1000,1500,63,500,20,1200,10,0,6000,3500,0,50,0,0,4000,0,0,1000,900,200,500,10,0,5000,5,0,5000,3500,25,9000,15,2000,2500,5500,6500,100,0,2700,2000,0,0,0,100,20,10,1000,100,500,150,0,200,100,500,3000,50,0,0,100,100,0,50,0,300,0,200,2000,0,0,100,3000,500,30,700,500,7000,3000,800,7000,0,300,600,1250,0,900,15,200,500,2500,2000,2500,400,0,800,400,3000,4000,0,1500,200,0,0,20,0,0,8000,0,0,10,2400,0,50,0,1500,4000,100,0,0,0,0,0,8500,50,0,0,0,5,0,30,300,2800,400,4000,1400,3000,0,50,0,500,0,200,100,500,500,0,8000,1200,0,0,0,0,1500,5000,50,0,4000,200,8500,10,0,60,5000,10000,3500,50,0,550,200,0,1000,1500,0,200,20,2500,7000,3000,1500,50,0,500,300,0,5000,1900,4900,10,750,2600,3000,1800,3000,5000,5000,5,10,0,9000,5,400,3150,4500,1100,100,0,0,1000,3000,2000,100,0,7000,3000,600,100,0,6500,5400,8000,0,700,0,0,100,200,3000,1700,0,1500,0,10000,0,900,1000,1000,100,20,20,0,5000,1700,2000,0,0,400,1000,0,600,1300,4000,0,0,7500,0,0,1000,400,0,200,2000,500,1500,50,50,100,0,800,3000,10000,200,30,0,2000,2000,400,100,500,0,200,7000,1000,150,3000,100,20,0,2000,3000,0,30,450,300,0,200,2000,2500,10,0,50,2000,300,2100,0,0,1000,4800,1500,1100,0,500,20,1000,50,0,0,1200,100,0,6800,1400,0,0,50,10,0,1500,200,0,1800,2500,1,10,50,0,15,25,8000,3500,0,0,300,300,7000,100,0,5,50,500,50,500,300,10,0,0,2000,4000,3200,10000,0,100,0,0,0,10000,3000,5000,2300,0,0,0,500,0,300,2500,20,2500,0,400,300,500,0,50,0,0,1500,0,10,0,3000,10,2000,0,0,0,0,50,100,400,200,100,1200,0,0,1000,400,600,3200,0,0,0,3000,300,300,0,300,250,50,25,1800,0,3200,0,3000,0,800,100,1000,20,300,0,10,2000,800,75,45,0,2000,20,50,5000,3800,0,0,150,0,0,0,0,600,50,0,50,4000,0,0,0,4000,0,2300,4000,2500,500,500,0,500,150,0,400,0,300,2500,0,0,50,0,2000,100,0,0,0,0,3000,0,0,0,0,0,50,500,100,10,3000,4000,50,0,40,50,100,40,200,0,400,0,0,0,0,10,50,1400,150,200,3000,0,0,0,3700,0,200,0,1000,50,0,0,100,300,7500,1700,0,20,200,10,0,50,1000,20,0,0,0,0,0,0,40,0,3000,0,200,300,50,200,0,2000,200,0,0,100,10,10,7,800,0,9000,3,0,30,0,0,100,0,0,0,2200,15,0,100,0,0,50,5000,0,0,2,0,200,150,400,0,20,1500,0,30,50,100,0,0,500,2400,1500,1300,20,200,15,0,10,0,2100,0,50,0,0,0,0,0,0,600,0,0,2000,0,0,0,0,0,300,25,50,1200,0,0,0,0,0,0,10,1000,200,10,4000,50,100,1000,100,100,100,100,0,0,0,0,500,10,300,100,0,300,0,20,0,50,200,0,150,0,800,0,0,0,50,100,0,20,0,0,10,0,0,0,0,0,0,15000,0,20,1100,0,10,0,100,1000,0,200,100,0,1500,100,0,100,100,0,0,0,37,0,0,100,0,50,0,5000,0,5000,0,0,0,0,0,0,30,200,0,100,10,40,1000,100,0,0,0,1500,20,0,0,0,100,100,6,50,0,0,0,1000,75,100,100,500,0,300,0,5,0,0,1000,0,1,0,100,0,3000,2000,0,0,0,0,0,0,100,0,100,0,0,2000,0,100,0,50,0,0,0,50,0,0,0,0,0,0,0,300,0,0,0,0,0,0,0,0,0,0,200,1500,1500,0,0,0,0,0,0,0,0,20,20,0,700,100,0,0,0,0,10,100,100,500,1000,200,35,10,0,0,6000,10,200,30,0,0,0,0,0,75,500,0,200,0,1500,0,0,0,0,0,0,3,0,200,500,0,20,1500,0,0,10,300,200,100,0,0,200,0,0,300,200,0,0,100,0,0,0,0,20,0,0,0,0,10,0,0,0,150,20,0,50,0,0,100,0,175,150,500,0,0,5,100,0,300,0,0,50,50,200,0,0,0,0,0,0,100,0,0,0,0,0,0,0,0,75,0,0,100,1200,0,1000,0,0,0,0,0,600,150,200,200,190,1000,600,0,3500,0,25,0,0,0,300,0,0,0,0,0,0,0,0,0,50,0,10,200,200,0,0,200,9000,0,0,0,0,0,50,0,0,0,75,0,10,15,7000,0,75,0,0,0,10,1000,800,0,50,400,0,0,200,0,20,0,0,0,0,1000,0,0,300,0,100,0,0,0,0,11300,11000,50,0,0,2000,20,0,0,0,200,0,0,50,500,50,0,0,300,0,0,0,20,2200,0,500,0,0,1000,0,0,0,300,0,10,0,0,0,3300,1500,0,10,500,10,0,11000,5000,3000,0,100,50,0,50,0,500,800,100,800,55,0,0,2000,10,0,0,0,0,0,100,0,50,0,50,0,0,0,0,50,0,200,0,500,0,0,200,0,0,0,0,0,0,50,0,500,4400,200,0,0,10,0,0,100,0,0,0,0,0,0,250,0,300,0,0,0,50,0,50,0,0,800,0,50,20,400,0,0,1000,2000,0,0,0,100,5,0,30,200,5,25,20,1000,0,0,100,0,0,20,10,25,400,0,0,0,600,3000,2200,0,100,0,0,0,0,3000,100,100,50,0,0,0,0,1500,600,10,0,50,50,0,30,30,400,100,50,200,0,100,50,0,0,7000,0,0,200,0,0,0,700,0,40,500,0,0,50,0,50,0,0,500,0,600,10,0,150,300,0,87,0,1740,0,10,0,0,0,2900,0,0,0,0,50,100,800,11000,500,450,0,0,0,400,50,50,200,100,50,300,50,5000,0,0,20,0,8000,0,0,300,0,200,5000,0,0,0,2400,0,300,100,0,150,0,13000,100,0,0,1500,0,20,600,200,5,10,0,1020,4400,100,200,10000,0,600,50,0,0,1000,3000,0,1400,1500,0,0,0,5,0,400,500,6000,0,50,0,600,100,2300,0,40,0,3500,4000,3000,10,50,0,0,0,0,0,100,0,50,0,1000,0,1900,200,100,500,40,0,100,100,1500,6,50,50,0,0,0,200,5,0,50,200,100,0,10,20,20,100,0,300,250,700,0,400,4000,0,0,0,0,0,1000,0,200,0,0,0,40,700,0,0,0,0,100,0,0,0,0,0,300,1600,600,1000,2800,0,0,50,100,0,3000,50,100,0,0,0,15,0,2,600,100,2500,4000,1800,0,20,500,1200,10,10,200,100,30,3000,5,30,0,0,500,50,30,1000,0,300,1200,20,0,0,500,200,0,3000,2500,2000,100,0,0,3000,150,1000,50,1800,0,35,300,100,1000,0,0,2500,0,100,50,0,0,0,1,0,50,5500,800,10,0,0,0,0,5,100,200,4000,4,250,300,0,0,3000,0,0,0,600,20,50,0,100,0,1800,0,0,0,0,500,1500,0,50,1,1500,3000,1500,10,800,0,1500,0,50,500,0,0,600,0,500,3000,1000,5,0,0,100,0,6000,600,2000,2000,9000,6000,0,1500,1000,4000,5000,300,200,75,2000,3500,0,0,0,40,0,450,500,0,5000,1600,0,0,800,2000,3000,0,400,1000,0,200,50,0,150,600,0,3000,11000,3000,0,800,10,200,800,10,200,500,0,200,500,0,200,2600,4000,0,500,200,50,0,10000,100,0,100,3500,2500,100,25,400,400,100,0,1000,5,0,2000,700,10,800,1800,0,100,300,0,0,0,2200,4000,4000,0,100,0,0,0,4000,400,1000,200,500,1500,6600,0,50,1200,10,50,0,0,0,50,30,0,500,5,500,20,100,4500,7500,3000,5000,10,0,100,50,1000,300,20,800,0,50,50,0,0,400,2500,0,250,100,100,3500,200,10,20,650,3200,5000,0,20,3000,20,150,500,0,0,5000,10,800,0,1400,3000,1600,0,4000,1000,0,75,0,1000,5000,2500,30,0,50,0,0,0,0,0,10,5,50,2000,10,0,2000,0,0,1500,50,800,1500,10400,0,0,0,100,800,0,2500,550,500,800,100,1800,4000,3000,0,150,0,0,300,3000,1600,100,0,100,50,200,4000,3000,0,100,3000,1500,0,2500,7,2500,2500,3000,1500,2500,0,500,150,400,250,0,5000,6100,0,0,5,0,20,1000,1000,2600,0,400,0,0,50,0,10,3000,200,0,0,10,250,200,0,10,400,200,0,0,300,20,1000,25,100,2,100,1000,500,500,200,0,10,15,0,0,20,1000,2500,600,3000,500,0,800,100,0,0,0,0,0,0,300,100,300,800,0,1000,3000,1500,1500,6000,0,10,400,30,5,50,900,1000,300,0,2000,3500,4600,2000,0,0,0,0,0,1500,1100,0,600,3000,1200,0,10,20,3000,600,3000,2000,20,0,0,16,100,10,0,10,4500,3500,2000,0,15,0,0,25,0,8000,300,30,2100,100,500,0,0,0,800,100,3000,1300,800,0,2000,0,0,3400,100,1500,500,100,3000,2000,0,800,0,100,0,800,0,8000,0,500,300,200,0,500,0,5000,4000,3000,2800,0,0,100,175,3000,600,100,0,100,470,0,1000,2000,200,1200,0,1000,0,200,0,0,0,0,2000,0,4500,4000,50,250,20,1200,0,0,0,4700,0,2400,250,300,400,2500,4000,3000,2000,4000,1300,0,25,0,250,200,900,2000,2000,3000,2500,0,3000,5000,1800,2600,1000,1000,1000,11000,4000,4000,4000,5000,25,0,400,3000,25,4700,100,4000,500,0,3000,1200,3000,0,3000,3000,2000,1500,500,0,0,0,300,3000,2000,200,0,1500,5000,1500,7000,4500,50,100,0,500,1000,7000,1400,3000,4000,5000,3000,1100,50,2500,1000,0,4000,8000,1700,2000,3600,20,2500,300,4000,200,500,2500,0,0,0,400,0,1800,20,900,7000,4000,50,10,100,200,5000,0,8300,0,7500,600,0,500,0,1000,0,2500,0,0,50,1500,7000,0,0,50,3000,400,150,500,0,5000,4000,200,0,0,0,0,5500,3000,400,0,300,100,0,0,100,400,700,1200,0,0,1000,100,200,0,8000,0,300,900,0,200,50,5000,800,100,0,5000,0,0,0,300,7000,200,100,50,150,2200,400,0,0,300,0,800,0,1000,10,1400,30,300,1000,0,0,300,0,3500,400,400,0,800,500,30,500,100,2500,10,0,1000,0,10,2400,100,100,80,500,400,400,100,0,0,0,600,600,0,0,500,50,150,800,7000,50,55,0,0,100,0,50,200,0,10,1000,0,100,0,0,10,0,600,0,100,400,800,20,10,300,100,300,200,0,0,0,1000,0,1200,10,0,500,4000,0,0,1800,4000,0,50,0,0,3000,0,25,0,200,200,10,500,0,0,50,500,50,200,5,5,10,300,0,0,0,20,200,300,500,200,100,5,0,200,0,0,1800,3000,1200,1800,250,1300,1800,10,20,1200,2000,150,200,0,0,500,650,0,500,100,0,500,0,200,1200,250,0,0,50,80,0,0,50,0,600,300,0,2000,75,1000,500,300,0,200,50,250,100,200,0,400,0,0,0,1500,0,1800,100,0,500,2500,0,0,0,50,0,0,200,25,1200,20,0,20,300,5,500,900,0,10,200,0,0,200,10,800,0,0,0,50,15,6000,200,500,500,0,0,200,100,0,50,0,50,0,0,1800,600,0,10,450,200,0,200,500,6500,50,200,0,10000,20,80,0,100,250,0,1100,15,400,0,800,3000,0,100,0,0,0,0,300,0,0,0,0,800,10,200,150,1000,0,0,0,1600,0,100,2300,200,0,800,0,0,450,1400,500,200,2000,35,150,1900,1000,0,0,400,20,1000,400,100,1300,0,0,0,0,0,800,100,3000,200,0,500,1,0,0,2000,3500,1000,0,10,0,0,37,1000,1200,0,0,100,100,30,400,500,0,0,0,20,50,100,150,200,0,0,0,0,800,2000,1100,0,5,100,200,2,0,75,0,200,50,150,100,150,2200,0,0,15,3000,0,0,0,200,0,2000,0,200,500,500,10200,0,6000,0,500,3000,2500,1000,0,800,3000,6,50,50,500,3000,2500,0,0,0,1000,75,6700,0,10,0,10000,10,2500,10,10,0,20,0,100,0,0,1200,3000,0,0,4000,0,0,0,200,2200,0,5000,300,200,1900,3500,3000,0,0,0,0,0,50,30,200,100,5500,2500,400,2000,0,1000,800,0,500,0,2000,3400,500,0,5,10,400,7000,600,100,1800,0,2000,2700,2000,1000,5700,3000,4000,0,100,0,800,200,4000,200,0,40,0,0,0,3000,100,3000,10,500,4000,0,0,0,95,5000,20,10,0,450,3000,3000,0,0,0,50,400,100,3200,2000,0,1000,5,10,5000,75,10,0,0,5000,4000,1000,0,3000,100,100,400,1880,1500,2000,50,0,5000,0,250,0,10,200,200,7000,60,200,0,1000,4800,10,25,755,1500,100,20,0,1000,50,1500,50,200,10,4000,0,0,300,0,500,1500,2300,10000,5000,8000,300,6000,200,500,1000,10,4200,1800,1000,800,4000,2000,0,100,4000,2000,0,10,20,1000,0,0,2100,3500,0,800,0,0,0,2000,0,0,0,0,200,450,500,0,0,4000,200,4000,800,5000,0,0,30,800,200,3000,0,0,300,5000,5000,10000,100,0,10100,200,2800,0,500,500,0,0,1000,100,300,0,2000,1500,0,0,0,0,2000,500,150,1000,100,0,2500,5600,2000,100,2500,500,1500,3000,700,100,0,200,0,2800,0,1000,0,0,0,1,0,800,0,500,700,0,30,0,0,0,0,50,200,0,0,0,700,50,0,0,0,0,15000,1200,0,0,0,200,10,4,0,0,0,1000,2500,0,2500,0,50,0,50,0,50,100,9500,4000,3000,200,2200,4000,1000,200,1500,100,100,50,800,500,20,100,300,0,0,50,5000,900,0,2000,0,0,0,100,0,0,1000,0,0,0,0,800,500,125,200,100,50,3000,0,0,1200,0,0,10,0,0,0,0,1400,0,40,1000,500,10,0,0,0,0,0,0,10,800,7000,0,0,15,50,0,0,0,50,100,10,0,4000,100,50,10,1,0,10,400,10,0,800,1000,0,10,20,100,0,100,100,5000,2200,3100,1500,0,300,100,1000,0,0,900,0,4000,0,0,200,0,0,0,50,50,0,0,6000,0,0,0,500,150,0,4500,10,0,5200,25,200,0,0,200,0,12,0,100,1,100,13000,0,0,0,0,500,0,1000,0,2200,0,7000,50,200,0,0,1200,200,0,2000,400,20,0,0,0,0,10,30,3500,0,0,30,0,0,200,0,1000,500,0,0,0,800,50,0,0,0,0,0,0,0,100,0,0,500,3000,1,15,0,400,0,500,20,0,10,500,5,100,0,0,3,600,20,0,0,0,0,11000,1800,0,20,10,12,0,0,10,0,0,0,10,0,0,100,50,8,10,0,1200,0,0,0,0,1000,200,0,0,0,100,0,0,0,100,0,10,0,0,0,20,0,400,50,100,0,50,1000,0,1500,2000,25,0,500,500,300,500,0,0,0,200,400,0,4000,20,0,0,0,14,0,1100,500,200,50,5,500,0,0,50,0,1500,0,0,0,12,0,100,0,200,0,2000,0,200,500,1700,0,0,0,0,500,300,30,0,100,0,0,300,2000,20,0,0,0,0,100,0,0,3500,0,0,0,100,0,500,200,2000,1500,0,50,0,200,0,0,0,1500,0,500,0,50,0,0,10,0,10,0,0,0,10,0,0,0,0,300,200,50,0,5,0,1000,0,50,0,50,50,100,0,0,0,0,0,20,10,25,0,0,50,400,7500,0,700,0,3,0,20,500,0,0,50,0,0,10,0,0,75,800,50,50,600,30,0,2,5,0,0,0,0,0,20,3000,50,5,100,0,0,200,100,20,0,0,0,0,0,40,0,0,100,50,100,0,150,0,0,80,0,10,0,150,0,0,100,0,0,50,0,20,0,0,10000,1400,0,0,0,20,25,200,50,500,500,50,0,10,11000,2000,0,0,0,400,0,500,1000,5,800,10,0,0,0,9700,30,100,25,20,0,0,0,0,0,10,0,0,10,1000,0,0,0,50,10,0,0,2400,0,50,400,300,0,10,0,400,0,2000,0,0,0,0,500,0,50,10,7000,500,100,0,0,0,0,0,0,6000,0,500,5,0,0,50,1500,500,100,50,110,100,9000,25,0,0,5,150,15,0,0,35,0,0,10,0,0,25,0,10,100,0,0,0,0,500,0,1000,0,200,0,0,0,0,300,6200,0,20,700,10,3500,30,0,2000,1200,0,30,0,0,2300,3000,50,100,0,0,0,0,0,0,0,1000,500,0,1500,0,0,50,0,500,7000,0,25,1000,0,0,0,0,10,0,0,0,100,0,0,0,2000,0,50,0,0,0,0,0,0,0,700,3000,10,100,0,500,1000,0,200,300,0,0,0,50,0,5,10,0,50,0,400,50,0,0,10,0,300,200,50,0,0,0,50,25,20,0,1200,30,0,0,25,100,0,500,200,3000,0,0,25,0,50,30,0,300,0,0,0,0,0,0,0,2500,0,100,0,100,20,600,300,0,0,10,0,0,10,0,100,0,7000,4000,6000,300,0,10,1000,1000,500,3000,0,0,25,0,30,150,0,500,0,1000,200,1200,100,0,0,2200,0,4000,0,3000,0,2000,0,200,500,0,5,50,0,75,5,1000,0,70,1000,0,0,1300,0,40,200,400,0,0,30,0,150,0,300,1000,0,4500,40,700,50,2000,0,800,20,0,20,500,200,4000,0,0,800,0,200,0,0,0,100,1700,15,20,600,0,3000,0,250,0,800,200,0,350,150,3500,5000,20,20,100,0,1400,1500,50,200,700,10,30,0,10,50,600,2500,2400,100,0,4000,0,500,100,100,550,100,150,350,1700,1500,0,0,0,0,0,20,300,0,30,10,8500,5000,50,0,0,1200,100,400,500,10,11000,1000,0,100,800,0,50,100,100,500,35,0,2000,1000,1000,0,300,4500,5000,1500,0,100,0,12000,700,40,0,0,500,300,200,5000,3000,0,0,0,0,0,100,1000,500,0,0,0,0,0,0,300,0,700,5,1500,3500,2500,1800,0,5,400,2000,1500,0,0,3000,500,1000,0,500,450,300,300,300,1200,6000,2000,1800,4000,0,0,0,0,500,0,500,1060,3700,1700,0,300,10,300,1500,1300,800,800,0,0,0,200,7000,500,800,20,300,1500,2000,0,50,50,600,100,10,0,700,600,1300,5000,3500,4500,2500,50,3500,800,1200,5000,500,100,0,0,1200,0,0,5,10,300,50,0,75,11000,1400,10,1000,1500,0,5,3700,0,2000,800,70,1500,6800,500,0,15,0,100,0,350,300,460,2500,175,200,0,0,20,1400,60,400,10,500,0,4000,200,10000,5000,20,2500,2000,5000,400,1500,0,500,15,500,800,3000,3200,0,4000,250,5,0,10,5400,4000,2000,8000,1300,0,0,0,0,500,3000,2500,0,0,200,500,0,0,100,0,2000,1000,1000,0,35,0,0,300,2500,3500,900,900,0,500,300,20,2500,400,50,0,50,0,1800,0,1100,0,0,200,5,1000,50,900,1600,3500,1500,0,0,0,15,0,300,1000,75,1600,2000,10000,1800,9000,500,5,1000,20,400,50,5000,18000,3000,900,0,2000,900,480,300,2500,150,300,200,200,1500,1100,4500,2000,5000,2500,0,20,0,0,500,0,1500,1000,50,0,50,1000,2250,1675,5000,1800,1000,500,0,90,0,1000,14000,6000,400,25,500,0,20,500,700,2000,0,15,300,0,150,1000,20,300,1000,0,0,20,500,3000,0,0,800,300,0,2500,1650,4000,2300,0,0,450,2500,0,100,10,0,200,200,2000,2300,0,2700,7400,1500,4000,200,0,1000,1500,1500,0,50,2700,500,3000,500,480,10,200,0,300,0,0,0,2550,1000,500,1400,100,0,500,4000,4000,2500,2000,1900,4,0,0,0,0,0,0,2000,1200,2200,0,10,7000,500,1000,4000,3000,1500,25,1400,1800,10,0,1000,0,0,0,0,6000,3500,1000,1850,10,1500,1500,1500,1500,100,400,0,11000,7000,20,750,800,3000,100,500,2000,2000,2500,0,0,0,0,0,0,200,0,0,500,3500,0,400,200,700,5000,2200,10,0,0,7500,1000,1400,0,900,1000,800,0,1200,7080,7000,1000,1000,1000,0,200,400,500,2000,2000,1500,0,50,0,1000,800,75,800,1000,1000,1000,0,400,350,10200,1300,0,0,2000,50,3000,3000,2000,800,1500,10,50,0,500,10,200,800,500,3000,2000,0,0,0,1200,40,4000,0,3000,10,0,0,4000,10,800,1900,200,4000,100,400,6000,5000,1400,2500,0,100,0,0,1000,35,4000,0,400,7000,5000,0,0,0,0,3000,10,3000,2500,1500,0,700,50,5000,0,0,200,0,0,0,500,0,50,100,2500,100,1000,4000,0,0,500,2000,250,7500,1500,4000,3800,3500,0,8,3000,2500,5000,2650,0,50,500,0,30,0,0,50,0,25,2700,2000,1500,2000,4000,5500,0,2000,50,50,0,0,0,25,25,1000,6000,1000,500,0,1000,5300,3500,0,0,1500,300,0,400,0,0,3000,0,100,0,100,150,0,0,1500,0,0,1000,0,50,1800,6000,0,0,300,2600,142,0,2500,4000,5000,1000,50,25,0,0,100,20,1500,100,300,800,0,0,0,0,100,1800,0,0,0,1000,2000,10,500,200,0,50,0,0,7000,100,10,0,1500,600,0,300,3000,0,100,250,4000,0,0,1200,0,300,1000,0,100,800,0,1300,7000,5400,0,0,500,2000,20,700,4000,800,0,10,300,5000,2000,1000,500,10,1500,0,2500,0,200,500,0,800,0,600,10,2000,100,30,4000,1000,1000,5,10,4000,15,25,0,1300,20,500,1300,200,3000,0,20,1100,500,10,100,1500,1000,1000,50,0,0,0,0,3000,0,30,500,700,10,600,0,0,500,1200,700,0,0,0,0,300,50,0,0,50,1200,0,0,2300,300,400,0,100,0,5,800,0,2200,800,10,0,200,2000,100,100,200,50,0,0,0,200,0,4000,0,300,0,30,0,0,0,7500,0,0,0,0,80,50,2,0,300,500,150,50,0,250,10,0,3000,0,0,0,50,10,1500,0,0,0],"xaxis":"x","y":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41,42,43,44,45,46,47,48,49,50,51,52,53,54,55,56,57,58,59,60,61,62,63,64,65,66,67,68,69,70,71,72,73,74,75,76,77,78,79,80,81,82,83,84,85,86,87,88,89,90,91,92,93,94,95,96,97,98,99,100,101,102,103,104,105,106,107,108,109,110,111,112,113,114,115,116,117,118,119,120,121,122,123,124,125,126,127,128,129,130,131,132,133,134,135,136,137,138,139,140,141,142,143,144,145,146,147,148,149,150,151,152,153,154,155,156,157,158,159,160,161,162,163,164,165,166,167,168,169,170,171,172,173,174,175,176,177,178,179,180,181,182,183,184,185,186,187,188,189,190,191,192,193,194,195,196,197,198,199,200,201,202,203,204,205,206,207,208,209,210,211,212,213,214,215,216,217,218,219,220,221,222,223,224,225,226,227,228,229,230,231,232,233,234,235,236,237,238,239,240,241,242,243,244,245,246,247,248,249,250,251,252,253,254,255,256,257,258,259,260,261,262,263,264,265,266,267,268,269,270,271,272,273,274,275,276,277,278,279,280,281,282,283,284,285,286,287,288,289,290,291,292,293,294,295,296,297,298,299,300,301,302,303,304,305,306,307,308,309,310,311,312,313,314,315,316,317,318,319,320,321,322,323,324,325,326,327,328,329,330,331,332,333,334,335,336,337,338,339,340,341,342,343,344,345,346,347,348,349,350,351,352,353,354,355,356,357,358,359,360,361,362,363,364,365,366,367,368,369,370,371,372,373,374,375,376,377,378,379,380,381,382,383,384,385,386,387,388,389,390,391,392,393,394,395,396,397,398,399,400,401,402,403,404,405,406,407,408,409,410,411,412,413,414,415,416,417,418,419,420,421,422,423,424,425,426,427,428,429,430,431,432,433,434,435,436,437,438,439,440,441,442,443,444,445,446,447,448,449,450,451,452,453,454,455,456,457,458,459,460,461,462,463,464,465,466,467,468,469,470,471,472,473,474,475,476,477,478,479,480,481,482,483,484,485,486,487,488,489,490,491,492,493,494,495,496,497,498,499,500,501,502,503,504,505,506,507,508,509,510,511,512,513,514,515,516,517,518,519,520,521,522,523,524,525,526,527,528,529,530,531,532,533,534,535,536,537,538,539,540,541,542,543,544,545,546,547,548,549,550,551,552,553,554,555,556,557,558,559,560,561,562,563,564,565,566,567,568,569,570,571,572,573,574,575,576,577,578,579,580,581,582,583,584,585,586,587,588,589,590,591,592,593,594,595,596,597,598,599,600,601,602,603,604,605,606,607,608,609,610,611,612,613,614,615,616,617,618,619,620,621,622,623,624,625,626,627,628,629,630,631,632,633,634,635,636,637,638,639,640,641,642,643,644,645,646,647,648,649,650,651,652,653,654,655,656,657,658,659,660,661,662,663,664,665,666,667,668,669,670,671,672,673,674,675,676,677,678,679,680,681,682,683,684,685,686,687,688,689,690,691,692,693,694,695,696,697,698,699,700,701,702,703,704,705,706,707,708,709,710,711,712,713,714,715,716,717,718,719,720,721,722,723,724,725,726,727,728,729,730,731,732,733,734,735,736,737,738,739,740,741,742,743,744,745,746,747,748,749,750,751,752,753,754,755,756,757,758,759,760,761,762,763,764,765,766,767,768,769,770,771,772,773,774,775,776,777,778,779,780,781,782,783,784,785,786,787,788,789,790,791,792,793,794,795,796,797,798,799,800,801,802,803,804,805,806,807,808,809,810,811,812,813,814,815,816,817,818,819,820,821,822,823,824,825,826,827,828,829,830,831,832,833,834,835,836,837,838,839,840,841,842,843,844,845,846,847,848,849,850,851,852,853,854,855,856,857,858,859,860,861,862,863,864,865,866,867,868,869,870,871,872,873,874,875,876,877,878,879,880,881,882,883,884,885,886,887,888,889,890,891,892,893,894,895,896,897,898,899,900,901,902,903,904,905,906,907,908,909,910,911,912,913,914,915,916,917,918,919,920,921,922,923,924,925,926,927,928,929,930,931,932,933,934,935,936,937,938,939,940,941,942,943,944,945,946,947,948,949,950,951,952,953,954,955,956,957,958,959,960,961,962,963,964,965,966,967,968,969,970,971,972,973,974,975,976,977,978,979,980,981,982,983,984,985,986,987,988,989,990,991,992,993,994,995,996,997,998,999,1000,1001,1002,1003,1004,1005,1006,1007,1008,1009,1010,1011,1012,1013,1014,1015,1016,1017,1018,1019,1020,1021,1022,1023,1024,1025,1026,1027,1028,1029,1030,1031,1032,1033,1034,1035,1036,1037,1038,1039,1040,1041,1042,1043,1044,1045,1046,1047,1048,1049,1050,1051,1052,1053,1054,1055,1056,1057,1058,1059,1060,1061,1062,1063,1064,1065,1066,1067,1068,1069,1070,1071,1072,1073,1074,1075,1076,1077,1078,1079,1080,1081,1082,1083,1084,1085,1086,1087,1088,1089,1090,1091,1092,1093,1094,1095,1096,1097,1098,1099,1100,1101,1102,1103,1104,1105,1106,1107,1108,1109,1110,1111,1112,1113,1114,1115,1116,1117,1118,1119,1120,1121,1122,1123,1124,1125,1126,1127,1128,1129,1130,1131,1132,1133,1134,1135,1136,1137,1138,1139,1140,1141,1142,1143,1144,1145,1146,1147,1148,1149,1150,1151,1152,1153,1154,1155,1156,1157,1158,1159,1160,1161,1162,1163,1164,1165,1166,1167,1168,1169,1170,1171,1172,1173,1174,1175,1176,1177,1178,1179,1180,1181,1182,1183,1184,1185,1186,1187,1188,1189,1190,1191,1192,1193,1194,1195,1196,1197,1198,1199,1200,1201,1202,1203,1204,1205,1206,1207,1208,1209,1210,1211,1212,1213,1214,1215,1216,1217,1218,1219,1220,1221,1222,1223,1224,1225,1226,1227,1228,1229,1230,1231,1232,1233,1234,1235,1236,1237,1238,1239,1240,1241,1242,1243,1244,1245,1246,1247,1248,1249,1250,1251,1252,1253,1254,1255,1256,1257,1258,1259,1260,1261,1262,1263,1264,1265,1266,1267,1268,1269,1270,1271,1272,1273,1274,1275,1276,1277,1278,1279,1280,1281,1282,1283,1284,1285,1286,1287,1288,1289,1290,1291,1292,1293,1294,1295,1296,1297,1298,1299,1300,1301,1302,1303,1304,1305,1306,1307,1308,1309,1310,1311,1312,1313,1314,1315,1316,1317,1318,1319,1320,1321,1322,1323,1324,1325,1326,1327,1328,1329,1330,1331,1332,1333,1334,1335,1336,1337,1338,1339,1340,1341,1342,1343,1344,1345,1346,1347,1348,1349,1350,1351,1352,1353,1354,1355,1356,1357,1358,1359,1360,1361,1362,1363,1364,1365,1366,1367,1368,1369,1370,1371,1372,1373,1374,1375,1376,1377,1378,1379,1380,1381,1382,1383,1384,1385,1386,1387,1388,1389,1390,1391,1392,1393,1394,1395,1396,1397,1398,1399,1400,1401,1402,1403,1404,1405,1406,1407,1408,1409,1410,1411,1412,1413,1414,1415,1416,1417,1418,1419,1420,1421,1422,1423,1424,1425,1426,1427,1428,1429,1430,1431,1432,1433,1434,1435,1436,1437,1438,1439,1440,1441,1442,1443,1444,1445,1446,1447,1448,1449,1450,1451,1452,1453,1454,1455,1456,1457,1458,1459,1460,1461,1462,1463,1464,1465,1466,1467,1468,1469,1470,1471,1472,1473,1474,1475,1476,1477,1478,1479,1480,1481,1482,1483,1484,1485,1486,1487,1488,1489,1490,1491,1492,1493,1494,1495,1496,1497,1498,1499,1500,1501,1502,1503,1504,1505,1506,1507,1508,1509,1510,1511,1512,1513,1514,1515,1516,1517,1518,1519,1520,1521,1522,1523,1524,1525,1526,1527,1528,1529,1530,1531,1532,1533,1534,1535,1536,1537,1538,1539,1540,1541,1542,1543,1544,1545,1546,1547,1548,1549,1550,1551,1552,1553,1554,1555,1556,1557,1558,1559,1560,1561,1562,1563,1564,1565,1566,1567,1568,1569,1570,1571,1572,1573,1574,1575,1576,1577,1578,1579,1580,1581,1582,1583,1584,1585,1586,1587,1588,1589,1590,1591,1592,1593,1594,1595,1596,1597,1598,1599,1600,1601,1602,1603,1604,1605,1606,1607,1608,1609,1610,1611,1612,1613,1614,1615,1616,1617,1618,1619,1620,1621,1622,1623,1624,1625,1626,1627,1628,1629,1630,1631,1632,1633,1634,1635,1636,1637,1638,1639,1640,1641,1642,1643,1644,1645,1646,1647,1648,1649,1650,1651,1652,1653,1654,1655,1656,1657,1658,1659,1660,1661,1662,1663,1664,1665,1666,1667,1668,1669,1670,1671,1672,1673,1674,1675,1676,1677,1678,1679,1680,1681,1682,1683,1684,1685,1686,1687,1688,1689,1690,1691,1692,1693,1694,1695,1696,1697,1698,1699,1700,1701,1702,1703,1704,1705,1706,1707,1708,1709,1710,1711,1712,1713,1714,1715,1716,1717,1718,1719,1720,1721,1722,1723,1724,1725,1726,1727,1728,1729,1730,1731,1732,1733,1734,1735,1736,1737,1738,1739,1740,1741,1742,1743,1744,1745,1746,1747,1748,1749,1750,1751,1752,1753,1754,1755,1756,1757,1758,1759,1760,1761,1762,1763,1764,1765,1766,1767,1768,1769,1770,1771,1772,1773,1774,1775,1776,1777,1778,1779,1780,1781,1782,1783,1784,1785,1786,1787,1788,1789,1790,1791,1792,1793,1794,1795,1796,1797,1798,1799,1800,1801,1802,1803,1804,1805,1806,1807,1808,1809,1810,1811,1812,1813,1814,1815,1816,1817,1818,1819,1820,1821,1822,1823,1824,1825,1826,1827,1828,1829,1830,1831,1832,1833,1834,1835,1836,1837,1838,1839,1840,1841,1842,1843,1844,1845,1846,1847,1848,1849,1850,1851,1852,1853,1854,1855,1856,1857,1858,1859,1860,1861,1862,1863,1864,1865,1866,1867,1868,1869,1870,1871,1872,1873,1874,1875,1876,1877,1878,1879,1880,1881,1882,1883,1884,1885,1886,1887,1888,1889,1890,1891,1892,1893,1894,1895,1896,1897,1898,1899,1900,1901,1902,1903,1904,1905,1906,1907,1908,1909,1910,1911,1912,1913,1914,1915,1916,1917,1918,1919,1920,1921,1922,1923,1924,1925,1926,1927,1928,1929,1930,1931,1932,1933,1934,1935,1936,1937,1938,1939,1940,1941,1942,1943,1944,1945,1946,1947,1948,1949,1950,1951,1952,1953,1954,1955,1956,1957,1958,1959,1960,1961,1962,1963,1964,1965,1966,1967,1968,1969,1970,1971,1972,1973,1974,1975,1976,1977,1978,1979,1980,1981,1982,1983,1984,1985,1986,1987,1988,1989,1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019,2020,2021,2022,2023,2024,2025,2026,2027,2028,2029,2030,2031,2032,2033,2034,2035,2036,2037,2038,2039,2040,2041,2042,2043,2044,2045,2046,2047,2048,2049,2050,2051,2052,2053,2054,2055,2056,2057,2058,2059,2060,2061,2062,2063,2064,2065,2066,2067,2068,2069,2070,2071,2072,2073,2074,2075,2076,2077,2078,2079,2080,2081,2082,2083,2084,2085,2086,2087,2088,2089,2090,2091,2092,2093,2094,2095,2096,2097,2098,2099,2100,2101,2102,2103,2104,2105,2106,2107,2108,2109,2110,2111,2112,2113,2114,2115,2116,2117,2118,2119,2120,2121,2122,2123,2124,2125,2126,2127,2128,2129,2130,2131,2132,2133,2134,2135,2136,2137,2138,2139,2140,2141,2142,2143,2144,2145,2146,2147,2148,2149,2150,2151,2152,2153,2154,2155,2156,2157,2158,2159,2160,2161,2162,2163,2164,2165,2166,2167,2168,2169,2170,2171,2172,2173,2174,2175,2176,2177,2178,2179,2180,2181,2182,2183,2184,2185,2186,2187,2188,2189,2190,2191,2192,2193,2194,2195,2196,2197,2198,2199,2200,2201,2202,2203,2204,2205,2206,2207,2208,2209,2210,2211,2212,2213,2214,2215,2216,2217,2218,2219,2220,2221,2222,2223,2224,2225,2226,2227,2228,2229,2230,2231,2232,2233,2234,2235,2236,2237,2238,2239,2240,2241,2242,2243,2244,2245,2246,2247,2248,2249,2250,2251,2252,2253,2254,2255,2256,2257,2258,2259,2260,2261,2262,2263,2264,2265,2266,2267,2268,2269,2270,2271,2272,2273,2274,2275,2276,2277,2278,2279,2280,2281,2282,2283,2284,2285,2286,2287,2288,2289,2290,2291,2292,2293,2294,2295,2296,2297,2298,2299,2300,2301,2302,2303,2304,2305,2306,2307,2308,2309,2310,2311,2312,2313,2314,2315,2316,2317,2318,2319,2320,2321,2322,2323,2324,2325,2326,2327,2328,2329,2330,2331,2332,2333,2334,2335,2336,2337,2338,2339,2340,2341,2342,2343,2344,2345,2346,2347,2348,2349,2350,2351,2352,2353,2354,2355,2356,2357,2358,2359,2360,2361,2362,2363,2364,2365,2366,2367,2368,2369,2370,2371,2372,2373,2374,2375,2376,2377,2378,2379,2380,2381,2382,2383,2384,2385,2386,2387,2388,2389,2390,2391,2392,2393,2394,2395,2396,2397,2398,2399,2400,2401,2402,2403,2404,2405,2406,2407,2408,2409,2410,2411,2412,2413,2414,2415,2416,2417,2418,2419,2420,2421,2422,2423,2424,2425,2426,2427,2428,2429,2430,2431,2432,2433,2434,2435,2436,2437,2438,2439,2440,2441,2442,2443,2444,2445,2446,2447,2448,2449,2450,2451,2452,2453,2454,2455,2456,2457,2458,2459,2460,2461,2462,2463,2464,2465,2466,2467,2468,2469,2470,2471,2472,2473,2474,2475,2476,2477,2478,2479,2480,2481,2482,2483,2484,2485,2486,2487,2488,2489,2490,2491,2492,2493,2494,2495,2496,2497,2498,2499,2500,2501,2502,2503,2504,2505,2506,2507,2508,2509,2510,2511,2512,2513,2514,2515,2516,2517,2518,2519,2520,2521,2522,2523,2524,2525,2526,2527,2528,2529,2530,2531,2532,2533,2534,2535,2536,2537,2538,2539,2540,2541,2542,2543,2544,2545,2546,2547,2548,2549,2550,2551,2552,2553,2554,2555,2556,2557,2558,2559,2560,2561,2562,2563,2564,2565,2566,2567,2568,2569,2570,2571,2572,2573,2574,2575,2576,2577,2578,2579,2580,2581,2582,2583,2584,2585,2586,2587,2588,2589,2590,2591,2592,2593,2594,2595,2596,2597,2598,2599,2600,2601,2602,2603,2604,2605,2606,2607,2608,2609,2610,2611,2612,2613,2614,2615,2616,2617,2618,2619,2620,2621,2622,2623,2624,2625,2626,2627,2628,2629,2630,2631,2632,2633,2634,2635,2636,2637,2638,2639,2640,2641,2642,2643,2644,2645,2646,2647,2648,2649,2650,2651,2652,2653,2654,2655,2656,2657,2658,2659,2660,2661,2662,2663,2664,2665,2666,2667,2668,2669,2670,2671,2672,2673,2674,2675,2676,2677,2678,2679,2680,2681,2682,2683,2684,2685,2686,2687,2688,2689,2690,2691,2692,2693,2694,2695,2696,2697,2698,2699,2700,2701,2702,2703,2704,2705,2706,2707,2708,2709,2710,2711,2712,2713,2714,2715,2716,2717,2718,2719,2720,2721,2722,2723,2724,2725,2726,2727,2728,2729,2730,2731,2732,2733,2734,2735,2736,2737,2738,2739,2740,2741,2742,2743,2744,2745,2746,2747,2748,2749,2750,2751,2752,2753,2754,2755,2756,2757,2758,2759,2760,2761,2762,2763,2764,2765,2766,2767,2768,2769,2770,2771,2772,2773,2774,2775,2776,2777,2778,2779,2780,2781,2782,2783,2784,2785,2786,2787,2788,2789,2790,2791,2792,2793,2794,2795,2796,2797,2798,2799,2800,2801,2802,2803,2804,2805,2806,2807,2808,2809,2810,2811,2812,2813,2814,2815,2816,2817,2818,2819,2820,2821,2822,2823,2824,2825,2826,2827,2828,2829,2830,2831,2832,2833,2834,2835,2836,2837,2838,2839,2840,2841,2842,2843,2844,2845,2846,2847,2848,2849,2850,2851,2852,2853,2854,2855,2856,2857,2858,2859,2860,2861,2862,2863,2864,2865,2866,2867,2868,2869,2870,2871,2872,2873,2874,2875,2876,2877,2878,2879,2880,2881,2882,2883,2884,2885,2886,2887,2888,2889,2890,2891,2892,2893,2894,2895,2896,2897,2898,2899,2900,2901,2902,2903,2904,2905,2906,2907,2908,2909,2910,2911,2912,2913,2914,2915,2916,2917,2918,2919,2920,2921,2922,2923,2924,2925,2926,2927,2928,2929,2930,2931,2932,2933,2934,2935,2936,2937,2938,2939,2940,2941,2942,2943,2944,2945,2946,2947,2948,2949,2950,2951,2952,2953,2954,2955,2956,2957,2958,2959,2960,2961,2962,2963,2964,2965,2966,2967,2968,2969,2970,2971,2972,2973,2974,2975,2976,2977,2978,2979,2980,2981,2982,2983,2984,2985,2986,2987,2988,2989,2990,2991,2992,2993,2994,2995,2996,2997,2998,2999,3000,3001,3002,3003,3004,3005,3006,3007,3008,3009,3010,3011,3012,3013,3014,3015,3016,3017,3018,3019,3020,3021,3022,3023,3024,3025,3026,3027,3028,3029,3030,3031,3032,3033,3034,3035,3036,3037,3038,3039,3040,3041,3042,3043,3044,3045,3046,3047,3048,3049,3050,3051,3052,3053,3054,3055,3056,3057,3058,3059,3060,3061,3062,3063,3064,3065,3066,3067,3068,3069,3070,3071,3072,3073,3074,3075,3076,3077,3078,3079,3080,3081,3082,3083,3084,3085,3086,3087,3088,3089,3090,3091,3092,3093,3094,3095,3096,3097,3098,3099,3100,3101,3102,3103,3104,3105,3106,3107,3108,3109,3110,3111,3112,3113,3114,3115,3116,3117,3118,3119,3120,3121,3122,3123,3124,3125,3126,3127,3128,3129,3130,3131,3132,3133,3134,3135,3136,3137,3138,3139,3140,3141,3142,3143,3144,3145,3146,3147,3148,3149,3150,3151,3152,3153,3154,3155,3156,3157,3158,3159,3160,3161,3162,3163,3164,3165,3166,3167,3168,3169,3170,3171,3172,3173,3174,3175,3176,3177,3178,3179,3180,3181,3182,3183,3184,3185,3186,3187,3188,3189,3190,3191,3192,3193,3194,3195,3196,3197,3198,3199,3200,3201,3202,3203,3204,3205,3206,3207,3208,3209,3210,3211,3212,3213,3214,3215,3216,3217,3218,3219,3220,3221,3222,3223,3224,3225,3226,3227,3228,3229,3230,3231,3232,3233,3234,3235,3236,3237,3238,3239,3240,3241,3242,3243,3244,3245,3246,3247,3248,3249,3250,3251,3252,3253,3254,3255,3256,3257,3258,3259,3260,3261,3262,3263,3264,3265,3266,3267,3268,3269,3270,3271,3272,3273,3274,3275,3276,3277,3278,3279,3280,3281,3282,3283,3284,3285,3286,3287,3288,3289,3290,3291,3292,3293,3294,3295,3296,3297,3298,3299,3300,3301,3302,3303,3304,3305,3306,3307,3308,3309,3310,3311,3312,3313,3314,3315,3316,3317,3318,3319,3320,3321,3322,3323,3324,3325,3326,3327,3328,3329,3330,3331,3332,3333,3334,3335,3336,3337,3338,3339,3340,3341,3342,3343,3344,3345,3346,3347,3348,3349,3350,3351,3352,3353,3354,3355,3356,3357,3358,3359,3360,3361,3362,3363,3364,3365,3366,3367,3368,3369,3370,3371,3372,3373,3374,3375,3376,3377,3378,3379,3380,3381,3382,3383,3384,3385,3386,3387,3388,3389,3390,3391,3392,3393,3394,3395,3396,3397,3398,3399,3400,3401,3402,3403,3404,3405,3406,3407,3408,3409,3410,3411,3412,3413,3414,3415,3416,3417,3418,3419,3420,3421,3422,3423,3424,3425,3426,3427,3428,3429,3430,3431,3432,3433,3434,3435,3436,3437,3438,3439,3440,3441,3442,3443,3444,3445,3446,3447,3448,3449,3450,3451,3452,3453,3454,3455,3456,3457,3458,3459,3460,3461,3462,3463,3464,3465,3466,3467,3468,3469,3470,3471,3472,3473,3474,3475,3476,3477,3478,3479,3480,3481,3482,3483,3484,3485,3486,3487,3488,3489,3490,3491,3492,3493,3494,3495,3496,3497,3498,3499,3500,3501,3502,3503,3504,3505,3506,3507,3508,3509,3510,3511,3512,3513,3514,3515,3516,3517,3518,3519,3520,3521,3522,3523,3524,3525,3526,3527,3528,3529,3530,3531,3532,3533,3534,3535,3536,3537,3538,3539,3540,3541,3542,3543,3544,3545,3546,3547,3548,3549,3550,3551,3552,3553,3554,3555,3556,3557,3558,3559,3560,3561,3562,3563,3564,3565,3566,3567,3568,3569,3570,3571,3572,3573,3574,3575,3576,3577,3578,3579,3580,3581,3582,3583,3584,3585,3586,3587,3588,3589,3590,3591,3592,3593,3594,3595,3596,3597,3598,3599,3600,3601,3602,3603,3604,3605,3606,3607,3608,3609,3610,3611,3612,3613,3614,3615,3616,3617,3618,3619,3620,3621,3622,3623,3624,3625,3626,3627,3628,3629,3630,3631,3632,3633,3634,3635,3636,3637,3638,3639,3640,3641,3642,3643,3644,3645,3646,3647,3648,3649,3650,3651,3652,3653,3654,3655,3656,3657,3658,3659,3660,3661,3662,3663,3664,3665,3666,3667,3668,3669,3670,3671,3672,3673,3674,3675,3676,3677,3678,3679,3680,3681,3682,3683,3684,3685,3686,3687,3688,3689,3690,3691,3692,3693,3694,3695,3696,3697,3698,3699,3700,3701,3702,3703,3704,3705,3706,3707,3708,3709,3710,3711,3712,3713,3714,3715,3716,3717,3718,3719,3720,3721,3722,3723,3724,3725,3726,3727,3728,3729,3730,3731,3732,3733,3734,3735,3736,3737,3738,3739,3740,3741,3742,3743,3744,3745,3746,3747,3748,3749,3750,3751,3752,3753,3754,3755,3756,3757,3758,3759,3760,3761,3762,3763,3764,3765,3766,3767,3768,3769,3770,3771,3772,3773,3774,3775,3776,3777,3778,3779,3780,3781,3782,3783,3784,3785,3786,3787,3788,3789,3790,3791,3792,3793,3794,3795,3796,3797,3798,3799,3800,3801,3802,3803,3804,3805,3806,3807,3808,3809,3810,3811,3812,3813,3814,3815,3816,3817,3818,3819,3820,3821,3822,3823,3824,3825,3826,3827,3828,3829,3830,3831,3832,3833,3834,3835,3836,3837,3838,3839,3840,3841,3842,3843,3844,3845,3846,3847,3848,3849,3850,3851,3852,3853,3854,3855,3856,3857,3858,3859,3860,3861,3862,3863,3864,3865,3866,3867,3868,3869,3870,3871,3872,3873,3874,3875,3876,3877,3878,3879,3880,3881,3882,3883,3884,3885,3886,3887,3888,3889,3890,3891,3892,3893,3894,3895,3896,3897,3898,3899,3900,3901,3902,3903,3904,3905,3906,3907,3908,3909,3910,3911,3912,3913,3914,3915,3916,3917,3918,3919,3920,3921,3922,3923,3924,3925,3926,3927,3928,3929,3930,3931,3932,3933,3934,3935,3936,3937,3938,3939,3940,3941,3942,3943,3944,3945,3946,3947,3948,3949,3950,3951,3952,3953,3954,3955,3956,3957,3958,3959,3960,3961,3962,3963,3964,3965,3966,3967,3968,3969,3970,3971,3972,3973,3974,3975,3976,3977,3978,3979,3980,3981,3982,3983,3984,3985,3986,3987,3988,3989,3990,3991,3992,3993,3994,3995,3996,3997,3998,3999,4000,4001,4002,4003,4004,4005,4006,4007,4008,4009,4010,4011,4012,4013,4014,4015,4016,4017,4018,4019,4020,4021,4022,4023,4024,4025,4026,4027,4028,4029,4030,4031,4032,4033,4034,4035,4036,4037,4038,4039,4040,4041,4042,4043,4044,4045,4046,4047,4048,4049,4050,4051,4052,4053,4054,4055,4056,4057,4058,4059,4060,4061,4062,4063,4064,4065,4066,4067,4068,4069,4070,4071,4072,4073,4074,4075,4076,4077,4078,4079,4080,4081,4082,4083,4084,4085,4086,4087,4088,4089,4090,4091,4092,4093,4094,4095,4096,4097,4098,4099,4100,4101,4102,4103,4104,4105,4106,4107,4108,4109,4110,4111,4112,4113,4114,4115,4116,4117,4118,4119,4120,4121,4122,4123,4124,4125,4126,4127,4128,4129,4130,4131,4132,4133,4134,4135,4136,4137,4138,4139,4140,4141,4142,4143,4144,4145,4146,4147,4148,4149,4150,4151,4152,4153,4154,4155,4156,4157,4158,4159,4160,4161,4162,4163,4164,4165,4166,4167,4168,4169,4170,4171,4172,4173,4174,4175,4176,4177,4178,4179,4180,4181,4182,4183,4184,4185,4186,4187,4188,4189,4190,4191,4192,4193,4194,4195,4196,4197,4198,4199,4200,4201,4202,4203,4204,4205,4206,4207,4208,4209,4210,4211,4212,4213,4214,4215,4216,4217,4218,4219,4220,4221,4222,4223,4224,4225,4226,4227,4228,4229,4230,4231,4232,4233,4234,4235,4236,4237,4238,4239,4240,4241,4242,4243,4244,4245,4246,4247,4248,4249,4250,4251,4252,4253,4254,4255,4256,4257,4258,4259,4260,4261,4262,4263,4264,4265,4266,4267,4268,4269,4270,4271,4272,4273,4274,4275,4276,4277,4278,4279,4280,4281,4282,4283,4284,4285,4286,4287,4288,4289,4290,4291,4292,4293,4294,4295,4296,4297,4298,4299,4300,4301,4302,4303,4304,4305,4306,4307,4308,4309,4310,4311,4312,4313,4314,4315,4316,4317,4318,4319,4320,4321,4322,4323,4324,4325,4326,4327,4328,4329,4330,4331,4332,4333,4334,4335,4336,4337,4338,4339,4340,4341,4342,4343,4344,4345,4346,4347,4348,4349,4350,4351,4352,4353,4354,4355,4356,4357,4358,4359,4360,4361,4362,4363,4364,4365,4366,4367,4368,4369,4370,4371,4372,4373,4374,4375,4376,4377,4378,4379,4380,4381,4382,4383,4384,4385,4386,4387,4388,4389,4390,4391,4392,4393,4394,4395,4396,4397,4398,4399,4400,4401,4402,4403,4404,4405,4406,4407,4408,4409,4410,4411,4412,4413,4414,4415,4416,4417,4418,4419,4420,4421,4422,4423,4424,4425,4426,4427,4428,4429,4430,4431,4432,4433,4434,4435,4436,4437,4438,4439,4440,4441,4442,4443,4444,4445,4446,4447,4448,4449,4450,4451,4452,4453,4454,4455,4456,4457,4458,4459,4460,4461,4462,4463,4464,4465,4466,4467,4468,4469,4470,4471,4472,4473,4474,4475,4476,4477,4478,4479,4480,4481,4482,4483,4484,4485,4486,4487,4488,4489,4490,4491,4492,4493,4494,4495,4496,4497,4498,4499,4500,4501,4502,4503,4504,4505,4506,4507,4508,4509,4510,4511,4512,4513,4514,4515,4516,4517,4518,4519,4520,4521,4522,4523,4524,4525,4526,4527,4528,4529,4530,4531,4532,4533,4534,4535,4536,4537,4538,4539,4540,4541,4542,4543,4544,4545,4546,4547,4548,4549,4550,4551,4552,4553,4554,4555,4556,4557,4558,4559,4560,4561,4562,4563,4564,4565,4566,4567,4568,4569,4570,4571,4572,4573,4574,4575,4576,4577,4578,4579,4580,4581,4582,4583,4584,4585,4586,4587,4588,4589,4590,4591,4592,4593,4594,4595,4596,4597,4598,4599,4600,4601,4602,4603,4604,4605,4606,4607,4608,4609,4610,4611,4612,4613,4614,4615,4616,4617,4618,4619,4620,4621,4622,4623,4624,4625,4626,4627,4628,4629,4630,4631,4632,4633,4634,4635,4636,4637,4638,4639,4640,4641,4642,4643,4644,4645,4646,4647,4648,4649,4650,4651,4652,4653,4654,4655,4656,4657,4658,4659,4660,4661,4662,4663,4664,4665,4666,4667,4668,4669,4670,4671,4672,4673,4674,4675,4676,4677,4678,4679,4680,4681,4682,4683,4684,4685,4686,4687,4688,4689,4690,4691,4692,4693,4694,4695,4696,4697,4698,4699,4700,4701,4702,4703,4704,4705,4706,4707,4708,4709,4710,4711,4712,4713,4714,4715,4716,4717,4718,4719,4720,4721,4722,4723,4724,4725,4726,4727,4728,4729,4730,4731,4732,4733,4734,4735,4736,4737,4738,4739,4740,4741,4742,4743,4744,4745,4746,4747,4748,4749,4750,4751,4752,4753,4754,4755,4756,4757,4758,4759,4760,4761,4762,4763,4764,4765,4766,4767,4768,4769,4770,4771,4772,4773,4774,4775,4776,4777,4778,4779,4780,4781,4782,4783,4784,4785,4786,4787,4788,4789,4790,4791,4792,4793,4794,4795,4796,4797,4798,4799,4800,4801,4802,4803,4804,4805,4806,4807,4808,4809,4810,4811,4812,4813,4814,4815,4816,4817,4818,4819,4820,4821,4822,4823,4824,4825,4826,4827,4828,4829,4830,4831,4832,4833,4834,4835,4836,4837,4838,4839,4840,4841,4842,4843,4844,4845,4846,4847,4848,4849,4850,4851,4852,4853,4854,4855,4856,4857,4858,4859,4860,4861,4862,4863,4864,4865,4866,4867,4868,4869,4870,4871,4872,4873,4874,4875,4876,4877,4878,4879,4880,4881,4882,4883,4884,4885,4886,4887,4888,4889,4890,4891,4892,4893,4894,4895,4896,4897,4898,4899,4900,4901,4902,4903,4904,4905,4906,4907,4908,4909,4910,4911,4912,4913,4914,4915,4916,4917,4918,4919,4920,4921,4922,4923,4924,4925,4926,4927,4928,4929,4930,4931,4932,4933,4934,4935,4936,4937,4938,4939,4940,4941,4942,4943,4944,4945,4946,4947,4948,4949,4950,4951,4952,4953,4954,4955,4956,4957,4958,4959,4960,4961,4962,4963,4964,4965,4966,4967,4968,4969,4970,4971,4972,4973,4974,4975,4976,4977,4978,4979,4980,4981,4982,4983,4984,4985,4986,4987,4988,4989,4990,4991,4992,4993,4994,4995,4996,4997,4998,4999,5000,5001,5002,5003,5004,5005,5006,5007,5008,5009,5010,5011,5012,5013,5014,5015,5016,5017,5018,5019,5020,5021,5022,5023,5024,5025,5026,5027,5028,5029,5030,5031,5032,5033,5034,5035,5036,5037,5038,5039,5040,5041,5042,5043,5044,5045,5046,5047,5048,5049,5050,5051,5052,5053,5054,5055,5056,5057,5058,5059,5060,5061,5062,5063,5064,5065,5066,5067,5068,5069,5070,5071,5072,5073,5074,5075,5076,5077,5078,5079,5080,5081,5082,5083,5084,5085,5086,5087,5088,5089,5090,5091,5092,5093,5094,5095,5096,5097,5098,5099,5100,5101,5102,5103,5104,5105,5106,5107,5108,5109,5110,5111,5112,5113,5114,5115,5116,5117,5118,5119,5120,5121,5122,5123,5124,5125,5126,5127,5128,5129,5130,5131,5132,5133,5134,5135,5136,5137,5138,5139,5140,5141,5142,5143,5144,5145,5146,5147,5148,5149,5150,5151,5152,5153,5154,5155,5156,5157,5158,5159,5160,5161,5162,5163,5164,5165,5166,5167,5168,5169,5170,5171,5172,5173,5174,5175,5176,5177,5178,5179,5180,5181,5182,5183,5184,5185,5186,5187,5188,5189,5190,5191,5192,5193,5194,5195,5196,5197,5198,5199,5200,5201,5202,5203,5204,5205,5206,5207,5208,5209,5210,5211,5212,5213,5214,5215,5216,5217,5218,5219,5220,5221,5222,5223,5224,5225,5226,5227,5228,5229,5230,5231,5232,5233,5234,5235,5236,5237,5238,5239,5240,5241,5242,5243,5244,5245,5246,5247,5248,5249,5250,5251,5252,5253,5254,5255,5256,5257,5258,5259,5260,5261,5262,5263,5264,5265,5266,5267,5268,5269,5270,5271,5272,5273,5274,5275,5276,5277,5278,5279,5280,5281,5282,5283,5284,5285,5286,5287,5288,5289,5290,5291,5292,5293,5294,5295,5296,5297,5298,5299,5300,5301,5302,5303,5304,5305,5306,5307,5308,5309,5310,5311,5312,5313,5314,5315,5316,5317,5318,5319,5320,5321,5322,5323,5324,5325,5326,5327,5328,5329,5330,5331,5332,5333,5334,5335,5336,5337,5338,5339,5340,5341,5342,5343,5344,5345,5346,5347,5348,5349,5350,5351,5352,5353,5354,5355,5356,5357,5358,5359,5360,5361,5362,5363,5364,5365,5366,5367,5368,5369,5370,5371,5372,5373,5374,5375,5376,5377,5378,5379,5380,5381,5382,5383,5384,5385,5386,5387,5388,5389,5390,5391,5392,5393,5394,5395,5396,5397,5398,5399,5400,5401,5402,5403,5404,5405,5406,5407,5408,5409,5410,5411,5412,5413,5414,5415,5416,5417,5418,5419,5420,5421,5422,5423,5424,5425,5426,5427,5428,5429,5430,5431,5432,5433,5434,5435,5436,5437,5438,5439,5440,5441,5442,5443,5444,5445,5446,5447,5448,5449,5450,5451,5452,5453,5454,5455,5456,5457,5458,5459,5460,5461,5462,5463,5464,5465,5466,5467,5468,5469,5470,5471,5472,5473,5474,5475,5476,5477,5478,5479,5480,5481,5482,5483,5484,5485,5486,5487,5488,5489,5490,5491,5492,5493,5494,5495,5496,5497,5498,5499,5500,5501,5502,5503,5504,5505,5506,5507,5508,5509,5510,5511,5512,5513,5514,5515,5516,5517,5518,5519,5520,5521,5522,5523,5524,5525,5526,5527,5528,5529,5530,5531,5532,5533,5534,5535,5536,5537,5538,5539,5540,5541,5542,5543,5544,5545,5546,5547,5548,5549,5550,5551,5552,5553,5554,5555,5556,5557,5558,5559,5560,5561,5562,5563,5564,5565,5566,5567,5568,5569,5570,5571,5572,5573,5574,5575,5576,5577,5578,5579,5580,5581,5582,5583,5584,5585,5586,5587,5588,5589,5590,5591,5592,5593,5594,5595,5596,5597,5598,5599,5600,5601,5602,5603,5604,5605,5606,5607,5608,5609,5610,5611,5612,5613,5614,5615,5616,5617,5618,5619,5620,5621,5622,5623,5624,5625,5626,5627,5628,5629,5630,5631,5632,5633,5634,5635,5636,5637,5638,5639,5640,5641,5642,5643,5644,5645,5646,5647,5648,5649,5650,5651,5652,5653,5654,5655,5656,5657,5658,5659,5660,5661,5662,5663,5664,5665,5666,5667,5668,5669,5670,5671,5672,5673,5674,5675,5676,5677,5678,5679,5680,5681,5682,5683,5684,5685,5686,5687,5688,5689,5690,5691,5692,5693,5694,5695,5696,5697,5698,5699,5700,5701,5702,5703,5704,5705,5706,5707,5708,5709,5710,5711,5712,5713,5714,5715,5716,5717,5718,5719,5720,5721,5722,5723,5724,5725,5726,5727,5728,5729,5730,5731,5732,5733,5734,5735,5736,5737,5738,5739,5740,5741,5742,5743,5744,5745,5746,5747,5748,5749,5750,5751,5752,5753,5754,5755,5756,5757,5758,5759,5760,5761,5762,5763,5764,5765,5766,5767,5768,5769,5770,5771,5772,5773,5774,5775,5776,5777,5778,5779,5780,5781,5782,5783,5784,5785,5786,5787,5788,5789,5790,5791,5792,5793,5794,5795,5796,5797,5798,5799,5800,5801,5802,5803,5804,5805,5806,5807,5808,5809,5810,5811,5812,5813,5814,5815,5816,5817,5818,5819,5820,5821,5822,5823,5824,5825,5826,5827,5828,5829,5830,5831,5832,5833,5834,5835,5836,5837,5838,5839,5840,5841,5842,5843,5844,5845,5846,5847,5848,5849,5850,5851,5852,5853,5854,5855,5856,5857,5858,5859,5860,5861,5862,5863,5864,5865,5866,5867,5868,5869,5870,5871,5872,5873,5874,5875,5876,5877,5878,5879,5880,5881,5882,5883,5884,5885,5886,5887,5888,5889,5890,5891,5892,5893,5894,5895,5896,5897,5898,5899,5900,5901,5902,5903,5904,5905,5906,5907,5908,5909,5910,5911,5912,5913,5914,5915,5916,5917,5918,5919,5920,5921,5922,5923,5924,5925,5926,5927,5928,5929,5930,5931,5932,5933,5934,5935,5936,5937,5938,5939,5940,5941,5942,5943,5944,5945,5946,5947,5948,5949,5950,5951,5952,5953,5954,5955,5956,5957,5958,5959,5960,5961,5962,5963,5964,5965,5966,5967,5968,5969,5970,5971,5972,5973,5974,5975,5976,5977,5978,5979,5980,5981,5982,5983,5984,5985,5986,5987,5988,5989,5990,5991,5992,5993,5994,5995,5996,5997,5998,5999,6000,6001,6002,6003,6004,6005,6006,6007,6008,6009,6010,6011,6012,6013,6014,6015,6016,6017,6018,6019,6020,6021,6022,6023,6024,6025,6026,6027,6028,6029,6030,6031,6032,6033,6034,6035,6036,6037,6038,6039,6040,6041,6042,6043,6044,6045,6046,6047,6048,6049,6050,6051,6052,6053,6054,6055,6056,6057,6058,6059,6060,6061,6062,6063,6064,6065,6066,6067,6068,6069,6070,6071,6072,6073,6074,6075,6076,6077,6078,6079,6080,6081,6082,6083,6084,6085,6086,6087,6088,6089,6090,6091,6092,6093,6094,6095,6096,6097,6098,6099,6100,6101,6102,6103,6104,6105,6106,6107,6108,6109,6110,6111,6112,6113,6114,6115,6116,6117,6118,6119,6120,6121,6122,6123,6124,6125,6126,6127,6128,6129,6130,6131,6132,6133,6134,6135,6136,6137,6138,6139,6140,6141,6142,6143,6144,6145,6146,6147,6148,6149,6150,6151,6152,6153,6154,6155,6156,6157,6158,6159,6160,6161,6162,6163,6164,6165,6166,6167,6168,6169,6170,6171,6172,6173,6174,6175,6176,6177,6178,6179,6180,6181,6182,6183,6184,6185,6186,6187,6188,6189,6190,6191,6192,6193,6194,6195,6196,6197,6198,6199,6200,6201,6202,6203,6204,6205,6206,6207,6208,6209,6210,6211,6212,6213,6214,6215,6216,6217,6218,6219,6220,6221,6222,6223,6224,6225,6226,6227,6228,6229,6230,6231,6232,6233,6234,6235,6236,6237,6238,6239,6240,6241,6242,6243,6244,6245,6246,6247,6248,6249,6250,6251,6252,6253,6254,6255,6256,6257,6258,6259,6260,6261,6262,6263,6264,6265,6266,6267,6268,6269,6270,6271,6272,6273,6274,6275,6276,6277,6278,6279,6280,6281,6282,6283,6284,6285,6286,6287,6288,6289,6290,6291,6292,6293,6294,6295,6296,6297,6298,6299,6300,6301,6302,6303,6304,6305,6306,6307,6308,6309,6310,6311,6312,6313,6314,6315,6316,6317,6318,6319,6320,6321,6322,6323,6324,6325,6326,6327,6328,6329,6330,6331,6332,6333,6334,6335,6336,6337,6338,6339,6340,6341,6342,6343,6344,6345,6346,6347,6348,6349,6350,6351,6352,6353,6354,6355,6356,6357,6358,6359,6360,6361,6362,6363,6364,6365,6366,6367,6368,6369,6370,6371,6372,6373,6374,6375,6376,6377,6378,6379,6380,6381,6382,6383,6384,6385,6386,6387,6388,6389,6390,6391,6392,6393,6394,6395,6396,6397,6398,6399,6400,6401,6402,6403,6404,6405,6406,6407,6408,6409,6410,6411,6412,6413,6414,6415,6416,6417,6418,6419,6420,6421,6422,6423,6424,6425,6426,6427,6428,6429,6430,6431,6432,6433,6434,6435,6436,6437,6438,6439,6440,6441,6442,6443,6444,6445,6446,6447,6448,6449,6450,6451,6452,6453,6454,6455,6456,6457,6458,6459,6460,6461,6462,6463,6464,6465,6466,6467,6468,6469,6470,6471,6472,6473,6474,6475,6476,6477,6478,6479,6480,6481,6482,6483,6484,6485,6486,6487,6488,6489,6490,6491,6492,6493,6494,6495,6496,6497,6498,6499,6500,6501,6502,6503,6504,6505,6506,6507,6508,6509,6510,6511,6512,6513,6514,6515,6516,6517,6518,6519,6520,6521,6522,6523,6524,6525,6526,6527,6528,6529,6530,6531,6532,6533,6534,6535,6536,6537,6538,6539,6540,6541,6542,6543,6544,6545,6546,6547,6548,6549,6550,6551,6552,6553,6554,6555,6556,6557,6558,6559,6560,6561,6562,6563,6564,6565,6566,6567,6568,6569,6570,6571,6572,6573,6574,6575,6576,6577,6578,6579,6580,6581,6582,6583,6584,6585,6586,6587,6588,6589,6590,6591,6592,6593,6594,6595,6596,6597,6598,6599,6600,6601,6602,6603,6604,6605,6606,6607,6608,6609,6610,6611,6612,6613,6614,6615,6616,6617,6618,6619,6620,6621,6622,6623,6624,6625,6626,6627,6628,6629,6630,6631,6632,6633,6634,6635,6636,6637,6638,6639,6640,6641,6642,6643,6644,6645,6646,6647,6648,6649,6650,6651,6652,6653,6654,6655,6656,6657,6658,6659,6660,6661,6662,6663,6664,6665,6666,6667,6668,6669,6670,6671,6672,6673,6674,6675,6676,6677,6678,6679,6680,6681,6682,6683,6684,6685,6686,6687,6688,6689,6690,6691,6692,6693,6694,6695,6696,6697,6698,6699,6700,6701,6702,6703,6704,6705,6706,6707,6708,6709,6710,6711,6712,6713,6714,6715,6716,6717,6718,6719,6720,6721,6722,6723,6724,6725,6726,6727,6728,6729,6730,6731,6732,6733,6734,6735,6736,6737,6738,6739,6740,6741,6742,6743,6744,6745,6746,6747,6748,6749,6750,6751,6752,6753,6754,6755,6756,6757,6758,6759,6760,6761,6762,6763,6764,6765,6766,6767,6768,6769,6770,6771,6772,6773,6774,6775,6776,6777,6778,6779,6780,6781,6782,6783,6784,6785,6786,6787,6788,6789,6790,6791,6792,6793,6794,6795,6796,6797,6798,6799,6800,6801,6802,6803,6804,6805,6806,6807,6808,6809,6810,6811,6812,6813,6814,6815,6816,6817,6818,6819,6820,6821,6822,6823,6824,6825,6826,6827,6828,6829,6830,6831,6832,6833,6834,6835,6836,6837,6838,6839,6840,6841,6842,6843,6844,6845,6846,6847,6848,6849,6850,6851,6852,6853,6854,6855,6856,6857,6858,6859,6860,6861,6862,6863,6864,6865,6866,6867,6868,6869,6870,6871,6872,6873,6874,6875,6876,6877,6878,6879,6880,6881,6882,6883,6884,6885,6886,6887,6888,6889,6890,6891,6892,6893,6894,6895,6896,6897,6898,6899,6900,6901,6902,6903,6904,6905,6906,6907,6908,6909,6910,6911,6912,6913,6914,6915,6916,6917,6918,6919,6920,6921,6922,6923,6924,6925,6926,6927,6928,6929,6930,6931,6932,6933,6934,6935,6936,6937,6938,6939,6940,6941,6942,6943,6944,6945,6946,6947,6948,6949,6950,6951,6952,6953,6954,6955,6956,6957,6958,6959,6960,6961,6962,6963,6964,6965,6966,6967,6968,6969,6970,6971,6972,6973,6974,6975,6976,6977,6978,6979,6980,6981,6982,6983,6984,6985,6986,6987,6988,6989,6990,6991,6992,6993,6994,6995,6996,6997,6998,6999,7000,7001,7002,7003,7004,7005,7006,7007,7008,7009,7010,7011,7012,7013,7014,7015,7016,7017,7018,7019,7020,7021,7022,7023,7024,7025,7026,7027,7028,7029,7030,7031,7032,7033,7034,7035,7036,7037,7038,7039,7040,7041,7042,7043,7044,7045,7046,7047,7048,7049,7050,7051,7052,7053,7054,7055,7056,7057,7058,7059,7060,7061,7062,7063,7064,7065,7066,7067,7068,7069,7070,7071,7072,7073,7074,7075,7076,7077,7078,7079,7080,7081,7082,7083,7084,7085,7086,7087,7088,7089,7090,7091,7092,7093,7094,7095,7096,7097,7098,7099,7100,7101,7102,7103,7104,7105,7106,7107,7108,7109,7110,7111,7112,7113,7114,7115,7116,7117,7118,7119,7120,7121,7122,7123,7124,7125,7126,7127,7128,7129,7130,7131,7132,7133,7134,7135,7136,7137,7138,7139,7140,7141,7142,7143,7144,7145,7146,7147,7148,7149,7150,7151,7152,7153,7154,7155,7156,7157,7158,7159,7160,7161,7162,7163,7164,7165,7166,7167,7168,7169,7170,7171,7172,7173,7174,7175,7176,7177,7178,7179,7180,7181,7182,7183,7184,7185,7186,7187,7188,7189,7190,7191,7192,7193,7194,7195,7196,7197,7198,7199,7200,7201,7202,7203,7204,7205,7206,7207,7208,7209,7210,7211,7212,7213,7214,7215,7216,7217,7218,7219,7220,7221,7222,7223,7224,7225,7226,7227,7228,7229,7230,7231,7232,7233,7234,7235,7236,7237,7238,7239,7240,7241,7242,7243,7244,7245,7246,7247,7248,7249,7250,7251,7252,7253,7254,7255,7256,7257,7258,7259,7260,7261,7262,7263,7264,7265,7266,7267,7268,7269,7270,7271,7272,7273,7274,7275,7276,7277,7278,7279,7280,7281,7282,7283,7284,7285,7286,7287,7288,7289,7290,7291,7292,7293,7294,7295,7296,7297,7298,7299,7300,7301,7302,7303,7304,7305,7306,7307,7308,7309,7310,7311,7312,7313,7314,7315,7316,7317,7318,7319,7320,7321,7322,7323,7324,7325,7326,7327,7328,7329,7330,7331,7332,7333,7334,7335,7336,7337,7338,7339,7340,7341,7342,7343,7344,7345,7346,7347,7348,7349,7350,7351,7352,7353,7354,7355,7356,7357,7358,7359,7360,7361,7362,7363,7364,7365,7366,7367,7368,7369,7370,7371,7372,7373,7374,7375,7376,7377,7378,7379,7380,7381,7382,7383,7384,7385,7386,7387,7388,7389,7390,7391,7392,7393,7394,7395,7396,7397,7398,7399,7400,7401,7402,7403,7404,7405,7406,7407,7408,7409,7410,7411,7412,7413,7414,7415,7416,7417,7418,7419,7420,7421,7422,7423,7424,7425,7426,7427,7428,7429,7430,7431,7432,7433,7434,7435,7436,7437,7438,7439,7440,7441,7442,7443,7444,7445,7446,7447,7448,7449,7450,7451,7452,7453,7454,7455,7456,7457,7458,7459,7460,7461,7462,7463,7464,7465,7466,7467,7468,7469,7470,7471,7472,7473,7474,7475,7476,7477,7478,7479,7480,7481,7482,7483,7484,7485,7486,7487,7488,7489,7490,7491,7492,7493,7494,7495,7496,7497,7498,7499,7500,7501,7502,7503,7504,7505,7506,7507,7508,7509,7510,7511,7512,7513,7514,7515,7516,7517,7518,7519,7520,7521,7522,7523,7524,7525,7526,7527,7528,7529,7530,7531,7532,7533,7534,7535,7536,7537,7538,7539,7540,7541,7542,7543,7544,7545,7546,7547,7548,7549,7550,7551,7552,7553,7554,7555,7556,7557,7558,7559,7560,7561,7562,7563,7564,7565,7566,7567,7568,7569,7570,7571,7572,7573,7574,7575,7576,7577,7578,7579,7580,7581,7582,7583,7584,7585,7586,7587,7588,7589,7590,7591,7592,7593,7594,7595,7596,7597,7598,7599,7600,7601,7602,7603,7604,7605,7606,7607,7608,7609,7610,7611,7612,7613,7614,7615,7616,7617,7618,7619,7620,7621,7622,7623,7624,7625,7626,7627,7628,7629,7630,7631,7632,7633,7634,7635,7636,7637,7638,7639,7640,7641,7642,7643,7644,7645,7646,7647,7648,7649,7650,7651,7652,7653,7654,7655,7656,7657,7658,7659,7660,7661,7662,7663,7664,7665,7666,7667,7668,7669,7670,7671,7672,7673,7674,7675,7676,7677,7678,7679,7680,7681,7682,7683,7684,7685,7686,7687,7688,7689,7690,7691,7692,7693,7694,7695,7696,7697,7698,7699,7700,7701,7702,7703,7704,7705,7706,7707,7708,7709,7710,7711,7712,7713,7714,7715,7716,7717,7718,7719,7720,7721,7722,7723,7724,7725,7726,7727,7728,7729,7730,7731,7732,7733,7734,7735,7736,7737,7738,7739,7740,7741,7742,7743,7744,7745,7746,7747,7748,7749,7750,7751,7752,7753,7754,7755,7756,7757,7758,7759,7760,7761,7762,7763,7764,7765,7766,7767,7768,7769,7770,7771,7772,7773,7774,7775,7776,7777,7778,7779,7780,7781,7782,7783,7784,7785,7786,7787,7788,7789,7790,7791,7792,7793,7794,7795,7796,7797,7798,7799,7800,7801,7802,7803,7804,7805,7806,7807,7808,7809,7810,7811,7812,7813,7814,7815,7816,7817,7818,7819,7820,7821,7822,7823,7824,7825,7826,7827,7828,7829,7830,7831,7832,7833,7834,7835,7836,7837,7838,7839,7840,7841,7842,7843,7844,7845,7846,7847,7848,7849,7850,7851,7852,7853,7854,7855,7856,7857,7858,7859,7860,7861,7862,7863,7864,7865,7866,7867,7868,7869,7870,7871,7872,7873,7874,7875,7876,7877,7878,7879,7880,7881,7882,7883,7884,7885,7886,7887,7888,7889,7890,7891,7892,7893,7894,7895,7896,7897,7898,7899,7900,7901,7902,7903,7904,7905,7906,7907,7908,7909,7910,7911,7912,7913,7914,7915,7916,7917,7918,7919,7920,7921,7922,7923,7924,7925,7926,7927,7928,7929,7930,7931,7932,7933,7934,7935,7936,7937,7938,7939,7940,7941,7942,7943,7944,7945,7946,7947,7948,7949,7950,7951,7952,7953,7954,7955,7956,7957,7958,7959,7960,7961,7962,7963,7964,7965,7966,7967,7968,7969,7970,7971,7972,7973,7974,7975,7976,7977,7978,7979,7980,7981,7982,7983,7984,7985,7986,7987,7988,7989,7990,7991,7992,7993,7994,7995,7996,7997,7998,7999,8000,8001,8002,8003,8004,8005,8006,8007,8008,8009,8010,8011,8012,8013,8014,8015,8016,8017,8018,8019,8020,8021,8022,8023,8024,8025,8026,8027,8028,8029,8030,8031,8032,8033,8034,8035,8036,8037,8038,8039,8040,8041,8042,8043,8044,8045,8046,8047,8048,8049,8050,8051,8052,8053,8054,8055,8056,8057,8058,8059,8060,8061,8062,8063,8064,8065,8066,8067,8068,8069,8070,8071,8072,8073,8074,8075,8076,8077,8078,8079,8080,8081,8082,8083,8084,8085,8086,8087,8088,8089,8090,8091,8092,8093,8094,8095,8096,8097,8098,8099,8100,8101,8102,8103,8104,8105,8106,8107,8108,8109,8110,8111,8112,8113,8114,8115,8116,8117,8118,8119,8120,8121,8122,8123,8124,8125,8126,8127,8128,8129,8130,8131,8132,8133,8134,8135,8136,8137,8138,8139,8140,8141,8142,8143,8144,8145,8146,8147,8148,8149,8150,8151,8152,8153,8154,8155,8156,8157,8158,8159,8160,8161,8162,8163,8164,8165,8166,8167,8168,8169,8170,8171,8172,8173,8174,8175,8176,8177,8178,8179,8180,8181,8182,8183,8184,8185,8186,8187,8188,8189,8190,8191,8192,8193,8194,8195,8196,8197,8198,8199,8200,8201,8202,8203,8204,8205,8206,8207,8208,8209,8210,8211,8212,8213,8214,8215,8216,8217,8218,8219,8220,8221,8222,8223,8224,8225,8226,8227,8228,8229,8230,8231,8232,8233,8234,8235,8236,8237,8238,8239,8240,8241,8242,8243,8244,8245,8246,8247,8248,8249,8250,8251,8252,8253,8254,8255,8256,8257,8258,8259,8260,8261,8262,8263,8264,8265,8266,8267,8268,8269,8270,8271,8272,8273,8274,8275,8276,8277,8278,8279,8280,8281,8282,8283,8284,8285,8286,8287,8288,8289,8290,8291,8292,8293,8294,8295,8296,8297,8298,8299,8300,8301,8302,8303,8304,8305,8306,8307,8308,8309,8310,8311,8312,8313,8314,8315,8316,8317,8318,8319,8320,8321,8322,8323,8324,8325,8326,8327,8328,8329,8330,8331,8332,8333,8334,8335,8336,8337,8338,8339,8340,8341,8342,8343,8344,8345,8346,8347,8348,8349,8350,8351,8352,8353,8354,8355,8356,8357,8358,8359,8360,8361,8362,8363,8364,8365,8366,8367,8368,8369,8370,8371,8372,8373,8374,8375,8376,8377,8378,8379,8380,8381,8382,8383,8384,8385,8386,8387,8388,8389,8390,8391,8392,8393,8394,8395,8396,8397,8398,8399,8400,8401,8402,8403,8404,8405,8406,8407,8408,8409,8410,8411,8412,8413,8414,8415,8416,8417,8418,8419,8420,8421,8422,8423,8424,8425,8426,8427,8428,8429,8430,8431,8432,8433,8434,8435,8436,8437,8438,8439,8440,8441,8442,8443,8444,8445,8446,8447,8448,8449,8450,8451,8452,8453,8454,8455,8456,8457,8458,8459,8460,8461,8462,8463,8464,8465,8466,8467,8468,8469,8470,8471,8472,8473,8474,8475,8476,8477,8478,8479,8480,8481,8482,8483,8484,8485,8486,8487,8488,8489,8490,8491,8492,8493,8494,8495,8496,8497,8498,8499,8500,8501,8502,8503,8504,8505,8506,8507,8508,8509,8510,8511,8512,8513,8514,8515,8516,8517,8518,8519,8520,8521,8522,8523,8524,8525,8526,8527,8528,8529,8530,8531,8532,8533,8534,8535,8536,8537,8538,8539,8540,8541,8542,8543,8544,8545,8546,8547,8548,8549,8550,8551,8552,8553,8554,8555,8556,8557,8558,8559,8560,8561,8562,8563,8564,8565,8566,8567,8568,8569,8570,8571,8572,8573,8574,8575,8576,8577,8578,8579,8580,8581,8582,8583,8584,8585,8586,8587,8588,8589,8590,8591,8592,8593,8594,8595,8596,8597,8598,8599,8600,8601,8602,8603,8604,8605,8606,8607,8608,8609,8610,8611,8612,8613,8614,8615,8616,8617,8618,8619,8620,8621,8622,8623,8624,8625,8626,8627,8628,8629,8630,8631,8632,8633,8634,8635,8636,8637,8638,8639,8640,8641,8642,8643,8644,8645,8646,8647,8648,8649,8650,8651,8652,8653,8654,8655,8656,8657,8658,8659,8660,8661,8662,8663,8664,8665,8666,8667,8668,8669,8670,8671,8672,8673,8674,8675,8676,8677,8678,8679,8680,8681,8682,8683,8684,8685,8686,8687,8688,8689,8690,8691,8692,8693,8694,8695,8696,8697,8698,8699,8700,8701,8702,8703,8704,8705,8706,8707,8708,8709,8710,8711,8712,8713,8714,8715,8716,8717,8718,8719,8720,8721,8722,8723,8724,8725,8726,8727,8728,8729,8730,8731,8732,8733,8734,8735,8736,8737,8738,8739,8740,8741,8742,8743,8744,8745,8746,8747,8748,8749,8750,8751,8752,8753,8754,8755,8756,8757,8758,8759,8760,8761,8762,8763,8764,8765,8766,8767,8768,8769,8770,8771,8772,8773,8774,8775,8776,8777,8778,8779,8780,8781,8782,8783,8784,8785,8786,8787,8788,8789,8790,8791,8792,8793,8794,8795,8796,8797,8798,8799,8800,8801,8802,8803,8804,8805,8806,8807,8808,8809,8810,8811,8812,8813,8814,8815,8816,8817,8818,8819,8820,8821,8822,8823,8824,8825,8826,8827,8828,8829,8830,8831,8832,8833,8834,8835,8836,8837,8838,8839,8840,8841,8842,8843,8844,8845,8846,8847,8848,8849,8850,8851,8852,8853,8854,8855,8856,8857,8858,8859,8860,8861,8862,8863,8864,8865,8866,8867,8868,8869,8870,8871,8872,8873,8874,8875,8876,8877,8878,8879,8880,8881,8882,8883,8884,8885,8886,8887,8888,8889,8890,8891,8892,8893,8894,8895,8896,8897,8898,8899,8900,8901,8902,8903,8904,8905,8906,8907,8908,8909,8910,8911,8912,8913,8914,8915,8916,8917,8918,8919,8920,8921,8922,8923,8924,8925,8926,8927,8928,8929,8930,8931,8932,8933,8934,8935,8936,8937,8938,8939,8940,8941,8942,8943,8944,8945,8946,8947,8948,8949,8950,8951,8952,8953,8954,8955,8956,8957,8958,8959,8960,8961,8962,8963,8964,8965,8966,8967,8968,8969,8970,8971,8972,8973,8974,8975,8976,8977,8978,8979,8980,8981,8982,8983,8984,8985,8986,8987,8988,8989,8990,8991,8992,8993,8994,8995,8996,8997,8998,8999,9000,9001,9002,9003,9004,9005,9006,9007,9008,9009,9010,9011,9012,9013,9014,9015,9016,9017,9018,9019,9020,9021,9022,9023,9024,9025,9026,9027,9028,9029,9030,9031,9032,9033,9034,9035,9036,9037,9038,9039,9040,9041,9042,9043,9044,9045,9046,9047,9048,9049,9050,9051,9052,9053,9054,9055,9056,9057,9058,9059,9060,9061,9062,9063,9064,9065,9066,9067,9068,9069,9070,9071,9072,9073,9074,9075,9076,9077,9078,9079,9080,9081,9082,9083,9084,9085,9086,9087,9088,9089,9090,9091,9092,9093,9094,9095,9096,9097,9098,9099,9100,9101,9102,9103,9104,9105,9106,9107,9108,9109,9110,9111,9112,9113,9114,9115,9116,9117,9118,9119,9120,9121,9122,9123,9124,9125,9126,9127,9128,9129,9130,9131,9132,9133,9134,9135,9136,9137,9138,9139,9140,9141,9142,9143,9144,9145,9146,9147,9148,9149,9150,9151,9152,9153,9154,9155,9156,9157,9158,9159,9160,9161,9162,9163,9164,9165,9166,9167,9168,9169,9170,9171,9172,9173,9174,9175,9176,9177,9178,9179,9180,9181,9182,9183,9184,9185,9186,9187,9188,9189,9190,9191,9192,9193,9194,9195,9196,9197,9198,9199,9200,9201,9202,9203,9204,9205,9206,9207,9208,9209,9210,9211,9212,9213,9214,9215,9216,9217,9218,9219,9220,9221,9222,9223,9224,9225,9226,9227,9228,9229,9230,9231,9232,9233,9234,9235,9236,9237,9238,9239,9240,9241,9242,9243,9244,9245,9246,9247,9248,9249,9250,9251,9252,9253,9254,9255,9256,9257,9258,9259,9260,9261,9262,9263,9264,9265,9266,9267,9268,9269,9270,9271,9272,9273,9274,9275,9276,9277,9278,9279,9280,9281,9282,9283,9284,9285,9286,9287,9288,9289,9290,9291,9292,9293,9294,9295,9296,9297,9298,9299,9300,9301,9302,9303,9304,9305,9306,9307,9308,9309,9310,9311,9312,9313,9314,9315,9316,9317,9318,9319,9320,9321,9322,9323,9324,9325,9326,9327,9328,9329,9330,9331,9332,9333,9334,9335,9336,9337,9338,9339,9340,9341,9342,9343,9344,9345,9346,9347,9348,9349,9350,9351,9352,9353,9354,9355,9356,9357,9358,9359,9360,9361,9362,9363,9364,9365,9366,9367,9368,9369,9370,9371,9372,9373,9374,9375,9376,9377,9378,9379,9380,9381,9382,9383,9384,9385,9386,9387,9388,9389,9390,9391,9392,9393,9394,9395,9396,9397,9398,9399,9400,9401,9402,9403,9404,9405,9406,9407,9408,9409,9410,9411,9412,9413,9414,9415,9416,9417,9418,9419,9420,9421,9422,9423,9424,9425,9426,9427,9428,9429,9430,9431,9432,9433,9434,9435,9436,9437,9438,9439,9440,9441,9442,9443,9444,9445,9446,9447,9448,9449,9450,9451,9452,9453,9454,9455,9456,9457,9458,9459,9460,9461,9462,9463,9464,9465,9466,9467,9468,9469,9470,9471,9472,9473,9474,9475,9476,9477,9478,9479,9480,9481,9482,9483,9484,9485,9486,9487,9488,9489,9490,9491,9492,9493,9494,9495,9496,9497,9498,9499,9500,9501,9502,9503,9504,9505,9506,9507,9508,9509,9510,9511,9512,9513,9514,9515,9516,9517,9518,9519,9520,9521,9522,9523,9524,9525,9526,9527,9528,9529,9530,9531,9532,9533,9534,9535,9536,9537,9538,9539,9540,9541,9542,9543,9544,9545,9546,9547,9548,9549,9550,9551,9552,9553,9554,9555,9556,9557,9558,9559,9560,9561,9562,9563,9564,9565,9566,9567,9568,9569,9570,9571,9572,9573,9574,9575,9576,9577,9578,9579,9580,9581,9582,9583,9584,9585,9586,9587,9588,9589,9590,9591,9592,9593,9594,9595,9596,9597,9598,9599,9600,9601,9602,9603,9604,9605,9606,9607,9608,9609,9610,9611,9612,9613,9614,9615,9616,9617,9618,9619,9620,9621,9622,9623,9624,9625,9626,9627,9628,9629,9630,9631,9632,9633,9634,9635,9636,9637,9638,9639,9640,9641,9642,9643,9644,9645,9646,9647,9648,9649,9650,9651,9652,9653,9654,9655,9656,9657,9658,9659,9660,9661,9662,9663,9664,9665,9666,9667,9668,9669,9670,9671,9672,9673,9674,9675,9676,9677,9678,9679,9680,9681,9682,9683,9684,9685,9686,9687,9688,9689,9690,9691,9692,9693,9694,9695,9696,9697,9698,9699,9700,9701,9702,9703,9704,9705,9706,9707,9708,9709,9710,9711,9712,9713,9714,9715,9716,9717,9718,9719,9720,9721,9722,9723,9724,9725,9726,9727,9728,9729,9730,9731,9732,9733,9734,9735,9736,9737,9738,9739,9740,9741,9742,9743,9744,9745,9746,9747,9748,9749,9750,9751,9752,9753,9754,9755,9756,9757,9758,9759,9760,9761,9762,9763,9764,9765,9766,9767,9768,9769,9770,9771,9772,9773,9774,9775,9776,9777,9778,9779,9780,9781,9782,9783,9784,9785,9786,9787,9788,9789,9790,9791,9792,9793,9794,9795,9796,9797,9798,9799,9800,9801,9802,9803,9804,9805,9806,9807,9808,9809,9810,9811,9812,9813,9814,9815,9816,9817,9818,9819,9820,9821,9822,9823,9824,9825,9826,9827,9828,9829,9830,9831,9832,9833,9834,9835,9836,9837,9838,9839,9840,9841,9842,9843,9844,9845,9846,9847,9848,9849,9850,9851,9852,9853,9854,9855,9856,9857,9858,9859,9860,9861,9862,9863,9864,9865,9866,9867,9868,9869,9870,9871,9872,9873,9874,9875,9876,9877,9878,9879,9880,9881,9882,9883,9884,9885,9886,9887,9888,9889,9890,9891,9892,9893,9894,9895,9896,9897,9898,9899,9900,9901,9902,9903,9904,9905,9906,9907,9908,9909,9910,9911,9912,9913,9914,9915,9916,9917,9918,9919,9920,9921,9922,9923,9924,9925,9926,9927,9928,9929,9930,9931,9932,9933,9934,9935,9936,9937,9938,9939,9940,9941,9942,9943,9944,9945,9946,9947,9948,9949,9950,9951,9952,9953,9954,9955,9956,9957,9958,9959,9960,9961,9962,9963,9964,9965,9966,9967,9968,9969,9970,9971,9972,9973,9974,9975,9976,9977,9978,9979,9980,9981,9982,9983,9984,9985,9986,9987,9988,9989,9990,9991,9992,9993,9994,9995,9996,9997,9998,9999,10000,10001,10002,10003,10004,10005,10006,10007,10008,10009,10010,10011,10012,10013,10014,10015,10016,10017,10018,10019,10020,10021,10022,10023,10024,10025,10026,10027,10028,10029,10030,10031,10032,10033,10034,10035,10036,10037,10038,10039,10040,10041,10042,10043,10044,10045,10046,10047,10048,10049,10050,10051,10052,10053,10054,10055,10056,10057,10058,10059,10060,10061,10062,10063,10064,10065,10066,10067,10068,10069,10070,10071,10072,10073,10074,10075,10076,10077,10078,10079,10080,10081,10082,10083,10084,10085,10086,10087,10088,10089,10090,10091,10092,10093,10094,10095,10096,10097,10098,10099,10100,10101,10102,10103,10104,10105,10106,10107,10108,10109,10110,10111,10112,10113,10114,10115,10116,10117,10118,10119,10120,10121,10122,10123,10124,10125,10126,10127,10128,10129,10130,10131,10132,10133,10134,10135,10136,10137,10138,10139,10140,10141,10142,10143,10144,10145,10146,10147,10148,10149,10150,10151,10152,10153,10154,10155,10156,10157,10158,10159,10160,10161,10162,10163,10164,10165,10166,10167,10168,10169,10170,10171,10172,10173,10174,10175,10176,10177,10178,10179,10180,10181,10182,10183,10184,10185,10186,10187,10188,10189,10190,10191,10192,10193,10194,10195,10196,10197,10198,10199,10200,10201,10202,10203,10204,10205,10206,10207,10208,10209,10210,10211,10212,10213,10214,10215,10216,10217,10218,10219,10220,10221,10222,10223,10224,10225,10226,10227,10228,10229,10230,10231,10232,10233,10234,10235,10236,10237,10238,10239,10240,10241,10242,10243,10244,10245,10246,10247,10248,10249,10250,10251,10252,10253,10254,10255,10256,10257,10258,10259,10260,10261,10262,10263,10264,10265,10266,10267,10268,10269,10270,10271,10272,10273,10274,10275,10276,10277,10278,10279,10280,10281,10282,10283,10284,10285,10286,10287,10288,10289,10290,10291,10292,10293,10294,10295,10296,10297,10298,10299,10300,10301,10302,10303,10304,10305,10306,10307,10308,10309,10310,10311,10312,10313,10314,10315,10316,10317,10318,10319,10320,10321,10322,10323,10324,10325,10326,10327,10328,10329,10330,10331,10332,10333,10334,10335,10336,10337,10338,10339,10340,10341,10342,10343,10344,10345,10346,10347,10348,10349,10350,10351,10352,10353,10354,10355,10356,10357,10358,10359,10360,10361,10362,10363,10364,10365,10366,10367,10368,10369,10370,10371,10372,10373,10374,10375,10376,10377,10378,10379,10380,10381,10382,10383,10384,10385,10386,10387,10388,10389,10390,10391,10392,10393,10394,10395,10396,10397,10398,10399,10400,10401,10402,10403,10404,10405,10406,10407,10408,10409,10410,10411,10412,10413,10414,10415,10416,10417,10418,10419,10420,10421,10422,10423,10424,10425,10426,10427,10428,10429,10430,10431,10432,10433,10434,10435,10436,10437,10438,10439,10440,10441,10442,10443,10444,10445,10446,10447,10448,10449,10450,10451,10452,10453,10454,10455,10456,10457,10458,10459,10460,10461,10462,10463,10464,10465,10466,10467,10468,10469,10470,10471,10472,10473,10474,10475,10476,10477,10478,10479,10480,10481,10482,10483,10484,10485,10486,10487,10488,10489,10490,10491,10492,10493,10494,10495,10496,10497,10498,10499,10500,10501,10502,10503,10504,10505,10506,10507,10508,10509,10510,10511,10512,10513,10514,10515,10516,10517,10518,10519,10520,10521,10522,10523,10524,10525,10526,10527,10528,10529,10530,10531,10532,10533,10534,10535,10536,10537,10538,10539,10540,10541,10542,10543,10544,10545,10546,10547,10548,10549,10550,10551,10552,10553,10554,10555,10556,10557,10558,10559,10560,10561,10562,10563,10564,10565,10566,10567,10568,10569,10570,10571,10572,10573,10574,10575,10576,10577,10578,10579,10580,10581,10582,10583,10584,10585,10586,10587,10588,10589,10590,10591,10592,10593,10594,10595,10596,10597,10598,10599,10600,10601,10602,10603,10604,10605,10606,10607,10608,10609,10610,10611,10612,10613,10614,10615,10616,10617,10618,10619,10620,10621,10622,10623,10624,10625,10626,10627,10628,10629,10630,10631,10632,10633,10634,10635,10636,10637,10638,10639,10640,10641,10642,10643,10644,10645,10646,10647,10648,10649,10650,10651,10652,10653,10654,10655,10656,10657,10658,10659,10660,10661,10662,10663,10664,10665,10666,10667,10668,10669,10670,10671,10672,10673,10674,10675,10676,10677,10678,10679,10680,10681,10682,10683,10684,10685,10686,10687,10688,10689,10690,10691,10692,10693,10694,10695,10696,10697,10698,10699,10700,10701,10702,10703,10704,10705,10706,10707,10708,10709,10710,10711,10712,10713,10714,10715,10716,10717,10718,10719,10720,10721,10722,10723,10724,10725,10726,10727,10728,10729,10730,10731,10732,10733,10734,10735,10736,10737,10738,10739,10740,10741,10742,10743,10744,10745,10746,10747,10748,10749,10750,10751,10752,10753,10754,10755,10756,10757,10758,10759,10760,10761,10762,10763,10764,10765,10766,10767,10768,10769,10770,10771,10772,10773,10774,10775,10776,10777,10778,10779,10780,10781,10782,10783,10784,10785,10786,10787,10788,10789,10790,10791,10792,10793,10794,10795,10796,10797,10798,10799,10800,10801,10802,10803,10804,10805,10806,10807,10808,10809,10810,10811,10812,10813,10814,10815,10816,10817,10818,10819,10820,10821,10822,10823,10824,10825,10826,10827,10828,10829,10830,10831,10832,10833,10834,10835,10836,10837,10838,10839,10840,10841,10842,10843,10844,10845,10846,10847,10848,10849,10850,10851,10852,10853,10854,10855,10856,10857,10858,10859,10860,10861,10862,10863,10864,10865,10866,10867,10868,10869,10870,10871,10872,10873,10874,10875,10876,10877,10878,10879,10880,10881,10882,10883,10884,10885,10886,10887,10888,10889,10890,10891,10892,10893,10894,10895,10896,10897,10898,10899,10900,10901,10902,10903,10904,10905,10906,10907,10908,10909,10910,10911,10912,10913,10914,10915,10916,10917,10918,10919,10920,10921,10922,10923,10924,10925,10926,10927,10928,10929,10930,10931,10932,10933,10934,10935,10936,10937,10938,10939,10940,10941,10942,10943,10944,10945,10946,10947,10948,10949,10950,10951,10952,10953,10954,10955,10956,10957,10958,10959,10960,10961,10962,10963,10964,10965,10966,10967,10968,10969,10970,10971,10972,10973,10974,10975,10976,10977,10978,10979,10980,10981,10982,10983,10984,10985,10986,10987,10988,10989,10990,10991,10992,10993,10994,10995,10996,10997,10998,10999,11000,11001,11002,11003,11004,11005,11006,11007,11008,11009,11010,11011,11012,11013,11014,11015,11016,11017,11018,11019,11020,11021,11022,11023,11024,11025,11026,11027,11028,11029,11030,11031,11032,11033,11034,11035,11036,11037,11038,11039,11040,11041,11042,11043,11044,11045,11046,11047,11048,11049,11050,11051,11052,11053,11054,11055,11056,11057,11058,11059,11060,11061,11062,11063,11064,11065,11066,11067,11068,11069,11070,11071,11072,11073,11074,11075,11076,11077,11078,11079,11080,11081,11082,11083,11084,11085,11086,11087,11088,11089,11090,11091,11092,11093,11094,11095,11096,11097,11098,11099,11100,11101,11102,11103,11104,11105,11106,11107,11108,11109,11110,11111,11112,11113,11114,11115,11116,11117,11118,11119,11120,11121,11122,11123,11124,11125,11126,11127,11128,11129,11130,11131,11132,11133,11134,11135,11136,11137,11138,11139,11140,11141,11142,11143,11144,11145,11146,11147,11148,11149,11150,11151,11152,11153,11154,11155,11156,11157,11158,11159,11160,11161,11162,11163,11164,11165,11166,11167,11168,11169,11170,11171,11172,11173,11174,11175,11176,11177,11178,11179,11180,11181,11182,11183,11184,11185,11186,11187,11188,11189,11190,11191,11192,11193,11194,11195,11196,11197,11198,11199,11200,11201,11202,11203,11204,11205,11206,11207,11208,11209,11210,11211,11212,11213,11214,11215,11216,11217,11218,11219,11220,11221,11222,11223,11224,11225,11226,11227,11228,11229,11230,11231,11232,11233,11234,11235,11236,11237,11238,11239,11240,11241,11242,11243,11244,11245,11246,11247,11248,11249,11250,11251,11252,11253,11254,11255,11256,11257,11258,11259,11260,11261,11262,11263,11264,11265,11266,11267,11268,11269,11270,11271,11272,11273,11274,11275,11276,11277,11278,11279,11280,11281,11282,11283,11284,11285,11286,11287,11288,11289,11290,11291,11292,11293,11294,11295,11296,11297,11298,11299,11300,11301,11302,11303,11304,11305,11306,11307,11308,11309,11310,11311,11312,11313,11314,11315,11316,11317,11318,11319,11320,11321,11322,11323,11324,11325,11326,11327,11328,11329,11330,11331,11332,11333,11334,11335,11336,11337,11338,11339,11340,11341,11342,11343,11344,11345,11346,11347,11348,11349,11350,11351,11352,11353,11354,11355,11356,11357,11358,11359,11360,11361,11362,11363,11364,11365,11366,11367,11368,11369,11370,11371,11372,11373,11374,11375,11376,11377,11378,11379,11380,11381,11382,11383,11384,11385,11386,11387,11388,11389,11390,11391,11392,11393,11394,11395,11396,11397,11398,11399,11400,11401,11402,11403,11404,11405,11406,11407,11408,11409,11410,11411,11412,11413,11414,11415,11416,11417,11418,11419,11420,11421,11422,11423,11424,11425,11426,11427,11428,11429,11430,11431,11432,11433,11434,11435,11436,11437,11438,11439,11440,11441,11442,11443,11444,11445,11446,11447,11448,11449,11450,11451,11452,11453,11454,11455,11456,11457,11458,11459,11460,11461,11462,11463,11464,11465,11466,11467,11468,11469,11470,11471,11472,11473,11474,11475,11476,11477,11478,11479,11480,11481,11482,11483,11484,11485,11486,11487,11488,11489,11490,11491,11492,11493,11494,11495,11496,11497,11498,11499,11500,11501,11502,11503,11504,11505,11506,11507,11508,11509,11510,11511,11512,11513,11514,11515,11516,11517,11518,11519,11520,11521,11522,11523,11524,11525,11526,11527,11528,11529,11530,11531,11532,11533,11534,11535,11536,11537,11538,11539,11540,11541,11542,11543,11544,11545,11546,11547,11548,11549,11550,11551,11552,11553,11554,11555,11556,11557,11558,11559,11560,11561,11562,11563,11564,11565,11566,11567,11568,11569,11570,11571,11572,11573,11574,11575,11576,11577,11578,11579,11580,11581,11582,11583,11584,11585,11586,11587,11588,11589,11590,11591,11592,11593,11594,11595,11596,11597,11598,11599,11600,11601,11602,11603,11604,11605,11606,11607,11608,11609,11610,11611,11612,11613,11614,11615,11616,11617,11618,11619,11620,11621,11622,11623,11624,11625,11626,11627,11628,11629,11630,11631,11632,11633,11634,11635,11636,11637,11638,11639,11640,11641,11642,11643,11644,11645,11646,11647,11648,11649,11650,11651,11652,11653,11654,11655,11656,11657,11658,11659,11660,11661,11662,11663,11664,11665,11666,11667,11668,11669,11670,11671,11672,11673,11674,11675,11676,11677,11678,11679,11680,11681,11682,11683,11684,11685,11686,11687,11688,11689,11690,11691,11692,11693,11694,11695,11696,11697,11698,11699,11700,11701,11702,11703,11704,11705,11706,11707,11708,11709,11710,11711,11712,11713,11714,11715,11716,11717,11718,11719,11720,11721,11722,11723,11724,11725,11726,11727,11728,11729,11730,11731,11732,11733,11734,11735,11736,11737,11738,11739,11740,11741,11742,11743,11744,11745,11746,11747,11748,11749,11750,11751,11752,11753,11754,11755,11756,11757,11758,11759,11760,11761,11762,11763,11764,11765,11766,11767,11768,11769,11770,11771,11772,11773,11774,11775,11776,11777,11778,11779,11780,11781,11782,11783,11784,11785,11786,11787,11788,11789,11790,11791,11792,11793,11794,11795,11796,11797,11798,11799,11800,11801,11802,11803,11804,11805,11806,11807,11808,11809,11810,11811,11812,11813,11814,11815,11816,11817,11818,11819,11820,11821,11822,11823,11824,11825,11826,11827,11828,11829,11830,11831,11832,11833,11834,11835,11836,11837,11838,11839,11840,11841,11842,11843,11844,11845,11846,11847,11848,11849,11850,11851,11852,11853,11854,11855,11856,11857,11858,11859,11860,11861,11862,11863,11864,11865,11866,11867,11868,11869,11870,11871,11872,11873,11874,11875,11876,11877,11878,11879,11880,11881,11882,11883,11884,11885,11886,11887,11888,11889,11890,11891,11892,11893,11894,11895,11896,11897,11898,11899,11900,11901,11902,11903,11904,11905,11906,11907,11908,11909,11910,11911,11912,11913,11914,11915,11916,11917,11918,11919,11920,11921,11922,11923,11924,11925,11926,11927,11928,11929,11930,11931,11932,11933,11934,11935,11936,11937,11938,11939,11940,11941,11942,11943,11944,11945,11946,11947,11948,11949,11950,11951,11952,11953,11954,11955,11956,11957,11958,11959,11960,11961,11962,11963,11964,11965,11966,11967,11968,11969,11970,11971,11972,11973,11974,11975,11976,11977,11978,11979,11980,11981,11982,11983,11984,11985,11986,11987,11988,11989,11990,11991,11992,11993,11994,11995,11996,11997,11998,11999,12000,12001,12002,12003,12004,12005,12006,12007,12008,12009,12010,12011,12012,12013,12014,12015,12016,12017,12018,12019,12020,12021,12022,12023,12024,12025,12026,12027,12028,12029,12030,12031,12032,12033,12034,12035,12036,12037,12038,12039,12040,12041,12042,12043,12044,12045,12046,12047,12048,12049,12050,12051,12052,12053,12054,12055,12056,12057,12058,12059,12060,12061,12062,12063,12064,12065,12066,12067,12068,12069,12070,12071,12072,12073,12074,12075,12076,12077,12078,12079,12080,12081,12082,12083,12084,12085,12086,12087,12088,12089,12090,12091,12092,12093,12094,12095,12096,12097,12098,12099,12100,12101,12102,12103,12104,12105,12106,12107,12108,12109,12110,12111,12112,12113,12114,12115,12116,12117,12118,12119,12120,12121,12122,12123,12124,12125,12126,12127,12128,12129,12130,12131,12132,12133,12134,12135,12136,12137,12138,12139,12140,12141,12142,12143,12144,12145,12146,12147,12148,12149,12150,12151,12152,12153,12154,12155,12156,12157,12158,12159,12160,12161,12162,12163,12164,12165,12166,12167,12168,12169,12170,12171,12172,12173,12174,12175,12176,12177,12178,12179,12180,12181,12182,12183,12184,12185,12186,12187,12188,12189,12190,12191,12192,12193,12194,12195,12196,12197,12198,12199,12200,12201,12202,12203,12204,12205,12206,12207,12208,12209,12210,12211,12212,12213,12214,12215,12216,12217,12218,12219,12220,12221,12222,12223,12224,12225,12226,12227,12228,12229,12230,12231,12232,12233,12234,12235,12236,12237,12238,12239,12240,12241,12242,12243,12244,12245,12246,12247,12248,12249,12250,12251,12252,12253,12254,12255,12256,12257,12258,12259,12260,12261,12262,12263,12264,12265,12266,12267,12268,12269,12270,12271,12272,12273,12274,12275,12276,12277,12278,12279,12280,12281,12282,12283,12284,12285,12286,12287,12288,12289,12290,12291,12292,12293,12294,12295,12296,12297,12298,12299,12300,12301,12302,12303,12304,12305,12306,12307,12308,12309,12310,12311,12312,12313,12314,12315,12316,12317,12318,12319,12320,12321,12322,12323,12324,12325,12326,12327,12328,12329,12330,12331,12332,12333,12334,12335,12336,12337,12338,12339,12340,12341,12342,12343,12344,12345,12346,12347,12348,12349,12350,12351,12352,12353,12354,12355,12356,12357,12358,12359,12360,12361,12362,12363,12364,12365,12366,12367,12368,12369,12370,12371,12372,12373,12374,12375,12376,12377,12378,12379,12380,12381,12382,12383,12384,12385,12386,12387,12388,12389,12390,12391,12392,12393,12394,12395,12396,12397,12398,12399,12400,12401,12402,12403,12404,12405,12406,12407,12408,12409,12410,12411,12412,12413,12414,12415,12416,12417,12418,12419,12420,12421,12422,12423,12424,12425,12426,12427,12428,12429,12430,12431,12432,12433,12434,12435,12436,12437,12438,12439,12440,12441,12442,12443,12444,12445,12446,12447,12448,12449,12450,12451,12452,12453,12454,12455,12456,12457,12458,12459,12460,12461,12462,12463,12464,12465,12466,12467,12468,12469,12470,12471,12472,12473,12474,12475,12476,12477,12478,12479,12480,12481,12482,12483,12484,12485,12486,12487,12488,12489,12490,12491,12492,12493,12494,12495,12496,12497,12498,12499,12500,12501,12502,12503,12504,12505,12506,12507,12508,12509,12510,12511,12512,12513,12514,12515,12516,12517,12518,12519,12520,12521,12522,12523,12524,12525,12526,12527,12528,12529,12530,12531,12532,12533,12534,12535,12536,12537,12538,12539,12540,12541,12542,12543,12544,12545,12546,12547,12548,12549,12550,12551,12552,12553,12554,12555,12556,12557,12558,12559,12560,12561,12562,12563,12564,12565,12566,12567,12568,12569,12570,12571,12572,12573,12574,12575,12576,12577,12578,12579,12580,12581,12582,12583,12584,12585,12586,12587,12588,12589,12590,12591,12592,12593,12594,12595,12596,12597,12598,12599,12600,12601,12602,12603,12604,12605,12606,12607,12608,12609,12610,12611,12612,12613,12614,12615,12616,12617,12618,12619,12620,12621,12622,12623,12624,12625,12626,12627,12628,12629,12630,12631,12632,12633,12634,12635,12636,12637,12638,12639,12640,12641,12642,12643,12644,12645,12646,12647,12648,12649,12650,12651,12652,12653,12654,12655,12656,12657,12658,12659,12660,12661,12662,12663,12664,12665,12666,12667,12668,12669,12670,12671,12672,12673,12674,12675,12676,12677,12678,12679,12680,12681,12682,12683,12684,12685,12686,12687,12688,12689,12690,12691,12692,12693,12694,12695,12696,12697,12698,12699,12700,12701,12702,12703,12704,12705,12706,12707,12708,12709,12710,12711,12712,12713,12714,12715,12716,12717,12718,12719,12720,12721,12722,12723,12724,12725,12726,12727,12728,12729,12730,12731,12732,12733,12734,12735,12736,12737,12738,12739,12740,12741,12742,12743,12744,12745,12746,12747,12748,12749,12750,12751,12752,12753,12754,12755,12756,12757,12758,12759,12760,12761,12762,12763,12764,12765,12766,12767,12768,12769,12770,12771,12772,12773,12774,12775,12776,12777,12778,12779,12780,12781,12782,12783,12784,12785,12786,12787,12788,12789,12790,12791,12792,12793,12794,12795,12796,12797,12798,12799,12800,12801,12802,12803,12804,12805,12806,12807,12808,12809,12810,12811,12812,12813,12814,12815,12816,12817,12818,12819,12820,12821,12822,12823,12824,12825,12826,12827,12828,12829,12830,12831,12832,12833,12834,12835,12836,12837,12838,12839,12840,12841,12842,12843,12844,12845,12846,12847,12848,12849,12850,12851,12852,12853,12854,12855,12856,12857,12858,12859,12860,12861,12862,12863,12864,12865,12866,12867,12868,12869,12870,12871,12872,12873,12874,12875,12876,12877,12878,12879,12880,12881,12882,12883,12884,12885,12886,12887,12888,12889,12890,12891,12892,12893,12894,12895,12896,12897,12898,12899,12900,12901,12902,12903,12904,12905,12906,12907,12908,12909,12910,12911,12912,12913,12914,12915,12916,12917,12918,12919,12920,12921,12922,12923,12924,12925,12926,12927,12928,12929,12930,12931,12932,12933,12934,12935,12936,12937,12938,12939,12940,12941,12942,12943,12944,12945,12946,12947,12948,12949,12950,12951,12952,12953,12954,12955,12956,12957,12958,12959,12960,12961,12962,12963,12964,12965,12966,12967,12968,12969,12970,12971,12972,12973,12974,12975,12976,12977,12978,12979,12980,12981,12982,12983,12984,12985,12986,12987,12988,12989,12990,12991,12992,12993,12994,12995,12996,12997,12998,12999,13000,13001,13002,13003,13004,13005,13006,13007,13008,13009,13010,13011,13012,13013,13014,13015,13016,13017,13018,13019,13020,13021,13022,13023,13024,13025,13026,13027,13028,13029,13030,13031,13032,13033,13034,13035,13036,13037,13038,13039,13040,13041,13042,13043,13044,13045,13046,13047,13048,13049,13050,13051,13052,13053,13054,13055,13056,13057,13058,13059,13060,13061,13062,13063,13064,13065,13066,13067,13068,13069,13070,13071,13072,13073,13074,13075,13076,13077,13078,13079,13080,13081,13082,13083,13084,13085,13086,13087,13088,13089,13090,13091,13092,13093,13094,13095,13096,13097,13098,13099,13100,13101,13102,13103,13104,13105,13106,13107,13108,13109,13110,13111,13112,13113,13114,13115,13116,13117,13118,13119,13120,13121,13122,13123,13124,13125,13126,13127,13128,13129,13130,13131,13132,13133,13134,13135,13136,13137,13138,13139,13140,13141,13142,13143,13144,13145,13146,13147,13148,13149,13150,13151,13152,13153,13154,13155,13156,13157,13158,13159,13160,13161,13162,13163,13164,13165,13166,13167,13168,13169,13170,13171,13172,13173,13174,13175,13176,13177,13178,13179,13180,13181,13182,13183,13184,13185,13186,13187,13188,13189,13190,13191,13192,13193,13194,13195,13196,13197,13198,13199,13200,13201,13202,13203,13204,13205,13206,13207,13208,13209,13210,13211,13212,13213,13214,13215,13216,13217,13218,13219,13220,13221,13222,13223,13224,13225,13226,13227,13228,13229,13230,13231,13232,13233,13234,13235,13236,13237,13238,13239,13240,13241,13242,13243,13244,13245,13246,13247,13248,13249,13250,13251,13252,13253,13254,13255,13256,13257,13258,13259,13260,13261,13262,13263,13264,13265,13266,13267,13268,13269,13270,13271,13272,13273,13274,13275,13276,13277,13278,13279,13280,13281,13282,13283,13284,13285,13286,13287,13288,13289,13290,13291,13292,13293,13294,13295,13296,13297,13298,13299,13300,13301,13302,13303,13304,13305,13306,13307,13308,13309,13310,13311,13312,13313,13314,13315,13316,13317,13318,13319,13320,13321,13322,13323,13324,13325,13326,13327,13328,13329,13330,13331,13332,13333,13334,13335,13336,13337,13338,13339,13340,13341,13342,13343,13344,13345,13346,13347,13348,13349,13350,13351,13352,13353,13354,13355,13356,13357,13358,13359,13360,13361,13362,13363,13364,13365,13366,13367,13368,13369,13370,13371,13372,13373,13374,13375,13376,13377,13378,13379,13380,13381,13382,13383,13384,13385,13386,13387,13388,13389,13390,13391,13392,13393,13394,13395,13396,13397,13398,13399,13400,13401,13402,13403,13404,13405,13406,13407,13408,13409,13410,13411,13412,13413,13414,13415,13416,13417,13418,13419,13420,13421,13422,13423,13424,13425,13426,13427,13428,13429,13430,13431,13432,13433,13434,13435,13436,13437,13438,13439,13440,13441,13442,13443,13444,13445,13446,13447,13448,13449,13450,13451,13452,13453,13454,13455,13456,13457,13458,13459,13460,13461,13462,13463,13464,13465,13466,13467,13468,13469,13470,13471,13472,13473,13474,13475,13476,13477,13478,13479,13480,13481,13482,13483,13484,13485,13486,13487,13488,13489,13490,13491,13492,13493,13494,13495,13496,13497,13498,13499,13500,13501,13502,13503,13504,13505,13506,13507,13508,13509,13510,13511,13512,13513,13514,13515,13516,13517,13518,13519,13520,13521,13522,13523,13524,13525,13526,13527,13528,13529,13530,13531,13532,13533,13534,13535,13536,13537,13538,13539,13540,13541,13542,13543,13544,13545,13546,13547,13548,13549,13550,13551,13552,13553,13554,13555,13556,13557,13558,13559,13560,13561,13562,13563,13564,13565,13566,13567,13568,13569,13570,13571,13572,13573,13574,13575,13576,13577,13578,13579,13580,13581,13582,13583,13584,13585,13586,13587,13588,13589,13590,13591,13592,13593,13594,13595,13596,13597,13598,13599,13600,13601,13602,13603,13604,13605,13606,13607,13608,13609,13610,13611,13612,13613,13614,13615,13616,13617,13618,13619,13620,13621,13622,13623,13624,13625,13626,13627,13628,13629,13630,13631,13632,13633,13634,13635,13636,13637,13638,13639,13640,13641,13642,13643,13644,13645,13646,13647,13648,13649,13650,13651,13652,13653,13654,13655,13656,13657,13658,13659,13660,13661,13662,13663,13664,13665,13666,13667,13668,13669,13670,13671,13672,13673,13674,13675,13676,13677,13678,13679,13680,13681,13682,13683,13684,13685,13686,13687,13688,13689,13690,13691,13692,13693,13694,13695,13696,13697,13698,13699,13700,13701,13702,13703,13704,13705,13706,13707,13708,13709,13710,13711,13712,13713,13714,13715,13716,13717,13718,13719,13720,13721,13722,13723,13724,13725,13726,13727,13728,13729,13730,13731,13732,13733,13734,13735,13736,13737,13738,13739,13740,13741,13742,13743,13744,13745,13746,13747,13748,13749,13750,13751,13752,13753,13754,13755,13756,13757,13758,13759,13760,13761,13762,13763,13764,13765,13766,13767,13768,13769,13770,13771,13772,13773,13774,13775,13776,13777,13778,13779,13780,13781,13782,13783,13784,13785,13786,13787,13788,13789,13790,13791,13792,13793,13794,13795,13796,13797,13798,13799,13800,13801,13802,13803,13804,13805,13806,13807,13808,13809,13810,13811,13812,13813,13814,13815,13816,13817,13818,13819,13820,13821,13822,13823,13824,13825,13826,13827,13828,13829,13830,13831,13832,13833,13834,13835,13836,13837,13838,13839,13840,13841,13842,13843,13844,13845,13846,13847,13848,13849,13850,13851,13852,13853,13854,13855,13856,13857,13858,13859,13860,13861,13862,13863,13864,13865,13866,13867,13868,13869,13870,13871,13872,13873,13874,13875,13876,13877,13878,13879,13880,13881,13882,13883,13884,13885,13886,13887,13888,13889,13890,13891,13892,13893,13894,13895,13896,13897,13898,13899,13900,13901,13902,13903,13904,13905,13906,13907,13908,13909,13910,13911,13912,13913,13914,13915,13916,13917,13918,13919,13920,13921,13922,13923,13924,13925,13926,13927,13928,13929,13930,13931,13932,13933,13934,13935,13936,13937,13938,13939,13940,13941,13942,13943,13944,13945,13946,13947,13948,13949,13950,13951,13952,13953,13954,13955,13956,13957,13958,13959,13960,13961,13962,13963,13964,13965,13966,13967,13968,13969,13970,13971,13972,13973,13974,13975,13976,13977,13978,13979,13980,13981,13982,13983,13984,13985,13986,13987,13988,13989,13990,13991,13992,13993,13994,13995,13996,13997,13998,13999,14000,14001,14002,14003,14004,14005,14006,14007,14008,14009,14010,14011,14012,14013,14014,14015,14016,14017,14018,14019,14020,14021,14022,14023,14024,14025,14026,14027,14028,14029,14030,14031,14032,14033,14034,14035,14036,14037,14038,14039,14040,14041,14042,14043,14044,14045,14046,14047,14048,14049,14050,14051,14052,14053,14054,14055,14056,14057,14058,14059,14060,14061,14062,14063,14064,14065,14066,14067,14068,14069,14070,14071,14072,14073,14074,14075,14076,14077,14078,14079,14080,14081,14082,14083,14084,14085,14086,14087,14088,14089,14090,14091,14092,14093,14094,14095,14096,14097,14098,14099,14100,14101,14102,14103,14104,14105,14106,14107,14108,14109,14110,14111,14112,14113,14114,14115,14116,14117,14118,14119,14120,14121,14122,14123,14124,14125,14126,14127,14128,14129,14130,14131,14132,14133,14134,14135,14136,14137,14138,14139,14140,14141,14142,14143,14144,14145,14146,14147,14148,14149,14150,14151,14152,14153,14154,14155,14156,14157,14158,14159,14160,14161,14162,14163,14164,14165,14166,14167,14168,14169,14170,14171,14172,14173,14174,14175,14176,14177,14178,14179,14180,14181,14182,14183,14184,14185,14186,14187,14188,14189,14190,14191,14192,14193,14194,14195,14196,14197,14198,14199,14200,14201,14202,14203,14204,14205,14206,14207,14208,14209,14210,14211,14212,14213,14214,14215,14216,14217,14218,14219,14220,14221,14222,14223,14224,14225,14226,14227,14228,14229,14230,14231,14232,14233,14234,14235,14236,14237,14238,14239,14240,14241,14242,14243,14244,14245,14246,14247,14248,14249,14250,14251,14252,14253,14254,14255,14256,14257,14258,14259,14260,14261,14262,14263,14264,14265,14266,14267,14268,14269,14270,14271,14272,14273,14274,14275,14276,14277,14278,14279,14280,14281,14282,14283,14284,14285,14286,14287,14288,14289,14290,14291,14292,14293,14294,14295,14296,14297,14298,14299,14300,14301,14302,14303,14304,14305,14306,14307,14308,14309,14310,14311,14312,14313,14314,14315,14316,14317,14318,14319,14320,14321,14322,14323,14324,14325,14326,14327,14328,14329,14330,14331,14332,14333,14334,14335,14336,14337,14338,14339,14340,14341,14342,14343,14344,14345,14346,14347,14348,14349,14350,14351,14352,14353,14354,14355,14356,14357,14358,14359,14360,14361,14362,14363,14364,14365,14366,14367,14368,14369,14370,14371,14372,14373,14374,14375,14376,14377,14378,14379,14380,14381,14382,14383,14384,14385,14386,14387,14388,14389,14390,14391,14392,14393,14394,14395,14396,14397,14398,14399,14400,14401,14402,14403,14404,14405,14406,14407,14408,14409,14410,14411,14412,14413,14414,14415,14416,14417,14418,14419,14420,14421,14422,14423,14424,14425,14426,14427,14428,14429,14430,14431,14432,14433,14434,14435,14436,14437,14438,14439,14440,14441,14442,14443,14444,14445,14446,14447,14448,14449,14450,14451,14452,14453,14454,14455,14456,14457,14458,14459,14460,14461,14462,14463,14464,14465,14466,14467,14468,14469,14470,14471,14472,14473,14474,14475,14476,14477,14478,14479,14480,14481,14482,14483,14484,14485,14486,14487,14488,14489,14490,14491,14492,14493,14494,14495,14496,14497,14498,14499,14500,14501,14502,14503,14504,14505,14506,14507,14508,14509,14510,14511,14512,14513,14514,14515,14516,14517,14518,14519,14520,14521,14522,14523,14524,14525,14526,14527,14528,14529,14530,14531,14532,14533,14534,14535,14536,14537,14538,14539,14540,14541,14542,14543,14544,14545,14546,14547,14548,14549,14550,14551,14552,14553,14554,14555,14556,14557,14558,14559,14560,14561,14562,14563,14564,14565,14566,14567,14568,14569,14570,14571,14572,14573,14574,14575,14576,14577,14578,14579,14580,14581,14582,14583,14584,14585,14586,14587,14588,14589,14590,14591,14592,14593,14594,14595,14596,14597,14598,14599,14600,14601,14602,14603,14604,14605,14606,14607,14608,14609,14610,14611,14612,14613,14614,14615,14616,14617,14618,14619,14620,14621,14622,14623,14624,14625,14626,14627,14628,14629,14630,14631,14632,14633,14634,14635,14636,14637,14638,14639,14640,14641,14642,14643,14644,14645,14646,14647,14648,14649,14650,14651,14652,14653,14654,14655,14656,14657,14658,14659,14660,14661,14662,14663,14664,14665,14666,14667,14668,14669,14670,14671,14672,14673,14674,14675,14676,14677,14678,14679,14680,14681,14682,14683,14684,14685,14686,14687,14688,14689,14690,14691,14692,14693,14694,14695,14696,14697,14698,14699,14700,14701,14702,14703,14704,14705,14706,14707,14708,14709,14710,14711,14712,14713,14714,14715,14716,14717,14718,14719,14720,14721,14722,14723,14724,14725,14726,14727,14728,14729,14730,14731,14732,14733,14734,14735,14736,14737,14738,14739,14740,14741,14742,14743,14744,14745,14746,14747,14748,14749,14750,14751,14752,14753,14754,14755,14756,14757,14758,14759,14760,14761,14762,14763,14764,14765,14766,14767,14768,14769,14770,14771,14772,14773,14774,14775,14776,14777,14778,14779,14780,14781,14782,14783,14784,14785,14786,14787,14788,14789,14790,14791,14792,14793,14794,14795,14796,14797,14798,14799,14800,14801,14802,14803,14804,14805,14806,14807,14808,14809,14810,14811,14812,14813,14814,14815,14816,14817,14818,14819,14820,14821,14822,14823,14824,14825,14826,14827,14828,14829,14830,14831,14832,14833,14834,14835,14836,14837,14838,14839,14840,14841,14842,14843,14844,14845,14846,14847,14848,14849,14850,14851,14852,14853,14854,14855,14856,14857,14858,14859,14860,14861,14862,14863,14864,14865,14866,14867,14868,14869,14870,14871,14872,14873,14874,14875,14876,14877,14878,14879,14880,14881,14882,14883,14884,14885,14886,14887,14888,14889,14890,14891,14892,14893,14894,14895,14896,14897,14898,14899,14900,14901,14902,14903,14904,14905,14906,14907,14908,14909,14910,14911,14912,14913,14914,14915,14916,14917,14918,14919,14920,14921,14922,14923,14924,14925,14926,14927,14928,14929,14930,14931,14932,14933,14934,14935,14936,14937,14938,14939,14940,14941,14942,14943,14944,14945,14946,14947,14948,14949,14950,14951,14952,14953,14954,14955,14956,14957,14958,14959,14960,14961,14962,14963,14964,14965,14966,14967,14968,14969,14970,14971,14972,14973,14974,14975,14976,14977,14978,14979,14980,14981,14982,14983,14984,14985,14986,14987,14988,14989,14990,14991,14992,14993,14994,14995,14996,14997,14998,14999,15000,15001,15002,15003,15004,15005,15006,15007,15008,15009,15010,15011,15012,15013,15014,15015,15016,15017,15018,15019,15020,15021,15022,15023,15024,15025,15026,15027,15028,15029,15030,15031,15032,15033,15034,15035,15036,15037,15038,15039,15040,15041,15042,15043,15044,15045,15046,15047,15048,15049,15050,15051,15052,15053,15054,15055,15056,15057,15058,15059,15060,15061,15062,15063,15064,15065,15066,15067,15068,15069,15070,15071,15072,15073,15074,15075,15076,15077,15078,15079,15080,15081,15082,15083,15084,15085,15086,15087,15088,15089,15090,15091,15092,15093,15094,15095,15096,15097,15098,15099,15100,15101,15102,15103,15104,15105,15106,15107,15108,15109,15110,15111,15112,15113,15114,15115,15116,15117,15118,15119,15120,15121,15122,15123,15124,15125,15126,15127,15128,15129,15130,15131,15132,15133,15134,15135,15136,15137,15138,15139,15140,15141,15142,15143,15144,15145,15146,15147,15148,15149,15150,15151,15152,15153,15154,15155,15156,15157,15158,15159,15160,15161,15162,15163,15164,15165,15166,15167,15168,15169,15170,15171,15172,15173,15174,15175,15176,15177,15178,15179,15180,15181,15182,15183,15184,15185,15186,15187,15188,15189,15190,15191,15192,15193,15194,15195,15196,15197,15198,15199,15200,15201,15202,15203,15204,15205,15206,15207,15208,15209,15210,15211,15212,15213,15214,15215,15216,15217,15218,15219,15220,15221,15222,15223,15224,15225,15226,15227,15228,15229,15230,15231,15232,15233,15234,15235,15236,15237,15238,15239,15240,15241,15242,15243,15244,15245,15246,15247,15248,15249,15250,15251,15252,15253,15254,15255,15256,15257,15258,15259,15260,15261,15262,15263,15264,15265,15266,15267,15268,15269,15270,15271,15272,15273,15274,15275,15276,15277,15278,15279,15280,15281,15282,15283,15284,15285,15286,15287,15288,15289,15290,15291,15292,15293,15294,15295,15296,15297,15298,15299,15300,15301,15302,15303,15304,15305,15306,15307,15308,15309,15310,15311,15312,15313,15314,15315,15316,15317,15318,15319,15320,15321,15322,15323,15324,15325,15326,15327,15328,15329,15330,15331,15332,15333,15334,15335,15336,15337,15338,15339,15340,15341,15342,15343,15344,15345,15346,15347,15348,15349,15350,15351,15352,15353,15354,15355,15356,15357,15358,15359,15360,15361,15362,15363,15364,15365,15366,15367,15368,15369,15370,15371,15372,15373,15374,15375,15376,15377,15378,15379,15380,15381,15382,15383,15384,15385,15386,15387,15388,15389,15390,15391,15392,15393,15394,15395,15396,15397,15398,15399,15400,15401,15402,15403,15404,15405,15406,15407,15408,15409,15410,15411,15412,15413,15414,15415,15416,15417,15418,15419,15420,15421,15422,15423,15424,15425,15426,15427,15428,15429,15430,15431,15432,15433,15434,15435,15436,15437,15438,15439,15440,15441,15442,15443,15444,15445,15446,15447,15448,15449,15450,15451,15452,15453,15454,15455,15456,15457,15458,15459,15460,15461,15462,15463,15464,15465,15466,15467,15468,15469,15470,15471,15472,15473,15474,15475,15476,15477,15478,15479,15480,15481,15482,15483,15484,15485,15486,15487,15488,15489,15490,15491,15492,15493,15494,15495,15496,15497,15498,15499,15500,15501,15502,15503,15504,15505,15506,15507,15508,15509,15510,15511,15512,15513,15514,15515,15516,15517,15518,15519,15520,15521,15522,15523,15524,15525,15526,15527,15528,15529,15530,15531,15532,15533,15534,15535,15536,15537,15538,15539,15540,15541,15542,15543,15544,15545,15546,15547,15548,15549,15550,15551,15552,15553,15554,15555,15556,15557,15558,15559,15560,15561,15562,15563,15564,15565,15566,15567,15568,15569,15570,15571,15572,15573,15574,15575,15576,15577,15578,15579,15580,15581,15582,15583,15584,15585,15586,15587,15588,15589,15590,15591,15592,15593,15594,15595,15596,15597,15598,15599,15600,15601,15602,15603,15604,15605,15606,15607,15608,15609,15610,15611,15612,15613,15614,15615,15616,15617,15618,15619,15620,15621,15622,15623,15624,15625,15626,15627,15628,15629,15630,15631,15632,15633,15634,15635,15636,15637,15638,15639,15640,15641,15642,15643,15644,15645,15646,15647,15648,15649,15650,15651,15652,15653,15654,15655,15656,15657,15658,15659,15660,15661,15662,15663,15664,15665,15666,15667,15668,15669,15670,15671,15672,15673,15674,15675,15676,15677,15678,15679,15680,15681,15682,15683,15684,15685,15686,15687,15688,15689,15690,15691,15692,15693,15694,15695,15696,15697,15698,15699,15700,15701,15702,15703,15704,15705,15706,15707,15708,15709,15710,15711,15712,15713,15714,15715,15716,15717,15718,15719,15720,15721,15722,15723,15724,15725,15726,15727,15728,15729,15730,15731,15732,15733,15734,15735,15736,15737,15738,15739,15740,15741,15742,15743,15744,15745,15746,15747,15748,15749,15750,15751,15752,15753,15754,15755,15756,15757,15758,15759,15760,15761,15762,15763,15764,15765,15766,15767,15768,15769,15770,15771,15772,15773,15774,15775,15776,15777,15778,15779,15780,15781,15782,15783,15784,15785,15786,15787,15788,15789,15790,15791,15792,15793,15794,15795,15796,15797,15798,15799,15800,15801,15802,15803,15804,15805,15806,15807,15808,15809,15810,15811,15812,15813,15814,15815,15816,15817,15818,15819,15820,15821,15822,15823,15824,15825,15826,15827,15828,15829,15830,15831,15832,15833,15834,15835,15836,15837,15838,15839,15840,15841,15842,15843,15844,15845,15846,15847,15848,15849,15850,15851,15852,15853,15854,15855,15856,15857,15858,15859,15860,15861,15862,15863,15864,15865,15866,15867,15868,15869,15870,15871,15872,15873,15874,15875,15876,15877,15878,15879,15880,15881,15882,15883,15884,15885,15886,15887,15888,15889,15890,15891,15892,15893,15894,15895,15896,15897,15898,15899,15900,15901,15902,15903,15904,15905,15906,15907,15908,15909,15910,15911,15912,15913,15914,15915,15916,15917,15918,15919,15920,15921,15922,15923,15924,15925,15926,15927,15928,15929,15930,15931,15932,15933,15934,15935,15936,15937,15938,15939,15940,15941,15942,15943,15944,15945,15946,15947,15948,15949,15950,15951,15952,15953,15954,15955,15956,15957,15958,15959,15960,15961,15962,15963,15964,15965,15966,15967,15968,15969,15970,15971,15972,15973,15974,15975,15976,15977,15978,15979,15980,15981,15982,15983,15984,15985,15986,15987,15988,15989,15990,15991,15992,15993,15994,15995,15996,15997,15998,15999,16000,16001,16002,16003,16004,16005,16006,16007,16008,16009,16010,16011,16012,16013,16014,16015,16016,16017,16018,16019,16020,16021,16022,16023,16024,16025,16026,16027,16028,16029,16030,16031,16032,16033,16034,16035,16036,16037,16038,16039,16040,16041,16042,16043,16044,16045,16046,16047,16048,16049,16050,16051,16052,16053,16054,16055,16056,16057,16058,16059,16060,16061,16062,16063,16064,16065,16066,16067,16068,16069,16070,16071,16072,16073,16074,16075,16076,16077,16078,16079,16080,16081,16082,16083,16084,16085,16086,16087,16088,16089,16090,16091,16092,16093,16094,16095,16096,16097,16098,16099,16100,16101,16102,16103,16104,16105,16106,16107,16108,16109,16110,16111,16112,16113,16114,16115,16116,16117,16118,16119,16120,16121,16122,16123,16124,16125,16126,16127,16128,16129,16130,16131,16132,16133,16134,16135,16136,16137,16138,16139,16140,16141,16142,16143,16144,16145,16146,16147,16148,16149,16150,16151,16152,16153,16154,16155,16156,16157,16158,16159,16160,16161,16162,16163,16164,16165,16166,16167,16168,16169,16170,16171,16172,16173,16174,16175,16176,16177,16178,16179,16180,16181,16182,16183,16184,16185,16186,16187,16188,16189,16190,16191,16192,16193,16194,16195,16196,16197,16198,16199,16200,16201,16202,16203,16204,16205,16206,16207,16208,16209,16210,16211,16212,16213,16214,16215,16216,16217,16218,16219,16220,16221,16222,16223,16224,16225,16226,16227,16228,16229,16230,16231,16232,16233,16234,16235,16236,16237,16238,16239,16240,16241,16242,16243,16244,16245,16246,16247,16248,16249,16250,16251,16252,16253,16254,16255,16256,16257,16258,16259,16260,16261,16262,16263,16264,16265,16266,16267,16268,16269,16270,16271,16272,16273,16274,16275,16276,16277,16278,16279,16280,16281,16282,16283,16284,16285,16286,16287,16288,16289,16290,16291,16292,16293,16294,16295,16296,16297,16298,16299,16300,16301,16302,16303,16304,16305,16306,16307,16308,16309,16310,16311,16312,16313,16314,16315,16316,16317,16318,16319,16320,16321,16322,16323,16324,16325,16326,16327,16328,16329,16330,16331,16332,16333,16334,16335,16336,16337,16338,16339,16340,16341,16342,16343,16344,16345,16346,16347,16348,16349,16350,16351,16352,16353,16354,16355,16356,16357,16358,16359,16360,16361,16362,16363,16364,16365,16366,16367,16368,16369,16370,16371,16372,16373,16374,16375,16376,16377,16378,16379,16380,16381,16382,16383,16384,16385,16386,16387,16388,16389,16390,16391,16392,16393,16394,16395,16396,16397,16398,16399,16400,16401,16402,16403,16404,16405,16406,16407,16408,16409,16410,16411,16412,16413,16414,16415,16416,16417,16418,16419,16420,16421,16422,16423,16424,16425,16426,16427,16428,16429,16430,16431,16432,16433,16434,16435,16436,16437,16438,16439,16440,16441,16442,16443,16444,16445,16446,16447,16448,16449,16450,16451,16452,16453,16454,16455,16456,16457,16458,16459,16460,16461,16462,16463,16464,16465,16466,16467,16468,16469,16470,16471,16472,16473,16474,16475,16476,16477,16478,16479,16480,16481,16482,16483,16484,16485,16486,16487,16488,16489,16490,16491,16492,16493,16494,16495,16496,16497,16498,16499,16500,16501,16502,16503,16504,16505,16506,16507,16508,16509,16510,16511,16512,16513,16514,16515,16516,16517,16518,16519,16520,16521,16522,16523,16524,16525,16526,16527,16528,16529,16530,16531,16532,16533,16534,16535,16536,16537,16538,16539,16540,16541,16542,16543,16544,16545,16546,16547,16548,16549,16550,16551,16552,16553,16554,16555,16556,16557,16558,16559,16560,16561,16562,16563,16564,16565,16566,16567,16568,16569,16570,16571,16572,16573,16574,16575,16576,16577,16578,16579,16580,16581,16582,16583,16584,16585,16586,16587,16588,16589,16590,16591,16592,16593,16594,16595,16596,16597,16598,16599,16600,16601,16602,16603,16604,16605,16606,16607,16608,16609,16610,16611,16612,16613,16614,16615,16616,16617,16618,16619,16620,16621,16622,16623,16624,16625,16626,16627,16628,16629,16630,16631,16632,16633,16634,16635,16636,16637,16638,16639,16640,16641,16642,16643,16644,16645,16646,16647,16648,16649,16650,16651,16652,16653,16654,16655,16656,16657,16658,16659,16660,16661,16662,16663,16664,16665,16666,16667,16668,16669,16670,16671,16672,16673,16674,16675,16676,16677,16678,16679,16680,16681,16682,16683,16684,16685,16686,16687,16688,16689,16690,16691,16692,16693,16694,16695,16696,16697,16698,16699,16700,16701,16702,16703,16704,16705,16706,16707,16708,16709,16710,16711,16712,16713,16714,16715,16716,16717,16718,16719,16720,16721,16722,16723,16724,16725,16726,16727,16728,16729,16730,16731,16732,16733,16734,16735,16736,16737,16738,16739,16740,16741,16742,16743,16744,16745,16746,16747,16748,16749,16750,16751,16752,16753,16754,16755,16756,16757,16758,16759,16760,16761,16762,16763,16764,16765,16766,16767,16768,16769,16770,16771,16772,16773,16774,16775,16776,16777,16778,16779,16780,16781,16782,16783,16784,16785,16786,16787,16788,16789,16790,16791,16792,16793,16794,16795,16796,16797,16798,16799,16800,16801,16802,16803,16804,16805,16806,16807,16808,16809,16810,16811,16812,16813,16814,16815,16816,16817,16818,16819,16820,16821,16822,16823,16824,16825,16826,16827,16828,16829,16830,16831,16832,16833,16834,16835,16836,16837,16838,16839,16840,16841,16842,16843,16844,16845,16846,16847,16848,16849,16850,16851,16852,16853,16854,16855,16856,16857,16858,16859,16860,16861,16862,16863,16864,16865,16866,16867,16868,16869,16870,16871,16872,16873,16874,16875,16876,16877,16878,16879,16880,16881,16882,16883,16884,16885,16886,16887,16888,16889,16890,16891,16892,16893,16894,16895,16896,16897,16898,16899,16900,16901,16902,16903,16904,16905,16906,16907,16908,16909,16910,16911,16912,16913,16914,16915,16916,16917,16918,16919,16920,16921,16922,16923,16924,16925,16926,16927,16928,16929,16930,16931,16932,16933,16934,16935,16936,16937,16938,16939,16940,16941,16942,16943,16944,16945,16946,16947,16948,16949,16950,16951,16952,16953,16954,16955,16956,16957,16958,16959,16960,16961,16962,16963,16964,16965,16966,16967,16968,16969,16970,16971,16972,16973,16974,16975,16976,16977,16978,16979,16980,16981,16982,16983,16984,16985,16986,16987,16988,16989,16990,16991,16992,16993,16994,16995,16996,16997,16998,16999,17000,17001,17002,17003,17004,17005,17006,17007,17008,17009,17010,17011,17012,17013,17014,17015,17016,17017,17018,17019,17020,17021,17022,17023,17024,17025,17026,17027,17028,17029,17030,17031,17032,17033,17034,17035,17036,17037,17038,17039,17040,17041,17042,17043,17044,17045,17046,17047,17048,17049,17050,17051,17052,17053,17054,17055,17056,17057,17058,17059,17060,17061,17062,17063,17064,17065,17066,17067,17068,17069,17070,17071,17072,17073,17074,17075,17076,17077,17078,17079,17080,17081,17082,17083,17084,17085,17086,17087,17088,17089,17090,17091,17092,17093,17094,17095,17096,17097,17098,17099,17100,17101,17102,17103,17104,17105,17106,17107,17108,17109,17110,17111,17112,17113,17114,17115,17116,17117,17118,17119,17120,17121,17122,17123,17124,17125,17126,17127,17128,17129,17130,17131,17132,17133,17134,17135,17136,17137,17138,17139,17140,17141,17142,17143,17144,17145,17146,17147,17148,17149,17150,17151,17152,17153,17154,17155,17156,17157,17158,17159,17160,17161,17162,17163,17164,17165,17166,17167,17168,17169,17170,17171,17172,17173,17174,17175,17176,17177,17178,17179,17180,17181,17182,17183,17184,17185,17186,17187,17188,17189,17190,17191,17192,17193,17194,17195,17196,17197,17198,17199,17200,17201,17202,17203,17204,17205,17206,17207,17208,17209,17210,17211,17212,17213,17214,17215,17216,17217,17218,17219,17220,17221,17222,17223,17224,17225,17226,17227,17228,17229,17230,17231,17232,17233,17234,17235,17236,17237,17238,17239,17240,17241,17242,17243,17244,17245,17246,17247,17248,17249,17250,17251,17252,17253,17254,17255,17256,17257,17258,17259,17260,17261,17262,17263,17264,17265,17266,17267,17268,17269,17270,17271,17272,17273,17274,17275,17276,17277,17278,17279,17280,17281,17282,17283,17284,17285,17286,17287,17288,17289,17290,17291,17292,17293,17294,17295,17296,17297,17298,17299,17300,17301,17302,17303,17304,17305,17306,17307,17308,17309,17310,17311,17312,17313,17314,17315,17316,17317,17318,17319,17320,17321,17322,17323,17324,17325,17326,17327,17328,17329,17330,17331,17332,17333,17334,17335,17336,17337,17338,17339,17340,17341,17342,17343,17344,17345,17346,17347,17348,17349,17350,17351,17352,17353,17354,17355,17356,17357,17358,17359,17360,17361,17362,17363,17364,17365,17366,17367,17368,17369,17370,17371,17372,17373,17374,17375,17376,17377,17378,17379,17380,17381,17382,17383,17384,17385,17386,17387,17388,17389,17390,17391,17392,17393,17394,17395,17396,17397,17398,17399,17400,17401,17402,17403,17404,17405,17406,17407,17408,17409,17410,17411,17412,17413,17414,17415,17416,17417,17418,17419,17420,17421,17422,17423,17424,17425,17426,17427,17428,17429,17430,17431,17432,17433,17434,17435,17436,17437,17438,17439,17440,17441,17442,17443,17444,17445,17446,17447,17448,17449,17450,17451,17452,17453,17454,17455,17456,17457,17458,17459,17460,17461,17462,17463,17464,17465,17466,17467,17468,17469,17470,17471,17472,17473,17474,17475,17476,17477,17478,17479,17480,17481,17482,17483,17484,17485,17486,17487,17488,17489,17490,17491,17492,17493,17494,17495,17496,17497,17498,17499,17500,17501,17502,17503,17504,17505,17506,17507,17508,17509,17510,17511,17512,17513,17514,17515,17516,17517,17518,17519,17520,17521,17522,17523,17524,17525,17526,17527,17528,17529,17530,17531,17532,17533,17534,17535,17536,17537,17538,17539,17540,17541,17542,17543,17544,17545,17546,17547,17548,17549,17550,17551,17552,17553,17554,17555,17556,17557,17558,17559,17560,17561,17562,17563,17564,17565,17566,17567,17568,17569,17570,17571,17572,17573,17574,17575,17576,17577,17578,17579,17580,17581,17582,17583,17584,17585,17586,17587,17588,17589,17590,17591,17592,17593,17594,17595,17596,17597,17598,17599,17600,17601,17602,17603,17604,17605,17606,17607,17608,17609,17610,17611,17612,17613,17614,17615,17616,17617,17618,17619,17620,17621,17622,17623,17624,17625,17626,17627,17628,17629,17630,17631,17632,17633,17634,17635,17636,17637,17638,17639,17640,17641,17642,17643,17644,17645,17646,17647,17648,17649,17650,17651,17652,17653,17654,17655,17656,17657,17658,17659,17660,17661,17662,17663,17664,17665,17666,17667,17668,17669,17670,17671,17672,17673,17674,17675,17676,17677,17678,17679,17680,17681,17682,17683,17684,17685,17686,17687,17688,17689,17690,17691,17692,17693,17694,17695,17696,17697,17698,17699,17700,17701,17702,17703,17704,17705,17706,17707,17708,17709,17710,17711,17712,17713,17714,17715,17716,17717,17718,17719,17720,17721,17722,17723,17724,17725,17726,17727,17728,17729,17730,17731,17732,17733,17734,17735,17736,17737,17738,17739,17740,17741,17742,17743,17744,17745,17746,17747,17748,17749,17750,17751,17752,17753,17754,17755,17756,17757,17758,17759,17760,17761,17762,17763,17764,17765,17766,17767,17768,17769,17770,17771,17772,17773,17774,17775,17776,17777,17778,17779,17780,17781,17782,17783,17784,17785,17786,17787,17788,17789,17790,17791,17792,17793,17794,17795,17796,17797,17798,17799,17800,17801,17802,17803,17804,17805,17806,17807,17808,17809,17810,17811,17812,17813,17814,17815,17816,17817,17818,17819,17820,17821,17822,17823,17824,17825,17826,17827,17828,17829,17830,17831,17832,17833,17834,17835,17836,17837,17838,17839,17840,17841,17842,17843,17844,17845,17846,17847,17848,17849,17850,17851,17852,17853,17854,17855,17856,17857,17858,17859,17860,17861,17862,17863,17864,17865,17866,17867,17868,17869,17870,17871,17872,17873,17874,17875,17876,17877,17878,17879,17880,17881,17882,17883,17884,17885,17886,17887,17888,17889,17890,17891,17892,17893,17894,17895,17896,17897,17898,17899,17900,17901,17902,17903,17904,17905,17906,17907,17908,17909,17910,17911,17912,17913,17914,17915,17916,17917,17918,17919,17920,17921,17922,17923,17924,17925,17926,17927,17928,17929,17930,17931,17932,17933,17934,17935,17936,17937,17938,17939,17940,17941,17942,17943,17944,17945,17946,17947,17948,17949,17950,17951,17952,17953,17954,17955,17956,17957,17958,17959,17960,17961,17962,17963,17964,17965,17966,17967,17968,17969,17970,17971,17972,17973,17974,17975,17976,17977,17978,17979,17980,17981,17982,17983,17984,17985,17986,17987,17988,17989,17990,17991,17992,17993,17994,17995,17996,17997,17998,17999,18000,18001,18002,18003,18004,18005,18006,18007,18008,18009,18010,18011,18012,18013,18014,18015,18016,18017,18018,18019,18020,18021,18022,18023,18024,18025,18026,18027,18028,18029,18030,18031,18032,18033,18034,18035,18036,18037,18038,18039,18040,18041,18042,18043,18044,18045,18046,18047,18048,18049,18050,18051,18052,18053,18054,18055,18056,18057,18058,18059,18060,18061,18062,18063,18064,18065,18066,18067,18068,18069,18070,18071,18072,18073,18074,18075,18076,18077,18078,18079,18080,18081,18082,18083,18084,18085,18086,18087,18088,18089,18090,18091,18092,18093,18094,18095,18096,18097,18098,18099,18100,18101,18102,18103,18104,18105,18106,18107,18108,18109,18110,18111,18112,18113,18114,18115,18116,18117,18118,18119,18120,18121,18122,18123,18124,18125,18126,18127,18128,18129,18130,18131,18132,18133,18134,18135,18136,18137,18138,18139,18140,18141,18142,18143,18144,18145,18146,18147,18148,18149,18150,18151,18152,18153,18154,18155,18156,18157,18158,18159,18160,18161,18162,18163,18164,18165,18166,18167,18168,18169,18170,18171,18172,18173,18174,18175,18176,18177,18178,18179,18180,18181,18182,18183,18184,18185,18186,18187,18188,18189,18190,18191,18192,18193,18194,18195,18196,18197,18198,18199,18200,18201,18202,18203,18204,18205,18206,18207,18208,18209,18210,18211,18212,18213,18214,18215,18216,18217,18218,18219,18220,18221,18222,18223,18224,18225,18226,18227,18228,18229,18230,18231,18232,18233,18234,18235,18236,18237,18238,18239,18240,18241,18242,18243,18244,18245,18246,18247,18248,18249,18250,18251,18252,18253,18254,18255,18256,18257,18258,18259,18260,18261,18262,18263,18264,18265,18266,18267,18268,18269,18270,18271,18272,18273,18274,18275,18276,18277,18278,18279,18280,18281,18282,18283,18284,18285,18286,18287,18288,18289,18290,18291,18292,18293,18294,18295,18296,18297,18298,18299,18300,18301,18302,18303,18304,18305,18306,18307,18308,18309,18310,18311,18312,18313,18314,18315,18316,18317,18318,18319,18320,18321,18322,18323,18324,18325,18326,18327,18328,18329,18330,18331,18332,18333,18334,18335,18336,18337,18338,18339,18340,18341,18342,18343,18344,18345,18346,18347,18348,18349,18350,18351,18352,18353,18354,18355,18356,18357,18358,18359,18360,18361,18362,18363,18364,18365,18366,18367,18368,18369,18370,18371,18372,18373,18374,18375,18376,18377,18378,18379,18380,18381,18382,18383,18384,18385,18386,18387,18388,18389,18390,18391,18392,18393,18394,18395,18396,18397,18398,18399,18400,18401,18402,18403,18404,18405,18406,18407,18408,18409,18410,18411,18412,18413,18414,18415,18416,18417,18418,18419,18420,18421,18422,18423,18424,18425,18426,18427,18428,18429,18430,18431,18432,18433,18434,18435,18436,18437,18438,18439,18440,18441,18442,18443,18444,18445,18446,18447,18448,18449,18450,18451,18452,18453,18454,18455,18456,18457,18458,18459,18460,18461,18462,18463,18464,18465,18466,18467,18468,18469,18470,18471,18472,18473,18474,18475,18476,18477,18478,18479,18480,18481,18482,18483,18484,18485,18486,18487,18488,18489,18490,18491,18492,18493,18494,18495,18496,18497,18498,18499,18500,18501,18502,18503,18504,18505,18506,18507,18508,18509,18510,18511,18512,18513,18514,18515,18516,18517,18518,18519,18520,18521,18522,18523,18524,18525,18526,18527,18528,18529,18530,18531,18532,18533,18534,18535,18536,18537,18538,18539,18540,18541,18542,18543,18544,18545,18546,18547,18548,18549,18550,18551,18552,18553,18554,18555,18556,18557,18558,18559,18560,18561,18562,18563,18564,18565,18566,18567,18568,18569,18570,18571,18572,18573,18574,18575,18576,18577,18578,18579,18580,18581,18582,18583,18584,18585,18586,18587,18588,18589,18590,18591,18592,18593,18594,18595,18596,18597,18598,18599,18600,18601,18602,18603,18604,18605,18606,18607,18608,18609,18610,18611,18612,18613,18614,18615,18616,18617,18618,18619,18620,18621,18622,18623,18624,18625,18626,18627,18628,18629,18630,18631,18632,18633,18634,18635,18636,18637,18638,18639,18640,18641,18642,18643,18644,18645,18646,18647,18648,18649,18650,18651,18652,18653,18654,18655,18656,18657,18658,18659,18660,18661,18662,18663,18664,18665,18666,18667,18668,18669,18670,18671,18672,18673,18674,18675,18676,18677,18678,18679,18680,18681,18682,18683,18684,18685,18686,18687,18688,18689,18690,18691,18692,18693,18694,18695,18696,18697,18698,18699,18700,18701,18702,18703,18704,18705,18706,18707,18708,18709,18710,18711,18712,18713,18714,18715,18716,18717,18718,18719,18720,18721,18722,18723,18724,18725,18726,18727,18728,18729,18730,18731,18732,18733,18734,18735,18736,18737,18738,18739,18740,18741,18742,18743,18744,18745,18746,18747,18748,18749,18750,18751,18752,18753,18754,18755,18756,18757,18758,18759,18760,18761,18762,18763,18764,18765,18766,18767,18768,18769,18770,18771,18772,18773,18774,18775,18776,18777,18778,18779,18780,18781,18782,18783,18784,18785,18786,18787,18788,18789,18790,18791,18792,18793,18794,18795,18796,18797,18798,18799,18800,18801,18802,18803,18804,18805,18806,18807,18808,18809,18810,18811,18812,18813,18814,18815,18816,18817,18818,18819,18820,18821,18822,18823,18824,18825,18826,18827,18828,18829,18830,18831,18832,18833,18834,18835,18836,18837,18838,18839,18840,18841,18842,18843,18844,18845,18846,18847,18848,18849,18850,18851,18852,18853,18854,18855,18856,18857,18858,18859,18860,18861,18862,18863,18864,18865,18866,18867,18868,18869,18870,18871,18872,18873,18874,18875,18876,18877,18878,18879,18880,18881,18882,18883,18884,18885,18886,18887,18888,18889,18890,18891,18892,18893,18894,18895,18896,18897,18898,18899,18900,18901,18902,18903,18904,18905,18906,18907,18908,18909,18910,18911,18912,18913,18914,18915,18916,18917,18918,18919,18920,18921,18922,18923,18924,18925,18926,18927,18928,18929,18930,18931,18932,18933,18934,18935,18936,18937,18938,18939,18940,18941,18942,18943,18944,18945,18946,18947,18948,18949,18950,18951,18952,18953,18954,18955,18956,18957,18958,18959,18960,18961,18962,18963,18964,18965,18966,18967,18968,18969,18970,18971,18972,18973,18974,18975,18976,18977,18978,18979,18980,18981,18982,18983,18984,18985,18986,18987,18988,18989,18990,18991,18992,18993,18994,18995,18996,18997,18998,18999,19000,19001,19002,19003,19004,19005,19006,19007,19008,19009,19010,19011,19012,19013,19014,19015,19016,19017,19018,19019,19020,19021,19022,19023,19024,19025,19026,19027,19028,19029,19030,19031,19032,19033,19034,19035,19036,19037,19038,19039,19040,19041,19042,19043,19044,19045,19046,19047,19048,19049,19050,19051,19052,19053,19054,19055,19056,19057,19058,19059,19060,19061,19062,19063,19064,19065,19066,19067,19068,19069,19070,19071,19072,19073,19074,19075,19076,19077,19078,19079,19080,19081,19082,19083,19084,19085,19086,19087,19088,19089,19090,19091,19092,19093,19094,19095,19096,19097,19098,19099,19100,19101,19102,19103,19104,19105,19106,19107,19108,19109,19110,19111,19112,19113,19114,19115,19116,19117,19118,19119,19120,19121,19122,19123,19124,19125,19126,19127,19128,19129,19130,19131,19132,19133,19134,19135,19136,19137,19138,19139,19140,19141,19142,19143,19144,19145,19146,19147,19148,19149,19150,19151,19152,19153,19154,19155,19156,19157,19158,19159,19160,19161,19162,19163,19164,19165,19166,19167,19168,19169,19170,19171,19172,19173,19174,19175,19176,19177,19178,19179,19180,19181,19182,19183,19184,19185,19186,19187,19188,19189,19190,19191,19192,19193,19194,19195,19196,19197,19198,19199,19200,19201,19202,19203,19204,19205,19206,19207,19208,19209,19210,19211,19212,19213,19214,19215,19216,19217,19218,19219,19220,19221,19222,19223,19224,19225,19226,19227,19228,19229,19230,19231,19232,19233,19234,19235,19236,19237,19238,19239,19240,19241,19242,19243,19244,19245,19246,19247,19248,19249,19250,19251,19252,19253,19254,19255,19256,19257,19258,19259,19260,19261,19262,19263,19264,19265,19266,19267,19268,19269,19270,19271,19272,19273,19274,19275,19276,19277,19278,19279,19280,19281,19282,19283,19284,19285,19286,19287,19288,19289,19290,19291,19292,19293,19294,19295,19296,19297,19298,19299,19300,19301,19302,19303,19304,19305,19306,19307,19308,19309,19310,19311,19312,19313,19314,19315,19316,19317,19318,19319,19320,19321,19322,19323,19324,19325,19326,19327,19328,19329,19330,19331,19332,19333,19334,19335,19336,19337,19338,19339,19340,19341,19342,19343,19344,19345,19346,19347,19348,19349,19350,19351,19352,19353,19354,19355,19356,19357,19358,19359,19360,19361,19362,19363,19364,19365,19366,19367,19368,19369,19370,19371,19372,19373,19374,19375,19376,19377,19378,19379,19380,19381,19382,19383,19384,19385,19386,19387,19388,19389,19390,19391,19392,19393,19394,19395,19396,19397,19398,19399,19400,19401,19402,19403,19404,19405,19406,19407,19408,19409,19410,19411,19412,19413,19414,19415,19416,19417,19418,19419,19420,19421,19422,19423,19424,19425,19426,19427,19428,19429,19430,19431,19432,19433,19434,19435,19436,19437,19438,19439,19440,19441,19442,19443,19444,19445,19446,19447,19448,19449,19450,19451,19452,19453,19454,19455,19456,19457,19458,19459,19460,19461,19462,19463,19464,19465,19466,19467,19468,19469,19470,19471,19472,19473,19474,19475,19476,19477,19478,19479,19480,19481,19482,19483,19484,19485,19486,19487,19488,19489,19490,19491,19492,19493,19494,19495,19496,19497,19498,19499,19500,19501,19502,19503,19504,19505,19506,19507,19508,19509,19510,19511,19512,19513,19514,19515,19516,19517,19518,19519,19520,19521,19522,19523,19524,19525,19526,19527,19528,19529,19530,19531,19532,19533,19534,19535,19536,19537,19538,19539,19540,19541,19542,19543,19544,19545,19546,19547,19548,19549,19550,19551,19552,19553,19554,19555,19556,19557,19558,19559,19560,19561,19562,19563,19564,19565,19566,19567,19568,19569,19570,19571,19572,19573,19574,19575,19576,19577,19578,19579,19580,19581,19582,19583,19584,19585,19586,19587,19588,19589,19590,19591,19592,19593,19594,19595,19596,19597,19598,19599,19600,19601,19602,19603,19604,19605,19606,19607,19608,19609,19610,19611,19612,19613,19614,19615,19616,19617,19618,19619,19620,19621,19622,19623,19624,19625,19626,19627,19628,19629,19630,19631,19632,19633,19634,19635,19636,19637,19638,19639,19640,19641,19642,19643,19644,19645,19646,19647,19648,19649,19650,19651,19652,19653,19654,19655,19656,19657,19658,19659,19660,19661,19662,19663,19664,19665,19666,19667,19668,19669,19670,19671,19672,19673,19674,19675,19676,19677,19678,19679,19680,19681,19682,19683,19684,19685,19686,19687,19688,19689,19690,19691,19692,19693,19694,19695,19696,19697,19698,19699,19700,19701,19702,19703,19704,19705,19706,19707,19708,19709,19710,19711,19712,19713,19714,19715,19716,19717,19718,19719,19720,19721,19722,19723,19724,19725,19726,19727,19728,19729,19730,19731,19732,19733,19734,19735,19736,19737,19738,19739,19740,19741,19742,19743,19744,19745,19746,19747,19748,19749,19750,19751,19752,19753,19754,19755,19756,19757,19758,19759,19760,19761,19762,19763,19764,19765,19766,19767,19768,19769,19770,19771,19772,19773,19774,19775,19776,19777,19778,19779,19780,19781,19782,19783,19784,19785,19786,19787,19788,19789,19790,19791,19792,19793,19794,19795,19796,19797,19798,19799,19800,19801,19802,19803,19804,19805,19806,19807,19808,19809,19810,19811,19812,19813,19814,19815,19816,19817,19818,19819,19820,19821,19822,19823,19824,19825,19826,19827,19828,19829,19830,19831,19832,19833,19834,19835,19836,19837,19838,19839,19840,19841,19842,19843,19844,19845,19846,19847,19848,19849,19850,19851,19852,19853,19854,19855,19856,19857,19858,19859,19860,19861,19862,19863,19864,19865,19866,19867,19868,19869,19870,19871,19872,19873,19874,19875,19876,19877,19878,19879,19880,19881,19882,19883,19884,19885,19886,19887,19888,19889,19890,19891,19892,19893,19894,19895,19896,19897,19898,19899,19900,19901,19902,19903,19904,19905,19906,19907,19908,19909,19910,19911,19912,19913,19914,19915,19916,19917,19918,19919,19920,19921,19922,19923,19924,19925,19926,19927,19928,19929,19930,19931,19932,19933,19934,19935,19936,19937,19938,19939,19940,19941,19942,19943,19944,19945,19946,19947,19948,19949,19950,19951,19952,19953,19954,19955,19956,19957,19958,19959,19960,19961,19962,19963,19964,19965,19966,19967,19968,19969,19970,19971,19972,19973,19974,19975,19976,19977,19978,19979,19980,19981,19982,19983,19984,19985,19986,19987,19988,19989,19990,19991,19992,19993,19994,19995,19996,19997,19998,19999,20000,20001,20002,20003,20004,20005,20006,20007,20008,20009,20010,20011,20012,20013,20014,20015,20016,20017,20018,20019,20020,20021,20022,20023,20024,20025,20026,20027,20028,20029,20030,20031,20032,20033,20034,20035,20036,20037,20038,20039,20040,20041,20042,20043,20044,20045,20046,20047,20048,20049,20050,20051,20052,20053,20054,20055,20056,20057,20058,20059,20060,20061,20062,20063,20064,20065,20066,20067,20068,20069,20070,20071,20072,20073,20074,20075,20076,20077,20078,20079,20080,20081,20082,20083,20084,20085,20086,20087,20088,20089,20090,20091,20092,20093,20094,20095,20096,20097,20098,20099,20100,20101,20102,20103,20104,20105,20106,20107,20108,20109,20110,20111,20112,20113,20114,20115,20116,20117,20118,20119,20120,20121,20122,20123,20124,20125,20126,20127,20128,20129,20130,20131,20132,20133,20134,20135,20136,20137,20138,20139,20140,20141,20142,20143,20144,20145,20146,20147,20148,20149,20150,20151,20152,20153,20154,20155,20156,20157,20158,20159,20160,20161,20162,20163,20164,20165,20166,20167,20168,20169,20170,20171,20172,20173,20174,20175,20176,20177,20178,20179,20180,20181,20182,20183,20184,20185,20186,20187,20188,20189,20190,20191,20192,20193,20194,20195,20196,20197,20198,20199,20200,20201,20202,20203,20204,20205,20206,20207,20208,20209,20210,20211,20212,20213,20214,20215,20216,20217,20218,20219,20220,20221,20222,20223,20224,20225,20226,20227,20228,20229,20230,20231,20232,20233,20234,20235,20236,20237,20238,20239,20240,20241,20242,20243,20244,20245,20246,20247,20248,20249,20250,20251,20252,20253,20254,20255,20256,20257,20258,20259,20260,20261,20262,20263,20264,20265,20266,20267,20268,20269,20270,20271,20272,20273,20274,20275,20276,20277,20278,20279,20280,20281,20282,20283,20284,20285,20286,20287,20288,20289,20290,20291,20292,20293,20294,20295,20296,20297,20298,20299,20300,20301,20302,20303,20304,20305,20306,20307,20308,20309,20310,20311,20312,20313,20314,20315,20316,20317,20318,20319,20320,20321,20322,20323,20324,20325,20326,20327,20328,20329,20330,20331,20332,20333,20334,20335,20336,20337,20338,20339,20340,20341,20342,20343,20344,20345,20346,20347,20348,20349,20350,20351,20352,20353,20354,20355,20356,20357,20358,20359,20360,20361,20362,20363,20364,20365,20366,20367,20368,20369,20370,20371,20372,20373,20374,20375,20376,20377,20378,20379,20380,20381,20382,20383,20384,20385,20386,20387,20388,20389,20390,20391,20392,20393,20394,20395,20396,20397,20398,20399,20400,20401,20402,20403,20404,20405,20406,20407,20408,20409,20410,20411,20412,20413,20414,20415,20416,20417,20418,20419,20420,20421,20422,20423,20424,20425,20426,20427,20428,20429,20430,20431,20432,20433,20434,20435,20436,20437,20438,20439,20440,20441,20442,20443,20444,20445,20446,20447,20448,20449,20450,20451,20452,20453,20454,20455,20456,20457,20458,20459,20460,20461,20462,20463,20464,20465,20466,20467,20468,20469,20470,20471,20472,20473,20474,20475,20476,20477,20478,20479,20480,20481,20482,20483,20484,20485,20486,20487,20488,20489,20490,20491,20492,20493,20494,20495,20496,20497,20498,20499,20500,20501,20502,20503,20504,20505,20506,20507,20508,20509,20510,20511,20512,20513,20514,20515,20516,20517,20518,20519,20520,20521,20522,20523,20524,20525,20526,20527,20528,20529,20530,20531,20532,20533,20534,20535,20536,20537,20538,20539,20540,20541,20542,20543,20544,20545,20546,20547,20548,20549,20550,20551,20552,20553,20554,20555,20556,20557,20558,20559,20560,20561,20562,20563,20564,20565,20566,20567,20568,20569,20570,20571,20572,20573,20574,20575,20576,20577,20578,20579,20580,20581,20582,20583,20584,20585,20586,20587,20588,20589,20590,20591,20592,20593,20594,20595,20596,20597,20598,20599,20600,20601,20602,20603,20604,20605,20606,20607,20608,20609,20610,20611,20612,20613,20614,20615,20616,20617,20618,20619,20620,20621,20622,20623,20624,20625,20626,20627,20628,20629,20630,20631,20632,20633,20634,20635,20636,20637,20638,20639,20640,20641,20642,20643,20644,20645,20646,20647,20648,20649,20650,20651,20652,20653,20654,20655,20656,20657,20658,20659,20660,20661,20662,20663,20664,20665,20666,20667,20668,20669,20670,20671,20672,20673,20674,20675,20676,20677,20678,20679,20680,20681,20682,20683,20684,20685,20686,20687,20688,20689,20690,20691,20692,20693,20694,20695,20696,20697,20698,20699,20700,20701,20702,20703,20704,20705,20706,20707,20708,20709,20710,20711,20712,20713,20714,20715,20716,20717,20718,20719,20720,20721,20722,20723,20724,20725,20726,20727,20728,20729,20730,20731,20732,20733,20734,20735,20736,20737,20738,20739,20740,20741,20742,20743,20744,20745,20746,20747,20748,20749,20750,20751,20752,20753,20754,20755,20756,20757,20758,20759,20760,20761,20762,20763,20764,20765,20766,20767,20768,20769,20770,20771,20772,20773,20774,20775,20776,20777,20778,20779,20780,20781,20782,20783,20784,20785,20786,20787,20788,20789,20790,20791,20792,20793,20794,20795,20796,20797,20798,20799,20800,20801,20802,20803,20804,20805,20806,20807,20808,20809,20810,20811,20812,20813,20814,20815,20816,20817,20818,20819,20820,20821,20822,20823,20824,20825,20826,20827,20828,20829,20830,20831,20832,20833,20834,20835,20836,20837,20838,20839,20840,20841,20842,20843,20844,20845,20846,20847,20848,20849,20850,20851,20852,20853,20854,20855,20856,20857,20858,20859,20860,20861,20862,20863,20864,20865,20866,20867,20868,20869,20870,20871,20872,20873,20874,20875,20876,20877,20878,20879,20880,20881,20882,20883,20884,20885,20886,20887,20888,20889,20890,20891,20892,20893,20894,20895,20896,20897,20898,20899,20900,20901,20902,20903,20904,20905,20906,20907,20908,20909,20910,20911,20912,20913,20914,20915,20916,20917,20918,20919,20920,20921,20922,20923,20924,20925,20926,20927,20928,20929,20930,20931,20932,20933,20934,20935,20936,20937,20938,20939,20940,20941,20942,20943,20944,20945,20946,20947,20948,20949,20950,20951,20952,20953,20954,20955,20956,20957,20958,20959,20960,20961,20962,20963,20964,20965,20966,20967,20968,20969,20970,20971,20972,20973,20974,20975,20976,20977,20978,20979,20980,20981,20982,20983,20984,20985,20986,20987,20988,20989,20990,20991,20992,20993,20994,20995,20996,20997,20998,20999,21000,21001,21002,21003,21004,21005,21006,21007,21008,21009,21010,21011,21012,21013,21014,21015,21016,21017,21018,21019,21020,21021,21022,21023,21024,21025,21026,21027,21028,21029,21030,21031,21032,21033,21034,21035,21036,21037,21038,21039,21040,21041,21042,21043,21044,21045,21046,21047,21048,21049,21050,21051,21052,21053,21054,21055,21056,21057,21058,21059,21060,21061,21062,21063,21064,21065,21066,21067,21068,21069,21070,21071,21072,21073,21074,21075,21076,21077,21078,21079,21080,21081,21082,21083,21084,21085,21086,21087,21088,21089,21090,21091,21092,21093,21094,21095,21096,21097,21098,21099,21100,21101,21102,21103,21104,21105,21106,21107,21108,21109,21110,21111,21112,21113,21114,21115,21116,21117,21118,21119,21120,21121,21122,21123,21124,21125,21126,21127,21128,21129,21130,21131,21132,21133,21134,21135,21136,21137,21138,21139,21140,21141,21142,21143,21144,21145,21146,21147,21148,21149,21150,21151,21152,21153,21154,21155,21156,21157,21158,21159,21160,21161,21162,21163,21164,21165,21166,21167,21168,21169,21170,21171,21172,21173,21174,21175,21176,21177,21178,21179,21180,21181,21182,21183,21184,21185,21186,21187,21188,21189,21190,21191,21192,21193,21194,21195,21196,21197,21198,21199,21200,21201,21202,21203,21204,21205,21206,21207,21208,21209,21210,21211,21212,21213,21214,21215,21216,21217,21218,21219,21220,21221,21222,21223,21224,21225,21226,21227,21228,21229,21230,21231,21232,21233,21234,21235,21236,21237,21238,21239,21240,21241,21242,21243,21244,21245,21246,21247,21248,21249,21250,21251,21252,21253,21254,21255,21256,21257,21258,21259,21260,21261,21262,21263,21264,21265,21266,21267,21268,21269,21270,21271,21272,21273,21274,21275,21276,21277,21278,21279,21280,21281,21282,21283,21284,21285,21286,21287,21288,21289,21290,21291,21292,21293,21294,21295,21296,21297,21298,21299,21300,21301,21302,21303,21304,21305,21306,21307,21308,21309,21310,21311,21312,21313,21314,21315,21316,21317,21318,21319,21320,21321,21322,21323,21324,21325,21326,21327,21328,21329,21330,21331,21332,21333,21334,21335,21336,21337,21338,21339,21340,21341,21342,21343,21344,21345,21346,21347,21348,21349,21350,21351,21352,21353,21354,21355,21356,21357,21358,21359,21360,21361,21362,21363,21364,21365,21366,21367,21368,21369,21370,21371,21372,21373,21374,21375,21376,21377,21378,21379,21380,21381,21382,21383,21384,21385,21386,21387,21388,21389,21390,21391,21392,21393,21394,21395,21396,21397,21398,21399,21400,21401,21402,21403,21404,21405,21406,21407,21408,21409,21410,21411,21412,21413,21414,21415,21416,21417,21418,21419,21420,21421,21422,21423,21424,21425,21426,21427,21428,21429,21430,21431,21432,21433,21434,21435,21436,21437,21438,21439,21440,21441,21442,21443,21444,21445,21446,21447,21448,21449,21450,21451,21452,21453,21454,21455,21456,21457,21458,21459,21460,21461,21462,21463,21464,21465,21466,21467,21468,21469,21470,21471,21472,21473,21474,21475,21476,21477,21478,21479,21480,21481,21482,21483,21484,21485,21486,21487,21488,21489,21490,21491,21492,21493,21494,21495,21496,21497,21498,21499,21500,21501,21502,21503,21504,21505,21506,21507,21508,21509,21510,21511,21512,21513,21514,21515,21516,21517,21518,21519,21520,21521,21522,21523,21524,21525,21526,21527,21528,21529,21530,21531,21532,21533,21534,21535,21536,21537,21538,21539,21540,21541,21542,21543,21544,21545,21546,21547,21548,21549,21550,21551,21552,21553,21554,21555,21556,21557,21558,21559,21560,21561,21562,21563,21564,21565,21566,21567,21568,21569,21570,21571,21572,21573,21574,21575,21576,21577,21578,21579,21580,21581,21582,21583,21584,21585,21586,21587,21588,21589,21590,21591,21592,21593,21594,21595,21596,21597,21598,21599,21600,21601,21602,21603,21604,21605,21606,21607,21608,21609,21610,21611,21612,21613,21614,21615,21616,21617,21618,21619,21620,21621,21622,21623,21624,21625,21626,21627,21628,21629,21630,21631,21632,21633,21634,21635,21636,21637,21638,21639,21640,21641,21642,21643,21644,21645,21646,21647,21648,21649,21650,21651,21652,21653,21654,21655,21656,21657,21658,21659,21660,21661,21662,21663,21664,21665,21666,21667,21668,21669,21670,21671,21672,21673,21674,21675,21676,21677,21678,21679,21680,21681,21682,21683,21684,21685,21686,21687,21688,21689,21690,21691,21692,21693,21694,21695,21696,21697,21698,21699,21700,21701,21702,21703,21704,21705,21706,21707,21708,21709,21710,21711,21712,21713,21714,21715,21716,21717,21718,21719,21720,21721,21722,21723,21724,21725,21726,21727,21728,21729,21730,21731,21732,21733,21734,21735,21736,21737,21738,21739,21740,21741,21742,21743,21744,21745,21746,21747,21748,21749,21750,21751,21752,21753,21754,21755,21756,21757,21758,21759,21760,21761,21762,21763,21764,21765,21766,21767,21768,21769,21770,21771,21772,21773,21774,21775,21776,21777,21778,21779,21780,21781,21782,21783,21784,21785,21786,21787,21788,21789,21790,21791,21792,21793,21794,21795,21796,21797,21798,21799,21800,21801,21802,21803,21804,21805,21806,21807,21808,21809,21810,21811,21812,21813,21814,21815,21816,21817,21818,21819,21820,21821,21822,21823,21824,21825,21826,21827,21828,21829,21830,21831,21832,21833,21834,21835,21836,21837,21838,21839,21840,21841,21842,21843,21844,21845,21846,21847,21848,21849,21850,21851,21852,21853,21854,21855,21856,21857,21858,21859,21860,21861,21862,21863,21864,21865,21866,21867,21868,21869,21870,21871,21872,21873,21874,21875,21876,21877,21878,21879,21880,21881,21882,21883,21884,21885,21886,21887,21888,21889,21890,21891,21892,21893,21894,21895,21896,21897,21898,21899,21900,21901,21902,21903,21904,21905,21906,21907,21908,21909,21910,21911,21912,21913,21914,21915,21916,21917,21918,21919,21920,21921,21922,21923,21924,21925,21926,21927,21928,21929,21930,21931,21932,21933,21934,21935,21936,21937,21938,21939,21940,21941,21942,21943,21944,21945,21946,21947,21948,21949,21950,21951,21952,21953,21954,21955,21956,21957,21958,21959,21960,21961,21962,21963,21964,21965,21966,21967,21968,21969,21970,21971,21972,21973,21974,21975,21976,21977,21978,21979,21980,21981,21982,21983,21984,21985,21986,21987,21988,21989,21990,21991,21992,21993,21994,21995,21996,21997,21998,21999,22000,22001,22002,22003,22004,22005,22006,22007,22008,22009,22010,22011,22012,22013,22014,22015,22016,22017,22018,22019,22020,22021,22022,22023,22024,22025,22026,22027,22028,22029,22030,22031,22032,22033,22034,22035,22036,22037,22038,22039,22040,22041,22042,22043,22044,22045,22046,22047,22048,22049,22050,22051,22052,22053,22054,22055,22056,22057,22058,22059,22060,22061,22062,22063,22064,22065,22066,22067,22068,22069,22070,22071,22072,22073,22074,22075,22076,22077,22078,22079,22080,22081,22082,22083,22084,22085,22086,22087,22088,22089,22090,22091,22092,22093,22094,22095,22096,22097,22098,22099,22100,22101,22102,22103,22104,22105,22106,22107,22108,22109,22110,22111,22112,22113,22114,22115,22116,22117,22118,22119,22120,22121,22122,22123,22124,22125,22126,22127,22128,22129,22130,22131,22132,22133,22134,22135,22136,22137,22138,22139,22140,22141,22142,22143,22144,22145,22146,22147,22148,22149,22150,22151,22152,22153,22154,22155,22156,22157,22158,22159,22160,22161,22162,22163,22164,22165,22166,22167,22168,22169,22170,22171,22172,22173,22174,22175,22176,22177,22178,22179,22180,22181,22182,22183,22184,22185,22186,22187,22188,22189,22190,22191,22192,22193,22194,22195,22196,22197,22198,22199,22200,22201,22202,22203,22204,22205,22206,22207,22208,22209,22210,22211,22212,22213,22214,22215,22216,22217,22218,22219,22220,22221,22222,22223,22224,22225,22226,22227,22228,22229,22230,22231,22232,22233,22234,22235,22236,22237,22238,22239,22240,22241,22242,22243,22244,22245,22246,22247,22248,22249,22250,22251,22252,22253,22254,22255,22256,22257,22258,22259,22260,22261,22262,22263,22264,22265,22266,22267,22268,22269,22270,22271,22272,22273,22274,22275,22276,22277,22278,22279,22280,22281,22282,22283,22284,22285,22286,22287,22288,22289,22290,22291,22292,22293,22294,22295,22296,22297,22298,22299,22300,22301,22302,22303,22304,22305,22306,22307,22308,22309,22310,22311,22312,22313,22314,22315,22316,22317,22318,22319,22320,22321,22322,22323,22324,22325,22326,22327,22328,22329,22330,22331,22332,22333,22334,22335,22336,22337,22338,22339,22340,22341,22342,22343,22344,22345,22346,22347,22348,22349,22350,22351,22352,22353,22354,22355,22356,22357,22358,22359,22360,22361,22362,22363,22364,22365,22366,22367,22368,22369,22370,22371,22372,22373,22374,22375,22376,22377,22378,22379,22380,22381,22382,22383,22384,22385,22386,22387,22388,22389,22390,22391,22392,22393,22394,22395,22396,22397,22398,22399,22400,22401,22402,22403,22404,22405,22406,22407,22408,22409,22410,22411,22412,22413,22414,22415,22416,22417,22418,22419,22420,22421,22422,22423,22424,22425,22426,22427,22428,22429,22430,22431,22432,22433,22434,22435,22436,22437,22438,22439,22440,22441,22442,22443,22444,22445,22446,22447,22448,22449,22450,22451,22452,22453,22454,22455,22456,22457,22458,22459,22460,22461,22462,22463,22464,22465,22466,22467,22468,22469,22470,22471,22472,22473,22474,22475,22476,22477,22478,22479,22480,22481,22482,22483,22484,22485,22486,22487,22488,22489,22490,22491,22492,22493,22494,22495,22496,22497,22498,22499,22500,22501,22502,22503,22504,22505,22506,22507,22508,22509,22510,22511,22512,22513,22514,22515,22516,22517,22518,22519,22520,22521,22522,22523,22524,22525,22526,22527,22528,22529,22530,22531,22532,22533,22534,22535,22536,22537,22538,22539,22540,22541,22542,22543,22544,22545,22546,22547,22548,22549,22550,22551,22552,22553,22554,22555,22556,22557,22558,22559,22560,22561,22562,22563,22564,22565,22566,22567,22568,22569,22570,22571,22572,22573,22574,22575,22576,22577,22578,22579,22580,22581,22582,22583,22584,22585,22586,22587,22588,22589,22590,22591,22592,22593,22594,22595,22596,22597,22598,22599,22600,22601,22602,22603,22604,22605,22606,22607,22608,22609,22610,22611,22612,22613,22614,22615,22616,22617,22618,22619,22620,22621,22622,22623,22624,22625,22626,22627,22628,22629,22630,22631,22632,22633,22634,22635,22636,22637,22638,22639,22640,22641,22642,22643,22644,22645,22646,22647,22648,22649,22650,22651,22652,22653,22654,22655,22656,22657,22658,22659,22660,22661,22662,22663,22664,22665,22666,22667,22668,22669,22670,22671,22672,22673,22674,22675,22676,22677,22678,22679,22680,22681,22682,22683,22684,22685,22686,22687,22688,22689,22690,22691,22692,22693,22694,22695,22696,22697,22698,22699,22700,22701,22702,22703,22704,22705,22706,22707,22708,22709,22710,22711,22712,22713,22714,22715,22716,22717,22718,22719,22720,22721,22722,22723,22724,22725,22726,22727,22728,22729,22730,22731,22732,22733,22734,22735,22736,22737,22738,22739,22740,22741,22742,22743,22744,22745,22746,22747,22748,22749,22750,22751,22752,22753,22754,22755,22756,22757,22758,22759,22760,22761,22762,22763,22764,22765,22766,22767,22768,22769,22770,22771,22772,22773,22774,22775,22776,22777,22778,22779,22780,22781,22782,22783,22784,22785,22786,22787,22788,22789,22790,22791,22792,22793,22794,22795,22796,22797,22798,22799,22800,22801,22802,22803,22804,22805,22806,22807,22808,22809,22810,22811,22812,22813,22814,22815,22816,22817,22818,22819,22820,22821,22822,22823,22824,22825,22826,22827,22828,22829,22830,22831,22832,22833,22834,22835,22836,22837,22838,22839,22840,22841,22842,22843,22844,22845,22846,22847,22848,22849,22850,22851,22852,22853,22854,22855,22856,22857,22858,22859,22860,22861,22862,22863,22864,22865,22866,22867,22868,22869,22870,22871,22872,22873,22874,22875,22876,22877,22878,22879,22880,22881,22882,22883,22884,22885,22886,22887,22888,22889,22890,22891,22892,22893,22894,22895,22896,22897,22898,22899,22900,22901,22902,22903,22904,22905,22906,22907,22908,22909,22910,22911,22912,22913,22914,22915,22916,22917,22918,22919,22920,22921,22922,22923,22924,22925,22926,22927,22928,22929,22930,22931,22932,22933,22934,22935,22936,22937,22938,22939,22940,22941,22942,22943,22944,22945,22946,22947,22948,22949,22950,22951,22952,22953,22954,22955,22956,22957,22958,22959,22960,22961,22962,22963,22964,22965,22966,22967,22968,22969,22970,22971,22972,22973,22974,22975,22976,22977,22978,22979,22980,22981,22982,22983,22984,22985,22986,22987,22988,22989,22990,22991,22992,22993,22994,22995,22996,22997,22998,22999,23000,23001,23002,23003,23004,23005,23006,23007,23008,23009,23010,23011,23012,23013,23014,23015,23016,23017,23018,23019,23020,23021,23022,23023,23024,23025,23026,23027,23028,23029,23030,23031,23032,23033,23034,23035,23036,23037,23038,23039,23040,23041,23042,23043,23044,23045,23046,23047,23048,23049,23050,23051,23052,23053,23054,23055,23056,23057,23058,23059,23060,23061,23062,23063,23064,23065,23066,23067,23068,23069,23070,23071,23072,23073,23074,23075,23076,23077,23078,23079,23080,23081,23082,23083,23084,23085,23086,23087,23088,23089,23090,23091,23092,23093,23094,23095,23096,23097,23098,23099,23100,23101,23102,23103,23104,23105,23106,23107,23108,23109,23110,23111,23112,23113,23114,23115,23116,23117,23118,23119,23120,23121,23122,23123,23124,23125,23126,23127,23128,23129,23130,23131,23132,23133,23134,23135,23136,23137,23138,23139,23140,23141,23142,23143,23144,23145,23146,23147,23148,23149,23150,23151,23152,23153,23154,23155,23156,23157,23158,23159,23160,23161,23162,23163,23164,23165,23166,23167,23168,23169,23170,23171,23172,23173,23174,23175,23176,23177,23178,23179,23180,23181,23182,23183,23184,23185,23186,23187,23188,23189,23190,23191,23192,23193,23194,23195,23196,23197,23198,23199,23200,23201,23202,23203,23204,23205,23206,23207,23208,23209,23210,23211,23212,23213,23214,23215,23216,23217,23218,23219,23220,23221,23222,23223,23224,23225,23226,23227,23228,23229,23230,23231,23232,23233,23234,23235,23236,23237,23238,23239,23240,23241,23242,23243,23244,23245,23246,23247,23248,23249,23250,23251,23252,23253,23254,23255,23256,23257,23258,23259,23260,23261,23262,23263,23264,23265,23266,23267,23268,23269,23270,23271,23272,23273,23274,23275,23276,23277,23278,23279,23280,23281,23282,23283,23284,23285,23286,23287,23288,23289,23290,23291,23292,23293,23294,23295,23296,23297,23298,23299,23300,23301,23302,23303,23304,23305,23306,23307,23308,23309,23310,23311,23312,23313,23314,23315,23316,23317,23318,23319,23320,23321,23322,23323,23324,23325,23326,23327,23328,23329,23330,23331,23332,23333,23334,23335,23336,23337,23338,23339,23340,23341,23342,23343,23344,23345,23346,23347,23348,23349,23350,23351,23352,23353,23354,23355,23356,23357,23358,23359,23360,23361,23362,23363,23364,23365,23366,23367,23368,23369,23370,23371,23372,23373,23374,23375,23376,23377,23378,23379,23380,23381,23382,23383,23384,23385,23386,23387,23388,23389,23390,23391,23392,23393,23394,23395,23396,23397,23398,23399,23400,23401,23402,23403,23404,23405,23406,23407,23408,23409,23410,23411,23412,23413,23414,23415,23416,23417,23418,23419,23420,23421,23422,23423,23424,23425,23426,23427,23428,23429,23430,23431,23432,23433,23434,23435,23436,23437,23438,23439,23440,23441,23442,23443,23444,23445,23446,23447,23448,23449,23450,23451,23452,23453,23454,23455,23456,23457,23458,23459,23460,23461,23462,23463,23464,23465,23466,23467,23468,23469,23470,23471,23472,23473,23474,23475,23476,23477,23478,23479,23480,23481,23482,23483,23484,23485,23486,23487,23488,23489,23490,23491,23492,23493,23494,23495,23496,23497,23498,23499,23500,23501,23502,23503,23504,23505,23506,23507,23508,23509,23510,23511,23512,23513,23514,23515,23516,23517,23518,23519,23520,23521,23522,23523,23524,23525,23526,23527,23528,23529,23530,23531,23532,23533,23534,23535,23536,23537,23538,23539,23540,23541,23542,23543,23544,23545,23546,23547,23548,23549,23550,23551,23552,23553,23554,23555,23556,23557,23558,23559,23560,23561,23562,23563,23564,23565,23566,23567,23568,23569,23570,23571,23572,23573,23574,23575,23576,23577,23578,23579,23580,23581,23582,23583,23584,23585,23586,23587,23588,23589,23590,23591,23592,23593,23594,23595,23596,23597,23598,23599,23600,23601,23602,23603,23604,23605,23606,23607,23608,23609,23610,23611,23612,23613,23614,23615,23616,23617,23618,23619,23620,23621,23622,23623,23624,23625,23626,23627,23628,23629,23630,23631,23632,23633,23634,23635,23636,23637,23638,23639,23640,23641,23642,23643,23644,23645,23646,23647,23648,23649,23650,23651,23652,23653,23654,23655,23656,23657,23658,23659,23660,23661,23662,23663,23664,23665,23666,23667,23668,23669,23670,23671,23672,23673,23674,23675,23676,23677,23678,23679,23680,23681,23682,23683,23684,23685,23686,23687,23688,23689,23690,23691,23692,23693,23694,23695,23696,23697,23698,23699,23700,23701,23702,23703,23704,23705,23706,23707,23708,23709,23710,23711,23712,23713,23714,23715,23716,23717,23718,23719,23720,23721,23722,23723,23724,23725,23726,23727,23728,23729,23730,23731,23732,23733,23734,23735,23736,23737,23738,23739,23740,23741,23742,23743,23744,23745,23746,23747,23748,23749,23750,23751,23752,23753,23754,23755,23756,23757,23758,23759,23760,23761,23762,23763,23764,23765,23766,23767,23768,23769,23770,23771,23772,23773,23774,23775,23776,23777,23778,23779,23780,23781,23782,23783,23784,23785,23786,23787,23788,23789,23790,23791,23792,23793,23794,23795,23796,23797,23798,23799,23800,23801,23802,23803,23804,23805,23806,23807,23808,23809,23810,23811,23812,23813,23814,23815,23816,23817,23818,23819,23820,23821,23822,23823,23824,23825,23826,23827,23828,23829,23830,23831,23832,23833,23834,23835,23836,23837,23838,23839,23840,23841,23842,23843,23844,23845,23846,23847,23848,23849,23850,23851,23852,23853,23854,23855,23856,23857,23858,23859,23860,23861,23862,23863,23864,23865,23866,23867,23868,23869,23870,23871,23872,23873,23874,23875,23876,23877,23878,23879,23880,23881,23882,23883,23884,23885,23886,23887,23888,23889,23890,23891,23892,23893,23894,23895,23896,23897,23898,23899,23900,23901,23902,23903,23904,23905,23906,23907,23908,23909,23910,23911,23912,23913,23914,23915,23916,23917,23918,23919,23920,23921,23922,23923,23924,23925,23926,23927,23928,23929,23930,23931,23932,23933,23934,23935,23936,23937,23938,23939,23940,23941,23942,23943,23944,23945,23946,23947,23948,23949,23950,23951,23952,23953,23954,23955,23956,23957,23958,23959,23960,23961,23962,23963,23964,23965,23966,23967,23968,23969,23970,23971,23972,23973,23974,23975,23976,23977,23978,23979,23980,23981,23982,23983,23984,23985,23986,23987,23988,23989,23990,23991,23992,23993,23994,23995,23996,23997,23998,23999,24000,24001,24002,24003,24004,24005,24006,24007,24008,24009,24010,24011,24012,24013,24014,24015,24016,24017,24018,24019,24020,24021,24022,24023,24024,24025,24026,24027,24028,24029,24030,24031,24032,24033,24034,24035,24036,24037,24038,24039,24040,24041,24042,24043,24044,24045,24046,24047,24048,24049,24050,24051,24052,24053,24054,24055,24056,24057,24058,24059,24060,24061,24062,24063,24064,24065,24066,24067,24068,24069,24070,24071,24072,24073,24074,24075,24076,24077,24078,24079,24080,24081,24082,24083,24084,24085,24086,24087,24088,24089,24090,24091,24092,24093,24094,24095,24096,24097,24098,24099,24100,24101,24102,24103,24104,24105,24106,24107,24108,24109,24110,24111,24112,24113,24114,24115,24116,24117,24118,24119,24120,24121,24122,24123,24124,24125,24126,24127,24128,24129,24130,24131,24132,24133,24134,24135,24136,24137,24138,24139,24140,24141,24142,24143,24144,24145,24146,24147,24148,24149,24150,24151,24152,24153,24154,24155,24156,24157,24158,24159,24160,24161,24162,24163,24164,24165,24166,24167,24168,24169,24170,24171,24172,24173,24174,24175,24176,24177,24178,24179,24180,24181,24182,24183,24184,24185,24186,24187,24188,24189,24190,24191,24192,24193,24194,24195,24196,24197,24198,24199,24200,24201,24202,24203,24204,24205,24206,24207,24208,24209,24210,24211,24212,24213,24214,24215,24216,24217,24218,24219,24220,24221,24222,24223,24224,24225,24226,24227,24228,24229,24230,24231,24232,24233,24234,24235,24236,24237,24238,24239,24240,24241,24242,24243,24244,24245,24246,24247,24248,24249,24250,24251,24252,24253,24254,24255,24256,24257,24258,24259,24260,24261,24262,24263,24264,24265,24266,24267,24268,24269,24270,24271,24272,24273,24274,24275,24276,24277,24278,24279,24280,24281,24282,24283,24284,24285,24286,24287,24288,24289,24290,24291,24292,24293,24294,24295,24296,24297,24298,24299,24300,24301,24302,24303,24304,24305,24306,24307,24308,24309,24310,24311,24312,24313,24314,24315,24316,24317,24318,24319,24320,24321,24322,24323,24324,24325,24326,24327,24328,24329,24330,24331,24332,24333,24334,24335,24336,24337,24338,24339,24340,24341,24342,24343,24344,24345,24346,24347,24348,24349,24350,24351,24352,24353,24354,24355,24356,24357,24358,24359,24360,24361,24362,24363,24364,24365,24366,24367,24368,24369,24370,24371,24372,24373,24374,24375,24376,24377,24378,24379,24380,24381,24382,24383,24384,24385,24386,24387,24388,24389,24390,24391,24392,24393,24394,24395,24396,24397,24398,24399,24400,24401,24402,24403,24404,24405,24406,24407,24408,24409,24410,24411,24412,24413,24414,24415,24416,24417,24418,24419,24420,24421,24422,24423,24424,24425,24426,24427,24428,24429,24430,24431,24432,24433,24434,24435,24436,24437,24438,24439,24440,24441,24442,24443,24444,24445,24446,24447,24448,24449,24450,24451,24452,24453,24454,24455,24456,24457,24458,24459,24460,24461,24462,24463,24464,24465,24466,24467,24468,24469,24470,24471,24472,24473,24474,24475,24476,24477,24478,24479,24480,24481,24482,24483,24484,24485,24486,24487,24488,24489,24490,24491,24492,24493,24494,24495,24496,24497,24498,24499,24500,24501,24502,24503,24504,24505,24506,24507,24508,24509,24510,24511,24512,24513,24514,24515,24516,24517,24518,24519,24520,24521,24522,24523,24524,24525,24526,24527,24528,24529,24530,24531,24532,24533,24534,24535,24536,24537,24538,24539,24540,24541,24542,24543,24544,24545,24546,24547,24548,24549,24550,24551,24552,24553,24554,24555,24556,24557,24558,24559,24560,24561,24562,24563,24564,24565,24566,24567,24568,24569,24570,24571,24572,24573,24574,24575,24576,24577,24578,24579,24580,24581,24582,24583,24584,24585,24586,24587,24588,24589,24590,24591,24592,24593,24594,24595,24596,24597,24598,24599,24600,24601,24602,24603,24604,24605,24606,24607,24608,24609,24610,24611,24612,24613,24614,24615,24616,24617,24618,24619,24620,24621,24622,24623,24624,24625,24626,24627,24628,24629,24630,24631,24632,24633,24634,24635,24636,24637,24638,24639,24640,24641,24642,24643,24644,24645,24646,24647,24648,24649,24650,24651,24652,24653,24654,24655,24656,24657,24658,24659,24660,24661,24662,24663,24664,24665,24666,24667,24668,24669,24670,24671,24672,24673,24674,24675,24676,24677,24678,24679,24680,24681,24682,24683,24684,24685,24686,24687,24688,24689,24690,24691,24692,24693,24694,24695,24696,24697,24698,24699,24700,24701,24702,24703,24704,24705,24706,24707,24708,24709,24710,24711,24712,24713,24714,24715,24716,24717,24718,24719,24720,24721,24722,24723,24724,24725,24726,24727,24728,24729,24730,24731,24732,24733,24734,24735,24736,24737,24738,24739,24740,24741,24742,24743,24744,24745,24746],"yaxis":"y","type":"scattergl"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Feet above ground (in thousands)","font":{"family":"Arial","size":18,"color":"#EE4266"}},"tickfont":{"family":"sans-serif","size":20,"color":"#B7C9F2"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"BirdStrikes","font":{"family":"Arial","size":18,"color":"#EE4266"}}},"coloraxis":{"colorbar":{"title":{"text":"Feet above ground"}},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]},"legend":{"tracegroupgap":0,"title":{"font":{"color":"rgba(1, 1, 50, 222)"}},"borderwidth":10,"bgcolor":"#FFDB00"},"title":{"text":"Altitude of aeroplanes at the time of strike.","font":{"color":"#F9F5F6"}},"height":500,"margin":{"l":50,"r":50,"b":100,"t":100,"pad":4},"font":{"color":"#F5DAD2","size":15},"hoverlabel":{"grouptitlefont":{"color":"#FF8F00"}},"width":1000,"paper_bgcolor":"#1A2130","plot_bgcolor":"rgba(255, 255,255, 200)"},                        {"responsive": true}                    ).then(function(){
                            
var gd = document.getElementById('23475b21-cd69-47b8-9815-9deb828a3919');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script> </div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=5100ea53-45b0-4bae-bd65-3328655707b4">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Key Insights :- In above chart we found that mostly birdstrikes occur during altitude(feet above ground) of flight between 0 to 5k (thousands) feet.number of feet increasing threre are less chances of birdstrike.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=35303799-ce43-40c8-aaa8-014e6f1268f7">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F-Altitude-bin-of-aeroplanes-at-the-time-of-strike">● Altitude bin of aeroplanes at the time of strike<a class="anchor-link" href="#%E2%97%8F-Altitude-bin-of-aeroplanes-at-the-time-of-strike">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=29b9bde6-f059-47d1-8b4c-798d20901b0e">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [45]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Count the altitude bin</span>
<span class="n">Altitude</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Altitude bin'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>

<span class="c1"># Get Altitude &lt; 1000 ft and Calculate percentage from all strikes</span>
<span class="n">less_1000ft</span> <span class="o">=</span> <span class="p">(</span><span class="n">Altitude</span><span class="p">[</span><span class="s1">'&lt; 1000 ft'</span><span class="p">]</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Altitude bin'</span><span class="p">])</span><span class="o">*</span><span class="mi">100</span><span class="p">)</span><span class="o">.</span><span class="n">round</span><span class="p">(</span><span class="mi">2</span><span class="p">)</span>
<span class="n">great_1000ft</span> <span class="o">=</span> <span class="p">(</span><span class="n">Altitude</span><span class="p">[</span><span class="s1">'&gt; 1000 ft'</span><span class="p">]</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Altitude bin'</span><span class="p">])</span><span class="o">*</span><span class="mi">100</span><span class="p">)</span><span class="o">.</span><span class="n">round</span><span class="p">(</span><span class="mi">2</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">'when Altitude bin &lt; 1000 ft birdstrikes percentaege:- '</span><span class="p">,</span><span class="nb">str</span><span class="p">(</span><span class="n">less_1000ft</span><span class="p">)</span><span class="o">+</span><span class="s1">' %'</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">'when Altitude bin &gt; 1000 ft birdstrikes percentaege:- '</span><span class="p">,</span><span class="nb">str</span><span class="p">(</span><span class="n">great_1000ft</span><span class="p">)</span><span class="o">+</span><span class="s1">' %'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>when Altitude bin &lt; 1000 ft birdstrikes percentaege:-  80.72 %
when Altitude bin &gt; 1000 ft birdstrikes percentaege:-  19.28 %
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=6ec0d7e5-c0e3-40f8-9d5b-509664be30c7">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Key Insights:- above we can clearly see that approx 80.76 % birdstrikes occur when altitude in &lt;1000 ft and 19.24 % strikes on &gt; 1000 ft.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=ae4d3887-d83e-40fb-ab3e-02503cd06e82">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F-Phase-of-flight-at-the-time-of-the-strike.">● Phase of flight at the time of the strike.<a class="anchor-link" href="#%E2%97%8F-Phase-of-flight-at-the-time-of-the-strike.">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=37c0afb8-5f75-427a-82b3-ed7581b03042">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [46]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">phase_count</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'When: Phase of flight'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=1e93eabd-af7b-4f45-a7dc-2fd08f105103">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [47]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">"Strikes on different phases:-"</span><span class="p">,</span><span class="n">phase_count</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Strikes on different phases:- When: Phase of flight
Approach        10151
Landing Roll     4946
Take-off run     4560
Climb            4247
Descent           763
Taxi               71
Parked              9
Name: count, dtype: int64
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=d086cc96-e74f-44b6-8af5-0a846bd45d0b">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [48]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">phase_flight</span> <span class="o">=</span> <span class="n">phase_count</span><span class="o">.</span><span class="n">to_dict</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=cd8534ad-3f4a-47a7-8a10-0cc203e3bbfb">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [49]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># use Year_dict keys and values in dict. Top10US</span>
<span class="n">Phase</span> <span class="o">=</span><span class="p">{</span><span class="s1">'phase'</span><span class="p">:</span><span class="n">phase_flight</span><span class="o">.</span><span class="n">keys</span><span class="p">(),</span><span class="s1">'BirdStrikes'</span><span class="p">:</span><span class="n">phase_flight</span><span class="o">.</span><span class="n">values</span><span class="p">()}</span>

<span class="c1"># Create bar chart with Plotly Express</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">Phase</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">'phase'</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">'BirdStrikes'</span><span class="p">,</span> <span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span> <span class="n">title</span><span class="o">=</span><span class="s1">'Phase of flight at the time of the strike.'</span><span class="p">,</span> <span class="n">text</span><span class="o">=</span><span class="s1">'BirdStrikes'</span><span class="p">)</span>

<span class="c1"># URL of a image</span>
<span class="n">image_url</span> <span class="o">=</span> <span class="s1">'https://images.pexels.com/photos/912050/pexels-photo-912050.jpeg?auto=compress&amp;cs=tinysrgb&amp;w=1260&amp;h=750&amp;dpr=1'</span>


<span class="c1"># set color to all markers</span>
<span class="n">colors</span> <span class="o">=</span> <span class="p">[</span><span class="s1">'#FF5580'</span><span class="p">]</span> <span class="o">*</span> <span class="nb">len</span><span class="p">(</span><span class="n">Phase</span><span class="p">[</span><span class="s1">'phase'</span><span class="p">])</span>


<span class="c1"># Add image as background</span>
<span class="n">fig</span><span class="o">.</span><span class="n">add_layout_image</span><span class="p">(</span>
    <span class="nb">dict</span><span class="p">(</span>
        <span class="n">source</span><span class="o">=</span><span class="n">image_url</span><span class="p">,</span>
        <span class="n">xref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">yref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">x</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
        <span class="n">y</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizex</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>  <span class="c1"># Adjust width</span>
        <span class="n">sizey</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span>  <span class="c1"># Adjust height</span>
        <span class="n">sizing</span><span class="o">=</span><span class="s2">"stretch"</span><span class="p">,</span>
        <span class="n">opacity</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span>
        <span class="n">layer</span><span class="o">=</span><span class="s2">"below"</span>   <span class="p">))</span>


<span class="c1"># Update outer layout</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span><span class="n">width</span><span class="o">=</span><span class="mi">1000</span><span class="p">,</span>
    <span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span><span class="n">legend_borderwidth</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span><span class="n">margin</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">l</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span>
        <span class="n">r</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span>
        <span class="n">b</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">t</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">pad</span><span class="o">=</span><span class="mi">4</span>
    <span class="p">),</span><span class="n">font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'#F5DAD2'</span><span class="p">),</span><span class="n">paper_bgcolor</span> <span class="o">=</span> <span class="s1">'#1A2130'</span><span class="p">,</span><span class="n">legend_bgcolor</span><span class="o">=</span><span class="s1">'#FFDB00'</span><span class="p">,</span><span class="n">title_font_color</span><span class="o">=</span><span class="s2">"#F9F5F6"</span><span class="p">,</span><span class="n">plot_bgcolor</span> <span class="o">=</span> <span class="s1">'rgba(0, 0,100, 200)'</span><span class="p">,</span><span class="n">legend_title_font_color</span><span class="o">=</span><span class="s1">'rgba(1, 1, 50, 222)'</span><span class="p">,</span><span class="n">hoverlabel_grouptitlefont_color</span><span class="o">=</span><span class="s1">'#FF8F00'</span>
                  <span class="p">,</span><span class="n">font_size</span><span class="o">=</span><span class="mi">15</span><span class="p">)</span>






<span class="c1"># Update layout to ensure the image covers the full background</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span>
    <span class="n">template</span><span class="o">=</span><span class="s2">"plotly_white"</span><span class="p">,</span>
    <span class="n">images</span><span class="o">=</span><span class="p">[</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">source</span><span class="o">=</span><span class="n">image_url</span><span class="p">,</span>
        <span class="n">xref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">yref</span><span class="o">=</span><span class="s2">"paper"</span><span class="p">,</span>
        <span class="n">x</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
        <span class="n">y</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizex</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
        <span class="n">sizey</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span>
        <span class="n">sizing</span><span class="o">=</span><span class="s2">"stretch"</span><span class="p">,</span>
        <span class="n">opacity</span><span class="o">=</span><span class="mf">0.4</span><span class="p">,</span>
        <span class="n">layer</span><span class="o">=</span><span class="s2">"below"</span>
    <span class="p">)],</span>
    <span class="n">margin</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">l</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">r</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">t</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span> <span class="n">b</span><span class="o">=</span><span class="mi">5</span><span class="p">)</span>  <span class="p">)</span>

<span class="c1"># Update text</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_traces</span><span class="p">(</span><span class="n">textfont_size</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span> <span class="n">textangle</span> <span class="o">=</span> <span class="mi">0</span><span class="p">,</span> <span class="n">marker</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">line</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s2">"#FFBF00"</span><span class="p">,</span> <span class="n">width</span><span class="o">=</span><span class="mi">1</span><span class="p">)),</span><span class="n">textposition</span><span class="o">=</span><span class="s1">'outside'</span><span class="p">,</span><span class="n">cliponaxis</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span><span class="n">textfont</span><span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'#FFF67E'</span><span class="p">),</span><span class="n">marker_color</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">marker_line_width</span><span class="o">=</span><span class="mi">2</span><span class="p">)</span>

<span class="c1"># Show chart</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_xaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"phase"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#FFC700"</span><span class="p">),</span><span class="n">tickfont</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">family</span><span class="o">=</span><span class="s2">"sans-serif"</span><span class="p">,</span>
        <span class="n">size</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span>
        <span class="n">color</span><span class="o">=</span><span class="s2">"white"</span>  <span class="p">,</span>
    <span class="c1"># Change the color of the x-axis category labels</span>
    <span class="p">))</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_yaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"BirdStrikes (in thousands)"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#FFC700"</span> <span class="p">))</span>


<span class="n">fig</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output" data-mime-type="text/html" tabindex="0">
<div> <div class="plotly-graph-div" id="33a76bb7-3dd8-4938-bc0d-ba1311545efa" style="height:500px; width:1000px;"></div> <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("33a76bb7-3dd8-4938-bc0d-ba1311545efa")) {                    Plotly.newPlot(                        "33a76bb7-3dd8-4938-bc0d-ba1311545efa",                        [{"alignmentgroup":"True","hovertemplate":"phase=%{x}<br>BirdStrikes=%{text}<extra></extra>","legendgroup":"","marker":{"color":["#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580","#FF5580"],"pattern":{"shape":""},"line":{"color":"#FFBF00","width":2}},"name":"","offsetgroup":"","orientation":"v","showlegend":false,"text":[10151.0,4946.0,4560.0,4247.0,763.0,71.0,9.0],"textposition":"outside","x":["Approach","Landing Roll","Take-off run","Climb","Descent","Taxi","Parked"],"xaxis":"x","y":[10151,4946,4560,4247,763,71,9],"yaxis":"y","type":"bar","textfont":{"color":"#FFF67E","size":12},"cliponaxis":false,"textangle":0}],                        {"template":{"data":{"barpolar":[{"marker":{"line":{"color":"white","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"white","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"#C8D4E3","linecolor":"#C8D4E3","minorgridcolor":"#C8D4E3","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"#C8D4E3","linecolor":"#C8D4E3","minorgridcolor":"#C8D4E3","startlinecolor":"#2a3f5f"},"type":"carpet"}],"choropleth":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"choropleth"}],"contourcarpet":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"contourcarpet"}],"contour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"contour"}],"heatmapgl":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmapgl"}],"heatmap":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmap"}],"histogram2dcontour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2dcontour"}],"histogram2d":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2d"}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"mesh3d":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"mesh3d"}],"parcoords":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"parcoords"}],"pie":[{"automargin":true,"type":"pie"}],"scatter3d":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatter3d"}],"scattercarpet":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattercarpet"}],"scattergeo":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergeo"}],"scattergl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergl"}],"scattermapbox":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattermapbox"}],"scatterpolargl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolargl"}],"scatterpolar":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolar"}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"scatterternary":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterternary"}],"surface":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"surface"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}]},"layout":{"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"autotypenumbers":"strict","coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]],"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]},"colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"geo":{"bgcolor":"white","lakecolor":"white","landcolor":"white","showlakes":true,"showland":true,"subunitcolor":"#C8D4E3"},"hoverlabel":{"align":"left"},"hovermode":"closest","mapbox":{"style":"light"},"paper_bgcolor":"white","plot_bgcolor":"white","polar":{"angularaxis":{"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":""},"bgcolor":"white","radialaxis":{"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":""}},"scene":{"xaxis":{"backgroundcolor":"white","gridcolor":"#DFE8F3","gridwidth":2,"linecolor":"#EBF0F8","showbackground":true,"ticks":"","zerolinecolor":"#EBF0F8"},"yaxis":{"backgroundcolor":"white","gridcolor":"#DFE8F3","gridwidth":2,"linecolor":"#EBF0F8","showbackground":true,"ticks":"","zerolinecolor":"#EBF0F8"},"zaxis":{"backgroundcolor":"white","gridcolor":"#DFE8F3","gridwidth":2,"linecolor":"#EBF0F8","showbackground":true,"ticks":"","zerolinecolor":"#EBF0F8"}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"ternary":{"aaxis":{"gridcolor":"#DFE8F3","linecolor":"#A2B1C6","ticks":""},"baxis":{"gridcolor":"#DFE8F3","linecolor":"#A2B1C6","ticks":""},"bgcolor":"white","caxis":{"gridcolor":"#DFE8F3","linecolor":"#A2B1C6","ticks":""}},"title":{"x":0.05},"xaxis":{"automargin":true,"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":"","title":{"standoff":15},"zerolinecolor":"#EBF0F8","zerolinewidth":2},"yaxis":{"automargin":true,"gridcolor":"#EBF0F8","linecolor":"#EBF0F8","ticks":"","title":{"standoff":15},"zerolinecolor":"#EBF0F8","zerolinewidth":2}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"phase","font":{"family":"Arial","size":18,"color":"#FFC700"}},"tickfont":{"family":"sans-serif","size":12,"color":"white"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"BirdStrikes (in thousands)","font":{"family":"Arial","size":18,"color":"#FFC700"}}},"legend":{"tracegroupgap":0,"title":{"font":{"color":"rgba(1, 1, 50, 222)"}},"borderwidth":10,"bgcolor":"#FFDB00"},"title":{"text":"Phase of flight at the time of the strike.","font":{"color":"#F9F5F6"}},"barmode":"relative","height":500,"images":[{"layer":"below","opacity":0.4,"sizex":1,"sizey":2,"sizing":"stretch","source":"https://images.pexels.com/photos/912050/pexels-photo-912050.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1","x":0,"xref":"paper","y":1,"yref":"paper"}],"margin":{"l":10,"r":0,"b":5,"t":50,"pad":4},"font":{"color":"#F5DAD2","size":15},"hoverlabel":{"grouptitlefont":{"color":"#FF8F00"}},"width":1000,"paper_bgcolor":"#1A2130","plot_bgcolor":"rgba(0, 0,100, 200)"},                        {"responsive": true}                    ).then(function(){
                            
var gd = document.getElementById('33a76bb7-3dd8-4938-bc0d-ba1311545efa');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script> </div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=1f78ab78-a399-4af3-82c2-de737b90e115">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Key Insights:- In Approach phase of flight  10205 birdstrikes occur compare to other phases.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=60a337a0-8c1a-47d8-ace1-5e0cf3269da0">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F-Average-Altitude-of-the-aeroplanes-in-different-phases-at-the-time-of-strike">● Average Altitude of the aeroplanes in different phases at the time of strike<a class="anchor-link" href="#%E2%97%8F-Average-Altitude-of-the-aeroplanes-in-different-phases-at-the-time-of-strike">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=4eacc6d2-e89b-47e5-95c7-62a2b66198a3">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [50]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Compute the average altitude in diifer. phases</span>
<span class="k">for</span> <span class="n">phase</span> <span class="ow">in</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'When: Phase of flight'</span><span class="p">]</span><span class="o">.</span><span class="n">unique</span><span class="p">():</span>

    <span class="c1"># Compute the mean of column Feet above ground (altitude) for the flight phase</span>
    <span class="n">altitude_phase</span> <span class="o">=</span> <span class="n">BirdStrike</span><span class="p">[</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'When: Phase of flight'</span><span class="p">]</span><span class="o">==</span><span class="n">phase</span><span class="p">][</span><span class="s1">'Feet above ground'</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>

    <span class="c1"># print the avg. altitude in differ. phase</span>
    <span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s1">'in </span><span class="si">{</span><span class="n">phase</span><span class="o">.</span><span class="n">upper</span><span class="p">()</span><span class="si">}</span><span class="s1"> phase Average Altitude of the aeroplanes :- '</span><span class="p">,</span><span class="nb">int</span><span class="p">(</span><span class="n">altitude_phase</span><span class="p">))</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>in CLIMB phase Average Altitude of the aeroplanes :-  1204
in LANDING ROLL phase Average Altitude of the aeroplanes :-  0
in APPROACH phase Average Altitude of the aeroplanes :-  1004
in TAKE-OFF RUN phase Average Altitude of the aeroplanes :-  0
in DESCENT phase Average Altitude of the aeroplanes :-  5924
in TAXI phase Average Altitude of the aeroplanes :-  0
in PARKED phase Average Altitude of the aeroplanes :-  0
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=e0a9177b-85f7-4306-a04a-1afcf6191279">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F-Effect-of-Bird-Strikes-&amp;-Impact-on-Flight">● Effect of Bird Strikes &amp; Impact on Flight<a class="anchor-link" href="#%E2%97%8F-Effect-of-Bird-Strikes-&amp;-Impact-on-Flight">¶</a></h1>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=fb165839-4b69-428c-b379-ada3d70aa877">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Average economical loss due to birdstrikes</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=39717e7f-e256-4764-ab3f-c8fb45ed0663">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [51]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">"Average economical loss from year 2000-2011 due to birdstrikes effects:- "</span><span class="p">,(</span><span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">YearCost</span><span class="p">[</span><span class="s1">'cost'</span><span class="p">])</span><span class="o">/</span><span class="mi">1000000</span><span class="p">)</span><span class="o">.</span><span class="n">round</span><span class="p">(</span><span class="mi">2</span><span class="p">),</span><span class="s2">"million $"</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Average economical loss from year 2000-2011 due to birdstrikes effects:-  11.31 million $
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=08c5436c-15dc-4266-9222-66d0fe301dfd">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="People-injured-due-to-birdstrikes">People injured due to birdstrikes<a class="anchor-link" href="#People-injured-due-to-birdstrikes">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=735bce53-1839-4f67-9005-c4df6c72ce92">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [52]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">"people injured due to birdstrikes:- "</span><span class="p">,</span><span class="n">BirdStrike</span><span class="p">[</span><span class="n">BirdStrike</span><span class="p">[</span><span class="s1">'Number of people injured'</span><span class="p">]</span><span class="o">!=</span><span class="mi">0</span><span class="p">][</span><span class="s1">'Number of people injured'</span><span class="p">]</span><span class="o">.</span><span class="n">sum</span><span class="p">())</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>people injured due to birdstrikes:-  21
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=651cfa73-544e-4362-82c6-2ab86913c090">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="Impact-on-Flight">Impact on Flight<a class="anchor-link" href="#Impact-on-Flight">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=a4e36494-9168-4b4e-9d4f-e3ce6a93c108">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [53]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># BirdStrikeOrg.dropna()[,'',Effect: Impact to flight']</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=9c000ade-9985-4835-955f-d2ff9c244039">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [54]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">Effect_in_flight</span> <span class="o">=</span> <span class="n">BirdStrikeOrg</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=cfe82cb4-5e24-401a-9ebe-a81babf74522">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [106]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">"due to birdstrikes most chances of impact:-"</span><span class="p">)</span>     
<span class="c1"># Calcualte the percentage chances of possible imapact on flight due to bird strikes</span>
<span class="k">for</span> <span class="p">(</span><span class="n">k</span><span class="p">,</span><span class="n">v</span><span class="p">)</span> <span class="ow">in</span> <span class="n">Effect_in_flight</span><span class="p">[</span><span class="s1">'Effect: Impact to flight'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">to_dict</span><span class="p">()</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>


            <span class="nb">print</span><span class="p">(</span><span class="n">k</span><span class="p">,(</span><span class="n">v</span><span class="o">/</span><span class="p">(</span><span class="n">Effect_in_flight</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">values</span><span class="o">.</span><span class="n">sum</span><span class="p">())</span><span class="o">*</span><span class="mi">100</span><span class="p">)</span><span class="o">.</span><span class="n">round</span><span class="p">(</span><span class="mi">2</span><span class="p">),</span><span class="s2">" %"</span><span class="p">)</span>
    
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>due to birdstrikes most chances of impact:-
Precautionary Landing 43.33  %
Aborted Take-off 29.44  %
Other 22.22  %
Engine Shut Down 5.0  %
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=2a4eb7f8-a37d-4bfd-a84e-43e0deb2a7f5">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Key Insights :- in above analysis we can clearly see that birdstrikes on flight can impact on financially and physically.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=499b8c82-8a53-4f9f-86c8-f277baa81fc8">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F-Effect-of-Strike-at-Different-Altitude">● Effect of Strike at Different Altitude<a class="anchor-link" href="#%E2%97%8F-Effect-of-Strike-at-Different-Altitude">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=111bd21f-b116-442a-834b-1255cec85878">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span> 
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=0d565273-a0fa-454a-b92a-8c7278d350fa">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [56]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">Effect_in_flight</span> <span class="o">=</span> <span class="n">Effect_in_flight</span><span class="p">[[</span><span class="s1">'Effect: Impact to flight'</span><span class="p">,</span><span class="s1">'Cost: Total $'</span><span class="p">,</span><span class="s1">'Feet above ground'</span><span class="p">,</span><span class="s1">'Effect: Indicated Damage'</span><span class="p">]]</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span> <span class="o">=</span> <span class="s1">'Feet above ground'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=f90e22cd-7243-45b4-9b3f-a08c2fc90b1b">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [57]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Change Data type with replace , character</span>
<span class="n">Effect_in_flight</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">]</span> <span class="o">=</span> <span class="n">Effect_in_flight</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">str</span><span class="p">)</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s2">","</span><span class="p">,</span><span class="s2">""</span><span class="p">)</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=7b309d9f-3285-48f0-a1e0-352b104d82ce">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span> 
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=12530b39-8172-4d9b-be46-81d38767cf0d">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [58]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Create a dictionary for visualization of data</span>
<span class="n">Altitude</span> <span class="o">=</span><span class="p">{</span><span class="s1">'Feet above ground'</span><span class="p">:</span><span class="n">Effect_in_flight</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">],</span><span class="s1">'BirdStrike'</span><span class="p">:[</span><span class="n">i</span> <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">Effect_in_flight</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">]))]</span> <span class="p">}</span>

<span class="c1"># Create bar chart with Plotly Express</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">Altitude</span><span class="p">,</span><span class="n">height</span><span class="o">=</span><span class="mi">600</span><span class="p">,</span><span class="n">x</span><span class="o">=</span><span class="s1">'Feet above ground'</span><span class="p">,</span><span class="n">y</span><span class="o">=</span><span class="s1">'BirdStrike'</span><span class="p">,</span><span class="n">color</span> <span class="o">=</span> <span class="n">Effect_in_flight</span><span class="p">[</span><span class="s1">'Effect: Impact to flight'</span><span class="p">],</span><span class="n">title</span><span class="o">=</span><span class="s1">'Impact to flight at different Altitude'</span><span class="p">)</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_xaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"Feet above ground (in thousands)"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#EE4266"</span><span class="p">),</span><span class="n">tickfont</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">family</span><span class="o">=</span><span class="s2">"sans-serif"</span><span class="p">,</span>
        <span class="n">size</span><span class="o">=</span><span class="mi">20</span><span class="p">,</span>
        <span class="n">color</span><span class="o">=</span><span class="s2">"#B7C9F2"</span><span class="p">,</span>
    <span class="c1"># Change the color of the x-axis category labels</span>
    <span class="p">))</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_yaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"BirdStrikes"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#EE4266"</span> <span class="p">))</span>



<span class="c1"># Update outer layout</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span><span class="n">legend</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">title</span><span class="o">=</span><span class="s2">"Impact to flight"</span><span class="p">,</span>
        <span class="n">font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
            <span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span>
            <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span>
            <span class="n">color</span><span class="o">=</span><span class="s2">"black"</span>
        <span class="p">),</span>
        <span class="n">bgcolor</span><span class="o">=</span><span class="s2">"LightSteelBlue"</span><span class="p">,</span>
        <span class="n">bordercolor</span><span class="o">=</span><span class="s2">"white"</span><span class="p">,</span>
        <span class="n">borderwidth</span><span class="o">=</span><span class="mi">2</span>
    <span class="p">),</span><span class="n">width</span><span class="o">=</span><span class="mi">1000</span><span class="p">,</span>
    <span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span><span class="n">legend_borderwidth</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span><span class="n">margin</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">l</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">r</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span>
        <span class="n">b</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">t</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">pad</span><span class="o">=</span><span class="mi">4</span>
    <span class="p">),</span><span class="n">font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'#F5DAD2'</span><span class="p">),</span><span class="n">paper_bgcolor</span> <span class="o">=</span> <span class="s1">'#1A2130'</span><span class="p">,</span><span class="n">legend_bgcolor</span><span class="o">=</span><span class="s1">'#F3F7EC'</span><span class="p">,</span><span class="n">title_font_color</span><span class="o">=</span><span class="s2">"#F9F5F6"</span><span class="p">,</span><span class="n">plot_bgcolor</span> <span class="o">=</span> <span class="s1">'rgba(255, 255,255, 200)'</span><span class="p">,</span><span class="n">legend_title_font_color</span><span class="o">=</span><span class="s1">'rgba(100,0, 200, 200)'</span><span class="p">,</span><span class="n">hoverlabel_grouptitlefont_color</span><span class="o">=</span><span class="s1">'#1A2130'</span>
                  <span class="p">,</span><span class="n">font_size</span><span class="o">=</span><span class="mi">15</span><span class="p">)</span>


<span class="n">fig</span><span class="o">.</span><span class="n">update_traces</span><span class="p">(</span><span class="n">marker</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">size</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span>
                              <span class="n">line</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">width</span> <span class="o">=</span> <span class="mi">2</span><span class="p">,</span>
                                        <span class="n">color</span> <span class="o">=</span> <span class="s1">'DarkSlateGrey'</span><span class="p">)),</span>
                  <span class="n">selector</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">mode</span><span class="o">=</span><span class="s1">'markers'</span><span class="p">))</span>
<span class="n">fig</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output" data-mime-type="text/html" tabindex="0">
<div> <div class="plotly-graph-div" id="8d316487-33f6-408e-a7da-8a638981a295" style="height:500px; width:1000px;"></div> <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("8d316487-33f6-408e-a7da-8a638981a295")) {                    Plotly.newPlot(                        "8d316487-33f6-408e-a7da-8a638981a295",                        [{"hovertemplate":"color=Aborted Take-off<br>Feet above ground=%{x}<br>BirdStrike=%{y}<extra></extra>","legendgroup":"Aborted Take-off","marker":{"color":"#636efa","symbol":"circle","line":{"color":"DarkSlateGrey","width":2},"size":12},"mode":"markers","name":"Aborted Take-off","orientation":"v","showlegend":true,"x":[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],"xaxis":"x","y":[0,1,3,5,6,7,8,9,10,11,17,18,22,25,26,27,28,29,30,32,35,36,37,39,41,44,48,51,52,53,55,56,58,60,61,63,65,66,67,70,71,75,76,79,82,83,85,87,88,92,93,94,96],"yaxis":"y","type":"scatter"},{"hovertemplate":"color=Precautionary Landing<br>Feet above ground=%{x}<br>BirdStrike=%{y}<extra></extra>","legendgroup":"Precautionary Landing","marker":{"color":"#EF553B","symbol":"circle","line":{"color":"DarkSlateGrey","width":2},"size":12},"mode":"markers","name":"Precautionary Landing","orientation":"v","showlegend":true,"x":[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1000,1000,1000,1100,1200,1300,1500,1500,1500,1800,10,10,10,10,10,100,100,100,150,2500,20,200,200,200,200,200,250,3,30,30,30,300,300,300,300,40,400,400,400,400,5,5500,50,50,50,50,500,500,500,500,600,700,700,75,8000,800,800,800],"xaxis":"x","y":[2,12,16,23,34,40,46,47,57,59,64,69,72,73,74,77,84,86,89,98,100,101,102,103,104,105,107,109,110,111,112,113,114,115,116,118,121,122,124,126,129,130,131,133,134,135,138,139,142,143,144,146,147,148,150,151,152,153,154,155,156,160,162,163,164,166,167,168,169,170,171,173,174,175,176,177,178,179],"yaxis":"y","type":"scatter"},{"hovertemplate":"color=Engine Shut Down<br>Feet above ground=%{x}<br>BirdStrike=%{y}<extra></extra>","legendgroup":"Engine Shut Down","marker":{"color":"#00cc96","symbol":"circle","line":{"color":"DarkSlateGrey","width":2},"size":12},"mode":"markers","name":"Engine Shut Down","orientation":"v","showlegend":true,"x":[0,0,0,0,0,0,0,1300,200],"xaxis":"x","y":[4,43,50,54,62,78,90,106,136],"yaxis":"y","type":"scatter"},{"hovertemplate":"color=Other<br>Feet above ground=%{x}<br>BirdStrike=%{y}<extra></extra>","legendgroup":"Other","marker":{"color":"#ab63fa","symbol":"circle","line":{"color":"DarkSlateGrey","width":2},"size":12},"mode":"markers","name":"Other","orientation":"v","showlegend":true,"x":[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1000,1500,100,100,100,100,2000,2500,20,200,25,3000,30,30,300,5,5,5,5500,50,63],"xaxis":"x","y":[13,14,15,19,20,21,24,31,33,38,42,45,49,68,80,81,91,95,97,99,108,117,119,120,123,125,127,128,132,137,140,141,145,149,157,158,159,161,165,172],"yaxis":"y","type":"scatter"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Feet above ground (in thousands)","font":{"family":"Arial","size":18,"color":"#EE4266"}},"tickfont":{"family":"sans-serif","size":20,"color":"#B7C9F2"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"BirdStrikes","font":{"family":"Arial","size":18,"color":"#EE4266"}}},"legend":{"title":{"text":"Impact to flight","font":{"color":"rgba(100,0, 200, 200)"}},"tracegroupgap":0,"font":{"family":"Arial","size":18,"color":"black"},"bgcolor":"#F3F7EC","bordercolor":"white","borderwidth":2},"title":{"text":"Impact to flight at different Altitude","font":{"color":"#F9F5F6"}},"height":500,"margin":{"l":100,"r":50,"b":100,"t":100,"pad":4},"font":{"color":"#F5DAD2","size":15},"hoverlabel":{"grouptitlefont":{"color":"#1A2130"}},"width":1000,"paper_bgcolor":"#1A2130","plot_bgcolor":"rgba(255, 255,255, 200)"},                        {"responsive": true}                    ).then(function(){
                            
var gd = document.getElementById('8d316487-33f6-408e-a7da-8a638981a295');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script> </div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=5cfb2aaf-5fc5-4942-8ef7-9498d5018b8e">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [59]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">BirdStrike</span><span class="o">.</span><span class="n">columns</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[59]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>Index(['Record ID', 'Aircraft: Type', 'Airport: Name', 'Altitude bin',
       'Aircraft: Make/Model', 'Wildlife: Number struck',
       'Wildlife: Number Struck Actual', 'FlightDate',
       'Effect: Indicated Damage', 'Aircraft: Number of engines?',
       'Aircraft: Airline/Operator', 'Origin State', 'When: Phase of flight',
       'Remains of wildlife collected?',
       'Remains of wildlife sent to Smithsonian', 'Wildlife: Size',
       'Conditions: Sky', 'Wildlife: Species',
       'Pilot warned of birds or wildlife?', 'Cost: Total $',
       'Feet above ground', 'Number of people injured', 'Is Aircraft Large?',
       'year', 'month', 'year_month'],
      dtype='object')</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=c5fd031c-69ba-46ea-b5eb-54a62b1afbe8">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Key Insights:- above chart we have found that on altitude 0 most birdstrikes occur and there are more impact to flight compare to other altitude.</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=c697a250-0b36-427a-ba72-6a3207ec40e0">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [60]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Create a dictionary for visualization of data</span>
<span class="n">Altitude</span> <span class="o">=</span><span class="p">{</span><span class="s1">'Feet above ground'</span><span class="p">:</span><span class="n">Effect_in_flight</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">],</span><span class="s1">'BirdStrike'</span><span class="p">:[</span><span class="n">i</span> <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">Effect_in_flight</span><span class="p">[</span><span class="s1">'Feet above ground'</span><span class="p">]))]</span> <span class="p">}</span>

<span class="c1"># Create bar chart with Plotly Express</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">Effect_in_flight</span><span class="p">[[</span><span class="s1">'Feet above ground'</span><span class="p">,</span><span class="s1">'Cost: Total $'</span><span class="p">]],</span><span class="n">height</span><span class="o">=</span><span class="mi">600</span><span class="p">,</span><span class="n">x</span><span class="o">=</span><span class="s1">'Feet above ground'</span><span class="p">,</span><span class="n">y</span><span class="o">=</span>  <span class="s1">'Cost: Total $'</span><span class="p">,</span><span class="n">title</span><span class="o">=</span><span class="s1">'Impact to cost at different Altitude'</span><span class="p">)</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_xaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"Feet above ground (in thousands)"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#EE4266"</span><span class="p">),</span><span class="n">tickfont</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">family</span><span class="o">=</span><span class="s2">"sans-serif"</span><span class="p">,</span>
        <span class="n">size</span><span class="o">=</span><span class="mi">20</span><span class="p">,</span>
        <span class="n">color</span><span class="o">=</span><span class="s2">"#B7C9F2"</span><span class="p">,</span>
    <span class="c1"># Change the color of the x-axis category labels</span>
    <span class="p">))</span>


<span class="c1"># Update the layout to change the font of the x-axis label</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_yaxes</span><span class="p">(</span><span class="n">title_text</span><span class="o">=</span><span class="s2">"Cost (in $)"</span><span class="p">,</span> <span class="n">title_font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"#EE4266"</span> <span class="p">))</span>



<span class="c1"># Update outer layout</span>
<span class="n">fig</span><span class="o">.</span><span class="n">update_layout</span><span class="p">(</span><span class="n">legend</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">title</span><span class="o">=</span><span class="s2">"Impact to flight"</span><span class="p">,</span>
        <span class="n">font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
            <span class="n">family</span><span class="o">=</span><span class="s2">"Arial"</span><span class="p">,</span>
            <span class="n">size</span><span class="o">=</span><span class="mi">18</span><span class="p">,</span>
            <span class="n">color</span><span class="o">=</span><span class="s2">"black"</span>
        <span class="p">),</span>
        <span class="n">bgcolor</span><span class="o">=</span><span class="s2">"LightSteelBlue"</span><span class="p">,</span>
        <span class="n">bordercolor</span><span class="o">=</span><span class="s2">"white"</span><span class="p">,</span>
        <span class="n">borderwidth</span><span class="o">=</span><span class="mi">2</span>
    <span class="p">),</span><span class="n">width</span><span class="o">=</span><span class="mi">1000</span><span class="p">,</span>
    <span class="n">height</span><span class="o">=</span><span class="mi">500</span><span class="p">,</span><span class="n">legend_borderwidth</span><span class="o">=</span><span class="mi">2</span><span class="p">,</span><span class="n">margin</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span>
        <span class="n">l</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">r</span><span class="o">=</span><span class="mi">50</span><span class="p">,</span>
        <span class="n">b</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">t</span><span class="o">=</span><span class="mi">100</span><span class="p">,</span>
        <span class="n">pad</span><span class="o">=</span><span class="mi">4</span>
    <span class="p">),</span><span class="n">font</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="s1">'#F5DAD2'</span><span class="p">),</span><span class="n">paper_bgcolor</span> <span class="o">=</span> <span class="s1">'#1A2130'</span><span class="p">,</span><span class="n">legend_bgcolor</span><span class="o">=</span><span class="s1">'#F3F7EC'</span><span class="p">,</span><span class="n">title_font_color</span><span class="o">=</span><span class="s2">"#F9F5F6"</span><span class="p">,</span><span class="n">plot_bgcolor</span> <span class="o">=</span> <span class="s1">'rgba(255, 255,255, 200)'</span><span class="p">,</span><span class="n">legend_title_font_color</span><span class="o">=</span><span class="s1">'rgba(100,0, 200, 200)'</span><span class="p">,</span><span class="n">hoverlabel_grouptitlefont_color</span><span class="o">=</span><span class="s1">'#1A2130'</span>
                  <span class="p">,</span><span class="n">font_size</span><span class="o">=</span><span class="mi">15</span><span class="p">)</span>


<span class="n">fig</span><span class="o">.</span><span class="n">update_traces</span><span class="p">(</span><span class="n">marker</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">size</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span>
                              <span class="n">line</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">width</span> <span class="o">=</span> <span class="mi">2</span><span class="p">,</span>
                                        <span class="n">color</span> <span class="o">=</span> <span class="s1">'DarkSlateGrey'</span><span class="p">)),</span>
                  <span class="n">selector</span><span class="o">=</span><span class="nb">dict</span><span class="p">(</span><span class="n">mode</span><span class="o">=</span><span class="s1">'markers'</span><span class="p">))</span>
<span class="n">fig</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output" data-mime-type="text/html" tabindex="0">
<div> <div class="plotly-graph-div" id="1a1afa5d-3ecd-4fd6-9326-25020563e876" style="height:500px; width:1000px;"></div> <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("1a1afa5d-3ecd-4fd6-9326-25020563e876")) {                    Plotly.newPlot(                        "1a1afa5d-3ecd-4fd6-9326-25020563e876",                        [{"hovertemplate":"Feet above ground=%{x}<br>Cost: Total $=%{y}<extra></extra>","legendgroup":"","marker":{"color":"#636efa","symbol":"circle","line":{"color":"DarkSlateGrey","width":2},"size":12},"mode":"markers","name":"","orientation":"h","showlegend":false,"x":[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1000,1000,1000,1000,1100,1200,1300,1300,1500,1500,1500,1500,1800,10,10,10,10,10,100,100,100,100,100,100,100,150,2000,2500,2500,20,20,200,200,200,200,200,200,200,25,250,3,3000,30,30,30,30,30,300,300,300,300,300,40,400,400,400,400,5,5,5,5,5500,5500,50,50,50,50,50,500,500,500,500,600,63,700,700,75,8000,800,800,800],"xaxis":"x","y":["0","0","0","0","0","31,693","0","1,901,610","0","0","0","0","0","0","0","1,540","0","0","0","0","0","433,367","0","0","0","0","190","0","0","0","0","0","0","0","0","0","0","0","24,053","0","0","0","318,699","151,010","0","3,879","16,236","0","0","0","108,229","44,906","0","0","3,006,592","0","0","0","0","0","0","0","2,977,459","1,482","0","0","0","0","0","0","0","300,000","0","0","4,329","0","0","0","0","21,646","0","0","0","0","0","0","0","0","0","0","0","51,950","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","0","1,082","0","0","0","0","0","34,226","0","0","0","0","0","0","0","0","0","30,066","0","0","666,719","0","0","0","0","0","27,057","0","0","10,223","0","112,255","0","0","0","0","0","0","0","0","0","0","0","15,812","24,053","848,578","0","7,885","0","0","0","0","0","2,840","0","0","0","0","0","3,247","0","0","0","0"],"yaxis":"y","type":"scatter"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Feet above ground (in thousands)","font":{"family":"Arial","size":18,"color":"#EE4266"}},"tickfont":{"family":"sans-serif","size":20,"color":"#B7C9F2"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"Cost (in $)","font":{"family":"Arial","size":18,"color":"#EE4266"}}},"legend":{"tracegroupgap":0,"font":{"family":"Arial","size":18,"color":"black"},"title":{"text":"Impact to flight","font":{"color":"rgba(100,0, 200, 200)"}},"bgcolor":"#F3F7EC","bordercolor":"white","borderwidth":2},"title":{"text":"Impact to cost at different Altitude","font":{"color":"#F9F5F6"}},"height":500,"margin":{"l":100,"r":50,"b":100,"t":100,"pad":4},"font":{"color":"#F5DAD2","size":15},"hoverlabel":{"grouptitlefont":{"color":"#1A2130"}},"width":1000,"paper_bgcolor":"#1A2130","plot_bgcolor":"rgba(255, 255,255, 200)"},                        {"responsive": true}                    ).then(function(){
                            
var gd = document.getElementById('1a1afa5d-3ecd-4fd6-9326-25020563e876');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script> </div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=af66f892-421c-4862-944b-2f0c3e4ff1d2">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Key Insights:- In above result we found that on between altitude 0-2000 too high cost due to bird strike effects.</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=99d98a2c-ef94-43c9-96c1-63dd3869e7a8">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [ ]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span> 
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=8e672f9e-029e-4f98-905a-f228aef1e904">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="%E2%97%8F-Were-Pilots-Informed?-&amp;-Prior-Warning-and-Effect-of-Strike-Relation">● Were Pilots Informed? &amp; Prior Warning and Effect of Strike Relation<a class="anchor-link" href="#%E2%97%8F-Were-Pilots-Informed?-&amp;-Prior-Warning-and-Effect-of-Strike-Relation">¶</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=891e3c64-266f-4dc7-b4f7-96d120331c4e">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [61]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">pilot_inform</span> <span class="o">=</span> <span class="n">BirdStrikeOrg</span><span class="p">[[</span><span class="s1">'Effect: Impact to flight'</span><span class="p">,</span><span class="s1">'Pilot warned of birds or wildlife?'</span><span class="p">,</span><span class="s1">'Cost: Total $'</span><span class="p">,</span><span class="s1">'Effect: Indicated Damage'</span><span class="p">]]</span><span class="o">.</span><span class="n">dropna</span><span class="p">()</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=f2043bdf-2ee3-44e9-9bb8-9852ff5410d5">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [62]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Check for pilots informed/warned or not</span>
<span class="n">pilot_inform</span><span class="p">[</span><span class="s1">'Cost: Total $'</span><span class="p">]</span> <span class="o">=</span> <span class="n">pilot_inform</span><span class="p">[</span><span class="s1">'Cost: Total $'</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">str</span><span class="p">)</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s2">","</span><span class="p">,</span><span class="s2">""</span><span class="p">)</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=d458215d-4be2-42d7-b678-c8da3f25aa40">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [63]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">cost_y</span> <span class="o">=</span> <span class="n">pilot_inform</span><span class="p">[</span><span class="n">pilot_inform</span><span class="p">[</span><span class="s1">'Pilot warned of birds or wildlife?'</span><span class="p">]</span><span class="o">==</span><span class="s1">'Y'</span><span class="p">][</span><span class="s1">'Cost: Total $'</span><span class="p">]</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span><span class="o">/</span><span class="mi">1000000</span>

<span class="nb">print</span><span class="p">(</span><span class="s2">"cost when pilot informed:- "</span><span class="p">,</span><span class="n">cost_y</span><span class="p">,</span><span class="s2">"Million $"</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>cost when pilot informed:-  47.210472 Million $
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=4ff95bae-fc64-4820-9e48-2478fde3e195">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [64]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">cost_n</span> <span class="o">=</span> <span class="n">pilot_inform</span><span class="p">[</span><span class="n">pilot_inform</span><span class="p">[</span><span class="s1">'Pilot warned of birds or wildlife?'</span><span class="p">]</span><span class="o">==</span><span class="s1">'N'</span><span class="p">][</span><span class="s1">'Cost: Total $'</span><span class="p">]</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span><span class="o">/</span><span class="mi">1000000</span>

<span class="nb">print</span><span class="p">(</span><span class="s2">"cost when pilot not informed:- "</span><span class="p">,</span><span class="n">cost_n</span><span class="p">,</span><span class="s2">"Million $"</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>cost when pilot not informed:-  59.121748 Million $
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=b0e6d4bb-35df-4403-ba91-7ba9275729a0">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [65]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">flight_damage_y</span> <span class="o">=</span> <span class="n">pilot_inform</span><span class="p">[</span><span class="n">pilot_inform</span><span class="p">[</span><span class="s1">'Pilot warned of birds or wildlife?'</span><span class="p">]</span><span class="o">==</span><span class="s1">'Y'</span><span class="p">][</span><span class="s1">'Effect: Indicated Damage'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"damage indicated when pilot informed:_"</span><span class="p">,</span><span class="n">flight_damage_y</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>damage indicated when pilot informed:_ Effect: Indicated Damage
No damage        516
Caused damage    393
Name: count, dtype: int64
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=e7a3091d-b0ca-46bc-9166-6a9e86d4012f">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [66]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">flight_damage_n</span> <span class="o">=</span> <span class="n">pilot_inform</span><span class="p">[</span><span class="n">pilot_inform</span><span class="p">[</span><span class="s1">'Pilot warned of birds or wildlife?'</span><span class="p">]</span><span class="o">==</span><span class="s1">'N'</span><span class="p">][</span><span class="s1">'Effect: Indicated Damage'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>

<span class="nb">print</span><span class="p">(</span><span class="s2">"damage indicated when pilot not informed:_"</span><span class="p">,</span><span class="n">flight_damage_n</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>damage indicated when pilot not informed:_ Effect: Indicated Damage
No damage        651
Caused damage    518
Name: count, dtype: int64
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=5fff0f93-74ce-4f19-8f95-2212dbb720e4">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [67]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">impact_flight_y</span> <span class="o">=</span> <span class="n">pilot_inform</span><span class="p">[</span><span class="n">pilot_inform</span><span class="p">[</span><span class="s1">'Pilot warned of birds or wildlife?'</span><span class="p">]</span><span class="o">==</span><span class="s1">'Y'</span><span class="p">][</span><span class="s1">'Effect: Impact to flight'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>


<span class="nb">print</span><span class="p">(</span><span class="s2">"Impact to flight when pilot informed:- "</span><span class="p">,</span><span class="n">impact_flight_y</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Impact to flight when pilot informed:-  Effect: Impact to flight
Precautionary Landing    502
Aborted Take-off         229
Other                    142
Engine Shut Down          36
Name: count, dtype: int64
</pre>
</div>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=a7a14764-8daf-4103-83fa-bd50d4e335be">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [68]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">impact_flight_n</span> <span class="o">=</span> <span class="n">pilot_inform</span><span class="p">[</span><span class="n">pilot_inform</span><span class="p">[</span><span class="s1">'Pilot warned of birds or wildlife?'</span><span class="p">]</span><span class="o">==</span><span class="s1">'N'</span><span class="p">][</span><span class="s1">'Effect: Impact to flight'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"Impact to flight when pilot not informed:- "</span><span class="p">,</span><span class="n">impact_flight_n</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>Impact to flight when pilot not informed:-  Effect: Impact to flight
Precautionary Landing    619
Aborted Take-off         250
Other                    248
Engine Shut Down          52
Name: count, dtype: int64
</pre>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=d79c0cfb-4574-4bed-a096-f7028e8fd972">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>Key Insights:- In Above result of analysis we found that birdstrikes impact on cost ,flight damage,and other damage can be decreasable by prior waring to pilot about the strike.in cost effect we have found there around 12 million loss of cost has decreased,on 100 birdstriks there are no damage.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=09ab6cdc-ca89-4c76-b44c-9e2bd08ed1db">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h2 id="%3E%3EProject-Summary">&gt;&gt;Project Summary<a class="anchor-link" href="#%3E%3EProject-Summary">¶</a></h2>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=b44db992-0ace-4bbd-8763-269b498dd0f2">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>In overall analysis we haave found mostly birdstrikes occur between altitude 0-1000 above to ground.we also describe the all cases we have analyze in past process.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=4f9191e1-8df0-4a3b-af6b-01f6894b003a">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1 id="Conclusion:-">Conclusion:-<a class="anchor-link" href="#Conclusion:-">¶</a></h1>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=831b6397-0126-4c91-8362-1b4bef7bff64">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p>If pilot prior warned about the birdstrike event we can decrease the cost and impact due to birdstrikes,there are seasonal changes in birdstrikes in winter season we found number of birdstrikes go down.</p>
</div>
</div>
</div>
</div>
</main>
</body>
</html>
