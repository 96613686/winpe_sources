# SAL2::CreateWellKnownACL(WELL_KNOWN_SID_TYPE,_ACL * *,_SECURITY_DESCRIPTOR * *)

- ea: `0x180085bb4`
- end: `0x180085cfa`
- name: `?CreateWellKnownACL@SAL2@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAU_ACL@@PEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `326`
- prototype: `unsigned int __fastcall(SAL2 *__hidden this, enum WELL_KNOWN_SID_TYPE, struct _ACL **, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180080a48`
- `0x180080b28`

## callees

- `0x18000256c`
- `0x180060e40`
- `0x180085bb4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180085cae`
- `KERNEL32!GetLastError` at `0x180085cae`
- `KERNEL32!LocalFree` at `0x180085cdf`
- `KERNEL32!LocalFree` at `0x180085cdf`
- `KERNEL32!LocalAlloc` at `0x180085be8`
- `KERNEL32!LocalAlloc` at `0x180085c2a`
- `KERNEL32!LocalAlloc` at `0x180085c7a`
- `KERNEL32!LocalAlloc` at `0x180085be8`
- `KERNEL32!LocalAlloc` at `0x180085c2a`
- `KERNEL32!LocalAlloc` at `0x180085c7a`
- `ADVAPI32!GetLengthSid` at `0x180085c18`
- `ADVAPI32!GetLengthSid` at `0x180085c18`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180085c8e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180085c8e`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180085ca4`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180085ca4`
- `ADVAPI32!InitializeAcl` at `0x180085c52`
- `ADVAPI32!InitializeAcl` at `0x180085c52`
- `ADVAPI32!AddAccessAllowedAce` at `0x180085c6a`
- `ADVAPI32!AddAccessAllowedAce` at `0x180085c6a`
- `ADVAPI32!CreateWellKnownSid` at `0x180085c07`
- `ADVAPI32!CreateWellKnownSid` at `0x180085c07`

## pseudocode

```c
__int64 __fastcall SAL2::CreateWellKnownACL(
        SAL2 *this,
        PACL *a2,
        PSECURITY_DESCRIPTOR *a3,
        struct _SECURITY_DESCRIPTOR **a4)
{
  HLOCAL v6; // rax
  void *v7; // rdi
  DWORD v8; // ebx
  ACL *v9; // rax
  struct _ACL *v10; // rax
  DWORD LastError; // ebx
  struct _SECURITY_DESCRIPTOR *v12; // r8
  DWORD cbSid; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  *a3 = 0;
  cbSid = 68;
  v6 = LocalAlloc(0, 0x44u);
  v7 = v6;
  if ( v6 )
  {
    if ( CreateWellKnownSid(WinWorldSid, 0, v6, &cbSid) )
    {
      v8 = GetLengthSid(v7) + 16;
      v9 = (ACL *)LocalAlloc(0x40u, v8);
      *a2 = v9;
      if ( v9 )
      {
        memset_0(v9, 0, v8);
        if ( InitializeAcl(*a2, v8, 2u) )
        {
          if ( AddAccessAllowedAce(*a2, 2u, 0x10000000u, v7) )
          {
            v10 = (struct _ACL *)LocalAlloc(0x40u, 0x28u);
            *a3 = v10;
            if ( v10 )
            {
              if ( InitializeSecurityDescriptor(v10, 1u) && SetSecurityDescriptorDacl(*a3, 1, *a2, 0) )
              {
                LastError = 0;
LABEL_14:
                LocalFree(v7);
                return LastError;
              }
            }
          }
        }
      }
    }
  }
  LastError = GetLastError();
  if ( LastError )
  {
    SBECoreUtil::FreeSecurityDescriptors((SBECoreUtil *)*a2, (struct _ACL *)*a3, v12);
    *a2 = 0;
    *a3 = 0;
  }
  if ( v7 )
    goto LABEL_14;
  return LastError;
}

```

## disassembly

```asm
0x180085bb4  mov     rax, rsp
0x180085bb7  mov     [rax+10h], rbx
0x180085bbb  mov     [rax+18h], rbp
0x180085bbf  mov     [rax+8], ecx
0x180085bc2  push    rsi
0x180085bc3  push    rdi
0x180085bc4  push    r14
0x180085bc6  sub     rsp, 20h
0x180085bca  mov     qword ptr [rdx], 0
0x180085bd1  mov     rsi, rdx
0x180085bd4  mov     edx, 44h ; 'D'; uBytes
0x180085bd9  mov     qword ptr [r8], 0
0x180085be0  xor     ecx, ecx; uFlags
0x180085be2  mov     [rax+8], edx
0x180085be5  mov     r14, r8
0x180085be8  call    cs:__imp_LocalAlloc
0x180085bee  mov     rdi, rax
0x180085bf1  test    rax, rax
0x180085bf4  jz      loc_180085CAE
0x180085bfa  xor     edx, edx; DomainSid
0x180085bfc  lea     r9, [rsp+38h+cbSid]; cbSid
0x180085c01  mov     r8, rax; pSid
0x180085c04  lea     ecx, [rdx+1]; WellKnownSidType
0x180085c07  call    cs:__imp_CreateWellKnownSid
0x180085c0d  test    eax, eax
0x180085c0f  jz      loc_180085CAE
0x180085c15  mov     rcx, rdi; pSid
0x180085c18  call    cs:__imp_GetLengthSid
0x180085c1e  mov     ecx, 40h ; '@'; uFlags
0x180085c23  lea     ebx, [rax+10h]
0x180085c26  mov     edx, ebx; uBytes
0x180085c28  mov     ebp, ebx
0x180085c2a  call    cs:__imp_LocalAlloc
0x180085c30  mov     [rsi], rax
0x180085c33  test    rax, rax
0x180085c36  jz      short loc_180085CAE
0x180085c38  mov     r8d, ebp; Size
0x180085c3b  xor     edx, edx; Val
0x180085c3d  mov     rcx, rax; void *
0x180085c40  call    memset_0
0x180085c45  mov     rcx, [rsi]; pAcl
0x180085c48  mov     ebp, 2
0x180085c4d  mov     r8d, ebp; dwAclRevision
0x180085c50  mov     edx, ebx; nAclLength
0x180085c52  call    cs:__imp_InitializeAcl
0x180085c58  test    eax, eax
0x180085c5a  jz      short loc_180085CAE
0x180085c5c  mov     rcx, [rsi]; pAcl
0x180085c5f  mov     r9, rdi; pSid
0x180085c62  mov     r8d, 10000000h; AccessMask
0x180085c68  mov     edx, ebp; dwAceRevision
0x180085c6a  call    cs:__imp_AddAccessAllowedAce
0x180085c70  test    eax, eax
0x180085c72  jz      short loc_180085CAE
0x180085c74  lea     edx, [rbp+26h]; uBytes
0x180085c77  lea     ecx, [rbp+3Eh]; uFlags
0x180085c7a  call    cs:__imp_LocalAlloc
0x180085c80  mov     [r14], rax
0x180085c83  test    rax, rax
0x180085c86  jz      short loc_180085CAE
0x180085c88  lea     edx, [rbp-1]; dwRevision
0x180085c8b  mov     rcx, rax; pSecurityDescriptor
0x180085c8e  call    cs:__imp_InitializeSecurityDescriptor
0x180085c94  test    eax, eax
0x180085c96  jz      short loc_180085CAE
0x180085c98  mov     r8, [rsi]; pDacl
0x180085c9b  lea     edx, [rbp-1]; bDaclPresent
0x180085c9e  mov     rcx, [r14]; pSecurityDescriptor
0x180085ca1  xor     r9d, r9d; bDaclDefaulted
0x180085ca4  call    cs:__imp_SetSecurityDescriptorDacl
0x180085caa  test    eax, eax
0x180085cac  jnz     short loc_180085CDA
0x180085cae  call    cs:__imp_GetLastError
0x180085cb4  mov     ebx, eax
0x180085cb6  test    eax, eax
0x180085cb8  jz      short loc_180085CD3
0x180085cba  mov     rdx, [r14]; struct _ACL *
0x180085cbd  mov     rcx, [rsi]; this
0x180085cc0  call    ?FreeSecurityDescriptors@SBECoreUtil@@YAXPEAU_ACL@@PEAU_SECURITY_DESCRIPTOR@@@Z; SBECoreUtil::FreeSecurityDescriptors(_ACL *,_SECURITY_DESCRIPTOR *)
0x180085cc5  mov     qword ptr [rsi], 0
0x180085ccc  mov     qword ptr [r14], 0
0x180085cd3  test    rdi, rdi
0x180085cd6  jz      short loc_180085CE5
0x180085cd8  jmp     short loc_180085CDC
0x180085cda  xor     ebx, ebx
0x180085cdc  mov     rcx, rdi; hMem
0x180085cdf  call    cs:__imp_LocalFree
0x180085ce5  mov     rbp, [rsp+38h+arg_10]
0x180085cea  mov     eax, ebx
0x180085cec  mov     rbx, [rsp+38h+arg_8]
0x180085cf1  add     rsp, 20h
0x180085cf5  pop     r14
0x180085cf7  pop     rdi
0x180085cf8  pop     rsi
0x180085cf9  retn
```
