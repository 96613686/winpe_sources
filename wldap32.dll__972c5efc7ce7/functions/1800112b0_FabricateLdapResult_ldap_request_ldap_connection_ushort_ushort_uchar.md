# FabricateLdapResult(ldap_request *,ldap_connection *,ushort *,ushort * *,uchar)

- ea: `0x1800112b0`
- end: `0x180011c6c`
- name: `?FabricateLdapResult@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAGE@Z`
- size: `2492`
- prototype: `unsigned int(struct ldap_request *, struct ldap_connection *, unsigned __int16 *, unsigned __int16 **, unsigned __int8)`
- caller_count: `3`
- callee_count: `14`
- tags: ``

## callers

- `0x180006d80`
- `0x18001af54`
- `0x180045b90`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000b440`
- `0x18000b5c8`
- `0x180010ef0`
- `0x1800112b0`
- `0x180011c80`
- `0x180011f50`
- `0x180014060`
- `0x180014460`
- `0x18001de00`
- `0x18001fb78`
- `0x180032bd8`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800114f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001172e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800114f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001172e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011522`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001175b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011522`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001175b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800112e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800112e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800116ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800116ff`

## string_xrefs

- `0x180011874`: `FabricateLdapResult: startWrite connection 0x%x encoding error of 0x%x.\n`
- `0x180011ae0`: `FabricateLdapResult: RetrieveFromCache failed\n`
- `0x180011b26`: `FabricateLdapResult: CacheIndex less than 0.\n`
- `0x180011b59`: `FabricateLdapMessage: Refcount is %d, Cacheindex is %d\n`
- `0x1800119af`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
__int64 __fastcall FabricateLdapResult(
        struct ldap_request *a1,
        struct _RTL_CRITICAL_SECTION *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        char a5)
{
  struct ldap_request *v7; // rsi
  unsigned int *v9; // rax
  int v10; // r10d
  unsigned int *v11; // rbx
  unsigned int v12; // eax
  int DebugInfo; // ecx
  int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // edi
  __int64 ReceiveStructure; // rsi
  _QWORD *v21; // rax
  unsigned int v22; // edx
  unsigned int v24; // edx
  int v25; // r13d
  const CHAR *v26; // rdx
  unsigned __int16 **v27; // rdi
  unsigned __int16 **v28; // r14
  const unsigned __int16 *v29; // rdx
  unsigned int v30; // eax
  int i; // esi
  const unsigned __int16 *v32; // rdx
  unsigned __int16 **v33; // rdi
  unsigned __int16 *v34; // rbp
  int v35; // eax
  int v36; // r9d
  int v37; // r8d
  int v38; // eax
  HANDLE v39; // rcx
  __int64 v40; // rdi
  struct _CACHEHOLDER * near *v41; // rcx
  bool v42; // zf
  bool v43; // zf
  int v44; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 **v45; // [rsp+38h] [rbp-30h] BYREF

