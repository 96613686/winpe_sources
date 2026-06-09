# PgmBuildAdminSecurityDescriptor

- ea: `0x1400384e4`
- end: `0x1400386fb`
- name: `PgmBuildAdminSecurityDescriptor`
- size: `535`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140036dac`
- `0x14003a078`

## callees

- `0x14001d000`
- `0x1400384e4`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140038505`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140038505`
- `ntoskrnl!RtlMapGenericMask` at `0x140038519`
- `ntoskrnl!RtlMapGenericMask` at `0x140038519`
- `ntoskrnl!SeExports` at `0x140038525`
- `ntoskrnl!RtlLengthSid` at `0x140038547`
- `ntoskrnl!RtlLengthSid` at `0x140038558`
- `ntoskrnl!RtlLengthSid` at `0x140038569`
- `ntoskrnl!RtlLengthSid` at `0x140038547`
- `ntoskrnl!RtlLengthSid` at `0x140038558`
- `ntoskrnl!RtlLengthSid` at `0x140038569`
- `ntoskrnl!RtlCreateAcl` at `0x1400385b2`
- `ntoskrnl!RtlCreateAcl` at `0x1400385b2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400385e9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003860b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003862d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400385e9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003860b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003862d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140038697`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140038697`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400386c7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400386c7`
- `ntoskrnl!ExAllocatePool2` at `0x140038589`
- `ntoskrnl!ExAllocatePool2` at `0x14003864e`
- `ntoskrnl!ExAllocatePool2` at `0x140038589`
- `ntoskrnl!ExAllocatePool2` at `0x14003864e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400385c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038683`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400386ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400385c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038683`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400386ae`

## pseudocode

```c
__int64 __fastcall PgmBuildAdminSecurityDescriptor(struct _ACL **a1)
{
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  PSID SeNetworkServiceSid; // r12
  PSID SeAliasAdminsSid; // rsi
  PSID SeLocalServiceSid; // r15
  ULONG v6; // edi
  ULONG v7; // edi
  ULONG v8; // edi
  size_t v9; // rbp
  struct _ACL *Pool2; // rax
  struct _ACL *v11; // rbx
  NTSTATUS Acl; // edi
  struct _ACL *v14; // rcx
  __int64 v15; // rax
  struct _ACL *v16; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  struct _ACL *v18; // rcx
  DWORD AccessMask; // [rsp+58h] [rbp+10h] BYREF

  AccessMask = 0x10000000;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  SeNetworkServiceSid = SeExports->SeNetworkServiceSid;
  SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
  SeLocalServiceSid = SeExports->SeLocalServiceSid;
  v6 = RtlLengthSid(SeNetworkServiceSid);
  v7 = RtlLengthSid(SeLocalServiceSid) + v6;
  v8 = RtlLengthSid(SeAliasAdminsSid) + 32 + v7;
  v9 = v8;
  Pool2 = (struct _ACL *)ExAllocatePool2(64, v8, 1399678800);
  v11 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  Acl = RtlCreateAcl(Pool2, v8, 2u);
  v14 = v11;
  if ( Acl < 0 )
    goto LABEL_4;
  Acl = RtlAddAccessAllowedAce(v11, 2u, AccessMask, SeAliasAdminsSid);
  v14 = v11;
  if ( Acl < 0 )
    goto LABEL_4;
  Acl = RtlAddAccessAllowedAce(v11, 2u, AccessMask, SeLocalServiceSid);
  v14 = v11;
  if ( Acl < 0 )
    goto LABEL_4;
  Acl = RtlAddAccessAllowedAce(v11, 2u, AccessMask, SeNetworkServiceSid);
  if ( Acl < 0 )
  {
LABEL_10:
    v14 = v11;
LABEL_4:
    ExFreePoolWithTag(v14, 0);
    return (unsigned int)Acl;
  }
  v15 = ExAllocatePool2(64, v9 + 40, 1399678800);
  v16 = (struct _ACL *)v15;
  if ( !v15 )
  {
    Acl = -1073741670;
    goto LABEL_10;
  }
  memmove((void *)(v15 + 40), v11, v9);
  ExFreePoolWithTag(v11, 0);
  SecurityDescriptor = RtlCreateSecurityDescriptor(v16, 1u);
  v18 = v16;
  if ( SecurityDescriptor < 0 )
    goto LABEL_12;
  SecurityDescriptor = RtlSetDaclSecurityDescriptor(v16, 1u, v16 + 5, 0);
  if ( SecurityDescriptor < 0 )
  {
    v18 = v16;
LABEL_12:
    ExFreePoolWithTag(v18, 0);
    return (unsigned int)SecurityDescriptor;
  }
  *a1 = v16;
  return 0;
}

