# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x18007bc24`
- end: `0x18007bd19`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `245`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800672a0`

## callees

- `0x18007bc24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007bc40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007bc40`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007bc58`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007bc58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bc62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bcc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bc62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bcc0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007bcb6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007bcb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007bd05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007bd05`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::IsProcessAppContainer(HANDLE ProcessHandle, bool *a2, bool *a3)
{
  signed int LastError; // eax
  signed int v6; // ebx
  signed int v7; // eax
  char *v8; // rcx
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    TokenHandle = (void *)-4LL;
    goto LABEL_6;
  }
  if ( OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
  {
LABEL_6:
    v6 = 0;
    goto LABEL_7;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_7:
  if ( v6 >= 0 )
  {
    ReturnLength = 0;
    TokenInformation = 0;
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      *a2 = TokenInformation != 0;
      v6 = 0;
    }
    else
    {
      v7 = GetLastError();
      v6 = v7;
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
    }
  }
  v8 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007bc24  mov     [rsp+arg_18], rbx
0x18007bc29  push    rdi
0x18007bc2a  sub     rsp, 30h
0x18007bc2e  mov     rdi, rdx
0x18007bc31  mov     rbx, rcx
0x18007bc34  mov     byte ptr [rdx], 0
0x18007bc37  mov     [rsp+38h+TokenHandle], 0
0x18007bc40  call    cs:__imp_GetCurrentProcess
0x18007bc46  cmp     rbx, rax
0x18007bc49  jz      short loc_18007BC79
0x18007bc4b  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18007bc50  mov     edx, 8; DesiredAccess
0x18007bc55  mov     rcx, rbx; ProcessHandle
0x18007bc58  call    cs:__imp_OpenProcessToken
0x18007bc5e  test    eax, eax
0x18007bc60  jnz     short loc_18007BC82
0x18007bc62  call    cs:__imp_GetLastError
0x18007bc68  mov     ebx, eax
0x18007bc6a  test    eax, eax
0x18007bc6c  jle     short loc_18007BC84
0x18007bc6e  movzx   ebx, ax
0x18007bc71  or      ebx, 80070000h
0x18007bc77  jmp     short loc_18007BC84
0x18007bc79  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x18007bc82  xor     ebx, ebx
0x18007bc84  test    ebx, ebx
0x18007bc86  js      short loc_18007BCED
0x18007bc88  mov     [rsp+38h+arg_8], 0
0x18007bc90  mov     [rsp+38h+TokenInformation], 0
0x18007bc98  lea     rax, [rsp+38h+arg_8]
0x18007bc9d  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18007bca2  mov     r9d, 4; TokenInformationLength
0x18007bca8  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18007bcad  lea     edx, [r9+19h]; TokenInformationClass
0x18007bcb1  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18007bcb6  call    cs:__imp_GetTokenInformation
0x18007bcbc  test    eax, eax
0x18007bcbe  jnz     short loc_18007BCE1
0x18007bcc0  call    cs:__imp_GetLastError
0x18007bcc6  mov     ebx, eax
0x18007bcc8  test    eax, eax
0x18007bcca  jle     short loc_18007BCD5
0x18007bccc  movzx   ebx, ax
0x18007bccf  or      ebx, 80070000h
0x18007bcd5  mov     eax, 80004005h
0x18007bcda  test    ebx, ebx
0x18007bcdc  cmovns  ebx, eax
0x18007bcdf  jmp     short loc_18007BCED
0x18007bce1  cmp     [rsp+38h+TokenInformation], 0
0x18007bce6  setnz   al
0x18007bce9  mov     [rdi], al
0x18007bceb  xor     ebx, ebx
0x18007bced  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18007bcf2  mov     [rsp+38h+TokenHandle], 0
0x18007bcfb  lea     rdx, [rcx-1]
0x18007bcff  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007bd03  ja      short loc_18007BD0C
0x18007bd05  call    cs:__imp_CloseHandle
0x18007bd0b  nop
0x18007bd0c  mov     eax, ebx
0x18007bd0e  mov     rbx, [rsp+38h+arg_18]
0x18007bd13  add     rsp, 30h
0x18007bd17  pop     rdi
0x18007bd18  retn
```
