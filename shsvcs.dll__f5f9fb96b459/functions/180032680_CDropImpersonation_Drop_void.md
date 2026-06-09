# CDropImpersonation::Drop(void)

- ea: `0x180032680`
- end: `0x1800326fe`
- name: `?Drop@CDropImpersonation@@QEAAJXZ`
- size: `126`
- prototype: `__int64 __fastcall(CDropImpersonation *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800083e0`

## callees

- `0x180032680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003269a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003269a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800326ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800326ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326c4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800326df`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800326df`

## pseudocode

```c
__int64 __fastcall CDropImpersonation::Drop(CDropImpersonation *this)
{
  unsigned int v1; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax

  v1 = 0;
  if ( *((_QWORD *)this + 1)
    || (CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, 4u, 0, (PHANDLE)this + 1)) )
  {
    if ( *(_BYTE *)this || RevertToSelf() )
    {
      *(_BYTE *)this = 1;
      return v1;
    }
  }
  else if ( GetLastError() == 1008 )
  {
    return v1;
  }
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v1;
}

```

## disassembly

```asm
0x180032680  mov     [rsp+arg_0], rbx
0x180032685  mov     [rsp+arg_8], rsi
0x18003268a  push    rdi
0x18003268b  sub     rsp, 20h
0x18003268f  xor     ebx, ebx
0x180032691  mov     rdi, rcx
0x180032694  cmp     [rcx+8], rbx
0x180032698  jnz     short loc_1800326DB
0x18003269a  call    cs:__imp_GetCurrentThread
0x1800326a0  lea     r9, [rdi+8]; TokenHandle
0x1800326a4  xor     r8d, r8d; OpenAsSelf
0x1800326a7  mov     rcx, rax; ThreadHandle
0x1800326aa  lea     edx, [rbx+4]; DesiredAccess
0x1800326ad  call    cs:__imp_OpenThreadToken
0x1800326b3  test    eax, eax
0x1800326b5  jnz     short loc_1800326DB
0x1800326b7  call    cs:__imp_GetLastError
0x1800326bd  cmp     eax, 3F0h
0x1800326c2  jz      short loc_1800326EC
0x1800326c4  call    cs:__imp_GetLastError
0x1800326ca  mov     ebx, eax
0x1800326cc  test    eax, eax
0x1800326ce  jle     short loc_1800326EC
0x1800326d0  movzx   ebx, ax
0x1800326d3  or      ebx, 80070000h
0x1800326d9  jmp     short loc_1800326EC
0x1800326db  cmp     [rdi], bl
0x1800326dd  jnz     short loc_1800326E9
0x1800326df  call    cs:__imp_RevertToSelf
0x1800326e5  test    eax, eax
0x1800326e7  jz      short loc_1800326C4
0x1800326e9  mov     byte ptr [rdi], 1
0x1800326ec  mov     rsi, [rsp+28h+arg_8]
0x1800326f1  mov     eax, ebx
0x1800326f3  mov     rbx, [rsp+28h+arg_0]
0x1800326f8  add     rsp, 20h
0x1800326fc  pop     rdi
0x1800326fd  retn
```
