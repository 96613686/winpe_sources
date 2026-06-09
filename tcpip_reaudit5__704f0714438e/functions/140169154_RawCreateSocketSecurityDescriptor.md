# RawCreateSocketSecurityDescriptor

- ea: `0x140169154`
- end: `0x140169371`
- name: `RawCreateSocketSecurityDescriptor`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14014b290`

## callees

- `0x140169154`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140169332`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140169332`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016928e`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401692bb`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401692e4`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016930d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016928e`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401692bb`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401692e4`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016930d`
- `ntoskrnl!RtlCreateAcl` at `0x14016925c`
- `ntoskrnl!RtlCreateAcl` at `0x14016925c`
- `ntoskrnl!RtlLengthSid` at `0x1401691c3`
- `ntoskrnl!RtlLengthSid` at `0x1401691d4`
- `ntoskrnl!RtlLengthSid` at `0x1401691e5`
- `ntoskrnl!RtlLengthSid` at `0x1401691f6`
- `ntoskrnl!RtlLengthSid` at `0x1401691c3`
- `ntoskrnl!RtlLengthSid` at `0x1401691d4`
- `ntoskrnl!RtlLengthSid` at `0x1401691e5`
- `ntoskrnl!RtlLengthSid` at `0x1401691f6`
- `ntoskrnl!SeExports` at `0x14016919a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140169184`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140169184`
- `ntoskrnl!ExAllocatePool3` at `0x14016922c`
- `ntoskrnl!ExAllocatePool3` at `0x14016922c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140169355`
- `ntoskrnl!ExFreePoolWithTag` at `0x140169355`

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
  SecurityDescriptor = RtlCreateSecurityDescriptor(qword_1402246D0, 1u);
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
              SecurityDescriptor = RtlSetDaclSecurityDescriptor(qword_1402246D0, 1u, Dacl, 0);
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
0x140169154  push    rbx
0x140169156  push    rbp
0x140169157  push    rsi
0x140169158  push    rdi
0x140169159  push    r12
0x14016915b  push    r14
0x14016915d  sub     rsp, 48h
0x140169161  xorps   xmm0, xmm0
0x140169164  mov     cs:Dacl, 0
0x14016916f  mov     r12d, 1
0x140169175  lea     rcx, qword_1402246D0; SecurityDescriptor
0x14016917c  mov     edx, r12d; Revision
0x14016917f  movups  [rsp+78h+var_48], xmm0
0x140169184  call    cs:__imp_RtlCreateSecurityDescriptor
0x14016918b  nop     dword ptr [rax+rax+00h]
0x140169190  mov     ebx, eax
0x140169192  test    eax, eax
0x140169194  js      loc_140169344
0x14016919a  mov     rax, cs:__imp_SeExports
0x1401691a1  mov     rcx, [rax]
0x1401691a4  mov     r14, [rcx+180h]
0x1401691ab  mov     rdi, [rcx+110h]
0x1401691b2  mov     rsi, [rcx+108h]
0x1401691b9  mov     rbp, [rcx+188h]
0x1401691c0  mov     rcx, r14; Sid
0x1401691c3  call    cs:__imp_RtlLengthSid
0x1401691ca  nop     dword ptr [rax+rax+00h]
0x1401691cf  mov     rcx, rbp; Sid
0x1401691d2  mov     ebx, eax
0x1401691d4  call    cs:__imp_RtlLengthSid
0x1401691db  nop     dword ptr [rax+rax+00h]
0x1401691e0  mov     rcx, rsi; Sid
0x1401691e3  add     ebx, eax
0x1401691e5  call    cs:__imp_RtlLengthSid
0x1401691ec  nop     dword ptr [rax+rax+00h]
0x1401691f1  mov     rcx, rdi; Sid
0x1401691f4  add     ebx, eax
0x1401691f6  call    cs:__imp_RtlLengthSid
0x1401691fd  nop     dword ptr [rax+rax+00h]
0x140169202  lea     r9, [rsp+78h+var_48]
0x140169207  mov     qword ptr [rsp+78h+var_48+8], 0
0x140169210  add     eax, 28h ; '('
0x140169213  mov     qword ptr [rsp+78h+var_48], r12
0x140169218  add     ebx, eax
0x14016921a  mov     dword ptr [rsp+78h+Sid], r12d
0x14016921f  mov     edx, ebx
0x140169221  lea     ecx, [r12+3Fh]
0x140169226  mov     r8d, 41446152h
0x14016922c  call    cs:__imp_ExAllocatePool3
0x140169233  nop     dword ptr [rax+rax+00h]
0x140169238  mov     cs:Dacl, rax
0x14016923f  test    rax, rax
0x140169242  jnz     short loc_14016924E
0x140169244  mov     ebx, 0C000009Ah
0x140169249  jmp     loc_14016934B
0x14016924e  mov     r12d, 2
0x140169254  mov     edx, ebx; AclLength
0x140169256  mov     r8d, r12d; AclRevision
0x140169259  mov     rcx, rax; Acl
0x14016925c  call    cs:__imp_RtlCreateAcl
0x140169263  nop     dword ptr [rax+rax+00h]
0x140169268  mov     ebx, eax
0x14016926a  test    eax, eax
0x14016926c  js      loc_140169344
0x140169272  mov     rcx, cs:Dacl; Acl
0x140169279  lea     r8d, [r12+1]; AceFlags
0x14016927e  mov     [rsp+78h+Sid], rdi; Sid
0x140169283  mov     edx, r12d; AceRevision
0x140169286  mov     edi, 0F003Fh
0x14016928b  mov     r9d, edi; AccessMask
0x14016928e  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140169295  nop     dword ptr [rax+rax+00h]
0x14016929a  mov     ebx, eax
0x14016929c  test    eax, eax
0x14016929e  js      loc_140169344
0x1401692a4  mov     rcx, cs:Dacl; Acl
0x1401692ab  lea     r8d, [r12+1]; AceFlags
0x1401692b0  mov     r9d, edi; AccessMask
0x1401692b3  mov     [rsp+78h+Sid], rsi; Sid
0x1401692b8  mov     edx, r12d; AceRevision
0x1401692bb  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1401692c2  nop     dword ptr [rax+rax+00h]
0x1401692c7  mov     ebx, eax
0x1401692c9  test    eax, eax
0x1401692cb  js      short loc_140169344
0x1401692cd  mov     rcx, cs:Dacl; Acl
0x1401692d4  lea     r8d, [r12+1]; AceFlags
0x1401692d9  mov     r9d, edi; AccessMask
0x1401692dc  mov     [rsp+78h+Sid], rbp; Sid
0x1401692e1  mov     edx, r12d; AceRevision
0x1401692e4  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1401692eb  nop     dword ptr [rax+rax+00h]
0x1401692f0  mov     ebx, eax
0x1401692f2  test    eax, eax
0x1401692f4  js      short loc_140169344
0x1401692f6  mov     rcx, cs:Dacl; Acl
0x1401692fd  lea     r8d, [r12+1]; AceFlags
0x140169302  mov     r9d, edi; AccessMask
0x140169305  mov     [rsp+78h+Sid], r14; Sid
0x14016930a  mov     edx, r12d; AceRevision
0x14016930d  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140169314  nop     dword ptr [rax+rax+00h]
0x140169319  mov     ebx, eax
0x14016931b  test    eax, eax
0x14016931d  js      short loc_140169344
0x14016931f  mov     r8, cs:Dacl; Dacl
0x140169326  lea     rcx, qword_1402246D0; SecurityDescriptor
0x14016932d  xor     r9d, r9d; DaclDefaulted
0x140169330  mov     dl, 1; DaclPresent
0x140169332  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140169339  nop     dword ptr [rax+rax+00h]
0x14016933e  mov     ebx, eax
0x140169340  test    eax, eax
0x140169342  jns     short loc_140169361
0x140169344  mov     rax, cs:Dacl
0x14016934b  test    rax, rax
0x14016934e  jz      short loc_140169361
0x140169350  xor     edx, edx; Tag
0x140169352  mov     rcx, rax; P
0x140169355  call    cs:__imp_ExFreePoolWithTag
0x14016935c  nop     dword ptr [rax+rax+00h]
0x140169361  mov     eax, ebx
0x140169363  add     rsp, 48h
0x140169367  pop     r14
0x140169369  pop     r12
0x14016936b  pop     rdi
0x14016936c  pop     rsi
0x14016936d  pop     rbp
0x14016936e  pop     rbx
0x14016936f  retn
```
