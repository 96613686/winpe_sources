# CDlpActionLayoutUsb::GetDiskAndOffsetFromPath(ushort const *,int *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180019b00`
- end: `0x180019de1`
- name: `?GetDiskAndOffsetFromPath@CDlpActionLayoutUsb@@AEAAJPEBGPEAHPEA_K2@Z`
- size: `737`
- prototype: `int(CDlpActionLayoutUsb *__hidden this, const unsigned __int16 *, int *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x180026054`

## callees

- `0x180001df8`
- `0x18000aba4`
- `0x180012f5c`
- `0x180019b00`
- `0x18001fd60`
- `0x180039d44`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180019bea`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180019bea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d4b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180019c57`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180019c57`

## string_xrefs

- `0x180019d86`: `CDlpActionLayoutUsb::GetDiskAndOffsetFromPath`

## pseudocode

```c
__int64 __fastcall CDlpActionLayoutUsb::GetDiskAndOffsetFromPath(
        CDlpActionLayoutUsb *this,
        const unsigned __int16 *a2,
        int *a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5)
{
  int v5; // r15d
  __int64 v9; // rcx
  signed int v10; // ebx
  signed int LastError; // eax
  __int64 v12; // rcx
  signed int v13; // eax
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 *ExtentsFromVolumePath; // rax
  unsigned __int64 *v17; // rbx
  int v18; // ebp
  unsigned __int64 v19; // r14
  unsigned __int64 v20; // rsi
  HANDLE ProcessHeap; // rax
  signed int v22; // eax
  int v23; // eax
  int v25; // [rsp+20h] [rbp-498h]
  int v26; // [rsp+28h] [rbp-490h]
  WCHAR szVolumeName[264]; // [rsp+40h] [rbp-478h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+250h] [rbp-268h] BYREF

  v5 = 0;
  if ( !a2 )
  {
    v9 = *((_QWORD *)this + 11);
    v10 = -2147024809;
    if ( v9 )
    {
      v26 = -2147024809;
      v25 = 1657;
      goto LABEL_46;
    }
    goto LABEL_49;
  }
  if ( !a3 )
  {
    v9 = *((_QWORD *)this + 11);
    v10 = -2147024809;
    if ( !v9 )
      goto LABEL_49;
    v26 = -2147024809;
    v25 = 1658;
LABEL_46:
    v23 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v9,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpActionLayoutUsb::GetDiskAndOffsetFromPath",
            v25,
            v26);
    v12 = (unsigned int)v23;
    if ( v23 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v23);
    goto LABEL_48;
  }
  if ( !a4 )
  {
    v9 = *((_QWORD *)this + 11);
    v10 = -2147024809;
    if ( !v9 )
      goto LABEL_49;
    v26 = -2147024809;
    v25 = 1659;
    goto LABEL_46;
  }
  memset_0(szVolumePathName, 0, 0x208u);
  if ( !GetVolumePathNameW(a2, szVolumePathName, 0x104u) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v10 = -2147467259;
    }
    if ( !*((_QWORD *)this + 11) )
      goto LABEL_49;
    v12 = 0;
    if ( v10 < 0 )
    {
      v26 = v10;
      v25 = 1662;
LABEL_45:
      v9 = *((_QWORD *)this + 11);
      goto LABEL_46;
    }
    goto LABEL_48;
  }
  memset_0(szVolumeName, 0, 0x208u);
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    v13 = GetLastError();
    v10 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v10 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v10 = -2147467259;
    }
    if ( !*((_QWORD *)this + 11) )
      goto LABEL_49;
    v12 = 0;
    if ( v10 < 0 )
    {
      v26 = v10;
      v25 = 1665;
      goto LABEL_45;
    }
LABEL_48:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
    goto LABEL_49;
  }
  v14 = -1;
  do
    ++v14;
  while ( szVolumeName[v14] );
  if ( v14 && szVolumeName[v14 - 1] == 92 )
  {
    v15 = 2 * v14 - 2;
    if ( v15 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v15) = 0;
  }
  ExtentsFromVolumePath = (unsigned __int64 *)GetExtentsFromVolumePath(szVolumeName, 1);
  v17 = ExtentsFromVolumePath;
  if ( ExtentsFromVolumePath )
  {
    v18 = 0;
    v19 = 0;
    v20 = 0;
    if ( *(_DWORD *)ExtentsFromVolumePath )
    {
      v18 = *((_DWORD *)ExtentsFromVolumePath + 2);
      v5 = 1;
      v19 = ExtentsFromVolumePath[2];
      v20 = ExtentsFromVolumePath[3];
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v17);
    if ( v5 )
    {
      v10 = 0;
      *a3 = v18;
      *a4 = v19;
      if ( a5 )
        *a5 = v20;
      goto LABEL_49;
    }
  }
  v22 = GetLastError();
  v10 = v22;
  if ( v22 )
  {
    if ( v22 > 0 )
      v10 = (unsigned __int16)v22 | 0x80070000;
  }
  else
  {
    v10 = -2147467259;
  }
  if ( *((_QWORD *)this + 11) )
  {
    v12 = 0;
    if ( v10 < 0 )
    {
      v26 = v10;
      v25 = 1672;
      goto LABEL_45;
    }
    goto LABEL_48;
  }
