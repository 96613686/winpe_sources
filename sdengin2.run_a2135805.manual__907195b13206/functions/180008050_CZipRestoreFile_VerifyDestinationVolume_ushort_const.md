# CZipRestoreFile::_VerifyDestinationVolume(ushort const *)

- ea: `0x180008050`
- end: `0x180008368`
- name: `?_VerifyDestinationVolume@CZipRestoreFile@@AEAAJPEBG@Z`
- size: `792`
- prototype: `int(CZipRestoreFile *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x1800052c0`
- `0x1800054c0`
- `0x180005780`

## callees

- `0x180008050`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009e924`
- `0x1800cf56a`
- `0x1800cf582`
- `0x1800cf58e`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000810a`
- `msvcrt!wcsrchr` at `0x18000810a`
- `KERNEL32!GetVolumePathNameW` at `0x180008190`
- `KERNEL32!GetVolumePathNameW` at `0x180008190`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800081d8`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800081d8`
- `KERNEL32!GetDriveTypeW` at `0x180008213`
- `KERNEL32!GetDriveTypeW` at `0x180008213`
- `KERNEL32!GetVolumeInformationW` at `0x180008276`
- `KERNEL32!GetVolumeInformationW` at `0x180008276`

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

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v17,
    "CZipRestoreFile::_VerifyDestinationVolume",
    0x358u,
    1u);
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
0x180008050  mov     [rsp-8+arg_10], rbx
0x180008055  push    rbp
0x180008056  push    rsi
0x180008057  push    rdi
0x180008058  lea     rbp, [rsp-5C0h]
0x180008060  sub     rsp, 6C0h
0x180008067  mov     rax, cs:__security_cookie
0x18000806e  xor     rax, rsp
0x180008071  mov     [rbp+5D0h+var_20], rax
0x180008078  mov     rbx, rdx
0x18000807b  mov     rsi, rcx
0x18000807e  mov     r9d, 1; unsigned __int16
0x180008084  mov     r8d, 358h; unsigned __int16
0x18000808a  lea     rdx, aCziprestorefil_14; "CZipRestoreFile::_VerifyDestinationVolu"...
0x180008091  lea     rcx, [rsp+6D0h+var_688]; this
0x180008096  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000809b  mov     [rsp+6D0h+FileSystemFlags], 0
0x1800080a3  mov     edi, 208h
0x1800080a8  mov     r8d, edi; Size
0x1800080ab  xor     edx, edx; Val
0x1800080ad  lea     rcx, [rbp+5D0h+szVolumePathName]; void *
0x1800080b1  call    memset_0
0x1800080b6  mov     r8d, edi; Size
0x1800080b9  xor     edx, edx; Val
0x1800080bb  lea     rcx, [rbp+5D0h+szVolumeName]; void *
0x1800080c2  call    memset_0
0x1800080c7  mov     r8d, edi; Size
0x1800080ca  xor     edx, edx; Val
0x1800080cc  lea     rcx, [rbp+5D0h+FileSystemNameBuffer]; void *
0x1800080d3  call    memset_0
0x1800080d8  mov     eax, 361h
0x1800080dd  test    rbx, rbx
0x1800080e0  jnz     short loc_1800080F5
0x1800080e2  mov     ebx, 80070057h
0x1800080e7  mov     [rsp+6D0h+var_688], ebx
0x1800080eb  mov     [rsp+6D0h+var_682], ax
0x1800080f0  jmp     loc_180008339
0x1800080f5  mov     [rsp+6D0h+var_688], 0
0x1800080fd  mov     [rsp+6D0h+var_684], ax
0x180008102  mov     edx, 5Ch ; '\'; Ch
0x180008107  mov     rcx, rbx; Str
0x18000810a  call    cs:__imp_wcsrchr
0x180008111  nop     dword ptr [rax+rax+00h]
0x180008116  mov     ecx, 36Ah
0x18000811b  test    rax, rax
0x18000811e  jnz     short loc_180008133
0x180008120  mov     ebx, 80070057h
0x180008125  mov     [rsp+6D0h+var_688], ebx
0x180008129  mov     [rsp+6D0h+var_682], cx
0x18000812e  jmp     loc_180008339
0x180008133  mov     [rsp+6D0h+var_684], cx
0x180008138  sub     rax, rbx
0x18000813b  sar     rax, 1
0x18000813e  mov     ecx, 36Bh
0x180008143  cmp     rax, 10000000h
0x180008149  jge     short loc_180008120
0x18000814b  mov     [rsp+6D0h+var_688], 0
0x180008153  mov     [rsp+6D0h+var_684], cx
0x180008158  lea     edi, [rax+1]
0x18000815b  cmp     edi, [rsi+88h]
0x180008161  jnz     short loc_180008183
0x180008163  mov     r8d, edi; MaxCount
0x180008166  mov     rdx, rbx; String2
0x180008169  mov     rcx, [rsi+80h]; String1
0x180008170  call    wcsncmp_0
0x180008175  test    eax, eax
0x180008177  jnz     short loc_180008183
0x180008179  mov     eax, 379h
0x18000817e  jmp     loc_180008332
0x180008183  mov     r8d, 104h; cchBufferLength
0x180008189  lea     rdx, [rbp+5D0h+szVolumePathName]; lpszVolumePathName
0x18000818d  mov     rcx, rbx; lpszFileName
0x180008190  call    cs:__imp_GetVolumePathNameW
0x180008197  nop     dword ptr [rax+rax+00h]
0x18000819c  test    eax, eax
0x18000819e  jnz     short loc_1800081B5
0x1800081a0  call    GetLastFailureAsHRESULT
0x1800081a5  mov     ebx, eax
0x1800081a7  mov     [rsp+6D0h+var_688], eax
0x1800081ab  mov     eax, 380h
0x1800081b0  jmp     loc_1800080EB
0x1800081b5  mov     [rsp+6D0h+var_688], 0
0x1800081bd  mov     eax, 380h
0x1800081c2  mov     [rsp+6D0h+var_684], ax
0x1800081c7  mov     r8d, 104h; cchBufferLength
0x1800081cd  lea     rdx, [rbp+5D0h+szVolumeName]; lpszVolumeName
0x1800081d4  lea     rcx, [rbp+5D0h+szVolumePathName]; lpszVolumeMountPoint
0x1800081d8  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800081df  nop     dword ptr [rax+rax+00h]
0x1800081e4  test    eax, eax
0x1800081e6  jnz     short loc_1800081FD
0x1800081e8  call    GetLastFailureAsHRESULT
0x1800081ed  mov     ebx, eax
0x1800081ef  mov     [rsp+6D0h+var_688], eax
0x1800081f3  mov     eax, 381h
0x1800081f8  jmp     loc_1800080EB
0x1800081fd  mov     [rsp+6D0h+var_688], 0
0x180008205  mov     eax, 381h
0x18000820a  mov     [rsp+6D0h+var_684], ax
0x18000820f  lea     rcx, [rbp+5D0h+szVolumePathName]; lpRootPathName
0x180008213  call    cs:__imp_GetDriveTypeW
0x18000821a  nop     dword ptr [rax+rax+00h]
0x18000821f  cmp     eax, 3
0x180008222  mov     eax, 388h
0x180008227  jz      short loc_180008233
0x180008229  mov     ebx, 810000FBh
0x18000822e  jmp     loc_1800080E7
0x180008233  mov     [rsp+6D0h+var_688], 0
0x18000823b  mov     [rsp+6D0h+var_684], ax
0x180008240  mov     [rsp+6D0h+nFileSystemNameSize], 104h; nFileSystemNameSize
0x180008248  lea     rax, [rbp+5D0h+FileSystemNameBuffer]
0x18000824f  mov     [rsp+6D0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x180008254  lea     rax, [rsp+6D0h+FileSystemFlags]
0x180008259  mov     [rsp+6D0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18000825e  mov     [rsp+6D0h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x180008267  xor     r9d, r9d; lpVolumeSerialNumber
0x18000826a  xor     r8d, r8d; nVolumeNameSize
0x18000826d  xor     edx, edx; lpVolumeNameBuffer
0x18000826f  lea     rcx, [rbp+5D0h+szVolumeName]; lpRootPathName
0x180008276  call    cs:__imp_GetVolumeInformationW
0x18000827d  nop     dword ptr [rax+rax+00h]
0x180008282  test    eax, eax
0x180008284  jnz     short loc_18000829B
0x180008286  call    GetLastFailureAsHRESULT
0x18000828b  mov     ebx, eax
0x18000828d  mov     [rsp+6D0h+var_688], eax
0x180008291  mov     eax, 390h
0x180008296  jmp     loc_1800080EB
0x18000829b  mov     eax, 390h
0x1800082a0  mov     [rsp+6D0h+var_684], ax
0x1800082a5  mov     eax, 392h
0x1800082aa  test    [rsp+6D0h+FileSystemFlags], 40000h
0x1800082b2  jz      loc_180008229
0x1800082b8  mov     [rsp+6D0h+var_684], ax
0x1800082bd  mov     eax, 393h
0x1800082c2  test    byte ptr [rsp+6D0h+FileSystemFlags], 8
0x1800082c7  jz      loc_180008229
0x1800082cd  mov     [rsp+6D0h+var_684], ax
0x1800082d2  lea     rdx, aNtfs; "NTFS"
0x1800082d9  lea     rcx, [rbp+5D0h+FileSystemNameBuffer]; String1
0x1800082e0  call    wcscmp_0
0x1800082e5  test    eax, eax
0x1800082e7  mov     eax, 394h
0x1800082ec  jnz     loc_180008229
0x1800082f2  mov     [rsp+6D0h+var_688], 0
0x1800082fa  mov     [rsp+6D0h+var_684], ax
0x1800082ff  mov     r8d, edi; unsigned int
0x180008302  mov     rdx, rbx; unsigned __int16 *
0x180008305  lea     rcx, [rsi+80h]; this
0x18000830c  call    ?Set@CBsString@@QEAAJPEBGK@Z; CBsString::Set(ushort const *,ulong)
0x180008311  mov     ebx, eax
0x180008313  mov     [rsp+6D0h+var_688], eax
0x180008317  test    eax, eax
0x180008319  jns     short loc_180008325
0x18000831b  mov     eax, 399h
0x180008320  jmp     loc_1800080EB
0x180008325  mov     [rsp+6D0h+var_688], 0
0x18000832d  mov     eax, 39Bh
0x180008332  xor     ebx, ebx
0x180008334  mov     [rsp+6D0h+var_684], ax
0x180008339  lea     rcx, [rsp+6D0h+var_688]; this
0x18000833e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180008343  mov     eax, ebx
0x180008345  mov     rcx, [rbp+5D0h+var_20]
0x18000834c  xor     rcx, rsp; StackCookie
0x18000834f  call    __security_check_cookie
0x180008354  mov     rbx, [rsp+6D0h+arg_10]
0x18000835c  add     rsp, 6C0h
0x180008363  pop     rdi
0x180008364  pop     rsi
0x180008365  pop     rbp
0x180008366  retn
```
