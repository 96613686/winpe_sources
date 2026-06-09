# WsCreateSymbolicLink

- ea: `0x1800089ac`
- end: `0x180008b44`
- name: `WsCreateSymbolicLink`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x180001750`
- `0x18002cbf4`

## callees

- `0x180008950`
- `0x1800089ac`
- `0x180008b50`
- `0x180009010`
- `0x180009090`
- `0x18001fbd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008aff`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180008aef`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180008aef`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180008a84`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180008a84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008a20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008a20`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008a3b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008a3b`

## pseudocode

```c
DWORD __fastcall WsCreateSymbolicLink(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        __int64 a4,
        LPCWSTR *a5,
        PHANDLE TokenHandle)
{
  __int64 v10; // rax
  DWORD result; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  DWORD v14; // eax
  bool v15; // zf
  __int64 v16; // [rsp+20h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+28h] [rbp-C0h] BYREF
  WCHAR TargetPath[64]; // [rsp+30h] [rbp-B8h] BYREF

  v10 = WsReturnSessionPath();
  *a5 = (LPCWSTR)v10;
  if ( !v10 )
    return GetLastError();
  result = WsImpersonateClient2(0, 0);
  if ( !result )
  {
    if ( TokenHandle )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 4u, 1, TokenHandle) )
      {
        LastError = GetLastError();
        WsRevertToSelf2(0, 0);
        *TokenHandle = (void *)-1LL;
        return LastError;
      }
    }
    if ( (unsigned int)(a2 - 1) <= 1 )
    {
      v16 = 0;
      v17 = 0;
      WsFindLocal(a4, a1, &v16, &v17);
      v15 = v16 == 0;
    }
    else
    {
      if ( QueryDosDeviceW(*a5, TargetPath, 0x40u) )
      {
LABEL_13:
        LastError = 85;
        goto LABEL_17;
      }
      v14 = GetLastError();
      LastError = 5;
      if ( v14 == 5 )
      {
LABEL_17:
        WsRevertToSelf2(0, 0);
        return LastError;
      }
      v15 = v14 == 2;
    }
    if ( v15 )
    {
      if ( DefineDosDeviceW(9u, *a5, a3) )
        LastError = 0;
      else
        LastError = GetLastError();
      goto LABEL_17;
    }
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x1800089ac  mov     [rsp+arg_8], rbx
0x1800089b1  push    rbp
0x1800089b2  push    rsi
0x1800089b3  push    rdi
0x1800089b4  push    r14
0x1800089b6  push    r15
0x1800089b8  sub     rsp, 0C0h
0x1800089bf  mov     rax, cs:__security_cookie
0x1800089c6  xor     rax, rsp
0x1800089c9  mov     [rsp+0E8h+var_38], rax
0x1800089d1  mov     rsi, [rsp+0E8h+arg_20]
0x1800089d9  mov     r14, r9
0x1800089dc  mov     rdi, [rsp+0E8h+TokenHandle]
0x1800089e4  mov     r15, r8
0x1800089e7  mov     ebp, edx
0x1800089e9  mov     rbx, rcx
0x1800089ec  call    WsReturnSessionPath
0x1800089f1  mov     [rsi], rax
0x1800089f4  test    rax, rax
0x1800089f7  jnz     short loc_180008A0A
0x1800089f9  call    cs:__imp_GetLastError
0x180008a00  nop     dword ptr [rax+rax+00h]
0x180008a05  jmp     loc_180008B1C
0x180008a0a  xor     edx, edx
0x180008a0c  xor     ecx, ecx
0x180008a0e  call    WsImpersonateClient2
0x180008a13  test    eax, eax
0x180008a15  jnz     loc_180008B1C
0x180008a1b  test    rdi, rdi
0x180008a1e  jz      short loc_180008A6E
0x180008a20  call    cs:__imp_GetCurrentThread
0x180008a27  nop     dword ptr [rax+rax+00h]
0x180008a2c  mov     edx, 4; DesiredAccess
0x180008a31  mov     r9, rdi; TokenHandle
0x180008a34  mov     rcx, rax; ThreadHandle
0x180008a37  lea     r8d, [rdx-3]; OpenAsSelf
0x180008a3b  call    cs:__imp_OpenThreadToken
0x180008a42  nop     dword ptr [rax+rax+00h]
0x180008a47  test    eax, eax
0x180008a49  jnz     short loc_180008A6E
0x180008a4b  call    cs:__imp_GetLastError
0x180008a52  nop     dword ptr [rax+rax+00h]
0x180008a57  xor     edx, edx
0x180008a59  xor     ecx, ecx
0x180008a5b  mov     ebx, eax
0x180008a5d  call    WsRevertToSelf2
0x180008a62  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180008a69  jmp     loc_180008B1A
0x180008a6e  lea     eax, [rbp-1]
0x180008a71  cmp     eax, 1
0x180008a74  jbe     short loc_180008AAE
0x180008a76  mov     rcx, [rsi]; lpDeviceName
0x180008a79  lea     rdx, [rsp+0E8h+TargetPath]; lpTargetPath
0x180008a7e  mov     r8d, 40h ; '@'; ucchMax
0x180008a84  call    cs:__imp_QueryDosDeviceW
0x180008a8b  nop     dword ptr [rax+rax+00h]
0x180008a90  test    eax, eax
0x180008a92  jnz     short loc_180008ADD
0x180008a94  call    cs:__imp_GetLastError
0x180008a9b  nop     dword ptr [rax+rax+00h]
0x180008aa0  mov     ebx, 5
0x180008aa5  cmp     eax, ebx
0x180008aa7  jz      short loc_180008B11
0x180008aa9  cmp     eax, 2
0x180008aac  jmp     short loc_180008ADB
0x180008aae  lea     r9, [rsp+0E8h+var_C0]
0x180008ab3  mov     [rsp+0E8h+var_C8], 0
0x180008abc  lea     r8, [rsp+0E8h+var_C8]
0x180008ac1  mov     [rsp+0E8h+var_C0], 0
0x180008aca  mov     rdx, rbx
0x180008acd  mov     rcx, r14
0x180008ad0  call    WsFindLocal
0x180008ad5  cmp     [rsp+0E8h+var_C8], 0
0x180008adb  jz      short loc_180008AE4
0x180008add  mov     ebx, 55h ; 'U'
0x180008ae2  jmp     short loc_180008B11
0x180008ae4  mov     rdx, [rsi]; lpDeviceName
0x180008ae7  mov     r8, r15; lpTargetPath
0x180008aea  mov     ecx, 9; dwFlags
0x180008aef  call    cs:__imp_DefineDosDeviceW
0x180008af6  nop     dword ptr [rax+rax+00h]
0x180008afb  test    eax, eax
0x180008afd  jnz     short loc_180008B0F
0x180008aff  call    cs:__imp_GetLastError
0x180008b06  nop     dword ptr [rax+rax+00h]
0x180008b0b  mov     ebx, eax
0x180008b0d  jmp     short loc_180008B11
0x180008b0f  xor     ebx, ebx
0x180008b11  xor     edx, edx
0x180008b13  xor     ecx, ecx
0x180008b15  call    WsRevertToSelf2
0x180008b1a  mov     eax, ebx
0x180008b1c  mov     rcx, [rsp+0E8h+var_38]
0x180008b24  xor     rcx, rsp; StackCookie
0x180008b27  call    __security_check_cookie
0x180008b2c  mov     rbx, [rsp+0E8h+arg_8]
0x180008b34  add     rsp, 0C0h
0x180008b3b  pop     r15
0x180008b3d  pop     r14
0x180008b3f  pop     rdi
0x180008b40  pop     rsi
0x180008b41  pop     rbp
0x180008b42  retn
```
