# SendLdapExtendedOp(ldap_request *,ldap_connection *,ushort *,CLdapBer * *,long)

- ea: `0x18003f138`
- end: `0x18003f40d`
- name: `?SendLdapExtendedOp@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAVCLdapBer@@J@Z`
- size: `725`
- prototype: `unsigned int __usercall@<eax>(struct ldap_request *@<rcx>, struct ldap_connection *@<rdx>, unsigned __int16 *@<r8>, struct CLdapBer **@<r9>, int)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x18002cf6c`
- `0x18003edf4`

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
- `0x18003f138`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f362`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f362`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f3d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f3d2`

## string_xrefs

- `0x18003f1ee`: `ldap_extendedop startWrite connection 0x%x encoding error of 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SendLdapExtendedOp(
        struct ldap_request *a1,
        struct ldap_connection *a2,
        unsigned __int16 *a3,
        struct CLdapBer **a4,
        int a5)
{
  __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // eax
  int v12; // edx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned __int8 *v15; // rdx
  unsigned int v16; // r8d
  unsigned int v17; // eax
  unsigned int inserted; // ebp
  unsigned int v20; // eax

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
      goto LABEL_4;
    v12 = a5;
    if ( !a5 )
      v12 = *((_DWORD *)a1 + 27);
    v13 = CLdapBer::HrAddValue((CLdapBer *)v9, v12, 2u);
    if ( v13 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_extendedop MsgNo connection 0x%x encoding error of 0x%x.\n", a2, v13);
      goto LABEL_27;
    }
    v11 = CLdapBer::HrStartWriteSequence((CLdapBer *)v9, 0x77u);
    if ( v11 )
    {
LABEL_4:
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_extendedop startWrite connection 0x%x encoding error of 0x%x.\n", a2, v11);
LABEL_27:
      CLdapBer::`scalar deleting destructor'((CLdapBer *)v9);
      return 83;
    }
    v14 = CLdapBer::HrAddValue((CLdapBer *)v9, a3, 0x80u);
    if ( v14 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldap_extendedop OID connection 0x%x encoding error of 0x%x.\n", a2, v14);
      goto LABEL_27;
    }
    v15 = (unsigned __int8 *)*((_QWORD *)a1 + 30);
    if ( v15 )
    {
      v16 = *((_DWORD *)a1 + 58);
      if ( v16 )
      {
        v17 = CLdapBer::HrAddBinaryValue((CLdapBer *)v9, v15, v16, 0x81u);
        if ( v17 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
            LDAPClientPrint(0x400000, "ldap_extendedop connection 0x%x encoding error of 0x%x.\n", a2, v17);
          goto LABEL_27;
        }
      }
    }
    CLdapBer::HrEndWriteSequence((CLdapBer *)v9);
    if ( *((_DWORD *)a2 + 250) != 2 )
    {
      if ( *((_QWORD *)a1 + 25) )
      {
        inserted = InsertServerControls(a1, a2, (struct CLdapBer *)v9);
        if ( inserted )
          goto LABEL_31;
      }
    }
    CLdapBer::HrEndWriteSequence((CLdapBer *)v9);
    EnterCriticalSection((LPCRITICAL_SECTION)a2 + 14);
    AddToPendingList((__int64)a1, (__int64)a2);
    v20 = LdapSend(a2, (struct CLdapBer *)v9, 0);
    inserted = v20;
    if ( v20 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
        LDAPClientPrint(0x100000, "ldap_extendedop connection 0x%x send with error of 0x%x.\n", (_DWORD)a2, v20);
      DecrementPendingList(a1, a2);
    }
    else
    {
      v9 = _InterlockedExchange64((volatile __int64 *)a4, v9);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)a2 + 14);
    if ( v9 )
LABEL_31:
      CLdapBer::`scalar deleting destructor'((CLdapBer *)v9);
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
0x18003f138  push    rbx
0x18003f13a  push    rbp
0x18003f13b  push    rsi
0x18003f13c  push    rdi
0x18003f13d  push    r12
0x18003f13f  push    r14
0x18003f141  push    r15
0x18003f143  sub     rsp, 20h
0x18003f147  mov     rdi, rdx
0x18003f14a  mov     rsi, rcx
0x18003f14d  mov     edx, 6C43424Ch
0x18003f152  mov     ecx, 368h
0x18003f157  mov     r15, r9
0x18003f15a  mov     rbp, r8
0x18003f15d  call    ldapMalloc
0x18003f162  xor     r12d, r12d
0x18003f165  mov     rbx, rax
0x18003f168  test    rax, rax
0x18003f16b  jz      loc_18003F3EC
0x18003f171  mov     eax, [rdi+3E8h]
0x18003f177  lea     edx, [r12+30h]; unsigned int
0x18003f17c  sub     eax, 2
0x18003f17f  mov     [rbx], r12
0x18003f182  neg     eax
0x18003f184  mov     [rbx+8], r12d
0x18003f188  mov     [rbx+10h], r12
0x18003f18c  mov     rcx, rbx; this
0x18003f18f  sbb     eax, eax
0x18003f191  mov     [rbx+344h], r12
0x18003f198  and     eax, 0FDE9h
0x18003f19d  mov     [rbx+18h], r12
0x18003f1a1  mov     [rbx+358h], r12b
0x18003f1a8  mov     [rbx+360h], r12d
0x18003f1af  mov     [rbx+35Ch], eax
0x18003f1b5  mov     [rbx+20h], r12d
0x18003f1b9  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18003f1be  test    eax, eax
0x18003f1c0  jz      short loc_18003F1FA
0x18003f1c2  cmp     cs:g_fTracingOn, r12d
0x18003f1c9  jz      loc_18003F301
0x18003f1cf  cmp     cs:g_fProviderEnabled, r12d
0x18003f1d6  jz      loc_18003F301
0x18003f1dc  mov     ecx, 400000h
0x18003f1e1  test    cs:g_ulTraceFlags, rcx
0x18003f1e8  jz      loc_18003F301
0x18003f1ee  lea     rdx, aLdapExtendedop_0; "ldap_extendedop startWrite connection 0"...
0x18003f1f5  jmp     loc_18003F2F6
0x18003f1fa  mov     edx, [rsp+58h+arg_20]
0x18003f201  test    edx, edx
0x18003f203  jnz     short loc_18003F208
0x18003f205  mov     edx, [rsi+6Ch]; int
0x18003f208  mov     r8d, 2; unsigned int
0x18003f20e  mov     rcx, rbx; this
0x18003f211  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x18003f216  test    eax, eax
0x18003f218  jz      short loc_18003F252
0x18003f21a  cmp     cs:g_fTracingOn, r12d
0x18003f221  jz      loc_18003F301
0x18003f227  cmp     cs:g_fProviderEnabled, r12d
0x18003f22e  jz      loc_18003F301
0x18003f234  mov     ecx, 400000h
0x18003f239  test    cs:g_ulTraceFlags, rcx
0x18003f240  jz      loc_18003F301
0x18003f246  lea     rdx, aLdapExtendedop_1; "ldap_extendedop MsgNo connection 0x%x e"...
0x18003f24d  jmp     loc_18003F2F6
0x18003f252  mov     edx, 77h ; 'w'; unsigned int
0x18003f257  mov     rcx, rbx; this
0x18003f25a  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18003f25f  test    eax, eax
0x18003f261  jnz     loc_18003F1C2
0x18003f267  mov     r8d, 80h; unsigned int
0x18003f26d  mov     rdx, rbp; unsigned __int16 *
0x18003f270  mov     rcx, rbx; this
0x18003f273  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x18003f278  test    eax, eax
0x18003f27a  jz      short loc_18003F2A5
0x18003f27c  cmp     cs:g_fTracingOn, r12d
0x18003f283  jz      short loc_18003F301
0x18003f285  cmp     cs:g_fProviderEnabled, r12d
0x18003f28c  jz      short loc_18003F301
0x18003f28e  mov     ecx, 400000h
0x18003f293  test    cs:g_ulTraceFlags, rcx
0x18003f29a  jz      short loc_18003F301
0x18003f29c  lea     rdx, aLdapExtendedop; "ldap_extendedop OID connection 0x%x enc"...
0x18003f2a3  jmp     short loc_18003F2F6
0x18003f2a5  mov     rdx, [rsi+0F0h]; unsigned __int8 *
0x18003f2ac  test    rdx, rdx
0x18003f2af  jz      short loc_18003F313
0x18003f2b1  mov     r8d, [rsi+0E8h]; unsigned int
0x18003f2b8  test    r8d, r8d
0x18003f2bb  jz      short loc_18003F313
0x18003f2bd  mov     r9d, 81h; unsigned int
0x18003f2c3  mov     rcx, rbx; this
0x18003f2c6  call    ?HrAddBinaryValue@CLdapBer@@QEAAKPEAEKK@Z; CLdapBer::HrAddBinaryValue(uchar *,ulong,ulong)
0x18003f2cb  test    eax, eax
0x18003f2cd  jz      short loc_18003F313
0x18003f2cf  cmp     cs:g_fTracingOn, r12d
0x18003f2d6  jz      short loc_18003F301
0x18003f2d8  cmp     cs:g_fProviderEnabled, r12d
0x18003f2df  jz      short loc_18003F301
0x18003f2e1  mov     ecx, 400000h
0x18003f2e6  test    cs:g_ulTraceFlags, rcx
0x18003f2ed  jz      short loc_18003F301
0x18003f2ef  lea     rdx, aLdapExtendedop_2; "ldap_extendedop connection 0x%x encodin"...
0x18003f2f6  mov     r9d, eax
0x18003f2f9  mov     r8, rdi
0x18003f2fc  call    LDAPClientPrint
0x18003f301  mov     rcx, rbx; this
0x18003f304  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18003f309  mov     eax, 53h ; 'S'
0x18003f30e  jmp     loc_18003F3FD
0x18003f313  mov     rcx, rbx; this
0x18003f316  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18003f31b  cmp     dword ptr [rdi+3E8h], 2
0x18003f322  jz      short loc_18003F350
0x18003f324  cmp     [rsi+0C8h], r12
0x18003f32b  jz      short loc_18003F350
0x18003f32d  mov     r8, rbx; struct CLdapBer *
0x18003f330  mov     rdx, rdi; struct ldap_connection *
0x18003f333  mov     rcx, rsi; struct ldap_request *
0x18003f336  call    ?InsertServerControls@@YAKPEAUldap_request@@PEAUldap_connection@@PEAVCLdapBer@@@Z; InsertServerControls(ldap_request *,ldap_connection *,CLdapBer *)
0x18003f33b  mov     ebp, eax
0x18003f33d  test    eax, eax
0x18003f33f  jz      short loc_18003F350
0x18003f341  mov     rcx, rbx; this
0x18003f344  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18003f349  mov     eax, ebp
0x18003f34b  jmp     loc_18003F3FD
0x18003f350  mov     rcx, rbx; this
0x18003f353  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18003f358  lea     r14, [rdi+230h]
0x18003f35f  mov     rcx, r14; lpCriticalSection
0x18003f362  call    cs:__imp_EnterCriticalSection
0x18003f369  nop     dword ptr [rax+rax+00h]
0x18003f36e  mov     rdx, rdi
0x18003f371  mov     rcx, rsi
0x18003f374  call    AddToPendingList
0x18003f379  xor     r8d, r8d; struct CLdapBer *
0x18003f37c  mov     rdx, rbx; struct CLdapBer *
0x18003f37f  mov     rcx, rdi; struct ldap_connection *
0x18003f382  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x18003f387  mov     ebp, eax
0x18003f389  test    eax, eax
0x18003f38b  jz      short loc_18003F3CC
0x18003f38d  cmp     cs:g_fTracingOn, r12d
0x18003f394  jz      short loc_18003F3BF
0x18003f396  cmp     cs:g_fProviderEnabled, r12d
0x18003f39d  jz      short loc_18003F3BF
0x18003f39f  mov     ecx, 100000h
0x18003f3a4  test    cs:g_ulTraceFlags, rcx
0x18003f3ab  jz      short loc_18003F3BF
0x18003f3ad  mov     r9d, eax
0x18003f3b0  lea     rdx, aLdapExtendedop_3; "ldap_extendedop connection 0x%x send wi"...
0x18003f3b7  mov     r8, rdi
0x18003f3ba  call    LDAPClientPrint
0x18003f3bf  mov     rdx, rdi
0x18003f3c2  mov     rcx, rsi
0x18003f3c5  call    DecrementPendingList
0x18003f3ca  jmp     short loc_18003F3CF
0x18003f3cc  xchg    rbx, [r15]
0x18003f3cf  mov     rcx, r14; lpCriticalSection
0x18003f3d2  call    cs:__imp_LeaveCriticalSection
0x18003f3d9  nop     dword ptr [rax+rax+00h]
0x18003f3de  test    rbx, rbx
0x18003f3e1  jz      loc_18003F349
0x18003f3e7  jmp     loc_18003F341
0x18003f3ec  mov     ebx, 5Ah ; 'Z'
0x18003f3f1  mov     rcx, rdi
0x18003f3f4  mov     edx, ebx
0x18003f3f6  call    SetConnectionError
0x18003f3fb  mov     eax, ebx
0x18003f3fd  add     rsp, 20h
0x18003f401  pop     r15
0x18003f403  pop     r14
0x18003f405  pop     r12
0x18003f407  pop     rdi
0x18003f408  pop     rsi
0x18003f409  pop     rbp
0x18003f40a  pop     rbx
0x18003f40b  retn
```
