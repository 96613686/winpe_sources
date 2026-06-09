# UbpmpReadMaintenanceSettings(_UBPM_MAINTENANCE_PARAMETERS *,ushort const * *)

- ea: `0x180029de0`
- end: `0x18002a23d`
- name: `?UbpmpReadMaintenanceSettings@@YAKPEAU_UBPM_MAINTENANCE_PARAMETERS@@PEAPEBG@Z`
- size: `1117`
- prototype: `unsigned int __fastcall(struct _UBPM_MAINTENANCE_PARAMETERS *, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030390`
- `0x1800390b0`

## callees

- `0x18000fbf0`
- `0x180029de0`
- `0x18002a244`
- `0x18002a380`
- `0x18002a420`
- `0x18002a444`
- `0x18002a4a8`
- `0x18002a784`
- `0x180040260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f5c`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x180029f4c`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x180029f4c`

## string_xrefs

- `0x180029e89`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Schedule\Maintenance`
- `0x180029e4b`: `\Registry\Machine\Software\Policies\Microsoft\Windows\Task Scheduler\Maintenance`
- `0x18002a0bd`: `Invalid registry keys`

## pseudocode

```c
__int64 __fastcall UbpmpReadMaintenanceSettings(struct _UBPM_MAINTENANCE_PARAMETERS *a1, const unsigned __int16 **a2)
{
  struct _KEY_VALUE_PARTIAL_INFORMATION *v3; // rbx
  ULONG v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  ULONG LastError; // edi
  HANDLE v10; // rdi
  unsigned int Value; // eax
  HANDLE v12; // rdi
  unsigned int v13; // eax
  unsigned int v14; // eax
  HANDLE v15; // rdi
  const unsigned __int16 *v16; // rax
  HANDLE v18; // rdi
  unsigned int v19; // eax
  HANDLE v20; // rdi
  unsigned int v21; // eax
  SYSTEMTIME v22; // xmm1
  __int128 v23; // xmm0
  struct _KEY_VALUE_PARTIAL_INFORMATION *v24; // [rsp+20h] [rbp-39h] BYREF
  unsigned __int8 v25[4]; // [rsp+28h] [rbp-31h] BYREF
  unsigned int v26; // [rsp+2Ch] [rbp-2Dh] BYREF
  HANDLE v27; // [rsp+30h] [rbp-29h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  SYSTEMTIME LocalTime[3]; // [rsp+40h] [rbp-19h] BYREF
  struct _SYSTEMTIME UniversalTime; // [rsp+70h] [rbp+17h] BYREF

  memset(LocalTime, 0, 44);
  v3 = 0;
  KeyHandle = 0;
  v27 = 0;
  v24 = 0;
  v26 = 0;
  UniversalTime = 0;
  v25[0] = 0;
  UbpmpInitializeMaintenanceParameters(LocalTime);
  v5 = UbpmUtilsRegOpenKey(
         L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\Task Scheduler\\Maintenance",
         0x20019u,
         &KeyHandle);
  LastError = v5;
  if ( v5 - 4 <= 0x48B )
    goto LABEL_44;
  if ( v5 == 1 )
    goto LABEL_44;
  if ( v5 >= 0x491 )
    goto LABEL_44;
  LastError = UbpmUtilsRegOpenKey(
                L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
                0x20019u,
                &v27);
  if ( LastError - 4 <= 0x48B || LastError == 1 || LastError >= 0x491 )
    goto LABEL_44;
  v10 = v27;
  Value = 2;
  if ( !KeyHandle
    || (Value = UbpmpUtilsRegGetValue(KeyHandle, L"Activation Boundary", &v24, &v26), v3 = v24, Value == 2) )
  {
    if ( v10 )
    {
      Value = UbpmpUtilsRegGetValue(v10, L"Activation Boundary", &v24, &v26);
      v3 = v24;
    }
  }
  if ( Value )
    goto LABEL_38;
  if ( !v3 || v3->DataLength <= 2 )
    goto LABEL_19;
  Value = UbpmUtilsParseDateTime(
            (const unsigned __int16 *)v3->Data,
            ((unsigned __int64)v3->DataLength - 2) >> 1,
            LocalTime,
            v25);
  if ( Value )
  {
LABEL_38:
    if ( Value != 2 )
    {
      v16 = L"Automatic Maintenance Activation Boundary";
      goto LABEL_40;
    }
LABEL_19:
    v12 = v27;
    if ( KeyHandle )
    {
      v13 = UbpmpUtilsRegGetValue(KeyHandle, L"Randomized", &v24, &v26);
      if ( !v13 )
        goto LABEL_25;
      if ( v13 != 2 )
      {
LABEL_41:
        v3 = v24;
        goto LABEL_42;
      }
      v3 = v24;
    }
    if ( !v12 )
      goto LABEL_28;
    v13 = UbpmpUtilsRegGetValue(v12, L"Randomized", &v24, &v26);
    if ( !v13 )
    {
LABEL_25:
      v3 = v24;
      if ( !v24 )
        goto LABEL_43;
      if ( v24->DataLength == 4 )
      {
        HIBYTE(LocalTime[2].wDay) = *(_DWORD *)v24->Data != 0;
        goto LABEL_28;
      }
LABEL_42:
      if ( v13 != 2 )
        goto LABEL_43;
LABEL_28:
      v14 = 2;
      v15 = v27;
      if ( !KeyHandle || (v14 = UbpmpUtilsRegGetValue(KeyHandle, L"Random Delay", &v24, &v26), v3 = v24, v14 == 2) )
      {
        if ( v15 )
        {
          v14 = UbpmpUtilsRegGetValue(v15, L"Random Delay", &v24, &v26);
          v3 = v24;
        }
      }
      if ( (v14
         || v3
         && v3->DataLength >= 2
         && (v14 = UbpmUtilsParseTimeSpan(
                     (const unsigned __int16 *)v3->Data,
                     ((unsigned __int64)v3->DataLength - 2) >> 1,
                     (struct _UBPM_TIMESPAN *)&LocalTime[1].wHour)) != 0)
        && v14 != 2 )
      {
        v16 = L"Automatic Maintenance Random Delay";
LABEL_40:
        LastError = 87;
LABEL_45:
        *a2 = v16;
        goto LABEL_46;
      }
      v18 = v27;
      *(_DWORD *)&LocalTime[1].wHour = 0;
      LocalTime[1].wMilliseconds = 0;
      if ( KeyHandle )
      {
        v19 = UbpmpUtilsRegGetValue(KeyHandle, L"WakeUp", &v24, &v26);
        if ( !v19 )
        {
LABEL_53:
          v3 = v24;
          if ( !v24 )
            goto LABEL_67;
          if ( v24->DataLength == 4 )
          {
            LOBYTE(LocalTime[2].wDay) = *(_DWORD *)v24->Data != 0;
            goto LABEL_56;
          }
LABEL_66:
          if ( v19 == 2 )
          {
LABEL_56:
            v20 = v27;
            if ( KeyHandle )
            {
              v21 = UbpmpUtilsRegGetValue(KeyHandle, L"MaintenanceDisabled", &v24, &v26);
              if ( !v21 )
                goto LABEL_62;
              if ( v21 != 2 )
              {
LABEL_68:
                v3 = v24;
LABEL_69:
                if ( v21 == 2 )
                  goto LABEL_70;
                goto LABEL_43;
              }
              v3 = v24;
            }
            if ( !v20 )
            {
LABEL_70:
              LastError = 0;
              *(_QWORD *)&LocalTime[1].wYear = 0x1E00015180LL;
              v22 = LocalTime[1];
              *(SYSTEMTIME *)a1 = LocalTime[0];
              v23 = *(_OWORD *)&LocalTime[1].wSecond;
              *((SYSTEMTIME *)a1 + 1) = v22;
              *(_OWORD *)((char *)a1 + 28) = v23;
              goto LABEL_46;
            }
            v21 = UbpmpUtilsRegGetValue(v20, L"MaintenanceDisabled", &v24, &v26);
            if ( !v21 )
            {
LABEL_62:
              v3 = v24;
              if ( v24 )
              {
                if ( v24->DataLength == 4 )
                {
                  LOBYTE(LocalTime[2].wHour) = *(_DWORD *)v24->Data != 0;
                  goto LABEL_70;
                }
                goto LABEL_69;
              }
LABEL_43:
              LastError = 87;
LABEL_44:
              v16 = L"Invalid registry keys";
              goto LABEL_45;
            }
            goto LABEL_68;
          }
LABEL_67:
          v16 = L"Automatic Maintenance WakeUp Policy";
          goto LABEL_40;
        }
        if ( v19 != 2 )
        {
LABEL_65:
          v3 = v24;
          goto LABEL_66;
        }
        v3 = v24;
      }
      if ( !v18 )
        goto LABEL_56;
      v19 = UbpmpUtilsRegGetValue(v18, L"WakeUp", &v24, &v26);
      if ( !v19 )
        goto LABEL_53;
      goto LABEL_65;
    }
    goto LABEL_41;
  }
  if ( v25[0] )
    goto LABEL_19;
  if ( TzSpecificLocalTimeToSystemTime(0, LocalTime, &UniversalTime) )
  {
    LocalTime[0] = UniversalTime;
    goto LABEL_19;
  }
  LastError = GetLastError();
LABEL_46:
  UBPM_MIDL_user_free(v3, v6, v7, v8);
  UbpmUtilsRegCloseKey(v27);
  UbpmUtilsRegCloseKey(KeyHandle);
  return LastError;
}

