# WxIsThreadAppContainer(int *)

- ea: `0x1800a8728`
- end: `0x1800a8840`
- name: `?WxIsThreadAppContainer@@YAJPEAH@Z`
- size: `280`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a83b4`

## callees

- `0x1800701d0`
- `0x1800a8728`
- `0x1800a8848`
- `0x18014a7a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a87b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a87b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a8757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a8757`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a8770`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a8770`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a87d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a87d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a87c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a87c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a879b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a879b`

## pseudocode

```c
__int64 __fastcall WxIsThreadAppContainer(int *a1)
{
  HANDLE CurrentThread; // rax
  signed int IsTokenAppContainer; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  HANDLE CurrentProcess; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int LastError; // eax
  int v11; // eax
  void *TokenHandle; // [rsp+28h] [rbp-20h] BYREF

  TokenHandle = 0;
  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
    goto LABEL_2;
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
LABEL_2:
      IsTokenAppContainer = WxIsTokenAppContainer(TokenHandle, a1);
      goto LABEL_3;
    }
    LastError = WxGetLastError(v9, v8);
    IsTokenAppContainer = LastError;
    if ( LastError > 0 )
      IsTokenAppContainer = (unsigned __int16)LastError | 0x80070000;
    if ( IsTokenAppContainer >= 0 )
      IsTokenAppContainer = -2147418113;
  }
  else
  {
    v11 = WxGetLastError(v6, v5);
    IsTokenAppContainer = v11;
    if ( v11 > 0 )
      IsTokenAppContainer = (unsigned __int16)v11 | 0x80070000;
    if ( IsTokenAppContainer >= 0 )
      IsTokenAppContainer = -2147418113;
  }
LABEL_3:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)IsTokenAppContainer;
}

```

## disassembly

```asm
0x1800a8728  push    rbx
0x1800a872a  sub     rsp, 40h
0x1800a872e  mov     rax, cs:__security_cookie
0x1800a8735  xor     rax, rsp
0x1800a8738  mov     [rsp+48h+var_18], rax
0x1800a873d  mov     rbx, rcx
0x1800a8740  mov     [rsp+48h+var_24], 0
0x1800a8748  mov     [rsp+48h+TokenHandle], 0
0x1800a8751  mov     dword ptr [rcx], 0
0x1800a8757  call    cs:__imp_GetCurrentThread
0x1800a875d  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800a8762  mov     edx, 20008h; DesiredAccess
0x1800a8767  mov     rcx, rax; ThreadHandle
0x1800a876a  mov     r8d, 1; OpenAsSelf
0x1800a8770  call    cs:__imp_OpenThreadToken
0x1800a8776  test    eax, eax
0x1800a8778  jz      short loc_1800A87B6
0x1800a877a  mov     rcx, [rsp+48h+TokenHandle]; void *
0x1800a877f  mov     rdx, rbx; int *
0x1800a8782  call    ?WxIsTokenAppContainer@@YAJPEAXPEAH@Z; WxIsTokenAppContainer(void *,int *)
0x1800a8787  mov     ebx, eax
0x1800a8789  test    eax, eax
0x1800a878b  js      loc_1800A8833
0x1800a8791  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800a8796  test    rcx, rcx
0x1800a8799  jz      short loc_1800A87A1
0x1800a879b  call    cs:__imp_CloseHandle
0x1800a87a1  mov     eax, ebx
0x1800a87a3  mov     rcx, [rsp+48h+var_18]
0x1800a87a8  xor     rcx, rsp; StackCookie
0x1800a87ab  call    __security_check_cookie
0x1800a87b0  add     rsp, 40h
0x1800a87b4  pop     rbx
0x1800a87b5  retn
0x1800a87b6  call    cs:__imp_GetLastError
0x1800a87bc  cmp     eax, 3F0h
0x1800a87c1  jnz     short loc_1800A8808
0x1800a87c3  call    cs:__imp_GetCurrentProcess
0x1800a87c9  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x1800a87ce  mov     edx, 20008h; DesiredAccess
0x1800a87d3  mov     rcx, rax; ProcessHandle
0x1800a87d6  call    cs:__imp_OpenProcessToken
0x1800a87dc  test    eax, eax
0x1800a87de  jnz     short loc_1800A877A
0x1800a87e0  call    WxGetLastError
0x1800a87e5  mov     ebx, eax
0x1800a87e7  test    eax, eax
0x1800a87e9  jle     short loc_1800A87F4
0x1800a87eb  movzx   ebx, ax
0x1800a87ee  or      ebx, 80070000h
0x1800a87f4  test    ebx, ebx
0x1800a87f6  mov     [rsp+48h+var_24], 227h
0x1800a87fe  mov     eax, 8000FFFFh
0x1800a8803  cmovns  ebx, eax
0x1800a8806  jmp     short loc_1800A8791
0x1800a8808  call    WxGetLastError
0x1800a880d  mov     ebx, eax
0x1800a880f  test    eax, eax
0x1800a8811  jle     short loc_1800A881C
0x1800a8813  movzx   ebx, ax
0x1800a8816  or      ebx, 80070000h
0x1800a881c  test    ebx, ebx
0x1800a881e  mov     [rsp+48h+var_24], 225h
0x1800a8826  mov     eax, 8000FFFFh
0x1800a882b  cmovns  ebx, eax
0x1800a882e  jmp     loc_1800A8791
0x1800a8833  mov     [rsp+48h+var_24], 229h
0x1800a883b  jmp     loc_1800A8791
```
