# CLocalDisconnectPlugin::Finish(void)

- ea: `0x18005a0d0`
- end: `0x18005a6e3`
- name: `?Finish@CLocalDisconnectPlugin@@UEAAJXZ`
- size: `1555`
- prototype: `__int64 __fastcall(CLocalDisconnectPlugin *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006a74`
- `0x18000d144`
- `0x18000d9fc`
- `0x180025570`
- `0x1800256d8`
- `0x1800361dc`
- `0x18003664c`
- `0x180053f54`
- `0x1800552d0`
- `0x1800567bc`
- `0x18005929c`
- `0x180059ba8`
- `0x18005a0d0`
- `0x18005ba70`
- `0x18005bbe4`
- `0x18005f594`
- `0x18007728a`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `SHELL32!__imp_LogoffWindowsDialog` at `0x18005a63c`
- `SHELL32!__imp_LogoffWindowsDialog` at `0x18005a63c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a398`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a4d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a398`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a4d7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a32f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a3d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a32f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a3d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a368`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a40d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a45a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a4a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a368`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a40d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a45a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a4a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005a4fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005a4fb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005a537`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005a537`

## string_xrefs

- `0x18005a1d3`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005a27e`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005a4f4`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
__int64 __fastcall CLocalDisconnectPlugin::Finish(CLocalDisconnectPlugin *this)
{
  int v2; // eax
  HKEY v3; // rbx
  unsigned int v4; // r14d
  _DWORD *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx
  signed int v9; // eax
  int v10; // eax
  LSTATUS v11; // eax
  bool v12; // sf
  int v13; // eax
  bool v14; // sf
  int v15; // eax
  bool v16; // sf
  int v17; // eax
  bool v18; // sf
  int v19; // eax
  bool v20; // sf
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  int ActivationFactory; // eax
  unsigned int v25; // edi
  __int64 v26; // rcx
  void (*v27)(void); // rax
  int v28; // eax
  HRESULT v29; // edx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 *v32; // rcx
  __int64 v33; // rcx
  __int64 *v35; // rcx
  __int64 v36; // rcx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  int dwOptionsc; // [rsp+20h] [rbp-E0h]
  int dwOptionsd; // [rsp+20h] [rbp-E0h]
  int dwOptionse; // [rsp+20h] [rbp-E0h]
  __int64 v43; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v44; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  void **v50; // [rsp+A0h] [rbp-60h] BYREF
  int v51; // [rsp+A8h] [rbp-58h] BYREF
  char v52; // [rsp+ACh] [rbp-54h]
  int v53; // [rsp+D0h] [rbp-30h] BYREF
  const char *v54; // [rsp+D8h] [rbp-28h]
  __int64 v55; // [rsp+E0h] [rbp-20h]
  char v56; // [rsp+E8h] [rbp-18h]
  int v57; // [rsp+F0h] [rbp-10h]
  _BYTE v58[152]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v59; // [rsp+190h] [rbp+90h]
  int v60; // [rsp+1A0h] [rbp+A0h]
  __int64 v61; // [rsp+1A8h] [rbp+A8h]
  int *v62; // [rsp+1B0h] [rbp+B0h]
  __int64 v63; // [rsp+1B8h] [rbp+B8h]
  __int64 v64; // [rsp+1C0h] [rbp+C0h]
  void ***v65; // [rsp+1C8h] [rbp+C8h]
  __int64 v66; // [rsp+1D0h] [rbp+D0h]
  int v67; // [rsp+1D8h] [rbp+D8h]
  int *v68; // [rsp+1E0h] [rbp+E0h]
  char v69; // [rsp+1E8h] [rbp+E8h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v51 = 0;
  v52 = 0;
  v56 = 0;
  v53 = 0;
  v54 = "DisconnectLocalFlow";
  v55 = 0;
  v57 = 0;
  v59 = 0;
  memset_0(v58, 0, sizeof(v58));
  v63 = 0;
  v61 = 0;
  v60 = 1;
  v62 = &v51;
  v64 = 0;
  v65 = &v50;
  v66 = 0;
  v68 = &v53;
  v67 = 0;
  v69 = 0;
  v50 = &TaskFlowTelemetry::DisconnectLocalFlow::`vftable';
  TaskFlowTelemetry::DisconnectLocalFlow::StartActivity((TaskFlowTelemetry::DisconnectLocalFlow *)&v50);
  hKey = 0;
  v2 = CLocalDisconnectPlugin::DisconnectLocalUser(
         (CLocalDisconnectPlugin *)((char *)this - 40),
         (struct IUserData **)&hKey);
  v3 = hKey;
  v4 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v2,
      dwOptions);
    SQMFlowFailure(3u, v4);
    v5 = (_DWORD *)*((_QWORD *)TaskFlowTelemetry::Instance() + 1);
    if ( v5 && *v5 )
    {
      TaskFlowTelemetry::Instance();
      TaskFlowTelemetry::TaskFlowFailure_(v8, 3, v4);
    }
    if ( (Microsoft_Windows_User_ControlPanelEnableBits & 8) != 0 )
      McTemplateU0zq_EventWriteTransfer(v7, v6, L"DisconnectLocalUser", v4);
