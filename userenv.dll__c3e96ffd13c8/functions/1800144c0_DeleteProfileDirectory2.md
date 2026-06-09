# DeleteProfileDirectory2

- ea: `0x1800144c0`
- end: `0x18001454e`
- name: `DeleteProfileDirectory2`
- size: `142`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, __int64, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000cea0`
- `0x1800142ac`
- `0x180014360`
- `0x1800143b0`
- `0x1800144c0`
- `0x180018ff4`

## string_xrefs

- `0x1800144e7`: `onecore\ds\security\gina\profile\userenv\dll\userenv.cpp`
- `0x180014510`: `onecore\ds\security\gina\profile\userenv\dll\userenv.cpp`

## pseudocode

```c
__int64 __fastcall DeleteProfileDirectory2(LPCWSTR lpFileName, unsigned int a2, __int64 a3, void *a4)
{
  int v6; // eax
  const unsigned __int16 *v7; // r8
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v12; // [rsp+48h] [rbp+20h] BYREF

  v12 = -1;
  if ( !a4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\userenv.cpp",
      0);
  v6 = wil::impersonate_token_nothrow(a4);
  v8 = v6;
  if ( v6 >= 0 )
    v8 = DeleteProfileDirectoryInternal(lpFileName, a2, v7);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\userenv.cpp",
      (const char *)(unsigned int)v6,
      v10);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v12);
  return v8;
}

```

## disassembly

```asm
0x1800144c0  mov     [rsp+arg_0], rbx
0x1800144c5  mov     [rsp+arg_8], rsi
0x1800144ca  push    rdi; int
0x1800144cb  sub     rsp, 20h
0x1800144cf  mov     [rsp+28h+arg_18], 0FFFFFFFFFFFFFFFFh
0x1800144d8  mov     edi, edx
0x1800144da  mov     rsi, rcx
0x1800144dd  test    r9, r9
0x1800144e0  jnz     short loc_1800144F8
0x1800144e2  mov     rcx, [rsp+28h]; this
0x1800144e7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800144ee  lea     edx, [r9+4Bh]; void *
0x1800144f2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800144f8  lea     rdx, [rsp+28h+arg_18]
0x1800144fd  mov     rcx, r9; Token
0x180014500  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x180014505  mov     ebx, eax
0x180014507  test    eax, eax
0x180014509  jns     short loc_180014526
0x18001450b  mov     rcx, [rsp+28h]; this
0x180014510  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\u"...
0x180014517  mov     r9d, eax; char *
0x18001451a  mov     edx, 4Ch ; 'L'; void *
0x18001451f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014524  jmp     short loc_180014532
0x180014526  mov     edx, edi; unsigned int
0x180014528  mov     rcx, rsi; lpFileName
0x18001452b  call    ?DeleteProfileDirectoryInternal@@YAJPEBGK0@Z; DeleteProfileDirectoryInternal(ushort const *,ulong,ushort const *)
0x180014530  mov     ebx, eax
0x180014532  lea     rcx, [rsp+28h+arg_18]
0x180014537  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001453c  mov     rsi, [rsp+28h+arg_8]
0x180014541  mov     eax, ebx
0x180014543  mov     rbx, [rsp+28h+arg_0]
0x180014548  add     rsp, 20h
0x18001454c  pop     rdi
0x18001454d  retn
```
