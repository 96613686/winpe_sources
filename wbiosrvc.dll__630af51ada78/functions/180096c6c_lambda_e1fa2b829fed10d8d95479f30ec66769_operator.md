# _lambda_e1fa2b829fed10d8d95479f30ec66769_::operator()

- ea: `0x180096c6c`
- end: `0x180096d4e`
- name: `_lambda_e1fa2b829fed10d8d95479f30ec66769_::operator()`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800970c0`

## callees

- `0x180011d90`
- `0x180043744`
- `0x18005388c`
- `0x180056358`
- `0x180096bc8`
- `0x180096c6c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180096ca0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180096ca0`
- `RPCRT4!RpcRevertToSelf` at `0x180096d31`
- `RPCRT4!RpcRevertToSelf` at `0x180096d31`
- `RPCRT4!RpcImpersonateClient` at `0x180096cd5`
- `RPCRT4!RpcImpersonateClient` at `0x180096cd5`
- `cryptngc!NgcAddBioProtector` at `0x180096d0c`
- `cryptngc!NgcAddBioProtector` at `0x180096d0c`

## string_xrefs

- `0x180096cbe`: `onecore\ds\security\biometrics\service\server\ngc.cpp`
- `0x180096ce4`: `onecore\ds\security\biometrics\service\server\ngc.cpp`
- `0x180096d1d`: `onecore\ds\security\biometrics\service\server\ngc.cpp`

## pseudocode

```c
__int64 __fastcall lambda_e1fa2b829fed10d8d95479f30ec66769_::operator()(__int64 a1)
{
  bool v2; // bl
  const char *v3; // r9
  int LastError; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 *v9; // [rsp+20h] [rbp-28h] BYREF
  LPWSTR v10; // [rsp+28h] [rbp-20h] BYREF
  char v11; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v13; // [rsp+50h] [rbp+8h] BYREF

  v10 = 0;
  v9 = &v13;
  v11 = 1;
  v13 = 0;
  v2 = !ConvertSidToStringSidW((PSID)(a1 + 8), &v10);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v9);
  if ( v2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2A,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\ngc.cpp",
                  v3);
LABEL_5:
    v6 = LastError;
    goto LABEL_9;
  }
  v5 = RpcImpersonateClient(*(RPC_BINDING_HANDLE *)(a1 + 80));
  if ( v5 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x2E,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\ngc.cpp",
                  (const char *)v5,
                  (unsigned int)v9);
    goto LABEL_5;
  }
  v7 = NgcAddBioProtector(v13, *(_QWORD *)(a1 + 88), &xmmword_1800E0220);
  v6 = v7;
  if ( v7 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\ngc.cpp",
      (const char *)(unsigned int)v7,
      (int)v9);
  RpcRevertToSelf();
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
  return v6;
}

```

## disassembly

```asm
0x180096c6c  mov     r11, rsp
0x180096c6f  mov     [r11+10h], rbx
0x180096c73  push    rdi
0x180096c74  sub     rsp, 40h
0x180096c78  lea     rax, [r11+8]
0x180096c7c  mov     qword ptr [r11-20h], 0
0x180096c84  mov     rdi, rcx
0x180096c87  mov     [r11-28h], rax
0x180096c8b  add     rcx, 8; Sid
0x180096c8f  mov     [rsp+48h+var_18], 1
0x180096c94  lea     rdx, [r11-20h]; StringSid
0x180096c98  mov     qword ptr [r11+8], 0
0x180096ca0  call    cs:__imp_ConvertSidToStringSidW
0x180096ca6  test    eax, eax
0x180096ca8  lea     rcx, [rsp+48h+var_28]
0x180096cad  setz    bl
0x180096cb0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180096cb5  test    bl, bl
0x180096cb7  jz      short loc_180096CD1
0x180096cb9  mov     rcx, [rsp+48h]; this
0x180096cbe  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\biometrics\\serv"...
0x180096cc5  mov     edx, 2Ah ; '*'; void *
0x180096cca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180096ccf  jmp     short loc_180096CF8
0x180096cd1  mov     rcx, [rdi+50h]; BindingHandle
0x180096cd5  call    cs:__imp_RpcImpersonateClient
0x180096cdb  test    eax, eax
0x180096cdd  jz      short loc_180096CFC
0x180096cdf  mov     rcx, [rsp+48h]; this
0x180096ce4  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\biometrics\\serv"...
0x180096ceb  mov     r9d, eax; char *
0x180096cee  mov     edx, 2Eh ; '.'; void *
0x180096cf3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180096cf8  mov     ebx, eax
0x180096cfa  jmp     short loc_180096D37
0x180096cfc  mov     rdx, [rdi+58h]
0x180096d00  lea     r8, xmmword_1800E0220
0x180096d07  mov     rcx, [rsp+48h+arg_0]
0x180096d0c  call    cs:__imp_NgcAddBioProtector
0x180096d12  mov     ebx, eax
0x180096d14  test    eax, eax
0x180096d16  jns     short loc_180096D31
0x180096d18  mov     rcx, [rsp+48h]; this
0x180096d1d  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\biometrics\\serv"...
0x180096d24  mov     r9d, eax; char *
0x180096d27  mov     edx, 35h ; '5'; void *
0x180096d2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096d31  call    cs:__imp_RpcRevertToSelf
0x180096d37  lea     rcx, [rsp+48h+arg_0]
0x180096d3c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180096d41  mov     eax, ebx
0x180096d43  mov     rbx, [rsp+48h+arg_8]
0x180096d48  add     rsp, 40h
0x180096d4c  pop     rdi
0x180096d4d  retn
```