```

## disassembly

```asm
0x180029de0  mov     [rsp-8+arg_10], rbx
0x180029de5  push    rbp
0x180029de6  push    rsi
0x180029de7  push    rdi
0x180029de8  push    r12
0x180029dea  push    r14
0x180029dec  lea     rbp, [rsp-37h]
0x180029df1  sub     rsp, 90h
0x180029df8  mov     rax, cs:__security_cookie
0x180029dff  xor     rax, rsp
0x180029e02  mov     [rbp+57h+var_30], rax
0x180029e06  xor     eax, eax
0x180029e08  xorps   xmm0, xmm0
0x180029e0b  mov     r14, rcx
0x180029e0e  mov     [rbp+57h+LocalTime.wYear], ax
0x180029e12  movups  [rbp+57h+var_5E], xmm0
0x180029e16  xor     ebx, ebx
0x180029e18  mov     [rbp+57h+KeyHandle], rax
0x180029e1c  lea     rcx, [rbp+57h+LocalTime]; struct _SYSTEMTIME *
0x180029e20  mov     [rbp+57h+var_80], rax
0x180029e24  movups  [rbp+57h+var_5E+0Ah], xmm0
0x180029e28  mov     rsi, rdx
0x180029e2b  mov     [rbp+57h+var_90], rbx
0x180029e2f  movups  xmmword ptr [rbp+57h+LocalTime.wMonth], xmm0
0x180029e33  mov     [rbp+57h+var_84], eax
0x180029e36  movups  xmmword ptr [rbp+57h+UniversalTime.wYear], xmm0
0x180029e3a  mov     [rbp+57h+var_88], al
0x180029e3d  call    ?UbpmpInitializeMaintenanceParameters@@YAXPEAU_UBPM_MAINTENANCE_PARAMETERS@@@Z; UbpmpInitializeMaintenanceParameters(_UBPM_MAINTENANCE_PARAMETERS *)
0x180029e42  lea     r8, [rbp+57h+KeyHandle]; KeyHandle
0x180029e46  mov     edx, 20019h; DesiredAccess
0x180029e4b  lea     rcx, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Policies"...
0x180029e52  call    ?UbpmUtilsRegOpenKey@@YAKPEBGKPEAPEAX@Z; UbpmUtilsRegOpenKey(ushort const *,ulong,void * *)
0x180029e57  mov     edi, eax
0x180029e59  lea     ecx, [rax-4]
0x180029e5c  cmp     ecx, 48Bh
0x180029e62  jbe     loc_18002A0BD
0x180029e68  cmp     eax, 1
0x180029e6b  jz      loc_18002A0BD
0x180029e71  mov     r12d, 491h
0x180029e77  cmp     eax, r12d
0x180029e7a  jnb     loc_18002A0BD
0x180029e80  lea     r8, [rbp+57h+var_80]; KeyHandle
0x180029e84  mov     edx, 20019h; DesiredAccess
0x180029e89  lea     rcx, aRegistryMachin; "\\Registry\\Machine\\Software\\Microsof"...
0x180029e90  call    ?UbpmUtilsRegOpenKey@@YAKPEBGKPEAPEAX@Z; UbpmUtilsRegOpenKey(ushort const *,ulong,void * *)
0x180029e95  mov     edi, eax
0x180029e97  add     eax, 0FFFFFFFCh
0x180029e9a  cmp     eax, 48Bh
0x180029e9f  jbe     loc_18002A0BD
0x180029ea5  cmp     edi, 1
0x180029ea8  jz      loc_18002A0BD
0x180029eae  cmp     edi, r12d
0x180029eb1  jnb     loc_18002A0BD
0x180029eb7  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180029ebb  lea     r12d, [rbx+2]
0x180029ebf  mov     rdi, [rbp+57h+var_80]
0x180029ec3  mov     eax, r12d
0x180029ec6  test    rcx, rcx
0x180029ec9  jz      short loc_180029EE8
0x180029ecb  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180029ecf  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180029ed3  lea     rdx, aActivationBoun; "Activation Boundary"
0x180029eda  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180029edf  mov     rbx, [rbp+57h+var_90]
0x180029ee3  cmp     eax, r12d
0x180029ee6  jnz     short loc_180029F08
0x180029ee8  test    rdi, rdi
0x180029eeb  jz      short loc_180029F08
0x180029eed  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180029ef1  mov     rcx, rdi; KeyHandle
0x180029ef4  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180029ef8  lea     rdx, aActivationBoun; "Activation Boundary"
0x180029eff  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180029f04  mov     rbx, [rbp+57h+var_90]
0x180029f08  test    eax, eax
0x180029f0a  jnz     loc_18002A094
0x180029f10  test    rbx, rbx
0x180029f13  jz      short loc_180029F8F
0x180029f15  cmp     [rbx+8], r12d
0x180029f19  jbe     short loc_180029F8F
0x180029f1b  mov     edx, [rbx+8]
0x180029f1e  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x180029f22  sub     rdx, r12
0x180029f25  lea     r9, [rbp+57h+var_88]; unsigned __int8 *
0x180029f29  shr     rdx, 1; unsigned __int64
0x180029f2c  lea     r8, [rbp+57h+LocalTime]; struct _SYSTEMTIME *
0x180029f30  call    ?UbpmUtilsParseDateTime@@YAKPEBG_KPEAU_SYSTEMTIME@@PEAE@Z; UbpmUtilsParseDateTime(ushort const *,unsigned __int64,_SYSTEMTIME *,uchar *)
0x180029f35  test    eax, eax
0x180029f37  jnz     loc_18002A094
0x180029f3d  cmp     [rbp+57h+var_88], al
0x180029f40  jnz     short loc_180029F8F
0x180029f42  lea     r8, [rbp+57h+UniversalTime]; lpUniversalTime
0x180029f46  xor     ecx, ecx; lpTimeZoneInformation
0x180029f48  lea     rdx, [rbp+57h+LocalTime]; lpLocalTime
0x180029f4c  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x180029f53  nop     dword ptr [rax+rax+00h]
0x180029f58  test    eax, eax
0x180029f5a  jnz     short loc_180029F6F
0x180029f5c  call    cs:__imp_GetLastError
0x180029f63  nop     dword ptr [rax+rax+00h]
0x180029f68  mov     edi, eax
0x180029f6a  jmp     loc_18002A0C7
0x180029f6f  movzx   eax, [rbp+57h+UniversalTime.wYear]
0x180029f73  movsd   xmm0, qword ptr [rbp+57h+UniversalTime.wMonth]
0x180029f78  mov     [rbp+57h+LocalTime.wYear], ax
0x180029f7c  mov     eax, dword ptr [rbp+57h+UniversalTime.wMinute]
0x180029f7f  mov     dword ptr [rbp+57h+LocalTime.wMinute], eax
0x180029f82  movzx   eax, [rbp+57h+UniversalTime.wMilliseconds]
0x180029f86  mov     [rbp+57h+LocalTime.wMilliseconds], ax
0x180029f8a  movsd   qword ptr [rbp+57h+LocalTime.wMonth], xmm0
0x180029f8f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180029f93  mov     rdi, [rbp+57h+var_80]
0x180029f97  test    rcx, rcx
0x180029f9a  jz      short loc_180029FC1
0x180029f9c  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180029fa0  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180029fa4  lea     rdx, aRandomized; "Randomized"
0x180029fab  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180029fb0  test    eax, eax
0x180029fb2  jz      short loc_180029FE5
0x180029fb4  cmp     eax, r12d
0x180029fb7  jnz     loc_18002A0AB
0x180029fbd  mov     rbx, [rbp+57h+var_90]
0x180029fc1  test    rdi, rdi
0x180029fc4  jz      short loc_18002A004
0x180029fc6  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180029fca  mov     rcx, rdi; KeyHandle
0x180029fcd  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180029fd1  lea     rdx, aRandomized; "Randomized"
0x180029fd8  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180029fdd  test    eax, eax
0x180029fdf  jnz     loc_18002A0AB
0x180029fe5  mov     rbx, [rbp+57h+var_90]
0x180029fe9  test    rbx, rbx
0x180029fec  jz      loc_18002A0B8
0x180029ff2  cmp     dword ptr [rbx+8], 4
0x180029ff6  jnz     loc_18002A0AF
0x180029ffc  cmp     dword ptr [rbx+0Ch], 0
0x18002a000  setnz   [rbp+57h+var_49]
0x18002a004  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002a008  mov     eax, r12d
0x18002a00b  mov     rdi, [rbp+57h+var_80]
0x18002a00f  test    rcx, rcx
0x18002a012  jz      short loc_18002A031
0x18002a014  lea     r9, [rbp+57h+var_84]; unsigned int *
0x18002a018  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x18002a01c  lea     rdx, aRandomDelay; "Random Delay"
0x18002a023  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x18002a028  mov     rbx, [rbp+57h+var_90]
0x18002a02c  cmp     eax, r12d
0x18002a02f  jnz     short loc_18002A051
0x18002a031  test    rdi, rdi
0x18002a034  jz      short loc_18002A051
0x18002a036  lea     r9, [rbp+57h+var_84]; unsigned int *
0x18002a03a  mov     rcx, rdi; KeyHandle
0x18002a03d  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x18002a041  lea     rdx, aRandomDelay; "Random Delay"
0x18002a048  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x18002a04d  mov     rbx, [rbp+57h+var_90]
0x18002a051  test    eax, eax
0x18002a053  jnz     short loc_18002A086
0x18002a055  test    rbx, rbx
0x18002a058  jz      loc_18002A107
0x18002a05e  cmp     [rbx+8], r12d
0x18002a062  jb      loc_18002A107
0x18002a068  mov     edx, [rbx+8]
0x18002a06b  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x18002a06f  sub     rdx, r12
0x18002a072  lea     r8, [rbp+57h+var_5E+6]; struct _UBPM_TIMESPAN *
0x18002a076  shr     rdx, 1; unsigned __int64
0x18002a079  call    ?UbpmUtilsParseTimeSpan@@YAKPEBG_KPEAU_UBPM_TIMESPAN@@@Z; UbpmUtilsParseTimeSpan(ushort const *,unsigned __int64,_UBPM_TIMESPAN *)
0x18002a07e  test    eax, eax
0x18002a080  jz      loc_18002A107
0x18002a086  cmp     eax, r12d
0x18002a089  jz      short loc_18002A107
0x18002a08b  lea     rax, aAutomaticMaint_1; "Automatic Maintenance Random Delay"
0x18002a092  jmp     short loc_18002A0A4
0x18002a094  cmp     eax, r12d
0x18002a097  jz      loc_180029F8F
0x18002a09d  lea     rax, aAutomaticMaint; "Automatic Maintenance Activation Bounda"...
0x18002a0a4  mov     edi, 57h ; 'W'
0x18002a0a9  jmp     short loc_18002A0C4
0x18002a0ab  mov     rbx, [rbp+57h+var_90]
0x18002a0af  cmp     eax, r12d
0x18002a0b2  jz      loc_18002A004
0x18002a0b8  mov     edi, 57h ; 'W'
0x18002a0bd  lea     rax, aInvalidRegistr; "Invalid registry keys"
0x18002a0c4  mov     [rsi], rax
0x18002a0c7  mov     rcx, rbx
0x18002a0ca  call    UBPM_MIDL_user_free
0x18002a0cf  mov     rcx, [rbp+57h+var_80]; void *
0x18002a0d3  call    ?UbpmUtilsRegCloseKey@@YAXPEAX@Z; UbpmUtilsRegCloseKey(void *)
0x18002a0d8  mov     rcx, [rbp+57h+KeyHandle]; void *
0x18002a0dc  call    ?UbpmUtilsRegCloseKey@@YAXPEAX@Z; UbpmUtilsRegCloseKey(void *)
0x18002a0e1  mov     eax, edi
0x18002a0e3  mov     rcx, [rbp+57h+var_30]
0x18002a0e7  xor     rcx, rsp; StackCookie
0x18002a0ea  call    __security_check_cookie
0x18002a0ef  mov     rbx, [rsp+0B0h+arg_10]
0x18002a0f7  add     rsp, 90h
0x18002a0fe  pop     r14
0x18002a100  pop     r12
0x18002a102  pop     rdi
0x18002a103  pop     rsi
0x18002a104  pop     rbp
0x18002a105  retn
0x18002a107  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002a10b  xor     eax, eax
0x18002a10d  mov     rdi, [rbp+57h+var_80]
0x18002a111  mov     dword ptr [rbp+57h+var_5E+6], eax
0x18002a114  mov     word ptr [rbp+57h+var_5E+0Ch], ax
0x18002a118  test    rcx, rcx
0x18002a11b  jz      short loc_18002A142
0x18002a11d  lea     r9, [rbp+57h+var_84]; unsigned int *
0x18002a121  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x18002a125  lea     rdx, aWakeup; "WakeUp"
0x18002a12c  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x18002a131  test    eax, eax
0x18002a133  jz      short loc_18002A166
0x18002a135  cmp     eax, r12d
0x18002a138  jnz     loc_18002A1EC
0x18002a13e  mov     rbx, [rbp+57h+var_90]
0x18002a142  test    rdi, rdi
0x18002a145  jz      short loc_18002A181
0x18002a147  lea     r9, [rbp+57h+var_84]; unsigned int *
0x18002a14b  mov     rcx, rdi; KeyHandle
0x18002a14e  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x18002a152  lea     rdx, aWakeup; "WakeUp"
0x18002a159  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x18002a15e  test    eax, eax
0x18002a160  jnz     loc_18002A1EC
0x18002a166  mov     rbx, [rbp+57h+var_90]
0x18002a16a  test    rbx, rbx
0x18002a16d  jz      loc_18002A1F5
0x18002a173  cmp     dword ptr [rbx+8], 4
0x18002a177  jnz     short loc_18002A1F0
0x18002a179  cmp     dword ptr [rbx+0Ch], 0
0x18002a17d  setnz   [rbp+57h+var_4A]
0x18002a181  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002a185  mov     rdi, [rbp+57h+var_80]
0x18002a189  test    rcx, rcx
0x18002a18c  jz      short loc_18002A1AF
0x18002a18e  lea     r9, [rbp+57h+var_84]; unsigned int *
0x18002a192  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x18002a196  lea     rdx, aMaintenancedis; "MaintenanceDisabled"
0x18002a19d  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x18002a1a2  test    eax, eax
0x18002a1a4  jz      short loc_18002A1CF
0x18002a1a6  cmp     eax, r12d
0x18002a1a9  jnz     short loc_18002A201
0x18002a1ab  mov     rbx, [rbp+57h+var_90]
0x18002a1af  test    rdi, rdi
0x18002a1b2  jz      short loc_18002A20E
0x18002a1b4  lea     r9, [rbp+57h+var_84]; unsigned int *
0x18002a1b8  mov     rcx, rdi; KeyHandle
0x18002a1bb  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x18002a1bf  lea     rdx, aMaintenancedis; "MaintenanceDisabled"
0x18002a1c6  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x18002a1cb  test    eax, eax
0x18002a1cd  jnz     short loc_18002A201
0x18002a1cf  mov     rbx, [rbp+57h+var_90]
0x18002a1d3  test    rbx, rbx
0x18002a1d6  jz      loc_18002A0B8
0x18002a1dc  cmp     dword ptr [rbx+8], 4
0x18002a1e0  jnz     short loc_18002A205
0x18002a1e2  cmp     dword ptr [rbx+0Ch], 0
0x18002a1e6  setnz   [rbp+57h+var_48]
0x18002a1ea  jmp     short loc_18002A20E
0x18002a1ec  mov     rbx, [rbp+57h+var_90]
0x18002a1f0  cmp     eax, r12d
0x18002a1f3  jz      short loc_18002A181
0x18002a1f5  lea     rax, aAutomaticMaint_0; "Automatic Maintenance WakeUp Policy"
0x18002a1fc  jmp     loc_18002A0A4
0x18002a201  mov     rbx, [rbp+57h+var_90]
0x18002a205  cmp     eax, r12d
0x18002a208  jnz     loc_18002A0B8
0x18002a20e  movups  xmm0, xmmword ptr [rbp+57h+LocalTime.wYear]
0x18002a212  mov     dword ptr [rbp+57h+var_5E+2], 1Eh
0x18002a219  xor     edi, edi
0x18002a21b  mov     dword ptr [rbp-9], 15180h
0x18002a222  movups  xmm1, xmmword ptr [rbp-9]
0x18002a226  movups  xmmword ptr [r14], xmm0
0x18002a22a  movups  xmm0, [rbp+57h+var_5E+0Ah]
0x18002a22e  movups  xmmword ptr [r14+10h], xmm1
0x18002a233  movups  xmmword ptr [r14+1Ch], xmm0
0x18002a238  jmp     loc_18002A0C7
```
