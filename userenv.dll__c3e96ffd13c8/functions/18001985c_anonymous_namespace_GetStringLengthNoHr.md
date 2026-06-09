# _anonymous_namespace_::_GetStringLengthNoHr

- ea: `0x18001985c`
- end: `0x1800198a3`
- name: `_anonymous_namespace_::_GetStringLengthNoHr`
- size: `71`
- prototype: `unsigned __int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008798`

## callees

- `0x1800072a0`
- `0x18001985c`
- `0x18001992c`

## string_xrefs

- `0x180019881`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
unsigned __int64 __fastcall anonymous_namespace_::_GetStringLengthNoHr(const unsigned __int16 *a1)
{
  int v1; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v1 = StringCchLengthW(a1, 0x7FFFFFFFu, &v4);
  if ( v1 >= 0 )
    return v4;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xF1,
    (int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    (const char *)(unsigned int)v1);
  return 0;
}

```

## disassembly

```asm
0x18001985c  sub     rsp, 28h
0x180019860  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x180019865  mov     [rsp+28h+arg_8], 0
0x18001986e  mov     edx, 7FFFFFFFh; unsigned __int64
0x180019873  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180019878  test    eax, eax
0x18001987a  jns     short loc_180019899
0x18001987c  mov     rcx, [rsp+28h]; this
0x180019881  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180019888  mov     r9d, eax; char *
0x18001988b  mov     edx, 0F1h; void *
0x180019890  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019895  xor     eax, eax
0x180019897  jmp     short loc_18001989E
0x180019899  mov     rax, [rsp+28h+arg_8]
0x18001989e  add     rsp, 28h
0x1800198a2  retn
```
