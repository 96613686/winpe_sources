# DeleteProfileDirectory2

- ea: `0x180015670`
- end: `0x1800156ff`
- name: `DeleteProfileDirectory2`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000db08`
- `0x180015420`
- `0x1800154ec`
- `0x180015544`
- `0x180015670`
- `0x18001aa00`

## string_xrefs

- `0x180015697`: `onecore\ds\security\gina\profile\userenv\dll\userenv.cpp`
- `0x1800156c0`: `onecore\ds\security\gina\profile\userenv\dll\userenv.cpp`

## pseudocode

```c
__int64 __fastcall DeleteProfileDirectory2(unsigned __int16 *lpFileName, unsigned int a2, __int64 a3, void *a4)
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
  v6 = wil::impersonate_token_nothrow(a4, (void **)&v12);
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
0x180015670  mov     [rsp+arg_0], rbx
0x180015675  mov     [rsp+arg_8], rsi
0x18001567a  push    rdi; int
0x18001567b  sub     rsp, 20h
0x18001567f  mov     [rsp+28h+arg_18], 0FFFFFFFFFFFFFFFFh
0x180015688  mov     edi, edx
0x18001568a  mov     rsi, rcx
0x18001568d  test    r9, r9
0x180015690  jnz     short loc_1800156A8
0x180015692  mov     rcx, [rsp+28h]; this
0x180015697  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001569e  lea     edx, [r9+4Bh]; void *
0x1800156a2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800156a8  lea     rdx, [rsp+28h+arg_18]
0x1800156ad  mov     rcx, r9; Token
0x1800156b0  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800156b5  mov     ebx, eax
0x1800156b7  test    eax, eax
0x1800156b9  jns     short loc_1800156D6
0x1800156bb  mov     rcx, [rsp+28h]; this
0x1800156c0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800156c7  mov     r9d, eax; char *
0x1800156ca  mov     edx, 4Ch ; 'L'; void *
0x1800156cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800156d4  jmp     short loc_1800156E2
0x1800156d6  mov     edx, edi; unsigned int
0x1800156d8  mov     rcx, rsi; lpFileName
0x1800156db  call    ?DeleteProfileDirectoryInternal@@YAJPEBGK0@Z; DeleteProfileDirectoryInternal(ushort const *,ulong,ushort const *)
0x1800156e0  mov     ebx, eax
0x1800156e2  lea     rcx, [rsp+28h+arg_18]
0x1800156e7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800156ec  mov     rsi, [rsp+28h+arg_8]
0x1800156f1  mov     eax, ebx
0x1800156f3  mov     rbx, [rsp+28h+arg_0]
0x1800156f8  add     rsp, 20h
0x1800156fc  pop     rdi
0x1800156fd  retn
```
