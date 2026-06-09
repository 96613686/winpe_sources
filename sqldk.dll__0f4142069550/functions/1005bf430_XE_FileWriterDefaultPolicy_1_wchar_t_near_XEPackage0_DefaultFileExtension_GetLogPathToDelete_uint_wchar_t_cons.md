# XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>::GetLogPathToDelete(uint,wchar_t * const,uint,uint *)

- ea: `0x1005bf430`
- end: `0x1005bf730`
- name: `?GetLogPathToDelete@?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@QEAAHIQEA_WIPEAI@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1005bec50`

## callees

- `0x100403070`
- `0x100404bf2`
- `0x10042d580`
- `0x100444460`
- `0x100444570`
- `0x10044acd0`
- `0x1005bf430`

## import_xrefs

- `KERNEL32!FindClose` at `0x1005bf600`
- `KERNEL32!FindClose` at `0x1005bf600`
- `KERNEL32!CreateFileW` at `0x1005bf6b4`
- `KERNEL32!CreateFileW` at `0x1005bf6b4`
- `KERNEL32!FindNextFileW` at `0x1005bf5c0`
- `KERNEL32!FindNextFileW` at `0x1005bf5c0`
- `KERNEL32!FindFirstFileW` at `0x1005bf521`
- `KERNEL32!FindFirstFileW` at `0x1005bf521`
- `KERNEL32!CloseHandle` at `0x1005bf724`
- `KERNEL32!CloseHandle` at `0x1005bf724`
- `KERNEL32!GetLastError` at `0x1005bf6da`
- `KERNEL32!GetLastError` at `0x1005bf6da`
- `api-ms-win-crt-convert-l1-1-0!wcstoll` at `0x1005bf63b`
- `api-ms-win-crt-convert-l1-1-0!wcstoll` at `0x1005bf63b`

## string_xrefs

- `0x1005bf6ec`: `[ERROR] Log file %ls cannot be deleted. Last error code from CreateFile is %lu \n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>::GetLogPathToDelete(
        __int64 a1,
        unsigned int a2,
        wchar_t *a3,
        unsigned int a4,
        _DWORD *a5)
{
  unsigned int v8; // esi
  __int64 v9; // r15
  __int64 v11; // rbp
  HANDLE FirstFileW; // r14
  __int64 v13; // rax
  WCHAR *v14; // rcx
  WCHAR *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rdi
  wchar_t *FileW; // rbx
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-988h]
  wchar_t *v20; // [rsp+40h] [rbp-968h]
  wchar_t *EndPtr[3]; // [rsp+68h] [rbp-940h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-928h] BYREF
  WCHAR v25[264]; // [rsp+2D0h] [rbp-6D8h] BYREF
  WCHAR FileName[264]; // [rsp+4E0h] [rbp-4C8h] BYREF
  wchar_t Buffer[304]; // [rsp+6F0h] [rbp-2B8h] BYREF

  v8 = 0;
  *a5 = 0;
  v9 = 1580LL * a2;
  if ( qword_100715060 && (unsigned __int8)qword_100715060(v9 + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 4LL, 260) )
  {
    *a3 = 0;
    return 1;
  }
  else
  {
    if ( a4 >= 0x104
      && XE_LogSpecs::LogSpec::GetSearchPattern(
           (XE_LogSpecs::LogSpec *)(v9 + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL)),
           FileName,
           0x104u) )
    {
      v11 = 0x7FFFFFFFFFFFFFFFLL;
      v20 = 0;
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        do
        {
          if ( !(unsigned int)XE_LogSpecs::LogSpec::IsAssociatedLog(
                                (XE_LogSpecs::LogSpec *)(v9 + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL)),
                                FindFileData.cFileName) )
            goto LABEL_13;
          v13 = -1;
          do
            ++v13;
          while ( FindFileData.cFileName[v13] );
          v14 = &FindFileData.cFileName[(unsigned int)v13];
          if ( v14 <= FindFileData.cFileName )
            goto LABEL_13;
          while ( *v14 != 95 )
          {
            if ( --v14 <= FindFileData.cFileName )
              goto LABEL_13;
          }
          v16 = wcstoll(v14 + 1, EndPtr, 10);
          v17 = v16;
          if ( v16 > 0
            && (++*a5, v16 < v11)
            && (unsigned int)qword_1007150E0(
                               v25,
                               260,
                               v9 + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 4LL,
                               FindFileData.cFileName) )
          {
            FileW = (wchar_t *)CreateFileW(v25, 0x40000000u, 0, 0, 3u, 0x80u, 0);
            EndPtr[1] = FileW;
            if ( FileW == (wchar_t *)-1LL )
            {
              LODWORD(dwCreationDisposition) = GetLastError();
              StringCchPrintfW(
                Buffer,
                0x12Cu,
                L"[ERROR] Log file %ls cannot be deleted. Last error code from CreateFile is %lu \n",
                v25,
                dwCreationDisposition);
              qword_1007150B0(Buffer);
              v15 = v20;
            }
            else
            {
              v11 = v17;
              v15 = v25;
              v20 = v25;
            }
            if ( FileW )
              CloseHandle(FileW);
          }
          else
          {
LABEL_13:
            v15 = v20;
          }
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        if ( v11 != 0x7FFFFFFFFFFFFFFFLL )
        {
          _mm_lfence();
          LOBYTE(v8) = (int)StringCchCopyW(a3, a4, v15) >= 0;
        }
      }
      if ( FirstFileW != (HANDLE)-1LL )
        FindClose(FirstFileW);
    }
    return v8;
  }
}

```

