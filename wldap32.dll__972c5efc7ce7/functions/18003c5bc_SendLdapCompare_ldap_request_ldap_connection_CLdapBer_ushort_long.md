# SendLdapCompare(ldap_request *,ldap_connection *,CLdapBer * *,ushort *,long)

- ea: `0x18003c5bc`
- end: `0x18003c98b`
- name: `?SendLdapCompare@@YAKPEAUldap_request@@PEAUldap_connection@@PEAPEAVCLdapBer@@PEAGJ@Z`
- size: `975`
- prototype: `unsigned int __usercall@<eax>(struct ldap_request *@<rcx>, struct ldap_connection *@<rdx>, struct CLdapBer **@<r8>, unsigned __int16 *@<r9>, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18002cf6c`
- `0x18003c254`

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
- `0x180029d28`
- `0x18002a9f8`
- `0x18002b020`
- `0x18002dbac`
- `0x18003c5bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c8de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c8de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c94e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c94e`

## string_xrefs

- `0x18003c681`: `ldap_compare startWrite connection 0x%x encoding error of 0x%x.\n`
- `0x18003c6d9`: `ldap_compare MsgNo connection 0x%x encoding error of 0x%x.\n`
- `0x18003c722`: `ldap_compare cmd connection 0x%x encoding error of 0x%x.\n`
- `0x18003c76f`: `ldap_compare DN connection 0x%x encoding error of 0x%x.\n`
- `0x18003c7b8`: `ldap_compare 1 connection 0x%x encoding error of 0x%x.\n`
- `0x18003c803`: `ldap_compare 2 connection 0x%x encoding error of 0x%x.\n`
- `0x18003c863`: `ldap_compare 3 connection 0x%x encoding error of 0x%x.\n`
- `0x18003c92c`: `ldap_compare connection 0x%x send with error of 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SendLdapCompare(
        struct ldap_request *a1,
        struct ldap_connection *a2,
        struct CLdapBer **a3,
        unsigned __int16 *a4,
        int a5)
{
  const unsigned __int16 *v5; // r14
  const unsigned __int16 *v7; // r12
  __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // edx
  int v15; // edx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // r8d
  unsigned __int8 *v22; // rdx
  unsigned int v23; // eax
  unsigned int v25; // edx
  unsigned int inserted; // ebp
  unsigned int v27; // eax

  v5 = (const unsigned __int16 *)*((_QWORD *)a1 + 29);
  v7 = (const unsigned __int16 *)*((_QWORD *)a1 + 30);
  v11 = ldapMalloc(872, 1816347212);
  if ( v11 )
  {
    v12 = *((_DWORD *)a2 + 250) - 2;
    *(_QWORD *)v11 = 0;
    *(_DWORD *)(v11 + 8) = 0;
    *(_QWORD *)(v11 + 16) = 0;
    *(_QWORD *)(v11 + 836) = 0;
    *(_QWORD *)(v11 + 24) = 0;
    *(_BYTE *)(v11 + 856) = 0;
    *(_DWORD *)(v11 + 864) = 0;
    *(_DWORD *)(v11 + 860) = v12 != 0 ? 0xFDE9 : 0;
    *(_DWORD *)(v11 + 32) = 0;
    v13 = CLdapBer::HrStartWriteSequence((CLdapBer *)v11, 0x30u);
    if ( v13 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_compare startWrite connection 0x%x encoding error of 0x%x.\n", a2, v13);
LABEL_43:
      CLdapBer::`scalar deleting destructor'((CLdapBer *)v11, v14);
      return 83;
    }
    v15 = a5;
    if ( !a5 )
      v15 = *((_DWORD *)a1 + 27);
    v16 = CLdapBer::HrAddValue((CLdapBer *)v11, v15, 2u);
    if ( v16 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_compare MsgNo connection 0x%x encoding error of 0x%x.\n", a2, v16);
      goto LABEL_43;
    }
    v17 = CLdapBer::HrStartWriteSequence((CLdapBer *)v11, 0x6Eu);
    if ( v17 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_compare cmd connection 0x%x encoding error of 0x%x.\n", a2, v17);
      goto LABEL_43;
    }
    v18 = CLdapBer::HrAddValue((CLdapBer *)v11, a4, 4u);
    if ( v18 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_compare DN connection 0x%x encoding error of 0x%x.\n", a2, v18);
      goto LABEL_43;
    }
    v19 = CLdapBer::HrStartWriteSequence((CLdapBer *)v11, 0x30u);
    if ( v19 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_compare 1 connection 0x%x encoding error of 0x%x.\n", a2, v19);
      goto LABEL_43;
    }
    v20 = CLdapBer::HrAddValue((CLdapBer *)v11, v5, 4u);
    if ( v20 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_compare 2 connection 0x%x encoding error of 0x%x.\n", a2, v20);
      goto LABEL_43;
    }
    v21 = *((_DWORD *)a1 + 62);
    if ( v21 && (v22 = (unsigned __int8 *)*((_QWORD *)a1 + 32)) != 0 )
      v23 = CLdapBer::HrAddBinaryValue((CLdapBer *)v11, v22, v21, 4u);
    else
      v23 = CLdapBer::HrAddValue((CLdapBer *)v11, v7, 4u);
    if ( v23 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_compare 3 connection 0x%x encoding error of 0x%x.\n", a2, v23);
      goto LABEL_43;
    }
    CLdapBer::HrEndWriteSequence((CLdapBer *)v11);
    CLdapBer::HrEndWriteSequence((CLdapBer *)v11);
    if ( *((_DWORD *)a2 + 250) != 2 )
    {
      if ( *((_QWORD *)a1 + 25) )
      {
        inserted = InsertServerControls(a1, a2, (struct CLdapBer *)v11);
        if ( inserted )
          goto LABEL_47;
      }
    }
    CLdapBer::HrEndWriteSequence((CLdapBer *)v11);
    EnterCriticalSection((LPCRITICAL_SECTION)a2 + 14);
    AddToPendingList(a1, a2);
    v27 = LdapSend(a2, (struct CLdapBer *)v11, 0);
    inserted = v27;
    if ( v27 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
        LDAPClientPrint(0x100000, "ldap_compare connection 0x%x send with error of 0x%x.\n", (_DWORD)a2, v27);
      DecrementPendingList(a1, a2);
    }
    else
    {
      v11 = _InterlockedExchange64((volatile __int64 *)a3, v11);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)a2 + 14);
    if ( v11 )
