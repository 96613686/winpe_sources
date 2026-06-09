# NavigateUrlInNewBrowserInstance

- ea: `0x180110654`
- end: `0x18011093a`
- name: `NavigateUrlInNewBrowserInstance`
- size: `742`
- prototype: `__int64 __fastcall(__int64, OLECHAR *, struct IEUserBroker *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180101f00`

## callees

- `0x18009b9dc`
- `0x18009d9a0`
- `0x1800f4b50`
- `0x1801103bc`
- `0x180110654`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1801106cc`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1801106cc`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011067c`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801107bf`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011067c`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801107bf`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801106a2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801106a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801106c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801106c0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x180110707`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18011082f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x180110707`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18011082f`
- `OLEAUT32!__imp_SysAllocString` at `0x18011089d`
- `OLEAUT32!__imp_SysAllocString` at `0x18011089d`
- `OLEAUT32!__imp_SysFreeString` at `0x1801108f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180110901`
- `OLEAUT32!__imp_SysFreeString` at `0x18011090b`
- `OLEAUT32!__imp_SysFreeString` at `0x180110927`
- `OLEAUT32!__imp_SysFreeString` at `0x1801108f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180110901`
- `OLEAUT32!__imp_SysFreeString` at `0x18011090b`
- `OLEAUT32!__imp_SysFreeString` at `0x180110927`

## string_xrefs

- `0x180110781`: `res://iesetup.dll/IESechelp.htm`
- `0x1801107cc`: `res://iesetup.dll/IESechelp.htm`
- `0x1801107fc`: `res://iesetup.dll/IESechelp.htm`
- `0x18011084f`: `res://iesetup.dll/IESechelp.htm`

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
0x180110654  mov     rax, rsp
0x180110657  mov     [rax+20h], r9
0x18011065b  mov     [rax+18h], r8
0x18011065f  mov     [rax+10h], rdx
0x180110663  mov     [rax+8], rcx
0x180110667  push    rbp
0x180110668  push    rbx
0x180110669  push    rdi
0x18011066a  lea     rbp, [rax-5Fh]
0x18011066e  sub     rsp, 0C0h
0x180110675  mov     edi, 1000002Dh
0x18011067a  mov     ecx, edi
0x18011067c  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180110682  cmp     eax, 2
0x180110685  jnz     short loc_18011069D
0x180110687  mov     rcx, [rbp+5Fh]; this
0x18011068b  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\lib\\nav\\iehelpe"...
0x180110692  mov     edx, 0FEh; void *
0x180110697  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18011069d  mov     ebx, 80004005h
0x1801106a2  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801106a8  test    al, al
0x1801106aa  jz      loc_1801107BD
0x1801106b0  mov     [rbp+57h+arg_0], 0
0x1801106b8  mov     [rbp+57h+arg_10], 0
0x1801106c0  call    cs:__imp_GetCurrentThreadId
0x1801106c6  mov     ecx, eax
0x1801106c8  lea     rdx, [rbp+57h+arg_10]
0x1801106cc  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1801106d2  mov     ebx, eax
0x1801106d4  test    eax, eax
0x1801106d6  js      loc_1801107BD
0x1801106dc  mov     rcx, [rbp+57h+arg_10]
0x1801106e0  lea     r9, [rbp+57h+dwProcessId]
0x1801106e4  mov     dword ptr [rbp+57h+dwProcessId], 0
0x1801106eb  xor     r8d, r8d
0x1801106ee  xor     edx, edx
0x1801106f0  mov     rax, [rcx]
0x1801106f3  mov     rax, [rax+18h]
0x1801106f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801106fc  mov     eax, dword ptr [rbp+57h+dwProcessId]
0x1801106ff  or      ecx, 0FFFFFFFFh
0x180110702  test    eax, eax
0x180110704  cmovnz  ecx, eax; dwProcessId
0x180110707  call    cs:__imp_AllowSetForegroundWindow
0x18011070d  mov     rcx, [rbp+57h+arg_10]
0x180110711  lea     r9, [rbp+57h+arg_8]
0x180110715  mov     [rbp+57h+arg_8], 0
0x18011071d  lea     r8, IID_IUnknown
0x180110724  lea     rdx, CLSID_CShdocvwBroker
0x18011072b  mov     rax, [rcx]
0x18011072e  mov     rax, [rax+30h]
0x180110732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110737  mov     ebx, eax
0x180110739  test    eax, eax
0x18011073b  js      short loc_180110769
0x18011073d  mov     rcx, [rbp+57h+arg_8]
0x180110741  lea     r8, [rbp+57h+arg_0]
0x180110745  lea     rdx, IID_IDualEngineBroker
0x18011074c  mov     rax, [rcx]
0x18011074f  mov     rax, [rax]
0x180110752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110757  mov     rcx, [rbp+57h+arg_8]
0x18011075b  mov     ebx, eax
0x18011075d  mov     rax, [rcx]
0x180110760  mov     rax, [rax+10h]
0x180110764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110769  mov     rcx, [rbp+57h+arg_10]
0x18011076d  mov     rax, [rcx]
0x180110770  mov     rax, [rax+10h]
0x180110774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110779  test    ebx, ebx
0x18011077b  js      short loc_1801107BD
0x18011077d  mov     rcx, [rbp+57h+arg_0]
0x180110781  lea     rdx, aResIesetupDllI; "res://iesetup.dll/IESechelp.htm"
0x180110788  xor     r9d, r9d
0x18011078b  mov     qword ptr [rsp+0D0h+var_B0], 0
0x180110794  xor     r8d, r8d
0x180110797  mov     rax, [rcx]
0x18011079a  mov     rax, [rax+40h]
0x18011079e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801107a3  mov     rcx, [rbp+57h+arg_0]
0x1801107a7  mov     ebx, eax
0x1801107a9  mov     rax, [rcx]
0x1801107ac  mov     rax, [rax+10h]
0x1801107b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801107b5  test    ebx, ebx
0x1801107b7  jns     loc_18011092D
0x1801107bd  mov     ecx, edi
0x1801107bf  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1801107c5  cmp     eax, 2
0x1801107c8  jz      short loc_1801107DF
0x1801107ca  xor     edx, edx
0x1801107cc  lea     rcx, aResIesetupDllI; "res://iesetup.dll/IESechelp.htm"
0x1801107d3  xor     dil, dil
0x1801107d6  call    IsProtectedModeURL
0x1801107db  test    eax, eax
0x1801107dd  jnz     short loc_1801107E2
0x1801107df  mov     dil, 1
0x1801107e2  xor     edx, edx; int
0x1801107e4  mov     dword ptr [rbp+57h+dwProcessId], 0
0x1801107eb  lea     rax, [rbp+57h+arg_8]
0x1801107ef  mov     [rbp+57h+arg_8], 0
0x1801107f7  mov     [rsp+30h], rax; unsigned __int16 **
0x1801107fc  lea     rcx, aResIesetupDllI; "res://iesetup.dll/IESechelp.htm"
0x180110803  lea     rax, [rbp+57h+dwProcessId]
0x180110807  mov     [rsp+0D0h+var_A8], 0; int *
0x180110810  lea     r8d, [rdx+1]; int
0x180110814  mov     qword ptr [rsp+0D0h+var_B0], rax; dwProcessId
0x180110819  mov     r9d, 8000h; unsigned int
0x18011081f  call    ?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z; LCIEGetRedirectionPolicyForURL2(ushort const *,int,int,ulong,ulong *,int *,ushort * *)
0x180110824  or      ecx, 0FFFFFFFFh; dwProcessId
0x180110827  mov     [rbp+57h+arg_10], 0
0x18011082f  call    cs:__imp_AllowSetForegroundWindow
0x180110835  mov     r9, [rbp+57h+arg_8]; int
0x180110839  lea     rdx, [rbp+57h+arg_10]; int
0x18011083d  mov     r8b, dil; int
0x180110840  call    CoCreateLocalServerIE
0x180110845  test    eax, eax
0x180110847  js      loc_180110923
0x18011084d  xor     eax, eax
0x18011084f  lea     rcx, aResIesetupDllI; "res://iesetup.dll/IESechelp.htm"
0x180110856  xorps   xmm0, xmm0
0x180110859  mov     [rbp+57h+var_80], rax
0x18011085d  mov     [rbp+57h+var_38], rax
0x180110861  xorps   xmm1, xmm1
0x180110864  mov     [rbp+57h+var_50], rax
0x180110868  mov     [rbp+57h+var_68], rax
0x18011086c  mov     [rbp+57h+var_20], rax
0x180110870  mov     eax, 3
0x180110875  movups  [rbp+57h+var_78], xmm1
0x180110879  mov     word ptr [rbp+57h+var_78], ax
0x18011087d  mov     eax, 8
0x180110882  movups  xmmword ptr [rbp+57h+bstrString], xmm0
0x180110886  mov     word ptr [rbp+57h+bstrString], ax
0x18011088a  movups  xmmword ptr [rbp+57h+var_48], xmm1
0x18011088e  mov     dword ptr [rbp+57h+var_78+8], 0
0x180110895  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180110899  movups  [rbp+57h+var_30], xmm0
0x18011089d  call    cs:__imp_SysAllocString
0x1801108a3  mov     [rbp+57h+bstrString+8], rax
0x1801108a7  test    rax, rax
0x1801108aa  jz      short loc_1801108FD
0x1801108ac  mov     rcx, [rbp+57h+arg_10]
0x1801108b0  or      edx, 0FFFFFFFFh
0x1801108b3  mov     rax, [rcx]
0x1801108b6  mov     rax, [rax+148h]
0x1801108bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801108c2  mov     rcx, [rbp+57h+arg_10]
0x1801108c6  lea     rdx, [rbp+57h+var_48]
0x1801108ca  mov     [rsp+0D0h+var_A8], rdx
0x1801108cf  lea     r9, [rbp+57h+var_60]
0x1801108d3  lea     rdx, [rbp+57h+var_30]
0x1801108d7  mov     qword ptr [rsp+0D0h+var_B0], rdx
0x1801108dc  lea     r8, [rbp+57h+var_78]
0x1801108e0  mov     rax, [rcx]
0x1801108e3  lea     rdx, [rbp+57h+bstrString]
0x1801108e7  mov     rax, [rax+1A0h]
0x1801108ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801108f3  mov     rcx, [rbp+57h+bstrString+8]; bstrString
0x1801108f7  call    cs:__imp_SysFreeString
0x1801108fd  mov     rcx, [rbp+57h+var_60+8]; bstrString
0x180110901  call    cs:__imp_SysFreeString
0x180110907  mov     rcx, [rbp+57h+var_48+8]; bstrString
0x18011090b  call    cs:__imp_SysFreeString
0x180110911  mov     rcx, [rbp+57h+arg_10]
0x180110915  mov     rax, [rcx]
0x180110918  mov     rax, [rax+10h]
0x18011091c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110921  xor     ebx, ebx
0x180110923  mov     rcx, [rbp+57h+arg_8]; bstrString
0x180110927  call    cs:__imp_SysFreeString
0x18011092d  mov     eax, ebx
0x18011092f  add     rsp, 0C0h
0x180110936  pop     rdi
0x180110937  pop     rbx
0x180110938  pop     rbp
0x180110939  retn
```
