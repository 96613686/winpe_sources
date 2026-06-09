# FirewallApi::InitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18005e400`
- end: `0x18005e64b`
- name: `?InitOnceCallback@FirewallApi@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `587`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180027630`
- `0x18002af10`
- `0x180032938`
- `0x180046e20`
- `0x180051f64`
- `0x18005e400`
- `0x180084f50`
- `0x1800c7f40`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005e43e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005e43e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e481`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e4bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e4e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e510`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e481`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e4bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e4e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e510`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e5f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e623`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e5f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e623`

## string_xrefs

- `0x18005e437`: `firewallapi.dll`
- `0x18005e494`: `Failed GetProcAddress FWOpenPolicyStore`
- `0x18005e47a`: `FWOpenPolicyStore`
- `0x18005e55f`: `FWOpenPolicyStore`
- `0x18005e45b`: `Failed LoadLibraryEx`
- `0x18005e5b5`: `FWOpenPolicyStore(FW_STORE_TYPE_IF_ISO)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FirewallApi::InitOnceCallback(PINIT_ONCE InitOnce, HMODULE *Parameter, PVOID *Context)
{
  HMODULE *v3; // rbx
  HMODULE Library; // rax
  HMODULE v5; // rcx
  FARPROC ProcAddress; // rax
  const unsigned __int16 *v8; // rcx
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  int v12; // eax
  int v13; // r8d
  int v14; // r9d
  int v15; // ebx
  int v16; // [rsp+40h] [rbp-40h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-38h] BYREF
  const char *v18; // [rsp+50h] [rbp-30h] BYREF
  HMODULE *v19; // [rsp+58h] [rbp-28h] BYREF
  HMODULE v20; // [rsp+60h] [rbp-20h] BYREF
  __int128 v21; // [rsp+68h] [rbp-18h] BYREF

  v3 = Parameter;
  v19 = Parameter;
  if ( !*Parameter )
  {
    Library = LoadLibraryExW(L"firewallapi.dll", 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v3,
      Library);
    v5 = *v19;
    if ( !*v19 )
    {
      LogError(L"Failed LoadLibraryEx");
      return 0;
    }
    *(_QWORD *)&v21 = &v19;
    BYTE8(v21) = 1;
    ProcAddress = GetProcAddress(v5, "FWOpenPolicyStore");
    v19[2] = (HMODULE)ProcAddress;
    if ( !ProcAddress )
    {
      v8 = L"Failed GetProcAddress FWOpenPolicyStore";
LABEL_7:
      LogError(v8);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
        v19,
        0);
      return 0;
    }
    v9 = GetProcAddress(*v19, "FWClosePolicyStore");
    v19[3] = (HMODULE)v9;
    if ( !v9 )
    {
      v8 = L"Failed GetProcAddress FWClosePolicyStore";
      goto LABEL_7;
    }
    v10 = GetProcAddress(*v19, "FWQueryFirewallRules");
    v19[4] = (HMODULE)v10;
    if ( !v10 )
    {
      v8 = L"Failed GetProcAddress FWQueryFirewallRules";
      goto LABEL_7;
    }
    v11 = GetProcAddress(*v19, "FWFreeFirewallRules");
    v19[5] = (HMODULE)v11;
    if ( !v11 )
    {
      v8 = L"failed GetProcAddress FWFreeFirewallRules";
      goto LABEL_7;
    }
    v3 = v19;
  }
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, v3 + 6);
  if ( !v19[11] )
  {
    v21 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v21, "FWOpenPolicyStore");
    v20 = 0;
    v12 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64, _DWORD, HMODULE *))v19[2])(545, 0, 8, 1, 0, &v20);
    v15 = v12;
    if ( (unsigned int)dword_18013A158 > 4 )
    {
      v16 = v12;
      v18 = "FWOpenPolicyStore(FW_STORE_TYPE_IF_ISO)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_18013A158,
        (unsigned int)&byte_18011E4EF,
        v13,
        v14,
        (__int64)&v18,
        (__int64)&v16);
    }
    if ( v15 )
    {
      WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v21);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      return 0;
    }
    v19[11] = v20;
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v21);
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return 1;
}

```

## disassembly

