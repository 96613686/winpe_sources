# SendLdapAdd(ldap_request *,ldap_connection *,ushort *,ldapmodW * * const,CLdapBer * *,uchar,long)

- ea: `0x18003a274`
- end: `0x18003a5f9`
- name: `?SendLdapAdd@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGQEAPEAUldapmodW@@PEAPEAVCLdapBer@@EJ@Z`
- size: `901`
- prototype: `unsigned int __fastcall(struct ldap_request *, struct ldap_connection *, unsigned __int16 *, struct ldapmodW **const, struct CLdapBer **, unsigned __int8, int)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x18002cf6c`
- `0x180039f4c`

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
- `0x180039cd0`
- `0x18003a274`
- `0x18003d2b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a549`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a549`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a5c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a5c0`

## string_xrefs

- `0x18003a371`: `ldap_add startWrite connection 0x%x encoding error of 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SendLdapAdd(
        struct ldap_request *a1,
        struct ldap_connection *a2,
        unsigned __int16 *a3,
        struct ldapmodW **const a4,
        struct CLdapBer **a5,
        unsigned __int8 a6,
        int a7)
{
  int v11; // edx
  unsigned int v12; // ebx
  __int64 v13; // rdi
  int v14; // eax
  unsigned int v15; // eax
  int v16; // edx
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v22; // eax
  unsigned int inserted; // r14d
  unsigned int v24; // eax

  if ( *((_DWORD *)a2 + 250) == 2 && (unsigned __int8)LdapCheckForMandatoryControl(*((_QWORD *)a1 + 25)) == 1 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
      LDAPClientPrint(0x8000, "SendLdapAdd Connection 0x%x has mandatory controls.\n", v11);
    v12 = 12;
    goto LABEL_57;
  }
  v13 = ldapMalloc(872, 1816347212);
  if ( v13 )
  {
    v14 = *((_DWORD *)a2 + 250) - 2;
    *(_QWORD *)v13 = 0;
    *(_DWORD *)(v13 + 8) = 0;
    *(_QWORD *)(v13 + 16) = 0;
    *(_QWORD *)(v13 + 836) = 0;
    *(_QWORD *)(v13 + 24) = 0;
    *(_BYTE *)(v13 + 856) = 0;
    *(_DWORD *)(v13 + 864) = 0;
    *(_DWORD *)(v13 + 860) = v14 != 0 ? 0xFDE9 : 0;
    *(_DWORD *)(v13 + 32) = 0;
    v15 = CLdapBer::HrStartWriteSequence((CLdapBer *)v13, 0x30u);
    if ( v15 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_add startWrite connection 0x%x encoding error of 0x%x.\n", a2, v15);
LABEL_36:
      CLdapBer::`scalar deleting destructor'((CLdapBer *)v13);
      return 83;
    }
    v16 = a7;
    if ( !a7 )
      v16 = *((_DWORD *)a1 + 27);
    v17 = CLdapBer::HrAddValue((CLdapBer *)v13, v16, 2u);
    if ( v17 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_add MsgNo connection 0x%x encoding error of 0x%x.\n", a2, v17);
      goto LABEL_36;
    }
    v18 = CLdapBer::HrStartWriteSequence((CLdapBer *)v13, 0x68u);
    if ( v18 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_add cmd connection 0x%x encoding error of 0x%x.\n", a2, v18);
      goto LABEL_36;
    }
    v19 = CLdapBer::HrAddValue((CLdapBer *)v13, a3, 4u);
    if ( v19 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_add DN connection 0x%x encoding error of 0x%x.\n", a2, v19);
      goto LABEL_36;
    }
    v20 = CLdapBer::HrStartWriteSequence((CLdapBer *)v13, 0x30u);
    if ( v20 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_add attrlist connection 0x%x encoding error of 0x%x.\n", a2, v20);
      goto LABEL_36;
    }
    v22 = EncodeAddList((struct CLdapBer *)v13, a4, a6);
    inserted = v22;
    if ( v22 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_add attrlist connection 0x%x encoding error of 0x%x.\n", (_DWORD)a2, v22);
    }
    else
    {
      CLdapBer::HrEndWriteSequence((CLdapBer *)v13);
      CLdapBer::HrEndWriteSequence((CLdapBer *)v13);
      if ( *((_DWORD *)a2 + 250) == 2
        || !*((_QWORD *)a1 + 25)
        || (inserted = InsertServerControls(a1, a2, (struct CLdapBer *)v13)) == 0 )
      {
        CLdapBer::HrEndWriteSequence((CLdapBer *)v13);
        EnterCriticalSection((LPCRITICAL_SECTION)a2 + 14);
        AddToPendingList((__int64)a1, (__int64)a2);
        v24 = LdapSend(a2, (struct CLdapBer *)v13, 0);
        inserted = v24;
        if ( v24 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
            LDAPClientPrint(0x100000, "ldap_add connection 0x%x send with error of 0x%x.\n", (_DWORD)a2, v24);
          DecrementPendingList(a1, a2);
        }
        else
        {
          v13 = _InterlockedExchange64((volatile __int64 *)a5, v13);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)a2 + 14);
        if ( !v13 )
          return inserted;
      }
    }
    CLdapBer::`scalar deleting destructor'((CLdapBer *)v13);
    return inserted;
  }
  v12 = 90;
LABEL_57:
  SetConnectionError(a2, v12);
  return v12;
}

```

