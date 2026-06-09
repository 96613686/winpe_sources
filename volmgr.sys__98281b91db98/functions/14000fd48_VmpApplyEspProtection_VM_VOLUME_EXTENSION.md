# VmpApplyEspProtection(VM_VOLUME_EXTENSION *)

- ea: `0x14000fd48`
- end: `0x14001000e`
- name: `?VmpApplyEspProtection@@YAJPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400046a4`
- `0x140015da0`

## callees

- `0x140005050`
- `0x14000fd48`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x14000fdbc`
- `ntoskrnl!RtlInitializeSid` at `0x14000fdbc`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000fde6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000fde6`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000ff93`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000ff93`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14000ffb1`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14000ffb1`
- `ntoskrnl!RtlLengthSid` at `0x14000fe13`
- `ntoskrnl!RtlLengthSid` at `0x14000fe24`
- `ntoskrnl!RtlLengthSid` at `0x14000fe44`
- `ntoskrnl!RtlLengthSid` at `0x14000fe55`
- `ntoskrnl!RtlLengthSid` at `0x14000fe13`
- `ntoskrnl!RtlLengthSid` at `0x14000fe24`
- `ntoskrnl!RtlLengthSid` at `0x14000fe44`
- `ntoskrnl!RtlLengthSid` at `0x14000fe55`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000fecf`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000ff02`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000ff35`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000ff5a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000fecf`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000ff02`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000ff35`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000ff5a`
- `ntoskrnl!RtlCreateAcl` at `0x14000fe9c`
- `ntoskrnl!RtlCreateAcl` at `0x14000fe9c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000ff75`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000ff75`
- `ntoskrnl!SeExports` at `0x14000fdfb`
- `ntoskrnl!SeExports` at `0x14000fe33`
- `ntoskrnl!SeExports` at `0x14000feb2`
- `ntoskrnl!SeExports` at `0x14000fee5`
- `ntoskrnl!SeExports` at `0x14000ff18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ffd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ffe6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ffd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ffe6`
- `ntoskrnl!ExAllocatePool2` at `0x14000fd94`
- `ntoskrnl!ExAllocatePool2` at `0x14000fe70`
- `ntoskrnl!ExAllocatePool2` at `0x14000fd94`
- `ntoskrnl!ExAllocatePool2` at `0x14000fe70`

## pseudocode

