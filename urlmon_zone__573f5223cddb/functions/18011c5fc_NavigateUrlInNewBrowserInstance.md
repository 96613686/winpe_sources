# NavigateUrlInNewBrowserInstance

- ea: `0x18011c5fc`
- end: `0x18011c92b`
- name: `NavigateUrlInNewBrowserInstance`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18010d020`

## callees

- `0x1800a25dc`
- `0x1800a4660`
- `0x1800ff0d0`
- `0x18011c33c`
- `0x18011c5fc`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x18011c686`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x18011c686`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011c624`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011c785`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011c624`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011c785`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18011c650`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18011c650`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18011c674`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18011c674`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18011c6c7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18011c7fb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18011c6c7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18011c7fb`
- `OLEAUT32!__imp_SysAllocString` at `0x18011c86f`
- `OLEAUT32!__imp_SysAllocString` at `0x18011c86f`
- `OLEAUT32!__imp_SysFreeString` at `0x18011c8cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18011c8df`
- `OLEAUT32!__imp_SysFreeString` at `0x18011c8ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18011c911`
- `OLEAUT32!__imp_SysFreeString` at `0x18011c8cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18011c8df`
- `OLEAUT32!__imp_SysFreeString` at `0x18011c8ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18011c911`

## string_xrefs

- `0x18011c747`: `res://iesetup.dll/IESechelp.htm`
- `0x18011c798`: `res://iesetup.dll/IESechelp.htm`
- `0x18011c7c8`: `res://iesetup.dll/IESechelp.htm`
- `0x18011c821`: `res://iesetup.dll/IESechelp.htm`

## pseudocode

