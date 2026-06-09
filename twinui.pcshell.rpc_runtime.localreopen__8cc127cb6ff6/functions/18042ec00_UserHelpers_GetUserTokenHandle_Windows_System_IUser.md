# UserHelpers::GetUserTokenHandle(Windows::System::IUser *)

- ea: `0x18042ec00`
- end: `0x18042ed41`
- name: `?GetUserTokenHandle@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18042fb44`

## callees

- `0x18007f488`
- `0x1800d4a50`
- `0x18035ea38`
- `0x18042ec00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042ec58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042ec92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042ecd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042ed06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042ec58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042ec92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042ecd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042ed06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18042ec77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18042ece7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18042ec77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18042ece7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18042ec37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18042ecb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18042ec37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18042ecb2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18042ec4a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18042ecc7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18042ec4a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18042ecc7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18042ec88`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18042ecf8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18042ec88`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18042ecf8`

## string_xrefs

- `0x18042ed2f`: `shellcommon\internal\shell\inc\Helpers\UserHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PHANDLE __fastcall UserHelpers::GetUserTokenHandle(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  bool v7; // sf
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *TokenHandle = 0;
  IsUMgrQueryUserTokenPresent();
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, TokenHandle) )
    goto LABEL_14;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147023888 )
    goto LABEL_17;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    goto LABEL_14;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147023888 )
    goto LABEL_17;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    TokenHandle,
    0);
  v5 = GetCurrentThread();
  if ( OpenThreadToken(v5, 8u, 1, TokenHandle) )
    goto LABEL_14;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147023888 )
    goto LABEL_17;
  v6 = GetCurrentProcess();
  if ( OpenProcessToken(v6, 8u, TokenHandle) )
  {
LABEL_14:
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_18;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_17:
  v7 = LastError < 0;
LABEL_18:
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Helpers\\UserHelpers.h",
      (const char *)(unsigned int)LastError,
      1);
  return TokenHandle;
}

```

## disassembly

```asm
0x18042ec00  mov     rax, rsp
0x18042ec03  mov     [rax+10h], rbx
0x18042ec07  mov     [rax+8], rcx
0x18042ec0b  push    rdi
0x18042ec0c  sub     rsp, 30h
0x18042ec10  mov     rbx, rcx
0x18042ec13  mov     dword ptr [rax-18h], 0
0x18042ec1a  mov     qword ptr [rcx], 0
0x18042ec21  mov     dword ptr [rax-18h], 1
0x18042ec28  call    IsUMgrQueryUserTokenPresent
0x18042ec2d  xor     edx, edx
0x18042ec2f  mov     rcx, rbx
0x18042ec32  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18042ec37  call    cs:__imp_GetCurrentThread
0x18042ec3d  mov     rcx, rax; ThreadHandle
0x18042ec40  mov     r9, rbx; TokenHandle
0x18042ec43  xor     r8d, r8d; OpenAsSelf
0x18042ec46  lea     edx, [r8+8]; DesiredAccess
0x18042ec4a  call    cs:__imp_OpenThreadToken
0x18042ec50  test    eax, eax
0x18042ec52  jnz     loc_18042ED02
0x18042ec58  call    cs:__imp_GetLastError
0x18042ec5e  mov     edi, 80070000h
0x18042ec63  test    eax, eax
0x18042ec65  jle     short loc_18042EC6C
0x18042ec67  movzx   eax, ax
0x18042ec6a  or      eax, edi
0x18042ec6c  cmp     eax, 800703F0h
0x18042ec71  jnz     loc_18042ED15
0x18042ec77  call    cs:__imp_GetCurrentProcess
0x18042ec7d  mov     rcx, rax; ProcessHandle
0x18042ec80  mov     r8, rbx; TokenHandle
0x18042ec83  mov     edx, 8; DesiredAccess
0x18042ec88  call    cs:__imp_OpenProcessToken
0x18042ec8e  test    eax, eax
0x18042ec90  jnz     short loc_18042ED02
0x18042ec92  call    cs:__imp_GetLastError
0x18042ec98  test    eax, eax
0x18042ec9a  jle     short loc_18042ECA1
0x18042ec9c  movzx   eax, ax
0x18042ec9f  or      eax, edi
0x18042eca1  cmp     eax, 800703F0h
0x18042eca6  jnz     short loc_18042ED15
0x18042eca8  xor     edx, edx
0x18042ecaa  mov     rcx, rbx
0x18042ecad  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18042ecb2  call    cs:__imp_GetCurrentThread
0x18042ecb8  mov     rcx, rax; ThreadHandle
0x18042ecbb  mov     r9, rbx; TokenHandle
0x18042ecbe  mov     edx, 8; DesiredAccess
0x18042ecc3  lea     r8d, [rdx-7]; OpenAsSelf
0x18042ecc7  call    cs:__imp_OpenThreadToken
0x18042eccd  test    eax, eax
0x18042eccf  jnz     short loc_18042ED02
0x18042ecd1  call    cs:__imp_GetLastError
0x18042ecd7  test    eax, eax
0x18042ecd9  jle     short loc_18042ECE0
0x18042ecdb  movzx   eax, ax
0x18042ecde  or      eax, edi
0x18042ece0  cmp     eax, 800703F0h
0x18042ece5  jnz     short loc_18042ED15
0x18042ece7  call    cs:__imp_GetCurrentProcess
0x18042eced  mov     rcx, rax; ProcessHandle
0x18042ecf0  mov     r8, rbx; TokenHandle
0x18042ecf3  mov     edx, 8; DesiredAccess
0x18042ecf8  call    cs:__imp_OpenProcessToken
0x18042ecfe  test    eax, eax
0x18042ed00  jz      short loc_18042ED06
0x18042ed02  xor     eax, eax
0x18042ed04  jmp     short loc_18042ED15
0x18042ed06  call    cs:__imp_GetLastError
0x18042ed0c  test    eax, eax
0x18042ed0e  jle     short loc_18042ED17
0x18042ed10  movzx   eax, ax
0x18042ed13  or      eax, edi
0x18042ed15  test    eax, eax
0x18042ed17  js      short loc_18042ED27
0x18042ed19  mov     rax, rbx
0x18042ed1c  mov     rbx, [rsp+38h+arg_8]
0x18042ed21  add     rsp, 30h
0x18042ed25  pop     rdi
0x18042ed26  retn
0x18042ed27  mov     rcx, [rsp+38h]; this
0x18042ed2c  mov     r9d, eax; char *
0x18042ed2f  lea     r8, aShellcommonInt_9; "shellcommon\\internal\\shell\\inc\\Help"...
0x18042ed36  mov     edx, 61h ; 'a'; void *
0x18042ed3b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
