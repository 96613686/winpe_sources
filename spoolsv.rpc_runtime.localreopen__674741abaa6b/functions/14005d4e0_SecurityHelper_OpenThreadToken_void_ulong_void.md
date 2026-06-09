# SecurityHelper::OpenThreadToken(void *,ulong,void * *)

- ea: `0x14005d4e0`
- end: `0x14005d556`
- name: `?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z`
- size: `118`
- prototype: `unsigned int __fastcall(HANDLE ThreadHandle, DWORD DesiredAccess, PHANDLE TokenHandle, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007090`
- `0x14003d3c4`
- `0x14003d53c`
- `0x140071760`
- `0x14007cd88`

## callees

- `0x14005d4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d53c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d53c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005d4f9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005d52c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005d4f9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005d52c`

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
0x14005d4e0  push    rbx
0x14005d4e2  push    rbp
0x14005d4e3  push    rsi
0x14005d4e4  push    rdi
0x14005d4e5  sub     rsp, 28h
0x14005d4e9  mov     rdi, r8
0x14005d4ec  mov     r9, r8; TokenHandle
0x14005d4ef  xor     r8d, r8d; OpenAsSelf
0x14005d4f2  mov     esi, edx
0x14005d4f4  mov     rbp, rcx
0x14005d4f7  xor     ebx, ebx
0x14005d4f9  call    cs:__imp_OpenThreadToken
0x14005d500  nop     dword ptr [rax+rax+00h]
0x14005d505  test    eax, eax
0x14005d507  jnz     short loc_14005D54A
0x14005d509  call    cs:__imp_GetLastError
0x14005d510  nop     dword ptr [rax+rax+00h]
0x14005d515  mov     ebx, eax
0x14005d517  cmp     eax, 3F0h
0x14005d51c  jz      short loc_14005D54A
0x14005d51e  xor     ebx, ebx
0x14005d520  mov     r9, rdi; TokenHandle
0x14005d523  mov     edx, esi; DesiredAccess
0x14005d525  mov     rcx, rbp; ThreadHandle
0x14005d528  lea     r8d, [rbx+1]; OpenAsSelf
0x14005d52c  call    cs:__imp_OpenThreadToken
0x14005d533  nop     dword ptr [rax+rax+00h]
0x14005d538  test    eax, eax
0x14005d53a  jnz     short loc_14005D54A
0x14005d53c  call    cs:__imp_GetLastError
0x14005d543  nop     dword ptr [rax+rax+00h]
0x14005d548  mov     ebx, eax
0x14005d54a  mov     eax, ebx
0x14005d54c  add     rsp, 28h
0x14005d550  pop     rdi
0x14005d551  pop     rsi
0x14005d552  pop     rbp
0x14005d553  pop     rbx
0x14005d554  retn
```
