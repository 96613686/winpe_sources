# SendLdapDelete(ldap_request *,ldap_connection *,ushort *,CLdapBer * *,long)

- ea: `0x18003e508`
- end: `0x18003e75e`
- name: `?SendLdapDelete@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAVCLdapBer@@J@Z`
- size: `598`
- prototype: `unsigned int __usercall@<eax>(struct ldap_request *@<rcx>, struct ldap_connection *@<rdx>, unsigned __int16 *@<r8>, struct CLdapBer **@<r9>, int)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x18002cf6c`
- `0x18003e250`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000df44`
- `0x180010ef0`
- `0x180011c80`
- `0x180011f50`
- `0x180014060`
- `0x180014460`
- `0x18001ce90`
- `0x18002a9f8`
- `0x18002b020`
- `0x18002dbac`
- `0x18003e508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e6b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e6b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e723`

## string_xrefs

- `0x18003e5be`: `ldap_delete startWrite conn 0x%x encoding error of 0x%x.\n`
- `0x18003e60a`: `ldap_delete MsgNo conn 0x%x encoding error of 0x%x.\n`
- `0x18003e648`: `ldap_delete DN conn 0x%x encoding error of 0x%x.\n`
- `0x18003e701`: `ldap_delete connection 0x%x send with error of 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SendLdapDelete(
        struct ldap_request *a1,
        struct ldap_connection *a2,
        unsigned __int16 *a3,
        struct CLdapBer **a4,
        int a5)
{
  __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // edx
  int v13; // edx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v17; // edx
  unsigned int inserted; // ebp
  unsigned int v19; // eax

  v9 = ldapMalloc(872, 1816347212);
  if ( v9 )
  {
    v10 = *((_DWORD *)a2 + 250) - 2;
    *(_QWORD *)v9 = 0;
    *(_DWORD *)(v9 + 8) = 0;
    *(_QWORD *)(v9 + 16) = 0;
    *(_QWORD *)(v9 + 836) = 0;
    *(_QWORD *)(v9 + 24) = 0;
    *(_BYTE *)(v9 + 856) = 0;
    *(_DWORD *)(v9 + 864) = 0;
    *(_DWORD *)(v9 + 860) = v10 != 0 ? 0xFDE9 : 0;
    *(_DWORD *)(v9 + 32) = 0;
    v11 = CLdapBer::HrStartWriteSequence((CLdapBer *)v9, 0x30u);
    if ( v11 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_delete startWrite conn 0x%x encoding error of 0x%x.\n", a2, v11);
LABEL_19:
      CLdapBer::`scalar deleting destructor'((CLdapBer *)v9, v12);
      return 83;
    }
    v13 = a5;
    if ( !a5 )
      v13 = *((_DWORD *)a1 + 27);
    v14 = CLdapBer::HrAddValue((CLdapBer *)v9, v13, 2u);
    if ( v14 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_delete MsgNo conn 0x%x encoding error of 0x%x.\n", a2, v14);
      goto LABEL_19;
    }
    v15 = CLdapBer::HrAddValue((CLdapBer *)v9, a3, 0x4Au);
    if ( v15 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_delete DN conn 0x%x encoding error of 0x%x.\n", a2, v15);
      goto LABEL_19;
    }
    if ( *((_DWORD *)a2 + 250) != 2 )
    {
      if ( *((_QWORD *)a1 + 25) )
      {
        inserted = InsertServerControls(a1, a2, (struct CLdapBer *)v9);
        if ( inserted )
          goto LABEL_23;
      }
    }
    CLdapBer::HrEndWriteSequence((CLdapBer *)v9);
    EnterCriticalSection((LPCRITICAL_SECTION)a2 + 14);
    AddToPendingList(a1, a2);
    v19 = LdapSend(a2, (struct CLdapBer *)v9, 0);
    inserted = v19;
    if ( v19 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
        LDAPClientPrint(0x100000, "ldap_delete connection 0x%x send with error of 0x%x.\n", (_DWORD)a2, v19);
      DecrementPendingList(a1, a2);
    }
    else
    {
      v9 = _InterlockedExchange64((volatile __int64 *)a4, v9);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)a2 + 14);
    if ( v9 )
LABEL_23:
      CLdapBer::`scalar deleting destructor'((CLdapBer *)v9, v17);
    return inserted;
  }
  else
  {
    SetConnectionError(a2, 90);
    return 90;
  }
}

```

## disassembly

```asm
0x18003e508  push    rbx
0x18003e50a  push    rbp
0x18003e50b  push    rsi
0x18003e50c  push    rdi
0x18003e50d  push    r12
0x18003e50f  push    r14
0x18003e511  push    r15
0x18003e513  sub     rsp, 20h
0x18003e517  mov     rdi, rdx
0x18003e51a  mov     rsi, rcx
0x18003e51d  mov     edx, 6C43424Ch
0x18003e522  mov     ecx, 368h
0x18003e527  mov     r15, r9
0x18003e52a  mov     rbp, r8
0x18003e52d  call    ldapMalloc
0x18003e532  xor     r12d, r12d
0x18003e535  mov     rbx, rax
0x18003e538  test    rax, rax
0x18003e53b  jz      loc_18003E73D
0x18003e541  mov     eax, [rdi+3E8h]
0x18003e547  lea     edx, [r12+30h]; unsigned int
0x18003e54c  sub     eax, 2
0x18003e54f  mov     [rbx], r12
0x18003e552  neg     eax
0x18003e554  mov     [rbx+8], r12d
0x18003e558  mov     [rbx+10h], r12
0x18003e55c  mov     rcx, rbx; this
0x18003e55f  sbb     eax, eax
0x18003e561  mov     [rbx+344h], r12
0x18003e568  and     eax, 0FDE9h
0x18003e56d  mov     [rbx+18h], r12
0x18003e571  mov     [rbx+358h], r12b
0x18003e578  mov     [rbx+360h], r12d
0x18003e57f  mov     [rbx+35Ch], eax
0x18003e585  mov     [rbx+20h], r12d
0x18003e589  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18003e58e  test    eax, eax
0x18003e590  jz      short loc_18003E5CA
0x18003e592  cmp     cs:g_fTracingOn, r12d
0x18003e599  jz      loc_18003E65A
0x18003e59f  cmp     cs:g_fProviderEnabled, r12d
0x18003e5a6  jz      loc_18003E65A
0x18003e5ac  mov     ecx, 400000h
0x18003e5b1  test    cs:g_ulTraceFlags, rcx
0x18003e5b8  jz      loc_18003E65A
0x18003e5be  lea     rdx, aLdapDeleteStar; "ldap_delete startWrite conn 0x%x encodi"...
0x18003e5c5  jmp     loc_18003E64F
0x18003e5ca  mov     edx, [rsp+58h+arg_20]
0x18003e5d1  test    edx, edx
0x18003e5d3  jnz     short loc_18003E5D8
0x18003e5d5  mov     edx, [rsi+6Ch]; int
0x18003e5d8  mov     r8d, 2; unsigned int
0x18003e5de  mov     rcx, rbx; this
0x18003e5e1  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x18003e5e6  test    eax, eax
0x18003e5e8  jz      short loc_18003E613
0x18003e5ea  cmp     cs:g_fTracingOn, r12d
0x18003e5f1  jz      short loc_18003E65A
0x18003e5f3  cmp     cs:g_fProviderEnabled, r12d
0x18003e5fa  jz      short loc_18003E65A
0x18003e5fc  mov     ecx, 400000h
0x18003e601  test    cs:g_ulTraceFlags, rcx
0x18003e608  jz      short loc_18003E65A
0x18003e60a  lea     rdx, aLdapDeleteMsgn; "ldap_delete MsgNo conn 0x%x encoding er"...
0x18003e611  jmp     short loc_18003E64F
0x18003e613  mov     r8d, 4Ah ; 'J'; unsigned int
0x18003e619  mov     rdx, rbp; unsigned __int16 *
0x18003e61c  mov     rcx, rbx; this
0x18003e61f  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x18003e624  test    eax, eax
0x18003e626  jz      short loc_18003E66C
0x18003e628  cmp     cs:g_fTracingOn, r12d
0x18003e62f  jz      short loc_18003E65A
0x18003e631  cmp     cs:g_fProviderEnabled, r12d
0x18003e638  jz      short loc_18003E65A
0x18003e63a  mov     ecx, 400000h
0x18003e63f  test    cs:g_ulTraceFlags, rcx
0x18003e646  jz      short loc_18003E65A
0x18003e648  lea     rdx, aLdapDeleteDnCo; "ldap_delete DN conn 0x%x encoding error"...
0x18003e64f  mov     r9d, eax
0x18003e652  mov     r8, rdi
0x18003e655  call    LDAPClientPrint
0x18003e65a  mov     rcx, rbx; this
0x18003e65d  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18003e662  mov     eax, 53h ; 'S'
0x18003e667  jmp     loc_18003E74E
0x18003e66c  cmp     dword ptr [rdi+3E8h], 2
0x18003e673  jz      short loc_18003E6A1
0x18003e675  cmp     [rsi+0C8h], r12
0x18003e67c  jz      short loc_18003E6A1
0x18003e67e  mov     r8, rbx; struct CLdapBer *
0x18003e681  mov     rdx, rdi; struct ldap_connection *
0x18003e684  mov     rcx, rsi; struct ldap_request *
0x18003e687  call    ?InsertServerControls@@YAKPEAUldap_request@@PEAUldap_connection@@PEAVCLdapBer@@@Z; InsertServerControls(ldap_request *,ldap_connection *,CLdapBer *)
0x18003e68c  mov     ebp, eax
0x18003e68e  test    eax, eax
0x18003e690  jz      short loc_18003E6A1
0x18003e692  mov     rcx, rbx; this
0x18003e695  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18003e69a  mov     eax, ebp
0x18003e69c  jmp     loc_18003E74E
0x18003e6a1  mov     rcx, rbx; this
0x18003e6a4  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18003e6a9  lea     r14, [rdi+230h]
0x18003e6b0  mov     rcx, r14; lpCriticalSection
0x18003e6b3  call    cs:__imp_EnterCriticalSection
0x18003e6ba  nop     dword ptr [rax+rax+00h]
0x18003e6bf  mov     rdx, rdi
0x18003e6c2  mov     rcx, rsi
0x18003e6c5  call    AddToPendingList
0x18003e6ca  xor     r8d, r8d; struct CLdapBer *
0x18003e6cd  mov     rdx, rbx; struct CLdapBer *
0x18003e6d0  mov     rcx, rdi; struct ldap_connection *
0x18003e6d3  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x18003e6d8  mov     ebp, eax
0x18003e6da  test    eax, eax
0x18003e6dc  jz      short loc_18003E71D
0x18003e6de  cmp     cs:g_fTracingOn, r12d
0x18003e6e5  jz      short loc_18003E710
0x18003e6e7  cmp     cs:g_fProviderEnabled, r12d
0x18003e6ee  jz      short loc_18003E710
0x18003e6f0  mov     ecx, 100000h
0x18003e6f5  test    cs:g_ulTraceFlags, rcx
0x18003e6fc  jz      short loc_18003E710
0x18003e6fe  mov     r9d, eax
0x18003e701  lea     rdx, aLdapDeleteConn_0; "ldap_delete connection 0x%x send with e"...
0x18003e708  mov     r8, rdi
0x18003e70b  call    LDAPClientPrint
0x18003e710  mov     rdx, rdi
0x18003e713  mov     rcx, rsi
0x18003e716  call    DecrementPendingList
0x18003e71b  jmp     short loc_18003E720
0x18003e71d  xchg    rbx, [r15]
0x18003e720  mov     rcx, r14; lpCriticalSection
0x18003e723  call    cs:__imp_LeaveCriticalSection
0x18003e72a  nop     dword ptr [rax+rax+00h]
0x18003e72f  test    rbx, rbx
0x18003e732  jz      loc_18003E69A
0x18003e738  jmp     loc_18003E692
0x18003e73d  mov     ebx, 5Ah ; 'Z'
0x18003e742  mov     rcx, rdi
0x18003e745  mov     edx, ebx
0x18003e747  call    SetConnectionError
0x18003e74c  mov     eax, ebx
0x18003e74e  add     rsp, 20h
0x18003e752  pop     r15
0x18003e754  pop     r14
0x18003e756  pop     r12
0x18003e758  pop     rdi
0x18003e759  pop     rsi
0x18003e75a  pop     rbp
0x18003e75b  pop     rbx
0x18003e75c  retn
```
