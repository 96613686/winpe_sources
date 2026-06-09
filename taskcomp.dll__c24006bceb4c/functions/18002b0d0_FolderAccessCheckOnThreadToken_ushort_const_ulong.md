# FolderAccessCheckOnThreadToken(ushort const *,ulong)

- ea: `0x18002b0d0`
- end: `0x18002b1ad`
- name: `?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z`
- size: `221`
- prototype: `signed int __fastcall(LPCWSTR lpFileName, DWORD DesiredAccess)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800069e0`
- `0x180028070`
- `0x180028170`
- `0x1800282d0`
- `0x1800283b0`
- `0x180028620`

## callees

- `0x18002af30`
- `0x18002b0d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b104`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b168`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b104`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b168`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b0ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b151`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b0ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b151`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b184`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b184`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002b147`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002b147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b195`

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
0x18002b0d0  mov     [rsp+arg_0], rbx
0x18002b0d5  mov     [rsp+arg_8], rsi
0x18002b0da  push    rdi
0x18002b0db  sub     rsp, 20h
0x18002b0df  mov     edi, edx
0x18002b0e1  mov     [rsp+28h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18002b0ea  mov     rsi, rcx
0x18002b0ed  call    cs:__imp_GetCurrentThread
0x18002b0f3  mov     edx, 8; DesiredAccess
0x18002b0f8  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18002b0fd  mov     rcx, rax; ThreadHandle
0x18002b100  lea     r8d, [rdx-7]; OpenAsSelf
0x18002b104  call    cs:__imp_OpenThreadToken
0x18002b10a  test    eax, eax
0x18002b10c  jz      short loc_18002B122
0x18002b10e  mov     rdx, [rsp+28h+TokenHandle]; ClientToken
0x18002b113  mov     r8d, edi; DesiredAccess
0x18002b116  mov     rcx, rsi; lpFileName
0x18002b119  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x18002b11e  mov     ebx, eax
0x18002b120  jmp     short loc_18002B18A
0x18002b122  call    cs:__imp_GetLastError
0x18002b128  cmp     eax, 3F0h
0x18002b12d  jz      short loc_18002B13D
0x18002b12f  test    eax, eax
0x18002b131  jle     short loc_18002B19D
0x18002b133  movzx   eax, ax
0x18002b136  or      eax, 80070000h
0x18002b13b  jmp     short loc_18002B19D
0x18002b13d  mov     ecx, 2; ImpersonationLevel
0x18002b142  mov     ebx, 80070005h
0x18002b147  call    cs:__imp_ImpersonateSelf
0x18002b14d  test    eax, eax
0x18002b14f  jz      short loc_18002B18A
0x18002b151  call    cs:__imp_GetCurrentThread
0x18002b157  mov     edx, 8; DesiredAccess
0x18002b15c  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18002b161  mov     rcx, rax; ThreadHandle
0x18002b164  lea     r8d, [rdx-7]; OpenAsSelf
0x18002b168  call    cs:__imp_OpenThreadToken
0x18002b16e  test    eax, eax
0x18002b170  jz      short loc_18002B184
0x18002b172  mov     rdx, [rsp+28h+TokenHandle]; ClientToken
0x18002b177  mov     r8d, edi; DesiredAccess
0x18002b17a  mov     rcx, rsi; lpFileName
0x18002b17d  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x18002b182  mov     ebx, eax
0x18002b184  call    cs:__imp_RevertToSelf
0x18002b18a  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18002b18f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b193  jz      short loc_18002B19B
0x18002b195  call    cs:__imp_CloseHandle
0x18002b19b  mov     eax, ebx
0x18002b19d  mov     rbx, [rsp+28h+arg_0]
0x18002b1a2  mov     rsi, [rsp+28h+arg_8]
0x18002b1a7  add     rsp, 20h
0x18002b1ab  pop     rdi
0x18002b1ac  retn
```
