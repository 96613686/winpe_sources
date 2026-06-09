# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x18004a950`
- end: `0x18004aa39`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `233`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a910`

## callees

- `0x180023730`
- `0x18004a950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa11`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004aa03`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004aa03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004a96c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004a96c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aa2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aa2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a9b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a9b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::IsProcessAppContainer(HANDLE ProcessHandle, bool *a2, bool *a3)
{
  signed int v5; // ebx
  BOOL v6; // eax
  char *v7; // rcx
  signed int LastError; // eax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    TokenHandle = (HANDLE)-4LL;
LABEL_3:
    v5 = 0;
    goto LABEL_4;
  }
  if ( OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    goto LABEL_3;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_4:
  if ( v5 >= 0 )
  {
    ReturnLength = 0;
    TokenInformation = 0;
    v6 = GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
    v5 = ResultFromWin32Bool(v6);
    if ( v5 >= 0 )
      *a2 = TokenInformation != 0;
  }
  v7 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004a950  mov     [rsp+arg_18], rbx
0x18004a955  push    rdi
0x18004a956  sub     rsp, 30h
0x18004a95a  mov     rdi, rdx
0x18004a95d  mov     rbx, rcx
0x18004a960  mov     byte ptr [rdx], 0
0x18004a963  mov     [rsp+38h+TokenHandle], 0
0x18004a96c  call    cs:__imp_GetCurrentProcess
0x18004a972  cmp     rbx, rax
0x18004a975  jnz     short loc_18004A9F6
0x18004a977  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x18004a980  xor     ebx, ebx
0x18004a982  test    ebx, ebx
0x18004a984  js      short loc_18004A9D1
0x18004a986  mov     [rsp+38h+arg_8], 0
0x18004a98e  mov     [rsp+38h+TokenInformation], 0
0x18004a996  lea     rax, [rsp+38h+arg_8]
0x18004a99b  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18004a9a0  mov     r9d, 4; TokenInformationLength
0x18004a9a6  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18004a9ab  lea     edx, [r9+19h]; TokenInformationClass
0x18004a9af  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18004a9b4  call    cs:__imp_GetTokenInformation
0x18004a9ba  mov     ecx, eax; int
0x18004a9bc  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18004a9c1  mov     ebx, eax
0x18004a9c3  test    eax, eax
0x18004a9c5  js      short loc_18004A9D1
0x18004a9c7  cmp     [rsp+38h+TokenInformation], 0
0x18004a9cc  setnz   cl
0x18004a9cf  mov     [rdi], cl
0x18004a9d1  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18004a9d6  mov     [rsp+38h+TokenHandle], 0
0x18004a9df  lea     rax, [rcx-1]
0x18004a9e3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004a9e7  jbe     short loc_18004AA2F
0x18004a9e9  mov     eax, ebx
0x18004a9eb  mov     rbx, [rsp+38h+arg_18]
0x18004a9f0  add     rsp, 30h
0x18004a9f4  pop     rdi
0x18004a9f5  retn
0x18004a9f6  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18004a9fb  mov     edx, 8; DesiredAccess
0x18004aa00  mov     rcx, rbx; ProcessHandle
0x18004aa03  call    cs:__imp_OpenProcessToken
0x18004aa09  test    eax, eax
0x18004aa0b  jnz     loc_18004A980
0x18004aa11  call    cs:__imp_GetLastError
0x18004aa17  mov     ebx, eax
0x18004aa19  test    eax, eax
0x18004aa1b  jle     loc_18004A982
0x18004aa21  movzx   ebx, ax
0x18004aa24  or      ebx, 80070000h
0x18004aa2a  jmp     loc_18004A982
0x18004aa2f  call    cs:__imp_CloseHandle
0x18004aa35  nop
0x18004aa36  jmp     short loc_18004A9E9
```