## disassembly

```asm
0x1005bf430  push    rbx
0x1005bf432  push    rbp
0x1005bf433  push    rsi
0x1005bf434  push    rdi
0x1005bf435  push    r12
0x1005bf437  push    r13
0x1005bf439  push    r14
0x1005bf43b  push    r15
0x1005bf43d  sub     rsp, 968h
0x1005bf444  mov     [rsp+9A8h+var_950], 0FFFFFFFFFFFFFFFEh
0x1005bf44d  mov     rax, cs:__security_cookie
0x1005bf454  xor     rax, rsp
0x1005bf457  mov     [rsp+9A8h+var_58], rax
0x1005bf45f  mov     edi, r9d
0x1005bf462  mov     dword ptr [rsp+9A8h+var_960], r9d
0x1005bf467  mov     rbx, r8
0x1005bf46a  mov     [rsp+9A8h+var_958], rbx
0x1005bf46f  mov     r13, rcx
0x1005bf472  mov     r12, [rsp+9A8h+arg_20]
0x1005bf47a  xor     esi, esi
0x1005bf47c  mov     [r12], esi
0x1005bf480  mov     eax, edx
0x1005bf482  mov     r8, cs:qword_100715060
0x1005bf489  imul    r15, rax, 62Ch
0x1005bf490  test    r8, r8
0x1005bf493  jz      short loc_1005BF4BB
0x1005bf495  mov     rax, [rcx+18h]
0x1005bf499  mov     rcx, [rax+8]
0x1005bf49d  add     rcx, 4
0x1005bf4a1  add     rcx, r15
0x1005bf4a4  mov     edx, 104h
0x1005bf4a9  call    r8 ; qword_100715060
0x1005bf4ac  test    al, al
0x1005bf4ae  jz      short loc_1005BF4BB
0x1005bf4b0  mov     [rbx], si
0x1005bf4b3  lea     eax, [rsi+1]
0x1005bf4b6  jmp     loc_1005BF608
0x1005bf4bb  cmp     edi, 104h
0x1005bf4c1  jb      loc_1005BF606
0x1005bf4c7  mov     rax, [r13+18h]
0x1005bf4cb  mov     rcx, [rax+8]
0x1005bf4cf  add     rcx, r15; this
0x1005bf4d2  mov     r8d, 104h; unsigned int
0x1005bf4d8  lea     rdx, [rsp+9A8h+FileName]; wchar_t *
0x1005bf4e0  call    ?GetSearchPattern@LogSpec@XE_LogSpecs@@QEBAHQEA_WI@Z; XE_LogSpecs::LogSpec::GetSearchPattern(wchar_t * const,uint)
0x1005bf4e5  test    eax, eax
0x1005bf4e7  jz      loc_1005BF606
0x1005bf4ed  mov     rbp, 7FFFFFFFFFFFFFFFh
0x1005bf4f7  mov     [rsp+9A8h+var_968], rsi
0x1005bf4fc  xor     edx, edx; Val
0x1005bf4fe  mov     r8d, 250h; Size
0x1005bf504  lea     rcx, [rsp+9A8h+FindFileData]; void *
0x1005bf50c  call    memset_0
0x1005bf511  lea     rdx, [rsp+9A8h+FindFileData]; lpFindFileData
0x1005bf519  lea     rcx, [rsp+9A8h+FileName]; lpFileName
0x1005bf521  call    cs:__imp_FindFirstFileW
0x1005bf527  mov     r14, rax
0x1005bf52a  mov     [rsp+9A8h+var_948], rax
0x1005bf52f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1005bf533  jz      loc_1005BF5F7
0x1005bf539  nop     dword ptr [rax]
0x1005bf53c  nop     dword ptr [rax+00h]
0x1005bf540  mov     rax, [r13+18h]
0x1005bf544  mov     rcx, [rax+8]
0x1005bf548  add     rcx, r15; this
0x1005bf54b  lea     rdx, [rsp+9A8h+FindFileData.cFileName]; wchar_t *
0x1005bf553  call    ?IsAssociatedLog@LogSpec@XE_LogSpecs@@QEBAHQEB_W@Z; XE_LogSpecs::LogSpec::IsAssociatedLog(wchar_t const * const)
0x1005bf558  test    eax, eax
0x1005bf55a  jz      short loc_1005BF5B0
0x1005bf55c  lea     rcx, [rsp+9A8h+FindFileData.cFileName]
0x1005bf564  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1005bf56b  nop     dword ptr [rax+rax+00h]
0x1005bf570  inc     rax
0x1005bf573  cmp     word ptr [rcx+rax*2], 0
0x1005bf578  jnz     short loc_1005BF570
0x1005bf57a  mov     eax, eax
0x1005bf57c  lea     rcx, [rsp+9A8h+FindFileData.cFileName]
0x1005bf584  lea     rcx, [rcx+rax*2]
0x1005bf588  lea     rax, [rsp+9A8h+FindFileData.cFileName]
0x1005bf590  cmp     rcx, rax
0x1005bf593  jbe     short loc_1005BF5B0
0x1005bf595  cmp     word ptr [rcx], 5Fh ; '_'
0x1005bf599  jz      loc_1005BF62C
0x1005bf59f  sub     rcx, 2
0x1005bf5a3  lea     rax, [rsp+9A8h+FindFileData.cFileName]
0x1005bf5ab  cmp     rcx, rax
0x1005bf5ae  ja      short loc_1005BF595
0x1005bf5b0  mov     rdi, [rsp+9A8h+var_968]
0x1005bf5b5  lea     rdx, [rsp+9A8h+FindFileData]; lpFindFileData
0x1005bf5bd  mov     rcx, r14; hFindFile
0x1005bf5c0  call    cs:__imp_FindNextFileW
0x1005bf5c6  test    eax, eax
0x1005bf5c8  jnz     loc_1005BF540
0x1005bf5ce  mov     rax, 7FFFFFFFFFFFFFFFh
0x1005bf5d8  cmp     rbp, rax
0x1005bf5db  jge     short loc_1005BF5F7
0x1005bf5dd  lfence
0x1005bf5e0  mov     edx, dword ptr [rsp+9A8h+var_960]; unsigned __int64
0x1005bf5e4  mov     r8, rdi; wchar_t *
0x1005bf5e7  mov     rcx, [rsp+9A8h+var_958]; wchar_t *
0x1005bf5ec  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1005bf5f1  test    eax, eax
0x1005bf5f3  setns   sil
0x1005bf5f7  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1005bf5fb  jz      short loc_1005BF606
0x1005bf5fd  mov     rcx, r14; hFindFile
0x1005bf600  call    cs:__imp_FindClose
0x1005bf606  mov     eax, esi
0x1005bf608  mov     rcx, [rsp+9A8h+var_58]
0x1005bf610  xor     rcx, rsp; StackCookie
0x1005bf613  call    __security_check_cookie
0x1005bf618  add     rsp, 968h
0x1005bf61f  pop     r15
0x1005bf621  pop     r14
0x1005bf623  pop     r13
0x1005bf625  pop     r12
0x1005bf627  pop     rdi
0x1005bf628  pop     rsi
0x1005bf629  pop     rbp
0x1005bf62a  pop     rbx
0x1005bf62b  retn
0x1005bf62c  add     rcx, 2; String
0x1005bf630  mov     r8d, 0Ah; Radix
0x1005bf636  lea     rdx, [rsp+9A8h+EndPtr]; EndPtr
0x1005bf63b  call    cs:__imp_wcstoll
0x1005bf641  mov     rdi, rax
0x1005bf644  test    rax, rax
0x1005bf647  jle     loc_1005BF5B0
0x1005bf64d  inc     dword ptr [r12]
0x1005bf651  cmp     rax, rbp
0x1005bf654  jge     loc_1005BF5B0
0x1005bf65a  mov     rcx, [r13+18h]
0x1005bf65e  mov     r8, [rcx+8]
0x1005bf662  add     r8, 4
0x1005bf666  add     r8, r15
0x1005bf669  lea     r9, [rsp+9A8h+FindFileData.cFileName]
0x1005bf671  mov     edx, 104h
0x1005bf676  lea     rcx, [rsp+9A8h+var_6D8]
0x1005bf67e  call    cs:qword_1007150E0
0x1005bf684  test    eax, eax
0x1005bf686  jz      loc_1005BF5B0
0x1005bf68c  mov     [rsp+9A8h+hTemplateFile], rsi; hTemplateFile
0x1005bf691  mov     [rsp+9A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1005bf699  mov     dword ptr [rsp+9A8h+dwCreationDisposition], 3; dwCreationDisposition
0x1005bf6a1  xor     r9d, r9d; lpSecurityAttributes
0x1005bf6a4  xor     r8d, r8d; dwShareMode
0x1005bf6a7  mov     edx, 40000000h; dwDesiredAccess
0x1005bf6ac  lea     rcx, [rsp+9A8h+var_6D8]; lpFileName
0x1005bf6b4  call    cs:__imp_CreateFileW
0x1005bf6ba  mov     rbx, rax
0x1005bf6bd  mov     [rsp+9A8h+var_938], rax
0x1005bf6c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1005bf6c6  jz      short loc_1005BF6DA
0x1005bf6c8  mov     rbp, rdi
0x1005bf6cb  lea     rdi, [rsp+9A8h+var_6D8]
0x1005bf6d3  mov     [rsp+9A8h+var_968], rdi
0x1005bf6d8  jmp     short loc_1005BF718
0x1005bf6da  call    cs:__imp_GetLastError
0x1005bf6e0  mov     dword ptr [rsp+9A8h+dwCreationDisposition], eax
0x1005bf6e4  lea     r9, [rsp+9A8h+var_6D8]
0x1005bf6ec  lea     r8, aErrorLogFileLs; "[ERROR] Log file %ls cannot be deleted."...
0x1005bf6f3  mov     edx, 12Ch; unsigned __int64
0x1005bf6f8  lea     rcx, [rsp+9A8h+Buffer]; Buffer
0x1005bf700  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1005bf705  lea     rcx, [rsp+9A8h+Buffer]
0x1005bf70d  call    cs:qword_1007150B0
0x1005bf713  mov     rdi, [rsp+9A8h+var_968]
0x1005bf718  test    rbx, rbx
0x1005bf71b  jz      loc_1005BF5B5
0x1005bf721  mov     rcx, rbx; hObject
0x1005bf724  call    cs:__imp_CloseHandle
0x1005bf72a  jmp     loc_1005BF5B5
```
