# ServiceDataSession::EnsureIntializedSecurityAndAppInfo(void)

- ea: `0x18000a780`
- end: `0x18000ae78`
- name: `?EnsureIntializedSecurityAndAppInfo@ServiceDataSession@@AEAAJXZ`
- size: `1784`
- prototype: `__int64 __fastcall(ServiceDataSession *__hidden this)`
- caller_count: `22`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800033c0`
- `0x180008870`
- `0x1800096d0`
- `0x1800097e4`
- `0x180009918`
- `0x180009990`
- `0x180009a90`
- `0x18000a530`
- `0x18000a640`
- `0x18000c8e0`
- `0x18000d8b0`
- `0x1800201b0`
- `0x180020a9c`
- `0x180030978`
- `0x1800353b0`
- `0x180058f88`
- `0x18005f400`
- `0x180061110`
- `0x180066dd8`
- `0x180068458`
- `0x18009f4f0`
- `0x1800a0274`

## callees

- `0x180007760`
- `0x180008f0c`
- `0x18000a780`
- `0x18003ed9c`
- `0x1800a4dfc`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a7a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a7a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000adf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000adf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae10`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18000a899`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18000a899`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000a856`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000a856`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a8c3`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a8f4`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a92d`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a95e`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a997`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a9d0`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000aa0d`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000aa4a`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000aa7c`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000aab9`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000aaf2`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ab2e`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ab6a`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000abaa`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000abe3`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ac1f`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ac5b`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ac97`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000acd3`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ad04`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ad35`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a8c3`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a8f4`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a92d`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a95e`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a997`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a9d0`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000aa0d`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000aa4a`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000aa7c`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000aab9`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000aaf2`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ab2e`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ab6a`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000abaa`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000abe3`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ac1f`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ac5b`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ac97`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000acd3`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ad04`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000ad35`

## string_xrefs

