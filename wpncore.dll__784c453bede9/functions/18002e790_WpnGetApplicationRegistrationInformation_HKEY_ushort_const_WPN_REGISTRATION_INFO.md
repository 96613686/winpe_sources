# WpnGetApplicationRegistrationInformation(HKEY__ *,ushort const *,WPN_REGISTRATION_INFO *)

- ea: `0x18002e790`
- end: `0x18002ee30`
- name: `?WpnGetApplicationRegistrationInformation@@YAJPEAUHKEY__@@PEBGPEAUWPN_REGISTRATION_INFO@@@Z`
- size: `1696`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, struct WPN_REGISTRATION_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002db0c`

## callees

- `0x18002e790`
- `0x18002ee38`
- `0x1800a0b2c`
- `0x1800af0a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e7f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e7f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e8ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e941`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e9a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ea08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ea81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e8ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e941`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e9a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ea08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ea81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e894`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e894`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002eac4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002eb07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002eac4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002eb07`

## string_xrefs

- `0x18002e860`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18002eb28`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18002ebc9`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18002ec2f`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18002ec80`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18002ed00`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18002ed4d`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18002eda4`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
__int64 __fastcall WpnGetApplicationRegistrationInformation(HKEY hKey, LPCWSTR lpSubKey, BYTE *a3)
{
  LSTATUS v6; // eax
  signed int v7; // edi
  __int64 v8; // rax
  __int64 v9; // rdx
  BYTE *v10; // r8
  BYTE *v11; // rcx
  _QWORD *v12; // rcx
  LSTATUS v14; // eax
  __int64 v15; // rcx
  _DWORD *v16; // rbx
  LSTATUS v17; // eax
  __int64 v18; // rcx
  HKEY v19; // rcx
  LSTATUS v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  LSTATUS v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  LSTATUS v27; // eax
  __int64 v28; // rcx
  LSTATUS ValueW; // eax
  __int64 v30; // rdx
  int v31; // ecx
  int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  int phkResultb; // [rsp+20h] [rbp-30h]
  int phkResultc; // [rsp+20h] [rbp-30h]
  int phkResultd; // [rsp+20h] [rbp-30h]
  int phkResulte; // [rsp+20h] [rbp-30h]
  int phkResultf; // [rsp+20h] [rbp-30h]
  int pvData; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD Type; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF
  int Data; // [rsp+90h] [rbp+40h] BYREF
  int v45; // [rsp+98h] [rbp+48h] BYREF

  if ( !hKey )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  if ( !lpSubKey )
    MicrosoftTelemetryAssertTriggeredNoArgs(hKey);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(hKey);
  Data = 0x10000000;
  hKeya = 0;
  Type = 0;
  cbData = 0;
  v45 = 0;
  v6 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x301,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v7,
      phkResult);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_18;
    v30 = 29;
    goto LABEL_57;
  }
  v8 = 2147483646;
  v9 = 130;
  v10 = a3;
  do
  {
    if ( !v8 )
      break;
    if ( !*lpSubKey )
      break;
    *(_WORD *)v10 = *lpSubKey++;
    v10 += 2;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v10 - 2;
  v7 = -2147024774;
  if ( v9 )
  {
    v11 = v10;
    v7 = 0;
  }
  *(_WORD *)v11 = 0;
  if ( !v9 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x30B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v7,
      phkResult);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v30 = 30;
      goto LABEL_57;
    }
    goto LABEL_18;
  }
  Type = 1;
  cbData = 256;
  v14 = RegQueryValueExW(hKeya, L"PackageMoniker", 0, &Type, a3 + 260, &cbData);
  v7 = v14;
  if ( v14 > 0 )
    v7 = (unsigned __int16)v14 | 0x80070000;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x31B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v7,
      phkResulta);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v30 = 31;
      goto LABEL_57;
    }
    goto LABEL_18;
  }
  if ( Type != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v15);
  v16 = a3 + 516;
  Type = 4;
  cbData = 4;
  v17 = RegQueryValueExW(hKeya, L"Capabilities", 0, &Type, a3 + 516, &cbData);
  v7 = v17;
  if ( v17 > 0 )
    v7 = (unsigned __int16)v17 | 0x80070000;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x32C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v7,
      phkResultb);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v30 = 32;
      goto LABEL_57;
    }
    goto LABEL_18;
  }
  if ( Type != 4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v18);
  if ( !*v16 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v18);
  v19 = hKeya;
  *v16 |= 0xB0004Fu;
  Type = 4;
  cbData = 4;
  v20 = RegQueryValueExW(v19, L"ApplicationType", 0, &Type, (LPBYTE)&Data, &cbData);
  v7 = v20;
  if ( v20 > 0 )
    v7 = (unsigned __int16)v20 | 0x80070000;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x340,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v7,
      phkResultc);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v30 = 33;
      goto LABEL_57;
    }
    goto LABEL_18;
  }
  if ( Type != 4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v21);
  v22 = Data;
  if ( Data != 0x10000000 && Data != 0x40000000 && Data != 0x80000000 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v21);
    v22 = Data;
  }
  *v16 |= v22;
  Type = 4;
  cbData = 4;
  v23 = RegQueryValueExW(hKeya, L"RegistrationType", 0, &Type, (LPBYTE)&v45, &cbData);
  if ( v23 != 2 )
  {
    if ( v23 > 0 )
      v7 = (unsigned __int16)v23 | 0x80070000;
    else
      v7 = v23;
    if ( v7 >= 0 )
    {
      if ( Type != 4 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v24);
      v25 = v45;
      if ( v45 )
      {
        if ( v45 == 1 )
          goto LABEL_60;
        MicrosoftTelemetryAssertTriggeredNoArgs(v24);
        v25 = v45;
      }
      if ( v25 != 1 )
      {
        v26 = 0;
LABEL_48:
        *((_DWORD *)a3 + 132) |= v26;
        goto LABEL_49;
      }
LABEL_60:
      v26 = 2;
      goto LABEL_48;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x358,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v7,
      phkResultd);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_18;
    v30 = 34;
LABEL_57:
    WPP_SF_d(v12[2], v30, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids, (unsigned int)v7);
    goto LABEL_18;
  }
