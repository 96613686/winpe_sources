# CZipRestoreFile::_VerifyDestinationVolume(ushort const *)

- ea: `0x180007ed8`
- end: `0x1800081d1`
- name: `?_VerifyDestinationVolume@CZipRestoreFile@@AEAAJPEBG@Z`
- size: `761`
- prototype: `int(CZipRestoreFile *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x180005130`
- `0x180005330`
- `0x1800055f0`

## callees

- `0x180007ed8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009a26c`
- `0x1800c97da`
- `0x1800c97f2`
- `0x1800c97fe`
- `0x1800c9830`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180007f92`
- `msvcrt!wcsrchr` at `0x180007f92`
- `KERNEL32!GetVolumePathNameW` at `0x180008012`
- `KERNEL32!GetVolumePathNameW` at `0x180008012`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180008054`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180008054`
- `KERNEL32!GetDriveTypeW` at `0x180008089`
- `KERNEL32!GetDriveTypeW` at `0x180008089`
- `KERNEL32!GetVolumeInformationW` at `0x1800080e6`
- `KERNEL32!GetVolumeInformationW` at `0x1800080e6`

## pseudocode

```c
__int64 __fastcall CZipRestoreFile::_VerifyDestinationVolume(CZipRestoreFile *this, const unsigned __int16 *a2)
{
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  wchar_t *v6; // rax
  __int16 v7; // cx
  __int64 v8; // rax
  unsigned int v9; // edi
  __int16 v10; // ax
  __int64 v11; // rcx
  __int64 v12; // rcx
  bool v13; // zf
  __int64 v14; // rcx
  DWORD FileSystemFlags; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v18; // [rsp+4Ch] [rbp-B4h]
  __int16 v19; // [rsp+4Eh] [rbp-B2h]
  WCHAR szVolumePathName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szVolumeName[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR FileSystemNameBuffer[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CZipRestoreFile::_VerifyDestinationVolume", 856, 1);
  FileSystemFlags = 0;
  memset_0(szVolumePathName, 0, 0x208u);
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(FileSystemNameBuffer, 0, 0x208u);
  v4 = 865;
  if ( a2 )
  {
    v17 = 0;
    v18 = 865;
    v6 = wcsrchr(a2, 0x5Cu);
    v7 = 874;
    if ( !v6 || (v18 = 874, v8 = v6 - a2, v7 = 875, v8 >= 0x10000000) )
    {
      LastFailureAsHRESULT = -2147024809;
      v17 = -2147024809;
      v19 = v7;
      goto LABEL_26;
    }
    v17 = 0;
    v18 = 875;
    v9 = v8 + 1;
    if ( (_DWORD)v8 + 1 == *((_DWORD *)this + 34) && !wcsncmp_0(*((const wchar_t **)this + 16), a2, v9) )
    {
      v10 = 889;
    }
    else
    {
      if ( !GetVolumePathNameW(a2, szVolumePathName, 0x104u) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
        v17 = LastFailureAsHRESULT;
        v4 = 896;
        goto LABEL_4;
      }
      v17 = 0;
      v18 = 896;
      if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
        v17 = LastFailureAsHRESULT;
        v4 = 897;
        goto LABEL_4;
      }
      v17 = 0;
      v18 = 897;
      v13 = GetDriveTypeW(szVolumePathName) == 3;
      v4 = 904;
      if ( !v13 )
        goto LABEL_16;
      v17 = 0;
      v18 = 904;
      if ( !GetVolumeInformationW(szVolumeName, 0, 0, 0, 0, &FileSystemFlags, FileSystemNameBuffer, 0x104u) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
        v17 = LastFailureAsHRESULT;
        v4 = 912;
        goto LABEL_4;
      }
      v18 = 912;
      v4 = 914;
      if ( (FileSystemFlags & 0x40000) == 0
        || (v18 = 914, v4 = 915, (FileSystemFlags & 8) == 0)
        || (v18 = 915, v13 = wcscmp_0(FileSystemNameBuffer, L"NTFS") == 0, v4 = 916, !v13) )
      {
LABEL_16:
        LastFailureAsHRESULT = -2130706181;
        goto LABEL_3;
      }
      v17 = 0;
      v18 = 916;
      LastFailureAsHRESULT = CBsString::Set((CZipRestoreFile *)((char *)this + 128), a2, v9);
      v17 = LastFailureAsHRESULT;
      if ( LastFailureAsHRESULT < 0 )
      {
        v4 = 921;
        goto LABEL_4;
      }
      v17 = 0;
      v10 = 923;
    }
    LastFailureAsHRESULT = 0;
    v18 = v10;
    goto LABEL_26;
  }
  LastFailureAsHRESULT = -2147024809;
LABEL_3:
  v17 = LastFailureAsHRESULT;
LABEL_4:
  v19 = v4;
LABEL_26:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180007ed8  mov     [rsp-8+arg_10], rbx
0x180007edd  push    rbp
0x180007ede  push    rsi
0x180007edf  push    rdi
0x180007ee0  lea     rbp, [rsp-5C0h]
0x180007ee8  sub     rsp, 6C0h
0x180007eef  mov     rax, cs:__security_cookie
0x180007ef6  xor     rax, rsp
0x180007ef9  mov     [rbp+5D0h+var_20], rax
0x180007f00  mov     rbx, rdx
0x180007f03  mov     rsi, rcx
0x180007f06  mov     r9d, 1; unsigned __int16
0x180007f0c  mov     r8d, 358h; unsigned __int16
0x180007f12  lea     rdx, aCziprestorefil_14; "CZipRestoreFile::_VerifyDestinationVolu"...
0x180007f19  lea     rcx, [rsp+6D0h+var_688]; this
0x180007f1e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180007f23  mov     [rsp+6D0h+FileSystemFlags], 0
0x180007f2b  mov     edi, 208h
0x180007f30  mov     r8d, edi; Size
0x180007f33  xor     edx, edx; Val
0x180007f35  lea     rcx, [rbp+5D0h+szVolumePathName]; void *
0x180007f39  call    memset_0
0x180007f3e  mov     r8d, edi; Size
0x180007f41  xor     edx, edx; Val
0x180007f43  lea     rcx, [rbp+5D0h+szVolumeName]; void *
0x180007f4a  call    memset_0
0x180007f4f  mov     r8d, edi; Size
0x180007f52  xor     edx, edx; Val
0x180007f54  lea     rcx, [rbp+5D0h+FileSystemNameBuffer]; void *
0x180007f5b  call    memset_0
0x180007f60  mov     eax, 361h
0x180007f65  test    rbx, rbx
0x180007f68  jnz     short loc_180007F7D
0x180007f6a  mov     ebx, 80070057h
0x180007f6f  mov     [rsp+6D0h+var_688], ebx
0x180007f73  mov     [rsp+6D0h+var_682], ax
0x180007f78  jmp     loc_1800081A3
0x180007f7d  mov     [rsp+6D0h+var_688], 0
0x180007f85  mov     [rsp+6D0h+var_684], ax
0x180007f8a  mov     edx, 5Ch ; '\'; Ch
0x180007f8f  mov     rcx, rbx; Str
0x180007f92  call    cs:__imp_wcsrchr
0x180007f98  mov     ecx, 36Ah
0x180007f9d  test    rax, rax
0x180007fa0  jnz     short loc_180007FB5
0x180007fa2  mov     ebx, 80070057h
0x180007fa7  mov     [rsp+6D0h+var_688], ebx
0x180007fab  mov     [rsp+6D0h+var_682], cx
0x180007fb0  jmp     loc_1800081A3
0x180007fb5  mov     [rsp+6D0h+var_684], cx
0x180007fba  sub     rax, rbx
0x180007fbd  sar     rax, 1
0x180007fc0  mov     ecx, 36Bh
0x180007fc5  cmp     rax, 10000000h
0x180007fcb  jge     short loc_180007FA2
0x180007fcd  mov     [rsp+6D0h+var_688], 0
0x180007fd5  mov     [rsp+6D0h+var_684], cx
0x180007fda  lea     edi, [rax+1]
0x180007fdd  cmp     edi, [rsi+88h]
0x180007fe3  jnz     short loc_180008005
0x180007fe5  mov     r8d, edi; MaxCount
0x180007fe8  mov     rdx, rbx; String2
0x180007feb  mov     rcx, [rsi+80h]; String1
0x180007ff2  call    wcsncmp_0
0x180007ff7  test    eax, eax
0x180007ff9  jnz     short loc_180008005
0x180007ffb  mov     eax, 379h
0x180008000  jmp     loc_18000819C
0x180008005  mov     r8d, 104h; cchBufferLength
0x18000800b  lea     rdx, [rbp+5D0h+szVolumePathName]; lpszVolumePathName
0x18000800f  mov     rcx, rbx; lpszFileName
0x180008012  call    cs:__imp_GetVolumePathNameW
0x180008018  test    eax, eax
0x18000801a  jnz     short loc_180008031
0x18000801c  call    GetLastFailureAsHRESULT
0x180008021  mov     ebx, eax
0x180008023  mov     [rsp+6D0h+var_688], eax
0x180008027  mov     eax, 380h
0x18000802c  jmp     loc_180007F73
0x180008031  mov     [rsp+6D0h+var_688], 0
0x180008039  mov     eax, 380h
0x18000803e  mov     [rsp+6D0h+var_684], ax
0x180008043  mov     r8d, 104h; cchBufferLength
0x180008049  lea     rdx, [rbp+5D0h+szVolumeName]; lpszVolumeName
0x180008050  lea     rcx, [rbp+5D0h+szVolumePathName]; lpszVolumeMountPoint
0x180008054  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000805a  test    eax, eax
0x18000805c  jnz     short loc_180008073
0x18000805e  call    GetLastFailureAsHRESULT
0x180008063  mov     ebx, eax
0x180008065  mov     [rsp+6D0h+var_688], eax
0x180008069  mov     eax, 381h
0x18000806e  jmp     loc_180007F73
0x180008073  mov     [rsp+6D0h+var_688], 0
0x18000807b  mov     eax, 381h
0x180008080  mov     [rsp+6D0h+var_684], ax
0x180008085  lea     rcx, [rbp+5D0h+szVolumePathName]; lpRootPathName
0x180008089  call    cs:__imp_GetDriveTypeW
0x18000808f  cmp     eax, 3
0x180008092  mov     eax, 388h
0x180008097  jz      short loc_1800080A3
0x180008099  mov     ebx, 810000FBh
0x18000809e  jmp     loc_180007F6F
0x1800080a3  mov     [rsp+6D0h+var_688], 0
0x1800080ab  mov     [rsp+6D0h+var_684], ax
0x1800080b0  mov     [rsp+6D0h+nFileSystemNameSize], 104h; nFileSystemNameSize
0x1800080b8  lea     rax, [rbp+5D0h+FileSystemNameBuffer]
0x1800080bf  mov     [rsp+6D0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x1800080c4  lea     rax, [rsp+6D0h+FileSystemFlags]
0x1800080c9  mov     [rsp+6D0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1800080ce  mov     [rsp+6D0h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x1800080d7  xor     r9d, r9d; lpVolumeSerialNumber
0x1800080da  xor     r8d, r8d; nVolumeNameSize
0x1800080dd  xor     edx, edx; lpVolumeNameBuffer
0x1800080df  lea     rcx, [rbp+5D0h+szVolumeName]; lpRootPathName
0x1800080e6  call    cs:__imp_GetVolumeInformationW
0x1800080ec  test    eax, eax
0x1800080ee  jnz     short loc_180008105
0x1800080f0  call    GetLastFailureAsHRESULT
0x1800080f5  mov     ebx, eax
0x1800080f7  mov     [rsp+6D0h+var_688], eax
0x1800080fb  mov     eax, 390h
0x180008100  jmp     loc_180007F73
0x180008105  mov     eax, 390h
0x18000810a  mov     [rsp+6D0h+var_684], ax
0x18000810f  mov     eax, 392h
0x180008114  test    [rsp+6D0h+FileSystemFlags], 40000h
0x18000811c  jz      loc_180008099
0x180008122  mov     [rsp+6D0h+var_684], ax
0x180008127  mov     eax, 393h
0x18000812c  test    byte ptr [rsp+6D0h+FileSystemFlags], 8
0x180008131  jz      loc_180008099
0x180008137  mov     [rsp+6D0h+var_684], ax
0x18000813c  lea     rdx, aNtfs; "NTFS"
0x180008143  lea     rcx, [rbp+5D0h+FileSystemNameBuffer]; String1
0x18000814a  call    wcscmp_0
0x18000814f  test    eax, eax
0x180008151  mov     eax, 394h
0x180008156  jnz     loc_180008099
0x18000815c  mov     [rsp+6D0h+var_688], 0
0x180008164  mov     [rsp+6D0h+var_684], ax
0x180008169  mov     r8d, edi; unsigned int
0x18000816c  mov     rdx, rbx; unsigned __int16 *
0x18000816f  lea     rcx, [rsi+80h]; this
0x180008176  call    ?Set@CBsString@@QEAAJPEBGK@Z; CBsString::Set(ushort const *,ulong)
0x18000817b  mov     ebx, eax
0x18000817d  mov     [rsp+6D0h+var_688], eax
0x180008181  test    eax, eax
0x180008183  jns     short loc_18000818F
0x180008185  mov     eax, 399h
0x18000818a  jmp     loc_180007F73
0x18000818f  mov     [rsp+6D0h+var_688], 0
0x180008197  mov     eax, 39Bh
0x18000819c  xor     ebx, ebx
0x18000819e  mov     [rsp+6D0h+var_684], ax
0x1800081a3  lea     rcx, [rsp+6D0h+var_688]; this
0x1800081a8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800081ad  mov     eax, ebx
0x1800081af  mov     rcx, [rbp+5D0h+var_20]
0x1800081b6  xor     rcx, rsp; StackCookie
0x1800081b9  call    __security_check_cookie
0x1800081be  mov     rbx, [rsp+6D0h+arg_10]
0x1800081c6  add     rsp, 6C0h
0x1800081cd  pop     rdi
0x1800081ce  pop     rsi
0x1800081cf  pop     rbp
0x1800081d0  retn
```
