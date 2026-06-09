# RawCreateSocketSecurityDescriptor

- ea: `0x14016ac54`
- end: `0x14016ae71`
- name: `RawCreateSocketSecurityDescriptor`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14014cde0`

## callees

- `0x14016ac54`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14016ae32`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14016ae32`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016ad8e`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016adbb`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016ade4`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016ae0d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016ad8e`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016adbb`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016ade4`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016ae0d`
- `ntoskrnl!RtlCreateAcl` at `0x14016ad5c`
- `ntoskrnl!RtlCreateAcl` at `0x14016ad5c`
- `ntoskrnl!RtlLengthSid` at `0x14016acc3`
- `ntoskrnl!RtlLengthSid` at `0x14016acd4`
- `ntoskrnl!RtlLengthSid` at `0x14016ace5`
- `ntoskrnl!RtlLengthSid` at `0x14016acf6`
- `ntoskrnl!RtlLengthSid` at `0x14016acc3`
- `ntoskrnl!RtlLengthSid` at `0x14016acd4`
- `ntoskrnl!RtlLengthSid` at `0x14016ace5`
- `ntoskrnl!RtlLengthSid` at `0x14016acf6`
- `ntoskrnl!SeExports` at `0x14016ac9a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14016ac84`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14016ac84`
- `ntoskrnl!ExAllocatePool3` at `0x14016ad2c`
- `ntoskrnl!ExAllocatePool3` at `0x14016ad2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016ae55`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016ae55`

## pseudocode