LABEL_49:
  Type = 3;
  cbData = 8;
  v27 = RegQueryValueExW(hKeya, L"WNF-Event", 0, &Type, a3 + 520, &cbData);
  if ( v27 == 2 )
    goto LABEL_50;
  if ( v27 > 0 )
    v7 = (unsigned __int16)v27 | 0x80070000;
  else
    v7 = v27;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x370,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v7,
      phkResulte);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_18;
    v30 = 35;
    goto LABEL_57;
  }
  if ( Type != 3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v28);
  *((_DWORD *)a3 + 132) |= 1u;
LABEL_50:
  cbData = 4096;
  if ( RegGetValueW(hKeya, 0, L"Uri", 2u, 0, a3 + 532, &cbData) )
    goto LABEL_18;
  pvData = 0;
  cbData = 4;
  ValueW = RegGetValueW(hKeya, 0, L"Recurrence", 0x10u, 0, &pvData, &cbData);
  v7 = ValueW;
  if ( ValueW > 0 )
    v7 = (unsigned __int16)ValueW | 0x80070000;
  if ( v7 >= 0 )
  {
    v31 = pvData;
    *((_DWORD *)a3 + 132) |= 4u;
    *((_DWORD *)a3 + 1157) = v31;
    goto LABEL_18;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x389,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
    (const char *)(unsigned int)v7,
    phkResultf);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v30 = 36;
    goto LABEL_57;
  }
LABEL_18:
  if ( hKeya )
    RegCloseKey(hKeya);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002e790  push    rbp
