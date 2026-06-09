# RestrictedToken::OpenCurrentProcToken(ulong,void * *)

- ea: `0x1800c5b2c`
- end: `0x1800c5c39`
- name: `?OpenCurrentProcToken@RestrictedToken@@AEAAJKPEAPEAX@Z`
- size: `269`
- prototype: `__int64 __fastcall(RestrictedToken *__hidden this, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800c551c`

## callees

- `0x1800a1d10`
- `0x1800c5b2c`
- `0x1800cf58c`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c5b94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c5b94`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c5ba4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c5ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5bae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c5c19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c5c19`

## pseudocode

```c
__int64 __fastcall RestrictedToken::OpenCurrentProcToken(RestrictedToken *this, __int64 a2, void **a3)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  void *v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-38h]
  void *TokenHandle; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    LODWORD(v9) = 171;
    WPP_SF_qD(1029, 10, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids, PacWorkerClient::s_RestrictedToken);
  }
  if ( a3 )
    *a3 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xABu, &TokenHandle) )
  {
    v6 = 0;
    v7 = 0;
    *a3 = TokenHandle;
    TokenHandle = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v7 = TokenHandle;
    if ( (v6 & 0x80000000) == 0 )
      v6 = -2147418113;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    WPP_SF_d(1029, 11, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids, v6, v9);
    v7 = TokenHandle;
  }
  if ( v7 )
    CloseHandle(v7);
  return v6;
}

```

## disassembly

```asm
0x1800c5b2c  mov     [rsp+arg_0], rbx
0x1800c5b31  push    rdi
0x1800c5b32  sub     rsp, 50h
0x1800c5b36  mov     rax, cs:__security_cookie
0x1800c5b3d  xor     rax, rsp
0x1800c5b40  mov     [rsp+58h+var_18], rax
0x1800c5b45  mov     rdi, r8
0x1800c5b48  mov     [rsp+58h+var_24], 0
0x1800c5b50  mov     [rsp+58h+TokenHandle], 0
0x1800c5b59  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c5b60  mov     ebx, 0ABh
0x1800c5b65  jz      short loc_1800C5B88
0x1800c5b67  mov     edx, 0Ah
0x1800c5b6c  mov     [rsp+58h+var_38], ebx
0x1800c5b70  mov     ecx, 405h
0x1800c5b75  lea     r9, ?s_RestrictedToken@PacWorkerClient@@0VRestrictedToken@@A; RestrictedToken PacWorkerClient::s_RestrictedToken
0x1800c5b7c  lea     r8, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids
0x1800c5b83  call    WPP_SF_qD
0x1800c5b88  test    rdi, rdi
0x1800c5b8b  jz      short loc_1800C5B94
0x1800c5b8d  mov     qword ptr [rdi], 0
0x1800c5b94  call    cs:__imp_GetCurrentProcess
0x1800c5b9a  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1800c5b9f  mov     edx, ebx; DesiredAccess
0x1800c5ba1  mov     rcx, rax; ProcessHandle
0x1800c5ba4  call    cs:__imp_OpenProcessToken
0x1800c5baa  test    eax, eax
0x1800c5bac  jnz     short loc_1800C5BDC
0x1800c5bae  call    cs:__imp_GetLastError
0x1800c5bb4  mov     ebx, eax
0x1800c5bb6  test    eax, eax
0x1800c5bb8  jle     short loc_1800C5BC3
0x1800c5bba  movzx   ebx, ax
0x1800c5bbd  or      ebx, 80070000h
0x1800c5bc3  mov     rcx, [rsp+58h+TokenHandle]
0x1800c5bc8  test    ebx, ebx
0x1800c5bca  mov     eax, 8000FFFFh
0x1800c5bcf  mov     [rsp+58h+var_24], 20h ; ' '
0x1800c5bd7  cmovns  ebx, eax
0x1800c5bda  jmp     short loc_1800C5BED
0x1800c5bdc  mov     rax, [rsp+58h+TokenHandle]
0x1800c5be1  xor     ebx, ebx
0x1800c5be3  xor     ecx, ecx
0x1800c5be5  mov     [rdi], rax
0x1800c5be8  mov     [rsp+58h+TokenHandle], rcx
0x1800c5bed  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c5bf4  jz      short loc_1800C5C14
0x1800c5bf6  mov     edx, 0Bh
0x1800c5bfb  lea     r8, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids
0x1800c5c02  mov     ecx, 405h
0x1800c5c07  mov     r9d, ebx
0x1800c5c0a  call    WPP_SF_d
0x1800c5c0f  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1800c5c14  test    rcx, rcx
0x1800c5c17  jz      short loc_1800C5C1F
0x1800c5c19  call    cs:__imp_CloseHandle
0x1800c5c1f  mov     eax, ebx
0x1800c5c21  mov     rcx, [rsp+58h+var_18]
0x1800c5c26  xor     rcx, rsp; StackCookie
0x1800c5c29  call    __security_check_cookie
0x1800c5c2e  mov     rbx, [rsp+58h+arg_0]
0x1800c5c33  add     rsp, 50h
0x1800c5c37  pop     rdi
0x1800c5c38  retn
```
