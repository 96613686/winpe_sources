# _RNvNtCs9MWeMO1rkJG_4core9panicking5panic

- ea: `0x140018630`
- end: `0x140018642`
- name: `_RNvNtCs9MWeMO1rkJG_4core9panicking5panic`
- size: `18`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD, _QWORD)`
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x140003860`
- `0x140004890`
- `0x140004af0`
- `0x140005040`
- `0x14000a950`
- `0x14000a990`
- `0x14000ab50`
- `0x14000b0e0`
- `0x14000b240`
- `0x14000b860`
- `0x14000be40`
- `0x14000c440`
- `0x14000c640`
- `0x14000cc10`
- `0x14000e720`
- `0x14000e9d0`
- `0x14000f6b0`
- `0x14000f800`
- `0x14000fab0`
- `0x14000fba0`
- `0x1400121f0`
- `0x140012380`
- `0x140012690`
- `0x140012770`
- `0x140012a30`
- `0x140013270`
- `0x140013c70`
- `0x140017400`
- `0x140018450`

## callees

- `0x140018650`

## pseudocode

```c
void __fastcall __noreturn RNvNtCs9MWeMO1rkJG_4core9panicking5panic(__int64 a1, __int64 a2, __int64 a3)
{
  RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(a1, 2 * a2 + 1, a3);
}

```

## disassembly

```asm
0x140018630  sub     rsp, 28h
0x140018634  lea     rdx, ds:1[rdx*2]
0x14001863c  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
```
