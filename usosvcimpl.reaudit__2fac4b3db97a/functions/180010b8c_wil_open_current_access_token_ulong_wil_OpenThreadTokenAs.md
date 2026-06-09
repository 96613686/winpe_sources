# wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)

- ea: `0x180010b8c`
- end: `0x180010c5f`
- name: `?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dc44`
- `0x180040a08`

## callees

- `0x180010b8c`
- `0x1800112d0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010bf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010bf1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010c04`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010c04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010bb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010bb2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010bc7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010bc7`

## string_xrefs

- `0x180010c4d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
void **__fastcall wil::open_current_access_token(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned __int64 v4; // r9
  HANDLE CurrentProcess; // rax
  signed int v6; // eax
  void **result; // rax
  int v8; // [rsp+20h] [rbp-28h]
  void *TokenHandle; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v4 = (unsigned int)LastError;
    if ( (_DWORD)v4 == -2147023888 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        goto LABEL_9;
      v6 = GetLastError();
      v4 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        v4 = (unsigned int)v6;
    }
    if ( (v4 & 0x80000000) != 0LL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE1,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)v4,
        v8);
  }
LABEL_9:
  result = a1;
  *a1 = TokenHandle;
  return result;
}

```

## disassembly

```asm
0x180010b8c  push    rbx
0x180010b8e  sub     rsp, 40h
0x180010b92  mov     rax, cs:__security_cookie
0x180010b99  xor     rax, rsp
0x180010b9c  mov     [rsp+48h+var_18], rax
0x180010ba1  mov     [rsp+48h+TokenHandle], rcx
0x180010ba6  mov     rbx, rcx
0x180010ba9  mov     [rsp+48h+TokenHandle], 0
0x180010bb2  call    cs:__imp_GetCurrentThread
0x180010bb8  xor     r8d, r8d; OpenAsSelf
0x180010bbb  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180010bc0  mov     rcx, rax; ThreadHandle
0x180010bc3  lea     edx, [r8+8]; DesiredAccess
0x180010bc7  call    cs:__imp_OpenThreadToken
0x180010bcd  test    eax, eax
0x180010bcf  jnz     short loc_180010C2A
0x180010bd1  call    cs:__imp_GetLastError
0x180010bd7  movzx   r9d, ax
0x180010bdb  or      r9d, 80070000h
0x180010be2  test    eax, eax
0x180010be4  cmovle  r9d, eax
0x180010be8  cmp     r9d, 800703F0h
0x180010bef  jnz     short loc_180010C25
0x180010bf1  call    cs:__imp_GetCurrentProcess
0x180010bf7  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180010bfc  mov     edx, 8; DesiredAccess
0x180010c01  mov     rcx, rax; ProcessHandle
0x180010c04  call    cs:__imp_OpenProcessToken
0x180010c0a  test    eax, eax
0x180010c0c  jnz     short loc_180010C2A
0x180010c0e  call    cs:__imp_GetLastError
0x180010c14  movzx   r9d, ax
0x180010c18  or      r9d, 80070000h
0x180010c1f  test    eax, eax
0x180010c21  cmovle  r9d, eax; char *
0x180010c25  test    r9d, r9d
0x180010c28  js      short loc_180010C48
0x180010c2a  mov     rcx, [rsp+48h+TokenHandle]
0x180010c2f  mov     rax, rbx
0x180010c32  mov     [rbx], rcx
0x180010c35  mov     rcx, [rsp+48h+var_18]
0x180010c3a  xor     rcx, rsp; StackCookie
0x180010c3d  call    __security_check_cookie
0x180010c42  add     rsp, 40h
0x180010c46  pop     rbx
0x180010c47  retn
0x180010c48  mov     rcx, [rsp+48h]; this
0x180010c4d  lea     r8, aCW1SPackagesMi_7; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180010c54  mov     edx, 0E1h; void *
0x180010c59  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
