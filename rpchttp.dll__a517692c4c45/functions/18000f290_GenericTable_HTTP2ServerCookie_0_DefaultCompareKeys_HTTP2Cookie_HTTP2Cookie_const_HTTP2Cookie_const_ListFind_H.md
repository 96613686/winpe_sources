# GenericTable<HTTP2ServerCookie,0,&DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::ListFind(HTTP2Cookie &)

- ea: `0x18000f290`
- end: `0x18000f2b6`
- name: `?ListFind@?$GenericTable@VHTTP2ServerCookie@@$0A@$1??$DefaultCompareKeys@VHTTP2Cookie@@@@YAHAEBVHTTP2Cookie@@0@Z@@AEAAPEAVHTTP2ServerCookie@@AEAVHTTP2Cookie@@@Z`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007be0`
- `0x180009d0c`
- `0x18000dfe8`
- `0x180016cd8`

## callees

- `0x18000f290`

## pseudocode

```c
_QWORD *__fastcall GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::ListFind(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *result; // rax
  __int64 v3; // r8

  for ( result = (_QWORD *)*a1; result != a1; result = (_QWORD *)*result )
  {
    v3 = result[4] - *a2;
    if ( !v3 )
      v3 = result[5] - a2[1];
    if ( !v3 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f290  mov     rax, [rcx]
0x18000f293  cmp     rax, rcx
0x18000f296  jz      short loc_18000F2B3
0x18000f298  mov     r8, [rax+20h]
0x18000f29c  sub     r8, [rdx]
0x18000f29f  jnz     short loc_18000F2A9
0x18000f2a1  mov     r8, [rax+28h]
0x18000f2a5  sub     r8, [rdx+8]
0x18000f2a9  test    r8, r8
0x18000f2ac  jz      short locret_18000F2B5
0x18000f2ae  mov     rax, [rax]
0x18000f2b1  jmp     short loc_18000F293
0x18000f2b3  xor     eax, eax
0x18000f2b5  retn
```
