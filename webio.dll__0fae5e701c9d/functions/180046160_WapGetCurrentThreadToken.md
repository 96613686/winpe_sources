# WapGetCurrentThreadToken

- ea: `0x180046160`
- end: `0x180046204`
- name: `WapGetCurrentThreadToken`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180046078`

## callees

- `0x180046160`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800461a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800461a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180046181`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180046181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800461d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800461d2`

## pseudocode

```c
__int64 __fastcall WapGetCurrentThreadToken(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // r8d
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    v3 = 0;
    *a1 = TokenHandle;
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1359;
    v3 = 0;
    *a1 = -(__int64)(LastError != 1008);
    if ( LastError != 1008 )
      return LastError;
  }
  return v3;
}

```

## disassembly

```asm
0x180046160  push    rbx
0x180046162  sub     rsp, 30h
0x180046166  mov     rax, cs:__security_cookie
0x18004616d  xor     rax, rsp
0x180046170  mov     [rsp+38h+var_10], rax
0x180046175  mov     rbx, rcx
0x180046178  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180046181  call    cs:__imp_GetCurrentThread
0x180046188  nop     dword ptr [rax+rax+00h]
0x18004618d  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180046192  mov     edx, 2000Ch; DesiredAccess
0x180046197  mov     rcx, rax; ThreadHandle
0x18004619a  mov     r8d, 1; OpenAsSelf
0x1800461a0  call    cs:__imp_OpenThreadToken
0x1800461a7  nop     dword ptr [rax+rax+00h]
0x1800461ac  test    eax, eax
0x1800461ae  jz      short loc_1800461D2
0x1800461b0  mov     rcx, [rsp+38h+TokenHandle]
0x1800461b5  xor     r8d, r8d
0x1800461b8  mov     [rbx], rcx
0x1800461bb  mov     eax, r8d
0x1800461be  mov     rcx, [rsp+38h+var_10]
0x1800461c3  xor     rcx, rsp; StackCookie
0x1800461c6  call    __security_check_cookie
0x1800461cb  add     rsp, 30h
0x1800461cf  pop     rbx
0x1800461d0  retn
0x1800461d2  call    cs:__imp_GetLastError
0x1800461d9  nop     dword ptr [rax+rax+00h]
0x1800461de  test    eax, eax
0x1800461e0  mov     ecx, 54Fh
0x1800461e5  cmovz   eax, ecx
0x1800461e8  lea     ecx, [rax-3F0h]
0x1800461ee  neg     ecx
0x1800461f0  sbb     rdx, rdx
0x1800461f3  xor     r8d, r8d
0x1800461f6  cmp     eax, 3F0h
0x1800461fb  mov     [rbx], rdx
0x1800461fe  cmovnz  r8d, eax
0x180046202  jmp     short loc_1800461BB
```
