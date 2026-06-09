# CUserName::InitializeUserName(void *)

- ea: `0x180025ddc`
- end: `0x180025f1e`
- name: `?InitializeUserName@CUserName@@AEAAJPEAX@Z`
- size: `322`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014f40`
- `0x1800b82d0`
- `0x1800b8620`
- `0x1800b86dc`
- `0x1800b8bb0`

## callees

- `0x18000a210`
- `0x180025ddc`
- `0x18002943c`
- `0x1800326dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025edd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025e12`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025e6f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025e12`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025e6f`

## string_xrefs

- `0x180025efb`: `Can get the TOKEN_USER length`
- `0x180025ef2`: `Can get the TOKEN_USER length: 0x%x`
- `0x180025e8e`: `GetTokenInformatino failed: 0x%x`

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
0x180025ddc  mov     rax, rsp
0x180025ddf  mov     [rax+8], rbx
0x180025de3  push    rdi
0x180025de4  sub     rsp, 30h
0x180025de8  mov     rbx, rdx
0x180025deb  mov     dword ptr [rax+18h], 0
0x180025df2  xor     r9d, r9d; TokenInformationLength
0x180025df5  mov     dword ptr [rax+20h], 0
0x180025dfc  mov     rdi, rcx
0x180025dff  lea     rax, [rax+18h]
0x180025e03  xor     r8d, r8d; TokenInformation
0x180025e06  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180025e0b  mov     rcx, rbx; TokenHandle
0x180025e0e  lea     edx, [r9+1]; TokenInformationClass
0x180025e12  call    cs:__imp_GetTokenInformation
0x180025e18  test    eax, eax
0x180025e1a  jnz     loc_180025EFB
0x180025e20  call    cs:__imp_GetLastError
0x180025e26  cmp     eax, 7Ah ; 'z'
0x180025e29  jnz     loc_180025EDD
0x180025e2f  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180025e33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025e3a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025e3f  mov     [rdi+648h], rax
0x180025e46  test    rax, rax
0x180025e49  jnz     short loc_180025E55
0x180025e4b  mov     ebx, 8007000Eh
0x180025e50  jmp     loc_180025F11
0x180025e55  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180025e5a  lea     rcx, [rsp+38h+arg_18]
0x180025e5f  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180025e64  mov     r8, rax; TokenInformation
0x180025e67  mov     rcx, rbx; TokenHandle
0x180025e6a  mov     edx, 1; TokenInformationClass
0x180025e6f  call    cs:__imp_GetTokenInformation
0x180025e75  test    eax, eax
0x180025e77  jnz     short loc_180025EA4
0x180025e79  call    cs:__imp_GetLastError
0x180025e7f  mov     ebx, eax
0x180025e81  test    eax, eax
0x180025e83  jle     short loc_180025E8E
0x180025e85  movzx   ebx, ax
0x180025e88  or      ebx, 80070000h
0x180025e8e  lea     rdx, aGettokeninform_0; "GetTokenInformatino failed: 0x%x"
0x180025e95  mov     r8d, ebx
0x180025e98  mov     ecx, 8; int
0x180025e9d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180025ea2  jmp     short loc_180025F11
0x180025ea4  mov     rdx, rbx; void *
0x180025ea7  mov     rcx, rdi; this
0x180025eaa  call    ?ResolveUserName@CUserName@@AEAAJPEAX@Z; CUserName::ResolveUserName(void *)
0x180025eaf  mov     ebx, eax
0x180025eb1  test    eax, eax
0x180025eb3  jns     short loc_180025ED2
0x180025eb5  lea     r9, aCusernameIniti; "CUserName::InitializeUserName"
0x180025ebc  mov     r8d, eax
0x180025ebf  lea     rdx, aResolveusernam; "ResolveUserName failed: 0x%x in %s"
0x180025ec6  mov     ecx, 8; int
0x180025ecb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180025ed0  jmp     short loc_180025F11
0x180025ed2  or      dword ptr [rdi+640h], 2
0x180025ed9  xor     ebx, ebx
0x180025edb  jmp     short loc_180025F11
0x180025edd  call    cs:__imp_GetLastError
0x180025ee3  mov     ebx, eax
0x180025ee5  test    eax, eax
0x180025ee7  jle     short loc_180025EF2
0x180025ee9  movzx   ebx, ax
0x180025eec  or      ebx, 80070000h
0x180025ef2  lea     rdx, aCanGetTheToken_0; "Can get the TOKEN_USER length: 0x%x"
0x180025ef9  jmp     short loc_180025E95
0x180025efb  lea     rdx, aCanGetTheToken; "Can get the TOKEN_USER length"
0x180025f02  mov     ecx, 8; int
0x180025f07  mov     ebx, 80070057h
0x180025f0c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180025f11  mov     eax, ebx
0x180025f13  mov     rbx, [rsp+38h+arg_0]
0x180025f18  add     rsp, 30h
0x180025f1c  pop     rdi
0x180025f1d  retn
```
