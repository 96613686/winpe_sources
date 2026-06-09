# _anonymous_namespace_::get_security_token_information

- ea: `0x180080ea0`
- end: `0x180081136`
- name: `_anonymous_namespace_::get_security_token_information`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800833b0`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x180005520`
- `0x18003af08`
- `0x180048c8c`
- `0x180049674`
- `0x18006dc58`
- `0x180080ea0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080feb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180080f16`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180080f16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081058`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081058`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080f4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080fe1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080f4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080fe1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180080ee3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180080ee3`

## string_xrefs

- `0x18008108c`: `get_security_token_information`
- `0x1800810c8`: `get_security_token_information`
- `0x180081104`: `get_security_token_information`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::get_security_token_information(
        __int64 a1,
        DWORD a2,
        TOKEN_INFORMATION_CLASS a3)
{
  HANDLE v5; // rbx
  DWORD LastError; // eax
  DWORD v7; // eax
  DWORD v8; // r9d
  __int64 v9; // r14
  char *v10; // rdi
  DWORD v11; // eax
  __int64 v12; // rdx
  void *v13; // rcx
  void *v14; // rax
  void *v15; // rcx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenInformation[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h]
  _QWORD v21[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+70h] [rbp-90h] BYREF

  v21[0] = a1;
  v5 = OpenProcess(0x1000u, 0, a2);
  v21[2] = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "get_security_token_information",
        510);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  TokenHandle = 0;
  if ( !OpenProcessToken(v5, 8u, &TokenHandle) )
  {
    v7 = GetLastError();
    if ( v7 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v7,
        0,
        "[%s:%d] failed; ",
        "get_security_token_information",
        513);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, a3, 0, 0, &TokenInformationLength)
    && (GetLastError() == 122 || GetLastError() == 24) )
  {
    v8 = TokenInformationLength;
    v9 = TokenInformationLength;
    *(_OWORD *)TokenInformation = 0;
    v20 = 0;
    if ( TokenInformationLength )
    {
      std::vector<char>::_Buy_nonzero(TokenInformation, TokenInformationLength);
      v10 = (char *)TokenInformation[0];
      memset_0(TokenInformation[0], 0, (unsigned int)v9);
      TokenInformation[1] = &v10[v9];
      v21[0] = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(v21);
      v8 = TokenInformationLength;
    }
    if ( !GetTokenInformation(TokenHandle, a3, TokenInformation[0], v8, &TokenInformationLength) )
    {
      v11 = GetLastError();
      if ( v11 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v11,
          0,
          "[%s:%d] failed; ",
          "get_security_token_information",
          520);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    v12 = v20;
    v20 = 0;
    v13 = TokenInformation[1];
    TokenInformation[1] = 0;
    v14 = TokenInformation[0];
    TokenInformation[0] = 0;
    *(_QWORD *)a1 = v14;
    *(_QWORD *)(a1 + 8) = v13;
    *(_QWORD *)(a1 + 16) = v12;
    *(_BYTE *)(a1 + 24) = 1;
    std::vector<char>::~vector<char>((char **)TokenInformation);
  }
  else
  {
    *(_BYTE *)(a1 + 24) = 0;
  }
  v15 = TokenHandle;
  if ( TokenHandle )
  {
    TokenHandle = 0;
    CloseHandle(v15);
  }
  TokenHandle = 0;
  if ( v5 )
    CloseHandle(v5);
  return a1;
}

```

## disassembly

