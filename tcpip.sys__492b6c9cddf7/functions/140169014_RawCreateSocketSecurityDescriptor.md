# RawCreateSocketSecurityDescriptor

- ea: `0x140169014`
- end: `0x140169231`
- name: `RawCreateSocketSecurityDescriptor`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14014b100`

## callees

- `0x140169014`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401691f2`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1401691f2`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016914e`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016917b`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401691a4`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401691cd`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016914e`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14016917b`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401691a4`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1401691cd`
- `ntoskrnl!RtlCreateAcl` at `0x14016911c`
- `ntoskrnl!RtlCreateAcl` at `0x14016911c`
- `ntoskrnl!RtlLengthSid` at `0x140169083`
- `ntoskrnl!RtlLengthSid` at `0x140169094`
- `ntoskrnl!RtlLengthSid` at `0x1401690a5`
- `ntoskrnl!RtlLengthSid` at `0x1401690b6`
- `ntoskrnl!RtlLengthSid` at `0x140169083`
- `ntoskrnl!RtlLengthSid` at `0x140169094`
- `ntoskrnl!RtlLengthSid` at `0x1401690a5`
- `ntoskrnl!RtlLengthSid` at `0x1401690b6`
- `ntoskrnl!SeExports` at `0x14016905a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140169044`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140169044`
- `ntoskrnl!ExAllocatePool3` at `0x1401690ec`
- `ntoskrnl!ExAllocatePool3` at `0x1401690ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140169215`
- `ntoskrnl!ExFreePoolWithTag` at `0x140169215`

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
  SecurityDescriptor = RtlCreateSecurityDescriptor(qword_140224710, 1u);
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
              SecurityDescriptor = RtlSetDaclSecurityDescriptor(qword_140224710, 1u, Dacl, 0);
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
0x140169014  push    rbx
0x140169016  push    rbp
0x140169017  push    rsi
0x140169018  push    rdi
0x140169019  push    r12
0x14016901b  push    r14
0x14016901d  sub     rsp, 48h
0x140169021  xorps   xmm0, xmm0
0x140169024  mov     cs:Dacl, 0
0x14016902f  mov     r12d, 1
0x140169035  lea     rcx, qword_140224710; SecurityDescriptor
0x14016903c  mov     edx, r12d; Revision
0x14016903f  movups  [rsp+78h+var_48], xmm0
0x140169044  call    cs:__imp_RtlCreateSecurityDescriptor
0x14016904b  nop     dword ptr [rax+rax+00h]
0x140169050  mov     ebx, eax
0x140169052  test    eax, eax
0x140169054  js      loc_140169204
0x14016905a  mov     rax, cs:__imp_SeExports
0x140169061  mov     rcx, [rax]
0x140169064  mov     r14, [rcx+180h]
0x14016906b  mov     rdi, [rcx+110h]
0x140169072  mov     rsi, [rcx+108h]
0x140169079  mov     rbp, [rcx+188h]
0x140169080  mov     rcx, r14; Sid
0x140169083  call    cs:__imp_RtlLengthSid
0x14016908a  nop     dword ptr [rax+rax+00h]
0x14016908f  mov     rcx, rbp; Sid
0x140169092  mov     ebx, eax
0x140169094  call    cs:__imp_RtlLengthSid
0x14016909b  nop     dword ptr [rax+rax+00h]
0x1401690a0  mov     rcx, rsi; Sid
0x1401690a3  add     ebx, eax
0x1401690a5  call    cs:__imp_RtlLengthSid
0x1401690ac  nop     dword ptr [rax+rax+00h]
0x1401690b1  mov     rcx, rdi; Sid
0x1401690b4  add     ebx, eax
0x1401690b6  call    cs:__imp_RtlLengthSid
0x1401690bd  nop     dword ptr [rax+rax+00h]
0x1401690c2  lea     r9, [rsp+78h+var_48]
0x1401690c7  mov     qword ptr [rsp+78h+var_48+8], 0
0x1401690d0  add     eax, 28h ; '('
0x1401690d3  mov     qword ptr [rsp+78h+var_48], r12
0x1401690d8  add     ebx, eax
0x1401690da  mov     dword ptr [rsp+78h+Sid], r12d
0x1401690df  mov     edx, ebx
0x1401690e1  lea     ecx, [r12+3Fh]
0x1401690e6  mov     r8d, 41446152h
0x1401690ec  call    cs:__imp_ExAllocatePool3
0x1401690f3  nop     dword ptr [rax+rax+00h]
0x1401690f8  mov     cs:Dacl, rax
0x1401690ff  test    rax, rax
0x140169102  jnz     short loc_14016910E
0x140169104  mov     ebx, 0C000009Ah
0x140169109  jmp     loc_14016920B
0x14016910e  mov     r12d, 2
0x140169114  mov     edx, ebx; AclLength
0x140169116  mov     r8d, r12d; AclRevision
0x140169119  mov     rcx, rax; Acl
0x14016911c  call    cs:__imp_RtlCreateAcl
0x140169123  nop     dword ptr [rax+rax+00h]
0x140169128  mov     ebx, eax
0x14016912a  test    eax, eax
0x14016912c  js      loc_140169204
0x140169132  mov     rcx, cs:Dacl; Acl
0x140169139  lea     r8d, [r12+1]; AceFlags
0x14016913e  mov     [rsp+78h+Sid], rdi; Sid
0x140169143  mov     edx, r12d; AceRevision
0x140169146  mov     edi, 0F003Fh
0x14016914b  mov     r9d, edi; AccessMask
0x14016914e  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140169155  nop     dword ptr [rax+rax+00h]
0x14016915a  mov     ebx, eax
0x14016915c  test    eax, eax
0x14016915e  js      loc_140169204
0x140169164  mov     rcx, cs:Dacl; Acl
0x14016916b  lea     r8d, [r12+1]; AceFlags
0x140169170  mov     r9d, edi; AccessMask
0x140169173  mov     [rsp+78h+Sid], rsi; Sid
0x140169178  mov     edx, r12d; AceRevision
0x14016917b  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140169182  nop     dword ptr [rax+rax+00h]
0x140169187  mov     ebx, eax
0x140169189  test    eax, eax
0x14016918b  js      short loc_140169204
0x14016918d  mov     rcx, cs:Dacl; Acl
0x140169194  lea     r8d, [r12+1]; AceFlags
0x140169199  mov     r9d, edi; AccessMask
0x14016919c  mov     [rsp+78h+Sid], rbp; Sid
0x1401691a1  mov     edx, r12d; AceRevision
0x1401691a4  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1401691ab  nop     dword ptr [rax+rax+00h]
0x1401691b0  mov     ebx, eax
0x1401691b2  test    eax, eax
0x1401691b4  js      short loc_140169204
0x1401691b6  mov     rcx, cs:Dacl; Acl
0x1401691bd  lea     r8d, [r12+1]; AceFlags
0x1401691c2  mov     r9d, edi; AccessMask
0x1401691c5  mov     [rsp+78h+Sid], r14; Sid
0x1401691ca  mov     edx, r12d; AceRevision
0x1401691cd  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1401691d4  nop     dword ptr [rax+rax+00h]
0x1401691d9  mov     ebx, eax
0x1401691db  test    eax, eax
0x1401691dd  js      short loc_140169204
0x1401691df  mov     r8, cs:Dacl; Dacl
0x1401691e6  lea     rcx, qword_140224710; SecurityDescriptor
0x1401691ed  xor     r9d, r9d; DaclDefaulted
0x1401691f0  mov     dl, 1; DaclPresent
0x1401691f2  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1401691f9  nop     dword ptr [rax+rax+00h]
0x1401691fe  mov     ebx, eax
0x140169200  test    eax, eax
0x140169202  jns     short loc_140169221
0x140169204  mov     rax, cs:Dacl
0x14016920b  test    rax, rax
0x14016920e  jz      short loc_140169221
0x140169210  xor     edx, edx; Tag
0x140169212  mov     rcx, rax; P
0x140169215  call    cs:__imp_ExFreePoolWithTag
0x14016921c  nop     dword ptr [rax+rax+00h]
0x140169221  mov     eax, ebx
0x140169223  add     rsp, 48h
0x140169227  pop     r14
0x140169229  pop     r12
0x14016922b  pop     rdi
0x14016922c  pop     rsi
0x14016922d  pop     rbp
0x14016922e  pop     rbx
0x14016922f  retn
```
