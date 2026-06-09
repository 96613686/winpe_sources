# WxGetThreadAppContainerSID(_SID *,ulong)

- ea: `0x18010a5a4`
- end: `0x18010a6b6`
- name: `?WxGetThreadAppContainerSID@@YAJPEAU_SID@@K@Z`
- size: `274`
- prototype: `__int64 __fastcall(struct _SID *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18010a3cc`

## callees

- `0x1800701d0`
- `0x18010a5a4`
- `0x18010a6bc`
- `0x18014a7a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a62c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a62c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010a5cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010a5cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010a5e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010a5e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18010a64c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18010a64c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010a639`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010a639`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010a611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010a611`

## pseudocode

```c
__int64 __fastcall WxGetThreadAppContainerSID(struct _SID *a1)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // r8d
  signed int TokenAppContainerSID; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  HANDLE CurrentProcess; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int LastError; // eax
  int v12; // eax
  void *TokenHandle; // [rsp+28h] [rbp-20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
    goto LABEL_2;
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
LABEL_2:
      TokenAppContainerSID = WxGetTokenAppContainerSID(TokenHandle, a1, v3);
      goto LABEL_3;
    }
    LastError = WxGetLastError(v10, v9);
    TokenAppContainerSID = LastError;
    if ( LastError > 0 )
      TokenAppContainerSID = (unsigned __int16)LastError | 0x80070000;
    if ( TokenAppContainerSID >= 0 )
      TokenAppContainerSID = -2147418113;
  }
  else
  {
    v12 = WxGetLastError(v7, v6);
    TokenAppContainerSID = v12;
    if ( v12 > 0 )
      TokenAppContainerSID = (unsigned __int16)v12 | 0x80070000;
    if ( TokenAppContainerSID >= 0 )
      TokenAppContainerSID = -2147418113;
  }
LABEL_3:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)TokenAppContainerSID;
}

```

## disassembly

```asm
0x18010a5a4  push    rbx
0x18010a5a6  sub     rsp, 40h
0x18010a5aa  mov     rax, cs:__security_cookie
0x18010a5b1  xor     rax, rsp
0x18010a5b4  mov     [rsp+48h+var_18], rax
0x18010a5b9  mov     rbx, rcx
0x18010a5bc  mov     [rsp+48h+var_24], 0
0x18010a5c4  mov     [rsp+48h+TokenHandle], 0
0x18010a5cd  call    cs:__imp_GetCurrentThread
0x18010a5d3  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18010a5d8  mov     edx, 20008h; DesiredAccess
0x18010a5dd  mov     rcx, rax; ThreadHandle
0x18010a5e0  mov     r8d, 1; OpenAsSelf
0x18010a5e6  call    cs:__imp_OpenThreadToken
0x18010a5ec  test    eax, eax
0x18010a5ee  jz      short loc_18010A62C
0x18010a5f0  mov     rcx, [rsp+48h+TokenHandle]; void *
0x18010a5f5  mov     rdx, rbx; struct _SID *
0x18010a5f8  call    ?WxGetTokenAppContainerSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenAppContainerSID(void *,_SID *,ulong)
0x18010a5fd  mov     ebx, eax
0x18010a5ff  test    eax, eax
0x18010a601  js      loc_18010A6A9
0x18010a607  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18010a60c  test    rcx, rcx
0x18010a60f  jz      short loc_18010A617
0x18010a611  call    cs:__imp_CloseHandle
0x18010a617  mov     eax, ebx
0x18010a619  mov     rcx, [rsp+48h+var_18]
0x18010a61e  xor     rcx, rsp; StackCookie
0x18010a621  call    __security_check_cookie
0x18010a626  add     rsp, 40h
0x18010a62a  pop     rbx
0x18010a62b  retn
0x18010a62c  call    cs:__imp_GetLastError
0x18010a632  cmp     eax, 3F0h
0x18010a637  jnz     short loc_18010A67E
0x18010a639  call    cs:__imp_GetCurrentProcess
0x18010a63f  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18010a644  mov     edx, 20008h; DesiredAccess
0x18010a649  mov     rcx, rax; ProcessHandle
0x18010a64c  call    cs:__imp_OpenProcessToken
0x18010a652  test    eax, eax
0x18010a654  jnz     short loc_18010A5F0
0x18010a656  call    WxGetLastError
0x18010a65b  mov     ebx, eax
0x18010a65d  test    eax, eax
0x18010a65f  jle     short loc_18010A66A
0x18010a661  movzx   ebx, ax
0x18010a664  or      ebx, 80070000h
0x18010a66a  test    ebx, ebx
0x18010a66c  mov     [rsp+48h+var_24], 1D2h
0x18010a674  mov     eax, 8000FFFFh
0x18010a679  cmovns  ebx, eax
0x18010a67c  jmp     short loc_18010A607
0x18010a67e  call    WxGetLastError
0x18010a683  mov     ebx, eax
0x18010a685  test    eax, eax
0x18010a687  jle     short loc_18010A692
0x18010a689  movzx   ebx, ax
0x18010a68c  or      ebx, 80070000h
0x18010a692  test    ebx, ebx
0x18010a694  mov     [rsp+48h+var_24], 1D0h
0x18010a69c  mov     eax, 8000FFFFh
0x18010a6a1  cmovns  ebx, eax
0x18010a6a4  jmp     loc_18010A607
0x18010a6a9  mov     [rsp+48h+var_24], 1D4h
0x18010a6b1  jmp     loc_18010A607
```
