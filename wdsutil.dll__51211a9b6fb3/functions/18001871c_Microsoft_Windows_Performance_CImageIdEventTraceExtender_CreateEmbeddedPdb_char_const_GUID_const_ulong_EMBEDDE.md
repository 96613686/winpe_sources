# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(char const *,_GUID const &,ulong,EMBEDDED_PDB_INFORMATION const &)

- ea: `0x18001871c`
- end: `0x180018c26`
- name: `?CreateEmbeddedPdb@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBDAEBU_GUID@@KAEBUEMBEDDED_PDB_INFORMATION@@@Z`
- size: `1290`
- prototype: `int(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, const char *, const struct _GUID *, unsigned int, const struct EMBEDDED_PDB_INFORMATION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016698`

## callees

- `0x180001d66`
- `0x18000abd4`
- `0x18000abfc`
- `0x1800102f4`
- `0x1800103ec`
- `0x180015ae0`
- `0x180018468`
- `0x1800185cc`
- `0x18001871c`
- `0x180018d14`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001891c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018a17`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018ab8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018b23`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018c04`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001891c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018a17`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018ab8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018b23`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018c04`
- `KERNEL32!GetLastError` at `0x1800189dc`
- `KERNEL32!GetLastError` at `0x1800189f1`
- `KERNEL32!GetLastError` at `0x180018a92`
- `KERNEL32!GetLastError` at `0x180018bde`
- `KERNEL32!GetLastError` at `0x1800189dc`
- `KERNEL32!GetLastError` at `0x1800189f1`
- `KERNEL32!GetLastError` at `0x180018a92`
- `KERNEL32!GetLastError` at `0x180018bde`
- `KERNEL32!CloseHandle` at `0x180018a86`
- `KERNEL32!CloseHandle` at `0x180018b04`
- `KERNEL32!CloseHandle` at `0x180018bd2`
- `KERNEL32!CloseHandle` at `0x180018a86`
- `KERNEL32!CloseHandle` at `0x180018b04`
- `KERNEL32!CloseHandle` at `0x180018bd2`
- `KERNEL32!WriteFile` at `0x180018b9b`
- `KERNEL32!WriteFile` at `0x180018b9b`
- `KERNEL32!SetFilePointer` at `0x180018ad9`
- `KERNEL32!SetFilePointer` at `0x180018ad9`
- `KERNEL32!SetFilePointerEx` at `0x180018a73`
- `KERNEL32!SetFilePointerEx` at `0x180018a73`
- `KERNEL32!CreateDirectoryW` at `0x18001877c`
- `KERNEL32!CreateDirectoryW` at `0x1800187eb`
- `KERNEL32!CreateDirectoryW` at `0x180018838`
- `KERNEL32!CreateDirectoryW` at `0x18001877c`
- `KERNEL32!CreateDirectoryW` at `0x1800187eb`
- `KERNEL32!CreateDirectoryW` at `0x180018838`
- `KERNEL32!CreateFileW` at `0x1800189c8`
- `KERNEL32!CreateFileW` at `0x1800189c8`
- `KERNEL32!GetFileAttributesW` at `0x180018990`
- `KERNEL32!GetFileAttributesW` at `0x180018990`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        char *a2,
        const struct _GUID *a3,
        int a4,
        DWORD *a5)
{
  const WCHAR *v9; // rbx
  unsigned int Error; // r14d
  int v12; // ecx
  size_t v13; // r8
  void **v14; // r9
  void **i; // r9
  void **v16; // rax
  __int64 v17; // r9
  unsigned __int64 v18; // rdi
  __int64 v19; // rbx
  void **v20; // r8
  const WCHAR *v21; // rbx
  HANDLE FileW; // r15
  signed int v23; // eax
  unsigned int v24; // edi
  DWORD v25; // r14d
  const WCHAR *v26; // rdi
  signed int LastError; // eax
  char *v28; // r12
  __int64 v29; // rax
  signed int v30; // eax
  LPCWSTR lpPathName[2]; // [rsp+48h] [rbp-41h] BYREF
  void *v32[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v33; // [rsp+68h] [rbp-21h]
  unsigned __int64 v34; // [rsp+70h] [rbp-19h]
  _QWORD Src[2]; // [rsp+78h] [rbp-11h] BYREF
  __int64 v36; // [rsp+88h] [rbp-1h]
  unsigned __int64 v37; // [rsp+90h] [rbp+7h]

  lpPathName[1] = (LPCWSTR)-2LL;
  v9 = (const WCHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)this + 41) - 24LL) + 24);
  lpPathName[0] = v9;
  if ( !CreateDirectoryW(v9, 0)
    && (Error = ATL::AtlHresultFromLastError(), Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u))
    || (ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          lpPathName,
          L"\\%hs",
          a2),
        v9 = lpPathName[0],
        !CreateDirectoryW(lpPathName[0], 0))
    && (Error = ATL::AtlHresultFromLastError(), Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u))
    || (Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(
          v12,
          (unsigned int)lpPathName,
          *((_QWORD *)this + 41),
          (_DWORD)a2,
          (__int64)a3,
          a4),
        v9 = lpPathName[0],
        !CreateDirectoryW(lpPathName[0], 0))
    && (Error = ATL::AtlHresultFromLastError(), Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
  {
    if ( _InterlockedDecrement((volatile signed __int32 *)v9 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 - 3) + 8LL))(*((_QWORD *)v9 - 3));
    return Error;
  }
  v34 = 15;
  v33 = 0;
  LOBYTE(v32[0]) = 0;
  if ( *a2 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
  }
  else
  {
    v13 = 0;
  }
  std::string::assign(v32, a2, v13);
  if ( v33 )
  {
    v14 = v32;
    if ( v34 >= 0x10 )
      v14 = (void **)v32[0];
    for ( i = (void **)((char *)v14 + v33 - 1); ; i = (void **)((char *)i - 1) )
    {
      v16 = v32;
      if ( *(_BYTE *)i == 46 )
        break;
      if ( v34 >= 0x10 )
        v16 = (void **)v32[0];
      if ( i == v16 )
        goto LABEL_26;
    }
    if ( v34 >= 0x10 )
      v16 = (void **)v32[0];
    v17 = (char *)i - (char *)v16;
  }
  else
  {
LABEL_26:
    v17 = -1;
  }
  if ( v17 != -1 )
  {
    v37 = 15;
    v36 = 0;
    LOBYTE(Src[0]) = 0;
    std::string::assign(Src);
    if ( v34 >= 0x10 )
      operator delete(v32[0]);
    LOBYTE(v32[0]) = 0;
    v18 = v37;
    v19 = v36;
    if ( v37 >= 0x10 )
    {
      v32[0] = (void *)Src[0];
    }
    else if ( v36 != -1 )
    {
      memcpy_0(v32, Src, v36 + 1);
    }
    v33 = v19;
    v34 = v18;
  }
  std::string::operator+=(v32);
  v20 = v32;
  if ( v34 >= 0x10 )
    v20 = (void **)v32[0];
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    lpPathName,
    L"\\%hs",
    v20);
  v21 = lpPathName[0];
  if ( GetFileAttributesW(lpPathName[0]) == -1 )
  {
    FileW = CreateFileW(v21, 0x40000000u, 0, 0, 1u, 0x80u, 0);
    if ( FileW )
    {
      v25 = *a5;
      lpPathName[0] = (LPCWSTR)*a5;
      v26 = lpPathName[0];
      if ( !SetFilePointerEx(FileW, (LARGE_INTEGER)lpPathName[0], 0, 0) )
      {
        CloseHandle(FileW);
        LastError = GetLastError();
        v24 = LastError;
        if ( LastError > 0 )
          v24 = (unsigned __int16)LastError | 0x80070000;
        if ( v34 >= 0x10 )
          operator delete(v32[0]);
        v34 = 15;
        goto LABEL_45;
      }
      SetFilePointer(FileW, 0, 0, 0);
      if ( v25 > 0x10000 )
        v25 = 0x10000;
      v28 = (char *)*((_QWORD *)a5 + 1);
LABEL_58:
      if ( v25 )
      {
        while ( 1 )
        {
          LODWORD(lpPathName[0]) = 0;
          if ( !WriteFile(FileW, v28, v25, (LPDWORD)lpPathName, 0) )
            break;
          v29 = LODWORD(lpPathName[0]);
          v26 = (const WCHAR *)((char *)v26 - LODWORD(lpPathName[0]));
          lpPathName[0] = v26;
          v28 += v29;
          v25 = (unsigned int)v26;
          if ( (unsigned int)v26 <= 0x10000 )
            goto LABEL_58;
          v25 = 0x10000;
        }
        CloseHandle(FileW);
        v30 = GetLastError();
        v24 = v30;
        if ( v30 > 0 )
          v24 = (unsigned __int16)v30 | 0x80070000;
        if ( v34 >= 0x10 )
          operator delete(v32[0]);
        v34 = 15;
        v33 = 0;
        LOBYTE(v32[0]) = 0;
        goto LABEL_46;
      }
      CloseHandle(FileW);
    }
    else if ( GetLastError() != 80 )
    {
      v23 = GetLastError();
      v24 = v23;
      if ( v23 > 0 )
        v24 = (unsigned __int16)v23 | 0x80070000;
      if ( v34 >= 0x10 )
        operator delete(v32[0]);
      v34 = 15;
LABEL_45:
      v33 = 0;
      LOBYTE(v32[0]) = 0;
LABEL_46:
      if ( _InterlockedDecrement((volatile signed __int32 *)v21 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v21 - 3) + 8LL))(*((_QWORD *)v21 - 3));
      return v24;
    }
  }
  if ( v34 >= 0x10 )
    operator delete(v32[0]);
  LOBYTE(v32[0]) = 0;
  v33 = 0;
  v34 = 15;
  if ( _InterlockedDecrement((volatile signed __int32 *)v21 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v21 - 3) + 8LL))(*((_QWORD *)v21 - 3));
  return 0;
}

