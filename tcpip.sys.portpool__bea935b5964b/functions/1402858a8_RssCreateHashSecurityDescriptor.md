# RssCreateHashSecurityDescriptor

- ea: `0x1402858a8`
- end: `0x140285ae4`
- name: `RssCreateHashSecurityDescriptor`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140285af0`

## callees

- `0x14025b34c`
- `0x1402858a8`

## import_xrefs

- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140285ab1`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140285ab1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140285a87`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140285a87`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1402859de`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140285a0d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140285a38`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140285a5f`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1402859de`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140285a0d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140285a38`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140285a5f`
- `ntoskrnl!RtlCreateAcl` at `0x1402859ad`
- `ntoskrnl!RtlCreateAcl` at `0x1402859ad`
- `ntoskrnl!RtlLengthSid` at `0x140285915`
- `ntoskrnl!RtlLengthSid` at `0x140285926`
- `ntoskrnl!RtlLengthSid` at `0x140285937`
- `ntoskrnl!RtlLengthSid` at `0x140285948`
- `ntoskrnl!RtlLengthSid` at `0x140285915`
- `ntoskrnl!RtlLengthSid` at `0x140285926`
- `ntoskrnl!RtlLengthSid` at `0x140285937`
- `ntoskrnl!RtlLengthSid` at `0x140285948`
- `ntoskrnl!SeExports` at `0x1402858e5`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402858cf`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402858cf`
- `ntoskrnl!ExAllocatePool3` at `0x14028597d`
- `ntoskrnl!ExAllocatePool3` at `0x14028597d`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140285a9c`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140285a9c`

## pseudocode

