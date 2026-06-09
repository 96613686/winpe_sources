# _anonymous_namespace_::_GetStringLengthNoHr

- ea: `0x18001b2e4`
- end: `0x18001b32c`
- name: `_anonymous_namespace_::_GetStringLengthNoHr`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008fe4`

## callees

- `0x180007f80`
- `0x18001b2e4`
- `0x18001b3b4`

## string_xrefs

- `0x18001b309`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
unsigned __int64 __fastcall anonymous_namespace_::_GetStringLengthNoHr(const unsigned __int16 *a1)
{
  int v1; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  v1 = StringCchLengthW(a1, 0x7FFFFFFFu, &v5);
  if ( v1 >= 0 )
    return v5;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xF1,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    (const char *)(unsigned int)v1,
    v3);
  return 0;
}

```

## disassembly

```asm
0x18001b2e4  sub     rsp, 28h
0x18001b2e8  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x18001b2ed  mov     [rsp+28h+arg_8], 0
0x18001b2f6  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001b2fb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001b300  test    eax, eax
0x18001b302  jns     short loc_18001B321
0x18001b304  mov     rcx, [rsp+28h]; this
0x18001b309  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001b310  mov     r9d, eax; char *
0x18001b313  mov     edx, 0F1h; void *
0x18001b318  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b31d  xor     eax, eax
0x18001b31f  jmp     short loc_18001B326
0x18001b321  mov     rax, [rsp+28h+arg_8]
0x18001b326  add     rsp, 28h
0x18001b32a  retn
```
