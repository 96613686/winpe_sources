# CShareMediaCore::_IsMachineInPowerSavingMode(int *)

- ea: `0x18000e99c`
- end: `0x18000ec8a`
- name: `?_IsMachineInPowerSavingMode@CShareMediaCore@@AEAAJPEAH@Z`
- size: `750`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180010bec`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180003860`
- `0x180003888`
- `0x18000e99c`

## import_xrefs

- `KERNEL32!GetSystemPowerStatus` at `0x18000ea6a`
- `KERNEL32!GetSystemPowerStatus` at `0x18000ea6a`
- `KERNEL32!LocalFree` at `0x18000eb81`
- `KERNEL32!LocalFree` at `0x18000eb81`
- `KERNEL32!GetLastError` at `0x18000ea2c`
- `KERNEL32!GetLastError` at `0x18000ea74`
- `KERNEL32!GetLastError` at `0x18000ea2c`
- `KERNEL32!GetLastError` at `0x18000ea74`
- `POWRPROF!PowerReadDCValue` at `0x18000ebd7`
- `POWRPROF!PowerReadDCValue` at `0x18000ec23`
- `POWRPROF!PowerReadDCValue` at `0x18000ebd7`
- `POWRPROF!PowerReadDCValue` at `0x18000ec23`
- `POWRPROF!PowerReadACValue` at `0x18000eb03`
- `POWRPROF!PowerReadACValue` at `0x18000eb4f`
- `POWRPROF!PowerReadACValue` at `0x18000eb03`
- `POWRPROF!PowerReadACValue` at `0x18000eb4f`
- `POWRPROF!PowerGetActiveScheme` at `0x18000ea9b`
- `POWRPROF!PowerGetActiveScheme` at `0x18000ea9b`
- `POWRPROF!GetPwrCapabilities` at `0x18000ea22`
- `POWRPROF!GetPwrCapabilities` at `0x18000ea22`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::_IsMachineInPowerSavingMode(CShareMediaCore *this, int *a2)
{
  _QWORD *v3; // rcx
  signed int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  DWORD v7; // eax
  int v8; // ecx
  int v9; // eax
  DWORD BufferSize; // [rsp+40h] [rbp-49h] BYREF
  BYTE Buffer[4]; // [rsp+44h] [rbp-45h] BYREF
  UCHAR v13[8]; // [rsp+48h] [rbp-41h] BYREF
  GUID *ActivePolicyGuid; // [rsp+50h] [rbp-39h] BYREF
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+58h] [rbp-31h] BYREF
  _SYSTEM_POWER_CAPABILITIES spc; // [rsp+70h] [rbp-19h] BYREF

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    goto LABEL_43;
  }
  *a2 = 0;
  v4 = 0;
  memset_0(&spc, 0, sizeof(spc));
  if ( !GetPwrCapabilities(&spc) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( spc.SystemS1 || spc.SystemS2 || spc.SystemS3 || spc.SystemS4 )
  {
    *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
    SystemPowerStatus.BatteryFullLifeTime = 0;
    if ( !GetSystemPowerStatus(&SystemPowerStatus) )
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    if ( v4 >= 0 )
    {
      ActivePolicyGuid = 0;
      if ( !PowerGetActiveScheme(0, &ActivePolicyGuid) )
      {
        *(_DWORD *)Buffer = 0;
        *(_DWORD *)v13 = 0;
        BufferSize = 0;
        if ( SystemPowerStatus.ACLineStatus )
        {
          if ( !spc.SystemS1 && !spc.SystemS2 && !spc.SystemS3
            || (BufferSize = 4,
                !PowerReadACValue(
                   0,
                   ActivePolicyGuid,
                   &GUID_SLEEP_SUBGROUP,
                   &GUID_STANDBY_TIMEOUT,
                   0,
                   Buffer,
                   &BufferSize)) )
          {
            if ( !*(_DWORD *)Buffer && spc.SystemS4 )
            {
              BufferSize = 4;
              v7 = PowerReadACValue(
                     0,
                     ActivePolicyGuid,
                     &GUID_SLEEP_SUBGROUP,
                     &GUID_HIBERNATE_TIMEOUT,
                     0,
                     v13,
                     &BufferSize);
              v8 = v4;
              if ( v7 )
                v8 = -2147467259;
              v4 = v8;
            }
            if ( v4 < 0 )
              goto LABEL_32;
            goto LABEL_28;
          }
        }
        else if ( !spc.SystemS1 && !spc.SystemS2 && !spc.SystemS3
               || (BufferSize = 4,
                   !PowerReadDCValue(
                      0,
                      ActivePolicyGuid,
                      &GUID_SLEEP_SUBGROUP,
                      &GUID_STANDBY_TIMEOUT,
                      0,
                      Buffer,
                      &BufferSize)) )
        {
          if ( *(_DWORD *)Buffer )
          {
LABEL_30:
            v9 = 1;
LABEL_31:
            *a2 = v9;
LABEL_32:
            LocalFree(ActivePolicyGuid);
            goto LABEL_33;
          }
          if ( !spc.SystemS4
            || (BufferSize = 4,
                !PowerReadDCValue(
                   0,
                   ActivePolicyGuid,
                   &GUID_SLEEP_SUBGROUP,
                   &GUID_HIBERNATE_TIMEOUT,
                   0,
                   v13,
                   &BufferSize)) )
          {
LABEL_28:
            if ( !*(_DWORD *)Buffer )
            {
              v9 = 0;
              if ( !*(_DWORD *)v13 )
                goto LABEL_31;
            }
            goto LABEL_30;
          }
        }
        v4 = -2147467259;
        goto LABEL_32;
      }
    }
  }
LABEL_33:
  v3 = WPP_GLOBAL_Control;
LABEL_43:
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
    WPP_SF_d(v3[2], 46, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e99c  mov     [rsp-8+arg_0], rbx
0x18000e9a1  mov     [rsp-8+arg_10], rsi
0x18000e9a6  push    rbp
0x18000e9a7  push    r14
0x18000e9a9  push    r15
0x18000e9ab  lea     rbp, [rsp-47h]
0x18000e9b0  sub     rsp, 0D0h
0x18000e9b7  mov     rax, cs:__security_cookie
0x18000e9be  xor     rax, rsp
0x18000e9c1  mov     [rbp+57h+var_20], rax
0x18000e9c5  mov     rsi, rdx
0x18000e9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9cf  lea     r15, WPP_GLOBAL_Control
0x18000e9d6  cmp     rcx, r15
0x18000e9d9  jz      short loc_18000E9FD
0x18000e9db  test    byte ptr [rcx+1Ch], 20h
0x18000e9df  jz      short loc_18000E9FD
0x18000e9e1  mov     rcx, [rcx+10h]
0x18000e9e5  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e9ec  mov     edx, 2Dh ; '-'
0x18000e9f1  call    WPP_SF_
0x18000e9f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9fd  xor     r14d, r14d
0x18000ea00  test    rsi, rsi
0x18000ea03  jz      loc_18000EC3B
0x18000ea09  xor     edx, edx; Val
0x18000ea0b  mov     [rsi], r14d
0x18000ea0e  lea     r8d, [r14+4Ch]; Size
0x18000ea12  mov     ebx, r14d
0x18000ea15  lea     rcx, [rbp+57h+spc]; void *
0x18000ea19  call    memset_0
0x18000ea1e  lea     rcx, [rbp+57h+spc]; lpspc
0x18000ea22  call    cs:__imp_GetPwrCapabilities
0x18000ea28  test    al, al
0x18000ea2a  jnz     short loc_18000EA41
0x18000ea2c  call    cs:__imp_GetLastError
0x18000ea32  mov     ebx, eax
0x18000ea34  test    eax, eax
0x18000ea36  jle     short loc_18000EA41
0x18000ea38  movzx   ebx, ax
0x18000ea3b  or      ebx, 80070000h
0x18000ea41  cmp     [rbp+57h+spc.SystemS1], r14b
0x18000ea45  jnz     short loc_18000EA5D
0x18000ea47  cmp     [rbp+57h+spc.SystemS2], r14b
0x18000ea4b  jnz     short loc_18000EA5D
0x18000ea4d  cmp     [rbp+57h+spc.SystemS3], r14b
0x18000ea51  jnz     short loc_18000EA5D
0x18000ea53  cmp     [rbp+57h+spc.SystemS4], r14b
0x18000ea57  jz      loc_18000EB87
0x18000ea5d  xor     eax, eax
0x18000ea5f  lea     rcx, [rbp+57h+SystemPowerStatus]; lpSystemPowerStatus
0x18000ea63  mov     qword ptr [rbp+57h+SystemPowerStatus.ACLineStatus], rax
0x18000ea67  mov     [rbp+57h+SystemPowerStatus.BatteryFullLifeTime], eax
0x18000ea6a  call    cs:__imp_GetSystemPowerStatus
0x18000ea70  test    eax, eax
0x18000ea72  jnz     short loc_18000EA89
0x18000ea74  call    cs:__imp_GetLastError
0x18000ea7a  mov     ebx, eax
0x18000ea7c  test    eax, eax
0x18000ea7e  jle     short loc_18000EA89
0x18000ea80  movzx   ebx, ax
0x18000ea83  or      ebx, 80070000h
0x18000ea89  test    ebx, ebx
0x18000ea8b  js      loc_18000EB87
0x18000ea91  lea     rdx, [rbp+57h+ActivePolicyGuid]; ActivePolicyGuid
0x18000ea95  mov     [rbp+57h+ActivePolicyGuid], r14
0x18000ea99  xor     ecx, ecx; UserRootPowerKey
0x18000ea9b  call    cs:__imp_PowerGetActiveScheme
0x18000eaa1  test    eax, eax
0x18000eaa3  jnz     loc_18000EB87
0x18000eaa9  mov     dword ptr [rbp+57h+var_9C], r14d
0x18000eaad  mov     dword ptr [rbp+57h+var_98], r14d
0x18000eab1  mov     [rbp+57h+var_A0], r14d
0x18000eab5  cmp     [rbp+57h+SystemPowerStatus.ACLineStatus], r14b
0x18000eab9  jz      loc_18000EB93
0x18000eabf  cmp     [rbp+57h+spc.SystemS1], r14b
0x18000eac3  jnz     short loc_18000EAD1
0x18000eac5  cmp     [rbp+57h+spc.SystemS2], r14b
0x18000eac9  jnz     short loc_18000EAD1
0x18000eacb  cmp     [rbp+57h+spc.SystemS3], r14b
0x18000eacf  jz      short loc_18000EB11
0x18000ead1  mov     rdx, [rbp+57h+ActivePolicyGuid]; SchemeGuid
0x18000ead5  lea     rax, [rbp+57h+var_A0]
0x18000ead9  mov     [rsp+0E0h+BufferSize], rax; BufferSize
0x18000eade  lea     r9, GUID_STANDBY_TIMEOUT; PowerSettingGuid
0x18000eae5  lea     rax, [rbp+57h+var_9C]
0x18000eae9  mov     [rbp+57h+var_A0], 4
0x18000eaf0  mov     [rsp+0E0h+Buffer], rax; Buffer
0x18000eaf5  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18000eafc  xor     ecx, ecx; RootPowerKey
0x18000eafe  mov     [rsp+0E0h+Type], r14; Type
0x18000eb03  call    cs:__imp_PowerReadACValue
0x18000eb09  test    eax, eax
0x18000eb0b  jnz     loc_18000EC31
0x18000eb11  cmp     dword ptr [rbp+57h+var_9C], r14d
0x18000eb15  jnz     short loc_18000EB63
0x18000eb17  cmp     [rbp+57h+spc.SystemS4], r14b
0x18000eb1b  jz      short loc_18000EB63
0x18000eb1d  mov     rdx, [rbp+57h+ActivePolicyGuid]; SchemeGuid
0x18000eb21  lea     rax, [rbp+57h+var_A0]
0x18000eb25  mov     [rsp+0E0h+BufferSize], rax; BufferSize
0x18000eb2a  lea     r9, GUID_HIBERNATE_TIMEOUT; PowerSettingGuid
0x18000eb31  lea     rax, [rbp+57h+var_98]
0x18000eb35  mov     [rbp+57h+var_A0], 4
0x18000eb3c  mov     [rsp+0E0h+Buffer], rax; Buffer
0x18000eb41  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18000eb48  xor     ecx, ecx; RootPowerKey
0x18000eb4a  mov     [rsp+0E0h+Type], r14; Type
0x18000eb4f  call    cs:__imp_PowerReadACValue
0x18000eb55  mov     ecx, ebx
0x18000eb57  mov     ebx, 80004005h
0x18000eb5c  test    eax, eax
0x18000eb5e  cmovnz  ecx, ebx
0x18000eb61  mov     ebx, ecx
0x18000eb63  test    ebx, ebx
0x18000eb65  js      short loc_18000EB7D
0x18000eb67  cmp     dword ptr [rbp+57h+var_9C], r14d
0x18000eb6b  jnz     short loc_18000EB76
0x18000eb6d  mov     eax, r14d
0x18000eb70  cmp     dword ptr [rbp+57h+var_98], r14d
0x18000eb74  jz      short loc_18000EB7B
0x18000eb76  mov     eax, 1
0x18000eb7b  mov     [rsi], eax
0x18000eb7d  mov     rcx, [rbp+57h+ActivePolicyGuid]; hMem
0x18000eb81  call    cs:__imp_LocalFree
0x18000eb87  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb8e  jmp     loc_18000EC40
0x18000eb93  cmp     [rbp+57h+spc.SystemS1], r14b
0x18000eb97  jnz     short loc_18000EBA5
0x18000eb99  cmp     [rbp+57h+spc.SystemS2], r14b
0x18000eb9d  jnz     short loc_18000EBA5
0x18000eb9f  cmp     [rbp+57h+spc.SystemS3], r14b
0x18000eba3  jz      short loc_18000EBE1
0x18000eba5  mov     rdx, [rbp+57h+ActivePolicyGuid]; SchemeGuid
0x18000eba9  lea     rax, [rbp+57h+var_A0]
0x18000ebad  mov     [rsp+0E0h+BufferSize], rax; BufferSize
0x18000ebb2  lea     r9, GUID_STANDBY_TIMEOUT; PowerSettingGuid
0x18000ebb9  lea     rax, [rbp+57h+var_9C]
0x18000ebbd  mov     [rbp+57h+var_A0], 4
0x18000ebc4  mov     [rsp+0E0h+Buffer], rax; Buffer
0x18000ebc9  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18000ebd0  xor     ecx, ecx; RootPowerKey
0x18000ebd2  mov     [rsp+0E0h+Type], r14; Type
0x18000ebd7  call    cs:__imp_PowerReadDCValue
0x18000ebdd  test    eax, eax
0x18000ebdf  jnz     short loc_18000EC31
0x18000ebe1  cmp     dword ptr [rbp+57h+var_9C], r14d
0x18000ebe5  jnz     short loc_18000EB76
0x18000ebe7  cmp     [rbp+57h+spc.SystemS4], r14b
0x18000ebeb  jz      loc_18000EB67
0x18000ebf1  mov     rdx, [rbp+57h+ActivePolicyGuid]; SchemeGuid
0x18000ebf5  lea     rax, [rbp+57h+var_A0]
0x18000ebf9  mov     [rsp+0E0h+BufferSize], rax; BufferSize
0x18000ebfe  lea     r9, GUID_HIBERNATE_TIMEOUT; PowerSettingGuid
0x18000ec05  lea     rax, [rbp+57h+var_98]
0x18000ec09  mov     [rbp+57h+var_A0], 4
0x18000ec10  mov     [rsp+0E0h+Buffer], rax; Buffer
0x18000ec15  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18000ec1c  xor     ecx, ecx; RootPowerKey
0x18000ec1e  mov     [rsp+0E0h+Type], r14; Type
0x18000ec23  call    cs:__imp_PowerReadDCValue
0x18000ec29  test    eax, eax
0x18000ec2b  jz      loc_18000EB67
0x18000ec31  mov     ebx, 80004005h
0x18000ec36  jmp     loc_18000EB7D
0x18000ec3b  mov     ebx, 80004003h
0x18000ec40  cmp     rcx, r15
0x18000ec43  jz      short loc_18000EC63
0x18000ec45  test    byte ptr [rcx+1Ch], 20h
0x18000ec49  jz      short loc_18000EC63
0x18000ec4b  mov     rcx, [rcx+10h]
0x18000ec4f  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000ec56  mov     edx, 2Eh ; '.'
0x18000ec5b  mov     r9d, ebx
0x18000ec5e  call    WPP_SF_d
0x18000ec63  mov     eax, ebx
0x18000ec65  mov     rcx, [rbp+57h+var_20]
0x18000ec69  xor     rcx, rsp; StackCookie
0x18000ec6c  call    __security_check_cookie
0x18000ec71  lea     r11, [rsp+0E0h+var_10]
0x18000ec79  mov     rbx, [r11+20h]
0x18000ec7d  mov     rsi, [r11+30h]
0x18000ec81  mov     rsp, r11
0x18000ec84  pop     r15
0x18000ec86  pop     r14
0x18000ec88  pop     rbp
0x18000ec89  retn
```
