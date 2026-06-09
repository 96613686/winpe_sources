# LUAGetUserType(void *,LUAUSERTYPE *)

- ea: `0x18001ce3c`
- end: `0x18001cf3c`
- name: `?LUAGetUserType@@YAJPEAXPEAW4LUAUSERTYPE@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(void *, enum LUAUSERTYPE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ec24`

## callees

- `0x180010680`
- `0x18001ce3c`
- `0x18001cf44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ce5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ce5b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ce6d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ce6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cf27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cf27`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cef6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cef6`

## pseudocode

```c
__int64 __fastcall LUAGetUserType(void *a1, enum LUAUSERTYPE *a2)
{
  HANDLE CurrentProcess; // rax
  void *v4; // rsi
  int Error; // ebx
  void *v6; // rcx
  int v7; // ecx
  void *TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  DWORD ReturnLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  TokenInformation = a1;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v6 = TokenHandle;
    v4 = TokenHandle;
  }
  else
  {
    v4 = 0;
    Error = ResultFromLastError();
    if ( Error < 0 )
      return (unsigned int)Error;
    v6 = TokenHandle;
  }
  LODWORD(TokenInformation) = 0;
  ReturnLength = 0;
  Error = LUAIsElevatedToken(v6, (int *)&TokenInformation, (int *)&ReturnLength);
  if ( Error >= 0 )
  {
    if ( (_DWORD)TokenInformation )
      *(_DWORD *)a2 = 0;
    else
      *(_DWORD *)a2 = 2 - (ReturnLength != 0);
    LODWORD(TokenInformation) = 0;
    ReturnLength = 4;
    if ( GetTokenInformation(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &ReturnLength) )
    {
      Error = 0;
      if ( (_DWORD)TokenInformation )
      {
        v7 = *(_DWORD *)a2;
        if ( (unsigned int)(*(_DWORD *)a2 - 16) > 2 )
          v7 += 16;
        *(_DWORD *)a2 = v7;
      }
    }
    else
    {
      Error = ResultFromLastError();
    }
  }
  if ( v4 )
    CloseHandle(v4);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001ce3c  mov     [rsp-18h+arg_8], rbx
0x18001ce41  mov     [rsp-18h+TokenInformation], rcx
0x18001ce46  push    rbp
0x18001ce47  push    rsi
0x18001ce48  push    rdi
0x18001ce49  mov     rbp, rsp
0x18001ce4c  sub     rsp, 30h
0x18001ce50  mov     rdi, rdx
0x18001ce53  mov     [rbp+TokenHandle], 0
0x18001ce5b  call    cs:__imp_GetCurrentProcess
0x18001ce61  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001ce65  mov     edx, 8; DesiredAccess
0x18001ce6a  mov     rcx, rax; ProcessHandle
0x18001ce6d  call    cs:__imp_OpenProcessToken
0x18001ce73  test    eax, eax
0x18001ce75  jnz     short loc_18001CE8E
0x18001ce77  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001ce7c  xor     esi, esi
0x18001ce7e  mov     ebx, eax
0x18001ce80  test    eax, eax
0x18001ce82  js      loc_18001CF2D
0x18001ce88  mov     rcx, [rbp+TokenHandle]
0x18001ce8c  jmp     short loc_18001CE95
0x18001ce8e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001ce92  mov     rsi, rcx
0x18001ce95  lea     r8, [rbp+arg_10]; int *
0x18001ce99  mov     dword ptr [rbp+TokenInformation], 0
0x18001cea0  lea     rdx, [rbp+TokenInformation]; int *
0x18001cea4  mov     [rbp+arg_10], 0
0x18001ceab  call    ?LUAIsElevatedToken@@YAJPEAXPEAH1@Z; LUAIsElevatedToken(void *,int *,int *)
0x18001ceb0  mov     ebx, eax
0x18001ceb2  test    eax, eax
0x18001ceb4  js      short loc_18001CF1F
0x18001ceb6  cmp     dword ptr [rbp+TokenInformation], 0
0x18001ceba  jz      short loc_18001CEC4
0x18001cebc  mov     dword ptr [rdi], 0
0x18001cec2  jmp     short loc_18001CED0
0x18001cec4  mov     eax, [rbp+arg_10]
0x18001cec7  neg     eax
0x18001cec9  sbb     ecx, ecx
0x18001cecb  add     ecx, 2
0x18001cece  mov     [rdi], ecx
0x18001ced0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001ced4  lea     rax, [rbp+arg_10]
0x18001ced8  mov     r9d, 4; TokenInformationLength
0x18001cede  mov     dword ptr [rbp+TokenInformation], 0
0x18001cee5  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001cee9  mov     [rbp+arg_10], r9d
0x18001ceed  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001cef2  lea     edx, [r9+16h]; TokenInformationClass
0x18001cef6  call    cs:__imp_GetTokenInformation
0x18001cefc  test    eax, eax
0x18001cefe  jnz     short loc_18001CF09
0x18001cf00  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001cf05  mov     ebx, eax
0x18001cf07  jmp     short loc_18001CF1F
0x18001cf09  xor     ebx, ebx
0x18001cf0b  cmp     dword ptr [rbp+TokenInformation], ebx
0x18001cf0e  jz      short loc_18001CF1F
0x18001cf10  mov     ecx, [rdi]
0x18001cf12  lea     eax, [rcx-10h]
0x18001cf15  cmp     eax, 2
0x18001cf18  jbe     short loc_18001CF1D
0x18001cf1a  add     ecx, 10h
0x18001cf1d  mov     [rdi], ecx
0x18001cf1f  test    rsi, rsi
0x18001cf22  jz      short loc_18001CF2D
0x18001cf24  mov     rcx, rsi; hObject
0x18001cf27  call    cs:__imp_CloseHandle
0x18001cf2d  mov     eax, ebx
0x18001cf2f  mov     rbx, [rsp+30h+arg_8]
0x18001cf34  add     rsp, 30h
0x18001cf38  pop     rdi
0x18001cf39  pop     rsi
0x18001cf3a  pop     rbp
0x18001cf3b  retn
```
