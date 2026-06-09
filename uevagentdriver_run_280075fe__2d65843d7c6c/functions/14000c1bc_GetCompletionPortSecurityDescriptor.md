# GetCompletionPortSecurityDescriptor

- ea: `0x14000c1bc`
- end: `0x14000c49c`
- name: `GetCompletionPortSecurityDescriptor`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c078`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x140001298`
- `0x1400015c0`
- `0x14000164c`
- `0x140001b40`
- `0x14000c1bc`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000c422`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000c422`
- `ntoskrnl!RtlLengthSid` at `0x14000c30a`
- `ntoskrnl!RtlLengthSid` at `0x14000c30a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000c3ec`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000c3ec`
- `ntoskrnl!RtlCreateAcl` at `0x14000c3aa`
- `ntoskrnl!RtlCreateAcl` at `0x14000c3aa`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000c379`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000c379`
- `ksecdd!SecLookupWellKnownSid` at `0x14000c275`
- `ksecdd!SecLookupWellKnownSid` at `0x14000c2c6`
- `ksecdd!SecLookupWellKnownSid` at `0x14000c275`
- `ksecdd!SecLookupWellKnownSid` at `0x14000c2c6`

## string_xrefs

- `0x14000c1ec`: `UevFilter.GetCompletionPortSecurityDescriptor: Entry\n`
- `0x14000c321`: `UevFilter.GetCompletionPortSecurityDescriptor: Failed to get WinAuthenticatedUserSid. Error = 0x%0X.\n`
- `0x14000c357`: `UevFilter.GetCompletionPortSecurityDescriptor: Failed to allocate memory for descriptor. Error = 0x%0X.\n`
- `0x14000c38b`: `UevFilter.GetCompletionPortSecurityDescriptor: Failed to create descriptor. Error = 0x%0X.\n`
- `0x14000c3bc`: `UevFilter.GetCompletionPortSecurityDescriptor: Failed to create new ACL. Error = 0x%0X.\n`
- `0x14000c400`: `UevFilter.GetCompletionPortSecurityDescriptor: Failed to add ACE to ACL. Error = 0x%0X.\n`
- `0x14000c434`: `UevFilter.GetCompletionPortSecurityDescriptor: Failed to set DACL. Error = 0x%0X.\n`
- `0x14000c479`: `UevFilter.GetCompletionPortSecurityDescriptor: Exit. Error = 0x%0X.\n`
- `0x14000c234`: `UevFilter.LookupWellKnownSid: Entry\n`
- `0x14000c29b`: `UevFilter.LookupWellKnownSid: Failed to allocate buffer for SID. Error = 0x%0X.\n`
- `0x14000c2a8`: `UevFilter.LookupWellKnownSid: Failed to get SID size. Error = 0x%0X.\n`
- `0x14000c2da`: `UevFilter.LookupWellKnownSid: Failed to get well known SID. Error = 0x%0X.\n`
- `0x14000c2f0`: `UevFilter.LookupWellKnownSid: Exit. Error = 0x%0X.\n`

## pseudocode

```c
__int64 __fastcall GetCompletionPortSecurityDescriptor(void **a1)
{
  NTSTATUS GenericBuffer; // ebx
  ULONG v3; // r12d
  unsigned int v4; // r15d
  PSID *v5; // rdi
  WELL_KNOWN_SID_TYPE v6; // r13d
  NTSTATUS v7; // eax
  __int64 v8; // rcx
  char *v9; // rcx
  __int64 v10; // rcx
  char *v11; // rcx
  struct _ACL *v12; // rdi
  unsigned int v13; // esi
  __int64 i; // rdi
  void *v15; // rcx
  ULONG SidSize; // [rsp+20h] [rbp-48h] BYREF
  WELL_KNOWN_SID_TYPE SidType; // [rsp+28h] [rbp-40h]
  ACCESS_MASK AccessMask; // [rsp+2Ch] [rbp-3Ch]
  PSID Sid; // [rsp+30h] [rbp-38h] BYREF
  int v21; // [rsp+38h] [rbp-30h]
  int v22; // [rsp+3Ch] [rbp-2Ch]
  __int64 v23; // [rsp+40h] [rbp-28h]
  int v24; // [rsp+48h] [rbp-20h]
  int v25; // [rsp+4Ch] [rbp-1Ch]
  __int64 v26; // [rsp+50h] [rbp-18h]

  SidType = WinAuthenticatedUserSid;
  GenericBuffer = 0;
  AccessMask = 2031617;
  Sid = 0;
  v21 = 26;
  v22 = 2031617;
  v23 = 0;
  v24 = 22;
  v3 = 8;
  v25 = 2031617;
  v26 = 0;
  DbgTrace(2, "UevFilter.GetCompletionPortSecurityDescriptor: Entry\n");
  v4 = 0;
  *a1 = 0;
  do
  {
    if ( GenericBuffer < 0 )
      goto LABEL_36;
    SidSize = 0;
    DbgTrace(2, "UevFilter.LookupWellKnownSid: Entry\n");
    v5 = &Sid + 2 * v4;
    if ( v5 )
    {
      v6 = *((_DWORD *)&SidType + 4 * v4);
      *v5 = 0;
      v7 = SecLookupWellKnownSid(v6, 0, 0, &SidSize);
      GenericBuffer = v7;
      if ( v7 == -1073741789 )
      {
        GenericBuffer = AllocateGenericBuffer(v8, SidSize, v5);
        if ( GenericBuffer < 0 )
        {
          v9 = "UevFilter.LookupWellKnownSid: Failed to allocate buffer for SID. Error = 0x%0X.\n";
LABEL_13:
          DbgTraceFrmtErr(v9);
          goto LABEL_15;
        }
      }
      else if ( v7 < 0 )
      {
        v9 = "UevFilter.LookupWellKnownSid: Failed to get SID size. Error = 0x%0X.\n";
        goto LABEL_13;
      }
      if ( !*v5 )
        goto LABEL_15;
      GenericBuffer = SecLookupWellKnownSid(v6, *v5, SidSize, &SidSize);
      if ( GenericBuffer >= 0 )
        goto LABEL_15;
      v9 = "UevFilter.LookupWellKnownSid: Failed to get well known SID. Error = 0x%0X.\n";
      goto LABEL_13;
    }
    GenericBuffer = -1073741811;
LABEL_15:
    DbgTraceFrmt(2, "UevFilter.LookupWellKnownSid: Exit. Error = 0x%0X.\n", GenericBuffer);
    if ( GenericBuffer < 0 )
      DbgTraceFrmtErr("UevFilter.GetCompletionPortSecurityDescriptor: Failed to get WinAuthenticatedUserSid. Error = 0x%0X.\n");
    else
      v3 += RtlLengthSid(*(&Sid + 2 * v4)) + 8;
    ++v4;
  }
  while ( v4 < 3 );
  if ( GenericBuffer < 0 )
    goto LABEL_36;
  GenericBuffer = AllocateGenericBuffer(v10, v3 + 40LL, a1);
  if ( GenericBuffer < 0 )
  {
    v11 = "UevFilter.GetCompletionPortSecurityDescriptor: Failed to allocate memory for descriptor. Error = 0x%0X.\n";
LABEL_35:
    DbgTraceFrmtErr(v11);
    goto LABEL_36;
  }
  memset(*a1, 0, v3 + 40LL);
  GenericBuffer = RtlCreateSecurityDescriptor(*a1, 1u);
  if ( GenericBuffer < 0 )
  {
    v11 = "UevFilter.GetCompletionPortSecurityDescriptor: Failed to create descriptor. Error = 0x%0X.\n";
    goto LABEL_35;
  }
  v12 = (struct _ACL *)((char *)*a1 + 40);
  GenericBuffer = RtlCreateAcl(v12, v3, 2u);
  if ( GenericBuffer < 0 )
  {
    v11 = "UevFilter.GetCompletionPortSecurityDescriptor: Failed to create new ACL. Error = 0x%0X.\n";
    goto LABEL_35;
  }
  if ( !v12 )
    goto LABEL_38;
  v13 = 0;
  while ( GenericBuffer >= 0 )
  {
    GenericBuffer = RtlAddAccessAllowedAce(v12, 2u, *(&AccessMask + 4 * v13), *(&Sid + 2 * v13));
    if ( GenericBuffer < 0 )
      DbgTraceFrmtErr("UevFilter.GetCompletionPortSecurityDescriptor: Failed to add ACE to ACL. Error = 0x%0X.\n");
    if ( ++v13 >= 3 )
    {
      if ( GenericBuffer < 0 )
        break;
      GenericBuffer = RtlSetDaclSecurityDescriptor(*a1, 1u, v12, 0);
      if ( GenericBuffer < 0 )
      {
        v11 = "UevFilter.GetCompletionPortSecurityDescriptor: Failed to set DACL. Error = 0x%0X.\n";
        goto LABEL_35;
      }
      goto LABEL_38;
    }
  }
LABEL_36:
  if ( *a1 )
  {
    FreeGenericBuffer(*a1);
    *a1 = 0;
  }
LABEL_38:
  for ( i = 0; i != 3; ++i )
  {
    v15 = *(&Sid + 2 * i);
    if ( v15 )
      FreeGenericBuffer(v15);
  }
  DbgTraceFrmt(2, "UevFilter.GetCompletionPortSecurityDescriptor: Exit. Error = 0x%0X.\n", GenericBuffer);
  return (unsigned int)GenericBuffer;
}