```

## disassembly

```asm
0x1400384e4  mov     [rsp+arg_0], rbx
0x1400384e9  mov     [rsp+arg_10], rbp
0x1400384ee  push    rsi
0x1400384ef  push    rdi
0x1400384f0  push    r12
0x1400384f2  push    r14
0x1400384f4  push    r15
0x1400384f6  sub     rsp, 20h
0x1400384fa  mov     r14, rcx
0x1400384fd  mov     [rsp+48h+AccessMask], 10000000h
0x140038505  call    cs:__imp_IoGetFileObjectGenericMapping
0x14003850c  nop     dword ptr [rax+rax+00h]
0x140038511  mov     rdx, rax; GenericMapping
0x140038514  lea     rcx, [rsp+48h+AccessMask]; AccessMask
0x140038519  call    cs:__imp_RtlMapGenericMask
0x140038520  nop     dword ptr [rax+rax+00h]
0x140038525  mov     rax, cs:__imp_SeExports
0x14003852c  mov     rdx, [rax]
0x14003852f  mov     r12, [rdx+188h]
0x140038536  mov     rsi, [rdx+110h]
0x14003853d  mov     rcx, r12; Sid
0x140038540  mov     r15, [rdx+180h]
0x140038547  call    cs:__imp_RtlLengthSid
0x14003854e  nop     dword ptr [rax+rax+00h]
0x140038553  mov     rcx, r15; Sid
0x140038556  mov     edi, eax
0x140038558  call    cs:__imp_RtlLengthSid
0x14003855f  nop     dword ptr [rax+rax+00h]
0x140038564  mov     rcx, rsi; Sid
0x140038567  add     edi, eax
0x140038569  call    cs:__imp_RtlLengthSid
0x140038570  nop     dword ptr [rax+rax+00h]
0x140038575  mov     r8d, 536D6750h
0x14003857b  mov     ecx, 40h ; '@'
0x140038580  add     eax, 20h ; ' '
0x140038583  add     edi, eax
0x140038585  mov     edx, edi
0x140038587  mov     ebp, edi
0x140038589  call    cs:__imp_ExAllocatePool2
0x140038590  nop     dword ptr [rax+rax+00h]
0x140038595  mov     rbx, rax
0x140038598  test    rax, rax
0x14003859b  jnz     short loc_1400385A7
0x14003859d  mov     eax, 0C000009Ah
0x1400385a2  jmp     loc_1400386E3
0x1400385a7  mov     r8d, 2; AclRevision
0x1400385ad  mov     edx, edi; AclLength
0x1400385af  mov     rcx, rbx; Acl
0x1400385b2  call    cs:__imp_RtlCreateAcl
0x1400385b9  nop     dword ptr [rax+rax+00h]
0x1400385be  mov     edi, eax
0x1400385c0  mov     rcx, rbx; Acl
0x1400385c3  test    eax, eax
0x1400385c5  jns     short loc_1400385DC
0x1400385c7  xor     edx, edx; Tag
0x1400385c9  call    cs:__imp_ExFreePoolWithTag
0x1400385d0  nop     dword ptr [rax+rax+00h]
0x1400385d5  mov     eax, edi
0x1400385d7  jmp     loc_1400386E3
0x1400385dc  mov     r8d, [rsp+48h+AccessMask]; AccessMask
0x1400385e1  mov     r9, rsi; Sid
0x1400385e4  mov     edx, 2; AceRevision
0x1400385e9  call    cs:__imp_RtlAddAccessAllowedAce
0x1400385f0  nop     dword ptr [rax+rax+00h]
0x1400385f5  mov     edi, eax
0x1400385f7  mov     rcx, rbx; Acl
0x1400385fa  test    eax, eax
0x1400385fc  js      short loc_1400385C7
0x1400385fe  mov     r8d, [rsp+48h+AccessMask]; AccessMask
0x140038603  mov     r9, r15; Sid
0x140038606  mov     edx, 2; AceRevision
0x14003860b  call    cs:__imp_RtlAddAccessAllowedAce
0x140038612  nop     dword ptr [rax+rax+00h]
0x140038617  mov     edi, eax
0x140038619  mov     rcx, rbx; Acl
0x14003861c  test    eax, eax
0x14003861e  js      short loc_1400385C7
0x140038620  mov     r8d, [rsp+48h+AccessMask]; AccessMask
0x140038625  mov     r9, r12; Sid
0x140038628  mov     edx, 2; AceRevision
0x14003862d  call    cs:__imp_RtlAddAccessAllowedAce
0x140038634  nop     dword ptr [rax+rax+00h]
0x140038639  mov     edi, eax
0x14003863b  test    eax, eax
0x14003863d  js      short loc_140038667
0x14003863f  lea     rdx, [rbp+28h]
0x140038643  mov     ecx, 40h ; '@'
0x140038648  mov     r8d, 536D6750h
0x14003864e  call    cs:__imp_ExAllocatePool2
0x140038655  nop     dword ptr [rax+rax+00h]
0x14003865a  mov     rdi, rax
0x14003865d  test    rax, rax
0x140038660  jnz     short loc_14003866F
0x140038662  mov     edi, 0C000009Ah
0x140038667  mov     rcx, rbx
0x14003866a  jmp     loc_1400385C7
0x14003866f  mov     r8, rbp; Size
0x140038672  lea     rcx, [rax+28h]; void *
0x140038676  mov     rdx, rbx; Src
0x140038679  call    memmove
0x14003867e  xor     edx, edx; Tag
0x140038680  mov     rcx, rbx; P
0x140038683  call    cs:__imp_ExFreePoolWithTag
0x14003868a  nop     dword ptr [rax+rax+00h]
0x14003868f  mov     edx, 1; Revision
0x140038694  mov     rcx, rdi; SecurityDescriptor
0x140038697  call    cs:__imp_RtlCreateSecurityDescriptor
0x14003869e  nop     dword ptr [rax+rax+00h]
0x1400386a3  mov     ebx, eax
0x1400386a5  mov     rcx, rdi; SecurityDescriptor
0x1400386a8  test    eax, eax
0x1400386aa  jns     short loc_1400386BE
0x1400386ac  xor     edx, edx; Tag
0x1400386ae  call    cs:__imp_ExFreePoolWithTag
0x1400386b5  nop     dword ptr [rax+rax+00h]
0x1400386ba  mov     eax, ebx
0x1400386bc  jmp     short loc_1400386E3
0x1400386be  xor     r9d, r9d; DaclDefaulted
0x1400386c1  lea     r8, [rdi+28h]; Dacl
0x1400386c5  mov     dl, 1; DaclPresent
0x1400386c7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400386ce  nop     dword ptr [rax+rax+00h]
0x1400386d3  mov     ebx, eax
0x1400386d5  test    eax, eax
0x1400386d7  jns     short loc_1400386DE
0x1400386d9  mov     rcx, rdi
0x1400386dc  jmp     short loc_1400386AC
0x1400386de  mov     [r14], rdi
0x1400386e1  xor     eax, eax
0x1400386e3  mov     rbx, [rsp+48h+arg_0]
0x1400386e8  mov     rbp, [rsp+48h+arg_10]
0x1400386ed  add     rsp, 20h
0x1400386f1  pop     r15
0x1400386f3  pop     r14
0x1400386f5  pop     r12
0x1400386f7  pop     rdi
0x1400386f8  pop     rsi
0x1400386f9  retn
```
