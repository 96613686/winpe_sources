# PgmBuildAdminSecurityDescriptor

- ea: `0x140038494`
- end: `0x1400386ab`
- name: `PgmBuildAdminSecurityDescriptor`
- size: `535`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140036d5c`
- `0x14003a078`

## callees

- `0x14001d000`
- `0x140038494`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400384b5`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400384b5`
- `ntoskrnl!RtlMapGenericMask` at `0x1400384c9`
- `ntoskrnl!RtlMapGenericMask` at `0x1400384c9`
- `ntoskrnl!SeExports` at `0x1400384d5`
- `ntoskrnl!RtlLengthSid` at `0x1400384f7`
- `ntoskrnl!RtlLengthSid` at `0x140038508`
- `ntoskrnl!RtlLengthSid` at `0x140038519`
- `ntoskrnl!RtlLengthSid` at `0x1400384f7`
- `ntoskrnl!RtlLengthSid` at `0x140038508`
- `ntoskrnl!RtlLengthSid` at `0x140038519`
- `ntoskrnl!RtlCreateAcl` at `0x140038562`
- `ntoskrnl!RtlCreateAcl` at `0x140038562`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140038599`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400385bb`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400385dd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140038599`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400385bb`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400385dd`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140038647`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140038647`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140038677`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140038677`
- `ntoskrnl!ExAllocatePool2` at `0x140038539`
- `ntoskrnl!ExAllocatePool2` at `0x1400385fe`
- `ntoskrnl!ExAllocatePool2` at `0x140038539`
- `ntoskrnl!ExAllocatePool2` at `0x1400385fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038579`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038633`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003865e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038579`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038633`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003865e`

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
0x140038494  mov     [rsp+arg_0], rbx
0x140038499  mov     [rsp+arg_10], rbp
0x14003849e  push    rsi
0x14003849f  push    rdi
0x1400384a0  push    r12
0x1400384a2  push    r14
0x1400384a4  push    r15
0x1400384a6  sub     rsp, 20h
0x1400384aa  mov     r14, rcx
0x1400384ad  mov     [rsp+48h+AccessMask], 10000000h
0x1400384b5  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400384bc  nop     dword ptr [rax+rax+00h]
0x1400384c1  mov     rdx, rax; GenericMapping
0x1400384c4  lea     rcx, [rsp+48h+AccessMask]; AccessMask
0x1400384c9  call    cs:__imp_RtlMapGenericMask
0x1400384d0  nop     dword ptr [rax+rax+00h]
0x1400384d5  mov     rax, cs:__imp_SeExports
0x1400384dc  mov     rdx, [rax]
0x1400384df  mov     r12, [rdx+188h]
0x1400384e6  mov     rsi, [rdx+110h]
0x1400384ed  mov     rcx, r12; Sid
0x1400384f0  mov     r15, [rdx+180h]
0x1400384f7  call    cs:__imp_RtlLengthSid
0x1400384fe  nop     dword ptr [rax+rax+00h]
0x140038503  mov     rcx, r15; Sid
0x140038506  mov     edi, eax
0x140038508  call    cs:__imp_RtlLengthSid
0x14003850f  nop     dword ptr [rax+rax+00h]
0x140038514  mov     rcx, rsi; Sid
0x140038517  add     edi, eax
0x140038519  call    cs:__imp_RtlLengthSid
0x140038520  nop     dword ptr [rax+rax+00h]
0x140038525  mov     r8d, 536D6750h
0x14003852b  mov     ecx, 40h ; '@'
0x140038530  add     eax, 20h ; ' '
0x140038533  add     edi, eax
0x140038535  mov     edx, edi
0x140038537  mov     ebp, edi
0x140038539  call    cs:__imp_ExAllocatePool2
0x140038540  nop     dword ptr [rax+rax+00h]
0x140038545  mov     rbx, rax
0x140038548  test    rax, rax
0x14003854b  jnz     short loc_140038557
0x14003854d  mov     eax, 0C000009Ah
0x140038552  jmp     loc_140038693
0x140038557  mov     r8d, 2; AclRevision
0x14003855d  mov     edx, edi; AclLength
0x14003855f  mov     rcx, rbx; Acl
0x140038562  call    cs:__imp_RtlCreateAcl
0x140038569  nop     dword ptr [rax+rax+00h]
0x14003856e  mov     edi, eax
0x140038570  mov     rcx, rbx; Acl
0x140038573  test    eax, eax
0x140038575  jns     short loc_14003858C
0x140038577  xor     edx, edx; Tag
0x140038579  call    cs:__imp_ExFreePoolWithTag
0x140038580  nop     dword ptr [rax+rax+00h]
0x140038585  mov     eax, edi
0x140038587  jmp     loc_140038693
0x14003858c  mov     r8d, [rsp+48h+AccessMask]; AccessMask
0x140038591  mov     r9, rsi; Sid
0x140038594  mov     edx, 2; AceRevision
0x140038599  call    cs:__imp_RtlAddAccessAllowedAce
0x1400385a0  nop     dword ptr [rax+rax+00h]
0x1400385a5  mov     edi, eax
0x1400385a7  mov     rcx, rbx; Acl
0x1400385aa  test    eax, eax
0x1400385ac  js      short loc_140038577
0x1400385ae  mov     r8d, [rsp+48h+AccessMask]; AccessMask
0x1400385b3  mov     r9, r15; Sid
0x1400385b6  mov     edx, 2; AceRevision
0x1400385bb  call    cs:__imp_RtlAddAccessAllowedAce
0x1400385c2  nop     dword ptr [rax+rax+00h]
0x1400385c7  mov     edi, eax
0x1400385c9  mov     rcx, rbx; Acl
0x1400385cc  test    eax, eax
0x1400385ce  js      short loc_140038577
0x1400385d0  mov     r8d, [rsp+48h+AccessMask]; AccessMask
0x1400385d5  mov     r9, r12; Sid
0x1400385d8  mov     edx, 2; AceRevision
0x1400385dd  call    cs:__imp_RtlAddAccessAllowedAce
0x1400385e4  nop     dword ptr [rax+rax+00h]
0x1400385e9  mov     edi, eax
0x1400385eb  test    eax, eax
0x1400385ed  js      short loc_140038617
0x1400385ef  lea     rdx, [rbp+28h]
0x1400385f3  mov     ecx, 40h ; '@'
0x1400385f8  mov     r8d, 536D6750h
0x1400385fe  call    cs:__imp_ExAllocatePool2
0x140038605  nop     dword ptr [rax+rax+00h]
0x14003860a  mov     rdi, rax
0x14003860d  test    rax, rax
0x140038610  jnz     short loc_14003861F
0x140038612  mov     edi, 0C000009Ah
0x140038617  mov     rcx, rbx
0x14003861a  jmp     loc_140038577
0x14003861f  mov     r8, rbp; Size
0x140038622  lea     rcx, [rax+28h]; void *
0x140038626  mov     rdx, rbx; Src
0x140038629  call    memmove
0x14003862e  xor     edx, edx; Tag
0x140038630  mov     rcx, rbx; P
0x140038633  call    cs:__imp_ExFreePoolWithTag
0x14003863a  nop     dword ptr [rax+rax+00h]
0x14003863f  mov     edx, 1; Revision
0x140038644  mov     rcx, rdi; SecurityDescriptor
0x140038647  call    cs:__imp_RtlCreateSecurityDescriptor
0x14003864e  nop     dword ptr [rax+rax+00h]
0x140038653  mov     ebx, eax
0x140038655  mov     rcx, rdi; SecurityDescriptor
0x140038658  test    eax, eax
0x14003865a  jns     short loc_14003866E
0x14003865c  xor     edx, edx; Tag
0x14003865e  call    cs:__imp_ExFreePoolWithTag
0x140038665  nop     dword ptr [rax+rax+00h]
0x14003866a  mov     eax, ebx
0x14003866c  jmp     short loc_140038693
0x14003866e  xor     r9d, r9d; DaclDefaulted
0x140038671  lea     r8, [rdi+28h]; Dacl
0x140038675  mov     dl, 1; DaclPresent
0x140038677  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14003867e  nop     dword ptr [rax+rax+00h]
0x140038683  mov     ebx, eax
0x140038685  test    eax, eax
0x140038687  jns     short loc_14003868E
0x140038689  mov     rcx, rdi
0x14003868c  jmp     short loc_14003865C
0x14003868e  mov     [r14], rdi
0x140038691  xor     eax, eax
0x140038693  mov     rbx, [rsp+48h+arg_0]
0x140038698  mov     rbp, [rsp+48h+arg_10]
0x14003869d  add     rsp, 20h
0x1400386a1  pop     r15
0x1400386a3  pop     r14
0x1400386a5  pop     r12
0x1400386a7  pop     rdi
0x1400386a8  pop     rsi
0x1400386a9  retn
```
