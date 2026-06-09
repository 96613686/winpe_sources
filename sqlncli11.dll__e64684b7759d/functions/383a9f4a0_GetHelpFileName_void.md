# GetHelpFileName(void)

- ea: `0x383a9f4a0`
- end: `0x383a9f82b`
- name: `?GetHelpFileName@@YAPEAGXZ`
- size: `907`
- prototype: `unsigned __int16 *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x3839d8950`
- `0x383a9f880`

## callees

- `0x383893160`
- `0x38391aed0`
- `0x383a9f4a0`

## import_xrefs

- `MSVCR100!wcsrchr` at `0x383a9f551`
- `MSVCR100!wcsrchr` at `0x383a9f551`
- `KERNEL32!GetModuleFileNameW` at `0x383a9f53b`
- `KERNEL32!GetModuleFileNameW` at `0x383a9f53b`
- `KERNEL32!GetLastError` at `0x383a9f62b`
- `KERNEL32!GetLastError` at `0x383a9f62b`
- `KERNEL32!GetSystemDefaultLCID` at `0x383a9f6bd`
- `KERNEL32!GetSystemDefaultLCID` at `0x383a9f6bd`
- `KERNEL32!CreateFileW` at `0x383a9f6ad`
- `KERNEL32!CreateFileW` at `0x383a9f752`
- `KERNEL32!CreateFileW` at `0x383a9f7e1`
- `KERNEL32!CreateFileW` at `0x383a9f6ad`
- `KERNEL32!CreateFileW` at `0x383a9f752`
- `KERNEL32!CreateFileW` at `0x383a9f7e1`
- `KERNEL32!CloseHandle` at `0x383a9f807`
- `KERNEL32!CloseHandle` at `0x383a9f807`
- `KERNEL32!GetUserDefaultLCID` at `0x383a9f5ad`
- `KERNEL32!GetUserDefaultLCID` at `0x383a9f5ad`

## pseudocode

```c
unsigned __int16 *GetHelpFileName(void)
{
  unsigned __int64 v0; // rdi
  __int64 v1; // rax
  WCHAR *v2; // rax
  const wchar_t *v3; // rbx
  unsigned __int16 *v5; // rsi
  wchar_t *v6; // rax
  LCID UserDefaultLCID; // eax
  signed int LastError; // eax
  bool v9; // sf
  HANDLE FileW; // rax
  LCID SystemDefaultLCID; // eax

  v0 = 261;
  v1 = 522;
  if ( !is_mul_ok(0x105u, 2u) )
    v1 = -1;
  v2 = (WCHAR *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v1);
  v3 = v2;
  if ( !v2 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
    {
      bidTraceW(off_383B43540[0], 48137, off_383B49120[0], 47);
      return 0;
    }
    return 0;
  }
  v5 = v2;
  if ( GetModuleFileNameW(g_hinstance, v2, 0x105u) )
  {
    v6 = wcsrchr(v3, 0x5Cu);
    if ( !v6 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43540[0], 58377, off_383B49120[0], 57);
      goto LABEL_38;
    }
    v5 = v6 + 1;
    v0 = 261 - (v6 + 1 - v3);
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError < 0;
    if ( LastError > 0 )
      v9 = 1;
    if ( v9 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43540[0], 67593, off_383B49120[0], 66);
      goto LABEL_38;
    }
  }
  UserDefaultLCID = GetUserDefaultLCID();
  if ( UserDefaultLCID == 3076 )
    UserDefaultLCID = 1028;
  if ( (int)StringCchPrintfW(v5, v0, L"%lu\\%ls", UserDefaultLCID, L"s11ch_sqlncli.chm") < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B43540[0], 79881, off_383B49120[0], 78);
    goto LABEL_38;
  }
  FileW = CreateFileW(v3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    SystemDefaultLCID = GetSystemDefaultLCID();
    if ( SystemDefaultLCID == 3076 )
      SystemDefaultLCID = 1028;
    if ( (int)StringCchPrintfW(v5, v0, L"%lu\\%ls", SystemDefaultLCID, L"s11ch_sqlncli.chm") < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43540[0], 101385, off_383B49120[0], 99);
      goto LABEL_38;
    }
    FileW = CreateFileW(v3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      if ( (int)StringCchPrintfW(v5, v0, L"%ls\\%ls", L"1033", L"s11ch_sqlncli.chm") < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43540[0], 119817, off_383B49120[0], 117);
        goto LABEL_38;
      }
      FileW = CreateFileW(v3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
LABEL_38:
        ((void (__fastcall *)(struct IMalloc *, const wchar_t *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v3);
        return 0;
      }
    }
  }
  CloseHandle(FileW);
  return (unsigned __int16 *)v3;
}

```

## disassembly

