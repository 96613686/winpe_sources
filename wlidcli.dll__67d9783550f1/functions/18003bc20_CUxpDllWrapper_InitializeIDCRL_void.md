# CUxpDllWrapper::InitializeIDCRL(void)

- ea: `0x18003bc20`
- end: `0x18003bd58`
- name: `?InitializeIDCRL@CUxpDllWrapper@@IEAAJXZ`
- size: `312`
- prototype: `__int64 __fastcall(CUxpDllWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18003b964`

## callees

- `0x18000a914`
- `0x18000af14`
- `0x18000ba8c`
- `0x18000bdf0`
- `0x180031a90`
- `0x18003bc20`
- `0x18004c9b8`
- `0x180053890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003bca4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003bca4`

## string_xrefs

- `0x18003bc6d`: `CUxpDllWrapper::InitializeIDCRL`
- `0x18003bd1f`: `CUxpDllWrapper::InitializeIDCRL`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUxpDllWrapper::InitializeIDCRL(CUxpDllWrapper *this)
{
  unsigned int v1; // edx
  int v2; // edi
  CUxpDllWrapper *v3; // rbx
  CUxpDllWrapper *v5; // [rsp+60h] [rbp+10h] BYREF
  unsigned __int16 *v6; // [rsp+68h] [rbp+18h] BYREF

  v5 = this;
  v6 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v5);
  v2 = WLIDCGetSvcEnvironment(&v6, v1);
  if ( v2 >= 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v5);
    v3 = v5;
    if ( !(unsigned int)_o__wcsicmp(v5, L"prod") || !*((_DWORD *)v3 - 4) )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v5);
      v3 = v5;
    }
    v2 = InitializeEx((GUID *)&rguid, 1);
    if ( v2 < 0 )
      Telemetry::IfFailExit(
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
        "CUxpDllWrapper::InitializeIDCRL",
        0xA3u,
        v2,
        "hr = IDCRL::InitializeEx(GUID_IDCRL_UIPROXY, IDCRL_API_VERSION_CURRENT, IDCRL::NO_UI | IDCRL::SKIP_CONNECTION_CH"
        "ECK | IDCRL::OFFLINE_MODE_ALLOWED, opt, 1)");
  }
  else
  {
    Telemetry::IfFailExit(
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
      "CUxpDllWrapper::InitializeIDCRL",
      0x93u,
      v2,
      "hr = WLIDCGetSvcEnvironment( &wstrSvcEnvBuf )");
    v3 = v5;
  }
  ATL::CStringData::Release((CUxpDllWrapper *)((char *)v3 - 24));
  CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v6);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003bc20  mov     [rsp-8+arg_10], rbx
0x18003bc25  mov     [rsp-8+arg_18], rdi
0x18003bc2a  mov     [rsp-8+arg_0], rcx
0x18003bc2f  push    rbp
0x18003bc30  mov     rbp, rsp
0x18003bc33  sub     rsp, 50h
0x18003bc37  mov     [rbp+arg_8], 0
0x18003bc3f  lea     rcx, [rbp+arg_0]
0x18003bc43  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003bc48  nop
0x18003bc49  lea     rcx, [rbp+arg_8]; unsigned __int16 **
0x18003bc4d  call    ?WLIDCGetSvcEnvironment@@YAJPEAPEAG@Z; WLIDCGetSvcEnvironment(ushort * *)
0x18003bc52  mov     edi, eax
0x18003bc54  test    eax, eax
0x18003bc56  jns     short loc_18003BC89
0x18003bc58  lea     rax, aHrWlidcgetsvce; "hr = WLIDCGetSvcEnvironment( &wstrSvcEn"...
0x18003bc5f  mov     [rsp+50h+var_30], rax; char *
0x18003bc64  mov     r9d, edi; int
0x18003bc67  mov     r8d, 93h; unsigned int
0x18003bc6d  lea     rdx, aCuxpdllwrapper_1; "CUxpDllWrapper::InitializeIDCRL"
0x18003bc74  lea     rcx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003bc7b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003bc80  mov     rbx, [rbp+arg_0]
0x18003bc84  jmp     loc_18003BD33
0x18003bc89  mov     rdx, [rbp+arg_8]
0x18003bc8d  lea     rcx, [rbp+arg_0]
0x18003bc91  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18003bc96  lea     rdx, aProd; "prod"
0x18003bc9d  mov     rbx, [rbp+arg_0]
0x18003bca1  mov     rcx, rbx
0x18003bca4  call    cs:__imp__o__wcsicmp
0x18003bcaa  test    eax, eax
0x18003bcac  jz      short loc_18003BCB4
0x18003bcae  cmp     dword ptr [rbx-10h], 0
0x18003bcb2  jnz     short loc_18003BCC8
0x18003bcb4  lea     rdx, aProduction; "production"
0x18003bcbb  lea     rcx, [rbp+arg_0]
0x18003bcbf  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18003bcc4  mov     rbx, [rbp+arg_0]
0x18003bcc8  mov     [rbp+var_20], 40h ; '@'
0x18003bcd0  mov     [rbp+var_10], 0
0x18003bcd8  mov     [rbp+var_18], rbx
0x18003bcdc  movsxd  rax, dword ptr [rbx-10h]
0x18003bce0  add     rax, rax
0x18003bce3  mov     [rbp+var_10], rax
0x18003bce7  mov     edx, 1
0x18003bcec  mov     dword ptr [rsp+50h+var_30], edx; int
0x18003bcf0  lea     r9, [rbp+var_20]
0x18003bcf4  lea     r8d, [rdx+6]
0x18003bcf8  lea     rcx, rguid; rguid
0x18003bcff  call    InitializeEx
0x18003bd04  mov     edi, eax
0x18003bd06  test    eax, eax
0x18003bd08  jns     short loc_18003BD33
0x18003bd0a  lea     rax, aHrIdcrlInitial; "hr = IDCRL::InitializeEx(GUID_IDCRL_UIP"...
0x18003bd11  mov     [rsp+50h+var_30], rax; char *
0x18003bd16  mov     r9d, edi; int
0x18003bd19  mov     r8d, 0A3h; unsigned int
0x18003bd1f  lea     rdx, aCuxpdllwrapper_1; "CUxpDllWrapper::InitializeIDCRL"
0x18003bd26  lea     rcx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003bd2d  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003bd32  nop
0x18003bd33  lea     rcx, [rbx-18h]; this
0x18003bd37  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003bd3c  nop
0x18003bd3d  lea     rcx, [rbp+arg_8]
0x18003bd41  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x18003bd46  mov     eax, edi
0x18003bd48  mov     rbx, [rsp+50h+arg_10]
0x18003bd4d  mov     rdi, [rsp+50h+arg_18]
0x18003bd52  add     rsp, 50h
0x18003bd56  pop     rbp
0x18003bd57  retn
```
