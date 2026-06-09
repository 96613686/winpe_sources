# LsaLookupClientIsWellKnownSid

- ea: `0x180020804`
- end: `0x1800208ba`
- name: `LsaLookupClientIsWellKnownSid`
- size: `182`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020624`

## callees

- `0x180020804`

## import_xrefs

- `ntdll!RtlEqualPrefixSid` at `0x18002083b`
- `ntdll!RtlEqualPrefixSid` at `0x18002083b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020888`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020888`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x180020864`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x180020864`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180020871`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180020871`

## pseudocode

```c
bool __fastcall LsaLookupClientIsWellKnownSid(PSID pSid)
{
  __int64 v1; // rbx
  void *v3; // rcx
  char v4; // bl
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  BOOL pfEqual; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  pfEqual = 0;
  while ( (unsigned int)v1 < 8 )
  {
    v3 = *(&WellKnownSidPrefixes + v1);
    if ( v3 && RtlEqualPrefixSid(v3, pSid) )
      return 1;
    v1 = (unsigned int)(v1 + 1);
  }
  v4 = 0;
  if ( AccountDomainSid )
  {
    if ( EqualDomainSid(AccountDomainSid, pSid, &pfEqual) )
    {
      SidSubAuthorityCount = GetSidSubAuthorityCount(pSid);
      if ( SidSubAuthorityCount )
      {
        if ( *SidSubAuthorityCount )
        {
          SidSubAuthority = GetSidSubAuthority(pSid, (unsigned int)*SidSubAuthorityCount - 1);
          if ( pfEqual )
          {
            if ( SidSubAuthority )
              return *SidSubAuthority < 0x3E8;
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180020804  mov     [rsp+arg_0], rbx
0x180020809  mov     [rsp+arg_10], rbp
0x18002080e  push    rdi
0x18002080f  sub     rsp, 20h
0x180020813  xor     ebx, ebx
0x180020815  mov     [rsp+28h+pfEqual], 0
0x18002081d  mov     rdi, rcx
0x180020820  lea     ebp, [rbx+1]
0x180020823  cmp     ebx, 8
0x180020826  jnb     short loc_18002084E
0x180020828  lea     rcx, WellKnownSidPrefixes
0x18002082f  mov     rcx, [rcx+rbx*8]; Sid1
0x180020833  test    rcx, rcx
0x180020836  jz      short loc_180020845
0x180020838  mov     rdx, rdi; Sid2
0x18002083b  call    cs:__imp_RtlEqualPrefixSid
0x180020841  test    al, al
0x180020843  jnz     short loc_180020849
0x180020845  add     ebx, ebp
0x180020847  jmp     short loc_180020823
0x180020849  setnz   bl
0x18002084c  jmp     short loc_1800208A8
0x18002084e  mov     rcx, cs:AccountDomainSid; pSid1
0x180020855  xor     bl, bl
0x180020857  test    rcx, rcx
0x18002085a  jz      short loc_1800208A8
0x18002085c  lea     r8, [rsp+28h+pfEqual]; pfEqual
0x180020861  mov     rdx, rdi; pSid2
0x180020864  call    cs:__imp_EqualDomainSid
0x18002086a  test    eax, eax
0x18002086c  jz      short loc_1800208A8
0x18002086e  mov     rcx, rdi; pSid
0x180020871  call    cs:__imp_GetSidSubAuthorityCount
0x180020877  test    rax, rax
0x18002087a  jz      short loc_1800208A8
0x18002087c  cmp     [rax], bl
0x18002087e  jbe     short loc_1800208A8
0x180020880  movzx   edx, byte ptr [rax]
0x180020883  mov     rcx, rdi; pSid
0x180020886  sub     edx, ebp; nSubAuthority
0x180020888  call    cs:__imp_GetSidSubAuthority
0x18002088e  cmp     [rsp+28h+pfEqual], 0
0x180020893  jz      short loc_1800208A8
0x180020895  test    rax, rax
0x180020898  jz      short loc_1800208A8
0x18002089a  xor     cl, cl
0x18002089c  cmp     dword ptr [rax], 3E8h
0x1800208a2  movzx   ebx, cl
0x1800208a5  cmovb   ebx, ebp
0x1800208a8  mov     rbp, [rsp+28h+arg_10]
0x1800208ad  mov     al, bl
0x1800208af  mov     rbx, [rsp+28h+arg_0]
0x1800208b4  add     rsp, 20h
0x1800208b8  pop     rdi
0x1800208b9  retn
```
