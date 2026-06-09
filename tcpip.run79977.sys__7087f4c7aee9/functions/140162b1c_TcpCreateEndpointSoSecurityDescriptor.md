# TcpCreateEndpointSoSecurityDescriptor

- ea: `0x140162b1c`
- end: `0x140162d21`
- name: `TcpCreateEndpointSoSecurityDescriptor`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140162fa0`

## callees

- `0x140162b1c`
- `0x140162d28`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140162cfa`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140162cfa`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162c56`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162c83`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162cac`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162cd5`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162c56`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162c83`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162cac`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162cd5`
- `ntoskrnl!RtlCreateAcl` at `0x140162c24`
- `ntoskrnl!RtlCreateAcl` at `0x140162c24`
- `ntoskrnl!RtlLengthSid` at `0x140162b8b`
- `ntoskrnl!RtlLengthSid` at `0x140162b9c`
- `ntoskrnl!RtlLengthSid` at `0x140162bad`
- `ntoskrnl!RtlLengthSid` at `0x140162bbe`
- `ntoskrnl!RtlLengthSid` at `0x140162b8b`
- `ntoskrnl!RtlLengthSid` at `0x140162b9c`
- `ntoskrnl!RtlLengthSid` at `0x140162bad`
- `ntoskrnl!RtlLengthSid` at `0x140162bbe`
- `ntoskrnl!SeExports` at `0x140162b62`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140162b4c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140162b4c`
- `ntoskrnl!ExAllocatePool3` at `0x140162bf4`
- `ntoskrnl!ExAllocatePool3` at `0x140162bf4`

## pseudocode

