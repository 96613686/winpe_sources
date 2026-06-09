# CreateArchiveImpl::WriteEntryToArchive(archive_entry *,void *)

- ea: `0x18005e604`
- end: `0x18005ea43`
- name: `?WriteEntryToArchive@CreateArchiveImpl@@AEAAJPEAUarchive_entry@@PEAX@Z`
- size: `1087`
- prototype: `int(CreateArchiveImpl *__hidden this, struct archive_entry *, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18005c004`
- `0x18005cb10`

## callees

- `0x180031e94`
- `0x180033aa8`
- `0x18003547c`
- `0x180036f50`
- `0x18003edd4`
- `0x18005df28`
- `0x18005e604`
- `0x180071010`

## import_xrefs

- `archiveint!archive_error_string` at `0x18005e660`
- `archiveint!archive_error_string` at `0x18005e8ea`
- `archiveint!archive_error_string` at `0x18005e660`
- `archiveint!archive_error_string` at `0x18005e8ea`
- `archiveint!archive_errno` at `0x18005e641`
- `archiveint!archive_errno` at `0x18005e8cb`
- `archiveint!archive_errno` at `0x18005e641`
- `archiveint!archive_errno` at `0x18005e8cb`
- `archiveint!archive_write_data` at `0x18005e706`
- `archiveint!archive_write_data` at `0x18005e706`
- `archiveint!archive_write_header` at `0x18005e62f`
- `archiveint!archive_write_header` at `0x18005e62f`
- `archiveint!archive_entry_size` at `0x18005e6c1`
- `archiveint!archive_entry_size` at `0x18005e6c1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005e79d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005e79d`

## string_xrefs

- `0x18005e682`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e6a8`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e7b3`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e7f0`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e82b`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e867`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e8ab`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e90c`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e948`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e96f`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e9ab`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005e9eb`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005ea27`: `shell\ext\zip\archive\archivecreate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateArchiveImpl::WriteEntryToArchive(CreateArchiveImpl *this, struct archive_entry *a2, void *a3)
{
  int v6; // eax
  unsigned int LastError; // edi
  const char *v8; // rax
  __int64 v10; // rsi
  const char *v12; // r9
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int lpOverlapped; // [rsp+20h] [rbp-68h]
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !(unsigned int)archive_write_header(*((_QWORD *)this + 8)) )
  {
    if ( archive_entry_size(a2) )
    {
      v10 = *((_QWORD *)this + 13);
      NumberOfBytesRead = 0;
      if ( !ReadFile(a3, *((LPVOID *)this + 24), *((_DWORD *)this + 50), &NumberOfBytesRead, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x2AE,
                      (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                      v12);
        *((_QWORD *)this + 13) = v10;
        v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 11) + 72LL))(
                *((_QWORD *)this + 11),
                v10,
                *((_QWORD *)this + 12));
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2A7,
            (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
            (const char *)(unsigned int)v13,
            lpOverlapped);
        return LastError;
      }
      v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 11) + 72LL))(
              *((_QWORD *)this + 11),
              *((_QWORD *)this + 13),
              *((_QWORD *)this + 12));
      LastError = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B2,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)(unsigned int)v14);
        *((_QWORD *)this + 13) = v10;
        v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 11) + 72LL))(
                *((_QWORD *)this + 11),
                v10,
                *((_QWORD *)this + 12));
        if ( v15 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2A7,
            (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
            (const char *)(unsigned int)v15,
            lpOverlapped);
        return LastError;
      }
    }
    return 0;
  }
  v6 = archive_errno(*((_QWORD *)this + 8));
  if ( v6 )
  {
    LastError = HRESULT_FROM_ERRNO(v6);
    if ( (LastError & 0x80000000) != 0 )
    {
      v8 = (const char *)archive_error_string(*((_QWORD *)this + 8));
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x29D,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)LastError,
        (int)"archive error: %hs",
        v8);
    }
  }
  else
  {
    LastError = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29D,
      (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
      (const char *)0x80004005LL);
  }
  return LastError;
}

```

## disassembly