```c
__int64 __fastcall NavigateUrlInNewBrowserInstance(__int64 a1, OLECHAR *a2, struct IEUserBroker *a3, __int64 a4)
{
  const char *v4; // r9
  int v5; // ebx
  DWORD CurrentThreadId; // eax
  DWORD v7; // ecx
  char v8; // di
  int v9; // r8d
  int v10; // ecx
  DWORD v12; // [rsp+28h] [rbp-59h]
  BSTR bstrString[2]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v14; // [rsp+58h] [rbp-29h]
  __int128 v15; // [rsp+60h] [rbp-21h] BYREF
  __int64 v16; // [rsp+70h] [rbp-11h]
  BSTR v17[2]; // [rsp+78h] [rbp-9h] BYREF
  __int64 v18; // [rsp+88h] [rbp+7h]
  BSTR v19[2]; // [rsp+90h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+A0h] [rbp+1Fh]
  __int128 v21; // [rsp+A8h] [rbp+27h] BYREF
  __int64 v22; // [rsp+B8h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  __int64 v24; // [rsp+E8h] [rbp+67h] BYREF
  BSTR v25; // [rsp+F0h] [rbp+6Fh] BYREF
  struct IEUserBroker *v26; // [rsp+F8h] [rbp+77h] BYREF
  __int64 dwProcessId; // [rsp+100h] [rbp+7Fh] BYREF

  dwProcessId = a4;
  v26 = a3;
  v25 = a2;
  v24 = a1;
  if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecoreuap\\inetcore\\lib\\nav\\iehelper.cpp",
      v4);
  v5 = -2147467259;
  if ( !IsDualEngineProcess() )
    goto LABEL_22;
  v24 = 0;
  v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v5 = CoCreateUserBrokerForThread(CurrentThreadId, &v26);
  if ( v5 < 0 )
    goto LABEL_22;
  LODWORD(dwProcessId) = 0;
  (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v26 + 24LL))(
    v26,
    0,
    0,
    &dwProcessId);
  v7 = -1;
  if ( (_DWORD)dwProcessId )
    v7 = dwProcessId;
  AllowSetForegroundWindow(v7);
  v25 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, BSTR *))(*(_QWORD *)v26 + 48LL))(
         v26,
         &CLSID_CShdocvwBroker,
         &IID_IUnknown,
         &v25);
  if ( v5 >= 0 )
  {
    v5 = (**(__int64 (__fastcall ***)(BSTR, GUID *, __int64 *))v25)(v25, &IID_IDualEngineBroker, &v24);
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v25 + 16LL))(v25);
  }
  (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v5 < 0
    || (v5 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
               v24,
               L"res://iesetup.dll/IESechelp.htm",
               0,
               0,
               0),
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24),
        v5 < 0) )
  {
LABEL_22:
    if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2
      || (v8 = 0, !(unsigned int)IsProtectedModeURL(L"res://iesetup.dll/IESechelp.htm")) )
    {
      v8 = 1;
    }
    LODWORD(dwProcessId) = 0;
    v25 = 0;
    LCIEGetRedirectionPolicyForURL2(
      L"res://iesetup.dll/IESechelp.htm",
      0,
      1,
      0x8000u,
      (unsigned int *)&dwProcessId,
      0,
      &v25);
    v26 = 0;
    AllowSetForegroundWindow(0xFFFFFFFF);
    LOBYTE(v9) = v8;
    if ( (int)CoCreateLocalServerIE(v10, (int)&v26, v9, (int)v25, v12) >= 0 )
    {
      v14 = 0;
      v20 = 0;
      v18 = 0;
      v16 = 0;
      v22 = 0;
      v15 = 0;
      LOWORD(v15) = 3;
      bstrString[0] = (BSTR)8;
      *(_OWORD *)v19 = 0;
      DWORD2(v15) = 0;
      *(_OWORD *)v17 = 0;
      v21 = 0;
      bstrString[1] = SysAllocString(L"res://iesetup.dll/IESechelp.htm");
      if ( bstrString[1] )
      {
        (*(void (__fastcall **)(struct IEUserBroker *, __int64))(*(_QWORD *)v26 + 328LL))(v26, 0xFFFFFFFFLL);
        (*(void (__fastcall **)(struct IEUserBroker *, BSTR *, __int128 *, BSTR *, __int128 *, BSTR *))(*(_QWORD *)v26 + 416LL))(
          v26,
          bstrString,
          &v15,
          v17,
          &v21,
          v19);
        SysFreeString(bstrString[1]);
      }
      SysFreeString(v17[1]);
      SysFreeString(v19[1]);
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v26 + 16LL))(v26);
      v5 = 0;
    }
    SysFreeString(v25);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18011c5fc  mov     rax, rsp
0x18011c5ff  mov     [rax+20h], r9
0x18011c603  mov     [rax+18h], r8
0x18011c607  mov     [rax+10h], rdx
0x18011c60b  mov     [rax+8], rcx
0x18011c60f  push    rbp
0x18011c610  push    rbx
0x18011c611  push    rdi
0x18011c612  lea     rbp, [rax-5Fh]
0x18011c616  sub     rsp, 0C0h
0x18011c61d  mov     edi, 1000002Dh
0x18011c622  mov     ecx, edi
0x18011c624  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18011c62b  nop     dword ptr [rax+rax+00h]
0x18011c630  cmp     eax, 2
0x18011c633  jnz     short loc_18011C64B
0x18011c635  mov     rcx, [rbp+5Fh]; this
0x18011c639  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\lib\\nav\\iehelpe"...
0x18011c640  mov     edx, 0FEh; void *
0x18011c645  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18011c64b  mov     ebx, 80004005h
0x18011c650  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18011c657  nop     dword ptr [rax+rax+00h]
0x18011c65c  test    al, al
0x18011c65e  jz      loc_18011C783
0x18011c664  mov     [rbp+57h+arg_0], 0
0x18011c66c  mov     [rbp+57h+arg_10], 0
0x18011c674  call    cs:__imp_GetCurrentThreadId
0x18011c67b  nop     dword ptr [rax+rax+00h]
0x18011c680  mov     ecx, eax
0x18011c682  lea     rdx, [rbp+57h+arg_10]
0x18011c686  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x18011c68d  nop     dword ptr [rax+rax+00h]
0x18011c692  mov     ebx, eax
0x18011c694  test    eax, eax
0x18011c696  js      loc_18011C783
0x18011c69c  mov     rcx, [rbp+57h+arg_10]
0x18011c6a0  lea     r9, [rbp+57h+dwProcessId]
0x18011c6a4  mov     dword ptr [rbp+57h+dwProcessId], 0
0x18011c6ab  xor     r8d, r8d
0x18011c6ae  xor     edx, edx
0x18011c6b0  mov     rax, [rcx]
0x18011c6b3  mov     rax, [rax+18h]
0x18011c6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c6bc  mov     eax, dword ptr [rbp+57h+dwProcessId]
0x18011c6bf  or      ecx, 0FFFFFFFFh
0x18011c6c2  test    eax, eax
0x18011c6c4  cmovnz  ecx, eax; dwProcessId
0x18011c6c7  call    cs:__imp_AllowSetForegroundWindow
0x18011c6ce  nop     dword ptr [rax+rax+00h]
0x18011c6d3  mov     rcx, [rbp+57h+arg_10]
0x18011c6d7  lea     r9, [rbp+57h+arg_8]
0x18011c6db  mov     [rbp+57h+arg_8], 0
0x18011c6e3  lea     r8, IID_IUnknown
0x18011c6ea  lea     rdx, CLSID_CShdocvwBroker
0x18011c6f1  mov     rax, [rcx]
0x18011c6f4  mov     rax, [rax+30h]
0x18011c6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c6fd  mov     ebx, eax
0x18011c6ff  test    eax, eax
0x18011c701  js      short loc_18011C72F
0x18011c703  mov     rcx, [rbp+57h+arg_8]
0x18011c707  lea     r8, [rbp+57h+arg_0]
0x18011c70b  lea     rdx, IID_IDualEngineBroker
0x18011c712  mov     rax, [rcx]
0x18011c715  mov     rax, [rax]
0x18011c718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c71d  mov     rcx, [rbp+57h+arg_8]
0x18011c721  mov     ebx, eax
0x18011c723  mov     rax, [rcx]
0x18011c726  mov     rax, [rax+10h]
0x18011c72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c72f  mov     rcx, [rbp+57h+arg_10]
0x18011c733  mov     rax, [rcx]
0x18011c736  mov     rax, [rax+10h]
0x18011c73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c73f  test    ebx, ebx
0x18011c741  js      short loc_18011C783
0x18011c743  mov     rcx, [rbp+57h+arg_0]
0x18011c747  lea     rdx, aResIesetupDllI; "res://iesetup.dll/IESechelp.htm"
0x18011c74e  xor     r9d, r9d
0x18011c751  mov     qword ptr [rsp+0D0h+var_B0], 0
0x18011c75a  xor     r8d, r8d
0x18011c75d  mov     rax, [rcx]
0x18011c760  mov     rax, [rax+40h]
0x18011c764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c769  mov     rcx, [rbp+57h+arg_0]
0x18011c76d  mov     ebx, eax
0x18011c76f  mov     rax, [rcx]
0x18011c772  mov     rax, [rax+10h]
0x18011c776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c77b  test    ebx, ebx
0x18011c77d  jns     loc_18011C91D
0x18011c783  mov     ecx, edi
0x18011c785  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18011c78c  nop     dword ptr [rax+rax+00h]
0x18011c791  cmp     eax, 2
0x18011c794  jz      short loc_18011C7AB
0x18011c796  xor     edx, edx
0x18011c798  lea     rcx, aResIesetupDllI; "res://iesetup.dll/IESechelp.htm"
0x18011c79f  xor     dil, dil
0x18011c7a2  call    IsProtectedModeURL
0x18011c7a7  test    eax, eax
0x18011c7a9  jnz     short loc_18011C7AE
0x18011c7ab  mov     dil, 1
0x18011c7ae  xor     edx, edx; int
0x18011c7b0  mov     dword ptr [rbp+57h+dwProcessId], 0
0x18011c7b7  lea     rax, [rbp+57h+arg_8]
0x18011c7bb  mov     [rbp+57h+arg_8], 0
0x18011c7c3  mov     [rsp+30h], rax; unsigned __int16 **
0x18011c7c8  lea     rcx, aResIesetupDllI; "res://iesetup.dll/IESechelp.htm"
0x18011c7cf  lea     rax, [rbp+57h+dwProcessId]
0x18011c7d3  mov     [rsp+0D0h+var_A8], 0; int *
0x18011c7dc  lea     r8d, [rdx+1]; int
0x18011c7e0  mov     qword ptr [rsp+0D0h+var_B0], rax; dwProcessId
0x18011c7e5  mov     r9d, 8000h; unsigned int
0x18011c7eb  call    ?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z; LCIEGetRedirectionPolicyForURL2(ushort const *,int,int,ulong,ulong *,int *,ushort * *)
0x18011c7f0  or      ecx, 0FFFFFFFFh; dwProcessId
0x18011c7f3  mov     [rbp+57h+arg_10], 0
0x18011c7fb  call    cs:__imp_AllowSetForegroundWindow
0x18011c802  nop     dword ptr [rax+rax+00h]
0x18011c807  mov     r9, [rbp+57h+arg_8]; int
0x18011c80b  lea     rdx, [rbp+57h+arg_10]; int
0x18011c80f  mov     r8b, dil; int
0x18011c812  call    CoCreateLocalServerIE
0x18011c817  test    eax, eax
0x18011c819  js      loc_18011C90D
0x18011c81f  xor     eax, eax
0x18011c821  lea     rcx, aResIesetupDllI; "res://iesetup.dll/IESechelp.htm"
0x18011c828  xorps   xmm0, xmm0
0x18011c82b  mov     [rbp+57h+var_80], rax
0x18011c82f  mov     [rbp+57h+var_38], rax
0x18011c833  xorps   xmm1, xmm1
0x18011c836  mov     [rbp+57h+var_50], rax
0x18011c83a  mov     [rbp+57h+var_68], rax
0x18011c83e  mov     [rbp+57h+var_20], rax
0x18011c842  mov     eax, 3
0x18011c847  movups  [rbp+57h+var_78], xmm1
0x18011c84b  mov     word ptr [rbp+57h+var_78], ax
0x18011c84f  mov     eax, 8
0x18011c854  movups  xmmword ptr [rbp+57h+bstrString], xmm0
0x18011c858  mov     word ptr [rbp+57h+bstrString], ax
0x18011c85c  movups  xmmword ptr [rbp+57h+var_48], xmm1
0x18011c860  mov     dword ptr [rbp+57h+var_78+8], 0
0x18011c867  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18011c86b  movups  [rbp+57h+var_30], xmm0
0x18011c86f  call    cs:__imp_SysAllocString
0x18011c876  nop     dword ptr [rax+rax+00h]
0x18011c87b  mov     [rbp+57h+bstrString+8], rax
0x18011c87f  test    rax, rax
0x18011c882  jz      short loc_18011C8DB
0x18011c884  mov     rcx, [rbp+57h+arg_10]
0x18011c888  or      edx, 0FFFFFFFFh
0x18011c88b  mov     rax, [rcx]
0x18011c88e  mov     rax, [rax+148h]
0x18011c895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c89a  mov     rcx, [rbp+57h+arg_10]
0x18011c89e  lea     rdx, [rbp+57h+var_48]
0x18011c8a2  mov     [rsp+0D0h+var_A8], rdx
0x18011c8a7  lea     r9, [rbp+57h+var_60]
0x18011c8ab  lea     rdx, [rbp+57h+var_30]
0x18011c8af  mov     qword ptr [rsp+0D0h+var_B0], rdx
0x18011c8b4  lea     r8, [rbp+57h+var_78]
0x18011c8b8  mov     rax, [rcx]
0x18011c8bb  lea     rdx, [rbp+57h+bstrString]
0x18011c8bf  mov     rax, [rax+1A0h]
0x18011c8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c8cb  mov     rcx, [rbp+57h+bstrString+8]; bstrString
0x18011c8cf  call    cs:__imp_SysFreeString
0x18011c8d6  nop     dword ptr [rax+rax+00h]
0x18011c8db  mov     rcx, [rbp+57h+var_60+8]; bstrString
0x18011c8df  call    cs:__imp_SysFreeString
0x18011c8e6  nop     dword ptr [rax+rax+00h]
0x18011c8eb  mov     rcx, [rbp+57h+var_48+8]; bstrString
0x18011c8ef  call    cs:__imp_SysFreeString
0x18011c8f6  nop     dword ptr [rax+rax+00h]
0x18011c8fb  mov     rcx, [rbp+57h+arg_10]
0x18011c8ff  mov     rax, [rcx]
0x18011c902  mov     rax, [rax+10h]
0x18011c906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c90b  xor     ebx, ebx
0x18011c90d  mov     rcx, [rbp+57h+arg_8]; bstrString
0x18011c911  call    cs:__imp_SysFreeString
0x18011c918  nop     dword ptr [rax+rax+00h]
0x18011c91d  mov     eax, ebx
0x18011c91f  add     rsp, 0C0h
0x18011c926  pop     rdi
0x18011c927  pop     rbx
0x18011c928  pop     rbp
0x18011c929  retn
```
