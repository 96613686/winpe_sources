# CUtils::IsTokenSid(void *,void *)

- ea: `0x18003028c`
- end: `0x18003042c`
- name: `?IsTokenSid@CUtils@@CAJPEAX0@Z`
- size: `416`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID Sid2)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002f2f0`
- `0x1800a27d8`

## callees

- `0x180009940`
- `0x18003028c`
- `0x180033f60`
- `0x180034df8`
- `0x1800cae70`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800303f9`
- `ntdll!RtlEqualSid` at `0x1800303f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800302fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800303cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800302fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800303cc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800302e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800303bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800302e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800303bc`

## string_xrefs

- `0x180030316`: `IsTokenSid: Error %x Getting TokenInformation`
- `0x1800303e7`: `IsTokenSid: Error %x Getting TokenInformation on buffer\n`
- `0x18003038f`: `IsTokenSid: Error allocating %d bytes memory\n`

## pseudocode

```c
__int64 __fastcall CUtils::IsTokenSid(HANDLE TokenHandle, PSID Sid2)
{
  unsigned int v4; // ebx
  signed int v5; // eax
  unsigned __int64 v6; // rcx
  void *v7; // rsp
  void *v8; // rsp
  signed int LastError; // eax
  PSID TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  PSID *p_TokenInformation; // [rsp+38h] [rbp+8h]

  if ( Sid2 )
  {
    LODWORD(TokenInformation) = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&TokenInformation);
    if ( (_DWORD)TokenInformation )
    {
      HIDWORD(TokenInformation) = (_DWORD)TokenInformation;
      v6 = (unsigned int)TokenInformation + 15LL;
      if ( v6 < (unsigned int)TokenInformation )
        v6 = 0xFFFFFFFFFFFFFF0LL;
      v7 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
      v8 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
      p_TokenInformation = &TokenInformation;
      if ( &TokenInformation )
      {
        if ( GetTokenInformation(
               TokenHandle,
               TokenUser,
               &TokenInformation,
               (DWORD)TokenInformation,
               (PDWORD)&TokenInformation) )
        {
          return RtlEqualSid(TokenInformation, Sid2) == 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          _DbgPrintMessage(8, "IsTokenSid: Error %x Getting TokenInformation on buffer\n", v4);
        }
      }
      else
      {
        _DbgPrintMessage(8, "IsTokenSid: Error allocating %d bytes memory\n", (_DWORD)TokenInformation);
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      _DbgPrintMessage(8, "IsTokenSid: Error %x Getting TokenInformation", v4);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v4;
}

```

## disassembly

