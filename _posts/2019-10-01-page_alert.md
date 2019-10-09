---
layout: post
title: "page alert"
categories:
  - Note
tags:
---
# page alert
首頁的check auth/index.blade.php
@if (count($errors) > 0)

- @foreach ($errors->all() as $error)
- {{ $error }}
- @endforeach

@endif
其他頁的popout 要check

