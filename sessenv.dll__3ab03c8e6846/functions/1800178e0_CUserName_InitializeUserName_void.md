# CUserName::InitializeUserName(void *)

- ea: `0x1800178e0`
- end: `0x180017a22`
- name: `?InitializeUserName@CUserName@@AEAAJPEAX@Z`
- size: `322`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014440`
- `0x18005a750`
- `0x18005ab50`
- `0x18005ac20`
- `0x18005acdc`
- `0x18005b1a0`

## callees

- `0x180003f30`
- `0x180013160`
- `0x1800178e0`
- `0x18001a2a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001797d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001797d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179e1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017916`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017973`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017916`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017973`

## string_xrefs

- `0x180017992`: `GetTokenInformatino failed: 0x%x`
- `0x1800179f6`: `Can get the TOKEN_USER length: 0x%x`
- `0x1800179ff`: `Can get the TOKEN_USER length`

## pseudocode

```c
__int64 __fastcall CUserName::InitializeUserName(CUserName *this, void *a2)
{
  void *v4; // rax
  unsigned int v5; // ebx
  signed int LastError; // eax
  int v7; // eax
  signed int v8; // eax
  DWORD TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  ReturnLength = 0;
  if ( GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v5 = -2147024809;
    _DbgPrintMessage(8, "Can get the TOKEN_USER length");
  }
  else if ( GetLastError() == 122 )
  {
    v4 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
    *((_QWORD *)this + 201) = v4;
    if ( v4 )
    {
      if ( GetTokenInformation(a2, TokenUser, v4, TokenInformationLength, &ReturnLength) )
      {
        v7 = CUserName::ResolveUserName(this, a2);
        v5 = v7;
        if ( v7 >= 0 )
        {
          *((_DWORD *)this + 400) |= 2u;
          return 0;
        }
        else
        {
          _DbgPrintMessage(8, "ResolveUserName failed: 0x%x in %s", v7, "CUserName::InitializeUserName");
        }
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        _DbgPrintMessage(8, "GetTokenInformatino failed: 0x%x", v5);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    _DbgPrintMessage(8, "Can get the TOKEN_USER length: 0x%x", v5);
  }
  return v5;
}

```

## disassembly

```asm
0x1800178e0  mov     rax, rsp
0x1800178e3  mov     [rax+8], rbx
0x1800178e7  push    rdi
0x1800178e8  sub     rsp, 30h
0x1800178ec  mov     rbx, rdx
0x1800178ef  mov     dword ptr [rax+18h], 0
0x1800178f6  xor     r9d, r9d; TokenInformationLength
0x1800178f9  mov     dword ptr [rax+20h], 0
0x180017900  mov     rdi, rcx
0x180017903  lea     rax, [rax+18h]
0x180017907  xor     r8d, r8d; TokenInformation
0x18001790a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001790f  mov     rcx, rbx; TokenHandle
0x180017912  lea     edx, [r9+1]; TokenInformationClass
0x180017916  call    cs:__imp_GetTokenInformation
0x18001791c  test    eax, eax
0x18001791e  jnz     loc_1800179FF
0x180017924  call    cs:__imp_GetLastError
0x18001792a  cmp     eax, 7Ah ; 'z'
0x18001792d  jnz     loc_1800179E1
0x180017933  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180017937  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001793e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017943  mov     [rdi+648h], rax
0x18001794a  test    rax, rax
0x18001794d  jnz     short loc_180017959
0x18001794f  mov     ebx, 8007000Eh
0x180017954  jmp     loc_180017A15
0x180017959  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18001795e  lea     rcx, [rsp+38h+arg_18]
0x180017963  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180017968  mov     r8, rax; TokenInformation
0x18001796b  mov     rcx, rbx; TokenHandle
0x18001796e  mov     edx, 1; TokenInformationClass
0x180017973  call    cs:__imp_GetTokenInformation
0x180017979  test    eax, eax
0x18001797b  jnz     short loc_1800179A8
0x18001797d  call    cs:__imp_GetLastError
0x180017983  mov     ebx, eax
0x180017985  test    eax, eax
0x180017987  jle     short loc_180017992
0x180017989  movzx   ebx, ax
0x18001798c  or      ebx, 80070000h
0x180017992  lea     rdx, aGettokeninform_0; "GetTokenInformatino failed: 0x%x"
0x180017999  mov     r8d, ebx
0x18001799c  mov     ecx, 8; int
0x1800179a1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800179a6  jmp     short loc_180017A15
0x1800179a8  mov     rdx, rbx; void *
0x1800179ab  mov     rcx, rdi; this
0x1800179ae  call    ?ResolveUserName@CUserName@@AEAAJPEAX@Z; CUserName::ResolveUserName(void *)
0x1800179b3  mov     ebx, eax
0x1800179b5  test    eax, eax
0x1800179b7  jns     short loc_1800179D6
0x1800179b9  lea     r9, aCusernameIniti; "CUserName::InitializeUserName"
0x1800179c0  mov     r8d, eax
0x1800179c3  lea     rdx, aResolveusernam; "ResolveUserName failed: 0x%x in %s"
0x1800179ca  mov     ecx, 8; int
0x1800179cf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800179d4  jmp     short loc_180017A15
0x1800179d6  or      dword ptr [rdi+640h], 2
0x1800179dd  xor     ebx, ebx
0x1800179df  jmp     short loc_180017A15
0x1800179e1  call    cs:__imp_GetLastError
0x1800179e7  mov     ebx, eax
0x1800179e9  test    eax, eax
0x1800179eb  jle     short loc_1800179F6
0x1800179ed  movzx   ebx, ax
0x1800179f0  or      ebx, 80070000h
0x1800179f6  lea     rdx, aCanGetTheToken_0; "Can get the TOKEN_USER length: 0x%x"
0x1800179fd  jmp     short loc_180017999
0x1800179ff  lea     rdx, aCanGetTheToken; "Can get the TOKEN_USER length"
0x180017a06  mov     ecx, 8; int
0x180017a0b  mov     ebx, 80070057h
0x180017a10  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017a15  mov     eax, ebx
0x180017a17  mov     rbx, [rsp+38h+arg_0]
0x180017a1c  add     rsp, 30h
0x180017a20  pop     rdi
0x180017a21  retn
```
