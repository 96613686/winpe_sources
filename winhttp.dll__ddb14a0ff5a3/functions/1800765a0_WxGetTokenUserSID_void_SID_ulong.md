# WxGetTokenUserSID(void *,_SID *,ulong)

- ea: `0x1800765a0`
- end: `0x1800766c4`
- name: `?WxGetTokenUserSID@@YAJPEAXPEAU_SID@@K@Z`
- size: `292`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pDestinationSid, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800760f0`

## callees

- `0x1800765a0`
- `0x1800a1d10`
- `0x1800a2660`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180076613`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180076613`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007662a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007662a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007667d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007667d`

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
      return -2147024809;
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
0x1800765a0  mov     [rsp+arg_10], rbx
0x1800765a5  push    rdi
0x1800765a6  sub     rsp, 0B0h
0x1800765ad  mov     rax, cs:__security_cookie
0x1800765b4  xor     rax, rsp
0x1800765b7  mov     [rsp+0B8h+var_18], rax
0x1800765bf  mov     rbx, rdx
0x1800765c2  mov     [rsp+0B8h+var_84], 0
0x1800765ca  xor     edx, edx; Val
0x1800765cc  mov     rdi, rcx
0x1800765cf  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x1800765d4  lea     r8d, [rdx+58h]; Size
0x1800765d8  call    memset_0
0x1800765dd  mov     [rsp+0B8h+var_88], 0
0x1800765e5  test    rdi, rdi
0x1800765e8  jz      loc_1800766A3
0x1800765ee  test    rbx, rbx
0x1800765f1  jz      loc_1800766B2
0x1800765f7  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800765fd  lea     rax, [rsp+0B8h+var_88]
0x180076602  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180076607  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18007660c  mov     rcx, rdi; TokenHandle
0x18007660f  lea     edx, [r9-57h]; TokenInformationClass
0x180076613  call    cs:__imp_GetTokenInformation
0x180076619  test    eax, eax
0x18007661b  jz      short loc_180076657
0x18007661d  mov     r8, [rsp+0B8h+TokenInformation]; pSourceSid
0x180076622  mov     rdx, rbx; pDestinationSid
0x180076625  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18007662a  call    cs:__imp_CopySid
0x180076630  test    eax, eax
0x180076632  jz      short loc_18007667D
0x180076634  xor     eax, eax
0x180076636  mov     rcx, [rsp+0B8h+var_18]
0x18007663e  xor     rcx, rsp; StackCookie
0x180076641  call    __security_check_cookie
0x180076646  mov     rbx, [rsp+0B8h+arg_10]
0x18007664e  add     rsp, 0B0h
0x180076655  pop     rdi
0x180076656  retn
0x180076657  call    cs:__imp_GetLastError
0x18007665d  test    eax, eax
0x18007665f  jle     short loc_180076669
0x180076661  movzx   eax, ax
0x180076664  or      eax, 80070000h
0x180076669  test    eax, eax
0x18007666b  mov     [rsp+0B8h+var_84], 1Fh
0x180076673  mov     ecx, 8000FFFFh
0x180076678  cmovns  eax, ecx
0x18007667b  jmp     short loc_180076636
0x18007667d  call    cs:__imp_GetLastError
0x180076683  test    eax, eax
0x180076685  jle     short loc_18007668F
0x180076687  movzx   eax, ax
0x18007668a  or      eax, 80070000h
0x18007668f  test    eax, eax
0x180076691  mov     [rsp+0B8h+var_84], 20h ; ' '
0x180076699  mov     ecx, 8000FFFFh
0x18007669e  cmovns  eax, ecx
0x1800766a1  jmp     short loc_180076636
0x1800766a3  mov     eax, 80070057h
0x1800766a8  mov     [rsp+0B8h+var_84], 1Bh
0x1800766b0  jmp     short loc_180076636
0x1800766b2  mov     eax, 80070057h
0x1800766b7  mov     [rsp+0B8h+var_84], 1Ch
0x1800766bf  jmp     loc_180076636
```
