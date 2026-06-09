# WxGetTokenIntegrityLevel(void *,ulong *)

- ea: `0x18004efc0`
- end: `0x18004f0b7`
- name: `?WxGetTokenIntegrityLevel@@YAJPEAXPEAK@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008cc70`

## callees

- `0x18004efc0`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f08f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f08f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004f036`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004f036`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18004f04f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18004f04f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004f062`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004f062`

## pseudocode

```c
signed int __fastcall WxGetTokenIntegrityLevel(void *a1, unsigned int *a2)
{
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v4; // ecx
  signed int result; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-98h] BYREF
  int v7; // [rsp+34h] [rbp-94h]
  _OWORD TokenInformation[7]; // [rsp+40h] [rbp-88h] BYREF

  *a2 = 4096;
  memset(TokenInformation, 0, 108);
  v7 = 0;
  ReturnLength = 108;
  if ( GetTokenInformation(a1, TokenIntegrityLevel, TokenInformation, 0x6Cu, &ReturnLength) )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(*(PSID *)&TokenInformation[0]);
    v4 = *GetSidSubAuthority(*(PSID *)&TokenInformation[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
    result = 0;
    *a2 = v4;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    v7 = 307;
    if ( result >= 0 )
      return -2147418113;
  }
  return result;
}

```

## disassembly

```asm
0x18004efc0  mov     r11, rsp
0x18004efc3  push    rbx
0x18004efc4  sub     rsp, 0C0h
0x18004efcb  mov     rax, cs:__security_cookie
0x18004efd2  xor     rax, rsp
0x18004efd5  mov     [rsp+0C8h+var_18], rax
0x18004efdd  xorps   xmm0, xmm0
0x18004efe0  mov     dword ptr [rdx], 1000h
0x18004efe6  movups  [rsp+0C8h+TokenInformation], xmm0
0x18004efeb  mov     rbx, rdx
0x18004efee  lea     rax, [rsp+0C8h+var_98]
0x18004eff3  movups  [rsp+0C8h+var_78], xmm0
0x18004eff8  mov     r9d, 6Ch ; 'l'; TokenInformationLength
0x18004effe  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x18004f003  movups  [rsp+0C8h+var_68], xmm0
0x18004f008  mov     edx, 19h; TokenInformationClass
0x18004f00d  mov     [rsp+0C8h+var_94], 0
0x18004f015  movups  [rsp+0C8h+var_58], xmm0
0x18004f01a  mov     [rsp+0C8h+var_98], 6Ch ; 'l'
0x18004f022  movups  xmmword ptr [r11-38h], xmm0
0x18004f027  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x18004f02c  movups  xmmword ptr [r11-2Ch], xmm0
0x18004f031  movups  xmmword ptr [r11-48h], xmm0
0x18004f036  call    cs:__imp_GetTokenInformation
0x18004f03c  test    eax, eax
0x18004f03e  jz      short loc_18004F08F
0x18004f040  mov     rcx, qword ptr [rsp+0C8h+TokenInformation]; pSid
0x18004f045  mov     [rsp+0C8h+arg_10], rdi
0x18004f04d  xor     edi, edi
0x18004f04f  call    cs:__imp_GetSidSubAuthorityCount
0x18004f055  movzx   ecx, byte ptr [rax]
0x18004f058  dec     cl
0x18004f05a  movzx   edx, cl; nSubAuthority
0x18004f05d  mov     rcx, qword ptr [rsp+0C8h+TokenInformation]; pSid
0x18004f062  call    cs:__imp_GetSidSubAuthority
0x18004f068  mov     ecx, [rax]
0x18004f06a  mov     eax, edi
0x18004f06c  mov     rdi, [rsp+0C8h+arg_10]
0x18004f074  mov     [rbx], ecx
0x18004f076  mov     rcx, [rsp+0C8h+var_18]
0x18004f07e  xor     rcx, rsp; StackCookie
0x18004f081  call    __security_check_cookie
0x18004f086  add     rsp, 0C0h
0x18004f08d  pop     rbx
0x18004f08e  retn
0x18004f08f  call    cs:__imp_GetLastError
0x18004f095  test    eax, eax
0x18004f097  jg      short loc_18004F0AD
0x18004f099  test    eax, eax
0x18004f09b  mov     [rsp+0C8h+var_94], 133h
0x18004f0a3  mov     ecx, 8000FFFFh
0x18004f0a8  cmovns  eax, ecx
0x18004f0ab  jmp     short loc_18004F076
0x18004f0ad  movzx   eax, ax
0x18004f0b0  or      eax, 80070000h
0x18004f0b5  jmp     short loc_18004F099
```
