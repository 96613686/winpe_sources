# AllocateAndExpandExclusionList(ushort const *,ulong,ushort const *,ulong,ushort * *,ulong &)

- ea: `0x18000a200`
- end: `0x18000a2e2`
- name: `?AllocateAndExpandExclusionList@@YAJPEBGK0KPEAPEAGAEAK@Z`
- size: `226`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ab88`

## callees

- `0x18000a200`
- `0x18000a2e8`
- `0x18001b3b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a265`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a265`

## string_xrefs

- `0x18000a245`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000a2c6`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall AllocateAndExpandExclusionList(
        const unsigned __int16 *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 **a5,
        unsigned int *a6)
{
  int v10; // eax
  unsigned int v11; // ebx
  unsigned __int16 *v12; // rax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  int v17; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a6 = 0;
  v10 = ExpandPaths(a1, a2, a3, a4, 0, a6);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9EA,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)(unsigned int)v10,
      v17);
LABEL_5:
    v13 = v11;
    v14 = 2552;
LABEL_8:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)v13,
      v17);
    return v11;
  }
  v12 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * *a6);
  *a5 = v12;
  if ( !v12 )
  {
    v11 = -2147024882;
    goto LABEL_5;
  }
  *v12 = 0;
  v15 = ExpandPaths(a1, a2, a3, a4, v12, a6);
  v11 = v15;
  if ( v15 < 0 )
  {
    v13 = (unsigned int)v15;
    v14 = 2561;
    goto LABEL_8;
  }
  return v11;
}

```

## disassembly

```asm
0x18000a200  push    rbx
0x18000a202  push    rbp
0x18000a203  push    rsi
0x18000a204  push    rdi
0x18000a205  push    r14
0x18000a207  push    r15
0x18000a209  sub     rsp, 38h
0x18000a20d  mov     rdi, [rsp+68h+arg_28]
0x18000a215  mov     esi, r9d
0x18000a218  mov     [rsp+68h+var_40], rdi; unsigned int *
0x18000a21d  mov     rbp, r8
0x18000a220  mov     r14d, edx
0x18000a223  mov     [rsp+68h+var_48], 0; int
0x18000a22c  mov     r15, rcx
0x18000a22f  mov     dword ptr [rdi], 0
0x18000a235  call    ?ExpandPaths@@YAJPEBGK0KPEAGAEAK@Z; ExpandPaths(ushort const *,ulong,ushort const *,ulong,ushort *,ulong &)
0x18000a23a  mov     ebx, eax
0x18000a23c  test    eax, eax
0x18000a23e  jns     short loc_18000A25B
0x18000a240  mov     rcx, [rsp+68h]; this
0x18000a245  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a24c  mov     r9d, eax; char *
0x18000a24f  mov     edx, 9EAh; void *
0x18000a254  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a259  jmp     short loc_18000A286
0x18000a25b  mov     edx, [rdi]
0x18000a25d  mov     ecx, 40h ; '@'; uFlags
0x18000a262  add     rdx, rdx; uBytes
0x18000a265  call    cs:__imp_LocalAlloc
0x18000a26c  nop     dword ptr [rax+rax+00h]
0x18000a271  mov     rcx, [rsp+68h+arg_20]
0x18000a279  mov     [rcx], rax
0x18000a27c  test    rax, rax
0x18000a27f  jnz     short loc_18000A290
0x18000a281  mov     ebx, 8007000Eh
0x18000a286  mov     r9d, ebx
0x18000a289  mov     edx, 9F8h
0x18000a28e  jmp     short loc_18000A2C1
0x18000a290  mov     rcx, rax
0x18000a293  mov     [rsp+68h+var_40], rdi; unsigned int *
0x18000a298  xor     eax, eax
0x18000a29a  mov     [rsp+68h+var_48], rcx; int
0x18000a29f  mov     r9d, esi; unsigned int
0x18000a2a2  mov     r8, rbp; unsigned __int16 *
0x18000a2a5  mov     edx, r14d; unsigned int
0x18000a2a8  mov     [rcx], ax
0x18000a2ab  mov     rcx, r15; unsigned __int16 *
0x18000a2ae  call    ?ExpandPaths@@YAJPEBGK0KPEAGAEAK@Z; ExpandPaths(ushort const *,ulong,ushort const *,ulong,ushort *,ulong &)
0x18000a2b3  mov     ebx, eax
0x18000a2b5  test    eax, eax
0x18000a2b7  jns     short loc_18000A2D2
0x18000a2b9  mov     r9d, eax; char *
0x18000a2bc  mov     edx, 0A01h; void *
0x18000a2c1  mov     rcx, [rsp+68h]; this
0x18000a2c6  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a2cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a2d2  mov     eax, ebx
0x18000a2d4  add     rsp, 38h
0x18000a2d8  pop     r15
0x18000a2da  pop     r14
0x18000a2dc  pop     rdi
0x18000a2dd  pop     rsi
0x18000a2de  pop     rbp
0x18000a2df  pop     rbx
0x18000a2e0  retn
```
