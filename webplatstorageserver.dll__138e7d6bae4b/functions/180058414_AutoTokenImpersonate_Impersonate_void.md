# AutoTokenImpersonate::Impersonate(void *)

- ea: `0x180058414`
- end: `0x180058511`
- name: `?Impersonate@AutoTokenImpersonate@@QEAAJPEAX@Z`
- size: `253`
- prototype: `__int64 __fastcall(AutoTokenImpersonate *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008cc70`

## callees

- `0x180058414`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180058441`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180058441`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005845a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005845a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800584a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800584a8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005849e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005849e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800584f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800584f1`

## pseudocode

```c
__int64 __fastcall AutoTokenImpersonate::Impersonate(AutoTokenImpersonate *this, void *a2)
{
  HANDLE CurrentThread; // rax
  signed int v4; // eax
  signed int v5; // ebx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+28h] [rbp-20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
  {
    if ( RevertToSelf() )
    {
      v5 = 0;
      *(_QWORD *)this = TokenHandle;
      TokenHandle = 0;
      *((_DWORD *)this + 2) = 1;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147418113;
    }
  }
  else if ( GetLastError() == 1008 )
  {
    v5 = 0;
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147418113;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180058414  mov     [rsp+arg_8], rbx
0x180058419  push    rdi
0x18005841a  sub     rsp, 40h
0x18005841e  mov     rax, cs:__security_cookie
0x180058425  xor     rax, rsp
0x180058428  mov     [rsp+48h+var_18], rax
0x18005842d  mov     rdi, rcx
0x180058430  mov     [rsp+48h+var_24], 0
0x180058438  mov     [rsp+48h+TokenHandle], 0
0x180058441  call    cs:__imp_GetCurrentThread
0x180058447  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18005844c  mov     edx, 2000Eh; DesiredAccess
0x180058451  mov     rcx, rax; ThreadHandle
0x180058454  mov     r8d, 1; OpenAsSelf
0x18005845a  call    cs:__imp_OpenThreadToken
0x180058460  test    eax, eax
0x180058462  jnz     short loc_18005849E
0x180058464  call    cs:__imp_GetLastError
0x18005846a  cmp     eax, 3F0h
0x18005846f  jz      short loc_18005849A
0x180058471  call    cs:__imp_GetLastError
0x180058477  mov     ebx, eax
0x180058479  test    eax, eax
0x18005847b  jle     short loc_180058486
0x18005847d  movzx   ebx, ax
0x180058480  or      ebx, 80070000h
0x180058486  test    ebx, ebx
0x180058488  mov     [rsp+48h+var_24], 184h
0x180058490  mov     eax, 8000FFFFh
0x180058495  cmovns  ebx, eax
0x180058498  jmp     short loc_1800584E7
0x18005849a  xor     ebx, ebx
0x18005849c  jmp     short loc_1800584E7
0x18005849e  call    cs:__imp_RevertToSelf
0x1800584a4  test    eax, eax
0x1800584a6  jnz     short loc_1800584D1
0x1800584a8  call    cs:__imp_GetLastError
0x1800584ae  mov     ebx, eax
0x1800584b0  test    eax, eax
0x1800584b2  jle     short loc_1800584BD
0x1800584b4  movzx   ebx, ax
0x1800584b7  or      ebx, 80070000h
0x1800584bd  test    ebx, ebx
0x1800584bf  mov     [rsp+48h+var_24], 197h
0x1800584c7  mov     eax, 8000FFFFh
0x1800584cc  cmovns  ebx, eax
0x1800584cf  jmp     short loc_1800584E7
0x1800584d1  mov     rcx, [rsp+48h+TokenHandle]
0x1800584d6  xor     ebx, ebx
0x1800584d8  mov     [rdi], rcx
0x1800584db  mov     [rsp+48h+TokenHandle], rbx
0x1800584e0  mov     dword ptr [rdi+8], 1
0x1800584e7  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800584ec  test    rcx, rcx
0x1800584ef  jz      short loc_1800584F7
0x1800584f1  call    cs:__imp_CloseHandle
0x1800584f7  mov     eax, ebx
0x1800584f9  mov     rcx, [rsp+48h+var_18]
0x1800584fe  xor     rcx, rsp; StackCookie
0x180058501  call    __security_check_cookie
0x180058506  mov     rbx, [rsp+48h+arg_8]
0x18005850b  add     rsp, 40h
0x18005850f  pop     rdi
0x180058510  retn
```
