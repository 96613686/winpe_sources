# _ImpersonateProcessToken(void *,void * *)

- ea: `0x1800d91c0`
- end: `0x1800d92d3`
- name: `?_ImpersonateProcessToken@@YAJPEAXPEAPEAX@Z`
- size: `275`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d92dc`
- `0x1800d9530`

## callees

- `0x18003d244`
- `0x1800d91c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d9202`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d9202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d91e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d91e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d9249`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d9249`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d929e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d92b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d929e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d92b4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800d9269`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800d9269`

## pseudocode

```c
__int64 __fastcall _ImpersonateProcessToken(HANDLE ProcessHandle, void **a2)
{
  HANDLE CurrentThread; // rax
  int Error; // eax
  int v6; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  HANDLE hToken; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    v6 = Error;
    if ( Error == -2147023888 )
    {
      TokenHandle = 0;
    }
    else if ( Error < 0 )
    {
      return (unsigned int)v6;
    }
  }
  hToken = 0;
  if ( OpenProcessToken(ProcessHandle, 0xEu, &hToken) || (v6 = ResultFromKnownLastError(), v6 >= 0) )
  {
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      v6 = 0;
    }
    else
    {
      v6 = ResultFromKnownLastError();
      if ( v6 < 0 )
      {
LABEL_11:
        CloseHandle(hToken);
        goto LABEL_12;
      }
    }
    *a2 = TokenHandle;
    TokenHandle = 0;
    goto LABEL_11;
  }
LABEL_12:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800d91c0  mov     [rsp+arg_0], rbx
0x1800d91c5  mov     [rsp+arg_18], rsi
0x1800d91ca  push    rdi
0x1800d91cb  sub     rsp, 20h
0x1800d91cf  mov     rdi, rdx
0x1800d91d2  mov     qword ptr [rdx], 0
0x1800d91d9  mov     rsi, rcx
0x1800d91dc  mov     [rsp+28h+TokenHandle], 0
0x1800d91e5  call    cs:__imp_GetCurrentThread
0x1800d91ec  nop     dword ptr [rax+rax+00h]
0x1800d91f1  mov     edx, 0Eh; DesiredAccess
0x1800d91f6  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800d91fb  mov     rcx, rax; ThreadHandle
0x1800d91fe  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800d9202  call    cs:__imp_OpenThreadToken
0x1800d9209  nop     dword ptr [rax+rax+00h]
0x1800d920e  test    eax, eax
0x1800d9210  jnz     short loc_1800D9233
0x1800d9212  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d9217  mov     ebx, eax
0x1800d9219  cmp     eax, 800703F0h
0x1800d921e  jnz     short loc_1800D922B
0x1800d9220  mov     [rsp+28h+TokenHandle], 0
0x1800d9229  jmp     short loc_1800D9233
0x1800d922b  test    eax, eax
0x1800d922d  js      loc_1800D92C0
0x1800d9233  lea     r8, [rsp+28h+hToken]; TokenHandle
0x1800d9238  mov     [rsp+28h+hToken], 0
0x1800d9241  mov     edx, 0Eh; DesiredAccess
0x1800d9246  mov     rcx, rsi; ProcessHandle
0x1800d9249  call    cs:__imp_OpenProcessToken
0x1800d9250  nop     dword ptr [rax+rax+00h]
0x1800d9255  test    eax, eax
0x1800d9257  jnz     short loc_1800D9264
0x1800d9259  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d925e  mov     ebx, eax
0x1800d9260  test    eax, eax
0x1800d9262  js      short loc_1800D92AA
0x1800d9264  mov     rcx, [rsp+28h+hToken]; hToken
0x1800d9269  call    cs:__imp_ImpersonateLoggedOnUser
0x1800d9270  nop     dword ptr [rax+rax+00h]
0x1800d9275  test    eax, eax
0x1800d9277  jz      short loc_1800D927D
0x1800d9279  xor     ebx, ebx
0x1800d927b  jmp     short loc_1800D9288
0x1800d927d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d9282  mov     ebx, eax
0x1800d9284  test    eax, eax
0x1800d9286  js      short loc_1800D9299
0x1800d9288  mov     rax, [rsp+28h+TokenHandle]
0x1800d928d  mov     [rdi], rax
0x1800d9290  mov     [rsp+28h+TokenHandle], 0
0x1800d9299  mov     rcx, [rsp+28h+hToken]; hObject
0x1800d929e  call    cs:__imp_CloseHandle
0x1800d92a5  nop     dword ptr [rax+rax+00h]
0x1800d92aa  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800d92af  test    rcx, rcx
0x1800d92b2  jz      short loc_1800D92C0
0x1800d92b4  call    cs:__imp_CloseHandle
0x1800d92bb  nop     dword ptr [rax+rax+00h]
0x1800d92c0  mov     rsi, [rsp+28h+arg_18]
0x1800d92c5  mov     eax, ebx
0x1800d92c7  mov     rbx, [rsp+28h+arg_0]
0x1800d92cc  add     rsp, 20h
0x1800d92d0  pop     rdi
0x1800d92d1  retn
```
