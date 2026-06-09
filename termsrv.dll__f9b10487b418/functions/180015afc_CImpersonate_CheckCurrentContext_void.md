# CImpersonate::CheckCurrentContext(void *)

- ea: `0x180015afc`
- end: `0x180015cff`
- name: `?CheckCurrentContext@CImpersonate@@AEAAJPEAX@Z`
- size: `515`
- prototype: `int(CImpersonate *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004da60`
- `0x1800b8d28`

## callees

- `0x18000a210`
- `0x180015afc`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180015c90`
- `ntdll!RtlEqualSid` at `0x180015c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015b2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015b2a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015b41`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015b41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cbd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015bb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015c54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015bb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015c54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ccb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ccb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015cd9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015b7e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015bf3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015c27`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015c7c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015b7e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015bf3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015c27`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015c7c`

## string_xrefs

- `0x180015b95`: `CheckCurrentContext: FAILED to get size infomration for input token, Error %x`
- `0x180015c3e`: `CheckCurrentContext: FAILED to get size infomration for current token, Error %x`
- `0x180015c05`: `CheckCurrentContext: FAILED to get token infomration for input token, Error %x`
- `0x180015c9e`: `TERMSRV: CheckCurrentContext - Different user is being impersonated`

## pseudocode

```c
__int64 __fastcall CImpersonate::CheckCurrentContext(CImpersonate *this, void *a2)
{
  PSID *v3; // rsi
  PSID *v4; // rdi
  HANDLE CurrentThread; // rax
  __int64 v6; // rbx
  DWORD LastError; // eax
  DWORD v8; // ebx
  DWORD v9; // eax
  DWORD v10; // ebx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  int v13; // [rsp+64h] [rbp+34h]
  void *TokenHandle; // [rsp+70h] [rbp+40h] BYREF

  v13 = HIDWORD(this);
  TokenHandle = 0;
  TokenInformationLength = 0;
  v3 = 0;
  v4 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    LODWORD(v6) = GetLastError();
    goto LABEL_20;
  }
  LODWORD(v6) = 1375;
  if ( a2 )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) )
    {
      LastError = GetLastError();
      LODWORD(v6) = LastError;
      if ( LastError != 122 )
      {
        _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get size infomration for input token, Error %x", LastError);
        goto LABEL_20;
      }
    }
    v8 = TokenInformationLength;
    v3 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v3 )
    {
LABEL_9:
      LODWORD(v6) = 8;
      _DbgPrintMessage(8, "CheckCurrentContext: FAILED to allocate memory");
      goto LABEL_20;
    }
    if ( !GetTokenInformation(a2, TokenUser, v3, v8, &TokenInformationLength) )
      goto LABEL_11;
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v9 = GetLastError();
      LODWORD(v6) = v9;
      if ( v9 != 122 )
      {
        _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get size infomration for current token, Error %x", v9);
        goto LABEL_20;
      }
    }
    v10 = TokenInformationLength;
    v4 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v4 )
      goto LABEL_9;
    if ( !GetTokenInformation(TokenHandle, TokenUser, v4, v10, &TokenInformationLength) )
    {
LABEL_11:
      v6 = GetLastError();
      _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get token infomration for input token, Error %x", v6);
      goto LABEL_20;
    }
    if ( RtlEqualSid(*v3, *v4) )
    {
      LODWORD(v6) = 0;
    }
    else
    {
      _DbgPrintMessage(4, "TERMSRV: CheckCurrentContext - Different user is being impersonated");
      LODWORD(v6) = 1375;
    }
  }
LABEL_20:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v3 )
    LocalFree(v3);
  if ( v4 )
    LocalFree(v4);
  if ( (int)v6 > 0 )
    LODWORD(v6) = (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015afc  mov     [rsp-28h+arg_8], rbx
0x180015b01  mov     qword ptr [rsp-28h+TokenInformationLength], rcx
0x180015b06  push    rbp
0x180015b07  push    rsi
0x180015b08  push    rdi
0x180015b09  push    r12
0x180015b0b  push    r14
0x180015b0d  mov     rbp, rsp
0x180015b10  sub     rsp, 30h
0x180015b14  mov     r14, rdx
0x180015b17  mov     [rbp+TokenHandle], 0
0x180015b1f  mov     [rbp+TokenInformationLength], 0
0x180015b26  xor     esi, esi
0x180015b28  xor     edi, edi
0x180015b2a  call    cs:__imp_GetCurrentThread
0x180015b30  lea     r12d, [rsi+1]
0x180015b34  mov     rcx, rax; ThreadHandle
0x180015b37  mov     r8d, r12d; OpenAsSelf
0x180015b3a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180015b3e  lea     edx, [rsi+0Eh]; DesiredAccess
0x180015b41  call    cs:__imp_OpenThreadToken
0x180015b47  test    eax, eax
0x180015b49  jnz     short loc_180015B58
0x180015b4b  call    cs:__imp_GetLastError
0x180015b51  mov     ebx, eax
0x180015b53  jmp     loc_180015CB4
0x180015b58  mov     ebx, 55Fh
0x180015b5d  test    r14, r14
0x180015b60  jz      loc_180015CB4
0x180015b66  lea     rax, [rbp+TokenInformationLength]
0x180015b6a  mov     [rbp+TokenInformationLength], esi
0x180015b6d  xor     r9d, r9d; TokenInformationLength
0x180015b70  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180015b75  xor     r8d, r8d; TokenInformation
0x180015b78  mov     edx, r12d; TokenInformationClass
0x180015b7b  mov     rcx, r14; TokenHandle
0x180015b7e  call    cs:__imp_GetTokenInformation
0x180015b84  test    eax, eax
0x180015b86  jnz     short loc_180015BAE
0x180015b88  call    cs:__imp_GetLastError
0x180015b8e  mov     ebx, eax
0x180015b90  cmp     eax, 7Ah ; 'z'
0x180015b93  jz      short loc_180015BAE
0x180015b95  lea     rdx, aCheckcurrentco_0; "CheckCurrentContext: FAILED to get size"...
0x180015b9c  mov     r8d, eax
0x180015b9f  mov     ecx, 8; int
0x180015ba4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015ba9  jmp     loc_180015CB4
0x180015bae  mov     ebx, [rbp+TokenInformationLength]
0x180015bb1  mov     ecx, 40h ; '@'; uFlags
0x180015bb6  mov     edx, ebx; uBytes
0x180015bb8  call    cs:__imp_LocalAlloc
0x180015bbe  mov     rsi, rax
0x180015bc1  test    rax, rax
0x180015bc4  jnz     short loc_180015BDE
0x180015bc6  mov     ebx, 8
0x180015bcb  lea     rdx, aCheckcurrentco_3; "CheckCurrentContext: FAILED to allocate"...
0x180015bd2  mov     ecx, ebx; int
0x180015bd4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015bd9  jmp     loc_180015CB4
0x180015bde  lea     rax, [rbp+TokenInformationLength]
0x180015be2  mov     r9d, ebx; TokenInformationLength
0x180015be5  mov     r8, rsi; TokenInformation
0x180015be8  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180015bed  mov     edx, r12d; TokenInformationClass
0x180015bf0  mov     rcx, r14; TokenHandle
0x180015bf3  call    cs:__imp_GetTokenInformation
0x180015bf9  test    eax, eax
0x180015bfb  jnz     short loc_180015C0E
0x180015bfd  call    cs:__imp_GetLastError
0x180015c03  mov     ebx, eax
0x180015c05  lea     rdx, aCheckcurrentco; "CheckCurrentContext: FAILED to get toke"...
0x180015c0c  jmp     short loc_180015B9C
0x180015c0e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180015c12  lea     rax, [rbp+TokenInformationLength]
0x180015c16  xor     r9d, r9d; TokenInformationLength
0x180015c19  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180015c1e  xor     r8d, r8d; TokenInformation
0x180015c21  mov     [rbp+TokenInformationLength], edi
0x180015c24  mov     edx, r12d; TokenInformationClass
0x180015c27  call    cs:__imp_GetTokenInformation
0x180015c2d  test    eax, eax
0x180015c2f  jnz     short loc_180015C4A
0x180015c31  call    cs:__imp_GetLastError
0x180015c37  mov     ebx, eax
0x180015c39  cmp     eax, 7Ah ; 'z'
0x180015c3c  jz      short loc_180015C4A
0x180015c3e  lea     rdx, aCheckcurrentco_1; "CheckCurrentContext: FAILED to get size"...
0x180015c45  jmp     loc_180015B9C
0x180015c4a  mov     ebx, [rbp+TokenInformationLength]
0x180015c4d  mov     ecx, 40h ; '@'; uFlags
0x180015c52  mov     edx, ebx; uBytes
0x180015c54  call    cs:__imp_LocalAlloc
0x180015c5a  mov     rdi, rax
0x180015c5d  test    rax, rax
0x180015c60  jz      loc_180015BC6
0x180015c66  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180015c6a  lea     rax, [rbp+TokenInformationLength]
0x180015c6e  mov     r9d, ebx; TokenInformationLength
0x180015c71  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180015c76  mov     r8, rdi; TokenInformation
0x180015c79  mov     edx, r12d; TokenInformationClass
0x180015c7c  call    cs:__imp_GetTokenInformation
0x180015c82  test    eax, eax
0x180015c84  jz      loc_180015BFD
0x180015c8a  mov     rdx, [rdi]; Sid2
0x180015c8d  mov     rcx, [rsi]; Sid1
0x180015c90  call    cs:__imp_RtlEqualSid
0x180015c96  test    al, al
0x180015c98  jz      short loc_180015C9E
0x180015c9a  xor     ebx, ebx
0x180015c9c  jmp     short loc_180015CB4
0x180015c9e  lea     rdx, aTermsrvCheckcu; "TERMSRV: CheckCurrentContext - Differen"...
0x180015ca5  mov     ecx, 4; int
0x180015caa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015caf  mov     ebx, 55Fh
0x180015cb4  mov     rcx, [rbp+TokenHandle]; hObject
0x180015cb8  test    rcx, rcx
0x180015cbb  jz      short loc_180015CC3
0x180015cbd  call    cs:__imp_CloseHandle
0x180015cc3  test    rsi, rsi
0x180015cc6  jz      short loc_180015CD1
0x180015cc8  mov     rcx, rsi; hMem
0x180015ccb  call    cs:__imp_LocalFree
0x180015cd1  test    rdi, rdi
0x180015cd4  jz      short loc_180015CDF
0x180015cd6  mov     rcx, rdi; hMem
0x180015cd9  call    cs:__imp_LocalFree
0x180015cdf  test    ebx, ebx
0x180015ce1  jle     short loc_180015CEC
0x180015ce3  movzx   ebx, bx
0x180015ce6  or      ebx, 80070000h
0x180015cec  mov     eax, ebx
0x180015cee  mov     rbx, [rsp+30h+arg_8]
0x180015cf3  add     rsp, 30h
0x180015cf7  pop     r14
0x180015cf9  pop     r12
0x180015cfb  pop     rdi
0x180015cfc  pop     rsi
0x180015cfd  pop     rbp
0x180015cfe  retn
```
