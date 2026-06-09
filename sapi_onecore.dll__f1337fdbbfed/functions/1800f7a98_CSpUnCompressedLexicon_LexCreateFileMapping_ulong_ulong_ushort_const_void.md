# CSpUnCompressedLexicon::LexCreateFileMapping(ulong,ulong,ushort const *,void * *)

- ea: `0x1800f7a98`
- end: `0x1800f7c56`
- name: `?LexCreateFileMapping@CSpUnCompressedLexicon@@AEAAJKKPEBGPEAPEAX@Z`
- size: `446`
- prototype: `int(CSpUnCompressedLexicon *__hidden this, unsigned int, unsigned int, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800f7864`

## callees

- `0x18000f110`
- `0x180013ec0`
- `0x1800156f0`
- `0x180019660`
- `0x180045938`
- `0x180079e30`
- `0x1800f7a98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7bfe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7c06`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7bfe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f7c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f7c18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f7c18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f7b9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f7b9f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800f7b3a`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800f7b3a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800f7b8e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800f7b8e`

## string_xrefs

- `0x1800f7bdb`: `Opened`
- `0x1800f7bd4`: `Created`

## pseudocode

```c
__int64 __fastcall CSpUnCompressedLexicon::LexCreateFileMapping(
        CSpUnCompressedLexicon *this,
        __int64 a2,
        DWORD a3,
        const unsigned __int16 *a4,
        void **a5)
{
  HANDLE FileMappingW; // rdi
  char v7; // si
  int Win32Error; // ebx
  DWORD LastError; // eax
  const char *v10; // r8
  int v12; // [rsp+30h] [rbp-268h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-260h]
  WCHAR Name[264]; // [rsp+50h] [rbp-248h] BYREF

  FileMappingW = 0;
  v7 = 0;
  *a5 = 0;
  Win32Error = StringCchCopyW(Name, 0x104u, a4);
  if ( Win32Error >= 0 )
  {
    Win32Error = StringCchCatW(Name, 0x104u, L"-Map-");
    if ( Win32Error >= 0 )
    {
      Win32Error = StringCchCatW(Name, 0x104u, L"GLOBAL");
      if ( Win32Error >= 0 )
      {
        FileMappingW = OpenFileMappingW(0x20006u, 0, Name);
        LastError = GetLastError();
        if ( FileMappingW || LastError != 2 )
        {
          v7 = 0;
        }
        else
        {
          CSpSecurityAttribute::CSpSecurityAttribute((CSpSecurityAttribute *)&v12, 4u, 131078);
          v7 = 1;
          FileMappingW = CreateFileMappingW(
                           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                           (LPSECURITY_ATTRIBUTES)((unsigned __int64)&v12 & -(__int64)(v12 != 0)),
                           4u,
                           0,
                           a3,
                           Name);
          LocalFree(hMem);
        }
        if ( FileMappingW )
        {
          if ( v7 && GetLastError() == 183 )
          {
            Win32Error = -2147418113;
          }
          else
          {
            v10 = "Opened";
            if ( !v7 )
              v10 = "Created";
            DoTraceMessage(16, "%s a lexicon map with name %S", v10, Name);
          }
        }
        else
        {
          Win32Error = SpHrFromLastWin32Error();
        }
      }
    }
  }
  free(0);
  free(0);
  if ( Win32Error >= 0 )
  {
    Win32Error = v7 == 0;
  }
  else if ( FileMappingW )
  {
    CloseHandle(FileMappingW);
    FileMappingW = 0;
  }
  *a5 = FileMappingW;
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800f7a98  mov     [rsp+arg_0], rbx
0x1800f7a9d  push    rbp
0x1800f7a9e  push    rsi
0x1800f7a9f  push    rdi
0x1800f7aa0  push    r14
0x1800f7aa2  push    r15
0x1800f7aa4  sub     rsp, 270h
0x1800f7aab  mov     rax, cs:__security_cookie
0x1800f7ab2  xor     rax, rsp
0x1800f7ab5  mov     [rsp+298h+var_38], rax
0x1800f7abd  mov     r14, [rsp+298h+arg_20]
0x1800f7ac5  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x1800f7aca  mov     ebp, r8d
0x1800f7acd  mov     r15d, 104h
0x1800f7ad3  xor     edi, edi
0x1800f7ad5  mov     r8, r9; unsigned __int16 *
0x1800f7ad8  mov     edx, r15d; unsigned __int64
0x1800f7adb  xor     sil, sil
0x1800f7ade  mov     [r14], rdi
0x1800f7ae1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f7ae6  mov     ebx, eax
0x1800f7ae8  test    eax, eax
0x1800f7aea  js      loc_1800F7BFC
0x1800f7af0  lea     r8, aMap; "-Map-"
0x1800f7af7  mov     edx, r15d; unsigned __int64
0x1800f7afa  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x1800f7aff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f7b04  mov     ebx, eax
0x1800f7b06  test    eax, eax
0x1800f7b08  js      loc_1800F7BFC
0x1800f7b0e  lea     r8, aGlobal; "GLOBAL"
0x1800f7b15  mov     edx, r15d; unsigned __int64
0x1800f7b18  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x1800f7b1d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f7b22  mov     ebx, eax
0x1800f7b24  test    eax, eax
0x1800f7b26  js      loc_1800F7BFC
0x1800f7b2c  mov     esi, 20006h
0x1800f7b31  lea     r8, [rsp+298h+Name]; lpName
0x1800f7b36  mov     ecx, esi; dwDesiredAccess
0x1800f7b38  xor     edx, edx; bInheritHandle
0x1800f7b3a  call    cs:__imp_OpenFileMappingW
0x1800f7b40  mov     rdi, rax
0x1800f7b43  call    cs:__imp_GetLastError
0x1800f7b49  test    rdi, rdi
0x1800f7b4c  jnz     short loc_1800F7BA7
0x1800f7b4e  cmp     eax, 2
0x1800f7b51  jnz     short loc_1800F7BA7
0x1800f7b53  lea     edi, [rax+2]
0x1800f7b56  mov     r8d, esi; unsigned int
0x1800f7b59  mov     edx, edi; unsigned int
0x1800f7b5b  lea     rcx, [rsp+298h+var_268]; this
0x1800f7b60  call    ??0CSpSecurityAttribute@@QEAA@KK@Z; CSpSecurityAttribute::CSpSecurityAttribute(ulong,ulong)
0x1800f7b65  mov     eax, [rsp+298h+var_268]
0x1800f7b69  mov     r8d, edi; flProtect
0x1800f7b6c  neg     eax
0x1800f7b6e  lea     rax, [rsp+298h+var_268]
0x1800f7b73  sbb     rdx, rdx
0x1800f7b76  xor     r9d, r9d; dwMaximumSizeHigh
0x1800f7b79  and     rdx, rax; lpFileMappingAttributes
0x1800f7b7c  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800f7b80  lea     rax, [rsp+298h+Name]
0x1800f7b85  mov     [rsp+298h+lpName], rax; lpName
0x1800f7b8a  mov     [rsp+298h+dwMaximumSizeLow], ebp; dwMaximumSizeLow
0x1800f7b8e  call    cs:__imp_CreateFileMappingW
0x1800f7b94  mov     rcx, [rsp+298h+hMem]; hMem
0x1800f7b99  mov     sil, 1
0x1800f7b9c  mov     rdi, rax
0x1800f7b9f  call    cs:__imp_LocalFree
0x1800f7ba5  jmp     short loc_1800F7BAA
0x1800f7ba7  xor     sil, sil
0x1800f7baa  test    rdi, rdi
0x1800f7bad  jnz     short loc_1800F7BB8
0x1800f7baf  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800f7bb4  mov     ebx, eax
0x1800f7bb6  jmp     short loc_1800F7BFC
0x1800f7bb8  test    sil, sil
0x1800f7bbb  jz      short loc_1800F7BD1
0x1800f7bbd  call    cs:__imp_GetLastError
0x1800f7bc3  cmp     eax, 0B7h
0x1800f7bc8  jnz     short loc_1800F7BD1
0x1800f7bca  mov     ebx, 8000FFFFh
0x1800f7bcf  jmp     short loc_1800F7BFC
0x1800f7bd1  test    sil, sil
0x1800f7bd4  lea     rax, aCreated; "Created"
0x1800f7bdb  lea     r8, aOpened; "Opened"
0x1800f7be2  mov     ecx, 10h; int
0x1800f7be7  cmovz   r8, rax
0x1800f7beb  lea     r9, [rsp+298h+Name]
0x1800f7bf0  lea     rdx, aSALexiconMapWi; "%s a lexicon map with name %S"
0x1800f7bf7  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800f7bfc  xor     ecx, ecx; Block
0x1800f7bfe  call    cs:__imp_free
0x1800f7c04  xor     ecx, ecx; Block
0x1800f7c06  call    cs:__imp_free
0x1800f7c0c  test    ebx, ebx
0x1800f7c0e  jns     short loc_1800F7C22
0x1800f7c10  test    rdi, rdi
0x1800f7c13  jz      short loc_1800F7C2A
0x1800f7c15  mov     rcx, rdi; hObject
0x1800f7c18  call    cs:__imp_CloseHandle
0x1800f7c1e  xor     edi, edi
0x1800f7c20  jmp     short loc_1800F7C2A
0x1800f7c22  xor     ebx, ebx
0x1800f7c24  test    sil, sil
0x1800f7c27  setz    bl
0x1800f7c2a  mov     [r14], rdi
0x1800f7c2d  mov     eax, ebx
0x1800f7c2f  mov     rcx, [rsp+298h+var_38]
0x1800f7c37  xor     rcx, rsp; StackCookie
0x1800f7c3a  call    __security_check_cookie
0x1800f7c3f  mov     rbx, [rsp+298h+arg_0]
0x1800f7c47  add     rsp, 270h
0x1800f7c4e  pop     r15
0x1800f7c50  pop     r14
0x1800f7c52  pop     rdi
0x1800f7c53  pop     rsi
0x1800f7c54  pop     rbp
0x1800f7c55  retn
```
