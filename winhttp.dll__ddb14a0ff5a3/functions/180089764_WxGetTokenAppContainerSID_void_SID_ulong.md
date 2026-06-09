# WxGetTokenAppContainerSID(void *,_SID *,ulong)

- ea: `0x180089764`
- end: `0x180089844`
- name: `?WxGetTokenAppContainerSID@@YAJPEAXPEAU_SID@@K@Z`
- size: `224`
- prototype: `int(void *, struct _SID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800760f0`

## callees

- `0x180089764`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800897a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800897a8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180089801`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180089801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800897b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008980f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800897b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008980f`

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
0x180089764  push    rbx
0x180089766  sub     rsp, 0A0h
0x18008976d  mov     rax, cs:__security_cookie
0x180089774  xor     rax, rsp
0x180089777  mov     [rsp+0A8h+var_18], rax
0x18008977f  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x180089785  mov     [rsp+0A8h+var_74], 0
0x18008978d  mov     rbx, rdx
0x180089790  mov     [rsp+0A8h+var_78], r9d
0x180089795  lea     rax, [rsp+0A8h+var_78]
0x18008979a  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x18008979f  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x1800897a4  lea     edx, [r9-2Dh]; TokenInformationClass
0x1800897a8  call    cs:__imp_GetTokenInformation
0x1800897ae  test    eax, eax
0x1800897b0  jnz     short loc_1800897EF
0x1800897b2  call    cs:__imp_GetLastError
0x1800897b8  test    eax, eax
0x1800897ba  jle     short loc_1800897C4
0x1800897bc  movzx   eax, ax
0x1800897bf  or      eax, 80070000h
0x1800897c4  test    eax, eax
0x1800897c6  mov     [rsp+0A8h+var_74], 0E0h
0x1800897ce  mov     ecx, 8000FFFFh
0x1800897d3  cmovns  eax, ecx
0x1800897d6  mov     rcx, [rsp+0A8h+var_18]
0x1800897de  xor     rcx, rsp; StackCookie
0x1800897e1  call    __security_check_cookie
0x1800897e6  add     rsp, 0A0h
0x1800897ed  pop     rbx
0x1800897ee  retn
0x1800897ef  mov     r8, [rsp+0A8h+TokenInformation]; pSourceSid
0x1800897f4  test    r8, r8
0x1800897f7  jz      short loc_180089835
0x1800897f9  mov     rdx, rbx; pDestinationSid
0x1800897fc  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180089801  call    cs:__imp_CopySid
0x180089807  test    eax, eax
0x180089809  jz      short loc_18008980F
0x18008980b  xor     eax, eax
0x18008980d  jmp     short loc_1800897D6
0x18008980f  call    cs:__imp_GetLastError
0x180089815  test    eax, eax
0x180089817  jle     short loc_180089821
0x180089819  movzx   eax, ax
0x18008981c  or      eax, 80070000h
0x180089821  test    eax, eax
0x180089823  mov     [rsp+0A8h+var_74], 0E4h
0x18008982b  mov     ecx, 8000FFFFh
0x180089830  cmovns  eax, ecx
0x180089833  jmp     short loc_1800897D6
0x180089835  mov     eax, 8000FFFFh
0x18008983a  mov     [rsp+0A8h+var_74], 0E2h
0x180089842  jmp     short loc_1800897D6
```