```c
__int64 RawCreateSocketSecurityDescriptor()
{
  NTSTATUS SecurityDescriptor; // ebx
  PSID SeLocalServiceSid; // r14
  PSID Sid; // rdi
  PSID SeLocalSystemSid; // rsi
  PSID SeNetworkServiceSid; // rbp
  ULONG v5; // ebx
  ULONG v6; // ebx
  ULONG v7; // ebx
  ULONG v8; // ebx
  struct _ACL *Pool3; // rax
  __int128 v11[4]; // [rsp+30h] [rbp-48h] BYREF

  Dacl = 0;
  v11[0] = 0;
  SecurityDescriptor = RtlCreateSecurityDescriptor(qword_140228750, 1u);
  if ( SecurityDescriptor >= 0 )
  {
    SeLocalServiceSid = SeExports->SeLocalServiceSid;
    Sid = SeExports->SeAliasAdminsSid;
    SeLocalSystemSid = SeExports->SeLocalSystemSid;
    SeNetworkServiceSid = SeExports->SeNetworkServiceSid;
    v5 = RtlLengthSid(SeLocalServiceSid);
    v6 = RtlLengthSid(SeNetworkServiceSid) + v5;
    v7 = RtlLengthSid(SeLocalSystemSid) + v6;
    v11[0] = 1u;
    v8 = RtlLengthSid(Sid) + 40 + v7;
    Pool3 = (struct _ACL *)ExAllocatePool3(64, v8, 1095000402, v11, 1);
    Dacl = Pool3;
    if ( !Pool3 )
    {
      SecurityDescriptor = -1073741670;
      goto LABEL_11;
    }
    SecurityDescriptor = RtlCreateAcl(Pool3, v8, 2u);
    if ( SecurityDescriptor >= 0 )
    {
      SecurityDescriptor = RtlAddAccessAllowedAceEx(Dacl, 2u, 3u, 0xF003Fu, Sid);
      if ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = RtlAddAccessAllowedAceEx(Dacl, 2u, 3u, 0xF003Fu, SeLocalSystemSid);
        if ( SecurityDescriptor >= 0 )
        {
          SecurityDescriptor = RtlAddAccessAllowedAceEx(Dacl, 2u, 3u, 0xF003Fu, SeNetworkServiceSid);
          if ( SecurityDescriptor >= 0 )
          {
            SecurityDescriptor = RtlAddAccessAllowedAceEx(Dacl, 2u, 3u, 0xF003Fu, SeLocalServiceSid);
            if ( SecurityDescriptor >= 0 )
            {
              SecurityDescriptor = RtlSetDaclSecurityDescriptor(qword_140228750, 1u, Dacl, 0);
              if ( SecurityDescriptor >= 0 )
                return (unsigned int)SecurityDescriptor;
            }
          }
        }
      }
    }
  }
  Pool3 = Dacl;
LABEL_11:
  if ( Pool3 )
    ExFreePoolWithTag(Pool3, 0);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x14016ac54  push    rbx
0x14016ac56  push    rbp
0x14016ac57  push    rsi
0x14016ac58  push    rdi
0x14016ac59  push    r12
0x14016ac5b  push    r14
0x14016ac5d  sub     rsp, 48h
0x14016ac61  xorps   xmm0, xmm0
0x14016ac64  mov     cs:Dacl, 0
0x14016ac6f  mov     r12d, 1
0x14016ac75  lea     rcx, qword_140228750; SecurityDescriptor
0x14016ac7c  mov     edx, r12d; Revision
0x14016ac7f  movups  [rsp+78h+var_48], xmm0
0x14016ac84  call    cs:__imp_RtlCreateSecurityDescriptor
0x14016ac8b  nop     dword ptr [rax+rax+00h]
0x14016ac90  mov     ebx, eax
0x14016ac92  test    eax, eax
0x14016ac94  js      loc_14016AE44
0x14016ac9a  mov     rax, cs:__imp_SeExports
0x14016aca1  mov     rcx, [rax]
0x14016aca4  mov     r14, [rcx+180h]
0x14016acab  mov     rdi, [rcx+110h]
0x14016acb2  mov     rsi, [rcx+108h]
0x14016acb9  mov     rbp, [rcx+188h]
0x14016acc0  mov     rcx, r14; Sid
0x14016acc3  call    cs:__imp_RtlLengthSid
0x14016acca  nop     dword ptr [rax+rax+00h]
0x14016accf  mov     rcx, rbp; Sid
0x14016acd2  mov     ebx, eax
0x14016acd4  call    cs:__imp_RtlLengthSid
0x14016acdb  nop     dword ptr [rax+rax+00h]
0x14016ace0  mov     rcx, rsi; Sid
0x14016ace3  add     ebx, eax
0x14016ace5  call    cs:__imp_RtlLengthSid
0x14016acec  nop     dword ptr [rax+rax+00h]
0x14016acf1  mov     rcx, rdi; Sid
0x14016acf4  add     ebx, eax
0x14016acf6  call    cs:__imp_RtlLengthSid
0x14016acfd  nop     dword ptr [rax+rax+00h]
0x14016ad02  lea     r9, [rsp+78h+var_48]
0x14016ad07  mov     qword ptr [rsp+78h+var_48+8], 0
0x14016ad10  add     eax, 28h ; '('
0x14016ad13  mov     qword ptr [rsp+78h+var_48], r12
0x14016ad18  add     ebx, eax
0x14016ad1a  mov     dword ptr [rsp+78h+Sid], r12d
0x14016ad1f  mov     edx, ebx
0x14016ad21  lea     ecx, [r12+3Fh]
0x14016ad26  mov     r8d, 41446152h
0x14016ad2c  call    cs:__imp_ExAllocatePool3
0x14016ad33  nop     dword ptr [rax+rax+00h]
0x14016ad38  mov     cs:Dacl, rax
0x14016ad3f  test    rax, rax
0x14016ad42  jnz     short loc_14016AD4E
0x14016ad44  mov     ebx, 0C000009Ah
0x14016ad49  jmp     loc_14016AE4B
0x14016ad4e  mov     r12d, 2
0x14016ad54  mov     edx, ebx; AclLength
0x14016ad56  mov     r8d, r12d; AclRevision
0x14016ad59  mov     rcx, rax; Acl
0x14016ad5c  call    cs:__imp_RtlCreateAcl
0x14016ad63  nop     dword ptr [rax+rax+00h]
0x14016ad68  mov     ebx, eax
0x14016ad6a  test    eax, eax
0x14016ad6c  js      loc_14016AE44
0x14016ad72  mov     rcx, cs:Dacl; Acl
0x14016ad79  lea     r8d, [r12+1]; AceFlags
0x14016ad7e  mov     [rsp+78h+Sid], rdi; Sid
0x14016ad83  mov     edx, r12d; AceRevision
0x14016ad86  mov     edi, 0F003Fh
0x14016ad8b  mov     r9d, edi; AccessMask
0x14016ad8e  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14016ad95  nop     dword ptr [rax+rax+00h]
0x14016ad9a  mov     ebx, eax
0x14016ad9c  test    eax, eax
0x14016ad9e  js      loc_14016AE44
0x14016ada4  mov     rcx, cs:Dacl; Acl
0x14016adab  lea     r8d, [r12+1]; AceFlags
0x14016adb0  mov     r9d, edi; AccessMask
0x14016adb3  mov     [rsp+78h+Sid], rsi; Sid
0x14016adb8  mov     edx, r12d; AceRevision
0x14016adbb  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14016adc2  nop     dword ptr [rax+rax+00h]
0x14016adc7  mov     ebx, eax
0x14016adc9  test    eax, eax
0x14016adcb  js      short loc_14016AE44
0x14016adcd  mov     rcx, cs:Dacl; Acl
0x14016add4  lea     r8d, [r12+1]; AceFlags
0x14016add9  mov     r9d, edi; AccessMask
0x14016addc  mov     [rsp+78h+Sid], rbp; Sid
0x14016ade1  mov     edx, r12d; AceRevision
0x14016ade4  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14016adeb  nop     dword ptr [rax+rax+00h]
0x14016adf0  mov     ebx, eax
0x14016adf2  test    eax, eax
0x14016adf4  js      short loc_14016AE44
0x14016adf6  mov     rcx, cs:Dacl; Acl
0x14016adfd  lea     r8d, [r12+1]; AceFlags
0x14016ae02  mov     r9d, edi; AccessMask
0x14016ae05  mov     [rsp+78h+Sid], r14; Sid
0x14016ae0a  mov     edx, r12d; AceRevision
0x14016ae0d  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14016ae14  nop     dword ptr [rax+rax+00h]
0x14016ae19  mov     ebx, eax
0x14016ae1b  test    eax, eax
0x14016ae1d  js      short loc_14016AE44
0x14016ae1f  mov     r8, cs:Dacl; Dacl
0x14016ae26  lea     rcx, qword_140228750; SecurityDescriptor
0x14016ae2d  xor     r9d, r9d; DaclDefaulted
0x14016ae30  mov     dl, 1; DaclPresent
0x14016ae32  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14016ae39  nop     dword ptr [rax+rax+00h]
0x14016ae3e  mov     ebx, eax
0x14016ae40  test    eax, eax
0x14016ae42  jns     short loc_14016AE61
0x14016ae44  mov     rax, cs:Dacl
0x14016ae4b  test    rax, rax
0x14016ae4e  jz      short loc_14016AE61
0x14016ae50  xor     edx, edx; Tag
0x14016ae52  mov     rcx, rax; P
0x14016ae55  call    cs:__imp_ExFreePoolWithTag
0x14016ae5c  nop     dword ptr [rax+rax+00h]
0x14016ae61  mov     eax, ebx
0x14016ae63  add     rsp, 48h
0x14016ae67  pop     r14
0x14016ae69  pop     r12
0x14016ae6b  pop     rdi
0x14016ae6c  pop     rsi
0x14016ae6d  pop     rbp
0x14016ae6e  pop     rbx
0x14016ae6f  retn
```
