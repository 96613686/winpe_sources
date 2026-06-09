# CThreadContext::ImpersonateSelf(void)

- ea: `0x180005540`
- end: `0x1800055d1`
- name: `?ImpersonateSelf@CThreadContext@@QEAAJXZ`
- size: `145`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005b78`

## callees

- `0x180005540`
- `0x180005690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005571`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005571`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005552`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055be`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180005594`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180005594`

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
0x180005540  push    rbx
0x180005542  sub     rsp, 20h
0x180005546  mov     rbx, rcx
0x180005549  mov     [rsp+28h+TokenHandle], 0
0x180005552  call    cs:__imp_GetCurrentThread
0x180005559  nop     dword ptr [rax+rax+00h]
0x18000555e  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180005563  mov     edx, 2000Ch; DesiredAccess
0x180005568  mov     rcx, rax; ThreadHandle
0x18000556b  mov     r8d, 1; OpenAsSelf
0x180005571  call    cs:__imp_OpenThreadToken
0x180005578  nop     dword ptr [rax+rax+00h]
0x18000557d  mov     ecx, eax; int
0x18000557f  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180005584  test    eax, eax
0x180005586  jns     short loc_1800055B9
0x180005588  cmp     eax, 800703F0h
0x18000558d  jnz     short loc_1800055B2
0x18000558f  mov     ecx, 2; ImpersonationLevel
0x180005594  call    cs:__imp_ImpersonateSelf
0x18000559b  nop     dword ptr [rax+rax+00h]
0x1800055a0  mov     ecx, eax; int
0x1800055a2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800055a7  test    eax, eax
0x1800055a9  js      short loc_1800055B2
0x1800055ab  mov     dword ptr [rbx+10h], 1
0x1800055b2  add     rsp, 20h
0x1800055b6  pop     rbx
0x1800055b7  retn
0x1800055b9  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800055be  call    cs:__imp_CloseHandle
0x1800055c5  nop     dword ptr [rax+rax+00h]
0x1800055ca  mov     eax, 1
0x1800055cf  jmp     short loc_1800055B2
```