```

## disassembly

```asm
0x18001871c  mov     rax, rsp
0x18001871f  push    rbp
0x180018720  push    rsi
0x180018721  push    rdi
0x180018722  push    r12
0x180018724  push    r13
0x180018726  push    r14
0x180018728  push    r15
0x18001872a  lea     rbp, [rax-57h]
0x18001872e  sub     rsp, 0A0h
0x180018735  mov     [rbp+4Fh+var_88], 0FFFFFFFFFFFFFFFEh
0x18001873d  mov     [rax+20h], rbx
0x180018741  mov     rax, cs:__security_cookie
0x180018748  xor     rax, rsp
0x18001874b  mov     [rbp+4Fh+var_40], rax
0x18001874f  mov     r15d, r9d
0x180018752  mov     r12, r8
0x180018755  mov     rdi, rdx
0x180018758  mov     rsi, rcx
0x18001875b  mov     r13, [rbp+4Fh+arg_20]
0x18001875f  mov     rcx, [rcx+148h]
0x180018766  sub     rcx, 18h
0x18001876a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001876f  lea     rbx, [rax+18h]
0x180018773  mov     [rbp+4Fh+lpPathName], rbx
0x180018777  xor     edx, edx; lpSecurityAttributes
0x180018779  mov     rcx, rbx; lpPathName
0x18001877c  call    cs:__imp_CreateDirectoryW
0x180018783  nop     dword ptr [rax+rax+00h]
0x180018788  test    eax, eax
0x18001878a  jnz     short loc_1800187CF
0x18001878c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180018791  mov     r14d, eax
0x180018794  mov     ecx, 0B7h; unsigned int
0x180018799  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001879e  cmp     r14d, eax
0x1800187a1  jz      short loc_1800187CF
0x1800187a3  lea     rdx, [rbx-18h]
0x1800187a7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800187ab  mov     ecx, esi
0x1800187ad  lock xadd [rdx+10h], ecx
0x1800187b2  add     ecx, esi
0x1800187b4  test    ecx, ecx
0x1800187b6  jg      short loc_1800187C7
0x1800187b8  mov     rcx, [rdx]
0x1800187bb  mov     rax, [rcx]
0x1800187be  mov     rax, [rax+8]
0x1800187c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187c7  mov     eax, r14d
0x1800187ca  jmp     loc_180018B5D
0x1800187cf  mov     r8, rdi
0x1800187d2  lea     rdx, aHs_0; "\\%hs"
0x1800187d9  lea     rcx, [rbp+4Fh+lpPathName]
0x1800187dd  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800187e2  xor     edx, edx; lpSecurityAttributes
0x1800187e4  mov     rbx, [rbp+4Fh+lpPathName]
0x1800187e8  mov     rcx, rbx; lpPathName
0x1800187eb  call    cs:__imp_CreateDirectoryW
0x1800187f2  nop     dword ptr [rax+rax+00h]
0x1800187f7  test    eax, eax
0x1800187f9  jnz     short loc_180018812
0x1800187fb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180018800  mov     r14d, eax
0x180018803  mov     ecx, 0B7h; unsigned int
0x180018808  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001880d  cmp     r14d, eax
0x180018810  jnz     short loc_1800187A3
0x180018812  mov     [rsp+0D0h+dwFlagsAndAttributes], r15d
0x180018817  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r12
0x18001881c  mov     r9, rdi
0x18001881f  mov     r8, [rsi+148h]
0x180018826  lea     rdx, [rbp+4Fh+lpPathName]
0x18001882a  call    ?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)
0x18001882f  xor     edx, edx; lpSecurityAttributes
0x180018831  mov     rbx, [rbp+4Fh+lpPathName]
0x180018835  mov     rcx, rbx; lpPathName
0x180018838  call    cs:__imp_CreateDirectoryW
0x18001883f  nop     dword ptr [rax+rax+00h]
0x180018844  xor     r12d, r12d
0x180018847  test    eax, eax
0x180018849  jnz     short loc_180018866
0x18001884b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180018850  mov     r14d, eax
0x180018853  mov     ecx, 0B7h; unsigned int
0x180018858  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001885d  cmp     r14d, eax
0x180018860  jnz     loc_1800187A3
0x180018866  mov     r14d, 0Fh
0x18001886c  mov     [rbp+4Fh+var_68], r14
0x180018870  mov     [rbp+4Fh+var_70], r12
0x180018874  mov     byte ptr [rbp+4Fh+var_80], r12b
0x180018878  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001887c  cmp     [rdi], r12b
0x18001887f  jnz     short loc_180018886
0x180018881  mov     r8, r12
0x180018884  jmp     short loc_180018892
0x180018886  mov     r8, rsi
0x180018889  inc     r8; Size
0x18001888c  cmp     [rdi+r8], r12b
0x180018890  jnz     short loc_180018889
0x180018892  mov     rdx, rdi; Src
0x180018895  lea     rcx, [rbp+4Fh+var_80]; void *
0x180018899  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18001889e  nop
0x18001889f  mov     r8, [rbp+4Fh+var_70]
0x1800188a3  cmp     r8, 1
0x1800188a7  jb      short loc_1800188EC
0x1800188a9  lea     r9, [rbp+4Fh+var_80]
0x1800188ad  mov     rcx, [rbp+4Fh+var_80]
0x1800188b1  mov     rdx, [rbp+4Fh+var_68]
0x1800188b5  cmp     rdx, 10h
0x1800188b9  cmovnb  r9, rcx
0x1800188bd  dec     r9
0x1800188c0  add     r9, r8
0x1800188c3  lea     rax, [rbp+4Fh+var_80]
0x1800188c7  cmp     byte ptr [r9], 2Eh ; '.'
0x1800188cb  jz      short loc_1800188DF
0x1800188cd  cmp     rdx, 10h
0x1800188d1  cmovnb  rax, rcx
0x1800188d5  cmp     r9, rax
0x1800188d8  jz      short loc_1800188EC
0x1800188da  dec     r9
0x1800188dd  jmp     short loc_1800188C3
0x1800188df  cmp     rdx, 10h
0x1800188e3  cmovnb  rax, rcx
0x1800188e7  sub     r9, rax
0x1800188ea  jmp     short loc_1800188EF
0x1800188ec  mov     r9, rsi
0x1800188ef  cmp     r9, rsi
0x1800188f2  jz      short loc_180018962
0x1800188f4  mov     [rbp+4Fh+var_48], r14
0x1800188f8  mov     [rbp+4Fh+var_50], r12
0x1800188fc  mov     byte ptr [rbp+4Fh+Src], r12b
0x180018900  xor     r8d, r8d
0x180018903  lea     rdx, [rbp+4Fh+var_80]
0x180018907  lea     rcx, [rbp+4Fh+Src]; void *
0x18001890b  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180018910  nop
0x180018911  cmp     [rbp+4Fh+var_68], 10h
0x180018916  jb      short loc_180018928
0x180018918  mov     rcx, [rbp+4Fh+var_80]
0x18001891c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018923  nop     dword ptr [rax+rax+00h]
0x180018928  mov     byte ptr [rbp+4Fh+var_80], r12b
0x18001892c  mov     rdi, [rbp+4Fh+var_48]
0x180018930  mov     rbx, [rbp+4Fh+var_50]
0x180018934  cmp     rdi, 10h
0x180018938  jnb     short loc_180018952
0x18001893a  lea     r8, [rbx+1]; Size
0x18001893e  test    r8, r8
0x180018941  jz      short loc_18001895A
0x180018943  lea     rdx, [rbp+4Fh+Src]; Src
0x180018947  lea     rcx, [rbp+4Fh+var_80]; void *
0x18001894b  call    memcpy_0
0x180018950  jmp     short loc_18001895A
0x180018952  mov     rax, [rbp+4Fh+Src]
0x180018956  mov     [rbp+4Fh+var_80], rax
0x18001895a  mov     [rbp+4Fh+var_70], rbx
0x18001895e  mov     [rbp+4Fh+var_68], rdi
0x180018962  lea     rcx, [rbp+4Fh+var_80]; Src
0x180018966  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@PEBD@Z; std::string::operator+=(char const *)
0x18001896b  lea     r8, [rbp+4Fh+var_80]
0x18001896f  cmp     [rbp+4Fh+var_68], 10h
0x180018974  cmovnb  r8, [rbp+4Fh+var_80]
0x180018979  lea     rdx, aHs_0; "\\%hs"
0x180018980  lea     rcx, [rbp+4Fh+lpPathName]
0x180018984  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180018989  mov     rbx, [rbp+4Fh+lpPathName]
0x18001898d  mov     rcx, rbx; lpFileName
0x180018990  call    cs:__imp_GetFileAttributesW
0x180018997  nop     dword ptr [rax+rax+00h]
0x18001899c  cmp     eax, 0FFFFFFFFh
0x18001899f  jnz     loc_180018B18
0x1800189a5  mov     [rsp+30h], r12; hTemplateFile
0x1800189aa  mov     [rsp+0D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800189b2  mov     [rsp+0D0h+dwCreationDisposition], 1; dwCreationDisposition
0x1800189ba  xor     r9d, r9d; lpSecurityAttributes
0x1800189bd  xor     r8d, r8d; dwShareMode
0x1800189c0  mov     edx, 40000000h; dwDesiredAccess
0x1800189c5  mov     rcx, rbx; lpFileName
0x1800189c8  call    cs:__imp_CreateFileW
0x1800189cf  nop     dword ptr [rax+rax+00h]
0x1800189d4  mov     r15, rax
0x1800189d7  test    rax, rax
0x1800189da  jnz     short loc_180018A56
0x1800189dc  call    cs:__imp_GetLastError
0x1800189e3  nop     dword ptr [rax+rax+00h]
0x1800189e8  cmp     eax, 50h ; 'P'
0x1800189eb  jz      loc_180018B18
0x1800189f1  call    cs:__imp_GetLastError
0x1800189f8  nop     dword ptr [rax+rax+00h]
0x1800189fd  mov     edi, eax
0x1800189ff  test    eax, eax
0x180018a01  jle     short loc_180018A0C
0x180018a03  movzx   edi, ax
0x180018a06  or      edi, 80070000h
0x180018a0c  cmp     [rbp+4Fh+var_68], 10h
0x180018a11  jb      short loc_180018A23
0x180018a13  mov     rcx, [rbp+4Fh+var_80]
0x180018a17  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018a1e  nop     dword ptr [rax+rax+00h]
0x180018a23  mov     [rbp+4Fh+var_68], r14
0x180018a27  mov     [rbp+4Fh+var_70], r12
0x180018a2b  mov     byte ptr [rbp+4Fh+var_80], r12b
0x180018a2f  lea     rdx, [rbx-18h]
0x180018a33  mov     ecx, esi
0x180018a35  lock xadd [rdx+10h], ecx
0x180018a3a  add     ecx, esi
0x180018a3c  test    ecx, ecx
0x180018a3e  jg      short loc_180018A4F
0x180018a40  mov     rcx, [rdx]
0x180018a43  mov     r8, [rcx]
0x180018a46  mov     rax, [r8+8]
0x180018a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a4f  mov     eax, edi
0x180018a51  jmp     loc_180018B5D
0x180018a56  mov     r14d, [r13+0]
0x180018a5a  mov     dword ptr [rbp+4Fh+lpPathName], r14d
0x180018a5e  xor     eax, eax
0x180018a60  mov     dword ptr [rbp+4Fh+lpPathName+4], eax
0x180018a63  xor     r9d, r9d; dwMoveMethod
0x180018a66  xor     r8d, r8d; lpNewFilePointer
0x180018a69  mov     rdi, [rbp+4Fh+lpPathName]
0x180018a6d  mov     rdx, rdi; liDistanceToMove
0x180018a70  mov     rcx, r15; hFile
0x180018a73  call    cs:__imp_SetFilePointerEx
0x180018a7a  nop     dword ptr [rax+rax+00h]
0x180018a7f  mov     rcx, r15; hFile
0x180018a82  test    eax, eax
0x180018a84  jnz     short loc_180018AD1
0x180018a86  call    cs:__imp_CloseHandle
0x180018a8d  nop     dword ptr [rax+rax+00h]
0x180018a92  call    cs:__imp_GetLastError
0x180018a99  nop     dword ptr [rax+rax+00h]
0x180018a9e  mov     edi, eax
0x180018aa0  test    eax, eax
0x180018aa2  jle     short loc_180018AAD
0x180018aa4  movzx   edi, ax
0x180018aa7  or      edi, 80070000h
0x180018aad  cmp     [rbp+4Fh+var_68], 10h
0x180018ab2  jb      short loc_180018AC4
0x180018ab4  mov     rcx, [rbp+4Fh+var_80]
0x180018ab8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018abf  nop     dword ptr [rax+rax+00h]
0x180018ac4  mov     [rbp+4Fh+var_68], 0Fh
0x180018acc  jmp     loc_180018A27
0x180018ad1  xor     r9d, r9d; dwMoveMethod
0x180018ad4  xor     r8d, r8d; lpDistanceToMoveHigh
0x180018ad7  xor     edx, edx; lDistanceToMove
0x180018ad9  call    cs:__imp_SetFilePointer
0x180018ae0  nop     dword ptr [rax+rax+00h]
0x180018ae5  mov     eax, 10000h
0x180018aea  cmp     r14d, eax
0x180018aed  cmova   r14d, eax
0x180018af1  mov     r12, [r13+8]
0x180018af5  xor     r13d, r13d
0x180018af8  test    r14d, r14d
0x180018afb  jnz     loc_180018B85
0x180018b01  mov     rcx, r15; hObject
0x180018b04  call    cs:__imp_CloseHandle
0x180018b0b  nop     dword ptr [rax+rax+00h]
0x180018b10  xor     r12d, r12d
0x180018b13  lea     r14d, [r12+0Fh]
0x180018b18  cmp     [rbp+4Fh+var_68], 10h
0x180018b1d  jb      short loc_180018B2F
0x180018b1f  mov     rcx, [rbp+4Fh+var_80]
0x180018b23  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018b2a  nop     dword ptr [rax+rax+00h]
0x180018b2f  mov     byte ptr [rbp+4Fh+var_80], r12b
0x180018b33  mov     [rbp+4Fh+var_70], r12
0x180018b37  mov     [rbp+4Fh+var_68], r14
0x180018b3b  lea     rdx, [rbx-18h]
0x180018b3f  mov     eax, esi
0x180018b41  lock xadd [rdx+10h], eax
0x180018b46  add     eax, esi
0x180018b48  test    eax, eax
0x180018b4a  jg      short loc_180018B5B
0x180018b4c  mov     rcx, [rdx]
0x180018b4f  mov     rax, [rcx]
0x180018b52  mov     rax, [rax+8]
0x180018b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b5b  xor     eax, eax
0x180018b5d  mov     rcx, [rbp+4Fh+var_40]
0x180018b61  xor     rcx, rsp; StackCookie
0x180018b64  call    __security_check_cookie
0x180018b69  mov     rbx, [rsp+0D0h+arg_18]
0x180018b71  add     rsp, 0A0h
0x180018b78  pop     r15
0x180018b7a  pop     r14
0x180018b7c  pop     r13
0x180018b7e  pop     r12
0x180018b80  pop     rdi
0x180018b81  pop     rsi
0x180018b82  pop     rbp
0x180018b83  retn
0x180018b85  mov     dword ptr [rbp+4Fh+lpPathName], r13d
0x180018b89  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; lpOverlapped
0x180018b8e  lea     r9, [rbp+4Fh+lpPathName]; lpNumberOfBytesWritten
0x180018b92  mov     r8d, r14d; nNumberOfBytesToWrite
0x180018b95  mov     rdx, r12; lpBuffer
  ... truncated ...
```