```

## disassembly

```asm
0x14000c1bc  push    rbp
0x14000c1be  push    rbx
0x14000c1bf  push    rsi
0x14000c1c0  push    rdi
0x14000c1c1  push    r12
0x14000c1c3  push    r13
0x14000c1c5  push    r14
0x14000c1c7  push    r15
0x14000c1c9  mov     rbp, rsp
0x14000c1cc  sub     rsp, 68h
0x14000c1d0  mov     eax, 1F0001h
0x14000c1d5  mov     [rbp+SidType], 11h
0x14000c1dc  xor     ebx, ebx
0x14000c1de  mov     [rbp+AccessMask], eax
0x14000c1e1  mov     r14, rcx
0x14000c1e4  mov     [rbp+Sid], 0
0x14000c1ec  lea     rdx, aUevfilterGetco_6; "UevFilter.GetCompletionPortSecurityDesc"...
0x14000c1f3  mov     [rbp+var_30], 1Ah
0x14000c1fa  mov     [rbp+var_2C], eax
0x14000c1fd  lea     ecx, [rbx+2]
0x14000c200  mov     [rbp+var_28], 0
0x14000c208  mov     [rbp+var_20], 16h
0x14000c20f  lea     r12d, [rbx+8]
0x14000c213  mov     [rbp+var_1C], eax
0x14000c216  mov     [rbp+var_18], 0
0x14000c21e  call    DbgTrace
0x14000c223  xor     r15d, r15d
0x14000c226  mov     [r14], rbx
0x14000c229  test    ebx, ebx
0x14000c22b  js      loc_14000C442
0x14000c231  mov     esi, r15d
0x14000c234  lea     rdx, aUevfilterLooku; "UevFilter.LookupWellKnownSid: Entry\n"
0x14000c23b  mov     ecx, 2
0x14000c240  shl     rsi, 4
0x14000c244  lea     rdi, [rbp+Sid]
0x14000c248  mov     [rbp+SidSize], 0
0x14000c24f  call    DbgTrace
0x14000c254  add     rdi, rsi
0x14000c257  jz      loc_14000C2E8
0x14000c25d  mov     r13d, [rbp+rsi+SidType]
0x14000c262  lea     r9, [rbp+SidSize]; SidSize
0x14000c266  mov     ecx, r13d; SidType
0x14000c269  mov     qword ptr [rdi], 0
0x14000c270  xor     r8d, r8d; SidBufferSize
0x14000c273  xor     edx, edx; Sid
0x14000c275  call    cs:__imp_SecLookupWellKnownSid
0x14000c27c  nop     dword ptr [rax+rax+00h]
0x14000c281  mov     ebx, eax
0x14000c283  cmp     eax, 0C0000023h
0x14000c288  jnz     short loc_14000C2A4
0x14000c28a  mov     edx, [rbp+SidSize]
0x14000c28d  mov     r8, rdi
0x14000c290  call    AllocateGenericBuffer
0x14000c295  mov     ebx, eax
0x14000c297  test    eax, eax
0x14000c299  jns     short loc_14000C2B3
0x14000c29b  lea     rcx, aUevfilterLooku_3; "UevFilter.LookupWellKnownSid: Failed to"...
0x14000c2a2  jmp     short loc_14000C2AF
0x14000c2a4  test    eax, eax
0x14000c2a6  jns     short loc_14000C2B3
0x14000c2a8  lea     rcx, aUevfilterLooku_2; "UevFilter.LookupWellKnownSid: Failed to"...
0x14000c2af  mov     edx, ebx
0x14000c2b1  jmp     short loc_14000C2E1
0x14000c2b3  mov     rdx, [rdi]; Sid
0x14000c2b6  test    rdx, rdx
0x14000c2b9  jz      short loc_14000C2ED
0x14000c2bb  mov     r8d, [rbp+SidSize]; SidBufferSize
0x14000c2bf  lea     r9, [rbp+SidSize]; SidSize
0x14000c2c3  mov     ecx, r13d; SidType
0x14000c2c6  call    cs:__imp_SecLookupWellKnownSid
0x14000c2cd  nop     dword ptr [rax+rax+00h]
0x14000c2d2  mov     ebx, eax
0x14000c2d4  test    eax, eax
0x14000c2d6  jns     short loc_14000C2ED
0x14000c2d8  mov     edx, eax
0x14000c2da  lea     rcx, aUevfilterLooku_1; "UevFilter.LookupWellKnownSid: Failed to"...
0x14000c2e1  call    DbgTraceFrmtErr
0x14000c2e6  jmp     short loc_14000C2ED
0x14000c2e8  mov     ebx, 0C000000Dh
0x14000c2ed  mov     r8d, ebx
0x14000c2f0  lea     rdx, aUevfilterLooku_0; "UevFilter.LookupWellKnownSid: Exit. Err"...
0x14000c2f7  mov     ecx, 2
0x14000c2fc  call    DbgTraceFrmt
0x14000c301  test    ebx, ebx
0x14000c303  js      short loc_14000C31F
0x14000c305  mov     rcx, [rbp+rsi+Sid]; Sid
0x14000c30a  call    cs:__imp_RtlLengthSid
0x14000c311  nop     dword ptr [rax+rax+00h]
0x14000c316  add     r12d, 8
0x14000c31a  add     r12d, eax
0x14000c31d  jmp     short loc_14000C32D
0x14000c31f  mov     edx, ebx
0x14000c321  lea     rcx, aUevfilterGetco_1; "UevFilter.GetCompletionPortSecurityDesc"...
0x14000c328  call    DbgTraceFrmtErr
0x14000c32d  inc     r15d
0x14000c330  cmp     r15d, 3
0x14000c334  jb      loc_14000C229
0x14000c33a  test    ebx, ebx
0x14000c33c  js      loc_14000C442
0x14000c342  mov     edi, r12d
0x14000c345  mov     r8, r14
0x14000c348  lea     rdx, [rdi+28h]
0x14000c34c  call    AllocateGenericBuffer
0x14000c351  mov     ebx, eax
0x14000c353  test    eax, eax
0x14000c355  jns     short loc_14000C363
0x14000c357  lea     rcx, aUevfilterGetco_4; "UevFilter.GetCompletionPortSecurityDesc"...
0x14000c35e  jmp     loc_14000C43B
0x14000c363  mov     rcx, [r14]; void *
0x14000c366  lea     r8, [rdi+28h]; Size
0x14000c36a  xor     edx, edx; Val
0x14000c36c  call    memset
0x14000c371  mov     rcx, [r14]; SecurityDescriptor
0x14000c374  mov     edx, 1; Revision
0x14000c379  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000c380  nop     dword ptr [rax+rax+00h]
0x14000c385  mov     ebx, eax
0x14000c387  test    eax, eax
0x14000c389  jns     short loc_14000C397
0x14000c38b  lea     rcx, aUevfilterGetco_2; "UevFilter.GetCompletionPortSecurityDesc"...
0x14000c392  jmp     loc_14000C43B
0x14000c397  mov     rdi, [r14]
0x14000c39a  mov     r8d, 2; AclRevision
0x14000c3a0  add     rdi, 28h ; '('
0x14000c3a4  mov     edx, r12d; AclLength
0x14000c3a7  mov     rcx, rdi; Acl
0x14000c3aa  call    cs:__imp_RtlCreateAcl
0x14000c3b1  nop     dword ptr [rax+rax+00h]
0x14000c3b6  mov     ebx, eax
0x14000c3b8  test    eax, eax
0x14000c3ba  jns     short loc_14000C3C5
0x14000c3bc  lea     rcx, aUevfilterGetco_0; "UevFilter.GetCompletionPortSecurityDesc"...
0x14000c3c3  jmp     short loc_14000C43B
0x14000c3c5  test    rdi, rdi
0x14000c3c8  jz      loc_14000C456
0x14000c3ce  xor     esi, esi
0x14000c3d0  test    ebx, ebx
0x14000c3d2  js      short loc_14000C442
0x14000c3d4  mov     r8d, esi
0x14000c3d7  mov     edx, 2; AceRevision
0x14000c3dc  add     r8, r8
0x14000c3df  mov     rcx, rdi; Acl
0x14000c3e2  mov     r9, [rbp+r8*8+Sid]; Sid
0x14000c3e7  mov     r8d, [rbp+r8*8+AccessMask]; AccessMask
0x14000c3ec  call    cs:__imp_RtlAddAccessAllowedAce
0x14000c3f3  nop     dword ptr [rax+rax+00h]
0x14000c3f8  mov     ebx, eax
0x14000c3fa  test    eax, eax
0x14000c3fc  jns     short loc_14000C40C
0x14000c3fe  mov     edx, eax
0x14000c400  lea     rcx, aUevfilterGetco_5; "UevFilter.GetCompletionPortSecurityDesc"...
0x14000c407  call    DbgTraceFrmtErr
0x14000c40c  inc     esi
0x14000c40e  cmp     esi, 3
0x14000c411  jb      short loc_14000C3D0
0x14000c413  test    ebx, ebx
0x14000c415  js      short loc_14000C442
0x14000c417  mov     rcx, [r14]; SecurityDescriptor
0x14000c41a  xor     r9d, r9d; DaclDefaulted
0x14000c41d  mov     r8, rdi; Dacl
0x14000c420  mov     dl, 1; DaclPresent
0x14000c422  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000c429  nop     dword ptr [rax+rax+00h]
0x14000c42e  mov     ebx, eax
0x14000c430  test    eax, eax
0x14000c432  jns     short loc_14000C456
0x14000c434  lea     rcx, aUevfilterGetco; "UevFilter.GetCompletionPortSecurityDesc"...
0x14000c43b  mov     edx, eax
0x14000c43d  call    DbgTraceFrmtErr
0x14000c442  mov     rcx, [r14]; P
0x14000c445  test    rcx, rcx
0x14000c448  jz      short loc_14000C456
0x14000c44a  call    FreeGenericBuffer
0x14000c44f  mov     qword ptr [r14], 0
0x14000c456  xor     edi, edi
0x14000c458  mov     rax, rdi
0x14000c45b  add     rax, rax
0x14000c45e  mov     rcx, [rbp+rax*8+Sid]; P
0x14000c463  test    rcx, rcx
0x14000c466  jz      short loc_14000C46D
0x14000c468  call    FreeGenericBuffer
0x14000c46d  inc     rdi
0x14000c470  cmp     rdi, 3
0x14000c474  jnz     short loc_14000C458
0x14000c476  mov     r8d, ebx
0x14000c479  lea     rdx, aUevfilterGetco_3; "UevFilter.GetCompletionPortSecurityDesc"...
0x14000c480  lea     ecx, [rdi-1]
0x14000c483  call    DbgTraceFrmt
0x14000c488  mov     eax, ebx
0x14000c48a  add     rsp, 68h
0x14000c48e  pop     r15
0x14000c490  pop     r14
0x14000c492  pop     r13
0x14000c494  pop     r12
0x14000c496  pop     rdi
0x14000c497  pop     rsi
0x14000c498  pop     rbx
0x14000c499  pop     rbp
0x14000c49a  retn
```