```asm
0x18005e400  mov     [rsp-8+arg_0], rbx
0x18005e405  push    rbp
0x18005e406  mov     rbp, rsp
0x18005e409  sub     rsp, 80h
0x18005e410  mov     rax, cs:__security_cookie
0x18005e417  xor     rax, rsp
0x18005e41a  mov     [rbp+var_8], rax
0x18005e41e  mov     rbx, rdx
0x18005e421  mov     [rbp+var_28], rdx
0x18005e425  cmp     qword ptr [rdx], 0
0x18005e429  jnz     loc_18005E533
0x18005e42f  xor     edx, edx; hFile
0x18005e431  mov     r8d, 800h; dwFlags
0x18005e437  lea     rcx, aFirewallapiDll; "firewallapi.dll"
0x18005e43e  call    cs:__imp_LoadLibraryExW
0x18005e444  mov     rdx, rax
0x18005e447  mov     rcx, rbx
0x18005e44a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18005e44f  mov     rax, [rbp+var_28]
0x18005e453  mov     rcx, [rax]; hModule
0x18005e456  test    rcx, rcx
0x18005e459  jnz     short loc_18005E46E
0x18005e45b  lea     rcx, aFailedLoadlibr; "Failed LoadLibraryEx"
0x18005e462  call    ?LogError@@YAXPEBG@Z; LogError(ushort const *)
0x18005e467  xor     eax, eax
0x18005e469  jmp     loc_18005E62E
0x18005e46e  lea     rax, [rbp+var_28]
0x18005e472  mov     qword ptr [rbp+var_18], rax
0x18005e476  mov     byte ptr [rbp+var_18+8], 1
0x18005e47a  lea     rdx, aFwopenpolicyst; "FWOpenPolicyStore"
0x18005e481  call    cs:__imp_GetProcAddress
0x18005e487  mov     rcx, [rbp+var_28]
0x18005e48b  mov     [rcx+10h], rax
0x18005e48f  test    rax, rax
0x18005e492  jnz     short loc_18005E4AE
0x18005e494  lea     rcx, aFailedGetproca_0; "Failed GetProcAddress FWOpenPolicyStore"
0x18005e49b  call    ?LogError@@YAXPEBG@Z; LogError(ushort const *)
0x18005e4a0  nop
0x18005e4a1  xor     edx, edx
0x18005e4a3  mov     rcx, [rbp+var_28]
0x18005e4a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18005e4ac  jmp     short loc_18005E467
0x18005e4ae  lea     rdx, aFwclosepolicys; "FWClosePolicyStore"
0x18005e4b5  mov     rcx, [rbp+var_28]
0x18005e4b9  mov     rcx, [rcx]; hModule
0x18005e4bc  call    cs:__imp_GetProcAddress
0x18005e4c2  mov     rcx, [rbp+var_28]
0x18005e4c6  mov     [rcx+18h], rax
0x18005e4ca  test    rax, rax
0x18005e4cd  jnz     short loc_18005E4D8
0x18005e4cf  lea     rcx, aFailedGetproca_2; "Failed GetProcAddress FWClosePolicyStor"...
0x18005e4d6  jmp     short loc_18005E49B
0x18005e4d8  lea     rdx, aFwqueryfirewal; "FWQueryFirewallRules"
0x18005e4df  mov     rcx, [rbp+var_28]
0x18005e4e3  mov     rcx, [rcx]; hModule
0x18005e4e6  call    cs:__imp_GetProcAddress
0x18005e4ec  mov     rcx, [rbp+var_28]
0x18005e4f0  mov     [rcx+20h], rax
0x18005e4f4  test    rax, rax
0x18005e4f7  jnz     short loc_18005E502
0x18005e4f9  lea     rcx, aFailedGetproca; "Failed GetProcAddress FWQueryFirewallRu"...
0x18005e500  jmp     short loc_18005E49B
0x18005e502  lea     rdx, aFwfreefirewall; "FWFreeFirewallRules"
0x18005e509  mov     rcx, [rbp+var_28]
0x18005e50d  mov     rcx, [rcx]; hModule
0x18005e510  call    cs:__imp_GetProcAddress
0x18005e516  mov     rcx, [rbp+var_28]
0x18005e51a  mov     [rcx+28h], rax
0x18005e51e  test    rax, rax
0x18005e521  jnz     short loc_18005E52F
0x18005e523  lea     rcx, aFailedGetproca_1; "failed GetProcAddress FWFreeFirewallRul"...
0x18005e52a  jmp     loc_18005E49B
0x18005e52f  mov     rbx, [rbp+var_28]
0x18005e533  mov     [rbp+lpCriticalSection], 0
0x18005e53b  lea     rdx, [rbx+30h]
0x18005e53f  lea     rcx, [rbp+lpCriticalSection]
0x18005e543  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18005e548  nop
0x18005e549  mov     rax, [rbp+var_28]
0x18005e54d  cmp     qword ptr [rax+58h], 0
0x18005e552  jnz     loc_18005E61A
0x18005e558  xorps   xmm0, xmm0
0x18005e55b  movups  [rbp+var_18], xmm0
0x18005e55f  lea     rdx, aFwopenpolicyst; "FWOpenPolicyStore"
0x18005e566  lea     rcx, [rbp+var_18]; this
0x18005e56a  call    ??0WcmTimerTracking@@QEAA@PEBD@Z; WcmTimerTracking::WcmTimerTracking(char const *)
0x18005e56f  nop
0x18005e570  mov     [rbp+var_20], 0
0x18005e578  mov     ecx, 221h
0x18005e57d  mov     rax, [rbp+var_28]
0x18005e581  lea     rdx, [rbp+var_20]
0x18005e585  mov     [rsp+80h+var_58], rdx
0x18005e58a  mov     dword ptr [rsp+80h+var_60], 0
0x18005e592  xor     edx, edx
0x18005e594  lea     r9d, [rdx+1]
0x18005e598  lea     r8d, [rdx+8]
0x18005e59c  mov     rax, [rax+10h]
0x18005e5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5a5  mov     ebx, eax
0x18005e5a7  mov     ecx, cs:dword_18013A158
0x18005e5ad  cmp     ecx, 4
0x18005e5b0  jbe     short loc_18005E5DE
0x18005e5b2  mov     [rbp+var_40], eax
0x18005e5b5  lea     rax, aFwopenpolicyst_0; "FWOpenPolicyStore(FW_STORE_TYPE_IF_ISO)"
0x18005e5bc  mov     [rbp+var_30], rax
0x18005e5c0  lea     rax, [rbp+var_40]
0x18005e5c4  mov     [rsp+80h+var_58], rax
0x18005e5c9  lea     rax, [rbp+var_30]
0x18005e5cd  mov     [rsp+80h+var_60], rax
0x18005e5d2  lea     rdx, byte_18011E4EF
0x18005e5d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005e5de  test    ebx, ebx
0x18005e5e0  jz      short loc_18005E604
0x18005e5e2  lea     rcx, [rbp+var_18]; this
0x18005e5e6  call    ??1WcmTimerTracking@@QEAA@XZ; WcmTimerTracking::~WcmTimerTracking(void)
0x18005e5eb  nop
0x18005e5ec  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18005e5f0  test    rcx, rcx
0x18005e5f3  jz      loc_18005E467
0x18005e5f9  call    cs:__imp_LeaveCriticalSection
0x18005e5ff  jmp     loc_18005E467
0x18005e604  mov     rcx, [rbp+var_28]
0x18005e608  mov     rax, [rbp+var_20]
0x18005e60c  mov     [rcx+58h], rax
0x18005e610  lea     rcx, [rbp+var_18]; this
0x18005e614  call    ??1WcmTimerTracking@@QEAA@XZ; WcmTimerTracking::~WcmTimerTracking(void)
0x18005e619  nop
0x18005e61a  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18005e61e  test    rcx, rcx
0x18005e621  jz      short loc_18005E629
0x18005e623  call    cs:__imp_LeaveCriticalSection
0x18005e629  mov     eax, 1
0x18005e62e  mov     rcx, [rbp+var_8]
0x18005e632  xor     rcx, rsp; StackCookie
0x18005e635  call    __security_check_cookie
0x18005e63a  mov     rbx, [rsp+80h+arg_0]
0x18005e642  add     rsp, 80h
0x18005e649  pop     rbp
0x18005e64a  retn
```