```asm
0x18005e604  push    rbx
0x18005e606  push    rbp
0x18005e607  push    rsi
0x18005e608  push    rdi
0x18005e609  push    r12
0x18005e60b  push    r14
0x18005e60d  push    r15
0x18005e60f  sub     rsp, 50h
0x18005e613  mov     rax, cs:__security_cookie
0x18005e61a  xor     rax, rsp
0x18005e61d  mov     [rsp+88h+var_48], rax
0x18005e622  mov     r12, r8
0x18005e625  mov     rdi, rdx
0x18005e628  mov     rbx, rcx
0x18005e62b  mov     rcx, [rcx+40h]
0x18005e62f  call    cs:__imp_archive_write_header
0x18005e635  test    eax, eax
0x18005e637  jz      loc_18005E6BE
0x18005e63d  mov     rcx, [rbx+40h]
0x18005e641  call    cs:__imp_archive_errno
0x18005e647  test    eax, eax
0x18005e649  jz      short loc_18005E698
0x18005e64b  mov     ecx, eax; int
0x18005e64d  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x18005e652  mov     edi, eax
0x18005e654  test    eax, eax
0x18005e656  jns     loc_18005E802
0x18005e65c  mov     rcx, [rbx+40h]
0x18005e660  call    cs:__imp_archive_error_string
0x18005e666  mov     rcx, [rsp+88h]; this
0x18005e66e  mov     [rsp+88h+var_60], rax; char *
0x18005e673  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x18005e67a  mov     [rsp+88h+lpOverlapped], rax; int
0x18005e67f  mov     r9d, edi; char *
0x18005e682  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e689  mov     edx, 29Dh; void *
0x18005e68e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005e693  jmp     loc_18005E802
0x18005e698  mov     rcx, [rsp+88h]
0x18005e6a0  mov     edi, 80004005h
0x18005e6a5  mov     r9d, edi
0x18005e6a8  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e6af  mov     edx, 29Dh
0x18005e6b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e6b9  jmp     loc_18005E802
0x18005e6be  mov     rcx, rdi
0x18005e6c1  call    cs:__imp_archive_entry_size
0x18005e6c7  test    rax, rax
0x18005e6ca  jnz     short loc_18005E6D3
0x18005e6cc  xor     eax, eax
0x18005e6ce  jmp     loc_18005E804
0x18005e6d3  mov     rsi, [rbx+68h]
0x18005e6d7  xor     r14d, r14d
0x18005e6da  mov     [rsp+88h+NumberOfBytesRead], r14d
0x18005e6df  mov     [rsp+88h+lpOverlapped], r14
0x18005e6e4  jmp     loc_18005E787
0x18005e6e9  mov     eax, [rsp+88h+NumberOfBytesRead]
0x18005e6ed  test    eax, eax
0x18005e6ef  jz      loc_18005E9C2
0x18005e6f5  mov     r15, [rbx+0C0h]
0x18005e6fc  mov     r8d, eax
0x18005e6ff  mov     rdx, r15
0x18005e702  mov     rcx, [rbx+40h]
0x18005e706  call    cs:__imp_archive_write_data
0x18005e70c  mov     rdi, rax
0x18005e70f  test    rax, rax
0x18005e712  js      loc_18005E8C7
0x18005e718  mov     eax, [rsp+88h+NumberOfBytesRead]
0x18005e71c  sub     eax, edi
0x18005e71e  mov     [rsp+88h+NumberOfBytesRead], eax
0x18005e722  add     [rbx+68h], rdi
0x18005e726  add     r14d, edi
0x18005e729  cmp     r14d, 0F4240h
0x18005e730  jb      short loc_18005E773
0x18005e732  mov     rcx, [rbx+58h]
0x18005e736  mov     rax, [rcx]
0x18005e739  mov     rax, [rax+38h]
0x18005e73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e742  test    eax, eax
0x18005e744  jnz     loc_18005E87D
0x18005e74a  xor     r14d, r14d
0x18005e74d  mov     rcx, [rbx+58h]
0x18005e751  mov     rax, [rcx]
0x18005e754  mov     r8, [rbx+60h]
0x18005e758  mov     rdx, [rbx+68h]
0x18005e75c  mov     rax, [rax+48h]
0x18005e760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e765  mov     ebp, eax
0x18005e767  test    eax, eax
0x18005e769  js      loc_18005E820
0x18005e76f  mov     eax, [rsp+88h+NumberOfBytesRead]
0x18005e773  add     r15, rdi
0x18005e776  test    eax, eax
0x18005e778  jnz     short loc_18005E6FC
0x18005e77a  mov     [rsp+88h+NumberOfBytesRead], eax
0x18005e77e  mov     [rsp+88h+lpOverlapped], 0; int
0x18005e787  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005e78c  mov     r8d, [rbx+0C8h]; nNumberOfBytesToRead
0x18005e793  mov     rdx, [rbx+0C0h]; lpBuffer
0x18005e79a  mov     rcx, r12; hFile
0x18005e79d  call    cs:__imp_ReadFile
0x18005e7a3  test    eax, eax
0x18005e7a5  jnz     loc_18005E6E9
0x18005e7ab  mov     rcx, [rsp+88h]; this
0x18005e7b3  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e7ba  mov     edx, 2AEh; void *
0x18005e7bf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005e7c4  mov     edi, eax
0x18005e7c6  mov     [rbx+68h], rsi
0x18005e7ca  mov     rcx, [rbx+58h]
0x18005e7ce  mov     rdx, [rcx]
0x18005e7d1  mov     rax, [rdx+48h]
0x18005e7d5  mov     r8, [rbx+60h]
0x18005e7d9  mov     rdx, rsi
0x18005e7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7e1  mov     rcx, [rsp+88h]; this
0x18005e7e9  test    eax, eax
0x18005e7eb  jns     short loc_18005E802
0x18005e7ed  mov     r9d, eax; char *
0x18005e7f0  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e7f7  mov     edx, 2A7h; void *
0x18005e7fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e801  nop
0x18005e802  mov     eax, edi
0x18005e804  mov     rcx, [rsp+88h+var_48]
0x18005e809  xor     rcx, rsp; StackCookie
0x18005e80c  call    __security_check_cookie
0x18005e811  add     rsp, 50h
0x18005e815  pop     r15
0x18005e817  pop     r14
0x18005e819  pop     r12
0x18005e81b  pop     rdi
0x18005e81c  pop     rsi
0x18005e81d  pop     rbp
0x18005e81e  pop     rbx
0x18005e81f  retn
0x18005e820  mov     rcx, [rsp+88h]
0x18005e828  mov     r9d, ebp
0x18005e82b  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e832  mov     edx, 2D1h
0x18005e837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e83c  nop
0x18005e83d  mov     [rbx+68h], rsi
0x18005e841  mov     rcx, [rbx+58h]
0x18005e845  mov     rax, [rcx]
0x18005e848  mov     r8, [rbx+60h]
0x18005e84c  mov     rdx, rsi
0x18005e84f  mov     rax, [rax+48h]
0x18005e853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e858  mov     rcx, [rsp+88h]; this
0x18005e860  test    eax, eax
0x18005e862  jns     short loc_18005E879
0x18005e864  mov     r9d, eax; char *
0x18005e867  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e86e  mov     edx, 2A7h; void *
0x18005e873  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e878  nop
0x18005e879  mov     eax, ebp
0x18005e87b  jmp     short loc_18005E804
0x18005e87d  mov     byte ptr [rbx+78h], 1
0x18005e881  mov     [rbx+68h], rsi
0x18005e885  mov     rcx, [rbx+58h]
0x18005e889  mov     rax, [rcx]
0x18005e88c  mov     r8, [rbx+60h]
0x18005e890  mov     rdx, rsi
0x18005e893  mov     rax, [rax+48h]
0x18005e897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e89c  mov     rcx, [rsp+88h]; this
0x18005e8a4  test    eax, eax
0x18005e8a6  jns     short loc_18005E8BD
0x18005e8a8  mov     r9d, eax; char *
0x18005e8ab  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e8b2  mov     edx, 2A7h; void *
0x18005e8b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e8bc  nop
0x18005e8bd  mov     eax, 800704C7h
0x18005e8c2  jmp     loc_18005E804
0x18005e8c7  mov     rcx, [rbx+40h]
0x18005e8cb  call    cs:__imp_archive_errno
0x18005e8d1  test    eax, eax
0x18005e8d3  jz      loc_18005E95F
0x18005e8d9  mov     ecx, eax; int
0x18005e8db  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x18005e8e0  mov     edi, eax
0x18005e8e2  test    eax, eax
0x18005e8e4  jns     short loc_18005E91E
0x18005e8e6  mov     rcx, [rbx+40h]
0x18005e8ea  call    cs:__imp_archive_error_string
0x18005e8f0  mov     rcx, [rsp+88h]; this
0x18005e8f8  mov     [rsp+88h+var_60], rax; char *
0x18005e8fd  lea     rax, aArchiveErrorHs; "archive error: %hs"
0x18005e904  mov     [rsp+88h+lpOverlapped], rax; int
0x18005e909  mov     r9d, edi; char *
0x18005e90c  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e913  mov     edx, 2BEh; void *
0x18005e918  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005e91d  nop
0x18005e91e  mov     [rbx+68h], rsi
0x18005e922  mov     rcx, [rbx+58h]
0x18005e926  mov     rax, [rcx]
0x18005e929  mov     r8, [rbx+60h]
0x18005e92d  mov     rdx, rsi
0x18005e930  mov     rax, [rax+48h]
0x18005e934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e939  mov     rcx, [rsp+88h]; this
0x18005e941  test    eax, eax
0x18005e943  jns     short loc_18005E95A
0x18005e945  mov     r9d, eax; char *
0x18005e948  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e94f  mov     edx, 2A7h; void *
0x18005e954  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e959  nop
0x18005e95a  jmp     loc_18005E802
0x18005e95f  mov     rcx, [rsp+88h]
0x18005e967  mov     edi, 80004005h
0x18005e96c  mov     r9d, edi
0x18005e96f  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e976  mov     edx, 2BEh
0x18005e97b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e980  nop
0x18005e981  mov     [rbx+68h], rsi
0x18005e985  mov     rcx, [rbx+58h]
0x18005e989  mov     rax, [rcx]
0x18005e98c  mov     r8, [rbx+60h]
0x18005e990  mov     rdx, rsi
0x18005e993  mov     rax, [rax+48h]
0x18005e997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e99c  mov     rcx, [rsp+88h]; this
0x18005e9a4  test    eax, eax
0x18005e9a6  jns     short loc_18005E9BD
0x18005e9a8  mov     r9d, eax; char *
0x18005e9ab  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e9b2  mov     edx, 2A7h; void *
0x18005e9b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e9bc  nop
0x18005e9bd  jmp     loc_18005E802
0x18005e9c2  mov     rcx, [rbx+58h]
0x18005e9c6  mov     rax, [rcx]
0x18005e9c9  mov     r8, [rbx+60h]
0x18005e9cd  mov     rdx, [rbx+68h]
0x18005e9d1  mov     rax, [rax+48h]
0x18005e9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9da  mov     edi, eax
0x18005e9dc  test    eax, eax
0x18005e9de  jns     short loc_18005EA3E
0x18005e9e0  mov     rcx, [rsp+88h]
0x18005e9e8  mov     r9d, eax
0x18005e9eb  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e9f2  mov     edx, 2B2h
0x18005e9f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e9fc  nop
0x18005e9fd  mov     [rbx+68h], rsi
0x18005ea01  mov     rcx, [rbx+58h]
0x18005ea05  mov     rdx, [rcx]
0x18005ea08  mov     rax, [rdx+48h]
0x18005ea0c  mov     r8, [rbx+60h]
0x18005ea10  mov     rdx, rsi
0x18005ea13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea18  mov     rcx, [rsp+88h]; this
0x18005ea20  test    eax, eax
0x18005ea22  jns     short loc_18005EA39
0x18005ea24  mov     r9d, eax; char *
0x18005ea27  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005ea2e  mov     edx, 2A7h; void *
0x18005ea33  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ea38  nop
0x18005ea39  jmp     loc_18005E802
0x18005ea3e  jmp     loc_18005E6CC
```
