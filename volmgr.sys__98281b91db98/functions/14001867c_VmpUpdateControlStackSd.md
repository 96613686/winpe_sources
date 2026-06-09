# VmpUpdateControlStackSd

- ea: `0x14001867c`
- end: `0x140018896`
- name: `VmpUpdateControlStackSd`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140018298`

## callees

- `0x14001867c`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001884e`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001884e`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14001886b`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14001886b`
- `ntoskrnl!RtlLengthSid` at `0x1400186b4`
- `ntoskrnl!RtlLengthSid` at `0x1400186c5`
- `ntoskrnl!RtlLengthSid` at `0x1400186e5`
- `ntoskrnl!RtlLengthSid` at `0x140018704`
- `ntoskrnl!RtlLengthSid` at `0x1400186b4`
- `ntoskrnl!RtlLengthSid` at `0x1400186c5`
- `ntoskrnl!RtlLengthSid` at `0x1400186e5`
- `ntoskrnl!RtlLengthSid` at `0x140018704`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001877f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400187b1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400187e3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140018815`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001877f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400187b1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400187e3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140018815`
- `ntoskrnl!RtlCreateAcl` at `0x14001874d`
- `ntoskrnl!RtlCreateAcl` at `0x14001874d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001882f`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001882f`
- `ntoskrnl!SeExports` at `0x140018685`
- `ntoskrnl!SeExports` at `0x1400186d4`
- `ntoskrnl!SeExports` at `0x1400186f3`
- `ntoskrnl!SeExports` at `0x140018763`
- `ntoskrnl!SeExports` at `0x140018795`
- `ntoskrnl!SeExports` at `0x1400187c7`
- `ntoskrnl!SeExports` at `0x1400187f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001887e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001887e`
- `ntoskrnl!ExAllocatePool2` at `0x140018722`
- `ntoskrnl!ExAllocatePool2` at `0x140018722`

## pseudocode

