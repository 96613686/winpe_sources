# AllocateAndExpandExclusionList(ushort const *,ulong,ushort const *,ulong,ushort * *,ulong &)

- ea: `0x1800098c4`
- end: `0x18000999f`
- name: `?AllocateAndExpandExclusionList@@YAJPEBGK0KPEAPEAGAEAK@Z`
- size: `219`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a200`

## callees

- `0x1800098c4`
- `0x1800099a8`
- `0x18001992c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009929`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009929`

## string_xrefs

- `0x180009909`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180009984`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

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
0x1800098c4  push    rbx
0x1800098c6  push    rbp
0x1800098c7  push    rsi
0x1800098c8  push    rdi
0x1800098c9  push    r14
0x1800098cb  push    r15
0x1800098cd  sub     rsp, 38h
0x1800098d1  mov     rdi, [rsp+68h+arg_28]
0x1800098d9  mov     esi, r9d
0x1800098dc  mov     [rsp+68h+var_40], rdi; unsigned int *
0x1800098e1  mov     rbp, r8
0x1800098e4  mov     r14d, edx
0x1800098e7  mov     [rsp+68h+var_48], 0; int
0x1800098f0  mov     r15, rcx
0x1800098f3  mov     dword ptr [rdi], 0
0x1800098f9  call    ?ExpandPaths@@YAJPEBGK0KPEAGAEAK@Z; ExpandPaths(ushort const *,ulong,ushort const *,ulong,ushort *,ulong &)
0x1800098fe  mov     ebx, eax
0x180009900  test    eax, eax
0x180009902  jns     short loc_18000991F
0x180009904  mov     rcx, [rsp+68h]; this
0x180009909  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180009910  mov     r9d, eax; char *
0x180009913  mov     edx, 9EAh; void *
0x180009918  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000991d  jmp     short loc_180009944
0x18000991f  mov     edx, [rdi]
0x180009921  mov     ecx, 40h ; '@'; uFlags
0x180009926  add     rdx, rdx; uBytes
0x180009929  call    cs:__imp_LocalAlloc
0x18000992f  mov     rcx, [rsp+68h+arg_20]
0x180009937  mov     [rcx], rax
0x18000993a  test    rax, rax
0x18000993d  jnz     short loc_18000994E
0x18000993f  mov     ebx, 8007000Eh
0x180009944  mov     r9d, ebx
0x180009947  mov     edx, 9F8h
0x18000994c  jmp     short loc_18000997F
0x18000994e  mov     rcx, rax
0x180009951  mov     [rsp+68h+var_40], rdi; unsigned int *
0x180009956  xor     eax, eax
0x180009958  mov     [rsp+68h+var_48], rcx; int
0x18000995d  mov     r9d, esi; unsigned int
0x180009960  mov     r8, rbp; unsigned __int16 *
0x180009963  mov     edx, r14d; unsigned int
0x180009966  mov     [rcx], ax
0x180009969  mov     rcx, r15; unsigned __int16 *
0x18000996c  call    ?ExpandPaths@@YAJPEBGK0KPEAGAEAK@Z; ExpandPaths(ushort const *,ulong,ushort const *,ulong,ushort *,ulong &)
0x180009971  mov     ebx, eax
0x180009973  test    eax, eax
0x180009975  jns     short loc_180009990
0x180009977  mov     r9d, eax; char *
0x18000997a  mov     edx, 0A01h; void *
0x18000997f  mov     rcx, [rsp+68h]; this
0x180009984  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000998b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009990  mov     eax, ebx
0x180009992  add     rsp, 38h
0x180009996  pop     r15
0x180009998  pop     r14
0x18000999a  pop     rdi
0x18000999b  pop     rsi
0x18000999c  pop     rbp
0x18000999d  pop     rbx
0x18000999e  retn
```
