# UbpmpReadMaintenanceSettings(_UBPM_MAINTENANCE_PARAMETERS *,ushort const * *)

- ea: `0x180027eb4`
- end: `0x180028304`
- name: `?UbpmpReadMaintenanceSettings@@YAKPEAU_UBPM_MAINTENANCE_PARAMETERS@@PEAPEBG@Z`
- size: `1104`
- prototype: `unsigned int __fastcall(struct _UBPM_MAINTENANCE_PARAMETERS *, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002e220`
- `0x180036a90`

## callees

- `0x180019d90`
- `0x180027eb4`
- `0x18002830c`
- `0x180028424`
- `0x1800284b4`
- `0x1800284d0`
- `0x180028530`
- `0x180028808`
- `0x18003d810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002802a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002802a`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x180028020`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x180028020`

## string_xrefs

- `0x180027f5d`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Schedule\Maintenance`
- `0x180027f1f`: `\Registry\Machine\Software\Policies\Microsoft\Windows\Task Scheduler\Maintenance`
- `0x180028185`: `Invalid registry keys`

## pseudocode

```c
__int64 __fastcall UbpmpReadMaintenanceSettings(struct _UBPM_MAINTENANCE_PARAMETERS *a1, const unsigned __int16 **a2)
{
  struct _KEY_VALUE_PARTIAL_INFORMATION *v3; // rbx
  ULONG v5; // eax
  ULONG LastError; // edi
  HANDLE v7; // rdi
  unsigned int Value; // eax
  HANDLE v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // eax
  HANDLE v12; // rdi
  const unsigned __int16 *v13; // rax
  HANDLE v15; // rdi
  unsigned int v16; // eax
  HANDLE v17; // rdi
  unsigned int v18; // eax
  SYSTEMTIME v19; // xmm1
  __int128 v20; // xmm0
  struct _KEY_VALUE_PARTIAL_INFORMATION *v21; // [rsp+20h] [rbp-39h] BYREF
  unsigned __int8 v22[4]; // [rsp+28h] [rbp-31h] BYREF
  unsigned int v23; // [rsp+2Ch] [rbp-2Dh] BYREF
  HANDLE v24; // [rsp+30h] [rbp-29h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  SYSTEMTIME LocalTime[3]; // [rsp+40h] [rbp-19h] BYREF
  struct _SYSTEMTIME UniversalTime; // [rsp+70h] [rbp+17h] BYREF

  memset(LocalTime, 0, 44);
  v3 = 0;
  KeyHandle = 0;
  v24 = 0;
  v21 = 0;
  v23 = 0;
  UniversalTime = 0;
  v22[0] = 0;
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
                &v24);
  if ( LastError - 4 <= 0x48B || LastError == 1 || LastError >= 0x491 )
    goto LABEL_44;
  v7 = v24;
  Value = 2;
  if ( !KeyHandle
    || (Value = UbpmpUtilsRegGetValue(KeyHandle, L"Activation Boundary", &v21, &v23), v3 = v21, Value == 2) )
  {
    if ( v7 )
    {
      Value = UbpmpUtilsRegGetValue(v7, L"Activation Boundary", &v21, &v23);
      v3 = v21;
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
            v22);
  if ( Value )
  {
LABEL_38:
    if ( Value != 2 )
    {
      v13 = L"Automatic Maintenance Activation Boundary";
      goto LABEL_40;
    }
LABEL_19:
    v9 = v24;
    if ( KeyHandle )
    {
      v10 = UbpmpUtilsRegGetValue(KeyHandle, L"Randomized", &v21, &v23);
      if ( !v10 )
        goto LABEL_25;
      if ( v10 != 2 )
      {
LABEL_41:
        v3 = v21;
        goto LABEL_42;
      }
      v3 = v21;
    }
    if ( !v9 )
      goto LABEL_28;
    v10 = UbpmpUtilsRegGetValue(v9, L"Randomized", &v21, &v23);
    if ( !v10 )
    {
LABEL_25:
      v3 = v21;
      if ( !v21 )
        goto LABEL_43;
      if ( v21->DataLength == 4 )
      {
        HIBYTE(LocalTime[2].wDay) = *(_DWORD *)v21->Data != 0;
        goto LABEL_28;
      }
LABEL_42:
      if ( v10 != 2 )
        goto LABEL_43;
LABEL_28:
      v11 = 2;
      v12 = v24;
      if ( !KeyHandle || (v11 = UbpmpUtilsRegGetValue(KeyHandle, L"Random Delay", &v21, &v23), v3 = v21, v11 == 2) )
      {
        if ( v12 )
        {
          v11 = UbpmpUtilsRegGetValue(v12, L"Random Delay", &v21, &v23);
          v3 = v21;
        }
      }
      if ( (v11
         || v3
         && v3->DataLength >= 2
         && (v11 = UbpmUtilsParseTimeSpan(
                     (const unsigned __int16 *)v3->Data,
                     ((unsigned __int64)v3->DataLength - 2) >> 1,
                     (struct _UBPM_TIMESPAN *)&LocalTime[1].wHour)) != 0)
        && v11 != 2 )
      {
        v13 = L"Automatic Maintenance Random Delay";
LABEL_40:
        LastError = 87;
LABEL_45:
        *a2 = v13;
        goto LABEL_46;
      }
      v15 = v24;
      *(_DWORD *)&LocalTime[1].wHour = 0;
      LocalTime[1].wMilliseconds = 0;
      if ( KeyHandle )
      {
        v16 = UbpmpUtilsRegGetValue(KeyHandle, L"WakeUp", &v21, &v23);
        if ( !v16 )
        {
LABEL_53:
          v3 = v21;
          if ( !v21 )
            goto LABEL_67;
          if ( v21->DataLength == 4 )
          {
            LOBYTE(LocalTime[2].wDay) = *(_DWORD *)v21->Data != 0;
            goto LABEL_56;
          }
LABEL_66:
          if ( v16 == 2 )
          {
LABEL_56:
            v17 = v24;
            if ( KeyHandle )
            {
              v18 = UbpmpUtilsRegGetValue(KeyHandle, L"MaintenanceDisabled", &v21, &v23);
              if ( !v18 )
                goto LABEL_62;
              if ( v18 != 2 )
              {
LABEL_68:
                v3 = v21;
LABEL_69:
                if ( v18 == 2 )
                  goto LABEL_70;
                goto LABEL_43;
              }
              v3 = v21;
            }
            if ( !v17 )
            {
LABEL_70:
              LastError = 0;
              *(_QWORD *)&LocalTime[1].wYear = 0x1E00015180LL;
              v19 = LocalTime[1];
              *(SYSTEMTIME *)a1 = LocalTime[0];
              v20 = *(_OWORD *)&LocalTime[1].wSecond;
              *((SYSTEMTIME *)a1 + 1) = v19;
              *(_OWORD *)((char *)a1 + 28) = v20;
              goto LABEL_46;
            }
            v18 = UbpmpUtilsRegGetValue(v17, L"MaintenanceDisabled", &v21, &v23);
            if ( !v18 )
            {
LABEL_62:
              v3 = v21;
              if ( v21 )
              {
                if ( v21->DataLength == 4 )
                {
                  LOBYTE(LocalTime[2].wHour) = *(_DWORD *)v21->Data != 0;
                  goto LABEL_70;
                }
                goto LABEL_69;
              }
LABEL_43:
              LastError = 87;
LABEL_44:
              v13 = L"Invalid registry keys";
              goto LABEL_45;
            }
            goto LABEL_68;
          }
LABEL_67:
          v13 = L"Automatic Maintenance WakeUp Policy";
          goto LABEL_40;
        }
        if ( v16 != 2 )
        {
LABEL_65:
          v3 = v21;
          goto LABEL_66;
        }
        v3 = v21;
      }
      if ( !v15 )
        goto LABEL_56;
      v16 = UbpmpUtilsRegGetValue(v15, L"WakeUp", &v21, &v23);
      if ( !v16 )
        goto LABEL_53;
      goto LABEL_65;
    }
    goto LABEL_41;
  }
  if ( v22[0] )
    goto LABEL_19;
  if ( TzSpecificLocalTimeToSystemTime(0, LocalTime, &UniversalTime) )
  {
    LocalTime[0] = UniversalTime;
    goto LABEL_19;
  }
  LastError = GetLastError();
LABEL_46:
  UBPM_MIDL_user_free(v3);
  UbpmUtilsRegCloseKey(v24);
  UbpmUtilsRegCloseKey(KeyHandle);
  return LastError;
}

