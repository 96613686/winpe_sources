# WFDSvc::ASP::CASPSessionSeeker::DoTargetedDiscovery(void)

- ea: `0x1800bf980`
- end: `0x1800bfe6f`
- name: `?DoTargetedDiscovery@CASPSessionSeeker@ASP@WFDSvc@@UEAAXXZ`
- size: `1263`
- prototype: `void __fastcall(WFDSvc::ASP::CASPSessionSeeker *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000be00`
- `0x1800596b4`
- `0x18006c1c0`
- `0x18007d770`
- `0x180093f18`
- `0x1800b2080`
- `0x1800bd620`
- `0x1800bee6c`
- `0x1800bf980`
- `0x180106340`
- `0x180106cec`
- `0x180106d54`
- `0x180107330`
- `0x180108cfc`
- `0x1801df8bc`
- `0x180202c98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfc4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfc54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfcb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfc4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfc54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfcb3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800bfdb7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800bfdb7`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryFromIdEx` at `0x1800bfd62`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryFromIdEx` at `0x1800bfd62`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800bfe37`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800bfe37`

## string_xrefs

- `0x1800bfdc4`: `Timed out in targeted discovery waiting for completion calback!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WFDSvc::ASP::CASPSessionSeeker::DoTargetedDiscovery(WFDSvc::ASP::CASPSessionSeeker *this)
{
  __int64 v2; // rdi
  int v3; // eax
  unsigned __int64 v4; // rax
  int v5; // eax
  signed int LastError; // eax
  signed int v7; // eax
  int v8; // eax
  DWORD v9; // eax
  const struct std::nothrow_t *v10; // rdx
  void *v11; // [rsp+68h] [rbp-98h] BYREF
  __int64 v12; // [rsp+70h] [rbp-90h] BYREF
  __int64 v13; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handles[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v15[16]; // [rsp+90h] [rbp-70h] BYREF
  void **v16; // [rsp+A0h] [rbp-60h]
  __int64 *v17; // [rsp+A8h] [rbp-58h]
  char v18; // [rsp+B0h] [rbp-50h]
  int v19[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v20; // [rsp+C8h] [rbp-38h] BYREF
  __int16 v21; // [rsp+CCh] [rbp-34h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, &WPP_2f24149a0c0238d65d957534ba88a50f_Traceguids, this);
  }
  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_1802A4B18 > *(_DWORD *)(v2 + 4) )
  {
    Init_thread_header(&dword_1802A4B18);
    if ( dword_1802A4B18 == -1 )
    {
      xmmword_1802A3A20 = DEVPKEY_WiFiDirect_Services;
      dword_1802A3A30 = 10;
      qword_1802A3A34 = 0;
      dword_1802A3A3C = 0;
      Init_thread_footer(&dword_1802A4B18);
    }
  }
  if ( dword_1802A4B1C > *(_DWORD *)(v2 + 4) )
  {
    Init_thread_header(&dword_1802A4B1C);
    if ( dword_1802A4B1C == -1 )
    {
      xmmword_1802A05A8 = DEVPKEY_AepService_ProtocolId;
      dword_1802A05B8 = 5;
      dword_1802A05BC = 0;
      qword_1802A05C0 = 0;
      dword_1802A05C8 = 13;
      dword_1802A05CC = 16;
      qword_1802A05D0 = (__int64)&DAF_ProtocolId_WiFiDirect;
      Init_thread_footer(&dword_1802A4B1C);
    }
  }
  v11 = 0;
  v12 = 0;
  memset_0(&v20, 0, 0x210u);
  v13 = 0;
  v16 = &v11;
  v17 = &v12;
  v18 = 1;
  v19[0] = 5;
  v19[1] = 1;
  v20 = *((_DWORD *)this + 276);
  v21 = *((_WORD *)this + 554);
  v3 = WfdDafObjectStringEncode((int)v19);
  if ( v3 < 0 )
    WFDSvc::CWFDSvcException::Throw(
      v3,
      "WFDSvc::ASP::CASPSessionSeeker::DoTargetedDiscovery",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspsession\\src\\aspsessionseeker.cpp",
      142,
      L"Function returned bad HRESULT",
      this);
  v4 = 2;
  if ( !is_mul_ok(1u, 2u) )
    v4 = -1;
  v11 = operator new[](v4, (const struct std::nothrow_t *)std::nothrow);
  if ( !v11 )
    WFDSvc::CWFDSvcException::Throw(
      -2147024882,
      "WFDSvc::ASP::CASPSessionSeeker::DoTargetedDiscovery",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspsession\\src\\aspsessionseeker.cpp",
      145,
      L"Allocation of pwszAepId failed",
      this);
  v5 = WfdDafObjectStringEncode((int)v19);
  if ( v5 < 0 )
    WFDSvc::CWFDSvcException::Throw(
      v5,
      "WFDSvc::ASP::CASPSessionSeeker::DoTargetedDiscovery",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspsession\\src\\aspsessionseeker.cpp",
      148,
      L"Function returned bad HRESULT",
      this);
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(v15, (char *)this + 1000);
  if ( !(unsigned __int8)_try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAA_NW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                           (char *)this + 1992,
                           1)
    && GetLastError() )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WFDSvc::CWFDSvcException::Throw(
      LastError,
      "WFDSvc::ASP::CASPSessionSeeker::DoTargetedDiscovery",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspsession\\src\\aspsessionseeker.cpp",
      155,
      L"Function returned bad Win32 Error Code",
      this);
  }
  if ( !(unsigned __int8)_try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAA_NW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                           (char *)this + 2000,
                           1)
    && GetLastError() )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    WFDSvc::CWFDSvcException::Throw(
      v7,
      "WFDSvc::ASP::CASPSessionSeeker::DoTargetedDiscovery",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspsession\\src\\aspsessionseeker.cpp",
      159,
      L"Function returned bad Win32 Error Code",
      this);
  }
  SmartPointer<WFDSvc::ASP::CSessionAction>::operator=(&v13, this);
  LockSentry<ReadersWriterLock,0>::Unlock(v15);
  v8 = DevCreateObjectQueryFromIdEx(
         5,
         v11,
         1,
         1,
         &xmmword_1802A3A20,
         1,
         &qword_1802A05A0,
         0,
         0,
         WFDSvc::ASP::CASPSessionSeeker::TargetedDiscoveryDevQueryCallback,
         this,
         &v12);
  if ( v8 < 0 )
    WFDSvc::CWFDSvcException::Throw(
      v8,
      "WFDSvc::ASP::CASPSessionSeeker::DoTargetedDiscovery",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspsession\\src\\aspsessionseeker.cpp",
      179,
      L"Function returned bad HRESULT",
      this);
  Handles[0] = *((HANDLE *)this + 249);
  Handles[1] = *((HANDLE *)this + 250);
  v9 = WaitForMultipleObjects(2u, Handles, 0, 0x2710u);
  if ( v9 == 258 )
    WFDSvc::CWFDSvcException::Throw(
      -2147023436,
      "WFDSvc::ASP::CASPSessionSeeker::DoTargetedDiscovery",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspsession\\src\\aspsessionseeker.cpp",
      0xBFu,
      L"Timed out in targeted discovery waiting for completion calback!");
  if ( v9 )
    WFDSvc::CWFDSvcException::Throw(
      -2147023673,
      "WFDSvc::ASP::CASPSessionSeeker::DoTargetedDiscovery",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\aspsession\\src\\aspsessionseeker.cpp",
      0xC3u,
      L"Targeted discovery cancelled");
  if ( v11 )
    operator delete(v11, v10);
  if ( v12 )
  {
    DevCloseObjectQuery();
    v12 = 0;
  }
  SmartPointer<WFDSvc::ASPCoordination::ASPCommandMessage>::~SmartPointer<WFDSvc::ASPCoordination::ASPCommandMessage>(&v13);
}

```