LABEL_57:
    wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v50, v4);
    if ( v3 )
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)v3 + 16LL))(v3);
    v50 = &TaskFlowTelemetry::DisconnectLocalFlow::`vftable';
    wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v50);
    wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)&v50);
    return v4;
  }
  *(_DWORD *)Data = 1;
  v9 = _RegSetKeyValue(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\ValidateUsername",
         L"Enabled",
         4u,
         Data,
         4u);
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v9,
      dwOptionsa);
  *(_QWORD *)Data = v3;
  if ( v3 )
    (*(void (__fastcall **)(HKEY))(*(_QWORD *)v3 + 8LL))(v3);
  ClearAutologon(Data);
  v10 = (*(__int64 (__fastcall **)(HKEY, _QWORD))(*(_QWORD *)v3 + 80LL))(v3, *((_QWORD *)this + 13));
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v10,
      dwOptionsa);
  hKey = 0;
  v11 = RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountState",
          0,
          0,
          1u,
          0xF003Fu,
          0,
          &hKey,
          0);
  v12 = v11 < 0;
  if ( v11 > 0 )
    v12 = 1;
  if ( !v12 )
  {
    *(_DWORD *)Data = 1;
    v13 = RegSetValueExW(hKey, L"ExplicitLocal", 0, 4u, Data, 4u);
    v14 = v13 < 0;
    if ( v13 > 0 )
    {
      v13 = (unsigned __int16)v13 | 0x80070000;
      v14 = v13 < 0;
    }
    if ( v14 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1A5,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)(unsigned int)v13,
        dwOptionsb);
    RegCloseKey(hKey);
  }
  phkResult = 0;
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture",
          0,
          0,
          0,
          2u,
          0,
          &phkResult,
          0) )
  {
    v15 = RegSetValueExW(phkResult, L"FirstName", 0, 1u, (const BYTE *)&Class, 2u);
    v16 = v15 < 0;
    if ( v15 > 0 )
    {
      v15 = (unsigned __int16)v15 | 0x80070000;
      v16 = v15 < 0;
    }
    if ( v16 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1AE,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)(unsigned int)v15,
        dwOptionsd);
    v17 = RegSetValueExW(phkResult, L"LastName", 0, 1u, (const BYTE *)&Class, 2u);
    v18 = v17 < 0;
    if ( v17 > 0 )
    {
      v17 = (unsigned __int16)v17 | 0x80070000;
      v18 = v17 < 0;
    }
    if ( v18 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)(unsigned int)v17,
        dwOptionse);
    v19 = RegSetValueExW(phkResult, L"DisplayName", 0, 1u, (const BYTE *)&Class, 2u);
    v20 = v19 < 0;
    if ( v19 > 0 )
    {
      v19 = (unsigned __int16)v19 | 0x80070000;
      v20 = v19 < 0;
    }
    if ( v20 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)(unsigned int)v19,
        dwOptionsc);
    RegCloseKey(phkResult);
  }
  v43 = 0;
  string = 0;
  v21 = WindowsCreateStringReference(
          L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
          0x40u,
          &hstringHeader,
          &string);
  if ( v21 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
    JUMPOUT(0x18005A6E2LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &v43);
  v25 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v44 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v43 + 248LL))(v43, &v44);
    v25 = v28;
    if ( v28 >= 0 )
    {
      v28 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
              v44,
              v29,
              v30);
      v25 = v28;
      if ( v28 >= 0 )
      {
        LogoffWindowsDialog(0);
        v35 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
        }
        v36 = v43;
        if ( v43 )
        {
          v43 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        }
        goto LABEL_57;
      }
      v31 = 442;
    }
    else
    {
      v31 = 441;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v28,
      dwOptionsc);
    v32 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
    }
    v33 = v43;
    if ( v43 )
    {
      v43 = 0;
      v27 = *(void (**)(void))(*(_QWORD *)v33 + 16LL);
      goto LABEL_49;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)ActivationFactory,
      dwOptionsc);
    v26 = v43;
    if ( v43 )
    {
      v43 = 0;
      v27 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
LABEL_49:
      v27();
    }
  }
  if ( v3 )
    (*(void (__fastcall **)(HKEY))(*(_QWORD *)v3 + 16LL))(v3);
  v50 = &TaskFlowTelemetry::DisconnectLocalFlow::`vftable';
  wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v50);
  wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)&v50);
  return v25;
}

