# CSdBackupConfigImpl::_WriteConfigHelper(_SD_BACKUP_CONFIG const *)

- ea: `0x18005a49c`
- end: `0x18005a9ed`
- name: `?_WriteConfigHelper@CSdBackupConfigImpl@@AEAAJPEBU_SD_BACKUP_CONFIG@@@Z`
- size: `1361`
- prototype: `__int64 __fastcall(CSdBackupConfigImpl *__hidden this, const struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005a230`

## callees

- `0x18005a49c`
- `0x18005aab8`
- `0x18005af80`
- `0x18005b3f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008723c`
- `0x1800885bc`
- `0x180088640`
- `0x180094518`
- `0x180094e88`
- `0x180095090`
- `0x18009ae34`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18005a898`
- `msvcrt!_wcsicmp` at `0x18005a898`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a583`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a648`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a8b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a96c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a99a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a9b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a9ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a583`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a648`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a8b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a96c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a99a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a9b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a9ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a536`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a536`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a5c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a6c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a8f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a5c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a6c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a8f5`
- `ole32!CoTaskMemFree` at `0x18005a97a`
- `ole32!CoTaskMemFree` at `0x18005a97a`

## string_xrefs

- `0x18005a4c1`: `CSdBackupConfigImpl::_WriteConfigHelper`

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
  String1[0] = (wchar_t *)qword_1800E8530;
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
0x18005a49c  push    rbp
0x18005a49e  push    rbx
0x18005a49f  push    rsi
0x18005a4a0  push    rdi
0x18005a4a1  push    r12
0x18005a4a3  lea     rbp, [rsp-37h]
0x18005a4a8  sub     rsp, 0B0h
0x18005a4af  mov     rbx, rdx
0x18005a4b2  mov     rdi, rcx
0x18005a4b5  mov     r9d, 1; unsigned __int16
0x18005a4bb  mov     r8d, 227h; unsigned __int16
0x18005a4c1  lea     rdx, aCsdbackupconfi_4; "CSdBackupConfigImpl::_WriteConfigHelper"
0x18005a4c8  lea     rcx, [rbp+57h+var_60]; this
0x18005a4cc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005a4d1  xor     esi, esi
0x18005a4d3  mov     [rbp+57h+KeyHandle], rsi
0x18005a4d7  mov     [rbp+57h+arg_18], rsi
0x18005a4db  mov     [rbp+57h+hKey], rsi
0x18005a4df  lea     rax, qword_1800E8530
0x18005a4e6  mov     [rbp+57h+String1], rax
0x18005a4ea  mov     [rbp+57h+var_68], rsi
0x18005a4ee  mov     [rbp+57h+dwDisposition], esi
0x18005a4f1  mov     [rbp+57h+String2], rsi
0x18005a4f5  mov     eax, 230h
0x18005a4fa  test    rbx, rbx
0x18005a4fd  jnz     short loc_18005A50F
0x18005a4ff  mov     [rbp+57h+var_60], 80070057h
0x18005a506  mov     [rbp+57h+var_5A], ax
0x18005a50a  jmp     loc_18005A976
0x18005a50f  mov     [rbp+57h+var_60], esi
0x18005a512  mov     [rbp+57h+var_5C], ax
0x18005a516  lea     rax, [rbp+57h+KeyHandle]
0x18005a51a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18005a51f  mov     r9d, 2001Fh; samDesired
0x18005a525  xor     r8d, r8d; ulOptions
0x18005a528  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005a52f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005a536  call    cs:__imp_RegOpenKeyExW
0x18005a53c  mov     r12d, 80070000h
0x18005a542  test    eax, eax
0x18005a544  jle     short loc_18005A54C
0x18005a546  movzx   eax, ax
0x18005a549  or      eax, r12d
0x18005a54c  mov     [rbp+57h+var_60], eax
0x18005a54f  test    eax, eax
0x18005a551  mov     eax, 235h
0x18005a556  js      short loc_18005A506
0x18005a558  mov     [rbp+57h+var_5C], ax
0x18005a55c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005a560  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005a565  mov     [rbp+57h+var_60], eax
0x18005a568  test    eax, eax
0x18005a56a  mov     eax, 236h
0x18005a56f  js      short loc_18005A506
0x18005a571  mov     [rbp+57h+var_5C], ax
0x18005a575  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a579  lea     rax, [rcx-1]
0x18005a57d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a581  ja      short loc_18005A58D
0x18005a583  call    cs:__imp_RegCloseKey
0x18005a589  mov     [rbp+57h+hKey], rsi
0x18005a58d  lea     rax, [rbp+57h+dwDisposition]
0x18005a591  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18005a596  lea     rax, [rbp+57h+hKey]
0x18005a59a  mov     [rsp+0D0h+var_98], rax; phkResult
0x18005a59f  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18005a5a4  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18005a5ac  mov     dword ptr [rsp+0D0h+phkResult], esi; dwOptions
0x18005a5b0  xor     r9d, r9d; lpClass
0x18005a5b3  xor     r8d, r8d; Reserved
0x18005a5b6  lea     rdx, c_wszSafedocsSchedulingKeyName; "ScheduleParams"
0x18005a5bd  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005a5c1  call    cs:__imp_RegCreateKeyExW
0x18005a5c7  test    eax, eax
0x18005a5c9  jle     short loc_18005A5D1
0x18005a5cb  movzx   eax, ax
0x18005a5ce  or      eax, r12d
0x18005a5d1  mov     [rbp+57h+var_60], eax
0x18005a5d4  test    eax, eax
0x18005a5d6  mov     eax, 243h
0x18005a5db  js      loc_18005A506
0x18005a5e1  mov     [rbp+57h+var_5C], ax
0x18005a5e5  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18005a5e9  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005a5ee  mov     [rbp+57h+var_60], eax
0x18005a5f1  test    eax, eax
0x18005a5f3  mov     eax, 244h
0x18005a5f8  js      loc_18005A506
0x18005a5fe  mov     [rbp+57h+var_5C], ax
0x18005a602  cmp     [rbp+57h+dwDisposition], 2
0x18005a606  jnz     loc_18005A706
0x18005a60c  mov     r9d, 1; int
0x18005a612  lea     r8, [rbp+57h+String2]; unsigned __int16 **
0x18005a616  lea     rdx, c_wszSafedocsScheduleLastAsrRestoreId; "LastAsrRestoreId"
0x18005a61d  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a621  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18005a626  mov     [rbp+57h+var_60], eax
0x18005a629  test    eax, eax
0x18005a62b  mov     eax, 24Bh
0x18005a630  js      loc_18005A506
0x18005a636  mov     [rbp+57h+var_5C], ax
0x18005a63a  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a63e  lea     rax, [rcx-1]
0x18005a642  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a646  ja      short loc_18005A652
0x18005a648  call    cs:__imp_RegCloseKey
0x18005a64e  mov     [rbp+57h+hKey], rsi
0x18005a652  xor     r8d, r8d; int
0x18005a655  lea     rdx, c_wszSafedocsSchedulingKeyName; "ScheduleParams"
0x18005a65c  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005a660  call    ?DeleteRegistryKeyTree@@YAJPEAUHKEY__@@PEBGH@Z; DeleteRegistryKeyTree(HKEY__ *,ushort const *,int)
0x18005a665  mov     [rbp+57h+var_60], eax
0x18005a668  test    eax, eax
0x18005a66a  mov     eax, 253h
0x18005a66f  js      loc_18005A506
0x18005a675  mov     [rbp+57h+var_5C], ax
0x18005a679  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a67d  lea     rax, [rcx-1]
0x18005a681  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a685  ja      short loc_18005A691
0x18005a687  call    cs:__imp_RegCloseKey
0x18005a68d  mov     [rbp+57h+hKey], rsi
0x18005a691  lea     rax, [rbp+57h+dwDisposition]
0x18005a695  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18005a69a  lea     rax, [rbp+57h+hKey]
0x18005a69e  mov     [rsp+0D0h+var_98], rax; phkResult
0x18005a6a3  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18005a6a8  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18005a6b0  mov     dword ptr [rsp+0D0h+phkResult], esi; dwOptions
0x18005a6b4  xor     r9d, r9d; lpClass
0x18005a6b7  xor     r8d, r8d; Reserved
0x18005a6ba  lea     rdx, c_wszSafedocsSchedulingKeyName; "ScheduleParams"
0x18005a6c1  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18005a6c5  call    cs:__imp_RegCreateKeyExW
0x18005a6cb  test    eax, eax
0x18005a6cd  jle     short loc_18005A6D5
0x18005a6cf  movzx   eax, ax
0x18005a6d2  or      eax, r12d
0x18005a6d5  mov     [rbp+57h+var_60], eax
0x18005a6d8  test    eax, eax
0x18005a6da  mov     eax, 25Ch
0x18005a6df  js      loc_18005A506
0x18005a6e5  mov     [rbp+57h+var_5C], ax
0x18005a6e9  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18005a6ed  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005a6f2  mov     [rbp+57h+var_60], eax
0x18005a6f5  test    eax, eax
0x18005a6f7  mov     eax, 25Dh
0x18005a6fc  js      loc_18005A506
0x18005a702  mov     [rbp+57h+var_5C], ax
0x18005a706  lea     r8, [rbx+28h]; struct _SD_STORAGE_DEVICE_PROP *
0x18005a70a  mov     rdx, [rbp+57h+hKey]; HKEY
0x18005a70e  mov     rcx, rdi; this
0x18005a711  call    ?_WriteStorageDevice@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEBU_SD_STORAGE_DEVICE_PROP@@@Z; CSdBackupConfigImpl::_WriteStorageDevice(HKEY__ *,_SD_STORAGE_DEVICE_PROP const *)
0x18005a716  mov     [rbp+57h+var_60], eax
0x18005a719  test    eax, eax
0x18005a71b  mov     eax, 260h
0x18005a720  js      loc_18005A506
0x18005a726  mov     [rbp+57h+var_5C], ax
0x18005a72a  mov     r8d, [rbx+0E8h]; unsigned int
0x18005a731  lea     rdx, c_wszSafedocsScheduleBackupType; "BackupType"
0x18005a738  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a73c  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005a741  mov     [rbp+57h+var_60], eax
0x18005a744  test    eax, eax
0x18005a746  mov     eax, 262h
0x18005a74b  js      loc_18005A506
0x18005a751  mov     [rbp+57h+var_5C], ax
0x18005a755  mov     r8, [rbx+8]; lpData
0x18005a759  mov     eax, 264h
0x18005a75e  test    r8, r8
0x18005a761  jz      loc_18005A4FF
0x18005a767  mov     [rbp+57h+var_60], esi
0x18005a76a  mov     [rbp+57h+var_5C], ax
0x18005a76e  lea     rdx, c_wszSafedocsScheduleName; "Name"
0x18005a775  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a779  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005a77e  mov     [rbp+57h+var_60], eax
0x18005a781  test    eax, eax
0x18005a783  mov     eax, 265h
0x18005a788  js      loc_18005A506
0x18005a78e  mov     [rbp+57h+var_5C], ax
0x18005a792  mov     r8, [rbx+10h]; lpData
0x18005a796  mov     eax, 267h
0x18005a79b  test    r8, r8
0x18005a79e  jz      loc_18005A4FF
0x18005a7a4  mov     [rbp+57h+var_60], esi
0x18005a7a7  mov     [rbp+57h+var_5C], ax
0x18005a7ab  lea     rdx, c_wszSafedocsScheduleDescription; "Description"
0x18005a7b2  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a7b6  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005a7bb  mov     [rbp+57h+var_60], eax
0x18005a7be  test    eax, eax
0x18005a7c0  mov     eax, 268h
0x18005a7c5  js      loc_18005A506
0x18005a7cb  mov     [rbp+57h+var_5C], ax
0x18005a7cf  mov     r8d, [rbx]; unsigned int
0x18005a7d2  lea     rdx, c_wszSafedocsScheduleBackupFlags; "BackupFlags"
0x18005a7d9  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a7dd  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005a7e2  mov     [rbp+57h+var_60], eax
0x18005a7e5  test    eax, eax
0x18005a7e7  mov     eax, 26Ah
0x18005a7ec  js      loc_18005A506
0x18005a7f2  mov     [rbp+57h+var_5C], ax
0x18005a7f6  mov     r8d, esi
0x18005a7f9  cmp     [rbx+0ECh], esi
0x18005a7ff  setnz   r8b; unsigned int
0x18005a803  lea     rdx, c_wszSafedocsScheduleIncludeFutureUsers; "IncludeFutureUsers"
0x18005a80a  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a80e  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005a813  mov     [rbp+57h+var_60], eax
0x18005a816  test    eax, eax
0x18005a818  mov     eax, 26Ch
0x18005a81d  js      loc_18005A506
0x18005a823  mov     [rbp+57h+var_5C], ax
0x18005a827  mov     rdx, [rbp+57h+hKey]; HKEY
0x18005a82b  mov     rcx, rdi; this
0x18005a82e  call    ?_WriteRegistryRules@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@@Z; CSdBackupConfigImpl::_WriteRegistryRules(HKEY__ *)
0x18005a833  mov     [rbp+57h+var_60], eax
0x18005a836  test    eax, eax
0x18005a838  mov     eax, 26Eh
0x18005a83d  js      loc_18005A506
0x18005a843  mov     [rbp+57h+var_5C], ax
0x18005a847  mov     r8, rbx; struct _SD_BACKUP_CONFIG *
0x18005a84a  mov     rdx, [rbp+57h+hKey]; HKEY
0x18005a84e  mov     rcx, rdi; this
0x18005a851  call    ?_WriteUsersToRegistry@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEBU_SD_BACKUP_CONFIG@@@Z; CSdBackupConfigImpl::_WriteUsersToRegistry(HKEY__ *,_SD_BACKUP_CONFIG const *)
0x18005a856  mov     [rbp+57h+var_60], eax
0x18005a859  test    eax, eax
0x18005a85b  mov     eax, 270h
0x18005a860  js      loc_18005A506
0x18005a866  mov     [rbp+57h+var_5C], ax
0x18005a86a  lea     rcx, [rbp+57h+String1]; this
0x18005a86e  call    ?SxGetLastAsrRestoreId@@YAJPEAVCBsString@@@Z; SxGetLastAsrRestoreId(CBsString *)
0x18005a873  mov     [rbp+57h+var_60], eax
0x18005a876  test    eax, eax
0x18005a878  mov     eax, 275h
0x18005a87d  js      loc_18005A506
0x18005a883  mov     [rbp+57h+var_5C], ax
0x18005a887  mov     rdx, [rbp+57h+String2]; String2
0x18005a88b  test    rdx, rdx
0x18005a88e  jz      loc_18005A976
0x18005a894  mov     rcx, [rbp+57h+String1]; String1
0x18005a898  call    cs:__imp__wcsicmp
0x18005a89e  test    eax, eax
0x18005a8a0  jz      loc_18005A976
0x18005a8a6  mov     rcx, [rbp+57h+arg_18]; hKey
0x18005a8aa  lea     rax, [rcx-1]
0x18005a8ae  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a8b2  ja      short loc_18005A8BE
0x18005a8b4  call    cs:__imp_RegCloseKey
0x18005a8ba  mov     [rbp+57h+arg_18], rsi
0x18005a8be  lea     rax, [rbp+57h+dwDisposition]
0x18005a8c2  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18005a8c7  lea     rax, [rbp+57h+arg_18]
0x18005a8cb  mov     [rsp+0D0h+var_98], rax; phkResult
0x18005a8d0  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18005a8d5  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18005a8dd  mov     dword ptr [rsp+0D0h+phkResult], esi; dwOptions
0x18005a8e1  xor     r9d, r9d; lpClass
0x18005a8e4  xor     r8d, r8d; Reserved
0x18005a8e7  lea     rdx, c_wszSafedocsStatusKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005a8ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005a8f5  call    cs:__imp_RegCreateKeyExW
0x18005a8fb  test    eax, eax
0x18005a8fd  jle     short loc_18005A905
0x18005a8ff  movzx   eax, ax
0x18005a902  or      eax, r12d
0x18005a905  mov     [rbp+57h+var_60], eax
0x18005a908  test    eax, eax
0x18005a90a  mov     eax, 289h
0x18005a90f  js      loc_18005A506
0x18005a915  mov     [rbp+57h+var_5C], ax
0x18005a919  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x18005a91d  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005a922  mov     [rbp+57h+var_60], eax
0x18005a925  test    eax, eax
0x18005a927  mov     eax, 28Ah
0x18005a92c  js      loc_18005A506
0x18005a932  mov     [rbp+57h+var_5C], ax
0x18005a936  mov     r8, [rbp+57h+String1]; lpData
0x18005a93a  lea     rdx, c_wszSafedocsScheduleLastTrackedAsrId; "TrackLastAsrRestoreId"
0x18005a941  mov     rcx, [rbp+57h+arg_18]; hKey
0x18005a945  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005a94a  mov     [rbp+57h+var_60], eax
0x18005a94d  test    eax, eax
0x18005a94f  mov     eax, 28Ch
0x18005a954  js      loc_18005A506
0x18005a95a  mov     [rbp+57h+var_5C], ax
0x18005a95e  mov     rcx, [rbp+57h+arg_18]; hKey
0x18005a962  lea     rax, [rcx-1]
0x18005a966  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a96a  ja      short loc_18005A976
0x18005a96c  call    cs:__imp_RegCloseKey
0x18005a972  mov     [rbp+57h+arg_18], rsi
0x18005a976  mov     rcx, [rbp+57h+String2]; pv
0x18005a97a  call    cs:__imp_CoTaskMemFree
0x18005a980  mov     ebx, [rbp+57h+var_60]
0x18005a983  lea     rcx, [rbp+57h+String1]; this
  ... truncated ...
```
