# SecurityHelper::OpenThreadToken(void *,ulong,void * *)

- ea: `0x180014d10`
- end: `0x180014d6d`
- name: `?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z`
- size: `93`
- prototype: `unsigned int __fastcall(HANDLE ThreadHandle, DWORD DesiredAccess, PHANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d08`
- `0x180011df8`

## callees

- `0x180014d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014d29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014d50`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014d29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014d50`

## pseudocode

```c
__int64 __fastcall SecurityHelper::OpenThreadToken(
        HANDLE ThreadHandle,
        DWORD DesiredAccess,
        PHANDLE TokenHandle,
        void **a4)
{
  DWORD LastError; // ebx

  LastError = 0;
  if ( !OpenThreadToken(ThreadHandle, DesiredAccess, 0, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      LastError = 0;
      if ( !OpenThreadToken(ThreadHandle, DesiredAccess, 1, TokenHandle) )
        return GetLastError();
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180014d10  push    rbx
0x180014d12  push    rbp
0x180014d13  push    rsi
0x180014d14  push    rdi
0x180014d15  sub     rsp, 28h
0x180014d19  mov     rdi, r8
0x180014d1c  mov     r9, r8; TokenHandle
0x180014d1f  xor     r8d, r8d; OpenAsSelf
0x180014d22  mov     esi, edx
0x180014d24  mov     rbp, rcx
0x180014d27  xor     ebx, ebx
0x180014d29  call    cs:__imp_OpenThreadToken
0x180014d2f  test    eax, eax
0x180014d31  jnz     short loc_180014D62
0x180014d33  call    cs:__imp_GetLastError
0x180014d39  mov     ebx, eax
0x180014d3b  cmp     eax, 3F0h
0x180014d40  jz      short loc_180014D62
0x180014d42  xor     ebx, ebx
0x180014d44  mov     r9, rdi; TokenHandle
0x180014d47  mov     edx, esi; DesiredAccess
0x180014d49  mov     rcx, rbp; ThreadHandle
0x180014d4c  lea     r8d, [rbx+1]; OpenAsSelf
0x180014d50  call    cs:__imp_OpenThreadToken
0x180014d56  test    eax, eax
0x180014d58  jnz     short loc_180014D62
0x180014d5a  call    cs:__imp_GetLastError
0x180014d60  mov     ebx, eax
0x180014d62  mov     eax, ebx
0x180014d64  add     rsp, 28h
0x180014d68  pop     rdi
0x180014d69  pop     rsi
0x180014d6a  pop     rbp
0x180014d6b  pop     rbx
0x180014d6c  retn
```
