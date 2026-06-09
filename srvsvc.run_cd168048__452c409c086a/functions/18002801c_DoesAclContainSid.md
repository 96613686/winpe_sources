# DoesAclContainSid

- ea: `0x18002801c`
- end: `0x1800280f1`
- name: `DoesAclContainSid`
- size: `213`
- prototype: `__int64 __fastcall(PACL pAcl, PSID pSid2)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000aa8c`

## callees

- `0x18001deb0`
- `0x18002801c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180028060`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180028060`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002807d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002807d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002809d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800280ba`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002809d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800280ba`

## pseudocode

```c
char __fastcall DoesAclContainSid(PACL pAcl, PSID pSid2, _DWORD *a3)
{
  unsigned __int16 i; // si
  _DWORD *v7; // rbx
  LPVOID pAce; // [rsp+20h] [rbp-48h] BYREF
  __int64 pAclInformation; // [rsp+28h] [rbp-40h] BYREF
  int v11; // [rsp+30h] [rbp-38h]

  pAce = 0;
  pAclInformation = 0;
  v11 = 0;
  if ( GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= (unsigned int)pAclInformation || !GetAce(pAcl, i, &pAce) )
        return 0;
      v7 = pAce;
      if ( *(_BYTE *)pAce )
      {
        if ( *(_BYTE *)pAce == 5 && EqualSid((char *)pAce + 44, pSid2) )
        {
          if ( a3 )
            *a3 = v7[1];
          return 1;
        }
      }
      else if ( EqualSid((char *)pAce + 8, pSid2) )
      {
        if ( a3 )
          *a3 = v7[1];
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002801c  push    rbx
0x18002801e  push    rbp
0x18002801f  push    rsi
0x180028020  push    rdi
0x180028021  push    r14
0x180028023  sub     rsp, 40h
0x180028027  mov     rax, cs:__security_cookie
0x18002802e  xor     rax, rsp
0x180028031  mov     [rsp+68h+var_30], rax
0x180028036  xor     eax, eax
0x180028038  mov     [rsp+68h+pAce], 0
0x180028041  mov     rdi, r8
0x180028044  mov     [rsp+68h+pAclInformation], rax
0x180028049  mov     rbp, rdx
0x18002804c  mov     [rsp+68h+var_38], eax
0x180028050  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x180028055  mov     r14, rcx
0x180028058  lea     r9d, [rax+2]; dwAclInformationClass
0x18002805c  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180028060  call    cs:__imp_GetAclInformation
0x180028066  test    eax, eax
0x180028068  jz      short loc_1800280D7
0x18002806a  xor     esi, esi
0x18002806c  movzx   edx, si; dwAceIndex
0x18002806f  cmp     edx, dword ptr [rsp+68h+pAclInformation]
0x180028073  jnb     short loc_1800280D7
0x180028075  lea     r8, [rsp+68h+pAce]; pAce
0x18002807a  mov     rcx, r14; pAcl
0x18002807d  call    cs:__imp_GetAce
0x180028083  test    eax, eax
0x180028085  jz      short loc_1800280D7
0x180028087  mov     rbx, [rsp+68h+pAce]
0x18002808c  mov     al, [rbx]
0x18002808e  test    al, al
0x180028090  jz      short loc_1800280B3
0x180028092  cmp     al, 5
0x180028094  jnz     short loc_1800280C4
0x180028096  lea     rcx, [rbx+2Ch]; pSid1
0x18002809a  mov     rdx, rbp; pSid2
0x18002809d  call    cs:__imp_EqualSid
0x1800280a3  test    eax, eax
0x1800280a5  jz      short loc_1800280C4
0x1800280a7  test    rdi, rdi
0x1800280aa  jz      short loc_1800280D3
0x1800280ac  mov     eax, [rbx+4]
0x1800280af  mov     [rdi], eax
0x1800280b1  jmp     short loc_1800280D3
0x1800280b3  lea     rcx, [rbx+8]; pSid1
0x1800280b7  mov     rdx, rbp; pSid2
0x1800280ba  call    cs:__imp_EqualSid
0x1800280c0  test    eax, eax
0x1800280c2  jnz     short loc_1800280C9
0x1800280c4  inc     si
0x1800280c7  jmp     short loc_18002806C
0x1800280c9  test    rdi, rdi
0x1800280cc  jz      short loc_1800280D3
0x1800280ce  mov     ecx, [rbx+4]
0x1800280d1  mov     [rdi], ecx
0x1800280d3  mov     al, 1
0x1800280d5  jmp     short loc_1800280D9
0x1800280d7  xor     al, al
0x1800280d9  mov     rcx, [rsp+68h+var_30]
0x1800280de  xor     rcx, rsp; StackCookie
0x1800280e1  call    __security_check_cookie
0x1800280e6  add     rsp, 40h
0x1800280ea  pop     r14
0x1800280ec  pop     rdi
0x1800280ed  pop     rsi
0x1800280ee  pop     rbp
0x1800280ef  pop     rbx
0x1800280f0  retn
```
