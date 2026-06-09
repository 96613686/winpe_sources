# FolderAccessCheckOnThreadToken(ushort const *,ulong)

- ea: `0x18002cc94`
- end: `0x18002cda9`
- name: `?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z`
- size: `277`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD DesiredAccess)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006e10`
- `0x180029920`
- `0x180029a20`
- `0x180029b90`
- `0x180029c70`
- `0x180029ef0`

## callees

- `0x18002cad4`
- `0x18002cc94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ccce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002cd51`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ccce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002cd51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ccb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002cd34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ccb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002cd34`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002cd73`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002cd73`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002cd24`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002cd24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cd8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cd8a`

## pseudocode

```c
signed int __fastcall FolderAccessCheckOnThreadToken(LPCWSTR lpFileName, DWORD DesiredAccess)
{
  HANDLE CurrentThread; // rax
  int v5; // ebx
  signed int result; // eax
  HANDLE v7; // rax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v5 = FolderAccessCheck(lpFileName, TokenHandle, DesiredAccess);
LABEL_10:
    if ( TokenHandle != (void *)-1LL )
      CloseHandle(TokenHandle);
    return v5;
  }
  result = GetLastError();
  if ( result == 1008 )
  {
    v5 = -2147024891;
    if ( ImpersonateSelf(SecurityImpersonation) )
    {
      v7 = GetCurrentThread();
      if ( OpenThreadToken(v7, 8u, 1, &TokenHandle) )
        v5 = FolderAccessCheck(lpFileName, TokenHandle, DesiredAccess);
      RevertToSelf();
    }
    goto LABEL_10;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002cc94  mov     [rsp+arg_0], rbx
0x18002cc99  mov     [rsp+arg_8], rsi
0x18002cc9e  push    rdi
0x18002cc9f  sub     rsp, 20h
0x18002cca3  mov     edi, edx
0x18002cca5  mov     [rsp+28h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18002ccae  mov     rsi, rcx
0x18002ccb1  call    cs:__imp_GetCurrentThread
0x18002ccb8  nop     dword ptr [rax+rax+00h]
0x18002ccbd  mov     edx, 8; DesiredAccess
0x18002ccc2  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18002ccc7  mov     rcx, rax; ThreadHandle
0x18002ccca  lea     r8d, [rdx-7]; OpenAsSelf
0x18002ccce  call    cs:__imp_OpenThreadToken
0x18002ccd5  nop     dword ptr [rax+rax+00h]
0x18002ccda  test    eax, eax
0x18002ccdc  jz      short loc_18002CCF5
0x18002ccde  mov     rdx, [rsp+28h+TokenHandle]; ClientToken
0x18002cce3  mov     r8d, edi; DesiredAccess
0x18002cce6  mov     rcx, rsi; lpFileName
0x18002cce9  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x18002ccee  mov     ebx, eax
0x18002ccf0  jmp     loc_18002CD7F
0x18002ccf5  call    cs:__imp_GetLastError
0x18002ccfc  nop     dword ptr [rax+rax+00h]
0x18002cd01  cmp     eax, 3F0h
0x18002cd06  jz      short loc_18002CD1A
0x18002cd08  test    eax, eax
0x18002cd0a  jle     loc_18002CD98
0x18002cd10  movzx   eax, ax
0x18002cd13  or      eax, 80070000h
0x18002cd18  jmp     short loc_18002CD98
0x18002cd1a  mov     ecx, 2; ImpersonationLevel
0x18002cd1f  mov     ebx, 80070005h
0x18002cd24  call    cs:__imp_ImpersonateSelf
0x18002cd2b  nop     dword ptr [rax+rax+00h]
0x18002cd30  test    eax, eax
0x18002cd32  jz      short loc_18002CD7F
0x18002cd34  call    cs:__imp_GetCurrentThread
0x18002cd3b  nop     dword ptr [rax+rax+00h]
0x18002cd40  mov     edx, 8; DesiredAccess
0x18002cd45  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18002cd4a  mov     rcx, rax; ThreadHandle
0x18002cd4d  lea     r8d, [rdx-7]; OpenAsSelf
0x18002cd51  call    cs:__imp_OpenThreadToken
0x18002cd58  nop     dword ptr [rax+rax+00h]
0x18002cd5d  test    eax, eax
0x18002cd5f  jz      short loc_18002CD73
0x18002cd61  mov     rdx, [rsp+28h+TokenHandle]; ClientToken
0x18002cd66  mov     r8d, edi; DesiredAccess
0x18002cd69  mov     rcx, rsi; lpFileName
0x18002cd6c  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x18002cd71  mov     ebx, eax
0x18002cd73  call    cs:__imp_RevertToSelf
0x18002cd7a  nop     dword ptr [rax+rax+00h]
0x18002cd7f  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18002cd84  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002cd88  jz      short loc_18002CD96
0x18002cd8a  call    cs:__imp_CloseHandle
0x18002cd91  nop     dword ptr [rax+rax+00h]
0x18002cd96  mov     eax, ebx
0x18002cd98  mov     rbx, [rsp+28h+arg_0]
0x18002cd9d  mov     rsi, [rsp+28h+arg_8]
0x18002cda2  add     rsp, 20h
0x18002cda6  pop     rdi
0x18002cda7  retn
```
