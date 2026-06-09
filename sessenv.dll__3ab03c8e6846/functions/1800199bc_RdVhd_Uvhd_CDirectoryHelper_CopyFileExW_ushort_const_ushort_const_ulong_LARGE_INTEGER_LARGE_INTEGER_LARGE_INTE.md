# RdVhd::Uvhd::CDirectoryHelper::CopyFileExW(ushort const *,ushort const *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,int *,ulong)

- ea: `0x1800199bc`
- end: `0x180019af9`
- name: `?CopyFileExW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBG0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z2PEAHK@Z`
- size: `317`
- prototype: `int(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *), void *, int *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18004cfd0`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x1800199bc`
- `0x180019b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a55`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x1800199f0`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180019ad1`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x1800199f0`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180019ad1`

## string_xrefs

- `0x180019a84`: `CopyFileExW failed for path '%s' '%s'. Trying with long path`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::CopyFileExW(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int (*a4)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *))
{
  unsigned int v6; // ebx
  signed int LastError; // eax
  const WCHAR *v8; // rbx
  const WCHAR *v9; // rax
  void **v11; // [rsp+30h] [rbp-31h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-29h]
  __int64 v13; // [rsp+3Ch] [rbp-25h]
  unsigned int v14; // [rsp+44h] [rbp-1Dh]
  __int64 v15; // [rsp+48h] [rbp-19h]
  int v16; // [rsp+50h] [rbp-11h]
  void **v17; // [rsp+58h] [rbp-9h] BYREF
  unsigned int v18; // [rsp+60h] [rbp-1h]
  __int64 v19; // [rsp+64h] [rbp+3h]
  unsigned int v20; // [rsp+6Ch] [rbp+Bh]
  __int64 v21; // [rsp+70h] [rbp+Fh]
  int v22; // [rsp+78h] [rbp+17h]

  v6 = CopyFileExW(a2, a3, 0, 0, 0, 1u);
  if ( !v6 && GetLastError() == 3 )
  {
    v19 = 128;
    v22 = 0x8000000;
    v17 = &CPathString::`vftable';
    v16 = 0x8000000;
    v11 = &CPathString::`vftable';
    v21 = 0;
    v20 = v6;
    v18 = v6;
    v13 = 128;
    v15 = 0;
    v14 = v6;
    v12 = v6;
    LastError = GetLastError();
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastError = LastError & 0x8000FFFF | 0x502A0000;
    }
    _TraceNrmRdvVmEx(L"UVHD", LastError, L"CopyFileExW failed for path '%s' '%s'. Trying with long path", a2, a3);
    v8 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a3, (struct CPathString *)&v11);
    v9 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a2, (struct CPathString *)&v17);
    v6 = CopyFileExW(v9, v8, 0, 0, 0, 1u);
    CPathString::~CPathString((CPathString *)&v11);
    CPathString::~CPathString((CPathString *)&v17);
  }
  return v6;
}

```

## disassembly

```asm
0x1800199bc  push    rbp
0x1800199be  push    rbx
0x1800199bf  push    rsi
0x1800199c0  push    rdi
0x1800199c1  lea     rbp, [rsp-27h]
0x1800199c6  sub     rsp, 88h
0x1800199cd  mov     rdi, r8
0x1800199d0  mov     rsi, rdx
0x1800199d3  mov     [rsp+0A0h+dwCopyFlags], 1; dwCopyFlags
0x1800199db  xor     r9d, r9d; lpData
0x1800199de  xor     r8d, r8d; lpProgressRoutine
0x1800199e1  mov     [rsp+0A0h+pbCancel], 0; pbCancel
0x1800199ea  mov     rdx, rdi; lpNewFileName
0x1800199ed  mov     rcx, rsi; lpExistingFileName
0x1800199f0  call    cs:__imp_CopyFileExW
0x1800199f6  mov     ebx, eax
0x1800199f8  test    eax, eax
0x1800199fa  jnz     loc_180019AEB
0x180019a00  call    cs:__imp_GetLastError
0x180019a06  cmp     eax, 3
0x180019a09  jnz     loc_180019AEB
0x180019a0f  mov     ecx, 8000000h
0x180019a14  mov     [rbp+3Fh+var_3C], 80h
0x180019a1c  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180019a23  mov     [rbp+3Fh+var_28], ecx
0x180019a26  mov     [rbp+3Fh+var_48], rax
0x180019a2a  mov     [rbp+3Fh+var_50], ecx
0x180019a2d  mov     [rbp+3Fh+var_70], rax
0x180019a31  mov     [rbp+3Fh+var_30], 0
0x180019a39  mov     [rbp+3Fh+var_34], ebx
0x180019a3c  mov     [rbp+3Fh+var_40], ebx
0x180019a3f  mov     [rbp+3Fh+var_64], 80h
0x180019a47  mov     [rbp+3Fh+var_58], 0
0x180019a4f  mov     [rbp+3Fh+var_5C], ebx
0x180019a52  mov     [rbp+3Fh+var_68], ebx
0x180019a55  call    cs:__imp_GetLastError
0x180019a5b  test    eax, eax
0x180019a5d  jz      short loc_180019A7C
0x180019a5f  test    eax, 0FFFF0000h
0x180019a64  jnz     short loc_180019A7C
0x180019a66  test    eax, eax
0x180019a68  jle     short loc_180019A72
0x180019a6a  movzx   eax, ax
0x180019a6d  or      eax, 80070000h
0x180019a72  and     eax, 0D02AFFFFh
0x180019a77  or      eax, 502A0000h
0x180019a7c  mov     r9, rsi
0x180019a7f  mov     [rsp+0A0h+pbCancel], rdi
0x180019a84  lea     r8, aCopyfileexwFai; "CopyFileExW failed for path '%s' '%s'. "...
0x180019a8b  mov     edx, eax; int
0x180019a8d  lea     rcx, aUvhd; "UVHD"
0x180019a94  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180019a99  lea     rdx, [rbp+3Fh+var_70]; struct CPathString *
0x180019a9d  mov     rcx, rdi; unsigned __int16 *
0x180019aa0  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x180019aa5  lea     rdx, [rbp+3Fh+var_48]; struct CPathString *
0x180019aa9  mov     rcx, rsi; unsigned __int16 *
0x180019aac  mov     rbx, rax
0x180019aaf  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x180019ab4  xor     r9d, r9d; lpData
0x180019ab7  mov     [rsp+0A0h+dwCopyFlags], 1; dwCopyFlags
0x180019abf  xor     r8d, r8d; lpProgressRoutine
0x180019ac2  mov     [rsp+0A0h+pbCancel], 0; pbCancel
0x180019acb  mov     rdx, rbx; lpNewFileName
0x180019ace  mov     rcx, rax; lpExistingFileName
0x180019ad1  call    cs:__imp_CopyFileExW
0x180019ad7  lea     rcx, [rbp+3Fh+var_70]; this
0x180019adb  mov     ebx, eax
0x180019add  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180019ae2  lea     rcx, [rbp+3Fh+var_48]; this
0x180019ae6  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180019aeb  mov     eax, ebx
0x180019aed  add     rsp, 88h
0x180019af4  pop     rdi
0x180019af5  pop     rsi
0x180019af6  pop     rbx
0x180019af7  pop     rbp
0x180019af8  retn
```
