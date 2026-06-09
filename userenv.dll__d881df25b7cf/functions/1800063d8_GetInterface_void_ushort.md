# _GetInterface(void * *,ushort *)

- ea: `0x1800063d8`
- end: `0x1800064c9`
- name: `?_GetInterface@@YAJPEAPEAXPEAG@Z`
- size: `241`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006300`
- `0x180012f10`
- `0x180012fa0`
- `0x180013030`

## callees

- `0x1800063d8`
- `0x180009248`
- `0x18000dae0`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180006412`
- `RPCRT4!RpcStringBindingComposeW` at `0x180006412`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000646e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000646e`
- `RPCRT4!RpcStringFreeW` at `0x180006451`
- `RPCRT4!RpcStringFreeW` at `0x180006492`
- `RPCRT4!RpcStringFreeW` at `0x180006451`
- `RPCRT4!RpcStringFreeW` at `0x180006492`

## string_xrefs

- `0x180006427`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`
- `0x1800064a7`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall _GetInterface(RPC_BINDING_HANDLE *Binding, unsigned __int16 *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  unsigned int v6; // eax
  unsigned int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RPC_WSTR StringBinding; // [rsp+48h] [rbp+10h] BYREF
  RPC_WSTR String; // [rsp+50h] [rbp+18h] BYREF

  StringBinding = 0;
  v3 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"IUserProfile2", 0, &StringBinding);
  if ( v3 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x46,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
           (const char *)v3,
           v7);
    if ( StringBinding )
    {
      String = StringBinding;
      RpcStringFreeW(&String);
    }
    return v4;
  }
  v6 = RpcBindingFromStringBindingW(StringBinding, Binding);
  if ( v6 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x49,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
           (const char *)v6,
           v7);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::RpcStringFreeLocal(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::RpcStringFreeLocal(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringBinding);
    return v4;
  }
  if ( StringBinding )
  {
    String = StringBinding;
    RpcStringFreeW(&String);
  }
  return 0;
}

```

## disassembly

```asm
0x1800063d8  mov     r11, rsp
0x1800063db  mov     [r11+10h], rdx
0x1800063df  push    rbx
0x1800063e0  sub     rsp, 30h
0x1800063e4  lea     rax, [r11+10h]
0x1800063e8  mov     qword ptr [r11+10h], 0
0x1800063f0  mov     rbx, rcx
0x1800063f3  mov     [r11-10h], rax
0x1800063f7  lea     r9, Endpoint; "IUserProfile2"
0x1800063fe  mov     qword ptr [r11-18h], 0
0x180006406  xor     r8d, r8d; NetworkAddr
0x180006409  lea     rdx, ProtSeq; "ncalrpc"
0x180006410  xor     ecx, ecx; ObjUuid
0x180006412  call    cs:__imp_RpcStringBindingComposeW
0x180006419  nop     dword ptr [rax+rax+00h]
0x18000641e  test    eax, eax
0x180006420  jz      short loc_180006466
0x180006422  mov     rcx, [rsp+38h]; this
0x180006427  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000642e  mov     r9d, eax; char *
0x180006431  mov     edx, 46h ; 'F'; void *
0x180006436  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000643b  mov     rcx, [rsp+38h+StringBinding]
0x180006440  mov     ebx, eax
0x180006442  test    rcx, rcx
0x180006445  jz      short loc_18000645D
0x180006447  mov     [rsp+38h+String], rcx
0x18000644c  lea     rcx, [rsp+38h+String]; String
0x180006451  call    cs:__imp_RpcStringFreeW
0x180006458  nop     dword ptr [rax+rax+00h]
0x18000645d  mov     eax, ebx
0x18000645f  add     rsp, 30h
0x180006463  pop     rbx
0x180006464  retn
0x180006466  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x18000646b  mov     rdx, rbx; Binding
0x18000646e  call    cs:__imp_RpcBindingFromStringBindingW
0x180006475  nop     dword ptr [rax+rax+00h]
0x18000647a  test    eax, eax
0x18000647c  jnz     short loc_1800064A2
0x18000647e  mov     rax, [rsp+38h+StringBinding]
0x180006483  test    rax, rax
0x180006486  jz      short loc_18000649E
0x180006488  lea     rcx, [rsp+38h+String]; String
0x18000648d  mov     [rsp+38h+String], rax
0x180006492  call    cs:__imp_RpcStringFreeW
0x180006499  nop     dword ptr [rax+rax+00h]
0x18000649e  xor     eax, eax
0x1800064a0  jmp     short loc_18000645F
0x1800064a2  mov     rcx, [rsp+38h]; this
0x1800064a7  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800064ae  mov     r9d, eax; char *
0x1800064b1  mov     edx, 49h ; 'I'; void *
0x1800064b6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800064bb  lea     rcx, [rsp+38h+StringBinding]
0x1800064c0  mov     ebx, eax
0x1800064c2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?RpcStringFreeLocal@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::RpcStringFreeLocal(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::RpcStringFreeLocal(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800064c7  jmp     short loc_18000645D
```
