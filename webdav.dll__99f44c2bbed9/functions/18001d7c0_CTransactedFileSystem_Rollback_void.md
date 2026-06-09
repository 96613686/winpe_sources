# CTransactedFileSystem::Rollback(void)

- ea: `0x18001d7c0`
- end: `0x18001d820`
- name: `?Rollback@CTransactedFileSystem@@UEAAJXZ`
- size: `96`
- prototype: `__int64 __fastcall(CTransactedFileSystem *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001d7c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d805`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d805`
- `ktmw32!RollbackTransaction` at `0x18001d7de`
- `ktmw32!RollbackTransaction` at `0x18001d7de`

## pseudocode

```c
__int64 __fastcall CTransactedFileSystem::Rollback(CTransactedFileSystem *this)
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
    if ( RollbackTransaction(v2) )
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
0x18001d7c0  mov     [rsp+arg_0], rbx
0x18001d7c5  push    rdi
0x18001d7c6  sub     rsp, 20h
0x18001d7ca  mov     rdi, rcx
0x18001d7cd  mov     rcx, [rcx+8]; TransactionHandle
0x18001d7d1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d7d5  jnz     short loc_18001D7DE
0x18001d7d7  mov     ebx, 80070057h
0x18001d7dc  jmp     short loc_18001D813
0x18001d7de  call    cs:__imp_RollbackTransaction
0x18001d7e4  test    eax, eax
0x18001d7e6  jz      short loc_18001D7EC
0x18001d7e8  xor     ebx, ebx
0x18001d7ea  jmp     short loc_18001D801
0x18001d7ec  call    cs:__imp_GetLastError
0x18001d7f2  mov     ebx, eax
0x18001d7f4  test    eax, eax
0x18001d7f6  jle     short loc_18001D801
0x18001d7f8  movzx   ebx, ax
0x18001d7fb  or      ebx, 80070000h
0x18001d801  mov     rcx, [rdi+8]; hObject
0x18001d805  call    cs:__imp_CloseHandle
0x18001d80b  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18001d813  mov     eax, ebx
0x18001d815  mov     rbx, [rsp+28h+arg_0]
0x18001d81a  add     rsp, 20h
0x18001d81e  pop     rdi
0x18001d81f  retn
```
