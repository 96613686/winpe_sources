# SecurityHelper::OpenThreadToken(void *,ulong,void * *)

- ea: `0x180016704`
- end: `0x18001677a`
- name: `?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z`
- size: `118`
- prototype: `unsigned int __fastcall(HANDLE ThreadHandle, DWORD DesiredAccess, PHANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d38`
- `0x180013528`

## callees

- `0x180016704`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001672d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001672d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016760`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001671d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016750`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001671d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016750`

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
0x180016704  push    rbx
0x180016706  push    rbp
0x180016707  push    rsi
0x180016708  push    rdi
0x180016709  sub     rsp, 28h
0x18001670d  mov     rdi, r8
0x180016710  mov     r9, r8; TokenHandle
0x180016713  xor     r8d, r8d; OpenAsSelf
0x180016716  mov     esi, edx
0x180016718  mov     rbp, rcx
0x18001671b  xor     ebx, ebx
0x18001671d  call    cs:__imp_OpenThreadToken
0x180016724  nop     dword ptr [rax+rax+00h]
0x180016729  test    eax, eax
0x18001672b  jnz     short loc_18001676E
0x18001672d  call    cs:__imp_GetLastError
0x180016734  nop     dword ptr [rax+rax+00h]
0x180016739  mov     ebx, eax
0x18001673b  cmp     eax, 3F0h
0x180016740  jz      short loc_18001676E
0x180016742  xor     ebx, ebx
0x180016744  mov     r9, rdi; TokenHandle
0x180016747  mov     edx, esi; DesiredAccess
0x180016749  mov     rcx, rbp; ThreadHandle
0x18001674c  lea     r8d, [rbx+1]; OpenAsSelf
0x180016750  call    cs:__imp_OpenThreadToken
0x180016757  nop     dword ptr [rax+rax+00h]
0x18001675c  test    eax, eax
0x18001675e  jnz     short loc_18001676E
0x180016760  call    cs:__imp_GetLastError
0x180016767  nop     dword ptr [rax+rax+00h]
0x18001676c  mov     ebx, eax
0x18001676e  mov     eax, ebx
0x180016770  add     rsp, 28h
0x180016774  pop     rdi
0x180016775  pop     rsi
0x180016776  pop     rbp
0x180016777  pop     rbx
0x180016778  retn
```
