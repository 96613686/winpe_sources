# IsRunningInAppContainer(void *,bool *)

- ea: `0x18007435c`
- end: `0x180074408`
- name: `?IsRunningInAppContainer@@YAJPEAXPEA_N@Z`
- size: `172`
- prototype: `int(void *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005aacc`

## callees

- `0x180026ec0`
- `0x1800299c8`
- `0x1800742e0`
- `0x18007435c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800743a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800743a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800743b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800743b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180074393`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180074393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007437a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007437a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800743c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800743c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800743f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800743f5`

## pseudocode

```c
__int64 __fastcall IsRunningInAppContainer(void *a1, bool *a2)
{
  HANDLE CurrentThread; // rax
  void *v4; // rcx
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  int Error; // eax
  unsigned int v8; // ebx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_2;
  LastError = GetLastError();
  if ( LastError != 1008 )
  {
    Error = ResultFromKnownError(LastError);
LABEL_7:
    v4 = 0;
    v8 = Error;
    if ( Error < 0 )
      goto LABEL_9;
    goto LABEL_8;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    goto LABEL_7;
  }
LABEL_2:
  v4 = TokenHandle;
LABEL_8:
  v8 = IsAppContainerToken(v4, a2);
LABEL_9:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v8;
}

```

## disassembly

```asm
0x18007435c  mov     [rsp+arg_8], rbx
0x180074361  mov     [rsp+TokenHandle], rcx
0x180074366  push    rdi
0x180074367  sub     rsp, 20h
0x18007436b  mov     rdi, rdx
0x18007436e  mov     byte ptr [rdx], 0
0x180074371  mov     [rsp+28h+TokenHandle], 0
0x18007437a  call    cs:__imp_GetCurrentThread
0x180074380  mov     ebx, 8
0x180074385  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18007438a  mov     rcx, rax; ThreadHandle
0x18007438d  mov     edx, ebx; DesiredAccess
0x18007438f  lea     r8d, [rbx-7]; OpenAsSelf
0x180074393  call    cs:__imp_OpenThreadToken
0x180074399  test    eax, eax
0x18007439b  jz      short loc_1800743A4
0x18007439d  mov     rcx, [rsp+28h+TokenHandle]
0x1800743a2  jmp     short loc_1800743E1
0x1800743a4  call    cs:__imp_GetLastError
0x1800743aa  cmp     eax, 3F0h
0x1800743af  jnz     short loc_1800743D2
0x1800743b1  call    cs:__imp_GetCurrentProcess
0x1800743b7  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800743bc  mov     edx, ebx; DesiredAccess
0x1800743be  mov     rcx, rax; ProcessHandle
0x1800743c1  call    cs:__imp_OpenProcessToken
0x1800743c7  test    eax, eax
0x1800743c9  jnz     short loc_18007439D
0x1800743cb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800743d0  jmp     short loc_1800743D9
0x1800743d2  mov     ecx, eax; unsigned int
0x1800743d4  call    ?ResultFromKnownError@@YAJK@Z; ResultFromKnownError(ulong)
0x1800743d9  xor     ecx, ecx; void *
0x1800743db  mov     ebx, eax
0x1800743dd  test    eax, eax
0x1800743df  js      short loc_1800743EB
0x1800743e1  mov     rdx, rdi; bool *
0x1800743e4  call    ?IsAppContainerToken@@YAJPEAXPEA_N@Z; IsAppContainerToken(void *,bool *)
0x1800743e9  mov     ebx, eax
0x1800743eb  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800743f0  test    rcx, rcx
0x1800743f3  jz      short loc_1800743FB
0x1800743f5  call    cs:__imp_CloseHandle
0x1800743fb  mov     eax, ebx
0x1800743fd  mov     rbx, [rsp+28h+arg_8]
0x180074402  add     rsp, 20h
0x180074406  pop     rdi
0x180074407  retn
```
