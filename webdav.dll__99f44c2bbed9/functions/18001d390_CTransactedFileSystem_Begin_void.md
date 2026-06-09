# CTransactedFileSystem::Begin(void *)

- ea: `0x18001d390`
- end: `0x18001d400`
- name: `?Begin@CTransactedFileSystem@@UEAAJPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(CTransactedFileSystem *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001d390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d3e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d3e4`
- `ktmw32!CreateTransaction` at `0x18001d3d4`
- `ktmw32!CreateTransaction` at `0x18001d3d4`

## pseudocode

```c
signed int __fastcall CTransactedFileSystem::Begin(CTransactedFileSystem *this, void *a2)
{
  signed int result; // eax
  HANDLE Transaction; // rax

  if ( *((_QWORD *)this + 1) != -1 )
    return -2147024809;
  *((_QWORD *)this + 1) = a2;
  if ( a2 != (void *)-1LL )
    return 0;
  Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, 0);
  *((_QWORD *)this + 1) = Transaction;
  if ( Transaction != (HANDLE)-1LL )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001d390  push    rbx
0x18001d392  sub     rsp, 40h
0x18001d396  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x18001d39b  mov     rbx, rcx
0x18001d39e  jz      short loc_18001D3A7
0x18001d3a0  mov     eax, 80070057h
0x18001d3a5  jmp     short loc_18001D3FA
0x18001d3a7  mov     [rcx+8], rdx
0x18001d3ab  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001d3af  jnz     short loc_18001D3F8
0x18001d3b1  mov     [rsp+48h+Description], 0; Description
0x18001d3ba  xor     r9d, r9d; IsolationLevel
0x18001d3bd  mov     [rsp+48h+Timeout], 0; Timeout
0x18001d3c5  xor     r8d, r8d; CreateOptions
0x18001d3c8  xor     edx, edx; UOW
0x18001d3ca  mov     [rsp+48h+IsolationFlags], 0; IsolationFlags
0x18001d3d2  xor     ecx, ecx; lpTransactionAttributes
0x18001d3d4  call    cs:__imp_CreateTransaction
0x18001d3da  mov     [rbx+8], rax
0x18001d3de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d3e2  jnz     short loc_18001D3F8
0x18001d3e4  call    cs:__imp_GetLastError
0x18001d3ea  test    eax, eax
0x18001d3ec  jle     short loc_18001D3FA
0x18001d3ee  movzx   eax, ax
0x18001d3f1  or      eax, 80070000h
0x18001d3f6  jmp     short loc_18001D3FA
0x18001d3f8  xor     eax, eax
0x18001d3fa  add     rsp, 40h
0x18001d3fe  pop     rbx
0x18001d3ff  retn
```