  v44 = -1;
  v7 = a1;
  v9 = (unsigned int *)HeapAlloc(LdapHeap, 8u, 0x370u);
  v10 = g_fTracingOn;
  v11 = v9;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
  {
    LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", 880, (_DWORD)v9, 1816347212);
    v10 = g_fTracingOn;
  }
  v12 = LdapAllocatedHeap;
  if ( v11 )
  {
    *v11 = 1816347212;
    v11[1] = 872;
    v11 += 2;
    v12 += 872;
    LdapAllocatedHeap = v12;
  }
  if ( v10 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
  {
    LDAPClientPrint(
      8,
      "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
      872,
      (_DWORD)v11,
      1816347212,
      v12);
    v10 = g_fTracingOn;
  }
  if ( v11 )
  {
    DebugInfo = (int)a2[25].DebugInfo;
    v14 = 0;
    *(_QWORD *)v11 = 0;
    if ( DebugInfo != 2 )
      v14 = 65001;
    v11[2] = 0;
    *((_QWORD *)v11 + 2) = 0;
    *(_QWORD *)(v11 + 209) = 0;
    *((_QWORD *)v11 + 3) = 0;
    *((_BYTE *)v11 + 856) = 0;
    v11[216] = 0;
    v11[215] = v14;
    v11[8] = 0;
    v15 = CLdapBer::HrStartWriteSequence((CLdapBer *)v11, 0x30u);
    if ( v15 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(
          0x400000,
          "FabricateLdapResult: startWrite connection 0x%x encoding error of 0x%x.\n",
          (_DWORD)a2,
          v15);
      goto LABEL_25;
    }
    v16 = CLdapBer::HrAddValue((CLdapBer *)v11, *((_DWORD *)v7 + 27), 2u);
    if ( v16 )
    {
      if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
        goto LABEL_25;
      LDAPClientPrint(0x400000, "FabricateLdapResult: MsgNo connection 0x%x encoding error of 0x%x.\n", (_DWORD)a2, v16);
      v19 = 83;
      goto LABEL_26;
    }
    v17 = CLdapBer::HrStartWriteSequence((CLdapBer *)v11, 0x64u);
    if ( v17 )
    {
      if ( !g_fTracingOn )
        goto LABEL_25;
      v42 = g_fProviderEnabled == 0;
LABEL_72:
      if ( v42 || (g_ulTraceFlags & 0x400000) == 0 )
        goto LABEL_25;
      LDAPClientPrint(0x400000, "FabricateLdapResult: cmd connection 0x%x encoding error of 0x%x.\n", (_DWORD)a2, v17);
      v19 = 83;
LABEL_26:
      SetConnectionError(a2, v19);
      CLdapBer::`scalar deleting destructor'((CLdapBer *)v11, v24);
      return v19;
    }
    v18 = CLdapBer::HrAddValue((CLdapBer *)v11, a3, 4u);
    if ( v18 || (v18 = CLdapBer::HrStartWriteSequence((CLdapBer *)v11, 0x30u)) != 0 )
    {
      if ( !g_fTracingOn )
        goto LABEL_25;
      v43 = g_fProviderEnabled == 0;
LABEL_77:
      if ( !v43 && (g_ulTraceFlags & 0x400000) != 0 )
      {
        LDAPClientPrint(0x400000, "FabricateLdapResult: DN connection 0x%x encoding error of 0x%x.\n", (_DWORD)a2, v18);
        v19 = 83;
      }
      else
      {
LABEL_25:
        v19 = 83;
      }
      goto LABEL_26;
    }
    if ( !a4 )
    {
LABEL_14:
      CLdapBer::HrEndWriteSequence((CLdapBer *)v11);
      CLdapBer::HrEndWriteSequence((CLdapBer *)v11);
      CLdapBer::HrEndWriteSequence((CLdapBer *)v11);
      v17 = CLdapBer::HrStartWriteSequence((CLdapBer *)v11, 0x30u);
      if ( v17 )
      {
LABEL_24:
        if ( !g_fTracingOn )
          goto LABEL_25;
        v42 = g_fProviderEnabled == 0;
      }
      else
      {
        v17 = CLdapBer::HrAddValue((CLdapBer *)v11, *((_DWORD *)v7 + 27), 2u);
        if ( v17 )
        {
          if ( !g_fTracingOn )
            goto LABEL_25;
          v42 = g_fProviderEnabled == 0;
        }
        else
        {
          v17 = CLdapBer::HrStartWriteSequence((CLdapBer *)v11, 0x65u);
          if ( v17 )
          {
            if ( !g_fTracingOn )
              goto LABEL_25;
            v42 = g_fProviderEnabled == 0;
          }
          else
          {
            v17 = CLdapBer::HrAddValue((CLdapBer *)v11, 0, 0xAu);
            if ( v17 )
            {
              if ( !g_fTracingOn )
                goto LABEL_25;
              v42 = g_fProviderEnabled == 0;
            }
            else
            {
              v17 = CLdapBer::HrAddValue((CLdapBer *)v11, 0, 4u);
              if ( v17 )
              {
                if ( !g_fTracingOn )
                  goto LABEL_25;
                v42 = g_fProviderEnabled == 0;
              }
              else
              {
                v17 = CLdapBer::HrAddValue((CLdapBer *)v11, 0, 4u);
                if ( !v17 )
                {
                  CLdapBer::HrEndWriteSequence((CLdapBer *)v11);
                  v19 = CLdapBer::HrEndWriteSequence((CLdapBer *)v11);
                  ReceiveStructure = LdapGetReceiveStructure(*v11);
                  if ( ReceiveStructure )
                  {
                    *(_DWORD *)(ReceiveStructure + 24) = *v11;
                    *(_QWORD *)ReceiveStructure = a2;
                    memcpy_0((void *)(ReceiveStructure + 36), *((const void **)v11 + 2), *v11);
                    EnterCriticalSection(a2 + 20);
                    v21 = *(_QWORD **)&a2[1].LockCount;
                    *(_QWORD *)(ReceiveStructure + 16) = v21;
                    *(_QWORD *)(ReceiveStructure + 8) = a2 + 1;
                    *v21 = ReceiveStructure + 8;
                    *(_QWORD *)&a2[1].LockCount = ReceiveStructure + 8;
                    LeaveCriticalSection(a2 + 20);
                    CLdapBer::`scalar deleting destructor'((CLdapBer *)v11, v22);
                    return 0;
                  }
                  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
                    LDAPClientTraceEvent(0x4000, "FabricateLdapResult: failed to get receive buffer\n");
                  goto LABEL_26;
                }
                if ( !g_fTracingOn )
                  goto LABEL_25;
                v42 = g_fProviderEnabled == 0;
              }
            }
          }
        }
      }
      goto LABEL_72;
    }
    v25 = 0;
    v45 = 0;
    while ( 1 )
    {
LABEL_28:
      v26 = (const CHAR *)a4[v25];
      v27 = &a4[v25];
      if ( !v26 )
      {
        v40 = v44;
        if ( v44 >= 0 )
        {
          EnterCriticalSection(&CacheLock);
          v41 = (&CacheArray)[v40];
          --*(_DWORD *)v41;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
            LDAPClientPrint(16, "FabricateLdapMessage: Refcount is %d, Cacheindex is %d\n", *(_DWORD *)v41, v40);
          LeaveCriticalSection(&CacheLock);
          v7 = a1;
          goto LABEL_14;
        }
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
          LDAPClientTraceEvent(0x400000, "FabricateLdapResult: CacheIndex less than 0.\n");
        goto LABEL_25;
      }
      if ( !RetrieveFromCache((struct ldap_connection *)a2, v26, a5, &v44, &v45) )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
          LDAPClientTraceEvent(0x400000, "FabricateLdapResult: RetrieveFromCache failed\n");
        v19 = 90;
        goto LABEL_26;
      }
      v28 = v45;
      if ( v45 )
        break;
      ++v25;
    }
    v18 = CLdapBer::HrStartWriteSequence((CLdapBer *)v11, 0x30u);
    if ( v18 )
    {
      if ( !g_fTracingOn )
        goto LABEL_25;
      v43 = g_fProviderEnabled == 0;
      goto LABEL_77;
    }
    v29 = *v27;
    if ( a5 )
      v30 = CLdapBer::HrAddValue((CLdapBer *)v11, v29, 4u);
    else
      v30 = CLdapBer::HrAddValue((CLdapBer *)v11, (LPCCH)v29, 4u);
    if ( v30 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      {
        if ( a5 )
        {
          if ( (g_ulTraceFlags & 0x10) != 0 )
            LDAPClientPrint(
              16,
              "FabricateLdapResult: connection 0x%x encoding error of 0x%x, attr = '%S'.\n",
              a2,
              v30,
              *v27);
        }
        else if ( (g_ulTraceFlags & 0x10) != 0 )
        {
          LDAPClientPrint(
            16,
            "FabricateLdapResult: connection 0x%x encoding error of 0x%x, attr = '%s'.\n",
            a2,
            v30,
            *v27);
        }
      }
      goto LABEL_25;
    }
    v17 = CLdapBer::HrStartWriteSequence((CLdapBer *)v11, 0x31u);
    if ( v17 )
      goto LABEL_24;
    for ( i = 0; ; ++i )
    {
      v32 = v28[i];
      v33 = &v28[i];
      if ( !v32 )
      {
        CLdapBer::HrEndWriteSequence((CLdapBer *)v11);
        CLdapBer::HrEndWriteSequence((CLdapBer *)v11);
        ldapFree(v28, 1819039308);
        ++v25;
        goto LABEL_28;
      }
      v17 = CLdapBer::HrAddValue((CLdapBer *)v11, v32, 4u);
      if ( v17 )
        goto LABEL_24;
      v34 = *v33;
      if ( *v33 )
      {
        v35 = *((_DWORD *)v34 - 2);
        if ( v35 != 1684095564 )
          break;
      }
LABEL_40:
      ;
    }
    if ( v35 == 1701987916 )
    {
      if ( !g_fTracingOn )
      {
LABEL_45:
        v36 = *((_DWORD *)v34 - 2);
        if ( v36 != 1818318412 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1818318412, v36);
        v37 = *((_DWORD *)v34 - 1);
        v38 = LdapAllocatedHeap - v37;
        LdapAllocatedHeap -= v37;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(
            8,
            "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
            v37,
            (_DWORD)v34,
            1818318412,
            v38);
        v39 = LdapHeap;
        *((_DWORD *)v34 - 2) = 1701987916;
        HeapFree(v39, 0, v34 - 4);
        goto LABEL_40;
      }
      if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (unsigned int)*v33);
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
        *((_DWORD *)v34 - 1),
        (_DWORD)v34 - 8,
        1818318412);
    goto LABEL_45;
  }
  if ( v10 && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
    LDAPClientPrint(0x4000, "FabricateLdapResult: unable to allocate message for 0x%x.\n", (_DWORD)a2);
  return 90;
}

