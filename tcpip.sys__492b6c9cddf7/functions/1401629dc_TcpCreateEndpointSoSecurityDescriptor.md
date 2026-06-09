# TcpCreateEndpointSoSecurityDescriptor

- ea: `0x1401629dc`
- end: `0x140162be1`
- name: `TcpCreateEndpointSoSecurityDescriptor`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140162e60`

## callees

- `0x1401629dc`
- `0x140162be8`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140162bba`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140162bba`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162b16`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162b43`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162b6c`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162b95`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162b16`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162b43`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162b6c`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140162b95`
- `ntoskrnl!RtlCreateAcl` at `0x140162ae4`
- `ntoskrnl!RtlCreateAcl` at `0x140162ae4`
- `ntoskrnl!RtlLengthSid` at `0x140162a4b`
- `ntoskrnl!RtlLengthSid` at `0x140162a5c`
- `ntoskrnl!RtlLengthSid` at `0x140162a6d`
- `ntoskrnl!RtlLengthSid` at `0x140162a7e`
- `ntoskrnl!RtlLengthSid` at `0x140162a4b`
- `ntoskrnl!RtlLengthSid` at `0x140162a5c`
- `ntoskrnl!RtlLengthSid` at `0x140162a6d`
- `ntoskrnl!RtlLengthSid` at `0x140162a7e`
- `ntoskrnl!SeExports` at `0x140162a22`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140162a0c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140162a0c`
- `ntoskrnl!ExAllocatePool3` at `0x140162ab4`
- `ntoskrnl!ExAllocatePool3` at `0x140162ab4`

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
  SecurityDescriptor = RtlCreateSecurityDescriptor(TcpEndpointSoSecurityDescriptor, 1u);
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
  SecurityDescriptor = RtlSetDaclSecurityDescriptor(TcpEndpointSoSecurityDescriptor, 1u, TcpEndpointSoDacl, 0);
  if ( SecurityDescriptor < 0 )
    goto LABEL_10;
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x1401629dc  push    rbx
0x1401629de  push    rbp
0x1401629df  push    rsi
0x1401629e0  push    rdi
0x1401629e1  push    r12
0x1401629e3  push    r14
0x1401629e5  sub     rsp, 48h
0x1401629e9  xorps   xmm0, xmm0
0x1401629ec  mov     cs:TcpEndpointSoDacl, 0
0x1401629f7  mov     r12d, 1
0x1401629fd  lea     rcx, TcpEndpointSoSecurityDescriptor; SecurityDescriptor
0x140162a04  mov     edx, r12d; Revision
0x140162a07  movups  [rsp+78h+var_48], xmm0
0x140162a0c  call    cs:__imp_RtlCreateSecurityDescriptor
0x140162a13  nop     dword ptr [rax+rax+00h]
0x140162a18  mov     ebx, eax
0x140162a1a  test    eax, eax
0x140162a1c  js      loc_140162BCC
0x140162a22  mov     rax, cs:__imp_SeExports
0x140162a29  mov     rcx, [rax]
0x140162a2c  mov     r14, [rcx+180h]
0x140162a33  mov     rdi, [rcx+110h]
0x140162a3a  mov     rsi, [rcx+108h]
0x140162a41  mov     rbp, [rcx+188h]
0x140162a48  mov     rcx, r14; Sid
0x140162a4b  call    cs:__imp_RtlLengthSid
0x140162a52  nop     dword ptr [rax+rax+00h]
0x140162a57  mov     rcx, rbp; Sid
0x140162a5a  mov     ebx, eax
0x140162a5c  call    cs:__imp_RtlLengthSid
0x140162a63  nop     dword ptr [rax+rax+00h]
0x140162a68  mov     rcx, rsi; Sid
0x140162a6b  add     ebx, eax
0x140162a6d  call    cs:__imp_RtlLengthSid
0x140162a74  nop     dword ptr [rax+rax+00h]
0x140162a79  mov     rcx, rdi; Sid
0x140162a7c  add     ebx, eax
0x140162a7e  call    cs:__imp_RtlLengthSid
0x140162a85  nop     dword ptr [rax+rax+00h]
0x140162a8a  lea     r9, [rsp+78h+var_48]
0x140162a8f  mov     qword ptr [rsp+78h+var_48+8], 0
0x140162a98  add     eax, 28h ; '('
0x140162a9b  mov     qword ptr [rsp+78h+var_48], r12
0x140162aa0  add     ebx, eax
0x140162aa2  mov     dword ptr [rsp+78h+Sid], r12d
0x140162aa7  mov     edx, ebx
0x140162aa9  lea     ecx, [r12+3Fh]
0x140162aae  mov     r8d, 45706354h
0x140162ab4  call    cs:__imp_ExAllocatePool3
0x140162abb  nop     dword ptr [rax+rax+00h]
0x140162ac0  mov     cs:TcpEndpointSoDacl, rax
0x140162ac7  test    rax, rax
0x140162aca  jnz     short loc_140162AD6
0x140162acc  mov     ebx, 0C000009Ah
0x140162ad1  jmp     loc_140162BCC
0x140162ad6  mov     r12d, 2
0x140162adc  mov     edx, ebx; AclLength
0x140162ade  mov     r8d, r12d; AclRevision
0x140162ae1  mov     rcx, rax; Acl
0x140162ae4  call    cs:__imp_RtlCreateAcl
0x140162aeb  nop     dword ptr [rax+rax+00h]
0x140162af0  mov     ebx, eax
0x140162af2  test    eax, eax
0x140162af4  js      loc_140162BCC
0x140162afa  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x140162b01  lea     r8d, [r12+1]; AceFlags
0x140162b06  mov     [rsp+78h+Sid], rdi; Sid
0x140162b0b  mov     edx, r12d; AceRevision
0x140162b0e  mov     edi, 0F003Fh
0x140162b13  mov     r9d, edi; AccessMask
0x140162b16  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140162b1d  nop     dword ptr [rax+rax+00h]
0x140162b22  mov     ebx, eax
0x140162b24  test    eax, eax
0x140162b26  js      loc_140162BCC
0x140162b2c  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x140162b33  lea     r8d, [r12+1]; AceFlags
0x140162b38  mov     r9d, edi; AccessMask
0x140162b3b  mov     [rsp+78h+Sid], rsi; Sid
0x140162b40  mov     edx, r12d; AceRevision
0x140162b43  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140162b4a  nop     dword ptr [rax+rax+00h]
0x140162b4f  mov     ebx, eax
0x140162b51  test    eax, eax
0x140162b53  js      short loc_140162BCC
0x140162b55  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x140162b5c  lea     r8d, [r12+1]; AceFlags
0x140162b61  mov     r9d, edi; AccessMask
0x140162b64  mov     [rsp+78h+Sid], rbp; Sid
0x140162b69  mov     edx, r12d; AceRevision
0x140162b6c  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140162b73  nop     dword ptr [rax+rax+00h]
0x140162b78  mov     ebx, eax
0x140162b7a  test    eax, eax
0x140162b7c  js      short loc_140162BCC
0x140162b7e  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x140162b85  lea     r8d, [r12+1]; AceFlags
0x140162b8a  mov     r9d, edi; AccessMask
0x140162b8d  mov     [rsp+78h+Sid], r14; Sid
0x140162b92  mov     edx, r12d; AceRevision
0x140162b95  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140162b9c  nop     dword ptr [rax+rax+00h]
0x140162ba1  mov     ebx, eax
0x140162ba3  test    eax, eax
0x140162ba5  js      short loc_140162BCC
0x140162ba7  mov     r8, cs:TcpEndpointSoDacl; Dacl
0x140162bae  lea     rcx, TcpEndpointSoSecurityDescriptor; SecurityDescriptor
0x140162bb5  xor     r9d, r9d; DaclDefaulted
0x140162bb8  mov     dl, 1; DaclPresent
0x140162bba  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140162bc1  nop     dword ptr [rax+rax+00h]
0x140162bc6  mov     ebx, eax
0x140162bc8  test    eax, eax
0x140162bca  jns     short loc_140162BD1
0x140162bcc  call    TcpDestroyEndpointSoSecurityDescriptor
0x140162bd1  mov     eax, ebx
0x140162bd3  add     rsp, 48h
0x140162bd7  pop     r14
0x140162bd9  pop     r12
0x140162bdb  pop     rdi
0x140162bdc  pop     rsi
0x140162bdd  pop     rbp
0x140162bde  pop     rbx
0x140162bdf  retn
```
