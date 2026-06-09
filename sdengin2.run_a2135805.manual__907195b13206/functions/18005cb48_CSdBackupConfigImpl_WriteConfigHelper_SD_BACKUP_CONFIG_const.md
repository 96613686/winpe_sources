# CSdBackupConfigImpl::_WriteConfigHelper(_SD_BACKUP_CONFIG const *)

- ea: `0x18005cb48`
- end: `0x18005d0ee`
- name: `?_WriteConfigHelper@CSdBackupConfigImpl@@AEAAJPEBU_SD_BACKUP_CONFIG@@@Z`
- size: `1446`
- prototype: `__int64 __fastcall(CSdBackupConfigImpl *__hidden this, const struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005c8c8`

## callees

- `0x18005cb48`
- `0x18005d1bc`
- `0x18005d6bc`
- `0x18005db5c`
- `0x180072e08`
- `0x180072f14`
- `0x18008abd0`
- `0x18008c040`
- `0x18008c0c4`
- `0x1800987fc`
- `0x1800991c8`
- `0x1800993dc`
- `0x18009f560`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18005cf68`
- `msvcrt!_wcsicmp` at `0x18005cf68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cc35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cd06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cd4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cf8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d04e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d0a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d0c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cc35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cd06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cd4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cf8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d04e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d0a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d0c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005cbe2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005cbe2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005cc79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005cd8f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005cfd1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005cc79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005cd8f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005cfd1`
- `ole32!CoTaskMemFree` at `0x18005d062`
- `ole32!CoTaskMemFree` at `0x18005d062`

## string_xrefs

- `0x18005cb6d`: `CSdBackupConfigImpl::_WriteConfigHelper`

## pseudocode

```c
__int64 __fastcall CSdBackupConfigImpl::_WriteConfigHelper(
        CSdBackupConfigImpl *this,
        const struct _SD_BACKUP_CONFIG *a2)
{
  __int16 v4; // ax
  int v5; // eax
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  bool v9; // sf
  int v10; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  int v14; // eax
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  BYTE *v18; // r8
  BYTE *v19; // r8
  int v20; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  unsigned int v24; // ebx
  HKEY KeyHandle; // [rsp+50h] [rbp-29h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp-21h] BYREF
  wchar_t *String1[2]; // [rsp+60h] [rbp-19h] BYREF
  int LastAsrRestoreId; // [rsp+70h] [rbp-9h] BYREF
  __int16 v30; // [rsp+74h] [rbp-5h]
  __int16 v31; // [rsp+76h] [rbp-3h]
  DWORD dwDisposition; // [rsp+E8h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+F0h] [rbp+77h] BYREF
  HKEY v34; // [rsp+F8h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastAsrRestoreId,
    "CSdBackupConfigImpl::_WriteConfigHelper",
    0x227u,
    1u);
  KeyHandle = 0;
  v34 = 0;
  hKey = 0;
  String1[0] = (wchar_t *)qword_1800EE510;
  String1[1] = 0;
  dwDisposition = 0;
  String2 = 0;
  v4 = 560;
  if ( !a2 )
    goto LABEL_2;
  LastAsrRestoreId = 0;
  v30 = 560;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup",
         0,
         0x2001Fu,
         &KeyHandle);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  LastAsrRestoreId = v5;
  v9 = v5 < 0;
  v4 = 565;
  if ( v9 )
    goto LABEL_3;
  v30 = 565;
  LastAsrRestoreId = SetRegKeyVirtualization(KeyHandle, v6, v7, v8);
  v4 = 566;
  if ( LastAsrRestoreId < 0 )
    goto LABEL_3;
  v30 = 566;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v10 = RegCreateKeyExW(KeyHandle, L"ScheduleParams", 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  if ( v10 > 0 )
    v10 = (unsigned __int16)v10 | 0x80070000;
  LastAsrRestoreId = v10;
  v9 = v10 < 0;
  v4 = 579;
  if ( v9 )
    goto LABEL_3;
  v30 = 579;
  LastAsrRestoreId = SetRegKeyVirtualization(hKey, v11, v12, v13);
  v4 = 580;
  if ( LastAsrRestoreId < 0 )
    goto LABEL_3;
  v30 = 580;
  if ( dwDisposition == 2 )
  {
    LastAsrRestoreId = ReadStringFromRegistry(hKey, L"LastAsrRestoreId", &String2, 1);
    v4 = 587;
    if ( LastAsrRestoreId < 0 )
      goto LABEL_3;
    v30 = 587;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    LastAsrRestoreId = DeleteRegistryKeyTree(KeyHandle, L"ScheduleParams", 0);
    v4 = 595;
    if ( LastAsrRestoreId < 0 )
      goto LABEL_3;
    v30 = 595;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v14 = RegCreateKeyExW(KeyHandle, L"ScheduleParams", 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    LastAsrRestoreId = v14;
    v9 = v14 < 0;
    v4 = 604;
    if ( v9 )
      goto LABEL_3;
    v30 = 604;
    LastAsrRestoreId = SetRegKeyVirtualization(hKey, v15, v16, v17);
    v4 = 605;
    if ( LastAsrRestoreId < 0 )
      goto LABEL_3;
    v30 = 605;
  }
  LastAsrRestoreId = CSdBackupConfigImpl::_WriteStorageDevice(
                       this,
                       hKey,
                       (const struct _SD_BACKUP_CONFIG *)((char *)a2 + 40));
  v4 = 608;
  if ( LastAsrRestoreId < 0
    || (v30 = 608,
        LastAsrRestoreId = SxRegWriteDWORD(hKey, L"BackupType", *((_DWORD *)a2 + 58)),
        v4 = 610,
        LastAsrRestoreId < 0) )
  {
LABEL_3:
    v31 = v4;
    goto LABEL_48;
  }
  v30 = 610;
  v18 = (BYTE *)*((_QWORD *)a2 + 1);
  v4 = 612;
  if ( !v18 )
    goto LABEL_2;
  LastAsrRestoreId = 0;
  v30 = 612;
  LastAsrRestoreId = SxRegWriteString(hKey, L"Name", v18);
  v4 = 613;
  if ( LastAsrRestoreId < 0 )
    goto LABEL_3;
  v30 = 613;
  v19 = (BYTE *)*((_QWORD *)a2 + 2);
  v4 = 615;
  if ( !v19 )
  {
LABEL_2:
    LastAsrRestoreId = -2147024809;
    goto LABEL_3;
  }
  LastAsrRestoreId = 0;
  v30 = 615;
  LastAsrRestoreId = SxRegWriteString(hKey, L"Description", v19);
  v4 = 616;
  if ( LastAsrRestoreId < 0 )
    goto LABEL_3;
  v30 = 616;
  LastAsrRestoreId = SxRegWriteDWORD(hKey, L"BackupFlags", *(_DWORD *)a2);
  v4 = 618;
  if ( LastAsrRestoreId < 0 )
    goto LABEL_3;
  v30 = 618;
  LastAsrRestoreId = SxRegWriteDWORD(hKey, L"IncludeFutureUsers", *((_DWORD *)a2 + 59) != 0);
  v4 = 620;
  if ( LastAsrRestoreId < 0 )
    goto LABEL_3;
  v30 = 620;
  LastAsrRestoreId = CSdBackupConfigImpl::_WriteRegistryRules(this, hKey);
  v4 = 622;
  if ( LastAsrRestoreId < 0 )
    goto LABEL_3;
  v30 = 622;
  LastAsrRestoreId = CSdBackupConfigImpl::_WriteUsersToRegistry(this, hKey, a2);
  v4 = 624;
  if ( LastAsrRestoreId < 0 )
    goto LABEL_3;
  v30 = 624;
  LastAsrRestoreId = SxGetLastAsrRestoreId((struct CBsString *)String1);
  v4 = 629;
  if ( LastAsrRestoreId < 0 )
    goto LABEL_3;
  v30 = 629;
  if ( String2 && _wcsicmp(String1[0], String2) )
  {
    if ( (unsigned __int64)v34 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v34);
      v34 = 0;
    }
    v20 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\Status",
            0,
            0,
            0,
            0x2001Fu,
            0,
            &v34,
            &dwDisposition);
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    LastAsrRestoreId = v20;
    v9 = v20 < 0;
    v4 = 649;
    if ( v9 )
      goto LABEL_3;
    v30 = 649;
    LastAsrRestoreId = SetRegKeyVirtualization(v34, v21, v22, v23);
    v4 = 650;
    if ( LastAsrRestoreId < 0 )
      goto LABEL_3;
    v30 = 650;
    LastAsrRestoreId = SxRegWriteString(v34, L"TrackLastAsrRestoreId", (BYTE *)String1[0]);
    v4 = 652;
    if ( LastAsrRestoreId < 0 )
      goto LABEL_3;
    v30 = 652;
    if ( (unsigned __int64)v34 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v34);
      v34 = 0;
    }
  }
