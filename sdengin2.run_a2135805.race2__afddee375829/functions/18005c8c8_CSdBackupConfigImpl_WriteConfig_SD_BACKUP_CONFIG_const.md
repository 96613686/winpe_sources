# CSdBackupConfigImpl::_WriteConfig(_SD_BACKUP_CONFIG const *)

- ea: `0x18005c8c8`
- end: `0x18005cb41`
- name: `?_WriteConfig@CSdBackupConfigImpl@@AEAAJPEBU_SD_BACKUP_CONFIG@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(CSdBackupConfigImpl *__hidden this, const struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config`

## callers

- `0x180059e80`

## callees

- `0x18005aa24`
- `0x18005c8c8`
- `0x18005cb48`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf56a`
- `0x1800cf582`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x18005c9be`
- `KERNEL32!GetVolumePathNameW` at `0x18005c9be`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18005c9f5`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18005c9f5`
- `KERNEL32!GetVolumeInformationW` at `0x18005ca4e`
- `KERNEL32!GetVolumeInformationW` at `0x18005ca4e`

## string_xrefs

- `0x18005c90c`: `CSdBackupConfigImpl::_WriteConfig`

## pseudocode

```c
__int64 __fastcall CSdBackupConfigImpl::_WriteConfig(CSdBackupConfigImpl *this, const struct _SD_BACKUP_CONFIG *a2)
{
  __int64 i; // rdi
  struct _SD_BACKUP_ROOT *v5; // r14
  int LastFailureAsHRESULT; // ebx
  __int16 v7; // ax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  DWORD FileSystemFlags; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v14; // [rsp+4Ch] [rbp-B4h]
  __int16 v15; // [rsp+4Eh] [rbp-B2h]
  WCHAR FileSystemNameBuffer[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v17; // [rsp+90h] [rbp-70h]
  __int128 v18; // [rsp+A0h] [rbp-60h]
  __int16 v19; // [rsp+B0h] [rbp-50h]
  WCHAR szVolumePathName[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR szVolumeName[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "CSdBackupConfigImpl::_WriteConfig", 0x1FAu, 1u);
  FileSystemFlags = 0;
  memset_0(szVolumePathName, 0, 0x208u);
  memset_0(szVolumeName, 0, 0x208u);
  *(_OWORD *)FileSystemNameBuffer = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( a2 )
  {
    v13 = 0;
    v14 = 515;
    for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 6); i = (unsigned int)(i + 1) )
    {
      v5 = (struct _SD_BACKUP_ROOT *)(*((_QWORD *)a2 + 4) + 24 * i);
      LastFailureAsHRESULT = CSdBackupConfigImpl::_AddRulesByName(this, v5);
      v13 = LastFailureAsHRESULT;
      v7 = 524;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_14;
      v14 = 524;
      if ( !GetVolumePathNameW(*(LPCWSTR *)v5, szVolumePathName, 0x104u) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
        v13 = LastFailureAsHRESULT;
        v7 = 529;
        goto LABEL_14;
      }
      v13 = 0;
      v14 = 529;
      if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
        v13 = LastFailureAsHRESULT;
        v7 = 530;
        goto LABEL_14;
      }
      v13 = 0;
      v14 = 530;
      if ( !GetVolumeInformationW(szVolumeName, 0, 0, 0, 0, &FileSystemFlags, FileSystemNameBuffer, 0x19u) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
        v13 = LastFailureAsHRESULT;
        v7 = 531;
LABEL_14:
        v15 = v7;
        goto LABEL_19;
      }
      v14 = 531;
      if ( wcscmp_0(FileSystemNameBuffer, L"NTFS") )
      {
        LastFailureAsHRESULT = -2130706430;
        v15 = 533;
        goto LABEL_18;
      }
      v13 = 0;
      v14 = 533;
    }
    LastFailureAsHRESULT = CSdBackupConfigImpl::_WriteConfigHelper(this, a2);
    v13 = LastFailureAsHRESULT;
    v7 = 539;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_14;
    v14 = 539;
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v15 = 515;
LABEL_18:
    v13 = LastFailureAsHRESULT;
  }
LABEL_19:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18005c8c8  mov     [rsp-8+arg_10], rbx
0x18005c8cd  mov     [rsp-8+arg_18], rsi
0x18005c8d2  push    rbp
0x18005c8d3  push    rdi
0x18005c8d4  push    r13
0x18005c8d6  push    r14
0x18005c8d8  push    r15
0x18005c8da  lea     rbp, [rsp-3F0h]
0x18005c8e2  sub     rsp, 4F0h
0x18005c8e9  mov     rax, cs:__security_cookie
0x18005c8f0  xor     rax, rsp
0x18005c8f3  mov     [rbp+410h+var_30], rax
0x18005c8fa  mov     rsi, rdx
0x18005c8fd  mov     r15, rcx
0x18005c900  mov     r9d, 1; unsigned __int16
0x18005c906  mov     r8d, 1FAh; unsigned __int16
0x18005c90c  lea     rdx, aCsdbackupconfi_21; "CSdBackupConfigImpl::_WriteConfig"
0x18005c913  lea     rcx, [rsp+510h+var_4C8]; this
0x18005c918  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005c91d  mov     [rsp+510h+FileSystemFlags], 0
0x18005c925  mov     ebx, 208h
0x18005c92a  mov     r8d, ebx; Size
0x18005c92d  xor     edx, edx; Val
0x18005c92f  lea     rcx, [rbp+410h+szVolumePathName]; void *
0x18005c933  call    memset_0
0x18005c938  mov     r8d, ebx; Size
0x18005c93b  xor     edx, edx; Val
0x18005c93d  lea     rcx, [rbp+410h+szVolumeName]; void *
0x18005c944  call    memset_0
0x18005c949  xorps   xmm0, xmm0
0x18005c94c  xor     eax, eax
0x18005c94e  movups  xmmword ptr [rbp+410h+FileSystemNameBuffer], xmm0
0x18005c952  movups  [rbp+410h+var_480], xmm0
0x18005c956  movups  [rbp+410h+var_470], xmm0
0x18005c95a  mov     [rbp+410h+var_460], ax
0x18005c95e  test    rsi, rsi
0x18005c961  jz      loc_18005CAF6
0x18005c967  mov     [rsp+510h+var_4C8], eax
0x18005c96b  lea     eax, [rbx-5]
0x18005c96e  mov     [rsp+510h+var_4C4], ax
0x18005c973  xor     edi, edi
0x18005c975  lea     r13d, [rbx+0Dh]
0x18005c979  cmp     edi, [rsi+18h]
0x18005c97c  jnb     loc_18005CAD5
0x18005c982  lea     rcx, [rdi+rdi*2]
0x18005c986  mov     rax, [rsi+20h]
0x18005c98a  lea     r14, [rax+rcx*8]
0x18005c98e  mov     rdx, r14; struct _SD_BACKUP_ROOT *
0x18005c991  mov     rcx, r15; this
0x18005c994  call    ?_AddRulesByName@CSdBackupConfigImpl@@AEAAJPEAU_SD_BACKUP_ROOT@@@Z; CSdBackupConfigImpl::_AddRulesByName(_SD_BACKUP_ROOT *)
0x18005c999  mov     ebx, eax
0x18005c99b  mov     [rsp+510h+var_4C8], eax
0x18005c99f  test    eax, eax
0x18005c9a1  mov     eax, 20Ch
0x18005c9a6  js      loc_18005CACE
0x18005c9ac  mov     [rsp+510h+var_4C4], ax
0x18005c9b1  mov     r8d, 104h; cchBufferLength
0x18005c9b7  lea     rdx, [rbp+410h+szVolumePathName]; lpszVolumePathName
0x18005c9bb  mov     rcx, [r14]; lpszFileName
0x18005c9be  call    cs:__imp_GetVolumePathNameW
0x18005c9c5  nop     dword ptr [rax+rax+00h]
0x18005c9ca  test    eax, eax
0x18005c9cc  jz      loc_18005CABE
0x18005c9d2  mov     [rsp+510h+var_4C8], 0
0x18005c9da  mov     eax, 211h
0x18005c9df  mov     [rsp+510h+var_4C4], ax
0x18005c9e4  mov     r8d, 104h; cchBufferLength
0x18005c9ea  lea     rdx, [rbp+410h+szVolumeName]; lpszVolumeName
0x18005c9f1  lea     rcx, [rbp+410h+szVolumePathName]; lpszVolumeMountPoint
0x18005c9f5  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18005c9fc  nop     dword ptr [rax+rax+00h]
0x18005ca01  test    eax, eax
0x18005ca03  jz      loc_18005CAAC
0x18005ca09  mov     [rsp+510h+var_4C8], 0
0x18005ca11  mov     eax, 212h
0x18005ca16  mov     [rsp+510h+var_4C4], ax
0x18005ca1b  mov     [rsp+510h+nFileSystemNameSize], 19h; nFileSystemNameSize
0x18005ca23  lea     rax, [rbp+410h+FileSystemNameBuffer]
0x18005ca27  mov     [rsp+510h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18005ca2c  lea     rax, [rsp+510h+FileSystemFlags]
0x18005ca31  mov     [rsp+510h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18005ca36  mov     [rsp+510h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x18005ca3f  xor     r9d, r9d; lpVolumeSerialNumber
0x18005ca42  xor     r8d, r8d; nVolumeNameSize
0x18005ca45  xor     edx, edx; lpVolumeNameBuffer
0x18005ca47  lea     rcx, [rbp+410h+szVolumeName]; lpRootPathName
0x18005ca4e  call    cs:__imp_GetVolumeInformationW
0x18005ca55  nop     dword ptr [rax+rax+00h]
0x18005ca5a  test    eax, eax
0x18005ca5c  jz      short loc_18005CA9A
0x18005ca5e  mov     eax, 213h
0x18005ca63  mov     [rsp+510h+var_4C4], ax
0x18005ca68  lea     rdx, aNtfs; "NTFS"
0x18005ca6f  lea     rcx, [rbp+410h+FileSystemNameBuffer]; String1
0x18005ca73  call    wcscmp_0
0x18005ca78  test    eax, eax
0x18005ca7a  jnz     short loc_18005CA8D
0x18005ca7c  mov     [rsp+510h+var_4C8], eax
0x18005ca80  mov     [rsp+510h+var_4C4], r13w
0x18005ca86  inc     edi
0x18005ca88  jmp     loc_18005C979
0x18005ca8d  mov     ebx, 81000002h
0x18005ca92  mov     [rsp+510h+var_4C2], r13w
0x18005ca98  jmp     short loc_18005CB05
0x18005ca9a  call    GetLastFailureAsHRESULT
0x18005ca9f  mov     ebx, eax
0x18005caa1  mov     [rsp+510h+var_4C8], eax
0x18005caa5  mov     eax, 213h
0x18005caaa  jmp     short loc_18005CACE
0x18005caac  call    GetLastFailureAsHRESULT
0x18005cab1  mov     ebx, eax
0x18005cab3  mov     [rsp+510h+var_4C8], eax
0x18005cab7  mov     eax, 212h
0x18005cabc  jmp     short loc_18005CACE
0x18005cabe  call    GetLastFailureAsHRESULT
0x18005cac3  mov     ebx, eax
0x18005cac5  mov     [rsp+510h+var_4C8], eax
0x18005cac9  mov     eax, 211h
0x18005cace  mov     [rsp+510h+var_4C2], ax
0x18005cad3  jmp     short loc_18005CB09
0x18005cad5  mov     rdx, rsi; struct _SD_BACKUP_CONFIG *
0x18005cad8  mov     rcx, r15; this
0x18005cadb  call    ?_WriteConfigHelper@CSdBackupConfigImpl@@AEAAJPEBU_SD_BACKUP_CONFIG@@@Z; CSdBackupConfigImpl::_WriteConfigHelper(_SD_BACKUP_CONFIG const *)
0x18005cae0  mov     ebx, eax
0x18005cae2  mov     [rsp+510h+var_4C8], eax
0x18005cae6  test    eax, eax
0x18005cae8  mov     eax, 21Bh
0x18005caed  js      short loc_18005CACE
0x18005caef  mov     [rsp+510h+var_4C4], ax
0x18005caf4  jmp     short loc_18005CB09
0x18005caf6  mov     ebx, 80070057h
0x18005cafb  mov     eax, 203h
0x18005cb00  mov     [rsp+510h+var_4C2], ax
0x18005cb05  mov     [rsp+510h+var_4C8], ebx
0x18005cb09  lea     rcx, [rsp+510h+var_4C8]; this
0x18005cb0e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005cb13  mov     eax, ebx
0x18005cb15  mov     rcx, [rbp+410h+var_30]
0x18005cb1c  xor     rcx, rsp; StackCookie
0x18005cb1f  call    __security_check_cookie
0x18005cb24  lea     r11, [rsp+510h+var_20]
0x18005cb2c  mov     rbx, [r11+40h]
0x18005cb30  mov     rsi, [r11+48h]
0x18005cb34  mov     rsp, r11
0x18005cb37  pop     r15
0x18005cb39  pop     r14
0x18005cb3b  pop     r13
0x18005cb3d  pop     rdi
0x18005cb3e  pop     rbp
0x18005cb3f  retn
```
