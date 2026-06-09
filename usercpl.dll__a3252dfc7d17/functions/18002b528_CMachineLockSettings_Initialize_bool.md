# CMachineLockSettings::Initialize(bool)

- ea: `0x18002b528`
- end: `0x18002b9ef`
- name: `?Initialize@CMachineLockSettings@@QEAAJ_N@Z`
- size: `1223`
- prototype: `__int64 __fastcall(CMachineLockSettings *__hidden this, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180026860`
- `0x1800292a0`

## callees

- `0x1800228d4`
- `0x18002b528`
- `0x18002ba7c`
- `0x18002c068`
- `0x18002c134`
- `0x18002c3e4`
- `0x18006d580`
- `0x18006eb10`
- `0x18006eb70`
- `0x180078010`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x18002b63f`
- `netutils!NetApiBufferFree` at `0x18002b63f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b9c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b9c5`
- `wkscli!NetGetJoinInformation` at `0x18002b62c`
- `wkscli!NetGetJoinInformation` at `0x18002b62c`
- `api-ms-win-power-setting-l1-1-0!PowerReadACValue` at `0x18002b79e`
- `api-ms-win-power-setting-l1-1-0!PowerReadACValue` at `0x18002b79e`
- `api-ms-win-power-setting-l1-1-0!PowerReadDCValue` at `0x18002b7fd`
- `api-ms-win-power-setting-l1-1-0!PowerReadDCValue` at `0x18002b7fd`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18002b5d8`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18002b5d8`
- `USER32!SystemParametersInfoW` at `0x18002b706`
- `USER32!SystemParametersInfoW` at `0x18002b742`
- `USER32!SystemParametersInfoW` at `0x18002b706`
- `USER32!SystemParametersInfoW` at `0x18002b742`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18002b606`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18002b606`

## string_xrefs

- `0x18002b905`: `Failed to create 'require password on wake' helper class with 0x%x`

## pseudocode

```c
__int64 __fastcall CMachineLockSettings::Initialize(CMachineLockSettings *this, char a2)
{
  const wchar_t *v2; // r14
  const wchar_t *v4; // r8
  const wchar_t *v5; // r8
  const wchar_t *v6; // r8
  const wchar_t *v7; // r8
  const wchar_t *v8; // r8
  signed int ActiveScheme; // eax
  int inited; // esi
  int v11; // eax
  enum _NETSETUP_JOIN_STATUS v12; // ecx
  char v13; // si
  const wchar_t *v14; // r8
  __int64 EASGroupPolicyTimeout; // rbx
  __int64 v16; // rdx
  __int64 EASPolicyDeviceLockTimeoutValue; // rsi
  __int64 v18; // rdx
  bool IsPasswordOnWakeRequired; // r15
  int IsOSSilentElevationOn; // ebx
  const wchar_t *v21; // r8
  int PasswordOnWakeSettingObject; // eax
  unsigned int v23; // r8d
  const wchar_t *v24; // r8
  struct IPasswordOnWakeSetting *v25; // rcx
  enum _NETSETUP_JOIN_STATUS v26; // ebx
  const wchar_t *v27; // r8
  __int64 v28; // rdx
  GUID *ActivePolicyGuid; // [rsp+40h] [rbp-10h] BYREF
  struct IPasswordOnWakeSetting *pvParam; // [rsp+90h] [rbp+40h] BYREF
  enum _NETSETUP_JOIN_STATUS BufferType; // [rsp+98h] [rbp+48h] BYREF
  LPWSTR NameBuffer; // [rsp+A0h] [rbp+50h] BYREF
  DWORD BufferSize; // [rsp+A8h] [rbp+58h] BYREF

  LOBYTE(BufferType) = a2;
  v2 = L"TRUE";
  v4 = L"TRUE";
  if ( (*((_BYTE *)this + 52) & 8) == 0 )
    v4 = L"FALSE";
  LogComment(0, L"Is AoAc device            : %s", v4);
  v5 = L"TRUE";
  if ( (*((_BYTE *)this + 52) & 1) == 0 )
    v5 = L"FALSE";
  LogComment(0, L"Is CAD Required           : %s", v5);
  v6 = L"TRUE";
  if ( (*((_BYTE *)this + 52) & 4) == 0 )
    v6 = L"FALSE";
  LogComment(0, L"Are batteries available   : %s", v6);
  v7 = L"TRUE";
  if ( (*((_BYTE *)this + 52) & 2) == 0 )
    v7 = L"FALSE";
  LogComment(0, L"Can this device standby   : %s", v7);
  v8 = L"TRUE";
  if ( (*((_BYTE *)this + 52) & 0x10) == 0 )
    v8 = L"FALSE";
  LogComment(0, L"Can this device hibernate : %s", v8);
  ActivePolicyGuid = 0;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  inited = ActiveScheme;
  if ( ActiveScheme > 0 )
    inited = (unsigned __int16)ActiveScheme | 0x80070000;
  if ( inited < 0 )
  {
    LogComment(0, L"Failed to retrieve active power scheme GUID with 0x%x", (unsigned int)inited);
    return (unsigned int)inited;
  }
  if ( (*((_BYTE *)this + 52) & 8) != 0 )
  {
    if ( (unsigned int)SHWindowsPolicy(POLID_AllowDomainDelayLock) )
      goto LABEL_24;
    v11 = `IsOS_OS_DOMAINMEMBER'::`2'::s_bIsDomainMember;
    if ( !`IsOS_OS_DOMAINMEMBER'::`2'::s_bIsDomainMember )
    {
      NameBuffer = 0;
      BufferType = NetSetupUnknownStatus;
      if ( NetGetJoinInformation(0, &NameBuffer, &BufferType) )
      {
        v12 = NetSetupUnknownStatus;
      }
      else
      {
        if ( NameBuffer )
          NetApiBufferFree(NameBuffer);
        v12 = BufferType;
      }
      v11 = (v12 != NetSetupDomainName) + 1;
      `IsOS_OS_DOMAINMEMBER'::`2'::s_bIsDomainMember = v11;
    }
    v13 = 1;
    if ( v11 != 1 )
LABEL_24:
      v13 = 0;
    v14 = L"TRUE";
    if ( !v13 )
      v14 = L"FALSE";
    LogComment(0, L"Is Delaylock disabled by policy: %s", v14);
    LODWORD(pvParam) = -1;
    LODWORD(EASGroupPolicyTimeout) = -(v13 == 0);
    if ( !CMachineLockSettings::_IsPasswordOnWakeRequired(this, v16, ActivePolicyGuid) )
      *((_DWORD *)this + 13) |= 0x20u;
    if ( (*((_BYTE *)this + 52) & 1) != 0 || (*((_BYTE *)this + 52) & 0x20) != 0 || v13 )
    {
      LODWORD(EASPolicyDeviceLockTimeoutValue) = -1;
      LogComment(0, L"DelayLock drop down setting will be disabled/hidden");
    }
    else
    {
      EASPolicyDeviceLockTimeoutValue = GetEASPolicyDeviceLockTimeoutValue();
      LogComment(0, L"EAS timeout: 0x%x", EASPolicyDeviceLockTimeoutValue);
      EASGroupPolicyTimeout = GetEASGroupPolicyTimeout();
      LogComment(0, L"Group policy timeout: 0x%x", EASGroupPolicyTimeout);
      LODWORD(NameBuffer) = 0;
      if ( SystemParametersInfoW(0x76u, 0, &NameBuffer, 0) )
      {
        if ( !(_DWORD)NameBuffer )
          v2 = L"FALSE";
        LogComment(0, L"Secure screen saver enabled: %s", v2);
        if ( (_DWORD)NameBuffer && SystemParametersInfoW(0xEu, 0, &pvParam, 0) )
          LogComment(0, L"Screensaver timeout: 0x%x", (unsigned int)pvParam);
      }
      if ( (*((_BYTE *)this + 52) & 2) != 0 )
      {
        BufferType = -1;
        BufferSize = 4;
        PowerReadACValue(
          0,
          ActivePolicyGuid,
          &GUID_SLEEP_SUBGROUP,
          &GUID_STANDBY_TIMEOUT,
          0,
          (LPBYTE)&BufferType,
          &BufferSize);
        LogComment(0, L"Sleep (AC value) timeout: 0x%x", (unsigned int)BufferType);
        if ( (unsigned int)pvParam >= BufferType )
          LODWORD(pvParam) = BufferType;
        if ( (*((_BYTE *)this + 52) & 4) != 0 )
        {
          BufferType = -1;
          BufferSize = 4;
          PowerReadDCValue(
            0,
            ActivePolicyGuid,
            &GUID_SLEEP_SUBGROUP,
            &GUID_STANDBY_TIMEOUT,
            0,
            (PUCHAR)&BufferType,
            &BufferSize);
          LogComment(0, L"Sleep (DC value) timeout: 0x%x", (unsigned int)BufferType);
          if ( (unsigned int)pvParam >= BufferType )
            LODWORD(pvParam) = BufferType;
        }
      }
    }
    inited = CMachineLockSettings::_InitDelayLockItems(
               this,
               v18,
               EASGroupPolicyTimeout,
               (unsigned int)pvParam,
               EASPolicyDeviceLockTimeoutValue);
    goto LABEL_73;
  }
  IsPasswordOnWakeRequired = 0;
  if ( (*((_BYTE *)this + 52) & 2) != 0 || (*((_BYTE *)this + 52) & 0x10) != 0 )
  {
    IsOSSilentElevationOn = LUAIsAdminAndIsOSSilentElevationOn();
    v21 = L"TRUE";
    if ( !IsOSSilentElevationOn )
      v21 = L"FALSE";
    LogComment(0, L"Is silent elevation       : %s", v21);
    if ( IsOSSilentElevationOn )
    {
      pvParam = 0;
      PasswordOnWakeSettingObject = CMachineLockSettings::_GetPasswordOnWakeSettingObject(this, &pvParam);
      inited = PasswordOnWakeSettingObject;
      if ( PasswordOnWakeSettingObject < 0 )
      {
        LogComment(
          0,
          L"Failed to create 'require password on wake' helper class with 0x%x",
          (unsigned int)PasswordOnWakeSettingObject);
      }
      else
      {
        v23 = *((_DWORD *)this + 13);
        BufferType = NetSetupUnknownStatus;
        inited = (*(__int64 (__fastcall **)(struct IPasswordOnWakeSetting *, GUID *, _QWORD, enum _NETSETUP_JOIN_STATUS *))(*(_QWORD *)pvParam + 24LL))(
                   pvParam,
                   ActivePolicyGuid,
                   (v23 >> 2) & 1,
                   &BufferType);
        v24 = L"TRUE";
        if ( BufferType == NetSetupUnknownStatus )
          v24 = L"FALSE";
        LogComment(0, L"Is restricted by GP       : %s", v24);
        if ( inited >= 0 && BufferType )
          *((_DWORD *)this + 12) |= 1u;
      }
      v25 = pvParam;
      if ( pvParam )
      {
        pvParam = 0;
        (*(void (__fastcall **)(struct IPasswordOnWakeSetting *))(*(_QWORD *)v25 + 16LL))(v25);
      }
      if ( inited < 0 )
        goto LABEL_72;
    }
    else
    {
      *((_DWORD *)this + 12) |= 0x10u;
    }
    BufferType = NetSetupUnknownStatus;
    LUAIsUserUACAdmin(&BufferType);
    v26 = BufferType;
    v27 = L"TRUE";
    if ( BufferType == NetSetupUnknownStatus )
      v27 = L"FALSE";
    LogComment(0, L"Is admin user             : %s", v27);
    if ( v26 == NetSetupUnknownStatus )
      *((_DWORD *)this + 12) |= 8u;
    IsPasswordOnWakeRequired = CMachineLockSettings::_IsPasswordOnWakeRequired(this, v28, ActivePolicyGuid);
    if ( ((GetEASGroupPolicyTimeout() + 1) & 0xFFFFFFFE) != 0 || GetEASPolicyDeviceLockTimeoutValue() - 1 <= 0xFFFFFFFD )
    {
      *((_DWORD *)this + 12) |= 4u;
      IsPasswordOnWakeRequired = 1;
    }
    if ( (*((_BYTE *)this + 48) & 4) == 0 )
      v2 = L"FALSE";
    LogComment(0, L"Is EAS enforced           : %s", v2);
  }
LABEL_72:
  *((_DWORD *)this + 10) = IsPasswordOnWakeRequired;
LABEL_73:
  LocalFree(ActivePolicyGuid);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18002b528  mov     byte ptr [rsp-38h+BufferType], dl
0x18002b52c  push    rbp
0x18002b52d  push    rbx
0x18002b52e  push    rsi
0x18002b52f  push    rdi
0x18002b530  push    r12
0x18002b532  push    r14
0x18002b534  push    r15
0x18002b536  mov     rbp, rsp
0x18002b539  sub     rsp, 50h
0x18002b53d  test    byte ptr [rcx+34h], 8
0x18002b541  lea     r14, aTrue_0; "TRUE"
0x18002b548  mov     rdi, rcx
0x18002b54b  lea     rbx, aFalse; "FALSE"
0x18002b552  mov     r8, r14
0x18002b555  lea     rdx, aIsAoacDeviceS; "Is AoAc device            : %s"
0x18002b55c  cmovz   r8, rbx
0x18002b560  xor     ecx, ecx; bool
0x18002b562  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b567  test    byte ptr [rdi+34h], 1
0x18002b56b  lea     rdx, aIsCadRequiredS; "Is CAD Required           : %s"
0x18002b572  mov     r8, r14
0x18002b575  cmovz   r8, rbx
0x18002b579  xor     ecx, ecx; bool
0x18002b57b  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b580  test    byte ptr [rdi+34h], 4
0x18002b584  lea     rdx, aAreBatteriesAv; "Are batteries available   : %s"
0x18002b58b  mov     r8, r14
0x18002b58e  cmovz   r8, rbx
0x18002b592  xor     ecx, ecx; bool
0x18002b594  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b599  test    byte ptr [rdi+34h], 2
0x18002b59d  lea     rdx, aCanThisDeviceS; "Can this device standby   : %s"
0x18002b5a4  mov     r8, r14
0x18002b5a7  cmovz   r8, rbx
0x18002b5ab  xor     ecx, ecx; bool
0x18002b5ad  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b5b2  test    byte ptr [rdi+34h], 10h
0x18002b5b6  lea     rdx, aCanThisDeviceH; "Can this device hibernate : %s"
0x18002b5bd  mov     r8, r14
0x18002b5c0  cmovz   r8, rbx
0x18002b5c4  xor     ecx, ecx; bool
0x18002b5c6  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b5cb  xor     r12d, r12d
0x18002b5ce  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x18002b5d2  xor     ecx, ecx; UserRootPowerKey
0x18002b5d4  mov     [rbp+ActivePolicyGuid], r12
0x18002b5d8  call    cs:__imp_PowerGetActiveScheme
0x18002b5de  mov     esi, eax
0x18002b5e0  test    eax, eax
0x18002b5e2  jle     short loc_18002B5ED
0x18002b5e4  movzx   esi, ax
0x18002b5e7  or      esi, 80070000h
0x18002b5ed  test    esi, esi
0x18002b5ef  js      loc_18002B9CD
0x18002b5f5  test    byte ptr [rdi+34h], 8
0x18002b5f9  jz      loc_18002B84D
0x18002b5ff  lea     rcx, POLID_AllowDomainDelayLock
0x18002b606  call    cs:__imp_SHWindowsPolicy
0x18002b60c  test    eax, eax
0x18002b60e  jnz     short loc_18002B666
0x18002b610  mov     eax, cs:?s_bIsDomainMember@?1??IsOS_OS_DOMAINMEMBER@@YAHXZ@4W4TRIBIT@@A; TRIBIT `IsOS_OS_DOMAINMEMBER(void)'::`2'::s_bIsDomainMember
0x18002b616  test    eax, eax
0x18002b618  jnz     short loc_18002B65E
0x18002b61a  lea     r8, [rbp+BufferType]; BufferType
0x18002b61e  mov     [rbp+NameBuffer], r12
0x18002b622  lea     rdx, [rbp+NameBuffer]; lpNameBuffer
0x18002b626  mov     [rbp+BufferType], r12d
0x18002b62a  xor     ecx, ecx; lpServer
0x18002b62c  call    cs:__imp_NetGetJoinInformation
0x18002b632  test    eax, eax
0x18002b634  jnz     short loc_18002B64A
0x18002b636  mov     rcx, [rbp+NameBuffer]; Buffer
0x18002b63a  test    rcx, rcx
0x18002b63d  jz      short loc_18002B645
0x18002b63f  call    cs:__imp_NetApiBufferFree
0x18002b645  mov     ecx, [rbp+BufferType]
0x18002b648  jmp     short loc_18002B64D
0x18002b64a  mov     ecx, r12d
0x18002b64d  cmp     ecx, 3
0x18002b650  mov     eax, r12d
0x18002b653  setnz   al
0x18002b656  inc     eax
0x18002b658  mov     cs:?s_bIsDomainMember@?1??IsOS_OS_DOMAINMEMBER@@YAHXZ@4W4TRIBIT@@A, eax; TRIBIT `IsOS_OS_DOMAINMEMBER(void)'::`2'::s_bIsDomainMember
0x18002b65e  mov     sil, 1
0x18002b661  cmp     eax, 1
0x18002b664  jz      short loc_18002B669
0x18002b666  mov     sil, r12b
0x18002b669  test    sil, sil
0x18002b66c  lea     rdx, aIsDelaylockDis; "Is Delaylock disabled by policy: %s"
0x18002b673  mov     r8, r14
0x18002b676  cmovz   r8, rbx
0x18002b67a  xor     ecx, ecx; bool
0x18002b67c  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b681  mov     r8, [rbp+ActivePolicyGuid]; struct _GUID *
0x18002b685  mov     al, sil
0x18002b688  neg     al
0x18002b68a  mov     rcx, rdi; this
0x18002b68d  sbb     ebx, ebx
0x18002b68f  or      r15d, 0FFFFFFFFh
0x18002b693  not     ebx
0x18002b695  mov     dword ptr [rbp+pvParam], r15d
0x18002b699  and     ebx, r15d
0x18002b69c  call    ?_IsPasswordOnWakeRequired@CMachineLockSettings@@AEAA_N_NPEAU_GUID@@@Z; CMachineLockSettings::_IsPasswordOnWakeRequired(bool,_GUID *)
0x18002b6a1  test    al, al
0x18002b6a3  jnz     short loc_18002B6A9
0x18002b6a5  or      dword ptr [rdi+34h], 20h
0x18002b6a9  test    byte ptr [rdi+34h], 1
0x18002b6ad  jnz     loc_18002B822
0x18002b6b3  test    byte ptr [rdi+34h], 20h
0x18002b6b7  jnz     loc_18002B822
0x18002b6bd  test    sil, sil
0x18002b6c0  jnz     loc_18002B822
0x18002b6c6  call    ?GetEASPolicyDeviceLockTimeoutValue@@YAKXZ; GetEASPolicyDeviceLockTimeoutValue(void)
0x18002b6cb  mov     r8d, eax
0x18002b6ce  lea     rdx, aEasTimeout0xX; "EAS timeout: 0x%x"
0x18002b6d5  xor     ecx, ecx; bool
0x18002b6d7  mov     esi, eax
0x18002b6d9  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b6de  call    ?GetEASGroupPolicyTimeout@@YAKXZ; GetEASGroupPolicyTimeout(void)
0x18002b6e3  mov     r8d, eax
0x18002b6e6  lea     rdx, aGroupPolicyTim; "Group policy timeout: 0x%x"
0x18002b6ed  xor     ecx, ecx; bool
0x18002b6ef  mov     ebx, eax
0x18002b6f1  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b6f6  xor     edx, edx; uiParam
0x18002b6f8  mov     dword ptr [rbp+NameBuffer], r12d
0x18002b6fc  xor     r9d, r9d; fWinIni
0x18002b6ff  lea     r8, [rbp+NameBuffer]; pvParam
0x18002b703  lea     ecx, [rdx+76h]; uiAction
0x18002b706  call    cs:__imp_SystemParametersInfoW
0x18002b70c  test    eax, eax
0x18002b70e  jz      short loc_18002B75E
0x18002b710  cmp     dword ptr [rbp+NameBuffer], r12d
0x18002b714  lea     rax, aFalse; "FALSE"
0x18002b71b  lea     rdx, aSecureScreenSa; "Secure screen saver enabled: %s"
0x18002b722  cmovz   r14, rax
0x18002b726  xor     ecx, ecx; bool
0x18002b728  mov     r8, r14
0x18002b72b  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b730  cmp     dword ptr [rbp+NameBuffer], r12d
0x18002b734  jz      short loc_18002B75E
0x18002b736  xor     edx, edx; uiParam
0x18002b738  lea     r8, [rbp+pvParam]; pvParam
0x18002b73c  xor     r9d, r9d; fWinIni
0x18002b73f  lea     ecx, [rdx+0Eh]; uiAction
0x18002b742  call    cs:__imp_SystemParametersInfoW
0x18002b748  test    eax, eax
0x18002b74a  jz      short loc_18002B75E
0x18002b74c  mov     r8d, dword ptr [rbp+pvParam]
0x18002b750  lea     rdx, aScreensaverTim; "Screensaver timeout: 0x%x"
0x18002b757  xor     ecx, ecx; bool
0x18002b759  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b75e  test    byte ptr [rdi+34h], 2
0x18002b762  jz      loc_18002B833
0x18002b768  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18002b76c  lea     rax, [rbp+arg_18]
0x18002b770  mov     [rsp+50h+BufferSize], rax; BufferSize
0x18002b775  lea     r9, GUID_STANDBY_TIMEOUT; PowerSettingGuid
0x18002b77c  lea     rax, [rbp+BufferType]
0x18002b780  mov     [rbp+BufferType], r15d
0x18002b784  mov     [rsp+50h+Buffer], rax; Buffer
0x18002b789  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18002b790  xor     ecx, ecx; RootPowerKey
0x18002b792  mov     [rsp+50h+Type], r12; Type
0x18002b797  mov     [rbp+arg_18], 4
0x18002b79e  call    cs:__imp_PowerReadACValue
0x18002b7a4  mov     r8d, [rbp+BufferType]
0x18002b7a8  lea     rdx, aSleepAcValueTi; "Sleep (AC value) timeout: 0x%x"
0x18002b7af  xor     ecx, ecx; bool
0x18002b7b1  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b7b6  mov     eax, [rbp+BufferType]
0x18002b7b9  cmp     dword ptr [rbp+pvParam], eax
0x18002b7bc  jb      short loc_18002B7C1
0x18002b7be  mov     dword ptr [rbp+pvParam], eax
0x18002b7c1  test    byte ptr [rdi+34h], 4
0x18002b7c5  jz      short loc_18002B833
0x18002b7c7  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18002b7cb  lea     rax, [rbp+arg_18]
0x18002b7cf  mov     [rsp+50h+BufferSize], rax; BufferSize
0x18002b7d4  lea     r9, GUID_STANDBY_TIMEOUT; PowerSettingGuid
0x18002b7db  lea     rax, [rbp+BufferType]
0x18002b7df  mov     [rbp+BufferType], r15d
0x18002b7e3  mov     [rsp+50h+Buffer], rax; Buffer
0x18002b7e8  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18002b7ef  xor     ecx, ecx; RootPowerKey
0x18002b7f1  mov     [rsp+50h+Type], r12; Type
0x18002b7f6  mov     [rbp+arg_18], 4
0x18002b7fd  call    cs:__imp_PowerReadDCValue
0x18002b803  mov     r8d, [rbp+BufferType]
0x18002b807  lea     rdx, aSleepDcValueTi; "Sleep (DC value) timeout: 0x%x"
0x18002b80e  xor     ecx, ecx; bool
0x18002b810  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b815  mov     eax, [rbp+BufferType]
0x18002b818  cmp     dword ptr [rbp+pvParam], eax
0x18002b81b  jb      short loc_18002B833
0x18002b81d  mov     dword ptr [rbp+pvParam], eax
0x18002b820  jmp     short loc_18002B833
0x18002b822  lea     rdx, aDelaylockDropD; "DelayLock drop down setting will be dis"...
0x18002b829  xor     ecx, ecx; bool
0x18002b82b  mov     esi, r15d
0x18002b82e  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b833  mov     r9d, dword ptr [rbp+pvParam]; unsigned int
0x18002b837  mov     r8d, ebx; unsigned int
0x18002b83a  mov     rcx, rdi; this
0x18002b83d  mov     dword ptr [rsp+50h+Type], esi; unsigned int
0x18002b841  call    ?_InitDelayLockItems@CMachineLockSettings@@AEAAJ_NKKK@Z; CMachineLockSettings::_InitDelayLockItems(bool,ulong,ulong,ulong)
0x18002b846  mov     esi, eax
0x18002b848  jmp     loc_18002B9C1
0x18002b84d  test    byte ptr [rdi+34h], 2
0x18002b851  mov     r15b, r12b
0x18002b854  jnz     short loc_18002B860
0x18002b856  test    byte ptr [rdi+34h], 10h
0x18002b85a  jz      loc_18002B9BA
0x18002b860  call    LUAIsAdminAndIsOSSilentElevationOn
0x18002b865  test    eax, eax
0x18002b867  lea     rdx, aIsSilentElevat; "Is silent elevation       : %s"
0x18002b86e  mov     ebx, eax
0x18002b870  mov     r8, r14
0x18002b873  lea     rax, aFalse; "FALSE"
0x18002b87a  cmovz   r8, rax
0x18002b87e  xor     ecx, ecx; bool
0x18002b880  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b885  test    ebx, ebx
0x18002b887  jnz     short loc_18002B892
0x18002b889  or      dword ptr [rdi+30h], 10h
0x18002b88d  jmp     loc_18002B934
0x18002b892  lea     rdx, [rbp+pvParam]; struct IPasswordOnWakeSetting **
0x18002b896  mov     [rbp+pvParam], r12
0x18002b89a  mov     rcx, rdi; this
0x18002b89d  call    ?_GetPasswordOnWakeSettingObject@CMachineLockSettings@@AEAAJPEAPEAUIPasswordOnWakeSetting@@@Z; CMachineLockSettings::_GetPasswordOnWakeSettingObject(IPasswordOnWakeSetting * *)
0x18002b8a2  mov     esi, eax
0x18002b8a4  test    eax, eax
0x18002b8a6  js      short loc_18002B902
0x18002b8a8  mov     rcx, [rbp+pvParam]
0x18002b8ac  lea     r9, [rbp+BufferType]
0x18002b8b0  mov     r8d, [rdi+34h]
0x18002b8b4  mov     rdx, [rbp+ActivePolicyGuid]
0x18002b8b8  mov     [rbp+BufferType], r12d
0x18002b8bc  mov     rax, [rcx]
0x18002b8bf  shr     r8d, 2
0x18002b8c3  and     r8d, 1
0x18002b8c7  mov     rax, [rax+18h]
0x18002b8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8d0  cmp     [rbp+BufferType], r12d
0x18002b8d4  lea     rdx, aIsRestrictedBy; "Is restricted by GP       : %s"
0x18002b8db  mov     esi, eax
0x18002b8dd  mov     r8, r14
0x18002b8e0  lea     rax, aFalse; "FALSE"
0x18002b8e7  cmovz   r8, rax
0x18002b8eb  xor     ecx, ecx; bool
0x18002b8ed  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b8f2  test    esi, esi
0x18002b8f4  js      short loc_18002B913
0x18002b8f6  cmp     [rbp+BufferType], r12d
0x18002b8fa  jz      short loc_18002B913
0x18002b8fc  or      dword ptr [rdi+30h], 1
0x18002b900  jmp     short loc_18002B913
0x18002b902  mov     r8d, eax
0x18002b905  lea     rdx, aFailedToCreate; "Failed to create 'require password on w"...
0x18002b90c  xor     ecx, ecx; bool
0x18002b90e  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b913  mov     rcx, [rbp+pvParam]
0x18002b917  test    rcx, rcx
0x18002b91a  jz      short loc_18002B92C
0x18002b91c  mov     [rbp+pvParam], r12
0x18002b920  mov     rax, [rcx]
0x18002b923  mov     rax, [rax+10h]
0x18002b927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b92c  test    esi, esi
0x18002b92e  js      loc_18002B9BA
0x18002b934  lea     rcx, [rbp+BufferType]
0x18002b938  mov     [rbp+BufferType], r12d
0x18002b93c  call    LUAIsUserUACAdmin
0x18002b941  mov     ebx, [rbp+BufferType]
0x18002b944  lea     rax, aFalse; "FALSE"
0x18002b94b  test    ebx, ebx
0x18002b94d  lea     rdx, aIsAdminUserS; "Is admin user             : %s"
0x18002b954  mov     r8, r14
0x18002b957  cmovz   r8, rax
0x18002b95b  xor     ecx, ecx; bool
0x18002b95d  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002b962  test    ebx, ebx
0x18002b964  jnz     short loc_18002B96A
0x18002b966  or      dword ptr [rdi+30h], 8
0x18002b96a  mov     r8, [rbp+ActivePolicyGuid]; struct _GUID *
0x18002b96e  mov     rcx, rdi; this
0x18002b971  call    ?_IsPasswordOnWakeRequired@CMachineLockSettings@@AEAA_N_NPEAU_GUID@@@Z; CMachineLockSettings::_IsPasswordOnWakeRequired(bool,_GUID *)
0x18002b976  mov     r15b, al
0x18002b979  call    ?GetEASGroupPolicyTimeout@@YAKXZ; GetEASGroupPolicyTimeout(void)
0x18002b97e  inc     eax
0x18002b980  test    eax, 0FFFFFFFEh
0x18002b985  jnz     short loc_18002B993
0x18002b987  call    ?GetEASPolicyDeviceLockTimeoutValue@@YAKXZ; GetEASPolicyDeviceLockTimeoutValue(void)
0x18002b98c  dec     eax
0x18002b98e  cmp     eax, 0FFFFFFFDh
0x18002b991  ja      short loc_18002B99A
0x18002b993  or      dword ptr [rdi+30h], 4
0x18002b997  mov     r15b, 1
0x18002b99a  test    byte ptr [rdi+30h], 4
  ... truncated ...
```