```c
__int64 __fastcall VmpUpdateControlStackSd(__int64 a1)
{
  PSID SeAliasAdminsSid; // rbx
  ULONG v3; // edi
  ULONG v4; // ebx
  struct _ACL *Pool2; // rax
  struct _ACL *v6; // rdi
  NTSTATUS Acl; // ebx
  _OWORD SecurityDescriptor[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v10; // [rsp+40h] [rbp-38h]

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v10 = 0;
  SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
  v3 = RtlLengthSid(SeExports->SeRestrictedSid);
  LODWORD(SeAliasAdminsSid) = v3 + RtlLengthSid(SeAliasAdminsSid);
  LODWORD(SeAliasAdminsSid) = RtlLengthSid(SeExports->SeLocalSystemSid) + (_DWORD)SeAliasAdminsSid;
  v4 = RtlLengthSid(SeExports->SeWorldSid) + 56 + (_DWORD)SeAliasAdminsSid;
  Pool2 = (struct _ACL *)ExAllocatePool2(258, v4, 538987862);
  v6 = Pool2;
  if ( Pool2 )
  {
    Acl = RtlCreateAcl(Pool2, v4, 2u);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v6, 2u, 0xA0000000, SeExports->SeWorldSid);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v6, 2u, 0x10000000u, SeExports->SeLocalSystemSid);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v6, 2u, 0x10000000u, SeExports->SeAliasAdminsSid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(v6, 2u, 0xA0000000, SeExports->SeRestrictedSid);
            if ( Acl >= 0 )
            {
              Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
              if ( Acl >= 0 )
              {
                Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v6, 0);
                if ( Acl >= 0 )
                  Acl = ObSetSecurityObjectByPointer(a1, 4, SecurityDescriptor);
              }
            }
          }
        }
      }
    }
    ExFreePoolWithTag(v6, 0);
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
0x14001867c  push    rbx
0x14001867e  push    rbp
0x14001867f  push    rsi
0x140018680  push    rdi
0x140018681  sub     rsp, 58h
0x140018685  mov     rdx, cs:__imp_SeExports
0x14001868c  xorps   xmm0, xmm0
0x14001868f  movups  [rsp+78h+SecurityDescriptor], xmm0
0x140018694  xor     eax, eax
0x140018696  mov     rsi, rcx
0x140018699  movups  [rsp+78h+var_48], xmm0
0x14001869e  mov     [rsp+78h+var_38], rax
0x1400186a3  mov     rax, [rdx]
0x1400186a6  mov     rcx, [rax+158h]; Sid
0x1400186ad  mov     rbx, [rax+110h]
0x1400186b4  call    cs:__imp_RtlLengthSid
0x1400186bb  nop     dword ptr [rax+rax+00h]
0x1400186c0  mov     rcx, rbx; Sid
0x1400186c3  mov     edi, eax
0x1400186c5  call    cs:__imp_RtlLengthSid
0x1400186cc  nop     dword ptr [rax+rax+00h]
0x1400186d1  lea     ebx, [rdi+rax]
0x1400186d4  mov     rax, cs:__imp_SeExports
0x1400186db  mov     rcx, [rax]
0x1400186de  mov     rcx, [rcx+108h]; Sid
0x1400186e5  call    cs:__imp_RtlLengthSid
0x1400186ec  nop     dword ptr [rax+rax+00h]
0x1400186f1  add     ebx, eax
0x1400186f3  mov     rax, cs:__imp_SeExports
0x1400186fa  mov     rcx, [rax]
0x1400186fd  mov     rcx, [rcx+0C0h]; Sid
0x140018704  call    cs:__imp_RtlLengthSid
0x14001870b  nop     dword ptr [rax+rax+00h]
0x140018710  mov     ecx, 102h
0x140018715  mov     r8d, 20204D56h
0x14001871b  add     eax, 38h ; '8'
0x14001871e  add     ebx, eax
0x140018720  mov     edx, ebx
0x140018722  call    cs:__imp_ExAllocatePool2
0x140018729  nop     dword ptr [rax+rax+00h]
0x14001872e  mov     rdi, rax
0x140018731  test    rax, rax
0x140018734  jnz     short loc_140018740
0x140018736  mov     ebx, 0C000009Ah
0x14001873b  jmp     loc_14001888A
0x140018740  mov     ebp, 2
0x140018745  mov     edx, ebx; AclLength
0x140018747  mov     r8d, ebp; AclRevision
0x14001874a  mov     rcx, rdi; Acl
0x14001874d  call    cs:__imp_RtlCreateAcl
0x140018754  nop     dword ptr [rax+rax+00h]
0x140018759  mov     ebx, eax
0x14001875b  test    eax, eax
0x14001875d  js      loc_140018879
0x140018763  mov     rax, cs:__imp_SeExports
0x14001876a  mov     r8d, 0A0000000h; AccessMask
0x140018770  mov     edx, ebp; AceRevision
0x140018772  mov     rcx, rdi; Acl
0x140018775  mov     r9, [rax]
0x140018778  mov     r9, [r9+0C0h]; Sid
0x14001877f  call    cs:__imp_RtlAddAccessAllowedAce
0x140018786  nop     dword ptr [rax+rax+00h]
0x14001878b  mov     ebx, eax
0x14001878d  test    eax, eax
0x14001878f  js      loc_140018879
0x140018795  mov     rax, cs:__imp_SeExports
0x14001879c  mov     r8d, 10000000h; AccessMask
0x1400187a2  mov     edx, ebp; AceRevision
0x1400187a4  mov     rcx, rdi; Acl
0x1400187a7  mov     r9, [rax]
0x1400187aa  mov     r9, [r9+108h]; Sid
0x1400187b1  call    cs:__imp_RtlAddAccessAllowedAce
0x1400187b8  nop     dword ptr [rax+rax+00h]
0x1400187bd  mov     ebx, eax
0x1400187bf  test    eax, eax
0x1400187c1  js      loc_140018879
0x1400187c7  mov     rax, cs:__imp_SeExports
0x1400187ce  mov     r8d, 10000000h; AccessMask
0x1400187d4  mov     edx, ebp; AceRevision
0x1400187d6  mov     rcx, rdi; Acl
0x1400187d9  mov     r9, [rax]
0x1400187dc  mov     r9, [r9+110h]; Sid
0x1400187e3  call    cs:__imp_RtlAddAccessAllowedAce
0x1400187ea  nop     dword ptr [rax+rax+00h]
0x1400187ef  mov     ebx, eax
0x1400187f1  test    eax, eax
0x1400187f3  js      loc_140018879
0x1400187f9  mov     rax, cs:__imp_SeExports
0x140018800  mov     r8d, 0A0000000h; AccessMask
0x140018806  mov     edx, ebp; AceRevision
0x140018808  mov     rcx, rdi; Acl
0x14001880b  mov     r9, [rax]
0x14001880e  mov     r9, [r9+158h]; Sid
0x140018815  call    cs:__imp_RtlAddAccessAllowedAce
0x14001881c  nop     dword ptr [rax+rax+00h]
0x140018821  mov     ebx, eax
0x140018823  test    eax, eax
0x140018825  js      short loc_140018879
0x140018827  lea     edx, [rbp-1]; Revision
0x14001882a  lea     rcx, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x14001882f  call    cs:__imp_RtlCreateSecurityDescriptor
0x140018836  nop     dword ptr [rax+rax+00h]
0x14001883b  mov     ebx, eax
0x14001883d  test    eax, eax
0x14001883f  js      short loc_140018879
0x140018841  xor     r9d, r9d; DaclDefaulted
0x140018844  lea     rcx, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x140018849  mov     r8, rdi; Dacl
0x14001884c  mov     dl, 1; DaclPresent
0x14001884e  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140018855  nop     dword ptr [rax+rax+00h]
0x14001885a  mov     ebx, eax
0x14001885c  test    eax, eax
0x14001885e  js      short loc_140018879
0x140018860  lea     r8, [rsp+78h+SecurityDescriptor]
0x140018865  mov     rcx, rsi
0x140018868  lea     edx, [rbp+2]
0x14001886b  call    cs:__imp_ObSetSecurityObjectByPointer
0x140018872  nop     dword ptr [rax+rax+00h]
0x140018877  mov     ebx, eax
0x140018879  xor     edx, edx; Tag
0x14001887b  mov     rcx, rdi; P
0x14001887e  call    cs:__imp_ExFreePoolWithTag
0x140018885  nop     dword ptr [rax+rax+00h]
0x14001888a  mov     eax, ebx
0x14001888c  add     rsp, 58h
0x140018890  pop     rdi
0x140018891  pop     rsi
0x140018892  pop     rbp
0x140018893  pop     rbx
0x140018894  retn
```