- `0x18000a873`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000ada8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000aaeb`: `userDataTasks`
- `0x18000ac90`: `userDataTasksSystem`
- `0x18000acfd`: `ID_CAP_COMMS_COMMON`
- `0x18000ad2e`: `ID_CAP_COMMS_SERVICES`

## pseudocode

```c
__int64 __fastcall ServiceDataSession::EnsureIntializedSecurityAndAppInfo(ServiceDataSession *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v3; // r8
  RPC_STATUS v5; // eax
  int RpcClientThreadToken; // esi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // esi
  __int64 v10; // rdx
  unsigned __int8 v11; // r14
  int v12; // esi
  int v13; // esi
  unsigned __int8 v14; // r14
  int v15; // esi
  int v16; // esi
  int v17; // esi
  int v18; // esi
  int v19; // esi
  int v20; // esi
  int v21; // esi
  int v22; // esi
  int v23; // esi
  int v24; // esi
  int v25; // esi
  int v26; // esi
  int v27; // esi
  int v28; // esi
  int v29; // esi
  int v30; // esi
  int v31; // r14d
  int v32; // esi
  int v33; // r15d
  int v34; // esi
  int v35; // ecx
  __int64 v36; // r8
  HANDLE v37; // rcx
  _BYTE v38[8]; // [rsp+30h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-28h] BYREF
  char v40; // [rsp+40h] [rbp-20h] BYREF
  char v41; // [rsp+41h] [rbp-1Fh] BYREF
  char v42; // [rsp+42h] [rbp-1Eh] BYREF
  _BYTE v43[5]; // [rsp+43h] [rbp-1Dh] BYREF
  _BYTE v44[16]; // [rsp+48h] [rbp-18h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1744);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1744));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWATCS>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWATCS>::GetImpl'::`2'::impl)
    && *((_DWORD *)this + 470) )
  {
    *((_DWORD *)this + 447) |= 0x102002u;
    *((_DWORD *)this + 448) |= 0x100000u;
    *((_DWORD *)this + 449) |= 0x100000u;
    *((_DWORD *)this + 446) = 1;
    LeaveCriticalSection(v1);
    return 0;
  }
  if ( *((_DWORD *)this + 446) )
    goto LABEL_102;
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      Udm_IntializedSecurityInfo_START,
      v3,
      1,
      v44);
  v5 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)this + 471);
  RpcClientThreadToken = v5;
  if ( !v5 )
  {
    hObject = 0;
    RpcClientThreadToken = GetRpcClientThreadToken(8u, &hObject);
    if ( RpcClientThreadToken < 0 )
    {
      v8 = 1689;
LABEL_92:
      v10 = 1;
LABEL_93:
      Log_HREvent(
        (unsigned int)RpcClientThreadToken,
        v10,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        v8);
      if ( hObject )
        CloseHandle(hObject);
      goto LABEL_95;
    }
    v38[0] = 0;
    v9 = CapabilityCheck(hObject, L"ID_CAP_APPOINTMENTS", v38);
    if ( v9 < 0 )
    {
      RpcClientThreadToken = v9 | 0x10000000;
      v8 = 1694;
      v10 = 0;
      goto LABEL_93;
    }
    v11 = v38[0];
    v12 = CapabilityCheck(hObject, L"appointments", v38);
    if ( v12 < 0 )
    {
      RpcClientThreadToken = v12 | 0x10000000;
      v8 = 1697;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] | v11 )
      *((_DWORD *)this + 447) |= 1u;
    v13 = CapabilityCheck(hObject, L"ID_CAP_CONTACTS", v38);
    if ( v13 < 0 )
    {
      RpcClientThreadToken = v13 | 0x10000000;
      v8 = 1706;
      v10 = 0;
      goto LABEL_93;
    }
    v14 = v38[0];
    v15 = CapabilityCheck(hObject, L"contacts", v38);
    if ( v15 < 0 )
    {
      RpcClientThreadToken = v15 | 0x10000000;
      v8 = 1709;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] | v14 )
      *((_DWORD *)this + 447) |= 2u;
    v16 = CapabilityCheck(hObject, L"ID_CAP_SMS", v38);
    if ( v16 < 0 )
    {
      RpcClientThreadToken = v16 | 0x10000000;
      v8 = 1717;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] )
      *((_DWORD *)this + 447) |= 0x44u;
    v17 = CapabilityCheck(hObject, L"chat", v38);
    if ( v17 < 0 )
    {
      RpcClientThreadToken = v17 | 0x10000000;
      v8 = 1726;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] )
      *((_DWORD *)this + 447) |= 4u;
    v41 = 0;
    v18 = CapabilityCheck(hObject, L"email", &v41);
    if ( v18 < 0 )
    {
      RpcClientThreadToken = v18 | 0x10000000;
      v8 = 1733;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v41 )
      *((_DWORD *)this + 447) |= 8u;
    v40 = 0;
    v19 = CapabilityCheck(hObject, L"phoneCallHistoryPublic", &v40);
    if ( v19 < 0 )
    {
      RpcClientThreadToken = v19 | 0x10000000;
      v8 = 1740;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v40 )
      goto LABEL_43;
    v20 = CapabilityCheck(hObject, L"phoneCallHistory", &v40);
    if ( v20 < 0 )
    {
      RpcClientThreadToken = v20 | 0x10000000;
      v8 = 1744;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v40 )
