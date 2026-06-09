# WxGetTokenAppContainerSID(void *,_SID *,ulong)

- ea: `0x18004ffe0`
- end: `0x1800500c8`
- name: `?WxGetTokenAppContainerSID@@YAJPEAXPEAU_SID@@K@Z`
- size: `232`
- prototype: `int(void *, struct _SID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008cc70`

## callees

- `0x18004ffe0`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050087`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180050044`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180050044`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050028`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050028`

## pseudocode

```c
int __fastcall WxGetTokenAppContainerSID(void *a1, struct _SID *a2)
{
  int result; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-78h] BYREF
  int v5; // [rsp+34h] [rbp-74h]
  PSID TokenInformation[10]; // [rsp+40h] [rbp-68h] BYREF

  v5 = 0;
  ReturnLength = 76;
  if ( GetTokenInformation(a1, TokenAppContainerSid, TokenInformation, 0x4Cu, &ReturnLength) )
  {
    if ( TokenInformation[0] )
    {
      if ( CopySid(0x44u, a2, TokenInformation[0]) )
      {
        return 0;
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        v5 = 228;
        if ( result >= 0 )
          return -2147418113;
      }
    }
    else
    {
      return -2147418113;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    v5 = 224;
    if ( result >= 0 )
      return -2147418113;
  }
  return result;
}

```

## disassembly

```asm
0x18004ffe0  push    rbx
0x18004ffe2  sub     rsp, 0A0h
0x18004ffe9  mov     rax, cs:__security_cookie
0x18004fff0  xor     rax, rsp
0x18004fff3  mov     [rsp+0A8h+var_18], rax
0x18004fffb  mov     rbx, rdx
0x18004fffe  mov     [rsp+0A8h+var_74], 0
0x180050006  lea     rax, [rsp+0A8h+var_78]
0x18005000b  mov     [rsp+0A8h+var_78], 4Ch ; 'L'
0x180050013  mov     edx, 1Fh; TokenInformationClass
0x180050018  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x18005001d  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x180050023  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x180050028  call    cs:__imp_GetTokenInformation
0x18005002e  test    eax, eax
0x180050030  jz      short loc_180050069
0x180050032  mov     r8, [rsp+0A8h+TokenInformation]; pSourceSid
0x180050037  test    r8, r8
0x18005003a  jz      short loc_1800500AF
0x18005003c  mov     rdx, rbx; pDestinationSid
0x18005003f  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180050044  call    cs:__imp_CopySid
0x18005004a  test    eax, eax
0x18005004c  jz      short loc_180050087
0x18005004e  xor     eax, eax
0x180050050  mov     rcx, [rsp+0A8h+var_18]
0x180050058  xor     rcx, rsp; StackCookie
0x18005005b  call    __security_check_cookie
0x180050060  add     rsp, 0A0h
0x180050067  pop     rbx
0x180050068  retn
0x180050069  call    cs:__imp_GetLastError
0x18005006f  test    eax, eax
0x180050071  jg      short loc_1800500A5
0x180050073  test    eax, eax
0x180050075  mov     [rsp+0A8h+var_74], 0E0h
0x18005007d  mov     ecx, 8000FFFFh
0x180050082  cmovns  eax, ecx
0x180050085  jmp     short loc_180050050
0x180050087  call    cs:__imp_GetLastError
0x18005008d  test    eax, eax
0x18005008f  jg      short loc_1800500BE
0x180050091  test    eax, eax
0x180050093  mov     [rsp+0A8h+var_74], 0E4h
0x18005009b  mov     ecx, 8000FFFFh
0x1800500a0  cmovns  eax, ecx
0x1800500a3  jmp     short loc_180050050
0x1800500a5  movzx   eax, ax
0x1800500a8  or      eax, 80070000h
0x1800500ad  jmp     short loc_180050073
0x1800500af  mov     eax, 8000FFFFh
0x1800500b4  mov     [rsp+0A8h+var_74], 0E2h
0x1800500bc  jmp     short loc_180050050
0x1800500be  movzx   eax, ax
0x1800500c1  or      eax, 80070000h
0x1800500c6  jmp     short loc_180050091
```
