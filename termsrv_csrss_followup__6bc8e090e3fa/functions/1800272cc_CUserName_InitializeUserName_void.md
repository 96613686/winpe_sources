# CUserName::InitializeUserName(void *)

- ea: `0x1800272cc`
- end: `0x18002742d`
- name: `?InitializeUserName@CUserName@@AEAAJPEAX@Z`
- size: `353`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800159d0`
- `0x1800beb40`
- `0x1800beee0`
- `0x1800befa4`
- `0x1800bf4b0`

## callees

- `0x180009940`
- `0x1800272cc`
- `0x18002aa3c`
- `0x18003444c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002737b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002737b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273e5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027302`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002736b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027302`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002736b`

## string_xrefs

- `0x180027409`: `Can get the TOKEN_USER length`
- `0x180027400`: `Can get the TOKEN_USER length: 0x%x`
- `0x180027396`: `GetTokenInformatino failed: 0x%x`

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
0x1800272cc  mov     rax, rsp
0x1800272cf  mov     [rax+8], rbx
0x1800272d3  push    rdi
0x1800272d4  sub     rsp, 30h
0x1800272d8  mov     rbx, rdx
0x1800272db  mov     dword ptr [rax+18h], 0
0x1800272e2  xor     r9d, r9d; TokenInformationLength
0x1800272e5  mov     dword ptr [rax+20h], 0
0x1800272ec  mov     rdi, rcx
0x1800272ef  lea     rax, [rax+18h]
0x1800272f3  xor     r8d, r8d; TokenInformation
0x1800272f6  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800272fb  mov     rcx, rbx; TokenHandle
0x1800272fe  lea     edx, [r9+1]; TokenInformationClass
0x180027302  call    cs:__imp_GetTokenInformation
0x180027309  nop     dword ptr [rax+rax+00h]
0x18002730e  test    eax, eax
0x180027310  jnz     loc_180027409
0x180027316  call    cs:__imp_GetLastError
0x18002731d  nop     dword ptr [rax+rax+00h]
0x180027322  cmp     eax, 7Ah ; 'z'
0x180027325  jnz     loc_1800273E5
0x18002732b  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18002732f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027336  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002733b  mov     [rdi+648h], rax
0x180027342  test    rax, rax
0x180027345  jnz     short loc_180027351
0x180027347  mov     ebx, 8007000Eh
0x18002734c  jmp     loc_18002741F
0x180027351  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180027356  lea     rcx, [rsp+38h+arg_18]
0x18002735b  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180027360  mov     r8, rax; TokenInformation
0x180027363  mov     rcx, rbx; TokenHandle
0x180027366  mov     edx, 1; TokenInformationClass
0x18002736b  call    cs:__imp_GetTokenInformation
0x180027372  nop     dword ptr [rax+rax+00h]
0x180027377  test    eax, eax
0x180027379  jnz     short loc_1800273AC
0x18002737b  call    cs:__imp_GetLastError
0x180027382  nop     dword ptr [rax+rax+00h]
0x180027387  mov     ebx, eax
0x180027389  test    eax, eax
0x18002738b  jle     short loc_180027396
0x18002738d  movzx   ebx, ax
0x180027390  or      ebx, 80070000h
0x180027396  lea     rdx, aGettokeninform_0; "GetTokenInformatino failed: 0x%x"
0x18002739d  mov     r8d, ebx
0x1800273a0  mov     ecx, 8; int
0x1800273a5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800273aa  jmp     short loc_18002741F
0x1800273ac  mov     rdx, rbx; void *
0x1800273af  mov     rcx, rdi; this
0x1800273b2  call    ?ResolveUserName@CUserName@@AEAAJPEAX@Z; CUserName::ResolveUserName(void *)
0x1800273b7  mov     ebx, eax
0x1800273b9  test    eax, eax
0x1800273bb  jns     short loc_1800273DA
0x1800273bd  lea     r9, aCusernameIniti; "CUserName::InitializeUserName"
0x1800273c4  mov     r8d, eax
0x1800273c7  lea     rdx, aResolveusernam; "ResolveUserName failed: 0x%x in %s"
0x1800273ce  mov     ecx, 8; int
0x1800273d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800273d8  jmp     short loc_18002741F
0x1800273da  or      dword ptr [rdi+640h], 2
0x1800273e1  xor     ebx, ebx
0x1800273e3  jmp     short loc_18002741F
0x1800273e5  call    cs:__imp_GetLastError
0x1800273ec  nop     dword ptr [rax+rax+00h]
0x1800273f1  mov     ebx, eax
0x1800273f3  test    eax, eax
0x1800273f5  jle     short loc_180027400
0x1800273f7  movzx   ebx, ax
0x1800273fa  or      ebx, 80070000h
0x180027400  lea     rdx, aCanGetTheToken_0; "Can get the TOKEN_USER length: 0x%x"
0x180027407  jmp     short loc_18002739D
0x180027409  lea     rdx, aCanGetTheToken; "Can get the TOKEN_USER length"
0x180027410  mov     ecx, 8; int
0x180027415  mov     ebx, 80070057h
0x18002741a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002741f  mov     eax, ebx
0x180027421  mov     rbx, [rsp+38h+arg_0]
0x180027426  add     rsp, 30h
0x18002742a  pop     rdi
0x18002742b  retn
```
