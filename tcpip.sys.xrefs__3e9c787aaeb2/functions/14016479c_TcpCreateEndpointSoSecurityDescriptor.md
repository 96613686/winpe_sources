# TcpCreateEndpointSoSecurityDescriptor

- ea: `0x14016479c`
- end: `0x1401649a1`
- name: `TcpCreateEndpointSoSecurityDescriptor`
- size: `517`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140164c20`

## callees

- `0x14016479c`
- `0x1401649a8`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14016497a`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14016497a`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401648d6`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140164903`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016492c`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140164955`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401648d6`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140164903`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016492c`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140164955`
- `ntoskrnl!RtlCreateAcl` at `0x1401648a4`
- `ntoskrnl!RtlCreateAcl` at `0x1401648a4`
- `ntoskrnl!RtlLengthSid` at `0x14016480b`
- `ntoskrnl!RtlLengthSid` at `0x14016481c`
- `ntoskrnl!RtlLengthSid` at `0x14016482d`
- `ntoskrnl!RtlLengthSid` at `0x14016483e`
- `ntoskrnl!RtlLengthSid` at `0x14016480b`
- `ntoskrnl!RtlLengthSid` at `0x14016481c`
- `ntoskrnl!RtlLengthSid` at `0x14016482d`
- `ntoskrnl!RtlLengthSid` at `0x14016483e`
- `ntoskrnl!SeExports` at `0x1401647e2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401647cc`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401647cc`
- `ntoskrnl!ExAllocatePool3` at `0x140164874`
- `ntoskrnl!ExAllocatePool3` at `0x140164874`

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
0x14016479c  push    rbx
0x14016479e  push    rbp
0x14016479f  push    rsi
0x1401647a0  push    rdi
0x1401647a1  push    r12
0x1401647a3  push    r14
0x1401647a5  sub     rsp, 48h
0x1401647a9  xorps   xmm0, xmm0
0x1401647ac  mov     cs:TcpEndpointSoDacl, 0
0x1401647b7  mov     r12d, 1
0x1401647bd  lea     rcx, TcpEndpointSoSecurityDescriptor; SecurityDescriptor
0x1401647c4  mov     edx, r12d; Revision
0x1401647c7  movups  [rsp+78h+var_48], xmm0
0x1401647cc  call    cs:__imp_RtlCreateSecurityDescriptor
0x1401647d3  nop     dword ptr [rax+rax+00h]
0x1401647d8  mov     ebx, eax
0x1401647da  test    eax, eax
0x1401647dc  js      loc_14016498C
0x1401647e2  mov     rax, cs:__imp_SeExports
0x1401647e9  mov     rcx, [rax]
0x1401647ec  mov     r14, [rcx+180h]
0x1401647f3  mov     rdi, [rcx+110h]
0x1401647fa  mov     rsi, [rcx+108h]
0x140164801  mov     rbp, [rcx+188h]
0x140164808  mov     rcx, r14; Sid
0x14016480b  call    cs:__imp_RtlLengthSid
0x140164812  nop     dword ptr [rax+rax+00h]
0x140164817  mov     rcx, rbp; Sid
0x14016481a  mov     ebx, eax
0x14016481c  call    cs:__imp_RtlLengthSid
0x140164823  nop     dword ptr [rax+rax+00h]
0x140164828  mov     rcx, rsi; Sid
0x14016482b  add     ebx, eax
0x14016482d  call    cs:__imp_RtlLengthSid
0x140164834  nop     dword ptr [rax+rax+00h]
0x140164839  mov     rcx, rdi; Sid
0x14016483c  add     ebx, eax
0x14016483e  call    cs:__imp_RtlLengthSid
0x140164845  nop     dword ptr [rax+rax+00h]
0x14016484a  lea     r9, [rsp+78h+var_48]
0x14016484f  mov     qword ptr [rsp+78h+var_48+8], 0
0x140164858  add     eax, 28h ; '('
0x14016485b  mov     qword ptr [rsp+78h+var_48], r12
0x140164860  add     ebx, eax
0x140164862  mov     dword ptr [rsp+78h+Sid], r12d
0x140164867  mov     edx, ebx
0x140164869  lea     ecx, [r12+3Fh]
0x14016486e  mov     r8d, 45706354h
0x140164874  call    cs:__imp_ExAllocatePool3
0x14016487b  nop     dword ptr [rax+rax+00h]
0x140164880  mov     cs:TcpEndpointSoDacl, rax
0x140164887  test    rax, rax
0x14016488a  jnz     short loc_140164896
0x14016488c  mov     ebx, 0C000009Ah
0x140164891  jmp     loc_14016498C
0x140164896  mov     r12d, 2
0x14016489c  mov     edx, ebx; AclLength
0x14016489e  mov     r8d, r12d; AclRevision
0x1401648a1  mov     rcx, rax; Acl
0x1401648a4  call    cs:__imp_RtlCreateAcl
0x1401648ab  nop     dword ptr [rax+rax+00h]
0x1401648b0  mov     ebx, eax
0x1401648b2  test    eax, eax
0x1401648b4  js      loc_14016498C
0x1401648ba  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x1401648c1  lea     r8d, [r12+1]; AceFlags
0x1401648c6  mov     [rsp+78h+Sid], rdi; Sid
0x1401648cb  mov     edx, r12d; AceRevision
0x1401648ce  mov     edi, 0F003Fh
0x1401648d3  mov     r9d, edi; AccessMask
0x1401648d6  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1401648dd  nop     dword ptr [rax+rax+00h]
0x1401648e2  mov     ebx, eax
0x1401648e4  test    eax, eax
0x1401648e6  js      loc_14016498C
0x1401648ec  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x1401648f3  lea     r8d, [r12+1]; AceFlags
0x1401648f8  mov     r9d, edi; AccessMask
0x1401648fb  mov     [rsp+78h+Sid], rsi; Sid
0x140164900  mov     edx, r12d; AceRevision
0x140164903  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14016490a  nop     dword ptr [rax+rax+00h]
0x14016490f  mov     ebx, eax
0x140164911  test    eax, eax
0x140164913  js      short loc_14016498C
0x140164915  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x14016491c  lea     r8d, [r12+1]; AceFlags
0x140164921  mov     r9d, edi; AccessMask
0x140164924  mov     [rsp+78h+Sid], rbp; Sid
0x140164929  mov     edx, r12d; AceRevision
0x14016492c  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140164933  nop     dword ptr [rax+rax+00h]
0x140164938  mov     ebx, eax
0x14016493a  test    eax, eax
0x14016493c  js      short loc_14016498C
0x14016493e  mov     rcx, cs:TcpEndpointSoDacl; Acl
0x140164945  lea     r8d, [r12+1]; AceFlags
0x14016494a  mov     r9d, edi; AccessMask
0x14016494d  mov     [rsp+78h+Sid], r14; Sid
0x140164952  mov     edx, r12d; AceRevision
0x140164955  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14016495c  nop     dword ptr [rax+rax+00h]
0x140164961  mov     ebx, eax
0x140164963  test    eax, eax
0x140164965  js      short loc_14016498C
0x140164967  mov     r8, cs:TcpEndpointSoDacl; Dacl
0x14016496e  lea     rcx, TcpEndpointSoSecurityDescriptor; SecurityDescriptor
0x140164975  xor     r9d, r9d; DaclDefaulted
0x140164978  mov     dl, 1; DaclPresent
0x14016497a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140164981  nop     dword ptr [rax+rax+00h]
0x140164986  mov     ebx, eax
0x140164988  test    eax, eax
0x14016498a  jns     short loc_140164991
0x14016498c  call    TcpDestroyEndpointSoSecurityDescriptor
0x140164991  mov     eax, ebx
0x140164993  add     rsp, 48h
0x140164997  pop     r14
0x140164999  pop     r12
0x14016499b  pop     rdi
0x14016499c  pop     rsi
0x14016499d  pop     rbp
0x14016499e  pop     rbx
0x14016499f  retn
```
