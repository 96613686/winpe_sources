# CUserProfile::GetFileSecurityW(ushort const *,void * *)

- ea: `0x18006e400`
- end: `0x18006e50d`
- name: `?GetFileSecurityW@CUserProfile@@CAJPEBGPEAPEAX@Z`
- size: `269`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006df3c`

## callees

- `0x180009940`
- `0x18003440c`
- `0x180034470`
- `0x18006e400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e4ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e4ba`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18006e432`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18006e4aa`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18006e432`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18006e4aa`

## string_xrefs

- `0x18006e44b`: `GetFileSecurity failed: 0x%x in %s`
- `0x18006e4e3`: `GetFileSecurity failed: 0x%x in %s`
- `0x18006e455`: `CUserProfile::GetFileSecurityW`
- `0x18006e4d9`: `CUserProfile::GetFileSecurityW`

## pseudocode

```c
__int64 __fastcall CUserProfile::GetFileSecurityW(LPCWSTR lpFileName, void **a2)
{
  signed int v4; // ebx
  void *v5; // rdi
  signed int LastError; // eax
  DWORD nLengthNeeded; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  nLengthNeeded = 0;
  GetFileSecurityW(lpFileName, 4u, 0, 0, &nLengthNeeded);
  if ( nLengthNeeded )
  {
    v5 = operator new[](nLengthNeeded, (const struct std::nothrow_t *)std::nothrow);
    if ( v5 )
    {
      v4 = 0;
      if ( GetFileSecurityW(lpFileName, 4u, v5, nLengthNeeded, &nLengthNeeded) )
        goto LABEL_11;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_11:
        *a2 = v5;
      }
      else
      {
        _DbgPrintMessage(8, "GetFileSecurity failed: 0x%x in %s", v4, "CUserProfile::GetFileSecurityW");
        operator delete(v5);
      }
    }
    else
    {
      v4 = -2147024882;
      _DbgPrintMessage(8, "memory allocation failed: 0x%x in %s", 2147942414LL, "CUserProfile::GetFileSecurityW");
    }
  }
  else
  {
    v4 = -2147467259;
    _DbgPrintMessage(8, "GetFileSecurity failed: 0x%x in %s", 2147500037LL, "CUserProfile::GetFileSecurityW");
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006e400  push    rbx
0x18006e402  push    rbp
0x18006e403  push    rsi
0x18006e404  push    rdi
0x18006e405  sub     rsp, 38h
0x18006e409  xor     r9d, r9d; nLength
0x18006e40c  mov     qword ptr [rdx], 0
0x18006e413  mov     rsi, rdx
0x18006e416  mov     [rsp+58h+nLengthNeeded], 0
0x18006e41e  lea     rax, [rsp+58h+nLengthNeeded]
0x18006e423  xor     r8d, r8d; pSecurityDescriptor
0x18006e426  mov     rbp, rcx
0x18006e429  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18006e42e  lea     edx, [r9+4]; RequestedInformation
0x18006e432  call    cs:__imp_GetFileSecurityW
0x18006e439  nop     dword ptr [rax+rax+00h]
0x18006e43e  mov     eax, [rsp+58h+nLengthNeeded]
0x18006e442  test    eax, eax
0x18006e444  jnz     short loc_18006E46B
0x18006e446  mov     ebx, 80004005h
0x18006e44b  lea     rdx, aGetfilesecurit; "GetFileSecurity failed: 0x%x in %s"
0x18006e452  mov     r8d, ebx
0x18006e455  lea     r9, aCuserprofileGe; "CUserProfile::GetFileSecurityW"
0x18006e45c  mov     ecx, 8; int
0x18006e461  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e466  jmp     loc_18006E501
0x18006e46b  mov     rcx, rax; unsigned __int64
0x18006e46e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006e475  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006e47a  mov     rdi, rax
0x18006e47d  test    rax, rax
0x18006e480  jnz     short loc_18006E490
0x18006e482  mov     ebx, 8007000Eh
0x18006e487  lea     rdx, aMemoryAllocati_0; "memory allocation failed: 0x%x in %s"
0x18006e48e  jmp     short loc_18006E452
0x18006e490  mov     r9d, [rsp+58h+nLengthNeeded]; nLength
0x18006e495  lea     rax, [rsp+58h+nLengthNeeded]
0x18006e49a  xor     ebx, ebx
0x18006e49c  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18006e4a1  mov     r8, rdi; pSecurityDescriptor
0x18006e4a4  mov     rcx, rbp; lpFileName
0x18006e4a7  lea     edx, [rbx+4]; RequestedInformation
0x18006e4aa  call    cs:__imp_GetFileSecurityW
0x18006e4b1  nop     dword ptr [rax+rax+00h]
0x18006e4b6  test    eax, eax
0x18006e4b8  jnz     short loc_18006E4FE
0x18006e4ba  call    cs:__imp_GetLastError
0x18006e4c1  nop     dword ptr [rax+rax+00h]
0x18006e4c6  mov     ebx, eax
0x18006e4c8  test    eax, eax
0x18006e4ca  jle     short loc_18006E4D5
0x18006e4cc  movzx   ebx, ax
0x18006e4cf  or      ebx, 80070000h
0x18006e4d5  test    ebx, ebx
0x18006e4d7  jns     short loc_18006E4FE
0x18006e4d9  lea     r9, aCuserprofileGe; "CUserProfile::GetFileSecurityW"
0x18006e4e0  mov     r8d, ebx
0x18006e4e3  lea     rdx, aGetfilesecurit; "GetFileSecurity failed: 0x%x in %s"
0x18006e4ea  mov     ecx, 8; int
0x18006e4ef  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e4f4  mov     rcx, rdi; Block
0x18006e4f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006e4fc  jmp     short loc_18006E501
0x18006e4fe  mov     [rsi], rdi
0x18006e501  mov     eax, ebx
0x18006e503  add     rsp, 38h
0x18006e507  pop     rdi
0x18006e508  pop     rsi
0x18006e509  pop     rbp
0x18006e50a  pop     rbx
0x18006e50b  retn
```
