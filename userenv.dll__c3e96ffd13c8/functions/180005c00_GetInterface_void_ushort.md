# _GetInterface(void * *,ushort *)

- ea: `0x180005c00`
- end: `0x180005cd8`
- name: `?_GetInterface@@YAJPEAPEAXPEAG@Z`
- size: `216`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005b28`
- `0x180011f4c`
- `0x180011fd8`
- `0x180012064`

## callees

- `0x180005c00`
- `0x1800089e4`
- `0x18000ce7c`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180005c3a`
- `RPCRT4!RpcStringBindingComposeW` at `0x180005c3a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180005c89`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180005c89`
- `RPCRT4!RpcStringFreeW` at `0x180005c73`
- `RPCRT4!RpcStringFreeW` at `0x180005ca7`
- `RPCRT4!RpcStringFreeW` at `0x180005c73`
- `RPCRT4!RpcStringFreeW` at `0x180005ca7`

## string_xrefs

- `0x180005c49`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`
- `0x180005cb6`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

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
0x180005c00  mov     r11, rsp
0x180005c03  mov     [r11+10h], rdx
0x180005c07  push    rbx
0x180005c08  sub     rsp, 30h
0x180005c0c  lea     rax, [r11+10h]
0x180005c10  mov     qword ptr [r11+10h], 0
0x180005c18  mov     rbx, rcx
0x180005c1b  mov     [r11-10h], rax
0x180005c1f  lea     r9, Endpoint; "IUserProfile2"
0x180005c26  mov     qword ptr [r11-18h], 0
0x180005c2e  xor     r8d, r8d; NetworkAddr
0x180005c31  lea     rdx, ProtSeq; "ncalrpc"
0x180005c38  xor     ecx, ecx; ObjUuid
0x180005c3a  call    cs:__imp_RpcStringBindingComposeW
0x180005c40  test    eax, eax
0x180005c42  jz      short loc_180005C81
0x180005c44  mov     rcx, [rsp+38h]; this
0x180005c49  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180005c50  mov     r9d, eax; char *
0x180005c53  mov     edx, 46h ; 'F'; void *
0x180005c58  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180005c5d  mov     rcx, [rsp+38h+StringBinding]
0x180005c62  mov     ebx, eax
0x180005c64  test    rcx, rcx
0x180005c67  jz      short loc_180005C79
0x180005c69  mov     [rsp+38h+String], rcx
0x180005c6e  lea     rcx, [rsp+38h+String]; String
0x180005c73  call    cs:__imp_RpcStringFreeW
0x180005c79  mov     eax, ebx
0x180005c7b  add     rsp, 30h
0x180005c7f  pop     rbx
0x180005c80  retn
0x180005c81  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x180005c86  mov     rdx, rbx; Binding
0x180005c89  call    cs:__imp_RpcBindingFromStringBindingW
0x180005c8f  test    eax, eax
0x180005c91  jnz     short loc_180005CB1
0x180005c93  mov     rax, [rsp+38h+StringBinding]
0x180005c98  test    rax, rax
0x180005c9b  jz      short loc_180005CAD
0x180005c9d  lea     rcx, [rsp+38h+String]; String
0x180005ca2  mov     [rsp+38h+String], rax
0x180005ca7  call    cs:__imp_RpcStringFreeW
0x180005cad  xor     eax, eax
0x180005caf  jmp     short loc_180005C7B
0x180005cb1  mov     rcx, [rsp+38h]; this
0x180005cb6  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180005cbd  mov     r9d, eax; char *
0x180005cc0  mov     edx, 49h ; 'I'; void *
0x180005cc5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180005cca  lea     rcx, [rsp+38h+StringBinding]
0x180005ccf  mov     ebx, eax
0x180005cd1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?RpcStringFreeLocal@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::RpcStringFreeLocal(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::RpcStringFreeLocal(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180005cd6  jmp     short loc_180005C79
```