```

## disassembly

```asm
0x1800112b0  mov     [rsp+arg_0], rcx
0x1800112b5  push    rbx
0x1800112b6  push    rsi
0x1800112b7  push    rdi
0x1800112b8  push    r12
0x1800112ba  push    r15
0x1800112bc  sub     rsp, 40h
0x1800112c0  mov     rdi, r8
0x1800112c3  mov     [rsp+68h+var_38], 0FFFFFFFFh
0x1800112cb  mov     r15, rdx
0x1800112ce  mov     rsi, rcx
0x1800112d1  mov     rcx, cs:LdapHeap; hHeap
0x1800112d8  mov     edx, 8; dwFlags
0x1800112dd  mov     r8d, 370h; dwBytes
0x1800112e3  mov     r12, r9
0x1800112e6  call    cs:__imp_HeapAlloc
0x1800112ed  nop     dword ptr [rax+rax+00h]
0x1800112f2  mov     r10d, cs:g_fTracingOn
0x1800112f9  mov     rbx, rax
0x1800112fc  test    r10d, r10d
0x1800112ff  jnz     loc_1800117B4
0x180011305  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001130b  test    rbx, rbx
0x18001130e  jz      short loc_18001132C
0x180011310  mov     dword ptr [rbx], 6C43424Ch
0x180011316  mov     dword ptr [rbx+4], 368h
0x18001131d  add     rbx, 8
0x180011321  add     eax, 368h
0x180011326  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001132c  test    r10d, r10d
0x18001132f  jnz     loc_1800117FC
0x180011335  test    rbx, rbx
0x180011338  jz      loc_18001155A
0x18001133e  mov     ecx, [r15+3E8h]
0x180011345  mov     edx, 0FDE9h
0x18001134a  mov     [rsp+68h+arg_8], rbp
0x18001134f  xor     ebp, ebp
0x180011351  cmp     ecx, 2
0x180011354  mov     [rsp+68h+arg_10], r13
0x18001135c  mov     eax, ebp
0x18001135e  mov     [rbx], rbp
0x180011361  cmovnz  eax, edx
0x180011364  mov     [rbx+8], ebp
0x180011367  mov     [rbx+10h], rbp
0x18001136b  mov     edx, 30h ; '0'; unsigned int
0x180011370  mov     [rbx+344h], rbp
0x180011377  mov     rcx, rbx; this
0x18001137a  mov     [rbx+18h], rbp
0x18001137e  mov     [rbx+358h], bpl
0x180011385  mov     [rbx+360h], ebp
0x18001138b  mov     [rsp+68h+arg_18], r14
0x180011393  mov     [rbx+35Ch], eax
0x180011399  mov     [rbx+20h], ebp
0x18001139c  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x1800113a1  test    eax, eax
0x1800113a3  jnz     loc_180011848
0x1800113a9  mov     edx, [rsi+6Ch]; int
0x1800113ac  mov     r8d, 2; unsigned int
0x1800113b2  mov     rcx, rbx; this
0x1800113b5  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x1800113ba  test    eax, eax
0x1800113bc  jnz     loc_18001188D
0x1800113c2  mov     edx, 64h ; 'd'; unsigned int
0x1800113c7  mov     rcx, rbx; this
0x1800113ca  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x1800113cf  test    eax, eax
0x1800113d1  jnz     loc_1800118D7
0x1800113d7  mov     r8d, 4; unsigned int
0x1800113dd  mov     rdx, rdi; unsigned __int16 *
0x1800113e0  mov     rcx, rbx; this
0x1800113e3  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x1800113e8  test    eax, eax
0x1800113ea  jnz     loc_18001192A
0x1800113f0  mov     edx, 30h ; '0'; unsigned int
0x1800113f5  mov     rcx, rbx; this
0x1800113f8  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x1800113fd  test    eax, eax
0x1800113ff  jnz     loc_18001192A
0x180011405  test    r12, r12
0x180011408  jnz     loc_18001159D
0x18001140e  mov     rcx, rbx; this
0x180011411  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x180011416  mov     rcx, rbx; this
0x180011419  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18001141e  mov     rcx, rbx; this
0x180011421  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x180011426  mov     edx, 30h ; '0'; unsigned int
0x18001142b  mov     rcx, rbx; this
0x18001142e  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x180011433  test    eax, eax
0x180011435  jnz     loc_180011575
0x18001143b  mov     edx, [rsi+6Ch]; int
0x18001143e  mov     r8d, 2; unsigned int
0x180011444  mov     rcx, rbx; this
0x180011447  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x18001144c  test    eax, eax
0x18001144e  jnz     loc_180011B7E
0x180011454  mov     edx, 65h ; 'e'; unsigned int
0x180011459  mov     rcx, rbx; this
0x18001145c  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x180011461  test    eax, eax
0x180011463  jnz     loc_180011B97
0x180011469  xor     edx, edx; int
0x18001146b  mov     r8d, 0Ah; unsigned int
0x180011471  mov     rcx, rbx; this
0x180011474  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x180011479  test    eax, eax
0x18001147b  jnz     loc_180011BB0
0x180011481  xor     edx, edx; unsigned __int16 *
0x180011483  mov     r8d, 4; unsigned int
0x180011489  mov     rcx, rbx; this
0x18001148c  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x180011491  test    eax, eax
0x180011493  jnz     loc_180011BC9
0x180011499  xor     edx, edx; unsigned __int16 *
0x18001149b  mov     r8d, 4; unsigned int
0x1800114a1  mov     rcx, rbx; this
0x1800114a4  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x1800114a9  test    eax, eax
0x1800114ab  jnz     loc_180011BE2
0x1800114b1  mov     rcx, rbx; this
0x1800114b4  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x1800114b9  mov     rcx, rbx; this
0x1800114bc  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x1800114c1  mov     ecx, [rbx]
0x1800114c3  mov     edi, eax
0x1800114c5  call    LdapGetReceiveStructure
0x1800114ca  mov     rsi, rax
0x1800114cd  test    rax, rax
0x1800114d0  jz      loc_180011BF4
0x1800114d6  mov     eax, [rbx]
0x1800114d8  lea     rcx, [rsi+24h]; void *
0x1800114dc  mov     [rsi+18h], eax
0x1800114df  mov     [rsi], r15
0x1800114e2  mov     r8d, [rbx]; Size
0x1800114e5  mov     rdx, [rbx+10h]; Src
0x1800114e9  call    memcpy_0
0x1800114ee  lea     rcx, [r15+320h]; lpCriticalSection
0x1800114f5  call    cs:__imp_EnterCriticalSection
0x1800114fc  nop     dword ptr [rax+rax+00h]
0x180011501  mov     rax, [r15+30h]
0x180011505  lea     r8, [r15+28h]
0x180011509  lea     rdx, [rsi+8]
0x18001150d  mov     [rsi+10h], rax
0x180011511  mov     [rdx], r8
0x180011514  lea     rcx, [r15+320h]; lpCriticalSection
0x18001151b  mov     [rax], rdx
0x18001151e  mov     [r8+8], rdx
0x180011522  call    cs:__imp_LeaveCriticalSection
0x180011529  nop     dword ptr [rax+rax+00h]
0x18001152e  mov     rcx, rbx; this
0x180011531  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x180011536  xor     eax, eax
0x180011538  mov     r13, [rsp+68h+arg_10]
0x180011540  mov     r14, [rsp+68h+arg_18]
0x180011548  mov     rbp, [rsp+68h+arg_8]
0x18001154d  add     rsp, 40h
0x180011551  pop     r15
0x180011553  pop     r12
0x180011555  pop     rdi
0x180011556  pop     rsi
0x180011557  pop     rbx
0x180011558  retn
0x18001155a  test    r10d, r10d
0x18001155d  jnz     loc_180011C35
0x180011563  mov     eax, 5Ah ; 'Z'
0x180011568  add     rsp, 40h
0x18001156c  pop     r15
0x18001156e  pop     r12
0x180011570  pop     rdi
0x180011571  pop     rsi
0x180011572  pop     rbx
0x180011573  retn
0x180011575  cmp     cs:g_fTracingOn, 0
0x18001157c  jnz     loc_180011B72
0x180011582  mov     edi, 53h ; 'S'
0x180011587  mov     edx, edi
0x180011589  mov     rcx, r15
0x18001158c  call    SetConnectionError
0x180011591  mov     rcx, rbx; this
0x180011594  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x180011599  mov     eax, edi
0x18001159b  jmp     short loc_180011538
0x18001159d  mov     r13d, ebp
0x1800115a0  mov     [rsp+68h+var_30], rbp
0x1800115a5  movzx   esi, [rsp+68h+arg_20]
0x1800115ad  mov     eax, r13d
0x1800115b0  mov     rdx, [r12+rax*8]; unsigned __int16 *
0x1800115b4  lea     rdi, [r12+rax*8]
0x1800115b8  test    rdx, rdx
0x1800115bb  jz      loc_18001171A
0x1800115c1  lea     rax, [rsp+68h+var_30]
0x1800115c6  movzx   r8d, sil; unsigned __int8
0x1800115ca  lea     r9, [rsp+68h+var_38]; int *
0x1800115cf  mov     [rsp+68h+var_48], rax; unsigned __int16 ***
0x1800115d4  mov     rcx, r15; struct ldap_connection *
0x1800115d7  call    ?RetrieveFromCache@@YAEPEAUldap_connection@@PEAGEPEAHPEAPEAPEAG@Z; RetrieveFromCache(ldap_connection *,ushort *,uchar,int *,ushort * * *)
0x1800115dc  test    al, al
0x1800115de  jz      loc_180011AC1
0x1800115e4  mov     r14, [rsp+68h+var_30]
0x1800115e9  test    r14, r14
0x1800115ec  jz      loc_18001197D
0x1800115f2  mov     edx, 30h ; '0'; unsigned int
0x1800115f7  mov     rcx, rbx; this
0x1800115fa  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x1800115ff  test    eax, eax
0x180011601  jnz     loc_180011AAF
0x180011607  mov     rdx, [rdi]; lpMultiByteStr
0x18001160a  mov     r8d, 4; unsigned int
0x180011610  mov     rcx, rbx; this
0x180011613  test    sil, sil
0x180011616  jz      loc_180011710
0x18001161c  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x180011621  mov     r9d, eax
0x180011624  test    eax, eax
0x180011626  jnz     loc_180011A44
0x18001162c  mov     edx, 31h ; '1'; unsigned int
0x180011631  mov     rcx, rbx; this
0x180011634  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x180011639  test    eax, eax
0x18001163b  jnz     loc_180011575
0x180011641  mov     esi, ebp
0x180011643  mov     eax, esi
0x180011645  mov     rcx, rbx; this
0x180011648  mov     rdx, [r14+rax*8]; unsigned __int16 *
0x18001164c  lea     rdi, [r14+rax*8]
0x180011650  test    rdx, rdx
0x180011653  jz      short loc_180011674
0x180011655  mov     r8d, 4; unsigned int
0x18001165b  call    ?HrAddValue@CLdapBer@@QEAAKPEBGK@Z; CLdapBer::HrAddValue(ushort const *,ulong)
0x180011660  test    eax, eax
0x180011662  jnz     loc_180011575
0x180011668  mov     rbp, [rdi]
0x18001166b  test    rbp, rbp
0x18001166e  jnz     short loc_180011698
0x180011670  inc     esi
0x180011672  jmp     short loc_180011643
0x180011674  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x180011679  mov     rcx, rbx; this
0x18001167c  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x180011681  mov     edx, 6C6C564Ch
0x180011686  mov     rcx, r14
0x180011689  call    ldapFree
0x18001168e  inc     r13d
0x180011691  xor     ebp, ebp
0x180011693  jmp     loc_1800115A5
0x180011698  mov     eax, [rbp-8]
0x18001169b  cmp     eax, 6461424Ch
0x1800116a0  jz      short loc_180011670
0x1800116a2  cmp     eax, 6572464Ch
0x1800116a7  jz      loc_180011985
0x1800116ad  cmp     cs:g_fTracingOn, 0
0x1800116b4  jnz     loc_1800119C5
0x1800116ba  mov     r9d, [rbp-8]
0x1800116be  cmp     r9d, 6C61564Ch
0x1800116c5  jnz     loc_180011771
0x1800116cb  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x1800116d1  mov     r8d, [rbp-4]
0x1800116d5  sub     eax, r8d
0x1800116d8  cmp     cs:g_fTracingOn, 0
0x1800116df  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x1800116e5  jnz     loc_180011A05
0x1800116eb  mov     rcx, cs:LdapHeap; hHeap
0x1800116f2  lea     r8, [rbp-8]; lpMem
0x1800116f6  xor     edx, edx; dwFlags
0x1800116f8  mov     dword ptr [rbp-8], 6572464Ch
0x1800116ff  call    cs:__imp_HeapFree
0x180011706  nop     dword ptr [rax+rax+00h]
0x18001170b  jmp     loc_180011670
0x180011710  call    ?HrAddValue@CLdapBer@@QEAAKPEBDK@Z; CLdapBer::HrAddValue(char const *,ulong)
0x180011715  jmp     loc_180011621
0x18001171a  movsxd  rdi, [rsp+68h+var_38]
0x18001171f  test    edi, edi
0x180011721  js      loc_180011AFB
0x180011727  lea     rcx, CacheLock; lpCriticalSection
0x18001172e  call    cs:__imp_EnterCriticalSection
0x180011735  nop     dword ptr [rax+rax+00h]
0x18001173a  lea     rcx, ?CacheArray@@3PAPEAU_CACHEHOLDER@@A; _CACHEHOLDER * near * CacheArray
0x180011741  mov     rcx, [rcx+rdi*8]
0x180011745  dec     dword ptr [rcx]
0x180011747  cmp     cs:g_fTracingOn, 0
0x18001174e  jnz     loc_180011B3C
0x180011754  lea     rcx, CacheLock; lpCriticalSection
0x18001175b  call    cs:__imp_LeaveCriticalSection
0x180011762  nop     dword ptr [rax+rax+00h]
0x180011767  mov     rsi, [rsp+68h+arg_0]
0x18001176c  jmp     loc_18001140E
0x180011771  cmp     cs:g_fTracingOn, 0
0x180011778  jz      loc_1800116CB
0x18001177e  cmp     cs:g_fProviderEnabled, 0
0x180011785  jz      loc_1800116CB
0x18001178b  test    byte ptr cs:g_ulTraceFlags, 8
0x180011792  jz      loc_1800116CB
0x180011798  mov     r8d, 6C61564Ch
0x18001179e  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x1800117a5  mov     ecx, 8
0x1800117aa  call    LDAPClientPrint
0x1800117af  jmp     loc_1800116CB
0x1800117b4  cmp     cs:g_fProviderEnabled, 0
0x1800117bb  jz      loc_180011305
  ... truncated ...
```