```

## disassembly

```asm
0x18005a0d0  push    rbp
0x18005a0d2  push    rbx
0x18005a0d3  push    rsi
0x18005a0d4  push    rdi
0x18005a0d5  push    r12
0x18005a0d7  push    r13
0x18005a0d9  push    r14
0x18005a0db  push    r15
0x18005a0dd  lea     rbp, [rsp-108h]
0x18005a0e5  sub     rsp, 208h
0x18005a0ec  mov     rax, cs:__security_cookie
0x18005a0f3  xor     rax, rsp
0x18005a0f6  mov     [rbp+140h+var_50], rax
0x18005a0fd  xor     r15d, r15d
0x18005a100  lea     rax, aDisconnectloca_0; "DisconnectLocalFlow"
0x18005a107  mov     rdi, rcx
0x18005a10a  mov     [rbp+140h+var_198], r15d
0x18005a10e  xorps   xmm0, xmm0
0x18005a111  mov     [rbp+140h+var_194], r15b
0x18005a115  lea     rcx, [rbp+140h+var_148]; void *
0x18005a119  mov     [rbp+140h+var_158], r15b
0x18005a11d  xor     edx, edx; Val
0x18005a11f  mov     [rbp+140h+var_170], r15d
0x18005a123  mov     r8d, 98h; Size
0x18005a129  mov     [rbp+140h+var_168], rax
0x18005a12d  mov     [rbp+140h+var_160], r15
0x18005a131  mov     [rbp+140h+var_150], r15d
0x18005a135  movdqa  [rbp+140h+var_B0], xmm0
0x18005a13d  call    memset_0
0x18005a142  xor     eax, eax
0x18005a144  mov     [rbp+140h+var_88], r15
0x18005a14b  mov     [rbp+140h+var_98], rax
0x18005a152  lea     esi, [r15+1]
0x18005a156  lea     rax, [rbp+140h+var_198]
0x18005a15a  mov     [rbp+140h+var_A0], esi
0x18005a160  mov     [rbp+140h+var_90], rax
0x18005a167  lea     r12, ??_7DisconnectLocalFlow@TaskFlowTelemetry@@6B@; const TaskFlowTelemetry::DisconnectLocalFlow::`vftable'
0x18005a16e  lea     rax, [rbp+140h+var_1A0]
0x18005a172  mov     [rbp+140h+var_80], r15
0x18005a179  mov     [rbp+140h+var_78], rax
0x18005a180  lea     rcx, [rbp+140h+var_1A0]; this
0x18005a184  lea     rax, [rbp+140h+var_170]
0x18005a188  mov     [rbp+140h+var_70], r15
0x18005a18f  mov     [rbp+140h+var_60], rax
0x18005a196  mov     [rbp+140h+var_68], r15d
0x18005a19d  mov     [rbp+140h+var_58], r15b
0x18005a1a4  mov     [rbp+140h+var_1A0], r12
0x18005a1a8  call    ?StartActivity@DisconnectLocalFlow@TaskFlowTelemetry@@QEAAXXZ; TaskFlowTelemetry::DisconnectLocalFlow::StartActivity(void)
0x18005a1ad  lea     rcx, [rdi-28h]; this
0x18005a1b1  mov     [rsp+240h+hKey], r15
0x18005a1b6  lea     rdx, [rsp+240h+hKey]; struct IUserData **
0x18005a1bb  call    ?DisconnectLocalUser@CLocalDisconnectPlugin@@AEAAJPEAPEAUIUserData@@@Z; CLocalDisconnectPlugin::DisconnectLocalUser(IUserData * *)
0x18005a1c0  mov     rbx, [rsp+240h+hKey]
0x18005a1c5  mov     r14d, eax
0x18005a1c8  test    eax, eax
0x18005a1ca  jns     short loc_18005A238
0x18005a1cc  mov     rcx, [rbp+148h]; this
0x18005a1d3  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005a1da  mov     r9d, eax; char *
0x18005a1dd  mov     edx, 193h; void *
0x18005a1e2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a1e7  lea     edi, [rsi+2]
0x18005a1ea  mov     edx, r14d; int
0x18005a1ed  mov     ecx, edi; unsigned int
0x18005a1ef  call    ?SQMFlowFailure@@YAXKJ@Z; SQMFlowFailure(ulong,long)
0x18005a1f4  call    ?Instance@TaskFlowTelemetry@@KAPEAV1@XZ; TaskFlowTelemetry::Instance(void)
0x18005a1f9  mov     rax, [rax+8]
0x18005a1fd  test    rax, rax
0x18005a200  jz      short loc_18005A217
0x18005a202  mov     eax, [rax]
0x18005a204  test    eax, eax
0x18005a206  jz      short loc_18005A217
0x18005a208  call    ?Instance@TaskFlowTelemetry@@KAPEAV1@XZ; TaskFlowTelemetry::Instance(void)
0x18005a20d  mov     r8d, r14d
0x18005a210  mov     edx, edi
0x18005a212  call    ?TaskFlowFailure_@TaskFlowTelemetry@@QEBAXW4TASK_FLOW_ID@@J@Z; TaskFlowTelemetry::TaskFlowFailure_(TASK_FLOW_ID,long)
0x18005a217  test    cs:Microsoft_Windows_User_ControlPanelEnableBits, 8
0x18005a21e  jz      loc_18005A67F
0x18005a224  mov     r9d, r14d
0x18005a227  lea     r8, aDisconnectloca; "DisconnectLocalUser"
0x18005a22e  call    McTemplateU0zq_EventWriteTransfer
0x18005a233  jmp     loc_18005A67F
0x18005a238  mov     r13d, 4
0x18005a23e  mov     dword ptr [rsp+240h+Data], esi
0x18005a242  lea     rax, [rsp+240h+Data]
0x18005a247  mov     [rsp+240h+samDesired], r13d; unsigned int
0x18005a24c  mov     r9d, r13d; unsigned int
0x18005a24f  mov     qword ptr [rsp+240h+dwOptions], rax; int
0x18005a254  lea     r8, aEnabled; "Enabled"
0x18005a25b  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18005a262  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005a269  call    ?_RegSetKeyValue@@YAKPEAUHKEY__@@PEBG1KPEBXK@Z; _RegSetKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18005a26e  mov     r12d, 80070000h
0x18005a274  test    eax, eax
0x18005a276  jle     short loc_18005A27E
0x18005a278  movzx   eax, ax
0x18005a27b  or      eax, r12d
0x18005a27e  lea     rsi, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005a285  test    eax, eax
0x18005a287  jns     short loc_18005A2A0
0x18005a289  mov     rcx, [rbp+148h]; this
0x18005a290  mov     r9d, eax; char *
0x18005a293  mov     r8, rsi; unsigned int
0x18005a296  mov     edx, 19Ah; void *
0x18005a29b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a2a0  mov     qword ptr [rsp+240h+Data], rbx
0x18005a2a5  test    rbx, rbx
0x18005a2a8  jz      short loc_18005A2B9
0x18005a2aa  mov     rax, [rbx]
0x18005a2ad  mov     rcx, rbx
0x18005a2b0  mov     rax, [rax+8]
0x18005a2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2b9  lea     rcx, [rsp+240h+Data]
0x18005a2be  call    ?ClearAutologon@@YAXV?$ComPtr@UIUserData@@@WRL@Microsoft@@@Z; ClearAutologon(Microsoft::WRL::ComPtr<IUserData>)
0x18005a2c3  mov     rax, [rbx]
0x18005a2c6  mov     rcx, rbx
0x18005a2c9  mov     rdx, [rdi+68h]
0x18005a2cd  mov     rax, [rax+50h]
0x18005a2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2d6  test    eax, eax
0x18005a2d8  jns     short loc_18005A2F1
0x18005a2da  mov     rcx, [rbp+148h]; this
0x18005a2e1  mov     r9d, eax; char *
0x18005a2e4  mov     r8, rsi; unsigned int
0x18005a2e7  mov     edx, 19Fh; void *
0x18005a2ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a2f1  mov     [rsp+240h+lpdwDisposition], r15; lpdwDisposition
0x18005a2f6  lea     rax, [rsp+240h+hKey]
0x18005a2fb  mov     [rsp+240h+phkResult], rax; phkResult
0x18005a300  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005a307  mov     [rsp+240h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18005a30c  mov     edi, 1
0x18005a311  mov     [rsp+240h+samDesired], 0F003Fh; samDesired
0x18005a319  xor     r9d, r9d; lpClass
0x18005a31c  xor     r8d, r8d; Reserved
0x18005a31f  mov     [rsp+240h+dwOptions], edi; dwOptions
0x18005a323  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005a32a  mov     [rsp+240h+hKey], r15
0x18005a32f  call    cs:__imp_RegCreateKeyExW
0x18005a335  test    eax, eax
0x18005a337  jle     short loc_18005A341
0x18005a339  movzx   eax, ax
0x18005a33c  or      eax, r12d
0x18005a33f  test    eax, eax
0x18005a341  js      short loc_18005A39E
0x18005a343  mov     rcx, [rsp+240h+hKey]; hKey
0x18005a348  lea     rax, [rsp+240h+Data]
0x18005a34d  mov     [rsp+240h+samDesired], r13d; cbData
0x18005a352  lea     rdx, aExplicitlocal; "ExplicitLocal"
0x18005a359  mov     r9d, r13d; dwType
0x18005a35c  mov     qword ptr [rsp+240h+dwOptions], rax; int
0x18005a361  xor     r8d, r8d; Reserved
0x18005a364  mov     dword ptr [rsp+240h+Data], edi
0x18005a368  call    cs:__imp_RegSetValueExW
0x18005a36e  test    eax, eax
0x18005a370  jle     short loc_18005A37A
0x18005a372  movzx   eax, ax
0x18005a375  or      eax, r12d
0x18005a378  test    eax, eax
0x18005a37a  jns     short loc_18005A393
0x18005a37c  mov     rcx, [rbp+148h]; this
0x18005a383  mov     r9d, eax; char *
0x18005a386  mov     r8, rsi; unsigned int
0x18005a389  mov     edx, 1A5h; void *
0x18005a38e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a393  mov     rcx, [rsp+240h+hKey]; hKey
0x18005a398  call    cs:__imp_RegCloseKey
0x18005a39e  mov     [rsp+240h+lpdwDisposition], r15; lpdwDisposition
0x18005a3a3  lea     rax, [rsp+240h+var_1D0]
0x18005a3a8  mov     [rsp+240h+phkResult], rax; phkResult
0x18005a3ad  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005a3b4  mov     [rsp+240h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18005a3b9  mov     edi, 2
0x18005a3be  mov     [rsp+240h+samDesired], edi; samDesired
0x18005a3c2  xor     r9d, r9d; lpClass
0x18005a3c5  xor     r8d, r8d; Reserved
0x18005a3c8  mov     [rsp+240h+dwOptions], r15d; dwOptions
0x18005a3cd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005a3d4  mov     [rsp+240h+var_1D0], r15
0x18005a3d9  call    cs:__imp_RegCreateKeyExW
0x18005a3df  test    eax, eax
0x18005a3e1  jnz     loc_18005A4DD
0x18005a3e7  mov     rcx, [rsp+240h+var_1D0]; hKey
0x18005a3ec  lea     rax, Class
0x18005a3f3  lea     r13d, [rdi-1]
0x18005a3f7  mov     [rsp+240h+samDesired], edi; cbData
0x18005a3fb  mov     r9d, r13d; dwType
0x18005a3fe  mov     qword ptr [rsp+240h+dwOptions], rax; int
0x18005a403  xor     r8d, r8d; Reserved
0x18005a406  lea     rdx, aFirstname; "FirstName"
0x18005a40d  call    cs:__imp_RegSetValueExW
0x18005a413  test    eax, eax
0x18005a415  jle     short loc_18005A41F
0x18005a417  movzx   eax, ax
0x18005a41a  or      eax, r12d
0x18005a41d  test    eax, eax
0x18005a41f  jns     short loc_18005A438
0x18005a421  mov     rcx, [rbp+148h]; this
0x18005a428  mov     r9d, eax; char *
0x18005a42b  mov     r8, rsi; unsigned int
0x18005a42e  mov     edx, 1AEh; void *
0x18005a433  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a438  mov     rcx, [rsp+240h+var_1D0]; hKey
0x18005a43d  lea     rax, Class
0x18005a444  mov     [rsp+240h+samDesired], edi; cbData
0x18005a448  lea     rdx, aLastname; "LastName"
0x18005a44f  mov     r9d, r13d; dwType
0x18005a452  mov     qword ptr [rsp+240h+dwOptions], rax; int
0x18005a457  xor     r8d, r8d; Reserved
0x18005a45a  call    cs:__imp_RegSetValueExW
0x18005a460  test    eax, eax
0x18005a462  jle     short loc_18005A46C
0x18005a464  movzx   eax, ax
0x18005a467  or      eax, r12d
0x18005a46a  test    eax, eax
0x18005a46c  jns     short loc_18005A485
0x18005a46e  mov     rcx, [rbp+148h]; this
0x18005a475  mov     r9d, eax; char *
0x18005a478  mov     r8, rsi; unsigned int
0x18005a47b  mov     edx, 1AFh; void *
0x18005a480  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a485  mov     rcx, [rsp+240h+var_1D0]; hKey
0x18005a48a  lea     rax, Class
0x18005a491  mov     [rsp+240h+samDesired], edi; cbData
0x18005a495  lea     rdx, aDisplayname; "DisplayName"
0x18005a49c  mov     r9d, r13d; dwType
0x18005a49f  mov     qword ptr [rsp+240h+dwOptions], rax; int
0x18005a4a4  xor     r8d, r8d; Reserved
0x18005a4a7  call    cs:__imp_RegSetValueExW
0x18005a4ad  test    eax, eax
0x18005a4af  jle     short loc_18005A4B9
0x18005a4b1  movzx   eax, ax
0x18005a4b4  or      eax, r12d
0x18005a4b7  test    eax, eax
0x18005a4b9  jns     short loc_18005A4D2
0x18005a4bb  mov     rcx, [rbp+148h]; this
0x18005a4c2  mov     r9d, eax; char *
0x18005a4c5  mov     r8, rsi; unsigned int
0x18005a4c8  mov     edx, 1B0h; void *
0x18005a4cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a4d2  mov     rcx, [rsp+240h+var_1D0]; hKey
0x18005a4d7  call    cs:__imp_RegCloseKey
0x18005a4dd  lea     r9, [rbp+140h+string]; string
0x18005a4e1  mov     [rsp+240h+var_1F0], r15
0x18005a4e6  lea     r8, [rsp+240h+hstringHeader]; hstringHeader
0x18005a4eb  mov     [rbp+140h+string], r15
0x18005a4ef  mov     edx, 40h ; '@'; length
0x18005a4f4  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18005a4fb  call    cs:__imp_WindowsCreateStringReference
0x18005a501  test    eax, eax
0x18005a503  js      loc_18005A6DB
0x18005a509  mov     rcx, [rsp+240h+var_1F0]
0x18005a50e  mov     rdi, [rbp+140h+string]
0x18005a512  test    rcx, rcx
0x18005a515  jz      short loc_18005A528
0x18005a517  mov     [rsp+240h+var_1F0], r15
0x18005a51c  mov     rax, [rcx]
0x18005a51f  mov     rax, [rax+10h]
0x18005a523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a528  lea     r8, [rsp+240h+var_1F0]
0x18005a52d  mov     rcx, rdi
0x18005a530  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x18005a537  call    cs:__imp_RoGetActivationFactory
0x18005a53d  mov     edi, eax
0x18005a53f  test    eax, eax
0x18005a541  jns     short loc_18005A579
0x18005a543  mov     rcx, [rbp+148h]; this
0x18005a54a  mov     r9d, eax; char *
0x18005a54d  mov     r8, rsi; unsigned int
0x18005a550  mov     edx, 1B6h; void *
0x18005a555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a55a  mov     rcx, [rsp+240h+var_1F0]
0x18005a55f  test    rcx, rcx
0x18005a562  jz      loc_18005A605
0x18005a568  mov     [rsp+240h+var_1F0], r15
0x18005a56d  mov     rdx, [rcx]
0x18005a570  mov     rax, [rdx+10h]
0x18005a574  jmp     loc_18005A600
0x18005a579  mov     rcx, [rsp+240h+var_1F0]
0x18005a57e  lea     rdx, [rsp+240h+var_1E8]
0x18005a583  mov     [rsp+240h+var_1E8], r15
0x18005a588  mov     rax, [rcx]
0x18005a58b  mov     rax, [rax+0F8h]
0x18005a592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a597  mov     edi, eax
0x18005a599  test    eax, eax
0x18005a59b  jns     short loc_18005A5A4
0x18005a59d  mov     edx, 1B9h
0x18005a5a2  jmp     short loc_18005A5BD
0x18005a5a4  mov     rcx, [rsp+240h+var_1E8]
0x18005a5a9  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x18005a5ae  mov     edi, eax
0x18005a5b0  test    eax, eax
0x18005a5b2  jns     loc_18005A63A
0x18005a5b8  mov     edx, 1BAh; void *
0x18005a5bd  mov     rcx, [rbp+148h]; this
0x18005a5c4  mov     r9d, eax; char *
0x18005a5c7  mov     r8, rsi; unsigned int
0x18005a5ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a5cf  mov     rcx, [rsp+240h+var_1E8]
  ... truncated ...
```