LABEL_43:
      *((_DWORD *)this + 447) |= 0x10u;
    v42 = 0;
    v21 = CapabilityCheck(hObject, L"smsSend", &v42);
    if ( v21 < 0 )
    {
      RpcClientThreadToken = v21 | 0x10000000;
      v8 = 1753;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v42 )
      *((_DWORD *)this + 447) |= 0x40u;
    v22 = CapabilityCheck(hObject, L"userDataTasks", v38);
    if ( v22 < 0 )
    {
      RpcClientThreadToken = v22 | 0x10000000;
      v8 = 1759;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] )
      *((_DWORD *)this + 447) |= 0x80u;
    v23 = CapabilityCheck(hObject, L"appointmentsSystem", v38);
    if ( v23 < 0 )
    {
      RpcClientThreadToken = v23 | 0x10000000;
      v8 = 1766;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] )
      *((_DWORD *)this + 447) |= 0x1001u;
    v24 = CapabilityCheck(hObject, L"contactsSystem", v38);
    if ( v24 < 0 )
    {
      RpcClientThreadToken = v24 | 0x10000000;
      v8 = 1773;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] )
      *((_DWORD *)this + 447) |= 0x2002u;
    v43[0] = 0;
    v25 = CapabilityCheck(hObject, L"blockedChatMessages", v43);
    if ( v25 < 0 )
    {
      RpcClientThreadToken = v25 | 0x10000000;
      v8 = 1781;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v43[0] )
      *((_DWORD *)this + 447) |= 0x20u;
    v26 = CapabilityCheck(hObject, L"emailSystem", v38);
    if ( v26 < 0 )
    {
      RpcClientThreadToken = v26 | 0x10000000;
      v8 = 1787;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] )
      *((_DWORD *)this + 447) |= 0x8008u;
    v27 = CapabilityCheck(hObject, L"chatSystem", v38);
    if ( v27 < 0 )
    {
      RpcClientThreadToken = v27 | 0x10000000;
      v8 = 1794;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] )
      *((_DWORD *)this + 447) |= 0x4004u;
    v28 = CapabilityCheck(hObject, L"phoneCallHistorySystem", v38);
    if ( v28 < 0 )
    {
      RpcClientThreadToken = v28 | 0x10000000;
      v8 = 1801;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] )
      *((_DWORD *)this + 447) |= 0x10010u;
    v29 = CapabilityCheck(hObject, L"userDataTasksSystem", v38);
    if ( v29 < 0 )
    {
      RpcClientThreadToken = v29 | 0x10000000;
      v8 = 1808;
      v10 = 0;
      goto LABEL_93;
    }
    if ( v38[0] )
      *((_DWORD *)this + 447) |= 0x20080u;
    v30 = CapabilityCheck(hObject, L"userDataSystem", v38);
    if ( v30 < 0 )
    {
      RpcClientThreadToken = v30 | 0x10000000;
      v8 = 1817;
      v10 = 0;
      goto LABEL_93;
    }
    v31 = v38[0];
    v32 = CapabilityCheck(hObject, L"ID_CAP_COMMS_COMMON", v38);
    if ( v32 < 0 )
    {
      RpcClientThreadToken = v32 | 0x10000000;
      v8 = 1820;
      v10 = 0;
      goto LABEL_93;
    }
    v33 = v38[0];
    v34 = CapabilityCheck(hObject, L"ID_CAP_COMMS_SERVICES", v38);
    if ( v34 < 0 )
    {
      RpcClientThreadToken = v34 | 0x10000000;
      v8 = 1823;
      v10 = 0;
      goto LABEL_93;
    }
    v35 = v33 | v31 | v38[0];
    if ( v38[0] )
      *((_DWORD *)this + 447) |= 0x2002u;
    if ( v35 )
    {
      *((_DWORD *)this + 447) |= 0x100000u;
      *((_DWORD *)this + 448) |= 0x100000u;
      *((_DWORD *)this + 449) |= 0x100000u;
    }
    RpcClientThreadToken = ServiceDataSession::_GetCallerAppDetails(this, hObject);
    if ( RpcClientThreadToken < 0 )
    {
      v8 = 1840;
      goto LABEL_92;
    }
    v37 = hObject;
    *((_DWORD *)this + 446) = 1;
    if ( v37 )
      CloseHandle(v37);
    if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
        Udm_IntializedSecurityInfo_STOP,
        v36,
        1,
        v44);
LABEL_102:
    LeaveCriticalSection(v1);
    return 0;
  }
  if ( v5 > 0 )
    RpcClientThreadToken = (unsigned __int16)v5 | 0x80070000;
  Log_HREvent(
    (unsigned int)RpcClientThreadToken,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
    1686);
LABEL_95:
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      Udm_IntializedSecurityInfo_STOP,
      v7,
      1,
      v44);
  LeaveCriticalSection(v1);
  return (unsigned int)RpcClientThreadToken;
}