## disassembly

```asm
0x18003a274  push    rbx
0x18003a276  push    rbp
0x18003a277  push    rsi
0x18003a278  push    rdi
0x18003a279  push    r14
0x18003a27b  push    r15
0x18003a27d  sub     rsp, 28h
0x18003a281  cmp     dword ptr [rdx+3E8h], 2
0x18003a288  mov     r15, r9
0x18003a28b  mov     r14, r8
0x18003a28e  mov     rsi, rdx
0x18003a291  mov     rbp, rcx
0x18003a294  jnz     short loc_18003A2DF
0x18003a296  mov     rcx, [rcx+0C8h]
0x18003a29d  call    LdapCheckForMandatoryControl
0x18003a2a2  cmp     al, 1
0x18003a2a4  jnz     short loc_18003A2DF
0x18003a2a6  xor     ebx, ebx
0x18003a2a8  cmp     cs:g_fTracingOn, ebx
0x18003a2ae  jz      short loc_18003A2D5
0x18003a2b0  cmp     cs:g_fProviderEnabled, ebx
0x18003a2b6  jz      short loc_18003A2D5
0x18003a2b8  mov     ecx, 8000h
0x18003a2bd  test    cs:g_ulTraceFlags, rcx
0x18003a2c4  jz      short loc_18003A2D5
0x18003a2c6  mov     r8, rdx
0x18003a2c9  lea     rdx, aSendldapaddCon; "SendLdapAdd Connection 0x%x has mandato"...
0x18003a2d0  call    LDAPClientPrint
0x18003a2d5  mov     ebx, 0Ch
0x18003a2da  jmp     loc_18003A5DF
0x18003a2df  mov     edx, 6C43424Ch
0x18003a2e4  mov     ecx, 368h
0x18003a2e9  call    ldapMalloc
0x18003a2ee  xor     ebx, ebx
0x18003a2f0  mov     rdi, rax
0x18003a2f3  test    rax, rax
0x18003a2f6  jz      loc_18003A5DA
0x18003a2fc  mov     eax, [rsi+3E8h]
0x18003a302  lea     edx, [rbx+30h]; unsigned int
0x18003a305  sub     eax, 2
0x18003a308  mov     [rdi], rbx
0x18003a30b  neg     eax
0x18003a30d  mov     [rdi+8], ebx
0x18003a310  mov     [rdi+10h], rbx
0x18003a314  mov     rcx, rdi; this
0x18003a317  sbb     eax, eax
0x18003a319  mov     [rdi+344h], rbx
0x18003a320  and     eax, 0FDE9h
0x18003a325  mov     [rdi+18h], rbx
0x18003a329  mov     [rdi+358h], bl
0x18003a32f  mov     [rdi+360h], ebx
0x18003a335  mov     [rdi+35Ch], eax
0x18003a33b  mov     [rdi+20h], ebx
0x18003a33e  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18003a343  test    eax, eax
0x18003a345  jz      short loc_18003A37D
0x18003a347  cmp     cs:g_fTracingOn, ebx
0x18003a34d  jz      loc_18003A494
0x18003a353  cmp     cs:g_fProviderEnabled, ebx
0x18003a359  jz      loc_18003A494
0x18003a35f  mov     ecx, 400000h
0x18003a364  test    cs:g_ulTraceFlags, rcx
0x18003a36b  jz      loc_18003A494
0x18003a371  lea     rdx, aLdapAddStartwr; "ldap_add startWrite connection 0x%x enc"...
0x18003a378  jmp     loc_18003A489
0x18003a37d  mov     edx, [rsp+58h+arg_30]
0x18003a384  test    edx, edx
0x18003a386  jnz     short loc_18003A38B
0x18003a388  mov     edx, [rbp+6Ch]; int
0x18003a38b  mov     r8d, 2; unsigned int
0x18003a391  mov     rcx, rdi; this
0x18003a394  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x18003a399  test    eax, eax
0x18003a39b  jz      short loc_18003A3D3
0x18003a39d  cmp     cs:g_fTracingOn, ebx
0x18003a3a3  jz      loc_18003A494
0x18003a3a9  cmp     cs:g_fProviderEnabled, ebx
0x18003a3af  jz      loc_18003A494
0x18003a3b5  mov     ecx, 400000h
0x18003a3ba  test    cs:g_ulTraceFlags, rcx
0x18003a3c1  jz      loc_18003A494
0x18003a3c7  lea     rdx, aLdapAddMsgnoCo; "ldap_add MsgNo connection 0x%x encoding"...
0x18003a3ce  jmp     loc_18003A489
0x18003a3d3  mov     edx, 68h ; 'h'; unsigned int
0x18003a3d8  mov     rcx, rdi; this
0x18003a3db  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18003a3e0  test    eax, eax
0x18003a3e2  jz      short loc_18003A417
0x18003a3e4  cmp     cs:g_fTracingOn, ebx
0x18003a3ea  jz      loc_18003A494
0x18003a3f0  cmp     cs:g_fProviderEnabled, ebx
0x18003a3f6  jz      loc_18003A494
0x18003a3fc  mov     ecx, 400000h
0x18003a401  test    cs:g_ulTraceFlags, rcx
0x18003a408  jz      loc_18003A494
0x18003a40e  lea     rdx, aLdapAddCmdConn; "ldap_add cmd connection 0x%x encoding e"...
0x18003a415  jmp     short loc_18003A489
0x18003a417  mov     r8d, 4; unsigned int
0x18003a41d  mov     rdx, r14; unsigned __int16 *
0x18003a420  mov     rcx, rdi; this
0x18003a423  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x18003a428  test    eax, eax
0x18003a42a  jz      short loc_18003A453
0x18003a42c  cmp     cs:g_fTracingOn, ebx
0x18003a432  jz      short loc_18003A494
0x18003a434  cmp     cs:g_fProviderEnabled, ebx
0x18003a43a  jz      short loc_18003A494
0x18003a43c  mov     ecx, 400000h
0x18003a441  test    cs:g_ulTraceFlags, rcx
0x18003a448  jz      short loc_18003A494
0x18003a44a  lea     rdx, aLdapAddDnConne; "ldap_add DN connection 0x%x encoding er"...
0x18003a451  jmp     short loc_18003A489
0x18003a453  mov     edx, 30h ; '0'; unsigned int
0x18003a458  mov     rcx, rdi; this
0x18003a45b  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18003a460  test    eax, eax
0x18003a462  jz      short loc_18003A4A6
0x18003a464  cmp     cs:g_fTracingOn, ebx
0x18003a46a  jz      short loc_18003A494
0x18003a46c  cmp     cs:g_fProviderEnabled, ebx
0x18003a472  jz      short loc_18003A494
0x18003a474  mov     ecx, 400000h
0x18003a479  test    cs:g_ulTraceFlags, rcx
0x18003a480  jz      short loc_18003A494
0x18003a482  lea     rdx, aLdapAddAttrlis_3; "ldap_add attrlist connection 0x%x encod"...
0x18003a489  mov     r9d, eax
0x18003a48c  mov     r8, rsi
0x18003a48f  call    LDAPClientPrint
0x18003a494  mov     rcx, rdi; this
0x18003a497  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18003a49c  mov     eax, 53h ; 'S'
0x18003a4a1  jmp     loc_18003A5EB
0x18003a4a6  mov     r8b, [rsp+58h+arg_28]; unsigned __int8
0x18003a4ae  mov     rdx, r15; struct ldapmodW **
0x18003a4b1  mov     rcx, rdi; this
0x18003a4b4  call    ?EncodeAddList@@YAKPEAVCLdapBer@@QEAPEAUldapmodW@@E@Z; EncodeAddList(CLdapBer *,ldapmodW * * const,uchar)
0x18003a4b9  mov     r14d, eax
0x18003a4bc  test    eax, eax
0x18003a4be  jz      short loc_18003A500
0x18003a4c0  cmp     cs:g_fTracingOn, ebx
0x18003a4c6  jz      short loc_18003A4F0
0x18003a4c8  cmp     cs:g_fProviderEnabled, ebx
0x18003a4ce  jz      short loc_18003A4F0
0x18003a4d0  mov     ecx, 400000h
0x18003a4d5  test    cs:g_ulTraceFlags, rcx
0x18003a4dc  jz      short loc_18003A4F0
0x18003a4de  mov     r9d, eax
0x18003a4e1  lea     rdx, aLdapAddAttrlis_3; "ldap_add attrlist connection 0x%x encod"...
0x18003a4e8  mov     r8, rsi
0x18003a4eb  call    LDAPClientPrint
0x18003a4f0  mov     rcx, rdi; this
0x18003a4f3  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18003a4f8  mov     eax, r14d
0x18003a4fb  jmp     loc_18003A5EB
0x18003a500  mov     rcx, rdi; this
0x18003a503  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18003a508  mov     rcx, rdi; this
0x18003a50b  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18003a510  cmp     dword ptr [rsi+3E8h], 2
0x18003a517  jz      short loc_18003A537
0x18003a519  cmp     [rbp+0C8h], rbx
0x18003a520  jz      short loc_18003A537
0x18003a522  mov     r8, rdi; struct CLdapBer *
0x18003a525  mov     rdx, rsi; struct ldap_connection *
0x18003a528  mov     rcx, rbp; struct ldap_request *
0x18003a52b  call    ?InsertServerControls@@YAKPEAUldap_request@@PEAUldap_connection@@PEAVCLdapBer@@@Z; InsertServerControls(ldap_request *,ldap_connection *,CLdapBer *)
0x18003a530  mov     r14d, eax
0x18003a533  test    eax, eax
0x18003a535  jnz     short loc_18003A4F0
0x18003a537  mov     rcx, rdi; this
0x18003a53a  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18003a53f  lea     r15, [rsi+230h]
0x18003a546  mov     rcx, r15; lpCriticalSection
0x18003a549  call    cs:__imp_EnterCriticalSection
0x18003a550  nop     dword ptr [rax+rax+00h]
0x18003a555  mov     rdx, rsi
0x18003a558  mov     rcx, rbp
0x18003a55b  call    AddToPendingList
0x18003a560  xor     r8d, r8d; struct CLdapBer *
0x18003a563  mov     rdx, rdi; struct CLdapBer *
0x18003a566  mov     rcx, rsi; struct ldap_connection *
0x18003a569  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x18003a56e  mov     r14d, eax
0x18003a571  test    eax, eax
0x18003a573  jz      short loc_18003A5B2
0x18003a575  cmp     cs:g_fTracingOn, ebx
0x18003a57b  jz      short loc_18003A5A5
0x18003a57d  cmp     cs:g_fProviderEnabled, ebx
0x18003a583  jz      short loc_18003A5A5
0x18003a585  mov     ecx, 100000h
0x18003a58a  test    cs:g_ulTraceFlags, rcx
0x18003a591  jz      short loc_18003A5A5
0x18003a593  mov     r9d, eax
0x18003a596  lea     rdx, aLdapAddConnect_2; "ldap_add connection 0x%x send with erro"...
0x18003a59d  mov     r8, rsi
0x18003a5a0  call    LDAPClientPrint
0x18003a5a5  mov     rdx, rsi
0x18003a5a8  mov     rcx, rbp
0x18003a5ab  call    DecrementPendingList
0x18003a5b0  jmp     short loc_18003A5BD
0x18003a5b2  mov     rax, [rsp+58h+arg_20]
0x18003a5ba  xchg    rdi, [rax]
0x18003a5bd  mov     rcx, r15; lpCriticalSection
0x18003a5c0  call    cs:__imp_LeaveCriticalSection
0x18003a5c7  nop     dword ptr [rax+rax+00h]
0x18003a5cc  test    rdi, rdi
0x18003a5cf  jz      loc_18003A4F8
0x18003a5d5  jmp     loc_18003A4F0
0x18003a5da  mov     ebx, 5Ah ; 'Z'
0x18003a5df  mov     edx, ebx
0x18003a5e1  mov     rcx, rsi
0x18003a5e4  call    SetConnectionError
0x18003a5e9  mov     eax, ebx
0x18003a5eb  add     rsp, 28h
0x18003a5ef  pop     r15
0x18003a5f1  pop     r14
0x18003a5f3  pop     rdi
0x18003a5f4  pop     rsi
0x18003a5f5  pop     rbp
0x18003a5f6  pop     rbx
0x18003a5f7  retn
```
