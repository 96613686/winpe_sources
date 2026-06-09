# CellHeap::CreateSecurityDescriptor(void)

- ea: `0x1800a7fa8`
- end: `0x1800a8090`
- name: `?CreateSecurityDescriptor@CellHeap@@AEAAJXZ`
- size: `232`
- prototype: `__int64 __fastcall(CellHeap *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800a7f30`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800a7fa8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800a8076`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800a8076`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800a7ffc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800a7ffc`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800a803d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800a805c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800a803d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800a805c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800a801e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800a801e`

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
0x1800a7fa8  mov     [rsp+arg_0], rbx
0x1800a7fad  push    rdi
0x1800a7fae  sub     rsp, 20h
0x1800a7fb2  mov     rbx, rcx
0x1800a7fb5  mov     ecx, 28h ; '('; dwBytes
0x1800a7fba  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a7fbf  mov     [rbx+50h], rax
0x1800a7fc3  test    rax, rax
0x1800a7fc6  jnz     short loc_1800A7FD2
0x1800a7fc8  mov     eax, 0Eh
0x1800a7fcd  jmp     loc_1800A8084
0x1800a7fd2  mov     ecx, 54h ; 'T'; dwBytes
0x1800a7fd7  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a7fdc  mov     rcx, [rbx+50h]; lpMem
0x1800a7fe0  mov     rdi, rax
0x1800a7fe3  test    rax, rax
0x1800a7fe6  jnz     short loc_1800A7FF7
0x1800a7fe8  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a7fed  mov     qword ptr [rbx+50h], 0
0x1800a7ff5  jmp     short loc_1800A7FC8
0x1800a7ff7  mov     edx, 1; dwRevision
0x1800a7ffc  call    cs:__imp_InitializeSecurityDescriptor
0x1800a8003  nop     dword ptr [rax+rax+00h]
0x1800a8008  test    eax, eax
0x1800a800a  jnz     short loc_1800A8012
0x1800a800c  mov     rcx, [rbx+50h]
0x1800a8010  jmp     short loc_1800A7FE8
0x1800a8012  mov     edx, 54h ; 'T'; nAclLength
0x1800a8017  mov     rcx, rdi; pAcl
0x1800a801a  lea     r8d, [rdx-52h]; dwAclRevision
0x1800a801e  call    cs:__imp_InitializeAcl
0x1800a8025  nop     dword ptr [rax+rax+00h]
0x1800a802a  mov     edx, 2; dwAceRevision
0x1800a802f  lea     r9, ?NetworkService@@3U_SID@@B; pSid
0x1800a8036  mov     rcx, rdi; pAcl
0x1800a8039  lea     r8d, [rdx+2]; AccessMask
0x1800a803d  call    cs:__imp_AddAccessAllowedAce
0x1800a8044  nop     dword ptr [rax+rax+00h]
0x1800a8049  mov     edx, 2; dwAceRevision
0x1800a804e  lea     r9, ?Admin1@@3U_RPC_SID2@@B; pSid
0x1800a8055  mov     rcx, rdi; pAcl
0x1800a8058  lea     r8d, [rdx+2]; AccessMask
0x1800a805c  call    cs:__imp_AddAccessAllowedAce
0x1800a8063  nop     dword ptr [rax+rax+00h]
0x1800a8068  mov     rcx, [rbx+50h]; pSecurityDescriptor
0x1800a806c  xor     r9d, r9d; bDaclDefaulted
0x1800a806f  mov     r8, rdi; pDacl
0x1800a8072  lea     edx, [r9+1]; bDaclPresent
0x1800a8076  call    cs:__imp_SetSecurityDescriptorDacl
0x1800a807d  nop     dword ptr [rax+rax+00h]
0x1800a8082  xor     eax, eax
0x1800a8084  mov     rbx, [rsp+28h+arg_0]
0x1800a8089  add     rsp, 20h
0x1800a808d  pop     rdi
0x1800a808e  retn
```
