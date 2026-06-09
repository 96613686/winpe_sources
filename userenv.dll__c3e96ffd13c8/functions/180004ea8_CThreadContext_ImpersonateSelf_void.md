# CThreadContext::ImpersonateSelf(void)

- ea: `0x180004ea8`
- end: `0x180004f20`
- name: `?ImpersonateSelf@CThreadContext@@QEAAJXZ`
- size: `120`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000542c`

## callees

- `0x180004ea8`
- `0x180004fc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004ed3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004ed3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004eba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004eba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f13`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180004ef0`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180004ef0`

## pseudocode

```c
__int64 __fastcall CThreadContext::ImpersonateSelf(CThreadContext *this)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // eax
  __int64 result; // rax
  BOOL v5; // eax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle);
  result = ResultFromWin32Bool(v3);
  if ( (int)result >= 0 )
  {
    CloseHandle(TokenHandle);
    return 1;
  }
  else if ( (_DWORD)result == -2147023888 )
  {
    v5 = ImpersonateSelf(SecurityImpersonation);
    result = ResultFromWin32Bool(v5);
    if ( (int)result >= 0 )
      *((_DWORD *)this + 4) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180004ea8  push    rbx
0x180004eaa  sub     rsp, 20h
0x180004eae  mov     rbx, rcx
0x180004eb1  mov     [rsp+28h+TokenHandle], 0
0x180004eba  call    cs:__imp_GetCurrentThread
0x180004ec0  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180004ec5  mov     edx, 2000Ch; DesiredAccess
0x180004eca  mov     rcx, rax; ThreadHandle
0x180004ecd  mov     r8d, 1; OpenAsSelf
0x180004ed3  call    cs:__imp_OpenThreadToken
0x180004ed9  mov     ecx, eax; int
0x180004edb  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180004ee0  test    eax, eax
0x180004ee2  jns     short loc_180004F0E
0x180004ee4  cmp     eax, 800703F0h
0x180004ee9  jnz     short loc_180004F08
0x180004eeb  mov     ecx, 2; ImpersonationLevel
0x180004ef0  call    cs:__imp_ImpersonateSelf
0x180004ef6  mov     ecx, eax; int
0x180004ef8  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180004efd  test    eax, eax
0x180004eff  js      short loc_180004F08
0x180004f01  mov     dword ptr [rbx+10h], 1
0x180004f08  add     rsp, 20h
0x180004f0c  pop     rbx
0x180004f0d  retn
0x180004f0e  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180004f13  call    cs:__imp_CloseHandle
0x180004f19  mov     eax, 1
0x180004f1e  jmp     short loc_180004F08
```
