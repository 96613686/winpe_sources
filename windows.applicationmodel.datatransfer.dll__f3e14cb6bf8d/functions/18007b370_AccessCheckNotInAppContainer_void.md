# AccessCheckNotInAppContainer(void *)

- ea: `0x18007b370`
- end: `0x18007b44d`
- name: `?AccessCheckNotInAppContainer@@YAJPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a158`
- `0x180022204`
- `0x18006b730`

## callees

- `0x18007b370`
- `0x18007b454`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007b3ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007b3ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007b383`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007b383`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007b39a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007b39a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007b3cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007b3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b3ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b3d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b3ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b3d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b43f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b43f`

## pseudocode

```c
__int64 __fastcall AccessCheckNotInAppContainer(void *a1)
{
  HANDLE CurrentThread; // rax
  void *v2; // rcx
  signed int LastError; // eax
  signed int v4; // ebx
  HANDLE CurrentProcess; // rax
  signed int v6; // eax
  void *v8; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  v8 = a1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_2;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_2:
      v2 = TokenHandle;
LABEL_15:
      LOBYTE(v8) = 0;
      v4 = IsAppContainerToken(v2, (bool *)&v8);
      if ( v4 >= 0 && (_BYTE)v8 )
        v4 = -2147024891;
      goto LABEL_18;
    }
    v6 = GetLastError();
    v4 = v6;
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
  }
  else
  {
    v2 = 0;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( v4 >= 0 )
      goto LABEL_15;
  }
LABEL_18:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007b370  mov     [rsp+arg_0], rcx
0x18007b375  push    rbx
0x18007b376  sub     rsp, 20h
0x18007b37a  mov     [rsp+28h+TokenHandle], 0
0x18007b383  call    cs:__imp_GetCurrentThread
0x18007b389  mov     edx, 8; DesiredAccess
0x18007b38e  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18007b393  mov     rcx, rax; ThreadHandle
0x18007b396  lea     r8d, [rdx-7]; OpenAsSelf
0x18007b39a  call    cs:__imp_OpenThreadToken
0x18007b3a0  test    eax, eax
0x18007b3a2  jz      short loc_18007B3AB
0x18007b3a4  mov     rcx, [rsp+28h+TokenHandle]
0x18007b3a9  jmp     short loc_18007B414
0x18007b3ab  call    cs:__imp_GetLastError
0x18007b3b1  mov     ebx, eax
0x18007b3b3  cmp     eax, 3F0h
0x18007b3b8  jnz     short loc_18007B3F8
0x18007b3ba  call    cs:__imp_GetCurrentProcess
0x18007b3c0  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18007b3c5  mov     edx, 8; DesiredAccess
0x18007b3ca  mov     rcx, rax; ProcessHandle
0x18007b3cd  call    cs:__imp_OpenProcessToken
0x18007b3d3  test    eax, eax
0x18007b3d5  jnz     short loc_18007B3A4
0x18007b3d7  call    cs:__imp_GetLastError
0x18007b3dd  mov     ebx, eax
0x18007b3df  test    eax, eax
0x18007b3e1  jle     short loc_18007B3EC
0x18007b3e3  movzx   ebx, ax
0x18007b3e6  or      ebx, 80070000h
0x18007b3ec  test    ebx, ebx
0x18007b3ee  mov     eax, 80004005h
0x18007b3f3  cmovns  ebx, eax
0x18007b3f6  jmp     short loc_18007B435
0x18007b3f8  xor     ecx, ecx; void *
0x18007b3fa  test    eax, eax
0x18007b3fc  jz      short loc_18007B40B
0x18007b3fe  jle     short loc_18007B410
0x18007b400  movzx   ebx, ax
0x18007b403  or      ebx, 80070000h
0x18007b409  jmp     short loc_18007B410
0x18007b40b  mov     ebx, 80004005h
0x18007b410  test    ebx, ebx
0x18007b412  js      short loc_18007B435
0x18007b414  lea     rdx, [rsp+28h+arg_0]; bool *
0x18007b419  mov     byte ptr [rsp+28h+arg_0], 0
0x18007b41e  call    ?IsAppContainerToken@@YAJPEAXPEA_N@Z; IsAppContainerToken(void *,bool *)
0x18007b423  mov     ebx, eax
0x18007b425  test    eax, eax
0x18007b427  js      short loc_18007B435
0x18007b429  cmp     byte ptr [rsp+28h+arg_0], 0
0x18007b42e  jz      short loc_18007B435
0x18007b430  mov     ebx, 80070005h
0x18007b435  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18007b43a  test    rcx, rcx
0x18007b43d  jz      short loc_18007B445
0x18007b43f  call    cs:__imp_CloseHandle
0x18007b445  mov     eax, ebx
0x18007b447  add     rsp, 20h
0x18007b44b  pop     rbx
0x18007b44c  retn
```
