# CellHeap::CreateSecurityDescriptor(void)

- ea: `0x1800a47cc`
- end: `0x1800a4895`
- name: `?CreateSecurityDescriptor@CellHeap@@AEAAJXZ`
- size: `201`
- prototype: `__int64 __fastcall(CellHeap *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800a4758`

## callees

- `0x180021e70`
- `0x180022870`
- `0x1800a47cc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800a4882`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800a4882`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800a4820`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800a4820`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800a4855`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800a486e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800a4855`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800a486e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800a483c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800a483c`

## pseudocode

```c
__int64 __fastcall CellHeap::CreateSecurityDescriptor(CellHeap *this)
{
  void *v2; // rax
  struct _ACL *v4; // rax
  void *v5; // rcx
  struct _ACL *v6; // rdi

  v2 = AllocWrapper(0x28u);
  *((_QWORD *)this + 10) = v2;
  if ( !v2 )
    return 14;
  v4 = (struct _ACL *)AllocWrapper(0x54u);
  v5 = (void *)*((_QWORD *)this + 10);
  v6 = v4;
  if ( !v4 )
  {
LABEL_4:
    FreeWrapper(v5);
    *((_QWORD *)this + 10) = 0;
    return 14;
  }
  if ( !InitializeSecurityDescriptor(v5, 1u) )
  {
    v5 = (void *)*((_QWORD *)this + 10);
    goto LABEL_4;
  }
  InitializeAcl(v6, 0x54u, 2u);
  AddAccessAllowedAce(v6, 2u, 4u, &NetworkService);
  AddAccessAllowedAce(v6, 2u, 4u, &Admin1);
  SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 10), 1, v6, 0);
  return 0;
}

```

## disassembly

```asm
0x1800a47cc  mov     [rsp+arg_0], rbx
0x1800a47d1  push    rdi
0x1800a47d2  sub     rsp, 20h
0x1800a47d6  mov     rbx, rcx
0x1800a47d9  mov     ecx, 28h ; '('; dwBytes
0x1800a47de  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a47e3  mov     [rbx+50h], rax
0x1800a47e7  test    rax, rax
0x1800a47ea  jnz     short loc_1800A47F6
0x1800a47ec  mov     eax, 0Eh
0x1800a47f1  jmp     loc_1800A488A
0x1800a47f6  mov     ecx, 54h ; 'T'; dwBytes
0x1800a47fb  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a4800  mov     rcx, [rbx+50h]; lpMem
0x1800a4804  mov     rdi, rax
0x1800a4807  test    rax, rax
0x1800a480a  jnz     short loc_1800A481B
0x1800a480c  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a4811  mov     qword ptr [rbx+50h], 0
0x1800a4819  jmp     short loc_1800A47EC
0x1800a481b  mov     edx, 1; dwRevision
0x1800a4820  call    cs:__imp_InitializeSecurityDescriptor
0x1800a4826  test    eax, eax
0x1800a4828  jnz     short loc_1800A4830
0x1800a482a  mov     rcx, [rbx+50h]
0x1800a482e  jmp     short loc_1800A480C
0x1800a4830  mov     edx, 54h ; 'T'; nAclLength
0x1800a4835  mov     rcx, rdi; pAcl
0x1800a4838  lea     r8d, [rdx-52h]; dwAclRevision
0x1800a483c  call    cs:__imp_InitializeAcl
0x1800a4842  mov     edx, 2; dwAceRevision
0x1800a4847  lea     r9, ?NetworkService@@3U_SID@@B; pSid
0x1800a484e  mov     rcx, rdi; pAcl
0x1800a4851  lea     r8d, [rdx+2]; AccessMask
0x1800a4855  call    cs:__imp_AddAccessAllowedAce
0x1800a485b  mov     edx, 2; dwAceRevision
0x1800a4860  lea     r9, ?Admin1@@3U_RPC_SID2@@B; pSid
0x1800a4867  mov     rcx, rdi; pAcl
0x1800a486a  lea     r8d, [rdx+2]; AccessMask
0x1800a486e  call    cs:__imp_AddAccessAllowedAce
0x1800a4874  mov     rcx, [rbx+50h]; pSecurityDescriptor
0x1800a4878  xor     r9d, r9d; bDaclDefaulted
0x1800a487b  mov     r8, rdi; pDacl
0x1800a487e  lea     edx, [r9+1]; bDaclPresent
0x1800a4882  call    cs:__imp_SetSecurityDescriptorDacl
0x1800a4888  xor     eax, eax
0x1800a488a  mov     rbx, [rsp+28h+arg_0]
0x1800a488f  add     rsp, 20h
0x1800a4893  pop     rdi
0x1800a4894  retn
```
