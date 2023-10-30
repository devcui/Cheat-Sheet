# MDN 0X0001 HTML5 CHEAT SHEET

# 1. ELEMENTS

- [`<a>`](#a): creates a hyperlink to web pages.
- [`<abbr>`](#abbr): represents an abbreviation or acronym.
- [`<acronym>`](#acronym): indicate a sequence of characters that compose an acronym or abbreviation for a word.
- [`<address>`](#address)
- [`<area>`](#area)
- [`<article>`](#article)
- [`<aside>`](#aside)
- [`<audio>`](#audio)
- [`<b>`](#b)
- [`<base>`](#base)
- [`<bdi>`](#bdi)
- [`<bdo>`](#bdo)
- [`<big>`](#big)
- [`<blockquote>`](#blockquote)
- [`<body>`](#body)
- [`<br>`](#br)
- [`<button>`](#button)
- [`<canvas>`](#canvas)
- [`<caption>`](#caption)
- [`<center>`](#center)
- [`<cite>`](#cite)
- [`<code>`](#code)
- [`<col>`](#col)
- [`<colgroup>`](#colgroup)
- [`<data>`](#data)
- [`<datalist>`](#datalist)
- [`<dd>`](#dd)
- [`<del>`](#del)
- [`<details>`](#details)
- [`<dfn>`](#dfn)
- [`<dialog>`](#dialog)
- [`<dir>`](#dir)
- [`<div>`](#div)
- [`<dl>`](#dl)
- [`<dt>`](#dt)
- [`<em>`](#em)
- [`<embed>`](#embed)
- [`<fieldset>`](#fieldset)
- [`<figcaption>`](#figcaption)
- [`<figure>`](#figure)
- [`<font>`](#font)
- [`<footer>`](#footer)
- [`<form>`](#form)
- [`<frame>`](#frame)
- [`<frameset>`](#frameset)
- [`<h1>`](#h1)
- [`<head>`](#head)
- [`<header>`](#header)
- [`<hgroup>`](#hgroup)
- [`<hr>`](#hr)
- [`<html>`](#html)
- [`<i>`](#i)
- [`<iframe>`](#iframe)
- [`<image>`](#image)
- [`<img>`](#img)
- [`<input>`](#input)
- [`<ins>`](#ins)
- [`<kbd>`](#kbd)
- [`<label>`](#label)
- [`<legend>`](#legend)
- [`<li>`](#li)
- [`<link>`](#link)
- [`<main>`](#main)
- [`<map>`](#map)
- [`<mark>`](#mark)
- [`<marquee>`](#marquee)
- [`<menu>`](#menu)
- [`<menuitem>`](#menuitem)
- [`<meta>`](#meta)
- [`<meter>`](#meter)
- [`<nav>`](#nav)
- [`<nobr>`](#nobr)
- [`<noembed>`](#noembed)
- [`<noframes>`](#noframes)
- [`<noscript>`](#noscript)
- [`<object>`](#object)
- [`<ol>`](#ol)
- [`<optgroup>`](#optgroup)
- [`<option>`](#option)
- [`<output>`](#output)
- [`<p>`](#p)
- [`<param>`](#param)
- [`<picture>`](#picture)
- [`<plaintext>`](#plaintext)
- [`<portal>`](#portal)
- [`<pre>`](#pre)
- [`<progress>`](#progress)
- [`<q>`](#q)
- [`<rb>`](#rb)
- [`<rp>`](#rp)
- [`<rt>`](#rt)
- [`<rtc>`](#rtc)
- [`<ruby>`](#ruby)
- [`<s>`](#s)
- [`<samp>`](#samp)
- [`<script>`](#script)
- [`<search>`](#search)
- [`<section>`](#section)
- [`<select>`](#select)
- [`<slot>`](#slot)
- [`<small>`](#small)
- [`<source>`](#source)
- [`<span>`](#span)
- [`<strike>`](#strike)
- [`<strong>`](#strong)
- [`<style>`](#style)
- [`<sub>`](#sub)
- [`<summary>`](#summary)
- [`<sup>`](#sup)
- [`<table>`](#table)
- [`<tbody>`](#tbody)
- [`<td>`](#td)
- [`<template>`](#template)
- [`<textarea>`](#textarea)
- [`<tfoot>`](#tfoot)
- [`<th>`](#th)
- [`<thead>`](#thead)
- [`<time>`](#time)
- [`<title>`](#title)
- [`<tr>`](#tr)
- [`<track>`](#track)
- [`<tt>`](#tt)
- [`<u>`](#u)
- [`<ul>`](#ul)
- [`<var>`](#var)
- [`<video>`](#video)
- [`<wbr>`](#wbr)
- [`<xmp>`](#xmp)

## 1.1 ELEMENTS INTRODUCTION

## a

### example

```html
<p>You can reach Michael at:</p>

<ul>
  <!-- link -->
  <li><a href="https://example.com">Website</a></li>
  <!-- mail -->
  <li><a href="mailto:m.bluth@example.com">Email</a></li>
  <!-- phone -->
  <li><a href="tel:+123456789">Phone</a></li>
  <!-- linking to relative urls -->
  <a href="//example.com">Scheme-relative URL</a>
  <a href="/en-US/docs/Web/HTML">Origin-relative URL</a>
  <a href="./p">Directory-relative URL</a>
  <!-- linking to an element on the same page -->
  <!-- <a> element links to the section below -->
  <p><a href="#Section_further_down">Jump to the heading below</a></p>
  <!-- heading to link to -->
  <h2 id="Section_further_down">Section further down</h2>
</ul>
```

### Using the download attribute to save a `<canvas>` as a PNG

```html
<style>
  html {
    font-family: sans-serif;
  }
  canvas {
    background: #fff;
    border: 1px dashed;
  }
  a {
    display: inline-block;
    background: #69c;
    color: #fff;
    padding: 5px 10px;
  }
</style>

<p>
  Paint by holding down the mouse button and moving it.
  <a href="" download="my_painting.png">Download my painting</a>
</p>
<canvas width="300" height="300"></canvas>

<script type="text/javascript">
  const canvas = document.querySelector("canvas");
  const c = canvas.getContext("2d");
  c.fillStyle = "hotpink";
  let isDrawing;

  function draw(x, y) {
    if (isDrawing) {
      c.beginPath();
      c.arc(x, y, 10, 0, Math.PI * 2);
      c.closePath();
      c.fill();
    }
  }

  canvas.addEventListener("mousemove", (event) =>
    draw(event.offsetX, event.offsetY),
  );
  canvas.addEventListener("mousedown", () => (isDrawing = true));
  canvas.addEventListener("mouseup", () => (isDrawing = false));

  document
    .querySelector("a")
    .addEventListener(
      "click",
      (event) => (event.target.href = canvas.toDataURL()),
    );
</script>
```

### link that opens a new tab/window

```html
<a target="_blank" href="https://www.wikipedia.org">
  Wikipedia (opens in new tab)
</a>
```

### link to a non-html resource

```html
<a href="2017-annual-report.ppt">2017 Annual Report (PowerPoint)</a>
```

## abbr

### example

```html
<p>
  You can use <abbr>CSS</abbr> (Cascading Style Sheets) to style your
  <abbr>HTML</abbr> (HyperText Markup Language). Using style sheets, you can
  keep your <abbr>CSS</abbr> presentation layer and <abbr>HTML</abbr> content
  layer separate. This is called "separation of concerns."
</p>
```

### providing an expansion

```html
<p>Ashok's joke made me <abbr title="Laugh Out Loud">LOL</abbr> big time.</p>
```

### defining an abbreviation

```html
<p>
  <dfn id="html"><abbr title="HyperText Markup Language">HTML</abbr> </dfn> is a
  markup language used to create the semantics and structure of a web page.
</p>

<p>
  A <dfn id="spec">Specification</dfn> (<abbr>spec</abbr>) is a document that
  outlines in detail how a technology or API is intended to function and how it
  is accessed.
</p>
```

## acronym

### example

```html
<p>
  The <acronym title="World Wide Web">WWW</acronym> is only a component of the
  Internet.
</p>
```

## address

## area

## article

## aside

## audio

## b

## base

## bdi

## bdo

## big

## blockquote

## body

## br

## button

## canvas

## caption

## center

## cite

## code

## col

## colgroup

## data

## datalist

## dd

## del

## details

## dfn

## dialog

## dir

## div

## dl

## dt

## em

## embed

## fieldset

## figcaption

## figure

## font

## footer

## form

## frame

## frameset

## h1

## head

## header

## hgroup

## hr

## html

## i

## iframe

## image

## img

## input

## ins

## kbd

## label

## legend

## li

## link

## main

## map

## mark

## marquee

## menu

## menuitem

## meta

## meter

## nav

## nobr

## noembed

## noframes

## noscript

## object

## ol

## optgroup

## option

## output

## p

## param

## picture

## plaintext

## portal

## pre

## progress

## q

## rb

## rp

## rt

## rtc

## ruby

## s

## samp

## script

## search

## section

## select

## slot

## small

## source

## span

## strike

## strong

## style

## sub

## summary

## sup

## table

## tbody

## td

## template

## textarea

## tfoot

## th

## thead

## time

## title

## tr

## track

## tt

## u

## ul

## var

## video

## wbr

## xmp

# 2. GLOBAL ATTRIBUTES

- [`accesskey`](#accesskey)
- [`autocapitalize`](#autocapitalize)
- [`autofocus`](#autofocus)
- [`class`](#class)
- [`contenteditable`](#contenteditable)
- [`contextmenu`](#contextmenu)
- [`data-*`](#data)
- [`dir`](#dir)
- [`draggable`](#draggable)
- [`enterkeyhint`](#enterkeyhint)
- [`exportparts`](#exportparts)
- [`hidden`](#hidden)
- [`id`](#id)
- [`inert`](#inert)
- [`inputmode`](#inputmode)
- [`is`](#is)
- [`itemid`](#itemid)
- [`itemprop`](#itemprop)
- [`itemref`](#itemref)
- [`itemscope`](#itemscope)
- [`itemtype`](#itemtype)
- [`lang`](#lang)
- [`nonce`](#nonce)
- [`part`](#part)
- [`popover`](#popover)
- [`slot`](#slot)
- [`spellcheck`](#spellcheck)
- [`style`](#style)
- [`tabindex`](#tabindex)
- [`title`](#title)
- [`translate`](#translate)
- [`virtualkeyboardpolicy`](#virtualkeyboardpolicy)

## 2.1 GLOBAL ATTRIBUTES INTRODUCTION

## accesskey

## autocapitalize

## autofocus

## class

## contenteditable

## contextmenu

## data-\*

## dir

## draggable

## enterkeyhint

## exportparts

## hidden

## id

## inert

## inputmode

## is

## itemid

## itemprop

## itemref

## itemscope

## itemtype

## lang

## nonce

## part

## popover

## slot

## spellcheck

## style

## tabindex

## title

## translate

## virtualkeyboardpolicy

# 3. ATTRIBUTES

- [`accept`](#accept)
- [`autocomplete`](#autocomplete)
- [`capture`](#capture)
- [`crossorigin`](#crossorigin)
- [`dirname`](#dirname)
- [`disabled`](#disabled)
- [`elementtiming`](#elementtiming)
- [`for`](#for)
- [`max`](#max)
- [`maxlength`](#maxlength)
- [`min`](#min)
- [`minlength`](#minlength)
- [`multiple`](#multiple)
- [`pattern`](#pattern)
- [`placeholder`](#placeholder)
- [`readonly`](#readonly)
- [`rel`](#rel)
- [`required`](#required)
- [`size`](#size)
- [`step`](#step)

## 3.1 ATTRIBUTES INTRODUCTION

## accept

## autocomplete

## capture

## crossorigin

## dirname

## disabled

## elementtiming

## for

## max

## maxlength

## min

## minlength

## multiple

## pattern

## placeholder

## readonly

## rel

## required

## size

## step

# 4. INPUT TYPES

- [`<input type="button">`](#input_type_button)
- [`<input type="checkbox">`](#input_type_checkbox)
- [`<input type="color">`](#input_type_color)
- [`<input type="date">`](#input_type_date)
- [`<input type="datetim]e-local">`](#input_type_datetime-local)
- [`<input type="email">`](#input_type_email)
- [`<input type="file">`](#input_type_file)
- [`<input type="hidden">`](#input_type_hidden)
- [`<input type="image">`](#input_type_image)
- [`<input type="month">`](#input_type_month)
- [`<input type="number">`](#input_type_number)
- [`<input type="password">`](#input_type_password)
- [`<input type="radio">`](#input_type_radio)
- [`<input type="range">`](#input_type_range)
- [`<input type="reset">`](#input_type_reset)
- [`<input type="search">`](#input_type_search)
- [`<input type="submit">`](#input_type_submit)
- [`<input type="tel">`](#input_type_tel)
- [`<input type="text">`](#input_type_text)
- [`<input type="time">`](#input_type_time)
- [`<input type="url">`](#input_type_url)
- [`<input type="week">`](#input_type_week)

## 4.1 INPUT TYPES INTRODUCTION

## input_type_button

## input_type_checkbox

## input_type_color

## input_type_date

## input_type_datetime-local

## input_type_email

## input_type_file

## input_type_hidden

## input_type_image

## input_type_month

## input_type_number

## input_type_password

## input_type_radio

## input_type_range

## input_type_reset

## input_type_search

## input_type_submit

## input_type_tel

## input_type_text

## input_type_time

## input_type_url

## input_type_week
