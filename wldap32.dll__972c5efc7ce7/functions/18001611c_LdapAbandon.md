# LdapAbandon

- ea: `0x18001611c`
- end: `0x180016356`
- name: `LdapAbandon`
- size: `570`
- prototype: ``
- caller_count: `23`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800153c0`
- `0x1800188d0`
- `0x18001b0d4`
- `0x18001f1d0`
- `0x180029f50`
- `0x18002a4f0`
- `0x180039ac0`
- `0x18003a9b0`
- `0x18003abb0`
- `0x18003ce30`
- `0x18003d0d0`
- `0x18003ea40`
- `0x18003ec30`
- `0x18003f420`
- `0x180040b10`
- `0x180040d10`
- `0x180047930`
- `0x180047a80`
- `0x180047f80`
- `0x180048210`
- `0x180048d40`
- `0x18004b28c`
- `0x18004b920`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x180008710`
- `0x18000c8c4`
- `0x18001611c`
- `0x18001ce90`
- `0x1800236f0`
- `0x18002a284`
- `0x18002a91c`
- `0x180038678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001616a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800161fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016289`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800162e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001616a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800161fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016289`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800162e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016188`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001624d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016269`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016188`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001624d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016269`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800162b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800162b8`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18001632e`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18001632e`

## pseudocode

```c
__int64 __fastcall LdapAbandon(__int64 a1, unsigned int a2, char a3)
{
  __int64 v5; // r13
  unsigned int v6; // edi
  __int64 LdapRequest; // rax
  __int64 v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rbp
  unsigned int v10; // eax
  struct ldap_connection **v11; // r14
  unsigned __int16 i; // r15
  __int64 *v13; // rbx
  __int64 *v14; // rcx
  struct _OVERLAPPED *v15; // rax

  v5 = a1;
  if ( !a2 )
  {
    v6 = 89;
LABEL_3:
    SetConnectionError(a1, v6);
    goto LABEL_28;
  }
  LdapRequest = FindLdapRequest(a2);
  v8 = LdapRequest;
  if ( !LdapRequest )
  {
    v6 = 80;
    a1 = v5;
    goto LABEL_3;
  }
  v9 = (struct _RTL_CRITICAL_SECTION *)(LdapRequest + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(LdapRequest + 48));
  *(_BYTE *)(v8 + 184) = 1;
  ClearPendingListForRequest(v8);
  LeaveCriticalSection(v9);
  if ( a3 )
  {
    v10 = SendLdapAbandon(*(struct ldap_connection **)(v8 + 32), a2);
    v11 = *(struct ldap_connection ***)(v8 + 168);
    v6 = v10;
    if ( v11 )
    {
      for ( i = 0; i < *(_WORD *)(v8 + 176); ++i )
      {
        if ( *v11 )
          SendLdapAbandon(*v11, a2);
        v11 += 8;
      }
    }
  }
  else
  {
    v6 = 0;
  }
  CloseLdapRequest(v8);
  EnterCriticalSection(v9);
  --*(_DWORD *)(v8 + 16);
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v8, *(_DWORD *)(v8 + 16));
  if ( *(_DWORD *)(v8 + 16) )
  {
    LeaveCriticalSection(v9);
  }
  else
  {
    LeaveCriticalSection(v9);
    DereferenceLdapRequest2((__int64 *)v8, 0);
  }
  if ( GlobalParallelRecvMode )
  {
    v15 = (struct _OVERLAPPED *)ldapMalloc(4, 1718960716);
    if ( v15 )
    {
      LODWORD(v15->Internal) = a2;
      PostQueuedCompletionStatus(*(HANDLE *)(v5 + 896), 4u, 0xFFFFFFFFFFFFFFFFuLL, v15);
    }
  }
  else
  {
    EnterCriticalSection(&WaiterLock);
    v13 = (__int64 *)GlobalListWaiters;
    while ( v13 != &GlobalListWaiters )
    {
      v14 = v13;
      v13 = (__int64 *)*v13;
      if ( *((_DWORD *)v14 + 8) == a2 )
      {
        *((_BYTE *)v14 + 40) = 1;
        SetEvent((HANDLE)v14[3]);
      }
    }
    LeaveCriticalSection(&WaiterLock);
    EnterCriticalSection(&SelectLock2);
    LdapWakeupSelect();
    LeaveCriticalSection(&SelectLock2);
  }
LABEL_28:
  _InterlockedAdd64(&qword_180066110, 1u);
  return (unsigned int)-(v6 != 0);
}

```