```asm
0x180080ea0  push    rbp
0x180080ea2  push    rbx
0x180080ea3  push    rsi
0x180080ea4  push    rdi
0x180080ea5  push    r12
0x180080ea7  push    r14
0x180080ea9  push    r15
0x180080eab  lea     rbp, [rsp-3B0h]
0x180080eb3  sub     rsp, 4B0h
0x180080eba  mov     rax, cs:__security_cookie
0x180080ec1  xor     rax, rsp
0x180080ec4  mov     [rbp+3E0h+var_40], rax
0x180080ecb  mov     r15d, r8d
0x180080ece  mov     rsi, rcx
0x180080ed1  mov     [rsp+4E0h+var_488], rcx
0x180080ed6  xor     r12d, r12d
0x180080ed9  mov     r8d, edx; dwProcessId
0x180080edc  xor     edx, edx; bInheritHandle
0x180080ede  mov     ecx, 1000h; dwDesiredAccess
0x180080ee3  call    cs:__imp_OpenProcess
0x180080ee9  mov     rbx, rax
0x180080eec  mov     [rsp+4E0h+var_478], rax
0x180080ef1  test    rax, rax
0x180080ef4  jnz     short loc_180080F04
0x180080ef6  call    cs:__imp_GetLastError
0x180080efc  test    eax, eax
0x180080efe  jnz     loc_1800810BE
0x180080f04  mov     [rsp+4E0h+TokenHandle], r12
0x180080f09  lea     r8, [rsp+4E0h+TokenHandle]; TokenHandle
0x180080f0e  mov     edx, 8; DesiredAccess
0x180080f13  mov     rcx, rbx; ProcessHandle
0x180080f16  call    cs:__imp_OpenProcessToken
0x180080f1c  test    eax, eax
0x180080f1e  jnz     short loc_180080F2E
0x180080f20  call    cs:__imp_GetLastError
0x180080f26  test    eax, eax
0x180080f28  jnz     loc_1800810FA
0x180080f2e  mov     [rsp+4E0h+TokenInformationLength], r12d
0x180080f33  lea     rax, [rsp+4E0h+TokenInformationLength]
0x180080f38  mov     [rsp+4E0h+ReturnLength], rax; ReturnLength
0x180080f3d  xor     r9d, r9d; TokenInformationLength
0x180080f40  xor     r8d, r8d; TokenInformation
0x180080f43  mov     edx, r15d; TokenInformationClass
0x180080f46  mov     rcx, [rsp+4E0h+TokenHandle]; TokenHandle
0x180080f4b  call    cs:__imp_GetTokenInformation
0x180080f51  test    eax, eax
0x180080f53  jnz     loc_180081032
0x180080f59  call    cs:__imp_GetLastError
0x180080f5f  cmp     eax, 7Ah ; 'z'
0x180080f62  jz      short loc_180080F73
0x180080f64  call    cs:__imp_GetLastError
0x180080f6a  cmp     eax, 18h
0x180080f6d  jnz     loc_180081032
0x180080f73  mov     r9d, [rsp+4E0h+TokenInformationLength]
0x180080f78  mov     r14d, r9d
0x180080f7b  xorps   xmm0, xmm0
0x180080f7e  movdqu  xmmword ptr [rsp+4E0h+TokenInformation], xmm0
0x180080f84  mov     [rsp+4E0h+var_490], r12
0x180080f89  test    r9d, r9d
0x180080f8c  jz      short loc_180080FCA
0x180080f8e  mov     edx, r9d
0x180080f91  lea     rcx, [rsp+4E0h+TokenInformation]
0x180080f96  call    ?_Buy_nonzero@?$vector@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::vector<char>::_Buy_nonzero(unsigned __int64)
0x180080f9b  mov     rdi, [rsp+4E0h+TokenInformation]
0x180080fa0  mov     r8d, r14d; Size
0x180080fa3  xor     edx, edx; Val
0x180080fa5  mov     rcx, rdi; void *
0x180080fa8  call    memset_0
0x180080fad  lea     rax, [r14+rdi]
0x180080fb1  mov     [rsp+4E0h+TokenInformation+8], rax
0x180080fb6  mov     [rsp+4E0h+var_488], r12
0x180080fbb  lea     rcx, [rsp+4E0h+var_488]
0x180080fc0  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180080fc5  mov     r9d, [rsp+4E0h+TokenInformationLength]; TokenInformationLength
0x180080fca  lea     rax, [rsp+4E0h+TokenInformationLength]
0x180080fcf  mov     [rsp+4E0h+ReturnLength], rax; ReturnLength
0x180080fd4  mov     r8, [rsp+4E0h+TokenInformation]; TokenInformation
0x180080fd9  mov     edx, r15d; TokenInformationClass
0x180080fdc  mov     rcx, [rsp+4E0h+TokenHandle]; TokenHandle
0x180080fe1  call    cs:__imp_GetTokenInformation
0x180080fe7  test    eax, eax
0x180080fe9  jnz     short loc_180080FF9
0x180080feb  call    cs:__imp_GetLastError
0x180080ff1  test    eax, eax
0x180080ff3  jnz     loc_180081082
0x180080ff9  mov     rdx, [rsp+4E0h+var_490]
0x180080ffe  mov     [rsp+4E0h+var_490], r12
0x180081003  mov     rcx, [rsp+4E0h+TokenInformation+8]
0x180081008  mov     [rsp+4E0h+TokenInformation+8], r12
0x18008100d  mov     rax, [rsp+4E0h+TokenInformation]
0x180081012  mov     [rsp+4E0h+TokenInformation], r12
0x180081017  mov     [rsi], rax
0x18008101a  mov     [rsi+8], rcx
0x18008101e  mov     [rsi+10h], rdx
0x180081022  mov     byte ptr [rsi+18h], 1
0x180081026  lea     rcx, [rsp+4E0h+TokenInformation]
0x18008102b  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180081030  jmp     short loc_180081036
0x180081032  mov     [rsi+18h], r12b
0x180081036  mov     rcx, [rsp+4E0h+TokenHandle]; hObject
0x18008103b  test    rcx, rcx
0x18008103e  jz      short loc_18008104B
0x180081040  mov     [rsp+4E0h+TokenHandle], r12
0x180081045  call    cs:__imp_CloseHandle
0x18008104b  mov     [rsp+4E0h+TokenHandle], r12
0x180081050  test    rbx, rbx
0x180081053  jz      short loc_18008105E
0x180081055  mov     rcx, rbx; hObject
0x180081058  call    cs:__imp_CloseHandle
0x18008105e  mov     rax, rsi
0x180081061  mov     rcx, [rbp+3E0h+var_40]
0x180081068  xor     rcx, rsp; StackCookie
0x18008106b  call    __security_check_cookie
0x180081070  add     rsp, 4B0h
0x180081077  pop     r15
0x180081079  pop     r14
0x18008107b  pop     r12
0x18008107d  pop     rdi
0x18008107e  pop     rsi
0x18008107f  pop     rbx
0x180081080  pop     rbp
0x180081081  retn
0x180081082  mov     edx, eax; __int64
0x180081084  mov     [rsp+4E0h+var_4B8], 208h
0x18008108c  lea     rax, aGetSecurityTok; "get_security_token_information"
0x180081093  mov     [rsp+4E0h+ReturnLength], rax
0x180081098  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008109f  xor     r8d, r8d; void *
0x1800810a2  lea     rcx, [rsp+4E0h+pExceptionObject]; this
0x1800810a7  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800810ac  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800810b3  lea     rcx, [rsp+4E0h+pExceptionObject]; pExceptionObject
0x1800810b8  call    _CxxThrowException_0
0x1800810be  mov     edx, eax; __int64
0x1800810c0  mov     [rsp+4E0h+var_4B8], 1FEh
0x1800810c8  lea     rax, aGetSecurityTok; "get_security_token_information"
0x1800810cf  mov     [rsp+4E0h+ReturnLength], rax
0x1800810d4  lea     r9, aSDFailed; "[%s:%d] failed; "
0x1800810db  xor     r8d, r8d; void *
0x1800810de  lea     rcx, [rsp+4E0h+pExceptionObject]; this
0x1800810e3  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800810e8  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800810ef  lea     rcx, [rsp+4E0h+pExceptionObject]; pExceptionObject
0x1800810f4  call    _CxxThrowException_0
0x1800810fa  mov     edx, eax; __int64
0x1800810fc  mov     [rsp+4E0h+var_4B8], 201h
0x180081104  lea     rax, aGetSecurityTok; "get_security_token_information"
0x18008110b  mov     [rsp+4E0h+ReturnLength], rax
0x180081110  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180081117  xor     r8d, r8d; void *
0x18008111a  lea     rcx, [rsp+4E0h+pExceptionObject]; this
0x18008111f  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180081124  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008112b  lea     rcx, [rsp+4E0h+pExceptionObject]; pExceptionObject
0x180081130  call    _CxxThrowException_0
```
