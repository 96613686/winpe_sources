# WxGetTokenUserSID(void *,_SID *,ulong)

- ea: `0x18005c81c`
- end: `0x18005c93b`
- name: `?WxGetTokenUserSID@@YAJPEAXPEAU_SID@@K@Z`
- size: `287`
- prototype: `signed int __fastcall(HANDLE TokenHandle, PSID pDestinationSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008cc70`

## callees

- `0x18005c81c`
- `0x180080fb0`
- `0x180081b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c8f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c8f2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005c8e8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005c8e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c8ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c8ab`

## pseudocode

```c
signed int __fastcall WxGetTokenUserSID(HANDLE TokenHandle, PSID pDestinationSid)
{
  signed int result; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-88h] BYREF
  int v6; // [rsp+34h] [rbp-84h]
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  v6 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  if ( TokenHandle )
  {
    if ( pDestinationSid )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
      {
        if ( CopySid(0x44u, pDestinationSid, TokenInformation[0]) )
        {
          return 0;
        }
        else
        {
          result = GetLastError();
          if ( result > 0 )
            result = (unsigned __int16)result | 0x80070000;
          v6 = 32;
          if ( result >= 0 )
            return -2147418113;
        }
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        v6 = 31;
        if ( result >= 0 )
          return -2147418113;
      }
    }
    else
    {
      result = -2147024809;
      v6 = 28;
    }
  }
  else
  {
    result = -2147024809;
    v6 = 27;
  }
  return result;
}

```

## disassembly

```asm
0x18005c81c  mov     [rsp+arg_10], rbx
0x18005c821  push    rdi
0x18005c822  sub     rsp, 0B0h
0x18005c829  mov     rax, cs:__security_cookie
0x18005c830  xor     rax, rsp
0x18005c833  mov     [rsp+0B8h+var_18], rax
0x18005c83b  mov     rbx, rdx
0x18005c83e  mov     [rsp+0B8h+var_84], 0
0x18005c846  xor     edx, edx; Val
0x18005c848  mov     rdi, rcx
0x18005c84b  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x18005c850  lea     r8d, [rdx+58h]; Size
0x18005c854  call    memset_0
0x18005c859  mov     [rsp+0B8h+var_88], 0
0x18005c861  test    rdi, rdi
0x18005c864  jnz     short loc_18005C878
0x18005c866  mov     eax, 80070057h
0x18005c86b  mov     [rsp+0B8h+var_84], 1Bh
0x18005c873  jmp     loc_18005C91A
0x18005c878  test    rbx, rbx
0x18005c87b  jnz     short loc_18005C88F
0x18005c87d  mov     eax, 80070057h
0x18005c882  mov     [rsp+0B8h+var_84], 1Ch
0x18005c88a  jmp     loc_18005C91A
0x18005c88f  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18005c895  lea     rax, [rsp+0B8h+var_88]
0x18005c89a  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18005c89f  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18005c8a4  mov     rcx, rdi; TokenHandle
0x18005c8a7  lea     edx, [r9-57h]; TokenInformationClass
0x18005c8ab  call    cs:__imp_GetTokenInformation
0x18005c8b1  test    eax, eax
0x18005c8b3  jnz     short loc_18005C8DB
0x18005c8b5  call    cs:__imp_GetLastError
0x18005c8bb  test    eax, eax
0x18005c8bd  jle     short loc_18005C8C7
0x18005c8bf  movzx   eax, ax
0x18005c8c2  or      eax, 80070000h
0x18005c8c7  test    eax, eax
0x18005c8c9  mov     [rsp+0B8h+var_84], 1Fh
0x18005c8d1  mov     ecx, 8000FFFFh
0x18005c8d6  cmovns  eax, ecx
0x18005c8d9  jmp     short loc_18005C91A
0x18005c8db  mov     r8, [rsp+0B8h+TokenInformation]; pSourceSid
0x18005c8e0  mov     rdx, rbx; pDestinationSid
0x18005c8e3  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18005c8e8  call    cs:__imp_CopySid
0x18005c8ee  test    eax, eax
0x18005c8f0  jnz     short loc_18005C918
0x18005c8f2  call    cs:__imp_GetLastError
0x18005c8f8  test    eax, eax
0x18005c8fa  jle     short loc_18005C904
0x18005c8fc  movzx   eax, ax
0x18005c8ff  or      eax, 80070000h
0x18005c904  test    eax, eax
0x18005c906  mov     [rsp+0B8h+var_84], 20h ; ' '
0x18005c90e  mov     ecx, 8000FFFFh
0x18005c913  cmovns  eax, ecx
0x18005c916  jmp     short loc_18005C91A
0x18005c918  xor     eax, eax
0x18005c91a  mov     rcx, [rsp+0B8h+var_18]
0x18005c922  xor     rcx, rsp; StackCookie
0x18005c925  call    __security_check_cookie
0x18005c92a  mov     rbx, [rsp+0B8h+arg_10]
0x18005c932  add     rsp, 0B0h
0x18005c939  pop     rdi
0x18005c93a  retn
```