## disassembly

```asm
0x18001611c  push    rbx
0x18001611e  push    rbp
0x18001611f  push    rsi
0x180016120  push    rdi
0x180016121  push    r13
0x180016123  push    r14
0x180016125  push    r15
0x180016127  sub     rsp, 20h
0x18001612b  mov     dil, r8b
0x18001612e  mov     esi, edx
0x180016130  mov     r13, rcx
0x180016133  mov     r15d, 1
0x180016139  test    edx, edx
0x18001613b  jnz     short loc_18001614C
0x18001613d  lea     edi, [rdx+59h]
0x180016140  mov     edx, edi
0x180016142  call    SetConnectionError
0x180016147  jmp     loc_18001633A
0x18001614c  mov     ecx, esi
0x18001614e  call    FindLdapRequest
0x180016153  mov     rbx, rax
0x180016156  test    rax, rax
0x180016159  jnz     short loc_180016163
0x18001615b  lea     edi, [rax+50h]
0x18001615e  mov     rcx, r13
0x180016161  jmp     short loc_180016140
0x180016163  lea     rbp, [rax+30h]
0x180016167  mov     rcx, rbp; lpCriticalSection
0x18001616a  call    cs:__imp_EnterCriticalSection
0x180016171  nop     dword ptr [rax+rax+00h]
0x180016176  mov     rcx, rbx
0x180016179  mov     [rbx+0B8h], r15b
0x180016180  call    ClearPendingListForRequest
0x180016185  mov     rcx, rbp; lpCriticalSection
0x180016188  call    cs:__imp_LeaveCriticalSection
0x18001618f  nop     dword ptr [rax+rax+00h]
0x180016194  test    dil, dil
0x180016197  jz      loc_180016265
0x18001619d  mov     rcx, [rbx+20h]; struct ldap_connection *
0x1800161a1  mov     edx, esi; unsigned int
0x1800161a3  call    ?SendLdapAbandon@@YAKPEAUldap_connection@@K@Z; SendLdapAbandon(ldap_connection *,ulong)
0x1800161a8  mov     r14, [rbx+0A8h]
0x1800161af  mov     edi, eax
0x1800161b1  test    r14, r14
0x1800161b4  jz      short loc_1800161F3
0x1800161b6  xor     r15d, r15d
0x1800161b9  xor     ecx, ecx
0x1800161bb  cmp     cx, [rbx+0B0h]
0x1800161c2  jnb     short loc_1800161ED
0x1800161c4  lea     eax, [rcx+1]
0x1800161c7  mov     rcx, [r14]; struct ldap_connection *
0x1800161ca  test    rcx, rcx
0x1800161cd  jz      short loc_1800161DB
0x1800161cf  mov     edx, esi; unsigned int
0x1800161d1  call    ?SendLdapAbandon@@YAKPEAUldap_connection@@K@Z; SendLdapAbandon(ldap_connection *,ulong)
0x1800161d6  mov     eax, 1
0x1800161db  add     r14, 40h ; '@'
0x1800161df  add     r15w, ax
0x1800161e3  cmp     r15w, [rbx+0B0h]
0x1800161eb  jb      short loc_1800161C7
0x1800161ed  mov     r15d, 1
0x1800161f3  mov     rcx, rbx
0x1800161f6  call    CloseLdapRequest
0x1800161fb  mov     rcx, rbp; lpCriticalSection
0x1800161fe  call    cs:__imp_EnterCriticalSection
0x180016205  nop     dword ptr [rax+rax+00h]
0x18001620a  dec     dword ptr [rbx+10h]
0x18001620d  mov     r14d, 4
0x180016213  cmp     cs:g_fTracingOn, 0
0x18001621a  jz      short loc_180016244
0x18001621c  cmp     cs:g_fProviderEnabled, 0
0x180016223  jz      short loc_180016244
0x180016225  test    byte ptr cs:g_ulTraceFlags, r14b
0x18001622c  jz      short loc_180016244
0x18001622e  mov     r9d, [rbx+10h]
0x180016232  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x180016239  mov     r8, rbx
0x18001623c  mov     ecx, r14d
0x18001623f  call    LDAPClientPrint
0x180016244  cmp     dword ptr [rbx+10h], 0
0x180016248  mov     rcx, rbp; lpCriticalSection
0x18001624b  jnz     short loc_180016269
0x18001624d  call    cs:__imp_LeaveCriticalSection
0x180016254  nop     dword ptr [rax+rax+00h]
0x180016259  xor     edx, edx
0x18001625b  mov     rcx, rbx
0x18001625e  call    DereferenceLdapRequest2
0x180016263  jmp     short loc_180016275
0x180016265  xor     edi, edi
0x180016267  jmp     short loc_1800161F3
0x180016269  call    cs:__imp_LeaveCriticalSection
0x180016270  nop     dword ptr [rax+rax+00h]
0x180016275  cmp     cs:GlobalParallelRecvMode, 0
0x18001627c  jnz     loc_180016309
0x180016282  lea     rcx, WaiterLock; lpCriticalSection
0x180016289  call    cs:__imp_EnterCriticalSection
0x180016290  nop     dword ptr [rax+rax+00h]
0x180016295  mov     rbx, cs:GlobalListWaiters
0x18001629c  lea     rbp, GlobalListWaiters
0x1800162a3  jmp     short loc_1800162C4
0x1800162a5  lea     rcx, [rbx]
0x1800162a8  mov     rbx, [rbx]
0x1800162ab  cmp     [rcx+20h], esi
0x1800162ae  jnz     short loc_1800162C4
0x1800162b0  mov     [rcx+28h], r15b
0x1800162b4  mov     rcx, [rcx+18h]; hEvent
0x1800162b8  call    cs:__imp_SetEvent
0x1800162bf  nop     dword ptr [rax+rax+00h]
0x1800162c4  cmp     rbx, rbp
0x1800162c7  jnz     short loc_1800162A5
0x1800162c9  lea     rcx, WaiterLock; lpCriticalSection
0x1800162d0  call    cs:__imp_LeaveCriticalSection
0x1800162d7  nop     dword ptr [rax+rax+00h]
0x1800162dc  lea     rcx, SelectLock2; lpCriticalSection
0x1800162e3  call    cs:__imp_EnterCriticalSection
0x1800162ea  nop     dword ptr [rax+rax+00h]
0x1800162ef  call    LdapWakeupSelect
0x1800162f4  lea     rcx, SelectLock2; lpCriticalSection
0x1800162fb  call    cs:__imp_LeaveCriticalSection
0x180016302  nop     dword ptr [rax+rax+00h]
0x180016307  jmp     short loc_18001633A
0x180016309  mov     edx, 6675424Ch
0x18001630e  mov     ecx, r14d
0x180016311  call    ldapMalloc
0x180016316  test    rax, rax
0x180016319  jz      short loc_18001633A
0x18001631b  mov     [rax], esi
0x18001631d  mov     r9, rax; lpOverlapped
0x180016320  mov     rcx, [r13+380h]; CompletionPort
0x180016327  or      r8, 0FFFFFFFFFFFFFFFFh; dwCompletionKey
0x18001632b  mov     edx, r14d; dwNumberOfBytesTransferred
0x18001632e  call    cs:__imp_PostQueuedCompletionStatus
0x180016335  nop     dword ptr [rax+rax+00h]
0x18001633a  lock add cs:qword_180066110, r15
0x180016342  neg     edi
0x180016344  sbb     eax, eax
0x180016346  add     rsp, 20h
0x18001634a  pop     r15
0x18001634c  pop     r14
0x18001634e  pop     r13
0x180016350  pop     rdi
0x180016351  pop     rsi
0x180016352  pop     rbp
0x180016353  pop     rbx
0x180016354  retn
```
