# AutoTokenImpersonate::Impersonate(void *)

- ea: `0x1800766cc`
- end: `0x1800767c9`
- name: `?Impersonate@AutoTokenImpersonate@@QEAAJPEAX@Z`
- size: `253`
- prototype: `__int64 __fastcall(AutoTokenImpersonate *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800760f0`
- `0x18009a970`
- `0x1800bd448`

## callees

- `0x1800766cc`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007671c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007671c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180076712`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180076712`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800766f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800766f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007673e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800767a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007673e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800767a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076757`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076757`

## pseudocode

```c
__int64 __fastcall AutoTokenImpersonate::Impersonate(AutoTokenImpersonate *this, void *a2)
{
  HANDLE CurrentThread; // rax
  signed int v4; // ebx
  signed int v6; // eax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+28h] [rbp-20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
  {
    if ( RevertToSelf() )
    {
      v4 = 0;
      *(_QWORD *)this = TokenHandle;
      TokenHandle = 0;
      *((_DWORD *)this + 2) = 1;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147418113;
    }
  }
  else if ( GetLastError() == 1008 )
  {
    v4 = 0;
  }
  else
  {
    v6 = GetLastError();
    v4 = v6;
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147418113;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800766cc  mov     [rsp+arg_8], rbx
0x1800766d1  push    rdi
0x1800766d2  sub     rsp, 40h
0x1800766d6  mov     rax, cs:__security_cookie
0x1800766dd  xor     rax, rsp
0x1800766e0  mov     [rsp+48h+var_18], rax
0x1800766e5  mov     rdi, rcx
0x1800766e8  mov     [rsp+48h+var_24], 0
0x1800766f0  mov     [rsp+48h+TokenHandle], 0
0x1800766f9  call    cs:__imp_GetCurrentThread
0x1800766ff  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180076704  mov     edx, 2000Eh; DesiredAccess
0x180076709  mov     rcx, rax; ThreadHandle
0x18007670c  mov     r8d, 1; OpenAsSelf
0x180076712  call    cs:__imp_OpenThreadToken
0x180076718  test    eax, eax
0x18007671a  jz      short loc_18007673E
0x18007671c  call    cs:__imp_RevertToSelf
0x180076722  test    eax, eax
0x180076724  jz      short loc_1800767A0
0x180076726  mov     rcx, [rsp+48h+TokenHandle]
0x18007672b  xor     ebx, ebx
0x18007672d  mov     [rdi], rcx
0x180076730  mov     [rsp+48h+TokenHandle], rbx
0x180076735  mov     dword ptr [rdi+8], 1
0x18007673c  jmp     short loc_18007674D
0x18007673e  call    cs:__imp_GetLastError
0x180076744  cmp     eax, 3F0h
0x180076749  jnz     short loc_180076777
0x18007674b  xor     ebx, ebx
0x18007674d  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180076752  test    rcx, rcx
0x180076755  jz      short loc_18007675D
0x180076757  call    cs:__imp_CloseHandle
0x18007675d  mov     eax, ebx
0x18007675f  mov     rcx, [rsp+48h+var_18]
0x180076764  xor     rcx, rsp; StackCookie
0x180076767  call    __security_check_cookie
0x18007676c  mov     rbx, [rsp+48h+arg_8]
0x180076771  add     rsp, 40h
0x180076775  pop     rdi
0x180076776  retn
0x180076777  call    cs:__imp_GetLastError
0x18007677d  mov     ebx, eax
0x18007677f  test    eax, eax
0x180076781  jle     short loc_18007678C
0x180076783  movzx   ebx, ax
0x180076786  or      ebx, 80070000h
0x18007678c  test    ebx, ebx
0x18007678e  mov     [rsp+48h+var_24], 184h
0x180076796  mov     eax, 8000FFFFh
0x18007679b  cmovns  ebx, eax
0x18007679e  jmp     short loc_18007674D
0x1800767a0  call    cs:__imp_GetLastError
0x1800767a6  mov     ebx, eax
0x1800767a8  test    eax, eax
0x1800767aa  jle     short loc_1800767B5
0x1800767ac  movzx   ebx, ax
0x1800767af  or      ebx, 80070000h
0x1800767b5  test    ebx, ebx
0x1800767b7  mov     [rsp+48h+var_24], 197h
0x1800767bf  mov     eax, 8000FFFFh
0x1800767c4  cmovns  ebx, eax
0x1800767c7  jmp     short loc_18007674D
```
