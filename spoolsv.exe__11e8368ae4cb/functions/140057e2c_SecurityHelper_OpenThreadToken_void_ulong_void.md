# SecurityHelper::OpenThreadToken(void *,ulong,void * *)

- ea: `0x140057e2c`
- end: `0x140057e89`
- name: `?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z`
- size: `93`
- prototype: `unsigned int __fastcall(HANDLE ThreadHandle, DWORD DesiredAccess, PHANDLE TokenHandle, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400065f0`
- `0x140039f08`
- `0x14003a044`
- `0x14006abd0`
- `0x140075b58`

## callees

- `0x140057e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140057e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140057e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140057e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140057e76`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140057e45`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140057e6c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140057e45`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140057e6c`

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
0x140057e2c  push    rbx
0x140057e2e  push    rbp
0x140057e2f  push    rsi
0x140057e30  push    rdi
0x140057e31  sub     rsp, 28h
0x140057e35  mov     rdi, r8
0x140057e38  mov     r9, r8; TokenHandle
0x140057e3b  xor     r8d, r8d; OpenAsSelf
0x140057e3e  mov     esi, edx
0x140057e40  mov     rbp, rcx
0x140057e43  xor     ebx, ebx
0x140057e45  call    cs:__imp_OpenThreadToken
0x140057e4b  test    eax, eax
0x140057e4d  jnz     short loc_140057E7E
0x140057e4f  call    cs:__imp_GetLastError
0x140057e55  mov     ebx, eax
0x140057e57  cmp     eax, 3F0h
0x140057e5c  jz      short loc_140057E7E
0x140057e5e  xor     ebx, ebx
0x140057e60  mov     r9, rdi; TokenHandle
0x140057e63  mov     edx, esi; DesiredAccess
0x140057e65  mov     rcx, rbp; ThreadHandle
0x140057e68  lea     r8d, [rbx+1]; OpenAsSelf
0x140057e6c  call    cs:__imp_OpenThreadToken
0x140057e72  test    eax, eax
0x140057e74  jnz     short loc_140057E7E
0x140057e76  call    cs:__imp_GetLastError
0x140057e7c  mov     ebx, eax
0x140057e7e  mov     eax, ebx
0x140057e80  add     rsp, 28h
0x140057e84  pop     rdi
0x140057e85  pop     rsi
0x140057e86  pop     rbp
0x140057e87  pop     rbx
0x140057e88  retn
```