```c
__int64 __fastcall VmpApplyEspProtection(struct VM_VOLUME_EXTENSION *a1)
{
  __int64 v1; // r14
  void *Pool2; // rax
  void *v3; // rsi
  NTSTATUS Acl; // ebx
  ULONG i; // edi
  ULONG v6; // ebx
  PULONG v7; // rax
  PSID SeLocalSystemSid; // rbx
  ULONG v9; // edi
  ULONG v10; // ebx
  struct _ACL *v11; // rax
  struct _ACL *v12; // rdi
  _OWORD SecurityDescriptor[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v15; // [rsp+40h] [rbp-28h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+48h] [rbp-20h] BYREF

  v1 = *(_QWORD *)a1;
  v15 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  Pool2 = (void *)ExAllocatePool2(258, 68, 538987862);
  v3 = Pool2;
  if ( Pool2 )
  {
    Acl = RtlInitializeSid(Pool2, &IdentifierAuthority, 6u);
    if ( Acl >= 0 )
    {
      for ( i = 0; i < 6; ++i )
      {
        v6 = *((_DWORD *)qword_140007838 + (int)i);
        v7 = RtlSubAuthoritySid(v3, i);
        *v7 = v6;
      }
      SeLocalSystemSid = SeExports->SeLocalSystemSid;
      v9 = RtlLengthSid(SeExports->SeAliasAdminsSid);
      LODWORD(SeLocalSystemSid) = v9 + RtlLengthSid(SeLocalSystemSid);
      LODWORD(SeLocalSystemSid) = RtlLengthSid(SeExports->SeWorldSid) + (_DWORD)SeLocalSystemSid;
      v10 = RtlLengthSid(v3) + 56 + (_DWORD)SeLocalSystemSid;
      v11 = (struct _ACL *)ExAllocatePool2(258, v10, 538987862);
      v12 = v11;
      if ( v11 )
      {
        Acl = RtlCreateAcl(v11, v10, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v12, 2u, 0x120080u, SeExports->SeWorldSid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(v12, 2u, 0x10000000u, SeExports->SeLocalSystemSid);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAce(v12, 2u, 0x10000000u, SeExports->SeAliasAdminsSid);
              if ( Acl >= 0 )
              {
                Acl = RtlAddAccessAllowedAce(v12, 2u, 0x10000000u, v3);
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v12, 0);
                    if ( Acl >= 0 )
                    {
                      Acl = ObSetSecurityObjectByPointer(v1, 4, SecurityDescriptor);
                      if ( Acl >= 0 )
                        *(_DWORD *)(v1 + 52) |= 0x100100u;
                    }
                  }
                }
              }
            }
          }
        }
        ExFreePoolWithTag(v12, 0);
      }
      else
      {
        Acl = -1073741670;
      }
    }
    ExFreePoolWithTag(v3, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14000fd48  push    rbp
0x14000fd4a  push    rbx
0x14000fd4b  push    rsi
0x14000fd4c  push    rdi
0x14000fd4d  push    r12
0x14000fd4f  push    r14
0x14000fd51  mov     rbp, rsp
0x14000fd54  sub     rsp, 68h
0x14000fd58  mov     rax, cs:__security_cookie
0x14000fd5f  xor     rax, rsp
0x14000fd62  mov     [rbp+var_18], rax
0x14000fd66  mov     r14, [rcx]
0x14000fd69  xor     eax, eax
0x14000fd6b  xorps   xmm0, xmm0
0x14000fd6e  mov     [rbp+var_28], rax
0x14000fd72  mov     r12d, 20204D56h
0x14000fd78  mov     dword ptr [rbp+IdentifierAuthority.Value], eax
0x14000fd7b  mov     r8d, r12d
0x14000fd7e  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x14000fd84  lea     edx, [rax+44h]
0x14000fd87  mov     ecx, 102h
0x14000fd8c  movups  [rbp+SecurityDescriptor], xmm0
0x14000fd90  movups  [rbp+var_38], xmm0
0x14000fd94  call    cs:__imp_ExAllocatePool2
0x14000fd9b  nop     dword ptr [rax+rax+00h]
0x14000fda0  mov     rsi, rax
0x14000fda3  test    rax, rax
0x14000fda6  jnz     short loc_14000FDB2
0x14000fda8  mov     ebx, 0C000009Ah
0x14000fdad  jmp     loc_14000FFF2
0x14000fdb2  mov     r8b, 6; SubAuthorityCount
0x14000fdb5  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14000fdb9  mov     rcx, rsi; Sid
0x14000fdbc  call    cs:__imp_RtlInitializeSid
0x14000fdc3  nop     dword ptr [rax+rax+00h]
0x14000fdc8  mov     ebx, eax
0x14000fdca  test    eax, eax
0x14000fdcc  js      loc_14000FFE1
0x14000fdd2  xor     edi, edi
0x14000fdd4  movsxd  rax, edi
0x14000fdd7  lea     rbx, qword_140007838
0x14000fdde  mov     edx, edi; SubAuthority
0x14000fde0  mov     rcx, rsi; Sid
0x14000fde3  mov     ebx, [rbx+rax*4]
0x14000fde6  call    cs:__imp_RtlSubAuthoritySid
0x14000fded  nop     dword ptr [rax+rax+00h]
0x14000fdf2  inc     edi
0x14000fdf4  mov     [rax], ebx
0x14000fdf6  cmp     edi, 6
0x14000fdf9  jb      short loc_14000FDD4
0x14000fdfb  mov     rdx, cs:__imp_SeExports
0x14000fe02  mov     rax, [rdx]
0x14000fe05  mov     rcx, [rax+110h]; Sid
0x14000fe0c  mov     rbx, [rax+108h]
0x14000fe13  call    cs:__imp_RtlLengthSid
0x14000fe1a  nop     dword ptr [rax+rax+00h]
0x14000fe1f  mov     rcx, rbx; Sid
0x14000fe22  mov     edi, eax
0x14000fe24  call    cs:__imp_RtlLengthSid
0x14000fe2b  nop     dword ptr [rax+rax+00h]
0x14000fe30  lea     ebx, [rdi+rax]
0x14000fe33  mov     rax, cs:__imp_SeExports
0x14000fe3a  mov     rcx, [rax]
0x14000fe3d  mov     rcx, [rcx+0C0h]; Sid
0x14000fe44  call    cs:__imp_RtlLengthSid
0x14000fe4b  nop     dword ptr [rax+rax+00h]
0x14000fe50  mov     rcx, rsi; Sid
0x14000fe53  add     ebx, eax
0x14000fe55  call    cs:__imp_RtlLengthSid
0x14000fe5c  nop     dword ptr [rax+rax+00h]
0x14000fe61  mov     r8d, r12d
0x14000fe64  mov     ecx, 102h
0x14000fe69  add     eax, 38h ; '8'
0x14000fe6c  add     ebx, eax
0x14000fe6e  mov     edx, ebx
0x14000fe70  call    cs:__imp_ExAllocatePool2
0x14000fe77  nop     dword ptr [rax+rax+00h]
0x14000fe7c  mov     rdi, rax
0x14000fe7f  test    rax, rax
0x14000fe82  jnz     short loc_14000FE8E
0x14000fe84  mov     ebx, 0C000009Ah
0x14000fe89  jmp     loc_14000FFE1
0x14000fe8e  mov     r12d, 2
0x14000fe94  mov     edx, ebx; AclLength
0x14000fe96  mov     r8d, r12d; AclRevision
0x14000fe99  mov     rcx, rdi; Acl
0x14000fe9c  call    cs:__imp_RtlCreateAcl
0x14000fea3  nop     dword ptr [rax+rax+00h]
0x14000fea8  mov     ebx, eax
0x14000feaa  test    eax, eax
0x14000feac  js      loc_14000FFD0
0x14000feb2  mov     rax, cs:__imp_SeExports
0x14000feb9  mov     r8d, 120080h; AccessMask
0x14000febf  mov     edx, r12d; AceRevision
0x14000fec2  mov     rcx, rdi; Acl
0x14000fec5  mov     r9, [rax]
0x14000fec8  mov     r9, [r9+0C0h]; Sid
0x14000fecf  call    cs:__imp_RtlAddAccessAllowedAce
0x14000fed6  nop     dword ptr [rax+rax+00h]
0x14000fedb  mov     ebx, eax
0x14000fedd  test    eax, eax
0x14000fedf  js      loc_14000FFD0
0x14000fee5  mov     rax, cs:__imp_SeExports
0x14000feec  mov     r8d, 10000000h; AccessMask
0x14000fef2  mov     edx, r12d; AceRevision
0x14000fef5  mov     rcx, rdi; Acl
0x14000fef8  mov     r9, [rax]
0x14000fefb  mov     r9, [r9+108h]; Sid
0x14000ff02  call    cs:__imp_RtlAddAccessAllowedAce
0x14000ff09  nop     dword ptr [rax+rax+00h]
0x14000ff0e  mov     ebx, eax
0x14000ff10  test    eax, eax
0x14000ff12  js      loc_14000FFD0
0x14000ff18  mov     rax, cs:__imp_SeExports
0x14000ff1f  mov     r8d, 10000000h; AccessMask
0x14000ff25  mov     edx, r12d; AceRevision
0x14000ff28  mov     rcx, rdi; Acl
0x14000ff2b  mov     r9, [rax]
0x14000ff2e  mov     r9, [r9+110h]; Sid
0x14000ff35  call    cs:__imp_RtlAddAccessAllowedAce
0x14000ff3c  nop     dword ptr [rax+rax+00h]
0x14000ff41  mov     ebx, eax
0x14000ff43  test    eax, eax
0x14000ff45  js      loc_14000FFD0
0x14000ff4b  mov     r9, rsi; Sid
0x14000ff4e  mov     r8d, 10000000h; AccessMask
0x14000ff54  mov     edx, r12d; AceRevision
0x14000ff57  mov     rcx, rdi; Acl
0x14000ff5a  call    cs:__imp_RtlAddAccessAllowedAce
0x14000ff61  nop     dword ptr [rax+rax+00h]
0x14000ff66  mov     ebx, eax
0x14000ff68  test    eax, eax
0x14000ff6a  js      short loc_14000FFD0
0x14000ff6c  lea     edx, [r12-1]; Revision
0x14000ff71  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000ff75  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000ff7c  nop     dword ptr [rax+rax+00h]
0x14000ff81  mov     ebx, eax
0x14000ff83  test    eax, eax
0x14000ff85  js      short loc_14000FFD0
0x14000ff87  xor     r9d, r9d; DaclDefaulted
0x14000ff8a  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000ff8e  mov     r8, rdi; Dacl
0x14000ff91  mov     dl, 1; DaclPresent
0x14000ff93  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000ff9a  nop     dword ptr [rax+rax+00h]
0x14000ff9f  mov     ebx, eax
0x14000ffa1  test    eax, eax
0x14000ffa3  js      short loc_14000FFD0
0x14000ffa5  lea     r8, [rbp+SecurityDescriptor]
0x14000ffa9  mov     rcx, r14
0x14000ffac  lea     edx, [r12+2]
0x14000ffb1  call    cs:__imp_ObSetSecurityObjectByPointer
0x14000ffb8  nop     dword ptr [rax+rax+00h]
0x14000ffbd  mov     ebx, eax
0x14000ffbf  test    eax, eax
0x14000ffc1  js      short loc_14000FFD0
0x14000ffc3  mov     eax, [r14+34h]
0x14000ffc7  or      eax, 100100h
0x14000ffcc  mov     [r14+34h], eax
0x14000ffd0  xor     edx, edx; Tag
0x14000ffd2  mov     rcx, rdi; P
0x14000ffd5  call    cs:__imp_ExFreePoolWithTag
0x14000ffdc  nop     dword ptr [rax+rax+00h]
0x14000ffe1  xor     edx, edx; Tag
0x14000ffe3  mov     rcx, rsi; P
0x14000ffe6  call    cs:__imp_ExFreePoolWithTag
0x14000ffed  nop     dword ptr [rax+rax+00h]
0x14000fff2  mov     eax, ebx
0x14000fff4  mov     rcx, [rbp+var_18]
0x14000fff8  xor     rcx, rsp; StackCookie
0x14000fffb  call    __security_check_cookie
0x140010000  add     rsp, 68h
0x140010004  pop     r14
0x140010006  pop     r12
0x140010008  pop     rdi
0x140010009  pop     rsi
0x14001000a  pop     rbx
0x14001000b  pop     rbp
0x14001000c  retn
```