```

## disassembly

```asm
0x180027eb4  mov     [rsp-8+arg_10], rbx
0x180027eb9  push    rbp
0x180027eba  push    rsi
0x180027ebb  push    rdi
0x180027ebc  push    r12
0x180027ebe  push    r14
0x180027ec0  lea     rbp, [rsp-37h]
0x180027ec5  sub     rsp, 90h
0x180027ecc  mov     rax, cs:__security_cookie
0x180027ed3  xor     rax, rsp
0x180027ed6  mov     [rbp+57h+var_30], rax
0x180027eda  xor     eax, eax
0x180027edc  xorps   xmm0, xmm0
0x180027edf  mov     r14, rcx
0x180027ee2  mov     [rbp+57h+LocalTime.wYear], ax
0x180027ee6  movups  [rbp+57h+var_5E], xmm0
0x180027eea  xor     ebx, ebx
0x180027eec  mov     [rbp+57h+KeyHandle], rax
0x180027ef0  lea     rcx, [rbp+57h+LocalTime]; struct _SYSTEMTIME *
0x180027ef4  mov     [rbp+57h+var_80], rax
0x180027ef8  movups  [rbp+57h+var_5E+0Ah], xmm0
0x180027efc  mov     rsi, rdx
0x180027eff  mov     [rbp+57h+var_90], rbx
0x180027f03  movups  xmmword ptr [rbp+57h+LocalTime.wMonth], xmm0
0x180027f07  mov     [rbp+57h+var_84], eax
0x180027f0a  movups  xmmword ptr [rbp+57h+UniversalTime.wYear], xmm0
0x180027f0e  mov     [rbp+57h+var_88], al
0x180027f11  call    ?UbpmpInitializeMaintenanceParameters@@YAXPEAU_UBPM_MAINTENANCE_PARAMETERS@@@Z; UbpmpInitializeMaintenanceParameters(_UBPM_MAINTENANCE_PARAMETERS *)
0x180027f16  lea     r8, [rbp+57h+KeyHandle]; KeyHandle
0x180027f1a  mov     edx, 20019h; DesiredAccess
0x180027f1f  lea     rcx, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Policies"...
0x180027f26  call    ?UbpmUtilsRegOpenKey@@YAKPEBGKPEAPEAX@Z; UbpmUtilsRegOpenKey(ushort const *,ulong,void * *)
0x180027f2b  mov     edi, eax
0x180027f2d  lea     ecx, [rax-4]
0x180027f30  cmp     ecx, 48Bh
0x180027f36  jbe     loc_180028185
0x180027f3c  cmp     eax, 1
0x180027f3f  jz      loc_180028185
0x180027f45  mov     r12d, 491h
0x180027f4b  cmp     eax, r12d
0x180027f4e  jnb     loc_180028185
0x180027f54  lea     r8, [rbp+57h+var_80]; KeyHandle
0x180027f58  mov     edx, 20019h; DesiredAccess
0x180027f5d  lea     rcx, aRegistryMachin; "\\Registry\\Machine\\Software\\Microsof"...
0x180027f64  call    ?UbpmUtilsRegOpenKey@@YAKPEBGKPEAPEAX@Z; UbpmUtilsRegOpenKey(ushort const *,ulong,void * *)
0x180027f69  mov     edi, eax
0x180027f6b  add     eax, 0FFFFFFFCh
0x180027f6e  cmp     eax, 48Bh
0x180027f73  jbe     loc_180028185
0x180027f79  cmp     edi, 1
0x180027f7c  jz      loc_180028185
0x180027f82  cmp     edi, r12d
0x180027f85  jnb     loc_180028185
0x180027f8b  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180027f8f  lea     r12d, [rbx+2]
0x180027f93  mov     rdi, [rbp+57h+var_80]
0x180027f97  mov     eax, r12d
0x180027f9a  test    rcx, rcx
0x180027f9d  jz      short loc_180027FBC
0x180027f9f  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180027fa3  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180027fa7  lea     rdx, aActivationBoun; "Activation Boundary"
0x180027fae  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180027fb3  mov     rbx, [rbp+57h+var_90]
0x180027fb7  cmp     eax, r12d
0x180027fba  jnz     short loc_180027FDC
0x180027fbc  test    rdi, rdi
0x180027fbf  jz      short loc_180027FDC
0x180027fc1  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180027fc5  mov     rcx, rdi; KeyHandle
0x180027fc8  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180027fcc  lea     rdx, aActivationBoun; "Activation Boundary"
0x180027fd3  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180027fd8  mov     rbx, [rbp+57h+var_90]
0x180027fdc  test    eax, eax
0x180027fde  jnz     loc_18002815C
0x180027fe4  test    rbx, rbx
0x180027fe7  jz      short loc_180028057
0x180027fe9  cmp     [rbx+8], r12d
0x180027fed  jbe     short loc_180028057
0x180027fef  mov     edx, [rbx+8]
0x180027ff2  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x180027ff6  sub     rdx, r12
0x180027ff9  lea     r9, [rbp+57h+var_88]; unsigned __int8 *
0x180027ffd  shr     rdx, 1; unsigned __int64
0x180028000  lea     r8, [rbp+57h+LocalTime]; struct _SYSTEMTIME *
0x180028004  call    ?UbpmUtilsParseDateTime@@YAKPEBG_KPEAU_SYSTEMTIME@@PEAE@Z; UbpmUtilsParseDateTime(ushort const *,unsigned __int64,_SYSTEMTIME *,uchar *)
0x180028009  test    eax, eax
0x18002800b  jnz     loc_18002815C
0x180028011  cmp     [rbp+57h+var_88], al
0x180028014  jnz     short loc_180028057
0x180028016  lea     r8, [rbp+57h+UniversalTime]; lpUniversalTime
0x18002801a  xor     ecx, ecx; lpTimeZoneInformation
0x18002801c  lea     rdx, [rbp+57h+LocalTime]; lpLocalTime
0x180028020  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x180028026  test    eax, eax
0x180028028  jnz     short loc_180028037
0x18002802a  call    cs:__imp_GetLastError
0x180028030  mov     edi, eax
0x180028032  jmp     loc_18002818F
0x180028037  movzx   eax, [rbp+57h+UniversalTime.wYear]
0x18002803b  movsd   xmm0, qword ptr [rbp+57h+UniversalTime.wMonth]
0x180028040  mov     [rbp+57h+LocalTime.wYear], ax
0x180028044  mov     eax, dword ptr [rbp+57h+UniversalTime.wMinute]
0x180028047  mov     dword ptr [rbp+57h+LocalTime.wMinute], eax
0x18002804a  movzx   eax, [rbp+57h+UniversalTime.wMilliseconds]
0x18002804e  mov     [rbp+57h+LocalTime.wMilliseconds], ax
0x180028052  movsd   qword ptr [rbp+57h+LocalTime.wMonth], xmm0
0x180028057  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002805b  mov     rdi, [rbp+57h+var_80]
0x18002805f  test    rcx, rcx
0x180028062  jz      short loc_180028089
0x180028064  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180028068  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x18002806c  lea     rdx, aRandomized; "Randomized"
0x180028073  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180028078  test    eax, eax
0x18002807a  jz      short loc_1800280AD
0x18002807c  cmp     eax, r12d
0x18002807f  jnz     loc_180028173
0x180028085  mov     rbx, [rbp+57h+var_90]
0x180028089  test    rdi, rdi
0x18002808c  jz      short loc_1800280CC
0x18002808e  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180028092  mov     rcx, rdi; KeyHandle
0x180028095  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180028099  lea     rdx, aRandomized; "Randomized"
0x1800280a0  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x1800280a5  test    eax, eax
0x1800280a7  jnz     loc_180028173
0x1800280ad  mov     rbx, [rbp+57h+var_90]
0x1800280b1  test    rbx, rbx
0x1800280b4  jz      loc_180028180
0x1800280ba  cmp     dword ptr [rbx+8], 4
0x1800280be  jnz     loc_180028177
0x1800280c4  cmp     dword ptr [rbx+0Ch], 0
0x1800280c8  setnz   [rbp+57h+var_49]
0x1800280cc  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800280d0  mov     eax, r12d
0x1800280d3  mov     rdi, [rbp+57h+var_80]
0x1800280d7  test    rcx, rcx
0x1800280da  jz      short loc_1800280F9
0x1800280dc  lea     r9, [rbp+57h+var_84]; unsigned int *
0x1800280e0  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x1800280e4  lea     rdx, aRandomDelay; "Random Delay"
0x1800280eb  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x1800280f0  mov     rbx, [rbp+57h+var_90]
0x1800280f4  cmp     eax, r12d
0x1800280f7  jnz     short loc_180028119
0x1800280f9  test    rdi, rdi
0x1800280fc  jz      short loc_180028119
0x1800280fe  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180028102  mov     rcx, rdi; KeyHandle
0x180028105  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180028109  lea     rdx, aRandomDelay; "Random Delay"
0x180028110  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180028115  mov     rbx, [rbp+57h+var_90]
0x180028119  test    eax, eax
0x18002811b  jnz     short loc_18002814E
0x18002811d  test    rbx, rbx
0x180028120  jz      loc_1800281CE
0x180028126  cmp     [rbx+8], r12d
0x18002812a  jb      loc_1800281CE
0x180028130  mov     edx, [rbx+8]
0x180028133  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x180028137  sub     rdx, r12
0x18002813a  lea     r8, [rbp+57h+var_5E+6]; struct _UBPM_TIMESPAN *
0x18002813e  shr     rdx, 1; unsigned __int64
0x180028141  call    ?UbpmUtilsParseTimeSpan@@YAKPEBG_KPEAU_UBPM_TIMESPAN@@@Z; UbpmUtilsParseTimeSpan(ushort const *,unsigned __int64,_UBPM_TIMESPAN *)
0x180028146  test    eax, eax
0x180028148  jz      loc_1800281CE
0x18002814e  cmp     eax, r12d
0x180028151  jz      short loc_1800281CE
0x180028153  lea     rax, aAutomaticMaint_1; "Automatic Maintenance Random Delay"
0x18002815a  jmp     short loc_18002816C
0x18002815c  cmp     eax, r12d
0x18002815f  jz      loc_180028057
0x180028165  lea     rax, aAutomaticMaint; "Automatic Maintenance Activation Bounda"...
0x18002816c  mov     edi, 57h ; 'W'
0x180028171  jmp     short loc_18002818C
0x180028173  mov     rbx, [rbp+57h+var_90]
0x180028177  cmp     eax, r12d
0x18002817a  jz      loc_1800280CC
0x180028180  mov     edi, 57h ; 'W'
0x180028185  lea     rax, aInvalidRegistr; "Invalid registry keys"
0x18002818c  mov     [rsi], rax
0x18002818f  mov     rcx, rbx
0x180028192  call    UBPM_MIDL_user_free
0x180028197  mov     rcx, [rbp+57h+var_80]; void *
0x18002819b  call    ?UbpmUtilsRegCloseKey@@YAXPEAX@Z; UbpmUtilsRegCloseKey(void *)
0x1800281a0  mov     rcx, [rbp+57h+KeyHandle]; void *
0x1800281a4  call    ?UbpmUtilsRegCloseKey@@YAXPEAX@Z; UbpmUtilsRegCloseKey(void *)
0x1800281a9  mov     eax, edi
0x1800281ab  mov     rcx, [rbp+57h+var_30]
0x1800281af  xor     rcx, rsp; StackCookie
0x1800281b2  call    __security_check_cookie
0x1800281b7  mov     rbx, [rsp+0B0h+arg_10]
0x1800281bf  add     rsp, 90h
0x1800281c6  pop     r14
0x1800281c8  pop     r12
0x1800281ca  pop     rdi
0x1800281cb  pop     rsi
0x1800281cc  pop     rbp
0x1800281cd  retn
0x1800281ce  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800281d2  xor     eax, eax
0x1800281d4  mov     rdi, [rbp+57h+var_80]
0x1800281d8  mov     dword ptr [rbp+57h+var_5E+6], eax
0x1800281db  mov     word ptr [rbp+57h+var_5E+0Ch], ax
0x1800281df  test    rcx, rcx
0x1800281e2  jz      short loc_180028209
0x1800281e4  lea     r9, [rbp+57h+var_84]; unsigned int *
0x1800281e8  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x1800281ec  lea     rdx, aWakeup; "WakeUp"
0x1800281f3  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x1800281f8  test    eax, eax
0x1800281fa  jz      short loc_18002822D
0x1800281fc  cmp     eax, r12d
0x1800281ff  jnz     loc_1800282B3
0x180028205  mov     rbx, [rbp+57h+var_90]
0x180028209  test    rdi, rdi
0x18002820c  jz      short loc_180028248
0x18002820e  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180028212  mov     rcx, rdi; KeyHandle
0x180028215  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180028219  lea     rdx, aWakeup; "WakeUp"
0x180028220  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180028225  test    eax, eax
0x180028227  jnz     loc_1800282B3
0x18002822d  mov     rbx, [rbp+57h+var_90]
0x180028231  test    rbx, rbx
0x180028234  jz      loc_1800282BC
0x18002823a  cmp     dword ptr [rbx+8], 4
0x18002823e  jnz     short loc_1800282B7
0x180028240  cmp     dword ptr [rbx+0Ch], 0
0x180028244  setnz   [rbp+57h+var_4A]
0x180028248  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002824c  mov     rdi, [rbp+57h+var_80]
0x180028250  test    rcx, rcx
0x180028253  jz      short loc_180028276
0x180028255  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180028259  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x18002825d  lea     rdx, aMaintenancedis; "MaintenanceDisabled"
0x180028264  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180028269  test    eax, eax
0x18002826b  jz      short loc_180028296
0x18002826d  cmp     eax, r12d
0x180028270  jnz     short loc_1800282C8
0x180028272  mov     rbx, [rbp+57h+var_90]
0x180028276  test    rdi, rdi
0x180028279  jz      short loc_1800282D5
0x18002827b  lea     r9, [rbp+57h+var_84]; unsigned int *
0x18002827f  mov     rcx, rdi; KeyHandle
0x180028282  lea     r8, [rbp+57h+var_90]; struct _KEY_VALUE_PARTIAL_INFORMATION **
0x180028286  lea     rdx, aMaintenancedis; "MaintenanceDisabled"
0x18002828d  call    ?UbpmpUtilsRegGetValue@@YAKPEAXPEBGAEAPEAU_KEY_VALUE_PARTIAL_INFORMATION@@AEAK@Z; UbpmpUtilsRegGetValue(void *,ushort const *,_KEY_VALUE_PARTIAL_INFORMATION * &,ulong &)
0x180028292  test    eax, eax
0x180028294  jnz     short loc_1800282C8
0x180028296  mov     rbx, [rbp+57h+var_90]
0x18002829a  test    rbx, rbx
0x18002829d  jz      loc_180028180
0x1800282a3  cmp     dword ptr [rbx+8], 4
0x1800282a7  jnz     short loc_1800282CC
0x1800282a9  cmp     dword ptr [rbx+0Ch], 0
0x1800282ad  setnz   [rbp+57h+var_48]
0x1800282b1  jmp     short loc_1800282D5
0x1800282b3  mov     rbx, [rbp+57h+var_90]
0x1800282b7  cmp     eax, r12d
0x1800282ba  jz      short loc_180028248
0x1800282bc  lea     rax, aAutomaticMaint_0; "Automatic Maintenance WakeUp Policy"
0x1800282c3  jmp     loc_18002816C
0x1800282c8  mov     rbx, [rbp+57h+var_90]
0x1800282cc  cmp     eax, r12d
0x1800282cf  jnz     loc_180028180
0x1800282d5  movups  xmm0, xmmword ptr [rbp+57h+LocalTime.wYear]
0x1800282d9  mov     dword ptr [rbp+57h+var_5E+2], 1Eh
0x1800282e0  xor     edi, edi
0x1800282e2  mov     dword ptr [rbp-9], 15180h
0x1800282e9  movups  xmm1, xmmword ptr [rbp-9]
0x1800282ed  movups  xmmword ptr [r14], xmm0
0x1800282f1  movups  xmm0, [rbp+57h+var_5E+0Ah]
0x1800282f5  movups  xmmword ptr [r14+10h], xmm1
0x1800282fa  movups  xmmword ptr [r14+1Ch], xmm0
0x1800282ff  jmp     loc_18002818F
```