```asm
0x383a9f4a0  mov     [rsp+arg_0], rbx
0x383a9f4a5  mov     [rsp+arg_8], rsi
0x383a9f4aa  mov     [rsp+arg_10], rdi
0x383a9f4af  mov     [rsp+arg_18], r14
0x383a9f4b4  push    r15
0x383a9f4b6  sub     rsp, 40h
0x383a9f4ba  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a9f4c1  mov     edi, 105h
0x383a9f4c6  mov     eax, 2
0x383a9f4cb  mov     r8, [rcx]
0x383a9f4ce  mul     rdi
0x383a9f4d1  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x383a9f4d8  cmovo   rax, rdx
0x383a9f4dc  mov     rdx, rax
0x383a9f4df  call    qword ptr [r8+70h]
0x383a9f4e3  mov     rbx, rax
0x383a9f4e6  test    rax, rax
0x383a9f4e9  jnz     short loc_383A9F52B
0x383a9f4eb  test    byte ptr cs:_bidGblFlags, 2
0x383a9f4f2  jz      loc_383A9F800
0x383a9f4f8  mov     rcx, cs:off_383B43540; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9f4ff  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f506  test    rax, rax
0x383a9f509  jz      loc_383A9F800
0x383a9f50f  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f516  lea     r9d, [rbx+2Fh]
0x383a9f51a  mov     edx, 0BC09h
0x383a9f51f  call    _bidTraceW
0x383a9f524  xor     eax, eax
0x383a9f526  jmp     loc_383A9F810
0x383a9f52b  mov     rcx, cs:?g_hinstance@@3PEAUHINSTANCE__@@EA; hModule
0x383a9f532  mov     r8d, edi; nSize
0x383a9f535  mov     rdx, rax; lpFilename
0x383a9f538  mov     rsi, rax
0x383a9f53b  call    cs:__imp_GetModuleFileNameW
0x383a9f541  test    eax, eax
0x383a9f543  jz      loc_383A9F62B
0x383a9f549  mov     edx, 5Ch ; '\'; Ch
0x383a9f54e  mov     rcx, rbx; Str
0x383a9f551  call    cs:__imp_wcsrchr
0x383a9f557  mov     rsi, rax
0x383a9f55a  test    rax, rax
0x383a9f55d  jnz     short loc_383A9F59D
0x383a9f55f  test    byte ptr cs:_bidGblFlags, 2
0x383a9f566  jz      loc_383A9F7ED
0x383a9f56c  mov     rcx, cs:off_383B43540; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9f573  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f57a  test    rax, rax
0x383a9f57d  jz      loc_383A9F7ED
0x383a9f583  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f58a  lea     r9d, [rsi+39h]
0x383a9f58e  mov     edx, 0E409h
0x383a9f593  call    _bidTraceW
0x383a9f598  jmp     loc_383A9F7ED
0x383a9f59d  add     rsi, 2
0x383a9f5a1  mov     rax, rsi
0x383a9f5a4  sub     rax, rbx
0x383a9f5a7  sar     rax, 1
0x383a9f5aa  sub     rdi, rax
0x383a9f5ad  call    cs:__imp_GetUserDefaultLCID
0x383a9f5b3  mov     r15d, 404h
0x383a9f5b9  lea     r14, aS11chSqlncliCh; "s11ch_sqlncli.chm"
0x383a9f5c0  cmp     eax, 0C04h
0x383a9f5c5  lea     r8, aLuLs; "%lu\\%ls"
0x383a9f5cc  mov     rdx, rdi; unsigned __int64
0x383a9f5cf  cmovz   eax, r15d
0x383a9f5d3  mov     rcx, rsi; unsigned __int16 *
0x383a9f5d6  mov     qword ptr [rsp+48h+dwCreationDisposition], r14
0x383a9f5db  mov     r9d, eax
0x383a9f5de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x383a9f5e3  test    eax, eax
0x383a9f5e5  jns     loc_383A9F685
0x383a9f5eb  test    byte ptr cs:_bidGblFlags, 2
0x383a9f5f2  jz      loc_383A9F7ED
0x383a9f5f8  mov     rcx, cs:off_383B43540; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9f5ff  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f606  test    rax, rax
0x383a9f609  jz      loc_383A9F7ED
0x383a9f60f  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f616  mov     r9d, 4Eh ; 'N'
0x383a9f61c  mov     edx, 13809h
0x383a9f621  call    _bidTraceW
0x383a9f626  jmp     loc_383A9F7ED
0x383a9f62b  call    cs:__imp_GetLastError
0x383a9f631  test    eax, eax
0x383a9f633  jle     short loc_383A9F63F
0x383a9f635  movzx   eax, ax
0x383a9f638  or      eax, 80070000h
0x383a9f63d  test    eax, eax
0x383a9f63f  jns     loc_383A9F5AD
0x383a9f645  test    byte ptr cs:_bidGblFlags, 2
0x383a9f64c  jz      loc_383A9F7ED
0x383a9f652  mov     rcx, cs:off_383B43540; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9f659  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f660  test    rax, rax
0x383a9f663  jz      loc_383A9F7ED
0x383a9f669  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f670  mov     r9d, 42h ; 'B'
0x383a9f676  mov     edx, 10809h
0x383a9f67b  call    _bidTraceW
0x383a9f680  jmp     loc_383A9F7ED
0x383a9f685  xor     r9d, r9d; lpSecurityAttributes
0x383a9f688  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x383a9f691  mov     edx, 80000000h; dwDesiredAccess
0x383a9f696  lea     r8d, [r9+1]; dwShareMode
0x383a9f69a  mov     rcx, rbx; lpFileName
0x383a9f69d  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x383a9f6a5  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x383a9f6ad  call    cs:__imp_CreateFileW
0x383a9f6b3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x383a9f6b7  jnz     loc_383A9F804
0x383a9f6bd  call    cs:__imp_GetSystemDefaultLCID
0x383a9f6c3  lea     r8, aLuLs; "%lu\\%ls"
0x383a9f6ca  mov     rdx, rdi; unsigned __int64
0x383a9f6cd  cmp     eax, 0C04h
0x383a9f6d2  mov     rcx, rsi; unsigned __int16 *
0x383a9f6d5  mov     qword ptr [rsp+48h+dwCreationDisposition], r14
0x383a9f6da  cmovz   eax, r15d
0x383a9f6de  mov     r9d, eax
0x383a9f6e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x383a9f6e6  test    eax, eax
0x383a9f6e8  jns     short loc_383A9F72A
0x383a9f6ea  test    byte ptr cs:_bidGblFlags, 2
0x383a9f6f1  jz      loc_383A9F7ED
0x383a9f6f7  mov     rcx, cs:off_383B43540; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9f6fe  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f705  test    rax, rax
0x383a9f708  jz      loc_383A9F7ED
0x383a9f70e  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f715  mov     r9d, 63h ; 'c'
0x383a9f71b  mov     edx, 18C09h
0x383a9f720  call    _bidTraceW
0x383a9f725  jmp     loc_383A9F7ED
0x383a9f72a  xor     r9d, r9d; lpSecurityAttributes
0x383a9f72d  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x383a9f736  mov     edx, 80000000h; dwDesiredAccess
0x383a9f73b  lea     r8d, [r9+1]; dwShareMode
0x383a9f73f  mov     rcx, rbx; lpFileName
0x383a9f742  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x383a9f74a  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x383a9f752  call    cs:__imp_CreateFileW
0x383a9f758  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x383a9f75c  jnz     loc_383A9F804
0x383a9f762  lea     r9, a1033; "1033"
0x383a9f769  lea     r8, aLsLs_1; "%ls\\%ls"
0x383a9f770  mov     rdx, rdi; unsigned __int64
0x383a9f773  mov     rcx, rsi; unsigned __int16 *
0x383a9f776  mov     qword ptr [rsp+48h+dwCreationDisposition], r14
0x383a9f77b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x383a9f780  test    eax, eax
0x383a9f782  jns     short loc_383A9F7B9
0x383a9f784  test    byte ptr cs:_bidGblFlags, 2
0x383a9f78b  jz      short loc_383A9F7ED
0x383a9f78d  mov     rcx, cs:off_383B43540; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9f794  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f79b  test    rax, rax
0x383a9f79e  jz      short loc_383A9F7ED
0x383a9f7a0  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383a9f7a7  mov     r9d, 75h ; 'u'
0x383a9f7ad  mov     edx, 1D409h
0x383a9f7b2  call    _bidTraceW
0x383a9f7b7  jmp     short loc_383A9F7ED
0x383a9f7b9  xor     r9d, r9d; lpSecurityAttributes
0x383a9f7bc  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x383a9f7c5  mov     edx, 80000000h; dwDesiredAccess
0x383a9f7ca  lea     r8d, [r9+1]; dwShareMode
0x383a9f7ce  mov     rcx, rbx; lpFileName
0x383a9f7d1  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x383a9f7d9  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x383a9f7e1  call    cs:__imp_CreateFileW
0x383a9f7e7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x383a9f7eb  jnz     short loc_383A9F804
0x383a9f7ed  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a9f7f4  mov     rdx, rbx
0x383a9f7f7  mov     rax, [rcx]
0x383a9f7fa  call    qword ptr [rax+80h]
0x383a9f800  xor     eax, eax
0x383a9f802  jmp     short loc_383A9F810
0x383a9f804  mov     rcx, rax; hObject
0x383a9f807  call    cs:__imp_CloseHandle
0x383a9f80d  mov     rax, rbx
0x383a9f810  mov     rbx, [rsp+48h+arg_0]
0x383a9f815  mov     rsi, [rsp+48h+arg_8]
0x383a9f81a  mov     rdi, [rsp+48h+arg_10]
0x383a9f81f  mov     r14, [rsp+48h+arg_18]
0x383a9f824  add     rsp, 40h
0x383a9f828  pop     r15
0x383a9f82a  retn
```
