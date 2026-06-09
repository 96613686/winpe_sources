# ScCheckLastKnownGood(void)

- ea: `0x1400379d8`
- end: `0x140037f89`
- name: `?ScCheckLastKnownGood@@YAHXZ`
- size: `1457`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x1400848e0`

## callees

- `0x140004c58`
- `0x140015b14`
- `0x14001f99c`
- `0x14002b304`
- `0x140036514`
- `0x1400379d8`
- `0x140041778`
- `0x140043c80`
- `0x1400575b0`
- `0x140065528`
- `0x14006573c`
- `0x140065804`
- `0x1400659b8`
- `0x140065a14`
- `0x140066110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140037a2f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140037a2f`
- `ntdll!NtInitializeRegistry` at `0x140037c61`
- `ntdll!NtInitializeRegistry` at `0x140037c61`
- `ntdll!NtSetSystemEnvironmentValue` at `0x140037bdb`
- `ntdll!NtSetSystemEnvironmentValue` at `0x140037bdb`
- `ntdll!NtClose` at `0x140037b03`
- `ntdll!NtClose` at `0x140037b15`
- `ntdll!NtClose` at `0x140037ed7`
- `ntdll!NtClose` at `0x140037ee9`
- `ntdll!NtClose` at `0x140037f00`
- `ntdll!NtClose` at `0x140037f12`
- `ntdll!NtClose` at `0x140037f30`
- `ntdll!NtClose` at `0x140037f42`
- `ntdll!NtClose` at `0x140037b03`
- `ntdll!NtClose` at `0x140037b15`
- `ntdll!NtClose` at `0x140037ed7`
- `ntdll!NtClose` at `0x140037ee9`
- `ntdll!NtClose` at `0x140037f00`
- `ntdll!NtClose` at `0x140037f12`
- `ntdll!NtClose` at `0x140037f30`
- `ntdll!NtClose` at `0x140037f42`
- `ntdll!RtlNtStatusToDosError` at `0x140037b0b`
- `ntdll!RtlNtStatusToDosError` at `0x140037b1d`
- `ntdll!RtlNtStatusToDosError` at `0x140037be3`
- `ntdll!RtlNtStatusToDosError` at `0x140037c69`
- `ntdll!RtlNtStatusToDosError` at `0x140037edf`
- `ntdll!RtlNtStatusToDosError` at `0x140037ef1`
- `ntdll!RtlNtStatusToDosError` at `0x140037f08`
- `ntdll!RtlNtStatusToDosError` at `0x140037f1a`
- `ntdll!RtlNtStatusToDosError` at `0x140037f38`
- `ntdll!RtlNtStatusToDosError` at `0x140037f4a`
- `ntdll!RtlNtStatusToDosError` at `0x140037b0b`
- `ntdll!RtlNtStatusToDosError` at `0x140037b1d`
- `ntdll!RtlNtStatusToDosError` at `0x140037be3`
- `ntdll!RtlNtStatusToDosError` at `0x140037c69`
- `ntdll!RtlNtStatusToDosError` at `0x140037edf`
- `ntdll!RtlNtStatusToDosError` at `0x140037ef1`
- `ntdll!RtlNtStatusToDosError` at `0x140037f08`
- `ntdll!RtlNtStatusToDosError` at `0x140037f1a`
- `ntdll!RtlNtStatusToDosError` at `0x140037f38`
- `ntdll!RtlNtStatusToDosError` at `0x140037f4a`
- `ntdll!RtlInitUnicodeString` at `0x140037bbc`
- `ntdll!RtlInitUnicodeString` at `0x140037bcd`
- `ntdll!RtlInitUnicodeString` at `0x140037bbc`
- `ntdll!RtlInitUnicodeString` at `0x140037bcd`

## pseudocode

```c
__int64 ScCheckLastKnownGood(void)
{
  ULONG Privilege; // eax
  PRPC_ASYNC_STATE v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // edi
  unsigned int **v5; // rdx
  NTSTATUS v6; // eax
  NTSTATUS v7; // eax
  unsigned int v8; // r12d
  NTSTATUS v9; // eax
  ULONG v10; // eax
  PRPC_ASYNC_STATE v11; // rbx
  unsigned int v12; // r8d
  unsigned int v13; // r15d
  NTSTATUS v14; // eax
  PRPC_ASYNC_STATE v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  HKEY CtrlSetHandle; // rax
  unsigned int v19; // eax
  unsigned int v20; // r8d
  unsigned int v21; // eax
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  NTSTATUS v25; // eax
  NTSTATUS v26; // eax
  NTSTATUS v27; // eax
  HANDLE Handle; // [rsp+30h] [rbp-59h] BYREF
  HANDLE v29; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v30; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-41h] BYREF
  int v32; // [rsp+58h] [rbp-31h]
  struct _UNICODE_STRING Value; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v34; // [rsp+70h] [rbp-19h] BYREF
  unsigned int v35; // [rsp+74h] [rbp-15h]
  unsigned int v36; // [rsp+78h] [rbp-11h] BYREF
  unsigned int v37; // [rsp+7Ch] [rbp-Dh] BYREF
  unsigned __int16 v38[16]; // [rsp+80h] [rbp-9h] BYREF

  Handle = 0;
  v29 = 0;
  v30 = 0;
  if ( (MEMORY[0x7FFE02F0] & 0x10) == 0 )
    return 1;
  InitializeCriticalSection(&ScBootConfigCriticalSection);
  *(_DWORD *)&DestinationString.Length = 17;
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 18;
  DestinationString.Buffer = (PWSTR)0x900000008LL;
  v32 = 22;
  Privilege = ScGetPrivilege(5u, (unsigned int *)&DestinationString.Length);
  if ( Privilege )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 10, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, Privilege);
    return 0;
  }
  if ( ScGetTopKeys((HKEY *)&Handle, (HKEY *)&v29) )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_13;
    v3 = 11;
    goto LABEL_12;
  }
  if ( ScGetCtrlSetIds((HKEY)v29, &v34) )
  {
    v6 = NtClose(Handle);
    RtlNtStatusToDosError(v6);
    v7 = NtClose(v29);
    RtlNtStatusToDosError(v7);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_13;
    v3 = 12;
LABEL_12:
    WPP_SF_(v2->StubInfo, v3, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
    goto LABEL_13;
  }
  ScGatherOrphanIds((HKEY)Handle, v5, &v34);
  if ( (unsigned int)SetupInProgress(Handle, 0) || (v8 = v36, v34 != v36) )
  {
    ScGlobalLastKnownGood = 0;
    v26 = NtClose(Handle);
    RtlNtStatusToDosError(v26);
    v27 = NtClose(v29);
    RtlNtStatusToDosError(v27);
    v4 = 1;
    goto LABEL_76;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->StubInfo, 13, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
    v8 = v36;
  }
  DestinationString = 0;
  Value = 0;
  RtlInitUnicodeString(&DestinationString, L"LastKnownGood");
  RtlInitUnicodeString(&Value, L"False");
  v9 = NtSetSystemEnvironmentValue(&DestinationString, &Value);
  v10 = RtlNtStatusToDosError(v9);
  v4 = 1;
  if ( !v10 )
    goto LABEL_27;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
    goto LABEL_31;
  if ( (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 14, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, v10);
LABEL_27:
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v11->UserInfo) & 4) != 0 )
  {
    WPP_SF_(v11->StubInfo, 15, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
LABEL_31:
  if ( ScGetNewCtrlSetId(&v34, &v30) )
    goto LABEL_49;
  v13 = v30;
  v14 = NtInitializeRegistry(v30 + 4096);
  if ( RtlNtStatusToDosError(v14) )
  {
    v11 = WPP_GLOBAL_Control;
LABEL_49:
    if ( v11 == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
      goto LABEL_56;
    if ( (BYTE4(v11->UserInfo) & 1) != 0 )
    {
      WPP_SF_(v11->StubInfo, 16, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(v11->UserInfo) & 1) == 0 )
      goto LABEL_56;
    WPP_SF_(v11->StubInfo, 17, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
    goto LABEL_55;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 18, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
      v15 = WPP_GLOBAL_Control;
    }
    if ( v15 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v15->UserInfo) & 4) != 0 )
      WPP_SF_(v15->StubInfo, 19, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
  }
  v36 = v13;
  v16 = ScRegSetValueExW((HKEY)v29, L"LastKnownGood", v12, 4u, &v36, 4u);
  if ( !v16 )
  {
    v11 = WPP_GLOBAL_Control;
    v17 = ScGlobalLastKnownGood | 1;
    ScGlobalBootAccepted = 1;
    ScGlobalLastKnownGood |= 1u;
    if ( v37 )
      ScGlobalLastKnownGood = v17 | 2;
    goto LABEL_56;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 20, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, v16);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v11->UserInfo) & 1) != 0 )
    {
      WPP_SF_d(v11->StubInfo, 21, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, v13);
LABEL_55:
      v11 = WPP_GLOBAL_Control;
    }
  }
