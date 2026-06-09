# RssCreateHashSecurityDescriptor

- ea: `0x1402818d8`
- end: `0x140281b14`
- name: `RssCreateHashSecurityDescriptor`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140281b20`

## callees

- `0x14025734c`
- `0x1402818d8`

## import_xrefs

- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140281ae1`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140281ae1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140281ab7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140281ab7`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140281a0e`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140281a3d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140281a68`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140281a8f`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140281a0e`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140281a3d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140281a68`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140281a8f`
- `ntoskrnl!RtlCreateAcl` at `0x1402819dd`
- `ntoskrnl!RtlCreateAcl` at `0x1402819dd`
- `ntoskrnl!RtlLengthSid` at `0x140281945`
- `ntoskrnl!RtlLengthSid` at `0x140281956`
- `ntoskrnl!RtlLengthSid` at `0x140281967`
- `ntoskrnl!RtlLengthSid` at `0x140281978`
- `ntoskrnl!RtlLengthSid` at `0x140281945`
- `ntoskrnl!RtlLengthSid` at `0x140281956`
- `ntoskrnl!RtlLengthSid` at `0x140281967`
- `ntoskrnl!RtlLengthSid` at `0x140281978`
- `ntoskrnl!SeExports` at `0x140281915`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402818ff`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402818ff`
- `ntoskrnl!ExAllocatePool3` at `0x1402819ad`
- `ntoskrnl!ExAllocatePool3` at `0x1402819ad`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140281acc`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140281acc`

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
  SecurityDescriptor = RtlCreateSecurityDescriptor(&RssHashSecurityDescriptor, 1u);
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
                RtlSetDaclSecurityDescriptor(&RssHashSecurityDescriptor, 1u, (PACL)RssHashDacl, 0);
                RtlSetOwnerSecurityDescriptor(&RssHashSecurityDescriptor, SeNullSid, 0);
                SecurityDescriptor = RtlSetGroupSecurityDescriptor(&RssHashSecurityDescriptor, SeNullSid, 0);
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
0x1402818d8  push    rbx
0x1402818da  push    rbp
0x1402818db  push    rsi
0x1402818dc  push    rdi
0x1402818dd  push    r13
0x1402818df  push    r14
0x1402818e1  push    r15
0x1402818e3  sub     rsp, 40h
0x1402818e7  xorps   xmm0, xmm0
0x1402818ea  lea     rcx, RssHashSecurityDescriptor; SecurityDescriptor
0x1402818f1  mov     r13d, 1
0x1402818f7  mov     edx, r13d; Revision
0x1402818fa  movups  [rsp+78h+var_48], xmm0
0x1402818ff  call    cs:__imp_RtlCreateSecurityDescriptor
0x140281906  nop     dword ptr [rax+rax+00h]
0x14028190b  mov     ebx, eax
0x14028190d  test    eax, eax
0x14028190f  js      loc_140281AF3
0x140281915  mov     rax, cs:__imp_SeExports
0x14028191c  mov     rcx, [rax]
0x14028191f  mov     r15, [rcx+180h]
0x140281926  mov     rsi, [rcx+110h]
0x14028192d  mov     rbp, [rcx+108h]
0x140281934  mov     r14, [rcx+188h]
0x14028193b  mov     rdi, [rcx+0B8h]
0x140281942  mov     rcx, r15; Sid
0x140281945  call    cs:__imp_RtlLengthSid
0x14028194c  nop     dword ptr [rax+rax+00h]
0x140281951  mov     rcx, r14; Sid
0x140281954  mov     ebx, eax
0x140281956  call    cs:__imp_RtlLengthSid
0x14028195d  nop     dword ptr [rax+rax+00h]
0x140281962  mov     rcx, rbp; Sid
0x140281965  add     ebx, eax
0x140281967  call    cs:__imp_RtlLengthSid
0x14028196e  nop     dword ptr [rax+rax+00h]
0x140281973  mov     rcx, rsi; Sid
0x140281976  add     ebx, eax
0x140281978  call    cs:__imp_RtlLengthSid
0x14028197f  nop     dword ptr [rax+rax+00h]
0x140281984  lea     r9, [rsp+78h+var_48]
0x140281989  mov     qword ptr [rsp+78h+var_48+8], 0
0x140281992  add     eax, 28h ; '('
0x140281995  mov     qword ptr [rsp+78h+var_48], r13
0x14028199a  add     ebx, eax
0x14028199c  mov     dword ptr [rsp+78h+Sid], r13d
0x1402819a1  mov     edx, ebx
0x1402819a3  lea     ecx, [r13+3Fh]
0x1402819a7  mov     r8d, 67737352h
0x1402819ad  call    cs:__imp_ExAllocatePool3
0x1402819b4  nop     dword ptr [rax+rax+00h]
0x1402819b9  mov     cs:RssHashDacl, rax
0x1402819c0  test    rax, rax
0x1402819c3  jnz     short loc_1402819CF
0x1402819c5  mov     ebx, 0C000009Ah
0x1402819ca  jmp     loc_140281AF3
0x1402819cf  mov     r13d, 2
0x1402819d5  mov     edx, ebx; AclLength
0x1402819d7  mov     r8d, r13d; AclRevision
0x1402819da  mov     rcx, rax; Acl
0x1402819dd  call    cs:__imp_RtlCreateAcl
0x1402819e4  nop     dword ptr [rax+rax+00h]
0x1402819e9  mov     ebx, eax
0x1402819eb  test    eax, eax
0x1402819ed  js      loc_140281AF3
0x1402819f3  mov     rcx, cs:RssHashDacl; Acl
0x1402819fa  lea     r8d, [r13+1]; AceFlags
0x1402819fe  mov     [rsp+78h+Sid], rsi; Sid
0x140281a03  mov     edx, r13d; AceRevision
0x140281a06  mov     esi, 0F003Fh
0x140281a0b  mov     r9d, esi; AccessMask
0x140281a0e  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140281a15  nop     dword ptr [rax+rax+00h]
0x140281a1a  mov     ebx, eax
0x140281a1c  test    eax, eax
0x140281a1e  js      loc_140281AF3
0x140281a24  mov     rcx, cs:RssHashDacl; Acl
0x140281a2b  mov     r9d, esi; AccessMask
0x140281a2e  mov     [rsp+78h+Sid], rbp; Sid
0x140281a33  mov     edx, r13d; AceRevision
0x140281a36  lea     ebp, [r13+1]
0x140281a3a  mov     r8d, ebp; AceFlags
0x140281a3d  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140281a44  nop     dword ptr [rax+rax+00h]
0x140281a49  mov     ebx, eax
0x140281a4b  test    eax, eax
0x140281a4d  js      loc_140281AF3
0x140281a53  mov     rcx, cs:RssHashDacl; Acl
0x140281a5a  mov     r9d, esi; AccessMask
0x140281a5d  mov     r8d, ebp; AceFlags
0x140281a60  mov     [rsp+78h+Sid], r14; Sid
0x140281a65  mov     edx, r13d; AceRevision
0x140281a68  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140281a6f  nop     dword ptr [rax+rax+00h]
0x140281a74  mov     ebx, eax
0x140281a76  test    eax, eax
0x140281a78  js      short loc_140281AF3
0x140281a7a  mov     rcx, cs:RssHashDacl; Acl
0x140281a81  mov     r9d, esi; AccessMask
0x140281a84  mov     r8d, ebp; AceFlags
0x140281a87  mov     [rsp+78h+Sid], r15; Sid
0x140281a8c  mov     edx, r13d; AceRevision
0x140281a8f  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140281a96  nop     dword ptr [rax+rax+00h]
0x140281a9b  mov     ebx, eax
0x140281a9d  test    eax, eax
0x140281a9f  js      short loc_140281AF3
0x140281aa1  mov     r8, cs:RssHashDacl; Dacl
0x140281aa8  lea     rbx, RssHashSecurityDescriptor
0x140281aaf  mov     rcx, rbx; SecurityDescriptor
0x140281ab2  xor     r9d, r9d; DaclDefaulted
0x140281ab5  mov     dl, 1; DaclPresent
0x140281ab7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140281abe  nop     dword ptr [rax+rax+00h]
0x140281ac3  xor     r8d, r8d; OwnerDefaulted
0x140281ac6  mov     rdx, rdi; Owner
0x140281ac9  mov     rcx, rbx; SecurityDescriptor
0x140281acc  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140281ad3  nop     dword ptr [rax+rax+00h]
0x140281ad8  xor     r8d, r8d; GroupDefaulted
0x140281adb  mov     rdx, rdi; Group
0x140281ade  mov     rcx, rbx; SecurityDescriptor
0x140281ae1  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140281ae8  nop     dword ptr [rax+rax+00h]
0x140281aed  mov     ebx, eax
0x140281aef  test    eax, eax
0x140281af1  jns     short loc_140281B02
0x140281af3  cmp     cs:RssHashDacl, 0
0x140281afb  jz      short loc_140281B02
0x140281afd  call    RssDestroyHashSecurityDescriptor
0x140281b02  mov     eax, ebx
0x140281b04  add     rsp, 40h
0x140281b08  pop     r15
0x140281b0a  pop     r14
0x140281b0c  pop     r13
0x140281b0e  pop     rdi
0x140281b0f  pop     rsi
0x140281b10  pop     rbp
0x140281b11  pop     rbx
0x140281b12  retn
```
