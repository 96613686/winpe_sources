# IsRunningInAppContainer(void *,bool *)

- ea: `0x18007b4d0`
- end: `0x18007b5a6`
- name: `?IsRunningInAppContainer@@YAJPEAXPEA_N@Z`
- size: `214`
- prototype: `int(void *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e9a0`
- `0x180053690`

## callees

- `0x18007b454`
- `0x18007b4d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007b525`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007b525`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007b4ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007b4ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007b505`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007b505`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007b538`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007b538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b542`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b593`

## pseudocode

```c
__int64 __fastcall IsRunningInAppContainer(void *a1, bool *a2)
{
  HANDLE CurrentThread; // rax
  void *v4; // rcx
  signed int LastError; // eax
  signed int v6; // ebx
  HANDLE CurrentProcess; // rax
  signed int v8; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_2;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_2:
      v4 = TokenHandle;
LABEL_15:
      v6 = IsAppContainerToken(v4, a2);
      goto LABEL_16;
    }
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
  }
  else
  {
    v4 = 0;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( v6 >= 0 )
      goto LABEL_15;
  }
LABEL_16:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007b4d0  mov     [rsp+arg_8], rbx
0x18007b4d5  mov     [rsp+TokenHandle], rcx
0x18007b4da  push    rdi
0x18007b4db  sub     rsp, 20h
0x18007b4df  mov     rdi, rdx
0x18007b4e2  mov     byte ptr [rdx], 0
0x18007b4e5  mov     [rsp+28h+TokenHandle], 0
0x18007b4ee  call    cs:__imp_GetCurrentThread
0x18007b4f4  mov     edx, 8; DesiredAccess
0x18007b4f9  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18007b4fe  mov     rcx, rax; ThreadHandle
0x18007b501  lea     r8d, [rdx-7]; OpenAsSelf
0x18007b505  call    cs:__imp_OpenThreadToken
0x18007b50b  test    eax, eax
0x18007b50d  jz      short loc_18007B516
0x18007b50f  mov     rcx, [rsp+28h+TokenHandle]
0x18007b514  jmp     short loc_18007B57F
0x18007b516  call    cs:__imp_GetLastError
0x18007b51c  mov     ebx, eax
0x18007b51e  cmp     eax, 3F0h
0x18007b523  jnz     short loc_18007B563
0x18007b525  call    cs:__imp_GetCurrentProcess
0x18007b52b  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18007b530  mov     edx, 8; DesiredAccess
0x18007b535  mov     rcx, rax; ProcessHandle
0x18007b538  call    cs:__imp_OpenProcessToken
0x18007b53e  test    eax, eax
0x18007b540  jnz     short loc_18007B50F
0x18007b542  call    cs:__imp_GetLastError
0x18007b548  mov     ebx, eax
0x18007b54a  test    eax, eax
0x18007b54c  jle     short loc_18007B557
0x18007b54e  movzx   ebx, ax
0x18007b551  or      ebx, 80070000h
0x18007b557  test    ebx, ebx
0x18007b559  mov     eax, 80004005h
0x18007b55e  cmovns  ebx, eax
0x18007b561  jmp     short loc_18007B589
0x18007b563  xor     ecx, ecx; void *
0x18007b565  test    eax, eax
0x18007b567  jz      short loc_18007B576
0x18007b569  jle     short loc_18007B57B
0x18007b56b  movzx   ebx, ax
0x18007b56e  or      ebx, 80070000h
0x18007b574  jmp     short loc_18007B57B
0x18007b576  mov     ebx, 80004005h
0x18007b57b  test    ebx, ebx
0x18007b57d  js      short loc_18007B589
0x18007b57f  mov     rdx, rdi; bool *
0x18007b582  call    ?IsAppContainerToken@@YAJPEAXPEA_N@Z; IsAppContainerToken(void *,bool *)
0x18007b587  mov     ebx, eax
0x18007b589  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18007b58e  test    rcx, rcx
0x18007b591  jz      short loc_18007B599
0x18007b593  call    cs:__imp_CloseHandle
0x18007b599  mov     eax, ebx
0x18007b59b  mov     rbx, [rsp+28h+arg_8]
0x18007b5a0  add     rsp, 20h
0x18007b5a4  pop     rdi
0x18007b5a5  retn
```