LABEL_56:
  if ( v35 == v8 )
    goto LABEL_74;
  if ( v11 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v11->UserInfo) & 4) != 0 )
  {
    WPP_SF_(v11->StubInfo, 22, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v37 )
  {
    if ( v11 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v11->UserInfo) & 4) != 0 )
      WPP_SF_(v11->StubInfo, 23, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
    CtrlSetHandle = ScGetCtrlSetHandle((HKEY)Handle, v37, v38);
    ScDeleteRegTree((HKEY)Handle, CtrlSetHandle, v38);
  }
  v37 = v35;
  v19 = ScRegSetValueExW((HKEY)v29, L"Failed", v12, 4u, &v37, 4u);
  if ( v19
    && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 24, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, v19);
  }
  v35 = v34;
  v21 = ScRegSetValueExW((HKEY)v29, L"Default", v20, 4u, &v34, 4u);
  if ( !v21 )
  {
LABEL_74:
    v24 = NtClose(Handle);
    RtlNtStatusToDosError(v24);
    v25 = NtClose(v29);
    RtlNtStatusToDosError(v25);
    goto LABEL_76;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 25, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, v21);
  v22 = NtClose(v29);
  RtlNtStatusToDosError(v22);
  v23 = NtClose(Handle);
  RtlNtStatusToDosError(v23);