LABEL_49:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019b00  push    rbx
0x180019b02  push    rbp
0x180019b03  push    rsi
0x180019b04  push    rdi
0x180019b05  push    r12
0x180019b07  push    r13
0x180019b09  push    r14
0x180019b0b  push    r15
0x180019b0d  sub     rsp, 478h
0x180019b14  mov     rax, cs:__security_cookie
0x180019b1b  xor     rax, rsp
0x180019b1e  mov     [rsp+4B8h+var_58], rax
0x180019b26  mov     r12, [rsp+4B8h+arg_20]
0x180019b2e  xor     r15d, r15d
0x180019b31  mov     rax, r9
0x180019b34  mov     r13, r8
0x180019b37  mov     [rsp+4B8h+var_488], rax
0x180019b3c  mov     rbx, rdx
0x180019b3f  mov     rdi, rcx
0x180019b42  test    rdx, rdx
0x180019b45  jnz     short loc_180019B6C
0x180019b47  mov     rcx, [rcx+58h]
0x180019b4b  mov     eax, 80070057h
0x180019b50  mov     ebx, eax
0x180019b52  test    rcx, rcx
0x180019b55  jz      loc_180019DAE
0x180019b5b  mov     [rsp+4B8h+var_490], eax
0x180019b5f  mov     [rsp+4B8h+var_498], 679h
0x180019b67  jmp     loc_180019D86
0x180019b6c  test    r13, r13
0x180019b6f  jnz     short loc_180019B96
0x180019b71  mov     rcx, [rcx+58h]
0x180019b75  mov     eax, 80070057h
0x180019b7a  mov     ebx, eax
0x180019b7c  test    rcx, rcx
0x180019b7f  jz      loc_180019DAE
0x180019b85  mov     [rsp+4B8h+var_490], eax
0x180019b89  mov     [rsp+4B8h+var_498], 67Ah
0x180019b91  jmp     loc_180019D86
0x180019b96  test    rax, rax
0x180019b99  jnz     short loc_180019BC0
0x180019b9b  mov     rcx, [rcx+58h]
0x180019b9f  mov     eax, 80070057h
0x180019ba4  mov     ebx, eax
0x180019ba6  test    rcx, rcx
0x180019ba9  jz      loc_180019DAE
0x180019baf  mov     [rsp+4B8h+var_490], eax
0x180019bb3  mov     [rsp+4B8h+var_498], 67Bh
0x180019bbb  jmp     loc_180019D86
0x180019bc0  mov     esi, 208h
0x180019bc5  lea     rcx, [rsp+4B8h+szVolumePathName]; void *
0x180019bcd  mov     r8d, esi; Size
0x180019bd0  xor     edx, edx; Val
0x180019bd2  call    memset_0
0x180019bd7  mov     ebp, 104h
0x180019bdc  lea     rdx, [rsp+4B8h+szVolumePathName]; lpszVolumePathName
0x180019be4  mov     r8d, ebp; cchBufferLength
0x180019be7  mov     rcx, rbx; lpszFileName
0x180019bea  call    cs:__imp_GetVolumePathNameW
0x180019bf0  test    eax, eax
0x180019bf2  jnz     short loc_180019C38
0x180019bf4  call    cs:__imp_GetLastError
0x180019bfa  mov     ebx, eax
0x180019bfc  test    eax, eax
0x180019bfe  jnz     short loc_180019C07
0x180019c00  mov     ebx, 80004005h
0x180019c05  jmp     short loc_180019C12
0x180019c07  jle     short loc_180019C12
0x180019c09  movzx   ebx, ax
0x180019c0c  or      ebx, 80070000h
0x180019c12  cmp     [rdi+58h], r15
0x180019c16  jz      loc_180019DAE
0x180019c1c  mov     ecx, r15d
0x180019c1f  test    ebx, ebx
0x180019c21  jns     loc_180019DA9
0x180019c27  mov     [rsp+4B8h+var_490], ebx
0x180019c2b  mov     [rsp+4B8h+var_498], 67Eh
0x180019c33  jmp     loc_180019D82
0x180019c38  mov     r8, rsi; Size
0x180019c3b  lea     rcx, [rsp+4B8h+szVolumeName]; void *
0x180019c40  xor     edx, edx; Val
0x180019c42  call    memset_0
0x180019c47  mov     r8d, ebp; cchBufferLength
0x180019c4a  lea     rdx, [rsp+4B8h+szVolumeName]; lpszVolumeName
0x180019c4f  lea     rcx, [rsp+4B8h+szVolumePathName]; lpszVolumeMountPoint
0x180019c57  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180019c5d  test    eax, eax
0x180019c5f  jnz     short loc_180019CA5
0x180019c61  call    cs:__imp_GetLastError
0x180019c67  mov     ebx, eax
0x180019c69  test    eax, eax
0x180019c6b  jnz     short loc_180019C74
0x180019c6d  mov     ebx, 80004005h
0x180019c72  jmp     short loc_180019C7F
0x180019c74  jle     short loc_180019C7F
0x180019c76  movzx   ebx, ax
0x180019c79  or      ebx, 80070000h
0x180019c7f  cmp     [rdi+58h], r15
0x180019c83  jz      loc_180019DAE
0x180019c89  mov     ecx, r15d
0x180019c8c  test    ebx, ebx
0x180019c8e  jns     loc_180019DA9
0x180019c94  mov     [rsp+4B8h+var_490], ebx
0x180019c98  mov     [rsp+4B8h+var_498], 681h
0x180019ca0  jmp     loc_180019D82
0x180019ca5  lea     rcx, [rsp+4B8h+szVolumeName]
0x180019caa  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019cae  inc     rax
0x180019cb1  cmp     [rcx+rax*2], r15w
0x180019cb6  jnz     short loc_180019CAE
0x180019cb8  test    rax, rax
0x180019cbb  jz      short loc_180019CE0
0x180019cbd  mov     ecx, 5Ch ; '\'
0x180019cc2  cmp     cx, [rsp+rax*2+4B8h+var_47A]
0x180019cc7  jnz     short loc_180019CE0
0x180019cc9  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180019cd1  cmp     rcx, rsi
0x180019cd4  jnb     loc_180019DDB
0x180019cda  mov     [rsp+rcx+4B8h+szVolumeName], r15w
0x180019ce0  mov     edx, 1
0x180019ce5  lea     rcx, [rsp+4B8h+szVolumeName]; lpFileName
0x180019cea  call    GetExtentsFromVolumePath
0x180019cef  mov     rbx, rax
0x180019cf2  test    rax, rax
0x180019cf5  jz      short loc_180019D4B
0x180019cf7  cmp     dword ptr [rax], 1
0x180019cfa  mov     ebp, r15d
0x180019cfd  mov     r14, r15
0x180019d00  mov     rsi, r15
0x180019d03  jb      short loc_180019D16
0x180019d05  mov     ebp, [rax+8]
0x180019d08  mov     r15d, 1
0x180019d0e  mov     r14, [rax+10h]
0x180019d12  mov     rsi, [rax+18h]
0x180019d16  call    cs:__imp_GetProcessHeap
0x180019d1c  mov     r8, rbx; lpMem
0x180019d1f  xor     edx, edx; dwFlags
0x180019d21  mov     rcx, rax; hHeap
0x180019d24  call    cs:__imp_HeapFree
0x180019d2a  test    r15d, r15d
0x180019d2d  jz      short loc_180019D48
0x180019d2f  mov     rax, [rsp+4B8h+var_488]
0x180019d34  xor     ebx, ebx
0x180019d36  mov     [r13+0], ebp
0x180019d3a  mov     [rax], r14
0x180019d3d  test    r12, r12
0x180019d40  jz      short loc_180019DAE
0x180019d42  mov     [r12], rsi
0x180019d46  jmp     short loc_180019DAE
0x180019d48  xor     r15d, r15d
0x180019d4b  call    cs:__imp_GetLastError
0x180019d51  mov     ebx, eax
0x180019d53  test    eax, eax
0x180019d55  jnz     short loc_180019D5E
0x180019d57  mov     ebx, 80004005h
0x180019d5c  jmp     short loc_180019D69
0x180019d5e  jle     short loc_180019D69
0x180019d60  movzx   ebx, ax
0x180019d63  or      ebx, 80070000h
0x180019d69  cmp     [rdi+58h], r15
0x180019d6d  jz      short loc_180019DAE
0x180019d6f  mov     ecx, r15d
0x180019d72  test    ebx, ebx
0x180019d74  jns     short loc_180019DA9
0x180019d76  mov     [rsp+4B8h+var_490], ebx
0x180019d7a  mov     [rsp+4B8h+var_498], 688h
0x180019d82  mov     rcx, [rdi+58h]
0x180019d86  lea     r9, aCdlpactionlayo_33; "CDlpActionLayoutUsb::GetDiskAndOffsetFr"...
0x180019d8d  mov     edx, 4
0x180019d92  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180019d99  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180019d9e  mov     ecx, eax
0x180019da0  test    eax, eax
0x180019da2  jns     short loc_180019DA9
0x180019da4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180019da9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180019dae  mov     ecx, ebx
0x180019db0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180019db5  mov     eax, ebx
0x180019db7  mov     rcx, [rsp+4B8h+var_58]
0x180019dbf  xor     rcx, rsp; StackCookie
0x180019dc2  call    __security_check_cookie
0x180019dc7  add     rsp, 478h
0x180019dce  pop     r15
0x180019dd0  pop     r14
0x180019dd2  pop     r13
0x180019dd4  pop     r12
0x180019dd6  pop     rdi
0x180019dd7  pop     rsi
0x180019dd8  pop     rbp
0x180019dd9  pop     rbx
0x180019dda  retn
0x180019ddb  call    __report_rangecheckfailure
```
