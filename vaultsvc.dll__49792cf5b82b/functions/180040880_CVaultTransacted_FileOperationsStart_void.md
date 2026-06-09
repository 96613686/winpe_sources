# CVaultTransacted::FileOperationsStart(void)

- ea: `0x180040880`
- end: `0x1800408d8`
- name: `?FileOperationsStart@CVaultTransacted@@UEAAKXZ`
- size: `88`
- prototype: `unsigned int __fastcall(CVaultTransacted *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180040880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408c9`
- `ktmw32!CreateTransaction` at `0x1800408ac`
- `ktmw32!CreateTransaction` at `0x1800408ac`

## pseudocode

```c
DWORD __fastcall CVaultTransacted::FileOperationsStart(CVaultTransacted *this)
{
  HANDLE Transaction; // rax

  Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, 0);
  *((_QWORD *)this + 1) = Transaction;
  if ( Transaction != (HANDLE)-1LL )
    return 0;
  *((_QWORD *)this + 1) = 0;
  return GetLastError();
}

```

## disassembly

```asm
0x180040880  push    rbx
0x180040882  sub     rsp, 40h
0x180040886  mov     rbx, rcx
0x180040889  mov     [rsp+48h+Description], 0; Description
0x180040892  mov     [rsp+48h+Timeout], 0; Timeout
0x18004089a  xor     ecx, ecx; lpTransactionAttributes
0x18004089c  xor     r9d, r9d; IsolationLevel
0x18004089f  mov     [rsp+48h+IsolationFlags], 0; IsolationFlags
0x1800408a7  xor     r8d, r8d; CreateOptions
0x1800408aa  xor     edx, edx; UOW
0x1800408ac  call    cs:__imp_CreateTransaction
0x1800408b2  mov     [rbx+8], rax
0x1800408b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800408ba  jnz     short loc_1800408D0
0x1800408bc  mov     qword ptr [rbx+8], 0
0x1800408c4  add     rsp, 40h
0x1800408c8  pop     rbx
0x1800408c9  jmp     cs:__imp_GetLastError
0x1800408d0  xor     eax, eax
0x1800408d2  add     rsp, 40h
0x1800408d6  pop     rbx
0x1800408d7  retn
```