LABEL_13:
  v4 = 0;
LABEL_76:
  ScReleasePrivilege();
  if ( ScGlobalOrphanIds )
    ScStartCtrlSetCleanupThread();
  return v4;
}

```

## disassembly

```asm
0x1400379d8  push    rbp
0x1400379da  push    rbx
0x1400379db  push    rsi
0x1400379dc  push    rdi
0x1400379dd  push    r12
0x1400379df  push    r14
0x1400379e1  push    r15
0x1400379e3  lea     rbp, [rsp-27h]
0x1400379e8  sub     rsp, 0B0h
0x1400379ef  mov     rax, cs:__security_cookie
0x1400379f6  xor     rax, rsp
0x1400379f9  mov     [rbp+57h+var_40], rax
0x1400379fd  mov     [rbp+57h+Handle], 0
0x140037a05  mov     [rbp+57h+var_A8], 0
0x140037a0d  test    byte ptr ds:7FFE02F0h, 10h
0x140037a15  mov     [rbp+57h+var_A0], 0
0x140037a1c  jnz     short loc_140037A28
0x140037a1e  mov     eax, 1
0x140037a23  jmp     loc_140037F6B
0x140037a28  lea     rcx, ?ScBootConfigCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140037a2f  call    cs:__imp_InitializeCriticalSection
0x140037a35  lea     rdx, [rbp+57h+DestinationString]; unsigned int *
0x140037a39  mov     dword ptr [rbp+57h+DestinationString.Length], 11h
0x140037a40  mov     ecx, 5; unsigned int
0x140037a45  mov     dword ptr [rbp+57h+DestinationString+4], 12h
0x140037a4c  mov     dword ptr [rbp+57h+DestinationString.Buffer], 8
0x140037a53  mov     dword ptr [rbp+57h+DestinationString.Buffer+4], 9
0x140037a5a  mov     [rbp+57h+var_88], 16h
0x140037a61  call    ?ScGetPrivilege@@YAKKPEAK@Z; ScGetPrivilege(ulong,ulong *)
0x140037a66  test    eax, eax
0x140037a68  jz      short loc_140037AA5
0x140037a6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037a71  lea     rsi, WPP_GLOBAL_Control
0x140037a78  cmp     rcx, rsi
0x140037a7b  jz      short loc_140037A9E
0x140037a7d  mov     edi, 1
0x140037a82  test    [rcx+1Ch], dil
0x140037a86  jz      short loc_140037A9E
0x140037a88  mov     rcx, [rcx+10h]
0x140037a8c  lea     edx, [rdi+9]
0x140037a8f  mov     r9d, eax
0x140037a92  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140037a99  call    WPP_SF_d
0x140037a9e  xor     eax, eax
0x140037aa0  jmp     loc_140037F6B
0x140037aa5  lea     rdx, [rbp+57h+var_A8]; HKEY *
0x140037aa9  lea     rcx, [rbp+57h+Handle]; HKEY *
0x140037aad  call    ?ScGetTopKeys@@YAKPEAPEAUHKEY__@@0@Z; ScGetTopKeys(HKEY__ * *,HKEY__ * *)
0x140037ab2  test    eax, eax
0x140037ab4  jz      short loc_140037AEE
0x140037ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x140037abd  lea     rsi, WPP_GLOBAL_Control
0x140037ac4  cmp     rcx, rsi
0x140037ac7  jz      short loc_140037AE7
0x140037ac9  mov     edi, 1
0x140037ace  test    [rcx+1Ch], dil
0x140037ad2  jz      short loc_140037AE7
0x140037ad4  lea     edx, [rdi+0Ah]
0x140037ad7  mov     rcx, [rcx+10h]
0x140037adb  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140037ae2  call    WPP_SF_
0x140037ae7  xor     edi, edi
0x140037ae9  jmp     loc_140037F55
0x140037aee  mov     rcx, [rbp+57h+var_A8]; KeyHandle
0x140037af2  lea     rdx, [rbp+57h+var_70]; unsigned int *
0x140037af6  call    ?ScGetCtrlSetIds@@YAKPEAUHKEY__@@PEAK@Z; ScGetCtrlSetIds(HKEY__ *,ulong *)
0x140037afb  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140037aff  test    eax, eax
0x140037b01  jz      short loc_140037B46
0x140037b03  call    cs:__imp_NtClose
0x140037b09  mov     ecx, eax; Status
0x140037b0b  call    cs:__imp_RtlNtStatusToDosError
0x140037b11  mov     rcx, [rbp+57h+var_A8]; Handle
0x140037b15  call    cs:__imp_NtClose
0x140037b1b  mov     ecx, eax; Status
0x140037b1d  call    cs:__imp_RtlNtStatusToDosError
0x140037b23  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b2a  lea     rsi, WPP_GLOBAL_Control
0x140037b31  cmp     rcx, rsi
0x140037b34  jz      short loc_140037AE7
0x140037b36  mov     edi, 1
0x140037b3b  test    [rcx+1Ch], dil
0x140037b3f  jz      short loc_140037AE7
0x140037b41  lea     edx, [rdi+0Bh]
0x140037b44  jmp     short loc_140037AD7
0x140037b46  lea     r8, [rbp+57h+var_70]; unsigned int *
0x140037b4a  call    ?ScGatherOrphanIds@@YAXPEAUHKEY__@@PEAPEAKPEAK@Z; ScGatherOrphanIds(HKEY__ *,ulong * *,ulong *)
0x140037b4f  mov     rcx, [rbp+57h+Handle]
0x140037b53  xor     edx, edx
0x140037b55  call    SetupInProgress
0x140037b5a  test    eax, eax
0x140037b5c  jnz     loc_140037F22
0x140037b62  mov     r12d, [rbp+57h+var_68]
0x140037b66  cmp     [rbp+57h+var_70], r12d
0x140037b6a  jnz     loc_140037F22
0x140037b70  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b77  lea     rsi, WPP_GLOBAL_Control
0x140037b7e  lea     r14, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140037b85  cmp     rcx, rsi
0x140037b88  jz      short loc_140037BA3
0x140037b8a  test    byte ptr [rcx+1Ch], 4
0x140037b8e  jz      short loc_140037BA3
0x140037b90  mov     rcx, [rcx+10h]
0x140037b94  lea     edx, [rax+0Dh]
0x140037b97  mov     r8, r14
0x140037b9a  call    WPP_SF_
0x140037b9f  mov     r12d, [rbp+57h+var_68]
0x140037ba3  xorps   xmm0, xmm0
0x140037ba6  lea     rdx, aLastknowngood; "LastKnownGood"
0x140037bad  xorps   xmm1, xmm1
0x140037bb0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140037bb4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140037bb8  movups  xmmword ptr [rbp+57h+Value.Length], xmm1
0x140037bbc  call    cs:__imp_RtlInitUnicodeString
0x140037bc2  lea     rdx, aFalse_0; "False"
0x140037bc9  lea     rcx, [rbp+57h+Value]; DestinationString
0x140037bcd  call    cs:__imp_RtlInitUnicodeString
0x140037bd3  lea     rdx, [rbp+57h+Value]; Value
0x140037bd7  lea     rcx, [rbp+57h+DestinationString]; VariableName
0x140037bdb  call    cs:__imp_NtSetSystemEnvironmentValue
0x140037be1  mov     ecx, eax; Status
0x140037be3  call    cs:__imp_RtlNtStatusToDosError
0x140037be9  mov     edi, 1
0x140037bee  test    eax, eax
0x140037bf0  jz      short loc_140037C16
0x140037bf2  mov     rbx, cs:WPP_GLOBAL_Control
0x140037bf9  cmp     rbx, rsi
0x140037bfc  jz      short loc_140037C40
0x140037bfe  test    [rbx+1Ch], dil
0x140037c02  jz      short loc_140037C1D
0x140037c04  mov     rcx, [rbx+10h]
0x140037c08  lea     edx, [rdi+0Dh]
0x140037c0b  mov     r9d, eax
0x140037c0e  mov     r8, r14
0x140037c11  call    WPP_SF_d
0x140037c16  mov     rbx, cs:WPP_GLOBAL_Control
0x140037c1d  cmp     rbx, rsi
0x140037c20  jz      short loc_140037C40
0x140037c22  test    byte ptr [rbx+1Ch], 4
0x140037c26  jz      short loc_140037C40
0x140037c28  mov     rcx, [rbx+10h]
0x140037c2c  mov     edx, 0Fh
0x140037c31  mov     r8, r14
0x140037c34  call    WPP_SF_
0x140037c39  mov     rbx, cs:WPP_GLOBAL_Control
0x140037c40  lea     rdx, [rbp+57h+var_A0]; unsigned int *
0x140037c44  lea     rcx, [rbp+57h+var_70]; unsigned int *
0x140037c48  call    ?ScGetNewCtrlSetId@@YAKPEAK0@Z; ScGetNewCtrlSetId(ulong *,ulong *)
0x140037c4d  test    eax, eax
0x140037c4f  jnz     loc_140037D77
0x140037c55  mov     r15d, [rbp+57h+var_A0]
0x140037c59  mov     ecx, 1000h
0x140037c5e  add     ecx, r15d; Flag
0x140037c61  call    cs:__imp_NtInitializeRegistry
0x140037c67  mov     ecx, eax; Status
0x140037c69  call    cs:__imp_RtlNtStatusToDosError
0x140037c6f  test    eax, eax
0x140037c71  jnz     loc_140037D70
0x140037c77  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c7e  cmp     rcx, rsi
0x140037c81  jz      short loc_140037CBB
0x140037c83  test    byte ptr [rcx+1Ch], 4
0x140037c87  jz      short loc_140037C9F
0x140037c89  mov     rcx, [rcx+10h]
0x140037c8d  lea     edx, [rax+12h]
0x140037c90  mov     r8, r14
0x140037c93  call    WPP_SF_
0x140037c98  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c9f  cmp     rcx, rsi
0x140037ca2  jz      short loc_140037CBB
0x140037ca4  test    byte ptr [rcx+1Ch], 4
0x140037ca8  jz      short loc_140037CBB
0x140037caa  mov     rcx, [rcx+10h]
0x140037cae  mov     edx, 13h
0x140037cb3  mov     r8, r14
0x140037cb6  call    WPP_SF_
0x140037cbb  mov     rcx, [rbp+57h+var_A8]; KeyHandle
0x140037cbf  lea     rax, [rbp+57h+var_68]
0x140037cc3  mov     [rsp+0E0h+var_B8], 4; unsigned int
0x140037ccb  lea     rdx, aLastknowngood; "LastKnownGood"
0x140037cd2  mov     r9d, 4; unsigned int
0x140037cd8  mov     [rsp+0E0h+var_C0], rax; void *
0x140037cdd  mov     [rbp+57h+var_68], r15d
0x140037ce1  call    ?ScRegSetValueExW@@YAKPEAUHKEY__@@PEBGKKPEAXK@Z; ScRegSetValueExW(HKEY__ *,ushort const *,ulong,ulong,void *,ulong)
0x140037ce6  test    eax, eax
0x140037ce8  jz      short loc_140037D44
0x140037cea  mov     rbx, cs:WPP_GLOBAL_Control
0x140037cf1  cmp     rbx, rsi
0x140037cf4  jz      loc_140037DBD
0x140037cfa  test    [rbx+1Ch], dil
0x140037cfe  jz      short loc_140037D1B
0x140037d00  mov     rcx, [rbx+10h]
0x140037d04  mov     edx, 14h
0x140037d09  mov     r9d, eax
0x140037d0c  mov     r8, r14
0x140037d0f  call    WPP_SF_d
0x140037d14  mov     rbx, cs:WPP_GLOBAL_Control
0x140037d1b  cmp     rbx, rsi
0x140037d1e  jz      loc_140037DBD
0x140037d24  test    [rbx+1Ch], dil
0x140037d28  jz      loc_140037DBD
0x140037d2e  mov     rcx, [rbx+10h]
0x140037d32  mov     edx, 15h
0x140037d37  mov     r9d, r15d
0x140037d3a  mov     r8, r14
0x140037d3d  call    WPP_SF_d
0x140037d42  jmp     short loc_140037DB6
0x140037d44  mov     eax, cs:?ScGlobalLastKnownGood@@3KA; ulong ScGlobalLastKnownGood
0x140037d4a  mov     rbx, cs:WPP_GLOBAL_Control
0x140037d51  or      eax, edi
0x140037d53  cmp     [rbp+57h+var_64], 0
0x140037d57  mov     cs:?ScGlobalBootAccepted@@3HA, edi; int ScGlobalBootAccepted
0x140037d5d  mov     cs:?ScGlobalLastKnownGood@@3KA, eax; ulong ScGlobalLastKnownGood
0x140037d63  jz      short loc_140037DBD
0x140037d65  or      eax, 2
0x140037d68  mov     cs:?ScGlobalLastKnownGood@@3KA, eax; ulong ScGlobalLastKnownGood
0x140037d6e  jmp     short loc_140037DBD
0x140037d70  mov     rbx, cs:WPP_GLOBAL_Control
0x140037d77  cmp     rbx, rsi
0x140037d7a  jz      short loc_140037DBD
0x140037d7c  test    [rbx+1Ch], dil
0x140037d80  jz      short loc_140037D9A
0x140037d82  mov     rcx, [rbx+10h]
0x140037d86  mov     edx, 10h
0x140037d8b  mov     r8, r14
0x140037d8e  call    WPP_SF_
0x140037d93  mov     rbx, cs:WPP_GLOBAL_Control
0x140037d9a  cmp     rbx, rsi
0x140037d9d  jz      short loc_140037DBD
0x140037d9f  test    [rbx+1Ch], dil
0x140037da3  jz      short loc_140037DBD
0x140037da5  mov     rcx, [rbx+10h]
0x140037da9  mov     edx, 11h
0x140037dae  mov     r8, r14
0x140037db1  call    WPP_SF_
0x140037db6  mov     rbx, cs:WPP_GLOBAL_Control
0x140037dbd  cmp     [rbp+57h+var_6C], r12d
0x140037dc1  jz      loc_140037EFC
0x140037dc7  mov     r15d, 4
0x140037dcd  cmp     rbx, rsi
0x140037dd0  jz      short loc_140037DEF
0x140037dd2  test    [rbx+1Ch], r15b
0x140037dd6  jz      short loc_140037DEF
0x140037dd8  mov     rcx, [rbx+10h]
0x140037ddc  lea     edx, [r15+12h]
0x140037de0  mov     r8, r14
0x140037de3  call    WPP_SF_
0x140037de8  mov     rbx, cs:WPP_GLOBAL_Control
0x140037def  cmp     [rbp+57h+var_64], 0
0x140037df3  jz      short loc_140037E31
0x140037df5  cmp     rbx, rsi
0x140037df8  jz      short loc_140037E11
0x140037dfa  test    [rbx+1Ch], r15b
0x140037dfe  jz      short loc_140037E11
0x140037e00  mov     rcx, [rbx+10h]
0x140037e04  mov     edx, 17h
0x140037e09  mov     r8, r14
0x140037e0c  call    WPP_SF_
0x140037e11  mov     edx, [rbp+57h+var_64]; unsigned int
0x140037e14  lea     r8, [rbp+57h+var_60]; unsigned __int16 *
0x140037e18  mov     rcx, [rbp+57h+Handle]; HKEY
0x140037e1c  call    ?ScGetCtrlSetHandle@@YAPEAUHKEY__@@PEAU1@KPEAG@Z; ScGetCtrlSetHandle(HKEY__ *,ulong,ushort *)
0x140037e21  mov     rcx, [rbp+57h+Handle]; HKEY
0x140037e25  lea     r8, [rbp+57h+var_60]; unsigned __int16 *
0x140037e29  mov     rdx, rax; HKEY
0x140037e2c  call    ?ScDeleteRegTree@@YAXPEAUHKEY__@@0PEBG@Z; ScDeleteRegTree(HKEY__ *,HKEY__ *,ushort const *)
0x140037e31  mov     eax, [rbp+57h+var_6C]
0x140037e34  lea     rdx, aFailed_0; "Failed"
0x140037e3b  mov     rcx, [rbp+57h+var_A8]; KeyHandle
0x140037e3f  mov     r9d, r15d; unsigned int
0x140037e42  mov     [rbp+57h+var_64], eax
0x140037e45  lea     rax, [rbp+57h+var_64]
0x140037e49  mov     [rsp+0E0h+var_B8], r15d; unsigned int
0x140037e4e  mov     [rsp+0E0h+var_C0], rax; void *
0x140037e53  call    ?ScRegSetValueExW@@YAKPEAUHKEY__@@PEBGKKPEAXK@Z; ScRegSetValueExW(HKEY__ *,ushort const *,ulong,ulong,void *,ulong)
0x140037e58  test    eax, eax
0x140037e5a  jz      short loc_140037E82
0x140037e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140037e63  cmp     rcx, rsi
0x140037e66  jz      short loc_140037E82
0x140037e68  test    [rcx+1Ch], dil
0x140037e6c  jz      short loc_140037E82
0x140037e6e  mov     rcx, [rcx+10h]
0x140037e72  mov     edx, 18h
0x140037e77  mov     r9d, eax
0x140037e7a  mov     r8, r14
0x140037e7d  call    WPP_SF_d
0x140037e82  mov     eax, [rbp+57h+var_70]
0x140037e85  lea     rdx, aDefault; "Default"
0x140037e8c  mov     rcx, [rbp+57h+var_A8]; KeyHandle
0x140037e90  mov     r9d, r15d; unsigned int
0x140037e93  mov     [rbp+57h+var_6C], eax
0x140037e96  lea     rax, [rbp+57h+var_70]
0x140037e9a  mov     [rsp+0E0h+var_B8], r15d; unsigned int
0x140037e9f  mov     [rsp+0E0h+var_C0], rax; void *
0x140037ea4  call    ?ScRegSetValueExW@@YAKPEAUHKEY__@@PEBGKKPEAXK@Z; ScRegSetValueExW(HKEY__ *,ushort const *,ulong,ulong,void *,ulong)
0x140037ea9  test    eax, eax
0x140037eab  jz      short loc_140037EFC
0x140037ead  mov     rcx, cs:WPP_GLOBAL_Control
0x140037eb4  cmp     rcx, rsi
  ... truncated ...
```