LABEL_47:
      CLdapBer::`scalar deleting destructor'((CLdapBer *)v11, v25);
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
0x18003c5bc  push    rbx
0x18003c5be  push    rbp
0x18003c5bf  push    rsi
0x18003c5c0  push    rdi
0x18003c5c1  push    r12
0x18003c5c3  push    r13
0x18003c5c5  push    r14
0x18003c5c7  push    r15
0x18003c5c9  sub     rsp, 28h
0x18003c5cd  mov     r14, [rcx+0E8h]
0x18003c5d4  mov     rdi, rdx
0x18003c5d7  mov     r12, [rcx+0F0h]
0x18003c5de  mov     rsi, rcx
0x18003c5e1  mov     edx, 6C43424Ch
0x18003c5e6  mov     ecx, 368h
0x18003c5eb  mov     rbp, r9
0x18003c5ee  mov     r15, r8
0x18003c5f1  call    ldapMalloc
0x18003c5f6  xor     r13d, r13d
0x18003c5f9  mov     rbx, rax
0x18003c5fc  test    rax, rax
0x18003c5ff  jz      loc_18003C968
0x18003c605  mov     eax, [rdi+3E8h]
0x18003c60b  lea     edx, [r13+30h]; unsigned int
0x18003c60f  sub     eax, 2
0x18003c612  mov     [rbx], r13
0x18003c615  neg     eax
0x18003c617  mov     [rbx+8], r13d
0x18003c61b  mov     [rbx+10h], r13
0x18003c61f  mov     rcx, rbx; this
0x18003c622  sbb     eax, eax
0x18003c624  mov     [rbx+344h], r13
0x18003c62b  and     eax, 0FDE9h
0x18003c630  mov     [rbx+18h], r13
0x18003c634  mov     [rbx+358h], r13b
0x18003c63b  mov     [rbx+360h], r13d
0x18003c642  mov     [rbx+35Ch], eax
0x18003c648  mov     [rbx+20h], r13d
0x18003c64c  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18003c651  test    eax, eax
0x18003c653  jz      short loc_18003C68D
0x18003c655  cmp     cs:g_fTracingOn, r13d
0x18003c65c  jz      loc_18003C875
0x18003c662  cmp     cs:g_fProviderEnabled, r13d
0x18003c669  jz      loc_18003C875
0x18003c66f  mov     ecx, 400000h
0x18003c674  test    cs:g_ulTraceFlags, rcx
0x18003c67b  jz      loc_18003C875
0x18003c681  lea     rdx, aLdapCompareSta; "ldap_compare startWrite connection 0x%x"...
0x18003c688  jmp     loc_18003C86A
0x18003c68d  mov     edx, [rsp+68h+arg_20]
0x18003c694  test    edx, edx
0x18003c696  jnz     short loc_18003C69B
0x18003c698  mov     edx, [rsi+6Ch]; int
0x18003c69b  mov     r8d, 2; unsigned int
0x18003c6a1  mov     rcx, rbx; this
0x18003c6a4  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x18003c6a9  test    eax, eax
0x18003c6ab  jz      short loc_18003C6E5
0x18003c6ad  cmp     cs:g_fTracingOn, r13d
0x18003c6b4  jz      loc_18003C875
0x18003c6ba  cmp     cs:g_fProviderEnabled, r13d
0x18003c6c1  jz      loc_18003C875
0x18003c6c7  mov     ecx, 400000h
0x18003c6cc  test    cs:g_ulTraceFlags, rcx
0x18003c6d3  jz      loc_18003C875
0x18003c6d9  lea     rdx, aLdapCompareMsg; "ldap_compare MsgNo connection 0x%x enco"...
0x18003c6e0  jmp     loc_18003C86A
0x18003c6e5  mov     edx, 6Eh ; 'n'; unsigned int
0x18003c6ea  mov     rcx, rbx; this
0x18003c6ed  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18003c6f2  test    eax, eax
0x18003c6f4  jz      short loc_18003C72E
0x18003c6f6  cmp     cs:g_fTracingOn, r13d
0x18003c6fd  jz      loc_18003C875
0x18003c703  cmp     cs:g_fProviderEnabled, r13d
0x18003c70a  jz      loc_18003C875
0x18003c710  mov     ecx, 400000h
0x18003c715  test    cs:g_ulTraceFlags, rcx
0x18003c71c  jz      loc_18003C875
0x18003c722  lea     rdx, aLdapCompareCmd; "ldap_compare cmd connection 0x%x encodi"...
0x18003c729  jmp     loc_18003C86A
0x18003c72e  mov     r8d, 4; unsigned int
0x18003c734  mov     rdx, rbp; unsigned __int16 *
0x18003c737  mov     rcx, rbx; this
0x18003c73a  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x18003c73f  test    eax, eax
0x18003c741  jz      short loc_18003C77B
0x18003c743  cmp     cs:g_fTracingOn, r13d
0x18003c74a  jz      loc_18003C875
0x18003c750  cmp     cs:g_fProviderEnabled, r13d
0x18003c757  jz      loc_18003C875
0x18003c75d  mov     ecx, 400000h
0x18003c762  test    cs:g_ulTraceFlags, rcx
0x18003c769  jz      loc_18003C875
0x18003c76f  lea     rdx, aLdapCompareDnC; "ldap_compare DN connection 0x%x encodin"...
0x18003c776  jmp     loc_18003C86A
0x18003c77b  mov     edx, 30h ; '0'; unsigned int
0x18003c780  mov     rcx, rbx; this
0x18003c783  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18003c788  test    eax, eax
0x18003c78a  jz      short loc_18003C7C4
0x18003c78c  cmp     cs:g_fTracingOn, r13d
0x18003c793  jz      loc_18003C875
0x18003c799  cmp     cs:g_fProviderEnabled, r13d
0x18003c7a0  jz      loc_18003C875
0x18003c7a6  mov     ecx, 400000h
0x18003c7ab  test    cs:g_ulTraceFlags, rcx
0x18003c7b2  jz      loc_18003C875
0x18003c7b8  lea     rdx, aLdapCompare1Co; "ldap_compare 1 connection 0x%x encoding"...
0x18003c7bf  jmp     loc_18003C86A
0x18003c7c4  mov     ebp, 4
0x18003c7c9  mov     rdx, r14; unsigned __int16 *
0x18003c7cc  mov     r8d, ebp; unsigned int
0x18003c7cf  mov     rcx, rbx; this
0x18003c7d2  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x18003c7d7  test    eax, eax
0x18003c7d9  jz      short loc_18003C80C
0x18003c7db  cmp     cs:g_fTracingOn, r13d
0x18003c7e2  jz      loc_18003C875
0x18003c7e8  cmp     cs:g_fProviderEnabled, r13d
0x18003c7ef  jz      loc_18003C875
0x18003c7f5  mov     ecx, 400000h
0x18003c7fa  test    cs:g_ulTraceFlags, rcx
0x18003c801  jz      short loc_18003C875
0x18003c803  lea     rdx, aLdapCompare2Co; "ldap_compare 2 connection 0x%x encoding"...
0x18003c80a  jmp     short loc_18003C86A
0x18003c80c  mov     r8d, [rsi+0F8h]; unsigned int
0x18003c813  test    r8d, r8d
0x18003c816  jz      short loc_18003C831
0x18003c818  mov     rdx, [rsi+100h]; unsigned __int8 *
0x18003c81f  test    rdx, rdx
0x18003c822  jz      short loc_18003C831
0x18003c824  mov     r9d, ebp; unsigned int
0x18003c827  mov     rcx, rbx; this
0x18003c82a  call    ?HrAddBinaryValue@CLdapBer@@QEAAKPEAEKK@Z; CLdapBer::HrAddBinaryValue(uchar *,ulong,ulong)
0x18003c82f  jmp     short loc_18003C83F
0x18003c831  mov     r8d, ebp; unsigned int
0x18003c834  mov     rdx, r12; unsigned __int16 *
0x18003c837  mov     rcx, rbx; this
0x18003c83a  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x18003c83f  test    eax, eax
0x18003c841  jz      short loc_18003C887
0x18003c843  cmp     cs:g_fTracingOn, r13d
0x18003c84a  jz      short loc_18003C875
0x18003c84c  cmp     cs:g_fProviderEnabled, r13d
0x18003c853  jz      short loc_18003C875
0x18003c855  mov     ecx, 400000h
0x18003c85a  test    cs:g_ulTraceFlags, rcx
0x18003c861  jz      short loc_18003C875
0x18003c863  lea     rdx, aLdapCompare3Co; "ldap_compare 3 connection 0x%x encoding"...
0x18003c86a  mov     r9d, eax
0x18003c86d  mov     r8, rdi
0x18003c870  call    LDAPClientPrint
0x18003c875  mov     rcx, rbx; this
0x18003c878  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18003c87d  mov     eax, 53h ; 'S'
0x18003c882  jmp     loc_18003C979
0x18003c887  mov     rcx, rbx; this
0x18003c88a  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18003c88f  mov     rcx, rbx; this
0x18003c892  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18003c897  cmp     dword ptr [rdi+3E8h], 2
0x18003c89e  jz      short loc_18003C8CC
0x18003c8a0  cmp     [rsi+0C8h], r13
0x18003c8a7  jz      short loc_18003C8CC
0x18003c8a9  mov     r8, rbx; struct CLdapBer *
0x18003c8ac  mov     rdx, rdi; struct ldap_connection *
0x18003c8af  mov     rcx, rsi; struct ldap_request *
0x18003c8b2  call    ?InsertServerControls@@YAKPEAUldap_request@@PEAUldap_connection@@PEAVCLdapBer@@@Z; InsertServerControls(ldap_request *,ldap_connection *,CLdapBer *)
0x18003c8b7  mov     ebp, eax
0x18003c8b9  test    eax, eax
0x18003c8bb  jz      short loc_18003C8CC
0x18003c8bd  mov     rcx, rbx; this
0x18003c8c0  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18003c8c5  mov     eax, ebp
0x18003c8c7  jmp     loc_18003C979
0x18003c8cc  mov     rcx, rbx; this
0x18003c8cf  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18003c8d4  lea     r14, [rdi+230h]
0x18003c8db  mov     rcx, r14; lpCriticalSection
0x18003c8de  call    cs:__imp_EnterCriticalSection
0x18003c8e5  nop     dword ptr [rax+rax+00h]
0x18003c8ea  mov     rdx, rdi
0x18003c8ed  mov     rcx, rsi
0x18003c8f0  call    AddToPendingList
0x18003c8f5  xor     r8d, r8d; struct CLdapBer *
0x18003c8f8  mov     rdx, rbx; struct CLdapBer *
0x18003c8fb  mov     rcx, rdi; struct ldap_connection *
0x18003c8fe  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x18003c903  mov     ebp, eax
0x18003c905  test    eax, eax
0x18003c907  jz      short loc_18003C948
0x18003c909  cmp     cs:g_fTracingOn, r13d
0x18003c910  jz      short loc_18003C93B
0x18003c912  cmp     cs:g_fProviderEnabled, r13d
0x18003c919  jz      short loc_18003C93B
0x18003c91b  mov     ecx, 100000h
0x18003c920  test    cs:g_ulTraceFlags, rcx
0x18003c927  jz      short loc_18003C93B
0x18003c929  mov     r9d, eax
0x18003c92c  lea     rdx, aLdapCompareCon_1; "ldap_compare connection 0x%x send with "...
0x18003c933  mov     r8, rdi
0x18003c936  call    LDAPClientPrint
0x18003c93b  mov     rdx, rdi
0x18003c93e  mov     rcx, rsi
0x18003c941  call    DecrementPendingList
0x18003c946  jmp     short loc_18003C94B
0x18003c948  xchg    rbx, [r15]
0x18003c94b  mov     rcx, r14; lpCriticalSection
0x18003c94e  call    cs:__imp_LeaveCriticalSection
0x18003c955  nop     dword ptr [rax+rax+00h]
0x18003c95a  test    rbx, rbx
0x18003c95d  jz      loc_18003C8C5
0x18003c963  jmp     loc_18003C8BD
0x18003c968  mov     ebx, 5Ah ; 'Z'
0x18003c96d  mov     rcx, rdi
0x18003c970  mov     edx, ebx
0x18003c972  call    SetConnectionError
0x18003c977  mov     eax, ebx
0x18003c979  add     rsp, 28h
0x18003c97d  pop     r15
0x18003c97f  pop     r14
0x18003c981  pop     r13
0x18003c983  pop     r12
0x18003c985  pop     rdi
0x18003c986  pop     rsi
0x18003c987  pop     rbp
0x18003c988  pop     rbx
0x18003c989  retn
```