LABEL_48:
  CoTaskMemFree(String2);
  v24 = LastAsrRestoreId;
  CBsString::_Release((CBsString *)String1);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (unsigned __int64)v34 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v34);
    v34 = 0;
  }
  if ( (unsigned __int64)KeyHandle - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(KeyHandle);
    KeyHandle = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastAsrRestoreId);
  return v24;
}

```

## disassembly

```asm
0x18005cb48  push    rbp
0x18005cb4a  push    rbx
0x18005cb4b  push    rsi
0x18005cb4c  push    rdi
0x18005cb4d  push    r12
0x18005cb4f  lea     rbp, [rsp-37h]
0x18005cb54  sub     rsp, 0B0h
0x18005cb5b  mov     rbx, rdx
0x18005cb5e  mov     rdi, rcx
0x18005cb61  mov     r9d, 1; unsigned __int16
0x18005cb67  mov     r8d, 227h; unsigned __int16
0x18005cb6d  lea     rdx, aCsdbackupconfi_4; "CSdBackupConfigImpl::_WriteConfigHelper"
0x18005cb74  lea     rcx, [rbp+57h+var_60]; this
0x18005cb78  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005cb7d  xor     esi, esi
0x18005cb7f  mov     [rbp+57h+KeyHandle], rsi
0x18005cb83  mov     [rbp+57h+arg_18], rsi
0x18005cb87  mov     [rbp+57h+hKey], rsi
0x18005cb8b  lea     rax, qword_1800EE510
0x18005cb92  mov     [rbp+57h+String1], rax
0x18005cb96  mov     [rbp+57h+var_68], rsi
0x18005cb9a  mov     [rbp+57h+dwDisposition], esi
0x18005cb9d  mov     [rbp+57h+String2], rsi
0x18005cba1  mov     eax, 230h
0x18005cba6  test    rbx, rbx
0x18005cba9  jnz     short loc_18005CBBB
0x18005cbab  mov     [rbp+57h+var_60], 80070057h
0x18005cbb2  mov     [rbp+57h+var_5A], ax
0x18005cbb6  jmp     loc_18005D05E
0x18005cbbb  mov     [rbp+57h+var_60], esi
0x18005cbbe  mov     [rbp+57h+var_5C], ax
0x18005cbc2  lea     rax, [rbp+57h+KeyHandle]
0x18005cbc6  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18005cbcb  mov     r9d, 2001Fh; samDesired
0x18005cbd1  xor     r8d, r8d; ulOptions
0x18005cbd4  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005cbdb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005cbe2  call    cs:__imp_RegOpenKeyExW
0x18005cbe9  nop     dword ptr [rax+rax+00h]
0x18005cbee  mov     r12d, 80070000h
0x18005cbf4  test    eax, eax
0x18005cbf6  jle     short loc_18005CBFE
0x18005cbf8  movzx   eax, ax
0x18005cbfb  or      eax, r12d
0x18005cbfe  mov     [rbp+57h+var_60], eax
0x18005cc01  test    eax, eax
0x18005cc03  mov     eax, 235h
0x18005cc08  js      short loc_18005CBB2
0x18005cc0a  mov     [rbp+57h+var_5C], ax
0x18005cc0e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005cc12  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005cc17  mov     [rbp+57h+var_60], eax
0x18005cc1a  test    eax, eax
0x18005cc1c  mov     eax, 236h
0x18005cc21  js      short loc_18005CBB2
0x18005cc23  mov     [rbp+57h+var_5C], ax
0x18005cc27  mov     rcx, [rbp+57h+hKey]; hKey
0x18005cc2b  lea     rax, [rcx-1]
0x18005cc2f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cc33  ja      short loc_18005CC45
0x18005cc35  call    cs:__imp_RegCloseKey
0x18005cc3c  nop     dword ptr [rax+rax+00h]
0x18005cc41  mov     [rbp+57h+hKey], rsi
0x18005cc45  lea     rax, [rbp+57h+dwDisposition]
0x18005cc49  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18005cc4e  lea     rax, [rbp+57h+hKey]
0x18005cc52  mov     [rsp+0D0h+var_98], rax; phkResult
0x18005cc57  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18005cc5c  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18005cc64  mov     dword ptr [rsp+0D0h+phkResult], esi; dwOptions
0x18005cc68  xor     r9d, r9d; lpClass
0x18005cc6b  xor     r8d, r8d; Reserved
0x18005cc6e  lea     rdx, c_wszSafedocsSchedulingKeyName; "ScheduleParams"
0x18005cc75  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005cc79  call    cs:__imp_RegCreateKeyExW
0x18005cc80  nop     dword ptr [rax+rax+00h]
0x18005cc85  test    eax, eax
0x18005cc87  jle     short loc_18005CC8F
0x18005cc89  movzx   eax, ax
0x18005cc8c  or      eax, r12d
0x18005cc8f  mov     [rbp+57h+var_60], eax
0x18005cc92  test    eax, eax
0x18005cc94  mov     eax, 243h
0x18005cc99  js      loc_18005CBB2
0x18005cc9f  mov     [rbp+57h+var_5C], ax
0x18005cca3  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18005cca7  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005ccac  mov     [rbp+57h+var_60], eax
0x18005ccaf  test    eax, eax
0x18005ccb1  mov     eax, 244h
0x18005ccb6  js      loc_18005CBB2
0x18005ccbc  mov     [rbp+57h+var_5C], ax
0x18005ccc0  cmp     [rbp+57h+dwDisposition], 2
0x18005ccc4  jnz     loc_18005CDD6
0x18005ccca  mov     r9d, 1; int
0x18005ccd0  lea     r8, [rbp+57h+String2]; unsigned __int16 **
0x18005ccd4  lea     rdx, c_wszSafedocsScheduleLastAsrRestoreId; "LastAsrRestoreId"
0x18005ccdb  mov     rcx, [rbp+57h+hKey]; hKey
0x18005ccdf  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18005cce4  mov     [rbp+57h+var_60], eax
0x18005cce7  test    eax, eax
0x18005cce9  mov     eax, 24Bh
0x18005ccee  js      loc_18005CBB2
0x18005ccf4  mov     [rbp+57h+var_5C], ax
0x18005ccf8  mov     rcx, [rbp+57h+hKey]; hKey
0x18005ccfc  lea     rax, [rcx-1]
0x18005cd00  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cd04  ja      short loc_18005CD16
0x18005cd06  call    cs:__imp_RegCloseKey
0x18005cd0d  nop     dword ptr [rax+rax+00h]
0x18005cd12  mov     [rbp+57h+hKey], rsi
0x18005cd16  xor     r8d, r8d; int
0x18005cd19  lea     rdx, c_wszSafedocsSchedulingKeyName; "ScheduleParams"
0x18005cd20  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005cd24  call    ?DeleteRegistryKeyTree@@YAJPEAUHKEY__@@PEBGH@Z; DeleteRegistryKeyTree(HKEY__ *,ushort const *,int)
0x18005cd29  mov     [rbp+57h+var_60], eax
0x18005cd2c  test    eax, eax
0x18005cd2e  mov     eax, 253h
0x18005cd33  js      loc_18005CBB2
0x18005cd39  mov     [rbp+57h+var_5C], ax
0x18005cd3d  mov     rcx, [rbp+57h+hKey]; hKey
0x18005cd41  lea     rax, [rcx-1]
0x18005cd45  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cd49  ja      short loc_18005CD5B
0x18005cd4b  call    cs:__imp_RegCloseKey
0x18005cd52  nop     dword ptr [rax+rax+00h]
0x18005cd57  mov     [rbp+57h+hKey], rsi
0x18005cd5b  lea     rax, [rbp+57h+dwDisposition]
0x18005cd5f  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18005cd64  lea     rax, [rbp+57h+hKey]
0x18005cd68  mov     [rsp+0D0h+var_98], rax; phkResult
0x18005cd6d  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18005cd72  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18005cd7a  mov     dword ptr [rsp+0D0h+phkResult], esi; dwOptions
0x18005cd7e  xor     r9d, r9d; lpClass
0x18005cd81  xor     r8d, r8d; Reserved
0x18005cd84  lea     rdx, c_wszSafedocsSchedulingKeyName; "ScheduleParams"
0x18005cd8b  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005cd8f  call    cs:__imp_RegCreateKeyExW
0x18005cd96  nop     dword ptr [rax+rax+00h]
0x18005cd9b  test    eax, eax
0x18005cd9d  jle     short loc_18005CDA5
0x18005cd9f  movzx   eax, ax
0x18005cda2  or      eax, r12d
0x18005cda5  mov     [rbp+57h+var_60], eax
0x18005cda8  test    eax, eax
0x18005cdaa  mov     eax, 25Ch
0x18005cdaf  js      loc_18005CBB2
0x18005cdb5  mov     [rbp+57h+var_5C], ax
0x18005cdb9  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18005cdbd  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005cdc2  mov     [rbp+57h+var_60], eax
0x18005cdc5  test    eax, eax
0x18005cdc7  mov     eax, 25Dh
0x18005cdcc  js      loc_18005CBB2
0x18005cdd2  mov     [rbp+57h+var_5C], ax
0x18005cdd6  lea     r8, [rbx+28h]; struct _SD_STORAGE_DEVICE_PROP *
0x18005cdda  mov     rdx, [rbp+57h+hKey]; HKEY
0x18005cdde  mov     rcx, rdi; this
0x18005cde1  call    ?_WriteStorageDevice@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEBU_SD_STORAGE_DEVICE_PROP@@@Z; CSdBackupConfigImpl::_WriteStorageDevice(HKEY__ *,_SD_STORAGE_DEVICE_PROP const *)
0x18005cde6  mov     [rbp+57h+var_60], eax
0x18005cde9  test    eax, eax
0x18005cdeb  mov     eax, 260h
0x18005cdf0  js      loc_18005CBB2
0x18005cdf6  mov     [rbp+57h+var_5C], ax
0x18005cdfa  mov     r8d, [rbx+0E8h]; unsigned int
0x18005ce01  lea     rdx, c_wszSafedocsScheduleBackupType; "BackupType"
0x18005ce08  mov     rcx, [rbp+57h+hKey]; hKey
0x18005ce0c  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005ce11  mov     [rbp+57h+var_60], eax
0x18005ce14  test    eax, eax
0x18005ce16  mov     eax, 262h
0x18005ce1b  js      loc_18005CBB2
0x18005ce21  mov     [rbp+57h+var_5C], ax
0x18005ce25  mov     r8, [rbx+8]; lpData
0x18005ce29  mov     eax, 264h
0x18005ce2e  test    r8, r8
0x18005ce31  jz      loc_18005CBAB
0x18005ce37  mov     [rbp+57h+var_60], esi
0x18005ce3a  mov     [rbp+57h+var_5C], ax
0x18005ce3e  lea     rdx, c_wszSafedocsScheduleName; "Name"
0x18005ce45  mov     rcx, [rbp+57h+hKey]; hKey
0x18005ce49  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005ce4e  mov     [rbp+57h+var_60], eax
0x18005ce51  test    eax, eax
0x18005ce53  mov     eax, 265h
0x18005ce58  js      loc_18005CBB2
0x18005ce5e  mov     [rbp+57h+var_5C], ax
0x18005ce62  mov     r8, [rbx+10h]; lpData
0x18005ce66  mov     eax, 267h
0x18005ce6b  test    r8, r8
0x18005ce6e  jz      loc_18005CBAB
0x18005ce74  mov     [rbp+57h+var_60], esi
0x18005ce77  mov     [rbp+57h+var_5C], ax
0x18005ce7b  lea     rdx, c_wszSafedocsScheduleDescription; "Description"
0x18005ce82  mov     rcx, [rbp+57h+hKey]; hKey
0x18005ce86  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005ce8b  mov     [rbp+57h+var_60], eax
0x18005ce8e  test    eax, eax
0x18005ce90  mov     eax, 268h
0x18005ce95  js      loc_18005CBB2
0x18005ce9b  mov     [rbp+57h+var_5C], ax
0x18005ce9f  mov     r8d, [rbx]; unsigned int
0x18005cea2  lea     rdx, c_wszSafedocsScheduleBackupFlags; "BackupFlags"
0x18005cea9  mov     rcx, [rbp+57h+hKey]; hKey
0x18005cead  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005ceb2  mov     [rbp+57h+var_60], eax
0x18005ceb5  test    eax, eax
0x18005ceb7  mov     eax, 26Ah
0x18005cebc  js      loc_18005CBB2
0x18005cec2  mov     [rbp+57h+var_5C], ax
0x18005cec6  mov     r8d, esi
0x18005cec9  cmp     [rbx+0ECh], esi
0x18005cecf  setnz   r8b; unsigned int
0x18005ced3  lea     rdx, c_wszSafedocsScheduleIncludeFutureUsers; "IncludeFutureUsers"
0x18005ceda  mov     rcx, [rbp+57h+hKey]; hKey
0x18005cede  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005cee3  mov     [rbp+57h+var_60], eax
0x18005cee6  test    eax, eax
0x18005cee8  mov     eax, 26Ch
0x18005ceed  js      loc_18005CBB2
0x18005cef3  mov     [rbp+57h+var_5C], ax
0x18005cef7  mov     rdx, [rbp+57h+hKey]; HKEY
0x18005cefb  mov     rcx, rdi; this
0x18005cefe  call    ?_WriteRegistryRules@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@@Z; CSdBackupConfigImpl::_WriteRegistryRules(HKEY__ *)
0x18005cf03  mov     [rbp+57h+var_60], eax
0x18005cf06  test    eax, eax
0x18005cf08  mov     eax, 26Eh
0x18005cf0d  js      loc_18005CBB2
0x18005cf13  mov     [rbp+57h+var_5C], ax
0x18005cf17  mov     r8, rbx; struct _SD_BACKUP_CONFIG *
0x18005cf1a  mov     rdx, [rbp+57h+hKey]; HKEY
0x18005cf1e  mov     rcx, rdi; this
0x18005cf21  call    ?_WriteUsersToRegistry@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEBU_SD_BACKUP_CONFIG@@@Z; CSdBackupConfigImpl::_WriteUsersToRegistry(HKEY__ *,_SD_BACKUP_CONFIG const *)
0x18005cf26  mov     [rbp+57h+var_60], eax
0x18005cf29  test    eax, eax
0x18005cf2b  mov     eax, 270h
0x18005cf30  js      loc_18005CBB2
0x18005cf36  mov     [rbp+57h+var_5C], ax
0x18005cf3a  lea     rcx, [rbp+57h+String1]; this
0x18005cf3e  call    ?SxGetLastAsrRestoreId@@YAJPEAVCBsString@@@Z; SxGetLastAsrRestoreId(CBsString *)
0x18005cf43  mov     [rbp+57h+var_60], eax
0x18005cf46  test    eax, eax
0x18005cf48  mov     eax, 275h
0x18005cf4d  js      loc_18005CBB2
0x18005cf53  mov     [rbp+57h+var_5C], ax
0x18005cf57  mov     rdx, [rbp+57h+String2]; String2
0x18005cf5b  test    rdx, rdx
0x18005cf5e  jz      loc_18005D05E
0x18005cf64  mov     rcx, [rbp+57h+String1]; String1
0x18005cf68  call    cs:__imp__wcsicmp
0x18005cf6f  nop     dword ptr [rax+rax+00h]
0x18005cf74  test    eax, eax
0x18005cf76  jz      loc_18005D05E
0x18005cf7c  mov     rcx, [rbp+57h+arg_18]; hKey
0x18005cf80  lea     rax, [rcx-1]
0x18005cf84  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cf88  ja      short loc_18005CF9A
0x18005cf8a  call    cs:__imp_RegCloseKey
0x18005cf91  nop     dword ptr [rax+rax+00h]
0x18005cf96  mov     [rbp+57h+arg_18], rsi
0x18005cf9a  lea     rax, [rbp+57h+dwDisposition]
0x18005cf9e  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18005cfa3  lea     rax, [rbp+57h+arg_18]
0x18005cfa7  mov     [rsp+0D0h+var_98], rax; phkResult
0x18005cfac  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18005cfb1  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18005cfb9  mov     dword ptr [rsp+0D0h+phkResult], esi; dwOptions
0x18005cfbd  xor     r9d, r9d; lpClass
0x18005cfc0  xor     r8d, r8d; Reserved
0x18005cfc3  lea     rdx, c_wszSafedocsStatusKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005cfca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005cfd1  call    cs:__imp_RegCreateKeyExW
0x18005cfd8  nop     dword ptr [rax+rax+00h]
0x18005cfdd  test    eax, eax
0x18005cfdf  jle     short loc_18005CFE7
0x18005cfe1  movzx   eax, ax
0x18005cfe4  or      eax, r12d
0x18005cfe7  mov     [rbp+57h+var_60], eax
0x18005cfea  test    eax, eax
0x18005cfec  mov     eax, 289h
0x18005cff1  js      loc_18005CBB2
0x18005cff7  mov     [rbp+57h+var_5C], ax
0x18005cffb  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x18005cfff  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005d004  mov     [rbp+57h+var_60], eax
0x18005d007  test    eax, eax
0x18005d009  mov     eax, 28Ah
0x18005d00e  js      loc_18005CBB2
0x18005d014  mov     [rbp+57h+var_5C], ax
0x18005d018  mov     r8, [rbp+57h+String1]; lpData
0x18005d01c  lea     rdx, c_wszSafedocsScheduleLastTrackedAsrId; "TrackLastAsrRestoreId"
0x18005d023  mov     rcx, [rbp+57h+arg_18]; hKey
0x18005d027  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005d02c  mov     [rbp+57h+var_60], eax
0x18005d02f  test    eax, eax
0x18005d031  mov     eax, 28Ch
0x18005d036  js      loc_18005CBB2
0x18005d03c  mov     [rbp+57h+var_5C], ax
0x18005d040  mov     rcx, [rbp+57h+arg_18]; hKey
  ... truncated ...
```
