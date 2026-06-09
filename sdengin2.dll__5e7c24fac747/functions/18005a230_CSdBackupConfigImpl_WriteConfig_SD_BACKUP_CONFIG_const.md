# CSdBackupConfigImpl::_WriteConfig(_SD_BACKUP_CONFIG const *)

- ea: `0x18005a230`
- end: `0x18005a496`
- name: `?_WriteConfig@CSdBackupConfigImpl@@AEAAJPEBU_SD_BACKUP_CONFIG@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(CSdBackupConfigImpl *__hidden this, const struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config`

## callers

- `0x180057990`

## callees

- `0x1800584c4`
- `0x18005a230`
- `0x18005a49c`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c97da`
- `0x1800c97f2`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x18005a326`
- `KERNEL32!GetVolumePathNameW` at `0x18005a326`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18005a357`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18005a357`
- `KERNEL32!GetVolumeInformationW` at `0x18005a3aa`
- `KERNEL32!GetVolumeInformationW` at `0x18005a3aa`

## string_xrefs

- `0x18005a274`: `CSdBackupConfigImpl::_WriteConfig`

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
0x18005a230  mov     [rsp-8+arg_10], rbx
0x18005a235  mov     [rsp-8+arg_18], rsi
0x18005a23a  push    rbp
0x18005a23b  push    rdi
0x18005a23c  push    r13
0x18005a23e  push    r14
0x18005a240  push    r15
0x18005a242  lea     rbp, [rsp-3F0h]
0x18005a24a  sub     rsp, 4F0h
0x18005a251  mov     rax, cs:__security_cookie
0x18005a258  xor     rax, rsp
0x18005a25b  mov     [rbp+410h+var_30], rax
0x18005a262  mov     rsi, rdx
0x18005a265  mov     r15, rcx
0x18005a268  mov     r9d, 1; unsigned __int16
0x18005a26e  mov     r8d, 1FAh; unsigned __int16
0x18005a274  lea     rdx, aCsdbackupconfi_21; "CSdBackupConfigImpl::_WriteConfig"
0x18005a27b  lea     rcx, [rsp+510h+var_4C8]; this
0x18005a280  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005a285  mov     [rsp+510h+FileSystemFlags], 0
0x18005a28d  mov     ebx, 208h
0x18005a292  mov     r8d, ebx; Size
0x18005a295  xor     edx, edx; Val
0x18005a297  lea     rcx, [rbp+410h+szVolumePathName]; void *
0x18005a29b  call    memset_0
0x18005a2a0  mov     r8d, ebx; Size
0x18005a2a3  xor     edx, edx; Val
0x18005a2a5  lea     rcx, [rbp+410h+szVolumeName]; void *
0x18005a2ac  call    memset_0
0x18005a2b1  xorps   xmm0, xmm0
0x18005a2b4  xor     eax, eax
0x18005a2b6  movups  xmmword ptr [rbp+410h+FileSystemNameBuffer], xmm0
0x18005a2ba  movups  [rbp+410h+var_480], xmm0
0x18005a2be  movups  [rbp+410h+var_470], xmm0
0x18005a2c2  mov     [rbp+410h+var_460], ax
0x18005a2c6  test    rsi, rsi
0x18005a2c9  jz      loc_18005A44C
0x18005a2cf  mov     [rsp+510h+var_4C8], eax
0x18005a2d3  lea     eax, [rbx-5]
0x18005a2d6  mov     [rsp+510h+var_4C4], ax
0x18005a2db  xor     edi, edi
0x18005a2dd  lea     r13d, [rbx+0Dh]
0x18005a2e1  cmp     edi, [rsi+18h]
0x18005a2e4  jnb     loc_18005A42B
0x18005a2ea  lea     rcx, [rdi+rdi*2]
0x18005a2ee  mov     rax, [rsi+20h]
0x18005a2f2  lea     r14, [rax+rcx*8]
0x18005a2f6  mov     rdx, r14; struct _SD_BACKUP_ROOT *
0x18005a2f9  mov     rcx, r15; this
0x18005a2fc  call    ?_AddRulesByName@CSdBackupConfigImpl@@AEAAJPEAU_SD_BACKUP_ROOT@@@Z; CSdBackupConfigImpl::_AddRulesByName(_SD_BACKUP_ROOT *)
0x18005a301  mov     ebx, eax
0x18005a303  mov     [rsp+510h+var_4C8], eax
0x18005a307  test    eax, eax
0x18005a309  mov     eax, 20Ch
0x18005a30e  js      loc_18005A424
0x18005a314  mov     [rsp+510h+var_4C4], ax
0x18005a319  mov     r8d, 104h; cchBufferLength
0x18005a31f  lea     rdx, [rbp+410h+szVolumePathName]; lpszVolumePathName
0x18005a323  mov     rcx, [r14]; lpszFileName
0x18005a326  call    cs:__imp_GetVolumePathNameW
0x18005a32c  test    eax, eax
0x18005a32e  jz      loc_18005A414
0x18005a334  mov     [rsp+510h+var_4C8], 0
0x18005a33c  mov     eax, 211h
0x18005a341  mov     [rsp+510h+var_4C4], ax
0x18005a346  mov     r8d, 104h; cchBufferLength
0x18005a34c  lea     rdx, [rbp+410h+szVolumeName]; lpszVolumeName
0x18005a353  lea     rcx, [rbp+410h+szVolumePathName]; lpszVolumeMountPoint
0x18005a357  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18005a35d  test    eax, eax
0x18005a35f  jz      loc_18005A402
0x18005a365  mov     [rsp+510h+var_4C8], 0
0x18005a36d  mov     eax, 212h
0x18005a372  mov     [rsp+510h+var_4C4], ax
0x18005a377  mov     [rsp+510h+nFileSystemNameSize], 19h; nFileSystemNameSize
0x18005a37f  lea     rax, [rbp+410h+FileSystemNameBuffer]
0x18005a383  mov     [rsp+510h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18005a388  lea     rax, [rsp+510h+FileSystemFlags]
0x18005a38d  mov     [rsp+510h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18005a392  mov     [rsp+510h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x18005a39b  xor     r9d, r9d; lpVolumeSerialNumber
0x18005a39e  xor     r8d, r8d; nVolumeNameSize
0x18005a3a1  xor     edx, edx; lpVolumeNameBuffer
0x18005a3a3  lea     rcx, [rbp+410h+szVolumeName]; lpRootPathName
0x18005a3aa  call    cs:__imp_GetVolumeInformationW
0x18005a3b0  test    eax, eax
0x18005a3b2  jz      short loc_18005A3F0
0x18005a3b4  mov     eax, 213h
0x18005a3b9  mov     [rsp+510h+var_4C4], ax
0x18005a3be  lea     rdx, aNtfs; "NTFS"
0x18005a3c5  lea     rcx, [rbp+410h+FileSystemNameBuffer]; String1
0x18005a3c9  call    wcscmp_0
0x18005a3ce  test    eax, eax
0x18005a3d0  jnz     short loc_18005A3E3
0x18005a3d2  mov     [rsp+510h+var_4C8], eax
0x18005a3d6  mov     [rsp+510h+var_4C4], r13w
0x18005a3dc  inc     edi
0x18005a3de  jmp     loc_18005A2E1
0x18005a3e3  mov     ebx, 81000002h
0x18005a3e8  mov     [rsp+510h+var_4C2], r13w
0x18005a3ee  jmp     short loc_18005A45B
0x18005a3f0  call    GetLastFailureAsHRESULT
0x18005a3f5  mov     ebx, eax
0x18005a3f7  mov     [rsp+510h+var_4C8], eax
0x18005a3fb  mov     eax, 213h
0x18005a400  jmp     short loc_18005A424
0x18005a402  call    GetLastFailureAsHRESULT
0x18005a407  mov     ebx, eax
0x18005a409  mov     [rsp+510h+var_4C8], eax
0x18005a40d  mov     eax, 212h
0x18005a412  jmp     short loc_18005A424
0x18005a414  call    GetLastFailureAsHRESULT
0x18005a419  mov     ebx, eax
0x18005a41b  mov     [rsp+510h+var_4C8], eax
0x18005a41f  mov     eax, 211h
0x18005a424  mov     [rsp+510h+var_4C2], ax
0x18005a429  jmp     short loc_18005A45F
0x18005a42b  mov     rdx, rsi; struct _SD_BACKUP_CONFIG *
0x18005a42e  mov     rcx, r15; this
0x18005a431  call    ?_WriteConfigHelper@CSdBackupConfigImpl@@AEAAJPEBU_SD_BACKUP_CONFIG@@@Z; CSdBackupConfigImpl::_WriteConfigHelper(_SD_BACKUP_CONFIG const *)
0x18005a436  mov     ebx, eax
0x18005a438  mov     [rsp+510h+var_4C8], eax
0x18005a43c  test    eax, eax
0x18005a43e  mov     eax, 21Bh
0x18005a443  js      short loc_18005A424
0x18005a445  mov     [rsp+510h+var_4C4], ax
0x18005a44a  jmp     short loc_18005A45F
0x18005a44c  mov     ebx, 80070057h
0x18005a451  mov     eax, 203h
0x18005a456  mov     [rsp+510h+var_4C2], ax
0x18005a45b  mov     [rsp+510h+var_4C8], ebx
0x18005a45f  lea     rcx, [rsp+510h+var_4C8]; this
0x18005a464  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005a469  mov     eax, ebx
0x18005a46b  mov     rcx, [rbp+410h+var_30]
0x18005a472  xor     rcx, rsp; StackCookie
0x18005a475  call    __security_check_cookie
0x18005a47a  lea     r11, [rsp+510h+var_20]
0x18005a482  mov     rbx, [r11+40h]
0x18005a486  mov     rsi, [r11+48h]
0x18005a48a  mov     rsp, r11
0x18005a48d  pop     r15
0x18005a48f  pop     r14
0x18005a491  pop     r13
0x18005a493  pop     rdi
0x18005a494  pop     rbp
0x18005a495  retn
```
