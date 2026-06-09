# TsCryptCheckSecurityDescriptorNeedsFixing(_SECURITY_DESCRIPTOR *,int *)

- ea: `0x18003ec18`
- end: `0x18003ed57`
- name: `?TsCryptCheckSecurityDescriptorNeedsFixing@@YAHPEAU_SECURITY_DESCRIPTOR@@PEAH@Z`
- size: `319`
- prototype: `__int64 __fastcall(struct _SECURITY_DESCRIPTOR *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f2e0`

## callees

- `0x18001a280`
- `0x18003ec18`
- `0x18003ee84`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003ecea`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003ecea`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003ed0b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003ed0b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003eccf`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003eccf`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003ecb6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003ecb6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18003ec72`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18003ec72`

## pseudocode

```c
__int64 __fastcall TsCryptCheckSecurityDescriptorNeedsFixing(struct _SECURITY_DESCRIPTOR *a1, int *a2)
{
  unsigned int v4; // edi
  __int16 v5; // bx
  struct _ACL *Dacl; // rsi
  DWORD i; // ebx
  WORD pControl[2]; // [rsp+20h] [rbp-59h] BYREF
  DWORD dwRevision; // [rsp+24h] [rbp-55h] BYREF
  DWORD cbSid; // [rsp+28h] [rbp-51h] BYREF
  LPVOID pAce; // [rsp+30h] [rbp-49h] BYREF
  __int64 pAclInformation; // [rsp+38h] [rbp-41h] BYREF
  int v14; // [rsp+40h] [rbp-39h]
  _BYTE pSid[80]; // [rsp+50h] [rbp-29h] BYREF

  cbSid = 68;
  *a2 = 0;
  pControl[0] = 0;
  dwRevision = 0;
  pAclInformation = 0;
  v14 = 0;
  v4 = 0;
  pAce = 0;
  if ( GetSecurityDescriptorControl(a1, pControl, &dwRevision) )
  {
    v5 = pControl[0] & 0x1000;
    Dacl = TsCryptGetDacl(a1);
    if ( !Dacl || v5 )
      return 1;
    if ( CreateWellKnownSid(WinWorldSid, 0, pSid, &cbSid)
      && GetAclInformation(Dacl, &pAclInformation, 0xCu, AclSizeInformation) )
    {
      for ( i = 0; i < (unsigned int)pAclInformation; ++i )
      {
        if ( !GetAce(Dacl, i, &pAce) )
          return v4;
        if ( (*((_BYTE *)pAce + 1) & 0x10) != 0
          && !*(_BYTE *)pAce
          && EqualSid(pSid, (char *)pAce + 8)
          && (*((_DWORD *)pAce + 1) & 0x90000001) != 0 )
        {
          *a2 = 1;
          return 1;
        }
      }
      return 1;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18003ec18  mov     [rsp-8+arg_10], rbx
0x18003ec1d  push    rbp
0x18003ec1e  push    rsi
0x18003ec1f  push    rdi
0x18003ec20  push    r14
0x18003ec22  push    r15
0x18003ec24  lea     rbp, [rsp-37h]
0x18003ec29  sub     rsp, 0B0h
0x18003ec30  mov     rax, cs:__security_cookie
0x18003ec37  xor     rax, rsp
0x18003ec3a  mov     [rbp+57h+var_30], rax
0x18003ec3e  xor     r15d, r15d
0x18003ec41  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18003ec48  xor     eax, eax
0x18003ec4a  mov     [rdx], r15d
0x18003ec4d  mov     r14, rdx
0x18003ec50  mov     [rbp+57h+pControl], r15w
0x18003ec55  lea     rdx, [rbp+57h+pControl]; pControl
0x18003ec59  mov     [rbp+57h+dwRevision], r15d
0x18003ec5d  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18003ec61  mov     [rbp+57h+pAclInformation], rax
0x18003ec65  mov     rsi, rcx
0x18003ec68  mov     [rbp+57h+var_90], eax
0x18003ec6b  mov     edi, r15d
0x18003ec6e  mov     [rbp+57h+pAce], r15
0x18003ec72  call    cs:__imp_GetSecurityDescriptorControl
0x18003ec78  test    eax, eax
0x18003ec7a  jz      loc_18003ED32
0x18003ec80  movzx   ebx, [rbp+57h+pControl]
0x18003ec84  mov     eax, 1000h
0x18003ec89  mov     rcx, rsi; struct _SECURITY_DESCRIPTOR *
0x18003ec8c  and     bx, ax
0x18003ec8f  call    ?TsCryptGetDacl@@YAPEAU_ACL@@PEAU_SECURITY_DESCRIPTOR@@@Z; TsCryptGetDacl(_SECURITY_DESCRIPTOR *)
0x18003ec94  mov     rsi, rax
0x18003ec97  test    rax, rax
0x18003ec9a  jz      loc_18003ED2D
0x18003eca0  test    bx, bx
0x18003eca3  jnz     loc_18003ED2D
0x18003eca9  xor     edx, edx; DomainSid
0x18003ecab  lea     r9, [rbp+57h+cbSid]; cbSid
0x18003ecaf  lea     r8, [rbp+57h+pSid]; pSid
0x18003ecb3  lea     ecx, [rdx+1]; WellKnownSidType
0x18003ecb6  call    cs:__imp_CreateWellKnownSid
0x18003ecbc  test    eax, eax
0x18003ecbe  jz      short loc_18003ED32
0x18003ecc0  lea     r9d, [r15+2]; dwAclInformationClass
0x18003ecc4  mov     rcx, rsi; pAcl
0x18003ecc7  lea     r8d, [r15+0Ch]; nAclInformationLength
0x18003eccb  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x18003eccf  call    cs:__imp_GetAclInformation
0x18003ecd5  test    eax, eax
0x18003ecd7  jz      short loc_18003ED32
0x18003ecd9  mov     ebx, r15d
0x18003ecdc  cmp     ebx, dword ptr [rbp+57h+pAclInformation]
0x18003ecdf  jnb     short loc_18003ED2D
0x18003ece1  lea     r8, [rbp+57h+pAce]; pAce
0x18003ece5  mov     edx, ebx; dwAceIndex
0x18003ece7  mov     rcx, rsi; pAcl
0x18003ecea  call    cs:__imp_GetAce
0x18003ecf0  test    eax, eax
0x18003ecf2  jz      short loc_18003ED32
0x18003ecf4  mov     rdx, [rbp+57h+pAce]
0x18003ecf8  test    byte ptr [rdx+1], 10h
0x18003ecfc  jz      short loc_18003ED22
0x18003ecfe  cmp     [rdx], r15b
0x18003ed01  jnz     short loc_18003ED22
0x18003ed03  add     rdx, 8; pSid2
0x18003ed07  lea     rcx, [rbp+57h+pSid]; pSid1
0x18003ed0b  call    cs:__imp_EqualSid
0x18003ed11  test    eax, eax
0x18003ed13  jz      short loc_18003ED22
0x18003ed15  mov     rax, [rbp+57h+pAce]
0x18003ed19  test    dword ptr [rax+4], 90000001h
0x18003ed20  jnz     short loc_18003ED26
0x18003ed22  inc     ebx
0x18003ed24  jmp     short loc_18003ECDC
0x18003ed26  mov     dword ptr [r14], 1
0x18003ed2d  mov     edi, 1
0x18003ed32  mov     eax, edi
0x18003ed34  mov     rcx, [rbp+57h+var_30]
0x18003ed38  xor     rcx, rsp; StackCookie
0x18003ed3b  call    __security_check_cookie
0x18003ed40  mov     rbx, [rsp+0D0h+arg_10]
0x18003ed48  add     rsp, 0B0h
0x18003ed4f  pop     r15
0x18003ed51  pop     r14
0x18003ed53  pop     rdi
0x18003ed54  pop     rsi
0x18003ed55  pop     rbp
0x18003ed56  retn
```