```c
__int64 RssCreateHashSecurityDescriptor()
{
  NTSTATUS SecurityDescriptor; // ebx
  PSID SeLocalServiceSid; // r15
  PSID Sid; // rsi
  PSID SeLocalSystemSid; // rbp
  PSID SeNetworkServiceSid; // r14
  PSID SeNullSid; // rdi
  ULONG v6; // ebx
  ULONG v7; // ebx
  ULONG v8; // ebx
  ULONG v9; // ebx
  struct _ACL *Pool3; // rax
  __int128 v12[4]; // [rsp+30h] [rbp-48h] BYREF

  v12[0] = 0;
  SecurityDescriptor = RtlCreateSecurityDescriptor(RssHashSecurityDescriptor, 1u);
  if ( SecurityDescriptor >= 0 )
  {
    SeLocalServiceSid = SeExports->SeLocalServiceSid;
    Sid = SeExports->SeAliasAdminsSid;
    SeLocalSystemSid = SeExports->SeLocalSystemSid;
    SeNetworkServiceSid = SeExports->SeNetworkServiceSid;
    SeNullSid = SeExports->SeNullSid;
    v6 = RtlLengthSid(SeLocalServiceSid);
    v7 = RtlLengthSid(SeNetworkServiceSid) + v6;
    v8 = RtlLengthSid(SeLocalSystemSid) + v7;
    v12[0] = 1u;
    v9 = RtlLengthSid(Sid) + 40 + v8;
    Pool3 = (struct _ACL *)ExAllocatePool3(64, v9, 1735619410, v12, 1);
    RssHashDacl = Pool3;
    if ( Pool3 )
    {
      SecurityDescriptor = RtlCreateAcl(Pool3, v9, 2u);
      if ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = RtlAddAccessAllowedAceEx((PACL)RssHashDacl, 2u, 3u, 0xF003Fu, Sid);
        if ( SecurityDescriptor >= 0 )
        {
          SecurityDescriptor = RtlAddAccessAllowedAceEx((PACL)RssHashDacl, 2u, 3u, 0xF003Fu, SeLocalSystemSid);
          if ( SecurityDescriptor >= 0 )
          {
            SecurityDescriptor = RtlAddAccessAllowedAceEx((PACL)RssHashDacl, 2u, 3u, 0xF003Fu, SeNetworkServiceSid);
            if ( SecurityDescriptor >= 0 )
            {
              SecurityDescriptor = RtlAddAccessAllowedAceEx((PACL)RssHashDacl, 2u, 3u, 0xF003Fu, SeLocalServiceSid);
              if ( SecurityDescriptor >= 0 )
              {
                RtlSetDaclSecurityDescriptor(RssHashSecurityDescriptor, 1u, (PACL)RssHashDacl, 0);
                RtlSetOwnerSecurityDescriptor(RssHashSecurityDescriptor, SeNullSid, 0);
                SecurityDescriptor = RtlSetGroupSecurityDescriptor(RssHashSecurityDescriptor, SeNullSid, 0);
                if ( SecurityDescriptor >= 0 )
                  return (unsigned int)SecurityDescriptor;
              }
            }
          }
        }
      }
    }
    else
    {
      SecurityDescriptor = -1073741670;
    }
  }
  if ( RssHashDacl )
    RssDestroyHashSecurityDescriptor();
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x1402858a8  push    rbx
0x1402858aa  push    rbp
0x1402858ab  push    rsi
0x1402858ac  push    rdi
0x1402858ad  push    r13
0x1402858af  push    r14
0x1402858b1  push    r15
0x1402858b3  sub     rsp, 40h
0x1402858b7  xorps   xmm0, xmm0
0x1402858ba  lea     rcx, RssHashSecurityDescriptor; SecurityDescriptor
0x1402858c1  mov     r13d, 1
0x1402858c7  mov     edx, r13d; Revision
0x1402858ca  movups  [rsp+78h+var_48], xmm0
0x1402858cf  call    cs:__imp_RtlCreateSecurityDescriptor
0x1402858d6  nop     dword ptr [rax+rax+00h]
0x1402858db  mov     ebx, eax
0x1402858dd  test    eax, eax
0x1402858df  js      loc_140285AC3
0x1402858e5  mov     rax, cs:__imp_SeExports
0x1402858ec  mov     rcx, [rax]
0x1402858ef  mov     r15, [rcx+180h]
0x1402858f6  mov     rsi, [rcx+110h]
0x1402858fd  mov     rbp, [rcx+108h]
0x140285904  mov     r14, [rcx+188h]
0x14028590b  mov     rdi, [rcx+0B8h]
0x140285912  mov     rcx, r15; Sid
0x140285915  call    cs:__imp_RtlLengthSid
0x14028591c  nop     dword ptr [rax+rax+00h]
0x140285921  mov     rcx, r14; Sid
0x140285924  mov     ebx, eax
0x140285926  call    cs:__imp_RtlLengthSid
0x14028592d  nop     dword ptr [rax+rax+00h]
0x140285932  mov     rcx, rbp; Sid
0x140285935  add     ebx, eax
0x140285937  call    cs:__imp_RtlLengthSid
0x14028593e  nop     dword ptr [rax+rax+00h]
0x140285943  mov     rcx, rsi; Sid
0x140285946  add     ebx, eax
0x140285948  call    cs:__imp_RtlLengthSid
0x14028594f  nop     dword ptr [rax+rax+00h]
0x140285954  lea     r9, [rsp+78h+var_48]
0x140285959  mov     qword ptr [rsp+78h+var_48+8], 0
0x140285962  add     eax, 28h ; '('
0x140285965  mov     qword ptr [rsp+78h+var_48], r13
0x14028596a  add     ebx, eax
0x14028596c  mov     dword ptr [rsp+78h+Sid], r13d
0x140285971  mov     edx, ebx
0x140285973  lea     ecx, [r13+3Fh]
0x140285977  mov     r8d, 67737352h
0x14028597d  call    cs:__imp_ExAllocatePool3
0x140285984  nop     dword ptr [rax+rax+00h]
0x140285989  mov     cs:RssHashDacl, rax
0x140285990  test    rax, rax
0x140285993  jnz     short loc_14028599F
0x140285995  mov     ebx, 0C000009Ah
0x14028599a  jmp     loc_140285AC3
0x14028599f  mov     r13d, 2
0x1402859a5  mov     edx, ebx; AclLength
0x1402859a7  mov     r8d, r13d; AclRevision
0x1402859aa  mov     rcx, rax; Acl
0x1402859ad  call    cs:__imp_RtlCreateAcl
0x1402859b4  nop     dword ptr [rax+rax+00h]
0x1402859b9  mov     ebx, eax
0x1402859bb  test    eax, eax
0x1402859bd  js      loc_140285AC3
0x1402859c3  mov     rcx, cs:RssHashDacl; Acl
0x1402859ca  lea     r8d, [r13+1]; AceFlags
0x1402859ce  mov     [rsp+78h+Sid], rsi; Sid
0x1402859d3  mov     edx, r13d; AceRevision
0x1402859d6  mov     esi, 0F003Fh
0x1402859db  mov     r9d, esi; AccessMask
0x1402859de  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1402859e5  nop     dword ptr [rax+rax+00h]
0x1402859ea  mov     ebx, eax
0x1402859ec  test    eax, eax
0x1402859ee  js      loc_140285AC3
0x1402859f4  mov     rcx, cs:RssHashDacl; Acl
0x1402859fb  mov     r9d, esi; AccessMask
0x1402859fe  mov     [rsp+78h+Sid], rbp; Sid
0x140285a03  mov     edx, r13d; AceRevision
0x140285a06  lea     ebp, [r13+1]
0x140285a0a  mov     r8d, ebp; AceFlags
0x140285a0d  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140285a14  nop     dword ptr [rax+rax+00h]
0x140285a19  mov     ebx, eax
0x140285a1b  test    eax, eax
0x140285a1d  js      loc_140285AC3
0x140285a23  mov     rcx, cs:RssHashDacl; Acl
0x140285a2a  mov     r9d, esi; AccessMask
0x140285a2d  mov     r8d, ebp; AceFlags
0x140285a30  mov     [rsp+78h+Sid], r14; Sid
0x140285a35  mov     edx, r13d; AceRevision
0x140285a38  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140285a3f  nop     dword ptr [rax+rax+00h]
0x140285a44  mov     ebx, eax
0x140285a46  test    eax, eax
0x140285a48  js      short loc_140285AC3
0x140285a4a  mov     rcx, cs:RssHashDacl; Acl
0x140285a51  mov     r9d, esi; AccessMask
0x140285a54  mov     r8d, ebp; AceFlags
0x140285a57  mov     [rsp+78h+Sid], r15; Sid
0x140285a5c  mov     edx, r13d; AceRevision
0x140285a5f  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140285a66  nop     dword ptr [rax+rax+00h]
0x140285a6b  mov     ebx, eax
0x140285a6d  test    eax, eax
0x140285a6f  js      short loc_140285AC3
0x140285a71  mov     r8, cs:RssHashDacl; Dacl
0x140285a78  lea     rbx, RssHashSecurityDescriptor
0x140285a7f  mov     rcx, rbx; SecurityDescriptor
0x140285a82  xor     r9d, r9d; DaclDefaulted
0x140285a85  mov     dl, 1; DaclPresent
0x140285a87  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140285a8e  nop     dword ptr [rax+rax+00h]
0x140285a93  xor     r8d, r8d; OwnerDefaulted
0x140285a96  mov     rdx, rdi; Owner
0x140285a99  mov     rcx, rbx; SecurityDescriptor
0x140285a9c  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140285aa3  nop     dword ptr [rax+rax+00h]
0x140285aa8  xor     r8d, r8d; GroupDefaulted
0x140285aab  mov     rdx, rdi; Group
0x140285aae  mov     rcx, rbx; SecurityDescriptor
0x140285ab1  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140285ab8  nop     dword ptr [rax+rax+00h]
0x140285abd  mov     ebx, eax
0x140285abf  test    eax, eax
0x140285ac1  jns     short loc_140285AD2
0x140285ac3  cmp     cs:RssHashDacl, 0
0x140285acb  jz      short loc_140285AD2
0x140285acd  call    RssDestroyHashSecurityDescriptor
0x140285ad2  mov     eax, ebx
0x140285ad4  add     rsp, 40h
0x140285ad8  pop     r15
0x140285ada  pop     r14
0x140285adc  pop     r13
0x140285ade  pop     rdi
0x140285adf  pop     rsi
0x140285ae0  pop     rbp
0x140285ae1  pop     rbx
0x140285ae2  retn
```