## disassembly

```asm
0x1800bf980  push    rbp
0x1800bf982  push    rbx
0x1800bf983  push    rsi
0x1800bf984  push    rdi
0x1800bf985  push    r12
0x1800bf987  push    r15
0x1800bf989  lea     rbp, [rsp-1F8h]
0x1800bf991  sub     rsp, 2F8h
0x1800bf998  mov     rax, cs:__security_cookie
0x1800bf99f  xor     rax, rsp
0x1800bf9a2  mov     [rbp+220h+var_40], rax
0x1800bf9a9  mov     rbx, rcx
0x1800bf9ac  lea     rax, WPP_GLOBAL_Control
0x1800bf9b3  mov     r15d, 1
0x1800bf9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf9c0  cmp     rcx, rax
0x1800bf9c3  jz      short loc_1800BF9E8
0x1800bf9c5  cmp     byte ptr [rcx+69h], 3
0x1800bf9c9  jb      short loc_1800BF9E8
0x1800bf9cb  test    [rcx+6Ch], r15b
0x1800bf9cf  jz      short loc_1800BF9E8
0x1800bf9d1  lea     edx, [r15+9]
0x1800bf9d5  mov     r9, rbx
0x1800bf9d8  lea     r8, WPP_2f24149a0c0238d65d957534ba88a50f_Traceguids
0x1800bf9df  mov     rcx, [rcx+60h]
0x1800bf9e3  call    WPP_SF_q
0x1800bf9e8  mov     ecx, cs:_tls_index
0x1800bf9ee  mov     rax, gs:58h
0x1800bf9f7  mov     r12d, 4
0x1800bf9fd  mov     rdi, [rax+rcx*8]
0x1800bfa01  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800bfa05  mov     eax, [rdi+r12]
0x1800bfa09  cmp     cs:dword_1802A4B18, eax
0x1800bfa0f  jle     short loc_1800BFA5A
0x1800bfa11  lea     rcx, dword_1802A4B18
0x1800bfa18  call    _Init_thread_header
0x1800bfa1d  cmp     cs:dword_1802A4B18, esi
0x1800bfa23  jnz     short loc_1800BFA5A
0x1800bfa25  movups  xmm0, cs:DEVPKEY_WiFiDirect_Services
0x1800bfa2c  movups  cs:xmmword_1802A3A20, xmm0
0x1800bfa33  mov     eax, cs:dword_18024BDB8
0x1800bfa39  mov     cs:dword_1802A3A30, eax
0x1800bfa3f  xor     eax, eax
0x1800bfa41  mov     cs:qword_1802A3A34, rax
0x1800bfa48  mov     cs:dword_1802A3A3C, eax
0x1800bfa4e  lea     rcx, dword_1802A4B18
0x1800bfa55  call    _Init_thread_footer
0x1800bfa5a  mov     eax, [rdi+r12]
0x1800bfa5e  cmp     cs:dword_1802A4B1C, eax
0x1800bfa64  jle     short loc_1800BFAD7
0x1800bfa66  lea     rcx, dword_1802A4B1C
0x1800bfa6d  call    _Init_thread_header
0x1800bfa72  cmp     cs:dword_1802A4B1C, esi
0x1800bfa78  jnz     short loc_1800BFAD7
0x1800bfa7a  movups  xmm0, cs:DEVPKEY_AepService_ProtocolId
0x1800bfa81  movups  cs:xmmword_1802A05A8, xmm0
0x1800bfa88  mov     eax, cs:dword_18024C160
0x1800bfa8e  mov     cs:dword_1802A05B8, eax
0x1800bfa94  mov     cs:dword_1802A05BC, 0
0x1800bfa9e  mov     cs:qword_1802A05C0, 0
0x1800bfaa9  mov     cs:dword_1802A05C8, 0Dh
0x1800bfab3  mov     cs:dword_1802A05CC, 10h
0x1800bfabd  lea     rax, DAF_ProtocolId_WiFiDirect
0x1800bfac4  mov     cs:qword_1802A05D0, rax
0x1800bfacb  lea     rcx, dword_1802A4B1C
0x1800bfad2  call    _Init_thread_footer
0x1800bfad7  mov     [rsp+320h+var_2B8], 0
0x1800bfae0  mov     [rsp+320h+var_2C0], 0
0x1800bfae8  mov     [rsp+320h+var_2B0], 0
0x1800bfaf1  xor     edx, edx; Val
0x1800bfaf3  mov     r8d, 210h; Size
0x1800bfaf9  lea     rcx, [rbp+220h+var_258]; void *
0x1800bfafd  call    memset_0
0x1800bfb02  mov     [rsp+320h+var_2A8], 0
0x1800bfb0b  lea     rax, [rsp+320h+var_2B8]
0x1800bfb10  mov     [rbp+220h+var_280], rax
0x1800bfb14  lea     rax, [rsp+320h+var_2B0]
0x1800bfb19  mov     [rbp+220h+var_278], rax
0x1800bfb1d  mov     [rbp+220h+var_270], r15b
0x1800bfb21  mov     [rbp+220h+var_260], 5
0x1800bfb28  mov     [rbp+220h+var_25C], r15d
0x1800bfb2c  mov     eax, [rbx+450h]
0x1800bfb32  mov     [rbp+220h+var_258], eax
0x1800bfb35  movzx   eax, word ptr [rbx+454h]
0x1800bfb3c  mov     [rbp+220h+var_254], ax
0x1800bfb40  xor     r9d, r9d
0x1800bfb43  lea     r8, [rsp+320h+var_2C0]
0x1800bfb48  lea     rcx, [rbp+220h+var_260]; int
0x1800bfb4c  call    WfdDafObjectStringEncode
0x1800bfb51  test    eax, eax
0x1800bfb53  jns     short loc_1800BFB82
0x1800bfb55  mov     [rsp+320h+var_2F8], rbx; void *
0x1800bfb5a  lea     rcx, aFunctionReturn_2; "Function returned bad HRESULT"
0x1800bfb61  mov     [rsp+320h+var_300], rcx; unsigned __int16 *
0x1800bfb66  mov     r9d, 8Eh; char
0x1800bfb6c  lea     r8, aOnecoreuapNetW_12; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bfb73  lea     rdx, aWfdsvcAspCasps_44; "WFDSvc::ASP::CASPSessionSeeker::DoTarge"...
0x1800bfb7a  mov     ecx, eax; int
0x1800bfb7c  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800bfb82  mov     ecx, [rsp+320h+var_2C0]
0x1800bfb86  inc     ecx
0x1800bfb88  mov     r12d, 2
0x1800bfb8e  mov     eax, r12d
0x1800bfb91  mul     rcx
0x1800bfb94  cmovb   rax, rsi
0x1800bfb98  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bfb9f  mov     rcx, rax; unsigned __int64
0x1800bfba2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bfba7  mov     [rsp+320h+var_2B8], rax
0x1800bfbac  test    rax, rax
0x1800bfbaf  jnz     short loc_1800BFBE1
0x1800bfbb1  mov     [rsp+320h+var_2F8], rbx; void *
0x1800bfbb6  lea     rax, aAllocationOfPw; "Allocation of pwszAepId failed"
0x1800bfbbd  mov     [rsp+320h+var_300], rax; unsigned __int16 *
0x1800bfbc2  mov     r9d, 91h; char
0x1800bfbc8  lea     r8, aOnecoreuapNetW_12; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bfbcf  lea     rdx, aWfdsvcAspCasps_44; "WFDSvc::ASP::CASPSessionSeeker::DoTarge"...
0x1800bfbd6  mov     ecx, 8007000Eh; int
0x1800bfbdb  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800bfbe1  mov     r9, rax
0x1800bfbe4  lea     r8, [rsp+320h+var_2C0]
0x1800bfbe9  lea     rcx, [rbp+220h+var_260]; int
0x1800bfbed  call    WfdDafObjectStringEncode
0x1800bfbf2  test    eax, eax
0x1800bfbf4  jns     short loc_1800BFC23
0x1800bfbf6  mov     [rsp+320h+var_2F8], rbx; void *
0x1800bfbfb  lea     rcx, aFunctionReturn_2; "Function returned bad HRESULT"
0x1800bfc02  mov     [rsp+320h+var_300], rcx; unsigned __int16 *
0x1800bfc07  mov     r9d, 94h; char
0x1800bfc0d  lea     r8, aOnecoreuapNetW_12; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bfc14  lea     rdx, aWfdsvcAspCasps_44; "WFDSvc::ASP::CASPSessionSeeker::DoTarge"...
0x1800bfc1b  mov     ecx, eax; int
0x1800bfc1d  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800bfc23  lea     rdx, [rbx+3E8h]
0x1800bfc2a  lea     rcx, [rbp+220h+var_290]
0x1800bfc2e  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x1800bfc33  nop
0x1800bfc34  lea     rsi, [rbx+7C8h]
0x1800bfc3b  mov     edx, r15d
0x1800bfc3e  mov     rcx, rsi
0x1800bfc41  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA_NW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800bfc46  test    al, al
0x1800bfc48  jnz     short loc_1800BFC93
0x1800bfc4a  call    cs:__imp_GetLastError
0x1800bfc50  test    eax, eax
0x1800bfc52  jz      short loc_1800BFC93
0x1800bfc54  call    cs:__imp_GetLastError
0x1800bfc5a  test    eax, eax
0x1800bfc5c  jle     short loc_1800BFC66
0x1800bfc5e  movzx   eax, ax
0x1800bfc61  or      eax, 80070000h
0x1800bfc66  mov     [rsp+320h+var_2F8], rbx; void *
0x1800bfc6b  lea     rcx, aFunctionReturn_1; "Function returned bad Win32 Error Code"
0x1800bfc72  mov     [rsp+320h+var_300], rcx; unsigned __int16 *
0x1800bfc77  mov     r9d, 9Bh; char
0x1800bfc7d  lea     r8, aOnecoreuapNetW_12; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bfc84  lea     rdx, aWfdsvcAspCasps_44; "WFDSvc::ASP::CASPSessionSeeker::DoTarge"...
0x1800bfc8b  mov     ecx, eax; int
0x1800bfc8d  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800bfc93  lea     rdi, [rbx+7D0h]
0x1800bfc9a  mov     edx, r15d
0x1800bfc9d  mov     rcx, rdi
0x1800bfca0  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA_NW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800bfca5  test    al, al
0x1800bfca7  jnz     short loc_1800BFCF2
0x1800bfca9  call    cs:__imp_GetLastError
0x1800bfcaf  test    eax, eax
0x1800bfcb1  jz      short loc_1800BFCF2
0x1800bfcb3  call    cs:__imp_GetLastError
0x1800bfcb9  test    eax, eax
0x1800bfcbb  jle     short loc_1800BFCC5
0x1800bfcbd  movzx   eax, ax
0x1800bfcc0  or      eax, 80070000h
0x1800bfcc5  mov     [rsp+320h+var_2F8], rbx; void *
0x1800bfcca  lea     rcx, aFunctionReturn_1; "Function returned bad Win32 Error Code"
0x1800bfcd1  mov     [rsp+320h+var_300], rcx; unsigned __int16 *
0x1800bfcd6  mov     r9d, 9Fh; char
0x1800bfcdc  lea     r8, aOnecoreuapNetW_12; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bfce3  lea     rdx, aWfdsvcAspCasps_44; "WFDSvc::ASP::CASPSessionSeeker::DoTarge"...
0x1800bfcea  mov     ecx, eax; int
0x1800bfcec  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800bfcf2  mov     rdx, rbx
0x1800bfcf5  lea     rcx, [rsp+320h+var_2A8]
0x1800bfcfa  call    ??4?$SmartPointer@VCSessionAction@ASP@WFDSvc@@@@QEAAAEAV0@PEAVCSessionAction@ASP@WFDSvc@@@Z; SmartPointer<WFDSvc::ASP::CSessionAction>::operator=(WFDSvc::ASP::CSessionAction *)
0x1800bfcff  nop
0x1800bfd00  lea     rcx, [rbp+220h+var_290]
0x1800bfd04  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x1800bfd09  lea     rax, [rsp+320h+var_2B0]
0x1800bfd0e  mov     [rsp+320h+var_2C8], rax
0x1800bfd13  mov     [rsp+320h+var_2D0], rbx
0x1800bfd18  lea     rax, ?TargetedDiscoveryDevQueryCallback@CASPSessionSeeker@ASP@WFDSvc@@KAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; WFDSvc::ASP::CASPSessionSeeker::TargetedDiscoveryDevQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x1800bfd1f  mov     [rsp+320h+var_2D8], rax
0x1800bfd24  mov     [rsp+320h+var_2E0], 0
0x1800bfd2d  mov     [rsp+320h+var_2E8], 0
0x1800bfd35  lea     rax, qword_1802A05A0
0x1800bfd3c  mov     [rsp+320h+var_2F0], rax
0x1800bfd41  mov     dword ptr [rsp+320h+var_2F8], r15d
0x1800bfd46  lea     rax, xmmword_1802A3A20
0x1800bfd4d  mov     [rsp+320h+var_300], rax
0x1800bfd52  mov     r9d, r15d
0x1800bfd55  mov     r8d, r15d
0x1800bfd58  mov     rdx, [rsp+320h+var_2B8]
0x1800bfd5d  mov     ecx, 5
0x1800bfd62  call    cs:__imp_DevCreateObjectQueryFromIdEx
0x1800bfd68  test    eax, eax
0x1800bfd6a  jns     short loc_1800BFD99
0x1800bfd6c  mov     [rsp+320h+var_2F8], rbx; void *
0x1800bfd71  lea     rcx, aFunctionReturn_2; "Function returned bad HRESULT"
0x1800bfd78  mov     [rsp+320h+var_300], rcx; unsigned __int16 *
0x1800bfd7d  mov     r9d, 0B3h; char
0x1800bfd83  lea     r8, aOnecoreuapNetW_12; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bfd8a  lea     rdx, aWfdsvcAspCasps_44; "WFDSvc::ASP::CASPSessionSeeker::DoTarge"...
0x1800bfd91  mov     ecx, eax; int
0x1800bfd93  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBGPEBX@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800bfd99  mov     rax, [rsi]
0x1800bfd9c  mov     [rbp+220h+Handles], rax
0x1800bfda0  mov     rax, [rdi]
0x1800bfda3  mov     [rbp+220h+var_298], rax
0x1800bfda7  mov     r9d, 2710h; dwMilliseconds
0x1800bfdad  xor     r8d, r8d; bWaitAll
0x1800bfdb0  lea     rdx, [rbp+220h+Handles]; lpHandles
0x1800bfdb4  mov     ecx, r12d; nCount
0x1800bfdb7  call    cs:__imp_WaitForMultipleObjects
0x1800bfdbd  cmp     eax, 102h
0x1800bfdc2  jnz     short loc_1800BFDEF
0x1800bfdc4  lea     rax, aTimedOutInTarg; "Timed out in targeted discovery waiting"...
0x1800bfdcb  mov     [rsp+320h+var_300], rax; unsigned __int16 *
0x1800bfdd0  mov     r9d, 0BFh; unsigned int
0x1800bfdd6  lea     r8, aOnecoreuapNetW_12; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bfddd  lea     rdx, aWfdsvcAspCasps_44; "WFDSvc::ASP::CASPSessionSeeker::DoTarge"...
0x1800bfde4  mov     ecx, 800705B4h; int
0x1800bfde9  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800bfdef  test    eax, eax
0x1800bfdf1  jz      short loc_1800BFE1E
0x1800bfdf3  lea     rax, aTargetedDiscov; "Targeted discovery cancelled"
0x1800bfdfa  mov     [rsp+320h+var_300], rax; unsigned __int16 *
0x1800bfdff  mov     r9d, 0C3h; unsigned int
0x1800bfe05  lea     r8, aOnecoreuapNetW_12; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bfe0c  lea     rdx, aWfdsvcAspCasps_44; "WFDSvc::ASP::CASPSessionSeeker::DoTarge"...
0x1800bfe13  mov     ecx, 800704C7h; int
0x1800bfe18  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800bfe1e  mov     rcx, [rsp+320h+var_2B8]; void *
0x1800bfe23  test    rcx, rcx
0x1800bfe26  jz      short loc_1800BFE2D
0x1800bfe28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bfe2d  mov     rcx, [rsp+320h+var_2B0]
0x1800bfe32  test    rcx, rcx
0x1800bfe35  jz      short loc_1800BFE46
0x1800bfe37  call    cs:__imp_DevCloseObjectQuery
0x1800bfe3d  mov     [rsp+320h+var_2B0], 0
0x1800bfe46  lea     rcx, [rsp+320h+var_2A8]
0x1800bfe4b  call    ??1?$SmartPointer@VASPCommandMessage@ASPCoordination@WFDSvc@@@@QEAA@XZ; SmartPointer<WFDSvc::ASPCoordination::ASPCommandMessage>::~SmartPointer<WFDSvc::ASPCoordination::ASPCommandMessage>(void)
0x1800bfe50  mov     rcx, [rbp+220h+var_40]
0x1800bfe57  xor     rcx, rsp; StackCookie
0x1800bfe5a  call    __security_check_cookie
0x1800bfe5f  add     rsp, 2F8h
0x1800bfe66  pop     r15
0x1800bfe68  pop     r12
0x1800bfe6a  pop     rdi
0x1800bfe6b  pop     rsi
0x1800bfe6c  pop     rbx
0x1800bfe6d  pop     rbp
0x1800bfe6e  retn
```
