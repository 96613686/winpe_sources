# CTransactedFileSystem::Commit(void)

- ea: `0x18001d410`
- end: `0x18001d470`
- name: `?Commit@CTransactedFileSystem@@UEAAJXZ`
- size: `96`
- prototype: `__int64 __fastcall(CTransactedFileSystem *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d43c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d43c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d455`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d455`
- `ktmw32!CommitTransaction` at `0x18001d42e`
- `ktmw32!CommitTransaction` at `0x18001d42e`

## pseudocode

```c
__int64 __fastcall CTransactedFileSystem::Commit(CTransactedFileSystem *this)
{
  void *v2; // rcx
  unsigned int v3; // ebx
  signed int LastError; // eax

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 == (void *)-1LL )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    if ( CommitTransaction(v2) )
    {
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(*((HANDLE *)this + 1));
    *((_QWORD *)this + 1) = -1;
  }
  return v3;
}

```

## disassembly

```asm
0x18001d410  mov     [rsp+arg_0], rbx
0x18001d415  push    rdi
0x18001d416  sub     rsp, 20h
0x18001d41a  mov     rdi, rcx
0x18001d41d  mov     rcx, [rcx+8]; TransactionHandle
0x18001d421  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d425  jnz     short loc_18001D42E
0x18001d427  mov     ebx, 80070057h
0x18001d42c  jmp     short loc_18001D463
0x18001d42e  call    cs:__imp_CommitTransaction
0x18001d434  test    eax, eax
0x18001d436  jz      short loc_18001D43C
0x18001d438  xor     ebx, ebx
0x18001d43a  jmp     short loc_18001D451
0x18001d43c  call    cs:__imp_GetLastError
0x18001d442  mov     ebx, eax
0x18001d444  test    eax, eax
0x18001d446  jle     short loc_18001D451
0x18001d448  movzx   ebx, ax
0x18001d44b  or      ebx, 80070000h
0x18001d451  mov     rcx, [rdi+8]; hObject
0x18001d455  call    cs:__imp_CloseHandle
0x18001d45b  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18001d463  mov     eax, ebx
0x18001d465  mov     rbx, [rsp+28h+arg_0]
0x18001d46a  add     rsp, 20h
0x18001d46e  pop     rdi
0x18001d46f  retn
```