```

## disassembly

```asm
0x18000a780  push    rbp
0x18000a782  push    rbx
0x18000a783  push    rdi
0x18000a784  mov     rbp, rsp
0x18000a787  sub     rsp, 60h
0x18000a78b  mov     rax, cs:__security_cookie
0x18000a792  xor     rax, rsp
0x18000a795  mov     [rbp+var_8], rax
0x18000a799  lea     rdi, [rcx+6D0h]
0x18000a7a0  mov     rbx, rcx
0x18000a7a3  mov     rcx, rdi; lpCriticalSection
0x18000a7a6  call    cs:__imp_EnterCriticalSection
0x18000a7ac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWATCS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWATCS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWATCS> `wil::Feature<__WilFeatureTraits_Feature_SWATCS>::GetImpl(void)'::`2'::impl
0x18000a7b3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWATCS@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWATCS>::__private_IsEnabled(void)
0x18000a7b8  test    al, al
0x18000a7ba  jz      short loc_18000A7FD
0x18000a7bc  cmp     dword ptr [rbx+758h], 0
0x18000a7c3  jz      short loc_18000A7FD
0x18000a7c5  or      dword ptr [rbx+6FCh], 102002h
0x18000a7cf  mov     rcx, rdi; lpCriticalSection
0x18000a7d2  or      dword ptr [rbx+700h], 100000h
0x18000a7dc  or      dword ptr [rbx+704h], 100000h
0x18000a7e6  mov     dword ptr [rbx+6F8h], 1
0x18000a7f0  call    cs:__imp_LeaveCriticalSection
0x18000a7f6  xor     eax, eax
0x18000a7f8  jmp     loc_18000AE64
0x18000a7fd  cmp     dword ptr [rbx+6F8h], 0
0x18000a804  mov     [rsp+60h+arg_8], rsi
0x18000a80c  mov     [rsp+60h+arg_10], r14
0x18000a814  mov     [rsp+60h+arg_18], r15
0x18000a81c  jnz     loc_18000AE41
0x18000a822  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, 1
0x18000a829  jz      short loc_18000A84D
0x18000a82b  lea     rax, [rbp+var_18]
0x18000a82f  mov     r9d, 1
0x18000a835  lea     rdx, Udm_IntializedSecurityInfo_START
0x18000a83c  mov     [rsp+60h+var_40], rax
0x18000a841  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x18000a848  call    McGenEventWrite_EventWriteTransfer
0x18000a84d  lea     rdx, [rbx+75Ch]; Pid
0x18000a854  xor     ecx, ecx; Binding
0x18000a856  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000a85c  mov     esi, eax
0x18000a85e  test    eax, eax
0x18000a860  jz      short loc_18000A888
0x18000a862  jle     short loc_18000A86D
0x18000a864  movzx   esi, ax
0x18000a867  or      esi, 80070000h
0x18000a86d  mov     r9d, 696h
0x18000a873  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000a87a  xor     edx, edx
0x18000a87c  mov     ecx, esi
0x18000a87e  call    Log_HREvent
0x18000a883  jmp     loc_18000ADC5
0x18000a888  lea     rdx, [rbp+hObject]
0x18000a88c  mov     [rbp+hObject], 0
0x18000a894  mov     ecx, 8
0x18000a899  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x18000a89f  mov     esi, eax
0x18000a8a1  test    eax, eax
0x18000a8a3  jns     short loc_18000A8B0
0x18000a8a5  mov     r9d, 699h
0x18000a8ab  jmp     loc_18000ADA3
0x18000a8b0  mov     rcx, [rbp+hObject]
0x18000a8b4  lea     r8, [rbp+var_30]
0x18000a8b8  lea     rdx, aIdCapAppointme; "ID_CAP_APPOINTMENTS"
0x18000a8bf  mov     [rbp+var_30], 0
0x18000a8c3  call    cs:__imp_CapabilityCheck
0x18000a8c9  mov     esi, eax
0x18000a8cb  test    eax, eax
0x18000a8cd  jns     short loc_18000A8E0
0x18000a8cf  bts     esi, 1Ch
0x18000a8d3  mov     r9d, 69Eh
0x18000a8d9  xor     edx, edx
0x18000a8db  jmp     loc_18000ADA8
0x18000a8e0  mov     rcx, [rbp+hObject]
0x18000a8e4  lea     r8, [rbp+var_30]
0x18000a8e8  movzx   r14d, [rbp+var_30]
0x18000a8ed  lea     rdx, aAppointments; "appointments"
0x18000a8f4  call    cs:__imp_CapabilityCheck
0x18000a8fa  mov     esi, eax
0x18000a8fc  test    eax, eax
0x18000a8fe  jns     short loc_18000A911
0x18000a900  bts     esi, 1Ch
0x18000a904  mov     r9d, 6A1h
0x18000a90a  xor     edx, edx
0x18000a90c  jmp     loc_18000ADA8
0x18000a911  or      r14b, [rbp+var_30]
0x18000a915  jz      short loc_18000A91E
0x18000a917  or      dword ptr [rbx+6FCh], 1
0x18000a91e  mov     rcx, [rbp+hObject]
0x18000a922  lea     r8, [rbp+var_30]
0x18000a926  lea     rdx, aIdCapContacts; "ID_CAP_CONTACTS"
0x18000a92d  call    cs:__imp_CapabilityCheck
0x18000a933  mov     esi, eax
0x18000a935  test    eax, eax
0x18000a937  jns     short loc_18000A94A
0x18000a939  bts     esi, 1Ch
0x18000a93d  mov     r9d, 6AAh
0x18000a943  xor     edx, edx
0x18000a945  jmp     loc_18000ADA8
0x18000a94a  mov     rcx, [rbp+hObject]
0x18000a94e  lea     r8, [rbp+var_30]
0x18000a952  movzx   r14d, [rbp+var_30]
0x18000a957  lea     rdx, aContacts; "contacts"
0x18000a95e  call    cs:__imp_CapabilityCheck
0x18000a964  mov     esi, eax
0x18000a966  test    eax, eax
0x18000a968  jns     short loc_18000A97B
0x18000a96a  bts     esi, 1Ch
0x18000a96e  mov     r9d, 6ADh
0x18000a974  xor     edx, edx
0x18000a976  jmp     loc_18000ADA8
0x18000a97b  or      r14b, [rbp+var_30]
0x18000a97f  jz      short loc_18000A988
0x18000a981  or      dword ptr [rbx+6FCh], 2
0x18000a988  mov     rcx, [rbp+hObject]
0x18000a98c  lea     r8, [rbp+var_30]
0x18000a990  lea     rdx, aIdCapSms; "ID_CAP_SMS"
0x18000a997  call    cs:__imp_CapabilityCheck
0x18000a99d  mov     esi, eax
0x18000a99f  test    eax, eax
0x18000a9a1  jns     short loc_18000A9B4
0x18000a9a3  bts     esi, 1Ch
0x18000a9a7  mov     r9d, 6B5h
0x18000a9ad  xor     edx, edx
0x18000a9af  jmp     loc_18000ADA8
0x18000a9b4  cmp     [rbp+var_30], 0
0x18000a9b8  jz      short loc_18000A9C1
0x18000a9ba  or      dword ptr [rbx+6FCh], 44h
0x18000a9c1  mov     rcx, [rbp+hObject]
0x18000a9c5  lea     r8, [rbp+var_30]
0x18000a9c9  lea     rdx, aChat; "chat"
0x18000a9d0  call    cs:__imp_CapabilityCheck
0x18000a9d6  mov     esi, eax
0x18000a9d8  test    eax, eax
0x18000a9da  jns     short loc_18000A9ED
0x18000a9dc  bts     esi, 1Ch
0x18000a9e0  mov     r9d, 6BEh
0x18000a9e6  xor     edx, edx
0x18000a9e8  jmp     loc_18000ADA8
0x18000a9ed  cmp     [rbp+var_30], 0
0x18000a9f1  jz      short loc_18000A9FA
0x18000a9f3  or      dword ptr [rbx+6FCh], 4
0x18000a9fa  mov     rcx, [rbp+hObject]
0x18000a9fe  lea     r8, [rbp+var_1F]
0x18000aa02  lea     rdx, aEmail_0; "email"
0x18000aa09  mov     [rbp+var_1F], 0
0x18000aa0d  call    cs:__imp_CapabilityCheck
0x18000aa13  mov     esi, eax
0x18000aa15  test    eax, eax
0x18000aa17  jns     short loc_18000AA2A
0x18000aa19  bts     esi, 1Ch
0x18000aa1d  mov     r9d, 6C5h
0x18000aa23  xor     edx, edx
0x18000aa25  jmp     loc_18000ADA8
0x18000aa2a  cmp     [rbp+var_1F], 0
0x18000aa2e  jz      short loc_18000AA37
0x18000aa30  or      dword ptr [rbx+6FCh], 8
0x18000aa37  mov     rcx, [rbp+hObject]
0x18000aa3b  lea     r8, [rbp+var_20]
0x18000aa3f  lea     rdx, aPhonecallhisto_1; "phoneCallHistoryPublic"
0x18000aa46  mov     [rbp+var_20], 0
0x18000aa4a  call    cs:__imp_CapabilityCheck
0x18000aa50  mov     esi, eax
0x18000aa52  test    eax, eax
0x18000aa54  jns     short loc_18000AA67
0x18000aa56  bts     esi, 1Ch
0x18000aa5a  mov     r9d, 6CCh
0x18000aa60  xor     edx, edx
0x18000aa62  jmp     loc_18000ADA8
0x18000aa67  cmp     [rbp+var_20], 0
0x18000aa6b  jnz     short loc_18000AA9F
0x18000aa6d  mov     rcx, [rbp+hObject]
0x18000aa71  lea     r8, [rbp+var_20]
0x18000aa75  lea     rdx, aPhonecallhisto_0; "phoneCallHistory"
0x18000aa7c  call    cs:__imp_CapabilityCheck
0x18000aa82  mov     esi, eax
0x18000aa84  test    eax, eax
0x18000aa86  jns     short loc_18000AA99
0x18000aa88  bts     esi, 1Ch
0x18000aa8c  mov     r9d, 6D0h
0x18000aa92  xor     edx, edx
0x18000aa94  jmp     loc_18000ADA8
0x18000aa99  cmp     [rbp+var_20], 0
0x18000aa9d  jz      short loc_18000AAA6
0x18000aa9f  or      dword ptr [rbx+6FCh], 10h
0x18000aaa6  mov     rcx, [rbp+hObject]
0x18000aaaa  lea     r8, [rbp+var_1E]
0x18000aaae  lea     rdx, aSmssend; "smsSend"
0x18000aab5  mov     [rbp+var_1E], 0
0x18000aab9  call    cs:__imp_CapabilityCheck
0x18000aabf  mov     esi, eax
0x18000aac1  test    eax, eax
0x18000aac3  jns     short loc_18000AAD6
0x18000aac5  bts     esi, 1Ch
0x18000aac9  mov     r9d, 6D9h
0x18000aacf  xor     edx, edx
0x18000aad1  jmp     loc_18000ADA8
0x18000aad6  cmp     [rbp+var_1E], 0
0x18000aada  jz      short loc_18000AAE3
0x18000aadc  or      dword ptr [rbx+6FCh], 40h
0x18000aae3  mov     rcx, [rbp+hObject]
0x18000aae7  lea     r8, [rbp+var_30]
0x18000aaeb  lea     rdx, aUserdatatasks; "userDataTasks"
0x18000aaf2  call    cs:__imp_CapabilityCheck
0x18000aaf8  mov     esi, eax
0x18000aafa  test    eax, eax
0x18000aafc  jns     short loc_18000AB0F
0x18000aafe  bts     esi, 1Ch
0x18000ab02  mov     r9d, 6DFh
0x18000ab08  xor     edx, edx
0x18000ab0a  jmp     loc_18000ADA8
0x18000ab0f  cmp     [rbp+var_30], 0
0x18000ab13  jz      short loc_18000AB1F
0x18000ab15  or      dword ptr [rbx+6FCh], 80h
0x18000ab1f  mov     rcx, [rbp+hObject]
0x18000ab23  lea     r8, [rbp+var_30]
0x18000ab27  lea     rdx, aAppointmentssy; "appointmentsSystem"
0x18000ab2e  call    cs:__imp_CapabilityCheck
0x18000ab34  mov     esi, eax
0x18000ab36  test    eax, eax
0x18000ab38  jns     short loc_18000AB4B
0x18000ab3a  bts     esi, 1Ch
0x18000ab3e  mov     r9d, 6E6h
0x18000ab44  xor     edx, edx
0x18000ab46  jmp     loc_18000ADA8
0x18000ab4b  cmp     [rbp+var_30], 0
0x18000ab4f  jz      short loc_18000AB5B
0x18000ab51  or      dword ptr [rbx+6FCh], 1001h
0x18000ab5b  mov     rcx, [rbp+hObject]
0x18000ab5f  lea     r8, [rbp+var_30]
0x18000ab63  lea     rdx, aContactssystem; "contactsSystem"
0x18000ab6a  call    cs:__imp_CapabilityCheck
0x18000ab70  mov     esi, eax
0x18000ab72  test    eax, eax
0x18000ab74  jns     short loc_18000AB87
0x18000ab76  bts     esi, 1Ch
0x18000ab7a  mov     r9d, 6EDh
0x18000ab80  xor     edx, edx
0x18000ab82  jmp     loc_18000ADA8
0x18000ab87  cmp     [rbp+var_30], 0
0x18000ab8b  jz      short loc_18000AB97
0x18000ab8d  or      dword ptr [rbx+6FCh], 2002h
0x18000ab97  mov     rcx, [rbp+hObject]
0x18000ab9b  lea     r8, [rbp+var_1D]
0x18000ab9f  lea     rdx, aBlockedchatmes; "blockedChatMessages"
0x18000aba6  mov     [rbp+var_1D], 0
0x18000abaa  call    cs:__imp_CapabilityCheck
0x18000abb0  mov     esi, eax
0x18000abb2  test    eax, eax
0x18000abb4  jns     short loc_18000ABC7
0x18000abb6  bts     esi, 1Ch
0x18000abba  mov     r9d, 6F5h
0x18000abc0  xor     edx, edx
0x18000abc2  jmp     loc_18000ADA8
0x18000abc7  cmp     [rbp+var_1D], 0
0x18000abcb  jz      short loc_18000ABD4
0x18000abcd  or      dword ptr [rbx+6FCh], 20h
0x18000abd4  mov     rcx, [rbp+hObject]
0x18000abd8  lea     r8, [rbp+var_30]
0x18000abdc  lea     rdx, aEmailsystem; "emailSystem"
0x18000abe3  call    cs:__imp_CapabilityCheck
0x18000abe9  mov     esi, eax
0x18000abeb  test    eax, eax
0x18000abed  jns     short loc_18000AC00
0x18000abef  bts     esi, 1Ch
0x18000abf3  mov     r9d, 6FBh
0x18000abf9  xor     edx, edx
0x18000abfb  jmp     loc_18000ADA8
0x18000ac00  cmp     [rbp+var_30], 0
0x18000ac04  jz      short loc_18000AC10
0x18000ac06  or      dword ptr [rbx+6FCh], 8008h
0x18000ac10  mov     rcx, [rbp+hObject]
0x18000ac14  lea     r8, [rbp+var_30]
0x18000ac18  lea     rdx, aChatsystem; "chatSystem"
0x18000ac1f  call    cs:__imp_CapabilityCheck
0x18000ac25  mov     esi, eax
0x18000ac27  test    eax, eax
0x18000ac29  jns     short loc_18000AC3C
0x18000ac2b  bts     esi, 1Ch
0x18000ac2f  mov     r9d, 702h
0x18000ac35  xor     edx, edx
0x18000ac37  jmp     loc_18000ADA8
0x18000ac3c  cmp     [rbp+var_30], 0
0x18000ac40  jz      short loc_18000AC4C
0x18000ac42  or      dword ptr [rbx+6FCh], 4004h
0x18000ac4c  mov     rcx, [rbp+hObject]
0x18000ac50  lea     r8, [rbp+var_30]
0x18000ac54  lea     rdx, aPhonecallhisto; "phoneCallHistorySystem"
0x18000ac5b  call    cs:__imp_CapabilityCheck
0x18000ac61  mov     esi, eax
0x18000ac63  test    eax, eax
0x18000ac65  jns     short loc_18000AC78
0x18000ac67  bts     esi, 1Ch
0x18000ac6b  mov     r9d, 709h
0x18000ac71  xor     edx, edx
0x18000ac73  jmp     loc_18000ADA8
0x18000ac78  cmp     [rbp+var_30], 0
0x18000ac7c  jz      short loc_18000AC88
  ... truncated ...
```