0x18002e792  push    rbx
0x18002e793  push    rsi
0x18002e794  push    rdi
0x18002e795  push    r14
0x18002e797  mov     rbp, rsp
0x18002e79a  sub     rsp, 50h
0x18002e79e  mov     rsi, r8
0x18002e7a1  mov     rbx, rdx
0x18002e7a4  mov     rdi, rcx
0x18002e7a7  test    rcx, rcx
0x18002e7aa  jz      loc_18002ECCA
0x18002e7b0  test    rbx, rbx
0x18002e7b3  jz      loc_18002ECD4
0x18002e7b9  test    rsi, rsi
0x18002e7bc  jz      loc_18002ECDE
0x18002e7c2  xor     r14d, r14d
0x18002e7c5  mov     [rbp+Data], 10000000h
0x18002e7cc  lea     rax, [rbp+hKey]
0x18002e7d0  mov     [rbp+hKey], r14
0x18002e7d4  mov     r9d, 20019h; samDesired
0x18002e7da  mov     [rbp+Type], r14d
0x18002e7de  xor     r8d, r8d; ulOptions
0x18002e7e1  mov     [rbp+cbData], r14d
0x18002e7e5  mov     rdx, rbx; lpSubKey
0x18002e7e8  mov     [rbp+arg_18], r14d
0x18002e7ec  mov     rcx, rdi; hKey
0x18002e7ef  mov     [rsp+50h+phkResult], rax; int
0x18002e7f4  call    cs:__imp_RegOpenKeyExW
0x18002e7fa  mov     edi, eax
0x18002e7fc  test    eax, eax
0x18002e7fe  jg      loc_18002E8A7
0x18002e804  test    edi, edi
0x18002e806  js      loc_18002EBC5
0x18002e80c  mov     eax, 7FFFFFFEh
0x18002e811  mov     edx, 82h
0x18002e816  mov     r8, rsi
0x18002e819  nop     dword ptr [rax+00000000h]
0x18002e820  test    rax, rax
0x18002e823  jz      short loc_18002E842
0x18002e825  movzx   ecx, word ptr [rbx]
0x18002e828  test    cx, cx
0x18002e82b  jz      short loc_18002E842
0x18002e82d  mov     [r8], cx
0x18002e831  add     rbx, 2
0x18002e835  add     r8, 2
0x18002e839  dec     rax
0x18002e83c  sub     rdx, 1
0x18002e840  jnz     short loc_18002E820
0x18002e842  test    rdx, rdx
0x18002e845  lea     rcx, [r8-2]
0x18002e849  mov     edi, 8007007Ah
0x18002e84e  cmovnz  rcx, r8
0x18002e852  cmovnz  edi, r14d
0x18002e856  mov     [rcx], r14w
0x18002e85a  jnz     short loc_18002E8B5
0x18002e85c  mov     rcx, [rbp+28h]; this
0x18002e860  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e867  mov     r9d, edi; char *
0x18002e86a  mov     edx, 30Bh; void *
0x18002e86f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e874  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e87b  lea     rax, WPP_GLOBAL_Control
0x18002e882  cmp     rcx, rax
0x18002e885  jnz     loc_18002ECE8
0x18002e88b  mov     rcx, [rbp+hKey]; hKey
0x18002e88f  test    rcx, rcx
0x18002e892  jz      short loc_18002E89A
0x18002e894  call    cs:__imp_RegCloseKey
0x18002e89a  mov     eax, edi
0x18002e89c  add     rsp, 50h
0x18002e8a0  pop     r14
0x18002e8a2  pop     rdi
0x18002e8a3  pop     rsi
0x18002e8a4  pop     rbx
0x18002e8a5  pop     rbp
0x18002e8a6  retn
0x18002e8a7  movzx   edi, ax
0x18002e8aa  or      edi, 80070000h
0x18002e8b0  jmp     loc_18002E804
0x18002e8b5  lea     rcx, [rbp+cbData]
0x18002e8b9  mov     [rbp+Type], 1
0x18002e8c0  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18002e8c5  lea     rax, [rsi+104h]
0x18002e8cc  mov     rcx, [rbp+hKey]; hKey
0x18002e8d0  lea     r9, [rbp+Type]; lpType
0x18002e8d4  xor     r8d, r8d; lpReserved
0x18002e8d7  mov     [rbp+cbData], 100h
0x18002e8de  lea     rdx, aPackagemoniker; "PackageMoniker"
0x18002e8e5  mov     [rsp+50h+phkResult], rax; int
0x18002e8ea  call    cs:__imp_RegQueryValueExW
0x18002e8f0  mov     edi, eax
0x18002e8f2  test    eax, eax
0x18002e8f4  jg      loc_18002EB7A
0x18002e8fa  test    edi, edi
0x18002e8fc  js      loc_18002ECFC
0x18002e902  cmp     [rbp+Type], 1
0x18002e906  jnz     loc_18002ED3F
0x18002e90c  mov     rcx, [rbp+hKey]; hKey
0x18002e910  lea     rax, [rbp+cbData]
0x18002e914  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002e919  lea     rbx, [rsi+204h]
0x18002e920  lea     r9, [rbp+Type]; lpType
0x18002e924  mov     [rsp+50h+phkResult], rbx; int
0x18002e929  xor     r8d, r8d; lpReserved
0x18002e92c  mov     [rbp+Type], 4
0x18002e933  lea     rdx, aCapabilities; "Capabilities"
0x18002e93a  mov     [rbp+cbData], 4
0x18002e941  call    cs:__imp_RegQueryValueExW
0x18002e947  mov     edi, eax
0x18002e949  test    eax, eax
0x18002e94b  jg      loc_18002EB88
0x18002e951  test    edi, edi
0x18002e953  js      loc_18002ED49
0x18002e959  cmp     [rbp+Type], 4
0x18002e95d  jnz     loc_18002ED8C
0x18002e963  cmp     [rbx], r14d
0x18002e966  jz      loc_18002ED96
0x18002e96c  mov     rcx, [rbp+hKey]; hKey
0x18002e970  lea     rax, [rbp+cbData]
0x18002e974  or      dword ptr [rbx], 0B0004Fh
0x18002e97a  lea     r9, [rbp+Type]; lpType
0x18002e97e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002e983  lea     rdx, aApplicationtyp; "ApplicationType"
0x18002e98a  lea     rax, [rbp+Data]
0x18002e98e  mov     [rbp+Type], 4
0x18002e995  xor     r8d, r8d; lpReserved
0x18002e998  mov     [rsp+50h+phkResult], rax; int
0x18002e99d  mov     [rbp+cbData], 4
0x18002e9a4  call    cs:__imp_RegQueryValueExW
0x18002e9aa  mov     edi, eax
0x18002e9ac  test    eax, eax
0x18002e9ae  jg      loc_18002EB96
0x18002e9b4  test    edi, edi
0x18002e9b6  js      loc_18002EDA0
0x18002e9bc  cmp     [rbp+Type], 4
0x18002e9c0  jnz     loc_18002EDE3
0x18002e9c6  mov     eax, [rbp+Data]
0x18002e9c9  cmp     eax, 10000000h
0x18002e9ce  jnz     loc_18002EC08
0x18002e9d4  or      [rbx], eax
0x18002e9d6  lea     r9, [rbp+Type]; lpType
0x18002e9da  mov     rcx, [rbp+hKey]; hKey
0x18002e9de  lea     rax, [rbp+cbData]
0x18002e9e2  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002e9e7  lea     rdx, aRegistrationty; "RegistrationType"
0x18002e9ee  lea     rax, [rbp+arg_18]
0x18002e9f2  mov     [rbp+Type], 4
0x18002e9f9  xor     r8d, r8d; lpReserved
0x18002e9fc  mov     [rsp+50h+phkResult], rax; int
0x18002ea01  mov     [rbp+cbData], 4
0x18002ea08  call    cs:__imp_RegQueryValueExW
0x18002ea0e  cmp     eax, 2
0x18002ea11  jz      short loc_18002EA4C
0x18002ea13  test    eax, eax
0x18002ea15  jg      loc_18002EBA4
0x18002ea1b  mov     edi, eax
0x18002ea1d  test    edi, edi
0x18002ea1f  js      loc_18002EC2B
0x18002ea25  cmp     [rbp+Type], 4
0x18002ea29  jnz     loc_18002EDED
0x18002ea2f  mov     eax, [rbp+arg_18]
0x18002ea32  test    eax, eax
0x18002ea34  jnz     loc_18002EBB2
0x18002ea3a  cmp     eax, 1
0x18002ea3d  jz      loc_18002EBBB
0x18002ea43  mov     eax, r14d
0x18002ea46  or      [rsi+210h], eax
0x18002ea4c  lea     rcx, [rbp+cbData]
0x18002ea50  mov     [rbp+Type], 3
0x18002ea57  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18002ea5c  lea     rax, [rsi+208h]
0x18002ea63  mov     rcx, [rbp+hKey]; hKey
0x18002ea67  lea     r9, [rbp+Type]; lpType
0x18002ea6b  xor     r8d, r8d; lpReserved
0x18002ea6e  mov     [rbp+cbData], 8
0x18002ea75  lea     rdx, aWnfEvent; "WNF-Event"
0x18002ea7c  mov     [rsp+50h+phkResult], rax; int
0x18002ea81  call    cs:__imp_RegQueryValueExW
0x18002ea87  cmp     eax, 2
0x18002ea8a  jnz     loc_18002EC6E
0x18002ea90  lea     rcx, [rbp+cbData]
0x18002ea94  mov     [rbp+cbData], 1000h
0x18002ea9b  mov     [rsp+50h+pcbData], rcx; pcbData
0x18002eaa0  lea     rax, [rsi+214h]
0x18002eaa7  mov     rcx, [rbp+hKey]; hkey
0x18002eaab  lea     r8, aUri; "Uri"
0x18002eab2  mov     [rsp+50h+lpcbData], rax; pvData
0x18002eab7  mov     r9d, 2; dwFlags
0x18002eabd  xor     edx, edx; lpSubKey
0x18002eabf  mov     [rsp+50h+phkResult], r14; pdwType
0x18002eac4  call    cs:__imp_RegGetValueW
0x18002eaca  test    eax, eax
0x18002eacc  jnz     loc_18002E88B
0x18002ead2  mov     rcx, [rbp+hKey]; hkey
0x18002ead6  lea     rax, [rbp+cbData]
0x18002eada  mov     [rsp+50h+pcbData], rax; pcbData
0x18002eadf  lea     r8, aRecurrence; "Recurrence"
0x18002eae6  lea     rax, [rbp+pvData]
0x18002eaea  mov     [rbp+pvData], r14d
0x18002eaee  mov     [rsp+50h+lpcbData], rax; pvData
0x18002eaf3  mov     r9d, 10h; dwFlags
0x18002eaf9  xor     edx, edx; lpSubKey
0x18002eafb  mov     [rsp+50h+phkResult], r14; int
0x18002eb00  mov     [rbp+cbData], 4
0x18002eb07  call    cs:__imp_RegGetValueW
0x18002eb0d  mov     edi, eax
0x18002eb0f  test    eax, eax
0x18002eb11  jle     short loc_18002EB1C
0x18002eb13  movzx   edi, ax
0x18002eb16  or      edi, 80070000h
0x18002eb1c  test    edi, edi
0x18002eb1e  jns     loc_18002EE1B
0x18002eb24  mov     rcx, [rbp+28h]; this
0x18002eb28  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002eb2f  mov     r9d, edi; char *
0x18002eb32  mov     edx, 389h; void *
0x18002eb37  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002eb3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb43  lea     rax, WPP_GLOBAL_Control
0x18002eb4a  cmp     rcx, rax
0x18002eb4d  jz      loc_18002E88B
0x18002eb53  test    byte ptr [rcx+1Ch], 80h
0x18002eb57  jz      loc_18002E88B
0x18002eb5d  mov     edx, 24h ; '$'
0x18002eb62  mov     rcx, [rcx+10h]
0x18002eb66  lea     r8, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids
0x18002eb6d  mov     r9d, edi
0x18002eb70  call    WPP_SF_d
0x18002eb75  jmp     loc_18002E88B
0x18002eb7a  movzx   edi, ax
0x18002eb7d  or      edi, 80070000h
0x18002eb83  jmp     loc_18002E8FA
0x18002eb88  movzx   edi, ax
0x18002eb8b  or      edi, 80070000h
0x18002eb91  jmp     loc_18002E951
0x18002eb96  movzx   edi, ax
0x18002eb99  or      edi, 80070000h
0x18002eb9f  jmp     loc_18002E9B4
0x18002eba4  movzx   edi, ax
0x18002eba7  or      edi, 80070000h
0x18002ebad  jmp     loc_18002EA1D
0x18002ebb2  cmp     eax, 1
0x18002ebb5  jnz     loc_18002EDF7
0x18002ebbb  mov     eax, 2
0x18002ebc0  jmp     loc_18002EA46
0x18002ebc5  mov     rcx, [rbp+28h]; this
0x18002ebc9  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002ebd0  mov     r9d, edi; char *
0x18002ebd3  mov     edx, 301h; void *
0x18002ebd8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ebdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebe4  lea     rax, WPP_GLOBAL_Control
0x18002ebeb  cmp     rcx, rax
0x18002ebee  jz      loc_18002E88B
0x18002ebf4  test    byte ptr [rcx+1Ch], 80h
0x18002ebf8  jz      loc_18002E88B
0x18002ebfe  mov     edx, 1Dh
0x18002ec03  jmp     loc_18002EB62
0x18002ec08  cmp     eax, 40000000h
0x18002ec0d  jz      loc_18002E9D4
0x18002ec13  cmp     eax, 80000000h
0x18002ec18  jz      loc_18002E9D4
0x18002ec1e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "ApplicationType == APP_IMMERSIVE || ApplicationType == APP_SYSTEM || ApplicationType == APP_PHONE_LEGACY")
0x18002ec23  mov     eax, [rbp+Data]
0x18002ec26  jmp     loc_18002E9D4
0x18002ec2b  mov     rcx, [rbp+28h]; this
0x18002ec2f  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002ec36  mov     r9d, edi; char *
0x18002ec39  mov     edx, 358h; void *
0x18002ec3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ec43  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec4a  lea     rax, WPP_GLOBAL_Control
0x18002ec51  cmp     rcx, rax
0x18002ec54  jz      loc_18002E88B
0x18002ec5a  test    byte ptr [rcx+1Ch], 80h
0x18002ec5e  jz      loc_18002E88B
0x18002ec64  mov     edx, 22h ; '"'
0x18002ec69  jmp     loc_18002EB62
0x18002ec6e  test    eax, eax
0x18002ec70  jg      short loc_18002ECBF
0x18002ec72  mov     edi, eax
0x18002ec74  test    edi, edi
0x18002ec76  jns     loc_18002EE04
0x18002ec7c  mov     rcx, [rbp+28h]; this
0x18002ec80  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002ec87  mov     r9d, edi; char *
0x18002ec8a  mov     edx, 370h; void *
0x18002ec8f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ec94  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec9b  lea     rax, WPP_GLOBAL_Control
0x18002eca2  cmp     rcx, rax
0x18002eca5  jz      loc_18002E88B
0x18002ecab  test    byte ptr [rcx+1Ch], 80h
0x18002ecaf  jz      loc_18002E88B
0x18002ecb5  mov     edx, 23h ; '#'
0x18002ecba  jmp     loc_18002EB62
0x18002ecbf  movzx   edi, ax
0x18002ecc2  or      edi, 80070000h
0x18002ecc8  jmp     short loc_18002EC74
  ... truncated ...
```
