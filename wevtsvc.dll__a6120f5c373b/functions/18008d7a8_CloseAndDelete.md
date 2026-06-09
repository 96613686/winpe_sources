# CloseAndDelete

- ea: `0x18008d7a8`
- end: `0x18008d85d`
- name: `CloseAndDelete`
- size: `181`
- prototype: `__int64 __fastcall(HANDLE *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18008aed8`
- `0x1800b23e8`
- `0x1800b29b8`

## callees

- `0x18003420c`
- `0x18005ff90`
- `0x18008d7a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d814`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x18008d7c1`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x18008d800`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x18008d7c1`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x18008d800`

## pseudocode

```c
__int64 __fastcall CloseAndDelete(HANDLE *a1)
{
  char *v2; // rbx
  DWORD LastError; // ebx
  char *v5; // [rsp+30h] [rbp+8h] BYREF
  char *v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (char *)ReOpenFile(*a1, 0, 7u, 0);
  v6 = v2;
  if ( v2 == (char *)-1LL || v2 + 1 == (char *)1 )
  {
    LastError = GetLastError();
  }
  else
  {
    tlx::unique_any<tlx::file_handle_traits>::reset(a1, 0);
    v5 = (char *)ReOpenFile(v2, 0x10000u, 7u, 0x4000000u);
    if ( v5 == (char *)-1LL || v5 + 1 == (char *)1 )
    {
      LastError = GetLastError();
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v5);
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v6);
    }
    else
    {
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v5);
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v6);
      LastError = 0;
    }
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(a1);
  return LastError;
}

```

## disassembly

```asm
0x18008d7a8  mov     [rsp+arg_10], rbx
0x18008d7ad  push    rdi
0x18008d7ae  sub     rsp, 20h
0x18008d7b2  xor     r9d, r9d; dwFlagsAndAttributes
0x18008d7b5  mov     rdi, rcx
0x18008d7b8  mov     rcx, [rcx]; hOriginalFile
0x18008d7bb  xor     edx, edx; dwDesiredAccess
0x18008d7bd  lea     r8d, [r9+7]; dwShareMode
0x18008d7c1  call    cs:__imp_ReOpenFile
0x18008d7c7  mov     rbx, rax
0x18008d7ca  mov     [rsp+28h+arg_8], rax
0x18008d7cf  inc     rax
0x18008d7d2  cmp     rax, 1
0x18008d7d6  ja      short loc_18008D7E2
0x18008d7d8  call    cs:__imp_GetLastError
0x18008d7de  mov     ebx, eax
0x18008d7e0  jmp     short loc_18008D848
0x18008d7e2  xor     edx, edx
0x18008d7e4  mov     rcx, rdi
0x18008d7e7  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18008d7ec  mov     edx, 10000h; dwDesiredAccess
0x18008d7f1  mov     r9d, 4000000h; dwFlagsAndAttributes
0x18008d7f7  mov     r8d, 7; dwShareMode
0x18008d7fd  mov     rcx, rbx; hOriginalFile
0x18008d800  call    cs:__imp_ReOpenFile
0x18008d806  mov     [rsp+28h+arg_0], rax
0x18008d80b  inc     rax
0x18008d80e  cmp     rax, 1
0x18008d812  ja      short loc_18008D832
0x18008d814  call    cs:__imp_GetLastError
0x18008d81a  lea     rcx, [rsp+28h+arg_0]
0x18008d81f  mov     ebx, eax
0x18008d821  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008d826  lea     rcx, [rsp+28h+arg_8]
0x18008d82b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008d830  jmp     short loc_18008D848
0x18008d832  lea     rcx, [rsp+28h+arg_0]
0x18008d837  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008d83c  lea     rcx, [rsp+28h+arg_8]
0x18008d841  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008d846  xor     ebx, ebx
0x18008d848  mov     rcx, rdi
0x18008d84b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008d850  mov     eax, ebx
0x18008d852  mov     rbx, [rsp+28h+arg_10]
0x18008d857  add     rsp, 20h
0x18008d85b  pop     rdi
0x18008d85c  retn
```