```asm
0x18003028c  mov     [rsp-8+arg_8], rdx
0x180030291  mov     [rsp-8+arg_0], rcx
0x180030296  push    rbp
0x180030297  push    rdi
0x180030298  push    r14
0x18003029a  sub     rsp, 50h
0x18003029e  lea     rbp, [rsp+30h]
0x1800302a3  mov     [rbp+30h+arg_10], rbx
0x1800302a7  mov     [rbp+30h+arg_18], rsi
0x1800302ab  mov     rax, cs:__security_cookie
0x1800302b2  xor     rax, rbp
0x1800302b5  mov     [rbp+30h+var_20], rax
0x1800302b9  mov     rsi, rdx
0x1800302bc  mov     r14, rcx
0x1800302bf  test    rdx, rdx
0x1800302c2  jnz     short loc_1800302CE
0x1800302c4  mov     ebx, 8000FFFFh
0x1800302c9  jmp     loc_18003040C
0x1800302ce  mov     [rbp+30h+TokenInformation], 0
0x1800302d5  lea     rax, [rbp+30h+TokenInformation]
0x1800302d9  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800302de  xor     r9d, r9d; TokenInformationLength
0x1800302e1  xor     r8d, r8d; TokenInformation
0x1800302e4  lea     edx, [r9+1]; TokenInformationClass
0x1800302e8  call    cs:__imp_GetTokenInformation
0x1800302ef  nop     dword ptr [rax+rax+00h]
0x1800302f4  mov     ebx, [rbp+30h+TokenInformation]
0x1800302f7  test    ebx, ebx
0x1800302f9  jnz     short loc_18003032F
0x1800302fb  call    cs:__imp_GetLastError
0x180030302  nop     dword ptr [rax+rax+00h]
0x180030307  mov     ebx, eax
0x180030309  test    eax, eax
0x18003030b  jle     short loc_180030316
0x18003030d  movzx   ebx, ax
0x180030310  or      ebx, 80070000h
0x180030316  lea     rdx, aIstokensidErro_1; "IsTokenSid: Error %x Getting TokenInfor"...
0x18003031d  mov     r8d, ebx
0x180030320  mov     ecx, 8; int
0x180030325  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003032a  jmp     loc_18003040C
0x18003032f  mov     [rbp+30h+var_2C], ebx
0x180030332  lea     rcx, [rbx+0Fh]
0x180030336  cmp     rcx, rbx
0x180030339  ja      short loc_180030345
0x18003033b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180030345  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180030349  mov     rax, rcx
0x18003034c  call    _alloca_probe
0x180030351  sub     rsp, rcx
0x180030354  lea     rdi, [rsp+60h+TokenInformation]
0x180030359  mov     [rbp+30h+var_28], rdi
0x18003035d  jmp     short loc_180030387
0x18003035f  call    _o__resetstkoflw_0
0x180030364  xor     edi, edi
0x180030366  mov     [rbp+30h+var_28], rdi
0x18003036a  mov     ebx, [rbp+30h+var_2C]
0x18003036d  mov     r8d, ebx
0x180030370  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x180030377  lea     ecx, [rdi+8]; int
0x18003037a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003037f  mov     rsi, [rbp+30h+arg_8]
0x180030383  mov     r14, [rbp+30h+arg_0]
0x180030387  test    rdi, rdi
0x18003038a  jnz     short loc_1800303A5
0x18003038c  mov     r8d, ebx
0x18003038f  lea     rdx, aIstokensidErro; "IsTokenSid: Error allocating %d bytes m"...
0x180030396  lea     ecx, [rdi+8]; int
0x180030399  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003039e  mov     ebx, 8007000Eh
0x1800303a3  jmp     short loc_18003040C
0x1800303a5  lea     rax, [rbp+30h+TokenInformation]
0x1800303a9  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800303ae  mov     r9d, ebx; TokenInformationLength
0x1800303b1  mov     r8, rdi; TokenInformation
0x1800303b4  mov     edx, 1; TokenInformationClass
0x1800303b9  mov     rcx, r14; TokenHandle
0x1800303bc  call    cs:__imp_GetTokenInformation
0x1800303c3  nop     dword ptr [rax+rax+00h]
0x1800303c8  test    eax, eax
0x1800303ca  jnz     short loc_1800303F3
0x1800303cc  call    cs:__imp_GetLastError
0x1800303d3  nop     dword ptr [rax+rax+00h]
0x1800303d8  mov     ebx, eax
0x1800303da  test    eax, eax
0x1800303dc  jle     short loc_1800303E7
0x1800303de  movzx   ebx, ax
0x1800303e1  or      ebx, 80070000h
0x1800303e7  lea     rdx, aIstokensidErro_0; "IsTokenSid: Error %x Getting TokenInfor"...
0x1800303ee  jmp     loc_18003031D
0x1800303f3  mov     rdx, rsi; Sid2
0x1800303f6  mov     rcx, [rdi]; Sid1
0x1800303f9  call    cs:__imp_RtlEqualSid
0x180030400  nop     dword ptr [rax+rax+00h]
0x180030405  xor     ebx, ebx
0x180030407  test    al, al
0x180030409  setz    bl
0x18003040c  mov     eax, ebx
0x18003040e  mov     rcx, [rbp+30h+var_20]
0x180030412  xor     rcx, rbp; StackCookie
0x180030415  call    __security_check_cookie
0x18003041a  mov     rbx, [rbp+30h+arg_10]
0x18003041e  mov     rsi, [rbp+30h+arg_18]
0x180030422  lea     rsp, [rbp+20h]
0x180030426  pop     r14
0x180030428  pop     rdi
0x180030429  pop     rbp
0x18003042a  retn
0x1800cb502  push    rbp
0x1800cb504  sub     rsp, 30h
0x1800cb508  lea     rbp, [rdx+30h]
0x1800cb50c  mov     rax, [rcx]
0x1800cb50f  xor     ecx, ecx
0x1800cb511  cmp     dword ptr [rax], 0C00000FDh
0x1800cb517  setz    cl
0x1800cb51a  mov     eax, ecx
0x1800cb51c  add     rsp, 30h
0x1800cb520  pop     rbp
0x1800cb521  retn
```
