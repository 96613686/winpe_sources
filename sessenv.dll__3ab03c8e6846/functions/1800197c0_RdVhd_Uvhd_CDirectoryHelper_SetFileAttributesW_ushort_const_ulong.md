# RdVhd::Uvhd::CDirectoryHelper::SetFileAttributesW(ushort const *,ulong)

- ea: `0x1800197c0`
- end: `0x18001989d`
- name: `?SetFileAttributesW@CDirectoryHelper@Uvhd@RdVhd@@UEBAHPEBGK@Z`
- size: `221`
- prototype: `int(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180013da0`
- `0x18004de00`
- `0x18004dfe0`
- `0x18004e2a0`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x1800197c0`
- `0x180019b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019828`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800197db`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180019879`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800197db`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180019879`

## string_xrefs

- `0x180019852`: `SetFileAttributesW failed for path '%s'. Trying with long path`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::SetFileAttributesW(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        DWORD a3)
{
  unsigned int v5; // ebx
  signed int LastError; // eax
  const WCHAR *v7; // rax
  void **v9; // [rsp+20h] [rbp-38h] BYREF
  __int128 v10; // [rsp+28h] [rbp-30h]
  __int64 v11; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+40h] [rbp-18h]

  v5 = SetFileAttributesW(a2, a3);
  if ( !v5 && GetLastError() == 3 )
  {
    *(_QWORD *)((char *)&v10 + 4) = 128;
    v9 = &CPathString::`vftable';
    v11 = 0;
    HIDWORD(v10) = v5;
    LODWORD(v12) = 0x8000000;
    LODWORD(v10) = v5;
    LastError = GetLastError();
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastError = LastError & 0x8000FFFF | 0x50290000;
    }
    _TraceNrmRdvVmEx(
      L"UVHD",
      LastError,
      L"SetFileAttributesW failed for path '%s'. Trying with long path",
      a2,
      v9,
      v10,
      v11,
      v12);
    v7 = RdVhd::Uvhd::CLongPath::TryConvertToLongPath(a2, (struct CPathString *)&v9);
    v5 = SetFileAttributesW(v7, a3);
    CPathString::~CPathString((CPathString *)&v9);
  }
  return v5;
}

```

## disassembly

```asm
0x1800197c0  mov     [rsp+arg_0], rbx
0x1800197c5  mov     [rsp+arg_8], rsi
0x1800197ca  push    rdi
0x1800197cb  sub     rsp, 50h
0x1800197cf  mov     esi, r8d
0x1800197d2  mov     rdi, rdx
0x1800197d5  mov     edx, r8d; dwFileAttributes
0x1800197d8  mov     rcx, rdi; lpFileName
0x1800197db  call    cs:__imp_SetFileAttributesW
0x1800197e1  mov     ebx, eax
0x1800197e3  test    eax, eax
0x1800197e5  jnz     loc_18001988B
0x1800197eb  call    cs:__imp_GetLastError
0x1800197f1  cmp     eax, 3
0x1800197f4  jnz     loc_18001988B
0x1800197fa  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180019801  mov     qword ptr [rsp+58h+var_30+4], 80h
0x18001980a  mov     [rsp+58h+var_38], rax
0x18001980f  mov     [rsp+58h+var_20], 0
0x180019818  mov     dword ptr [rsp+58h+var_30+0Ch], ebx
0x18001981c  mov     dword ptr [rsp+58h+var_18], 8000000h
0x180019824  mov     dword ptr [rsp+58h+var_30], ebx
0x180019828  call    cs:__imp_GetLastError
0x18001982e  test    eax, eax
0x180019830  jz      short loc_18001984F
0x180019832  test    eax, 0FFFF0000h
0x180019837  jnz     short loc_18001984F
0x180019839  test    eax, eax
0x18001983b  jle     short loc_180019845
0x18001983d  movzx   eax, ax
0x180019840  or      eax, 80070000h
0x180019845  and     eax, 0D029FFFFh
0x18001984a  or      eax, 50290000h
0x18001984f  mov     r9, rdi
0x180019852  lea     r8, aSetfileattribu_0; "SetFileAttributesW failed for path '%s'"...
0x180019859  mov     edx, eax; int
0x18001985b  lea     rcx, aUvhd; "UVHD"
0x180019862  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180019867  lea     rdx, [rsp+58h+var_38]; struct CPathString *
0x18001986c  mov     rcx, rdi; unsigned __int16 *
0x18001986f  call    ?TryConvertToLongPath@CLongPath@Uvhd@RdVhd@@SAPEBGPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CLongPath::TryConvertToLongPath(ushort const *,CPathString &)
0x180019874  mov     rcx, rax; lpFileName
0x180019877  mov     edx, esi; dwFileAttributes
0x180019879  call    cs:__imp_SetFileAttributesW
0x18001987f  lea     rcx, [rsp+58h+var_38]; this
0x180019884  mov     ebx, eax
0x180019886  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18001988b  mov     rsi, [rsp+58h+arg_8]
0x180019890  mov     eax, ebx
0x180019892  mov     rbx, [rsp+58h+arg_0]
0x180019897  add     rsp, 50h
0x18001989b  pop     rdi
0x18001989c  retn
```
