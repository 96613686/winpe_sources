# CImpersonate::CheckCurrentContext(void *)

- ea: `0x180016650`
- end: `0x1800168b7`
- name: `?CheckCurrentContext@CImpersonate@@AEAAJPEAX@Z`
- size: `615`
- prototype: `int(CImpersonate *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800500a0`
- `0x1800bf63c`

## callees

- `0x180009940`
- `0x180016650`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18001682f`
- `ntdll!RtlEqualSid` at `0x18001682f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001677b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001677b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001667e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001667e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001669b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001669b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016862`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016862`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001672a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800167e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001672a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800167e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016876`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001688a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016876`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001688a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800166e4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001676b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800167ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016815`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800166e4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001676b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800167ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016815`

## string_xrefs

- `0x180016707`: `CheckCurrentContext: FAILED to get size infomration for input token, Error %x`
- `0x1800167d1`: `CheckCurrentContext: FAILED to get size infomration for current token, Error %x`
- `0x180016789`: `CheckCurrentContext: FAILED to get token infomration for input token, Error %x`
- `0x180016843`: `TERMSRV: CheckCurrentContext - Different user is being impersonated`

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
0x180016650  mov     [rsp-28h+arg_8], rbx
0x180016655  mov     qword ptr [rsp-28h+TokenInformationLength], rcx
0x18001665a  push    rbp
0x18001665b  push    rsi
0x18001665c  push    rdi
0x18001665d  push    r12
0x18001665f  push    r14
0x180016661  mov     rbp, rsp
0x180016664  sub     rsp, 30h
0x180016668  mov     r14, rdx
0x18001666b  mov     [rbp+TokenHandle], 0
0x180016673  mov     [rbp+TokenInformationLength], 0
0x18001667a  xor     esi, esi
0x18001667c  xor     edi, edi
0x18001667e  call    cs:__imp_GetCurrentThread
0x180016685  nop     dword ptr [rax+rax+00h]
0x18001668a  lea     r12d, [rsi+1]
0x18001668e  mov     rcx, rax; ThreadHandle
0x180016691  mov     r8d, r12d; OpenAsSelf
0x180016694  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180016698  lea     edx, [rsi+0Eh]; DesiredAccess
0x18001669b  call    cs:__imp_OpenThreadToken
0x1800166a2  nop     dword ptr [rax+rax+00h]
0x1800166a7  test    eax, eax
0x1800166a9  jnz     short loc_1800166BE
0x1800166ab  call    cs:__imp_GetLastError
0x1800166b2  nop     dword ptr [rax+rax+00h]
0x1800166b7  mov     ebx, eax
0x1800166b9  jmp     loc_180016859
0x1800166be  mov     ebx, 55Fh
0x1800166c3  test    r14, r14
0x1800166c6  jz      loc_180016859
0x1800166cc  lea     rax, [rbp+TokenInformationLength]
0x1800166d0  mov     [rbp+TokenInformationLength], esi
0x1800166d3  xor     r9d, r9d; TokenInformationLength
0x1800166d6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800166db  xor     r8d, r8d; TokenInformation
0x1800166de  mov     edx, r12d; TokenInformationClass
0x1800166e1  mov     rcx, r14; TokenHandle
0x1800166e4  call    cs:__imp_GetTokenInformation
0x1800166eb  nop     dword ptr [rax+rax+00h]
0x1800166f0  test    eax, eax
0x1800166f2  jnz     short loc_180016720
0x1800166f4  call    cs:__imp_GetLastError
0x1800166fb  nop     dword ptr [rax+rax+00h]
0x180016700  mov     ebx, eax
0x180016702  cmp     eax, 7Ah ; 'z'
0x180016705  jz      short loc_180016720
0x180016707  lea     rdx, aCheckcurrentco_0; "CheckCurrentContext: FAILED to get size"...
0x18001670e  mov     r8d, eax
0x180016711  mov     ecx, 8; int
0x180016716  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001671b  jmp     loc_180016859
0x180016720  mov     ebx, [rbp+TokenInformationLength]
0x180016723  mov     ecx, 40h ; '@'; uFlags
0x180016728  mov     edx, ebx; uBytes
0x18001672a  call    cs:__imp_LocalAlloc
0x180016731  nop     dword ptr [rax+rax+00h]
0x180016736  mov     rsi, rax
0x180016739  test    rax, rax
0x18001673c  jnz     short loc_180016756
0x18001673e  mov     ebx, 8
0x180016743  lea     rdx, aCheckcurrentco_3; "CheckCurrentContext: FAILED to allocate"...
0x18001674a  mov     ecx, ebx; int
0x18001674c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180016751  jmp     loc_180016859
0x180016756  lea     rax, [rbp+TokenInformationLength]
0x18001675a  mov     r9d, ebx; TokenInformationLength
0x18001675d  mov     r8, rsi; TokenInformation
0x180016760  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180016765  mov     edx, r12d; TokenInformationClass
0x180016768  mov     rcx, r14; TokenHandle
0x18001676b  call    cs:__imp_GetTokenInformation
0x180016772  nop     dword ptr [rax+rax+00h]
0x180016777  test    eax, eax
0x180016779  jnz     short loc_180016795
0x18001677b  call    cs:__imp_GetLastError
0x180016782  nop     dword ptr [rax+rax+00h]
0x180016787  mov     ebx, eax
0x180016789  lea     rdx, aCheckcurrentco; "CheckCurrentContext: FAILED to get toke"...
0x180016790  jmp     loc_18001670E
0x180016795  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180016799  lea     rax, [rbp+TokenInformationLength]
0x18001679d  xor     r9d, r9d; TokenInformationLength
0x1800167a0  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800167a5  xor     r8d, r8d; TokenInformation
0x1800167a8  mov     [rbp+TokenInformationLength], edi
0x1800167ab  mov     edx, r12d; TokenInformationClass
0x1800167ae  call    cs:__imp_GetTokenInformation
0x1800167b5  nop     dword ptr [rax+rax+00h]
0x1800167ba  test    eax, eax
0x1800167bc  jnz     short loc_1800167DD
0x1800167be  call    cs:__imp_GetLastError
0x1800167c5  nop     dword ptr [rax+rax+00h]
0x1800167ca  mov     ebx, eax
0x1800167cc  cmp     eax, 7Ah ; 'z'
0x1800167cf  jz      short loc_1800167DD
0x1800167d1  lea     rdx, aCheckcurrentco_1; "CheckCurrentContext: FAILED to get size"...
0x1800167d8  jmp     loc_18001670E
0x1800167dd  mov     ebx, [rbp+TokenInformationLength]
0x1800167e0  mov     ecx, 40h ; '@'; uFlags
0x1800167e5  mov     edx, ebx; uBytes
0x1800167e7  call    cs:__imp_LocalAlloc
0x1800167ee  nop     dword ptr [rax+rax+00h]
0x1800167f3  mov     rdi, rax
0x1800167f6  test    rax, rax
0x1800167f9  jz      loc_18001673E
0x1800167ff  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180016803  lea     rax, [rbp+TokenInformationLength]
0x180016807  mov     r9d, ebx; TokenInformationLength
0x18001680a  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001680f  mov     r8, rdi; TokenInformation
0x180016812  mov     edx, r12d; TokenInformationClass
0x180016815  call    cs:__imp_GetTokenInformation
0x18001681c  nop     dword ptr [rax+rax+00h]
0x180016821  test    eax, eax
0x180016823  jz      loc_18001677B
0x180016829  mov     rdx, [rdi]; Sid2
0x18001682c  mov     rcx, [rsi]; Sid1
0x18001682f  call    cs:__imp_RtlEqualSid
0x180016836  nop     dword ptr [rax+rax+00h]
0x18001683b  test    al, al
0x18001683d  jz      short loc_180016843
0x18001683f  xor     ebx, ebx
0x180016841  jmp     short loc_180016859
0x180016843  lea     rdx, aTermsrvCheckcu; "TERMSRV: CheckCurrentContext - Differen"...
0x18001684a  mov     ecx, 4; int
0x18001684f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180016854  mov     ebx, 55Fh
0x180016859  mov     rcx, [rbp+TokenHandle]; hObject
0x18001685d  test    rcx, rcx
0x180016860  jz      short loc_18001686E
0x180016862  call    cs:__imp_CloseHandle
0x180016869  nop     dword ptr [rax+rax+00h]
0x18001686e  test    rsi, rsi
0x180016871  jz      short loc_180016882
0x180016873  mov     rcx, rsi; hMem
0x180016876  call    cs:__imp_LocalFree
0x18001687d  nop     dword ptr [rax+rax+00h]
0x180016882  test    rdi, rdi
0x180016885  jz      short loc_180016896
0x180016887  mov     rcx, rdi; hMem
0x18001688a  call    cs:__imp_LocalFree
0x180016891  nop     dword ptr [rax+rax+00h]
0x180016896  test    ebx, ebx
0x180016898  jle     short loc_1800168A3
0x18001689a  movzx   ebx, bx
0x18001689d  or      ebx, 80070000h
0x1800168a3  mov     eax, ebx
0x1800168a5  mov     rbx, [rsp+30h+arg_8]
0x1800168aa  add     rsp, 30h
0x1800168ae  pop     r14
0x1800168b0  pop     r12
0x1800168b2  pop     rdi
0x1800168b3  pop     rsi
0x1800168b4  pop     rbp
0x1800168b5  retn
```