```c
__int64 TcpCreateEndpointSoSecurityDescriptor()
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

  TcpEndpointSoDacl = 0;
  v11[0] = 0;
  SecurityDescriptor = RtlCreateSecurityDescriptor(&TcpEndpointSoSecurityDescriptor, 1u);
  if ( SecurityDescriptor < 0 )
    goto LABEL_10;
  SeLocalServiceSid = SeExports->SeLocalServiceSid;
  Sid = SeExports->SeAliasAdminsSid;
  SeLocalSystemSid = SeExports->SeLocalSystemSid;
  SeNetworkServiceSid = SeExports->SeNetworkServiceSid;
  v5 = RtlLengthSid(SeLocalServiceSid);
  v6 = RtlLengthSid(SeNetworkServiceSid) + v5;
  v7 = RtlLengthSid(SeLocalSystemSid) + v6;
  v11[0] = 1u;
  v8 = RtlLengthSid(Sid) + 40 + v7;
  Pool3 = (struct _ACL *)ExAllocatePool3(64, v8, 1164993364, v11, 1);
  TcpEndpointSoDacl = Pool3;
  if ( !Pool3 )
  {
    SecurityDescriptor = -1073741670;
LABEL_10:
    TcpDestroyEndpointSoSecurityDescriptor();
    return (unsigned int)SecurityDescriptor;
  }
  SecurityDescriptor = RtlCreateAcl(Pool3, v8, 2u);
  if ( SecurityDescriptor < 0 )
    goto LABEL_10;
  SecurityDescriptor = RtlAddAccessAllowedAceEx(TcpEndpointSoDacl, 2u, 3u, 0xF003Fu, Sid);
  if ( SecurityDescriptor < 0 )
    goto LABEL_10;
  SecurityDescriptor = RtlAddAccessAllowedAceEx(TcpEndpointSoDacl, 2u, 3u, 0xF003Fu, SeLocalSystemSid);
  if ( SecurityDescriptor < 0 )
    goto LABEL_10;
  SecurityDescriptor = RtlAddAccessAllowedAceEx(TcpEndpointSoDacl, 2u, 3u, 0xF003Fu, SeNetworkServiceSid);
  if ( SecurityDescriptor < 0 )
    goto LABEL_10;
  SecurityDescriptor = RtlAddAccessAllowedAceEx(TcpEndpointSoDacl, 2u, 3u, 0xF003Fu, SeLocalServiceSid);
  if ( SecurityDescriptor < 0 )
    goto LABEL_10;
  SecurityDescriptor = RtlSetDaclSecurityDescriptor(&TcpEndpointSoSecurityDescriptor, 1u, TcpEndpointSoDacl, 0);
  if ( SecurityDescriptor < 0 )
    goto LABEL_10;
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x140162b1c  push    rbx
0x140162b1e  push    rbp
0x140162b1f  push    rsi
0x140162b20  push    rdi
0x140162b21  push    r12
0x140162b23  push    r14
0x140162b25  sub     rsp, 48h
0x140162b29  xorps   xmm0, xmm0
0x140162b2c  mov     cs:TcpEndpointSoDacl, 0
0x140162b37  mov     r12d, 1
0x140162b3d  lea     rcx, TcpEndpointSoSecurityDescriptor; SecurityDescriptor
0x140162b44  mov     edx, r12d; Revision
0x140162b47  movups  [rsp+78h+var_48], xmm0
0x140162b4c  call    cs:__imp_RtlCreateSecurityDescriptor
0x140162b53  nop     dword ptr [rax+rax+00h]
0x140162b58  mov     ebx, eax
0x140162b5a  test    eax, eax
0x140162b5c  js      loc_140162D0C
0x140162b62  mov     rax, cs:__imp_SeExports
0x140162b69  mov     rcx, [rax]
0x140162b6c  mov     r14, [rcx+180h]
0x140162b73  mov     rdi, [rcx+110h]
0x140162b7a  mov     rsi, [rcx+108h]
0x140162b81  mov     rbp, [rcx+188h]
0x140162b88  mov     rcx, r14; Sid
0x140162b8b  call    cs:__imp_RtlLengthSid
0x140162b92  nop     dword ptr [rax+rax+00h]
0x140162b97  mov     rcx, rbp; Sid
0x140162b9a  mov     ebx, eax
0x140162b9c  call    cs:__imp_RtlLengthSid
0x140162ba3  nop     dword ptr [rax+rax+00h]
0x140162ba8  mov     rcx, rsi; Sid
0x140162bab  add     ebx, eax
0x140162bad  call    cs:__imp_RtlLengthSid
0x140162bb4  nop     dword ptr [rax+rax+00h]
0x140162bb9  mov     rcx, rdi; Sid
0x140162bbc  add     ebx, eax
0x140162bbe  call    cs:__imp_RtlLengthSid
0x140162bc5  nop     dword ptr [rax+rax+00h]
0x140162bca  lea     r9, [rsp+78h+var_48]
0x140162bcf  mov     qword ptr [rsp+78h+var_48+8], 0
0x140162bd8  add     eax, 28h ; '('
0x140162bdb  mov     qword ptr [rsp+78h+var_48], r12
0x140162be0  add     ebx, eax
0x140162be2  mov     dword ptr [rsp+78h+Sid], r12d
0x140162be7  mov     edx, ebx
0x140162be9  lea     ecx, [r12+3Fh]
0x140162bee  mov     r8d, 45706354h
0x140162bf4  call    cs:__imp_ExAllocatePool3
0x140162bfb  nop     dword ptr [rax+rax+00h]
0x140162c00  mov     cs:TcpEndpointSoDacl, rax
0x140162c07  test    rax, rax
0x140162c0a  jnz     short loc_140162C16
0x140162c0c  mov     ebx, 0C000009Ah
0x140162c11  jmp     loc_140162D0C
0x140162c16  mov     r12d, 2
0x140162c1c  mov     edx, ebx; AclLength
0x140162c1e  mov     r8d, r12d; AclRevision
0x140162c21  mov     rcx, rax; Acl
0x140162c24  call    cs:__imp_RtlCreateAcl
0x140162c2b  nop     dword ptr [rax+rax+00h]
0x140162c30  mov     ebx, eax
0x140162c32  test    eax, eax
0x140162c34  js      loc_140162D0C
0x140162c3a  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x140162c41  lea     r8d, [r12+1]; AceFlags
0x140162c46  mov     [rsp+78h+Sid], rdi; Sid
0x140162c4b  mov     edx, r12d; AceRevision
0x140162c4e  mov     edi, 0F003Fh
0x140162c53  mov     r9d, edi; AccessMask
0x140162c56  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140162c5d  nop     dword ptr [rax+rax+00h]
0x140162c62  mov     ebx, eax
0x140162c64  test    eax, eax
0x140162c66  js      loc_140162D0C
0x140162c6c  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x140162c73  lea     r8d, [r12+1]; AceFlags
0x140162c78  mov     r9d, edi; AccessMask
0x140162c7b  mov     [rsp+78h+Sid], rsi; Sid
0x140162c80  mov     edx, r12d; AceRevision
0x140162c83  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140162c8a  nop     dword ptr [rax+rax+00h]
0x140162c8f  mov     ebx, eax
0x140162c91  test    eax, eax
0x140162c93  js      short loc_140162D0C
0x140162c95  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x140162c9c  lea     r8d, [r12+1]; AceFlags
0x140162ca1  mov     r9d, edi; AccessMask
0x140162ca4  mov     [rsp+78h+Sid], rbp; Sid
0x140162ca9  mov     edx, r12d; AceRevision
0x140162cac  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140162cb3  nop     dword ptr [rax+rax+00h]
0x140162cb8  mov     ebx, eax
0x140162cba  test    eax, eax
0x140162cbc  js      short loc_140162D0C
0x140162cbe  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x140162cc5  lea     r8d, [r12+1]; AceFlags
0x140162cca  mov     r9d, edi; AccessMask
0x140162ccd  mov     [rsp+78h+Sid], r14; Sid
0x140162cd2  mov     edx, r12d; AceRevision
0x140162cd5  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140162cdc  nop     dword ptr [rax+rax+00h]
0x140162ce1  mov     ebx, eax
0x140162ce3  test    eax, eax
0x140162ce5  js      short loc_140162D0C
0x140162ce7  mov     r8, cs:TcpEndpointSoDacl; Dacl
0x140162cee  lea     rcx, TcpEndpointSoSecurityDescriptor; SecurityDescriptor
0x140162cf5  xor     r9d, r9d; DaclDefaulted
0x140162cf8  mov     dl, 1; DaclPresent
0x140162cfa  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140162d01  nop     dword ptr [rax+rax+00h]
0x140162d06  mov     ebx, eax
0x140162d08  test    eax, eax
0x140162d0a  jns     short loc_140162D11
0x140162d0c  call    TcpDestroyEndpointSoSecurityDescriptor
0x140162d11  mov     eax, ebx
0x140162d13  add     rsp, 48h
0x140162d17  pop     r14
0x140162d19  pop     r12
0x140162d1b  pop     rdi
0x140162d1c  pop     rsi
0x140162d1d  pop     rbp
0x140162d1e  pop     rbx
0x140162d1f  retn
```
