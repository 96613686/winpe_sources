# AgCxPrefetchThread

- ea: `0x18002afe0`
- end: `0x18002b536`
- name: `AgCxPrefetchThread`
- size: `1366`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000d4d0`
- `0x180010b44`
- `0x18002afe0`
- `0x18002c990`
- `0x18002dce0`
- `0x180031b64`
- `0x180035dd4`
- `0x1800513c4`
- `0x180052b38`
- `0x18005c148`
- `0x18005f89c`
- `0x180065008`
- `0x180069ad4`
- `0x180072fec`
- `0x1800830d4`
- `0x180090134`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b32c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b32c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b341`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b341`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b43d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b43d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b39b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b39b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b52b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b52b`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsForceCrash` at `0x18002b463`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsForceCrash` at `0x18002b463`

## pseudocode

```c
__int64 __fastcall AgCxPrefetchThread(unsigned int *Parameter)
{
  int v2; // r13d
  unsigned int PrefetchServiceThreadPrivileges; // esi
  unsigned int v4; // ebx
  _QWORD *v5; // r12
  int v6; // ebx
  int i; // r13d
  _QWORD *v8; // rdx
  unsigned __int64 *v9; // rdx
  __int64 v10; // rdx
  __int64 Next; // rax
  _BYTE *v12; // rdi
  unsigned int v13; // eax
  unsigned int v14; // eax
  char *v15; // r8
  int v16; // ecx
  __int64 v17; // rax
  unsigned int v18; // edx
  unsigned int v19; // r9d
  __int64 v20; // rax
  unsigned __int8 v21; // cl
  unsigned int v22; // ebx
  _DWORD *v23; // rdi
  unsigned int v24; // r12d
  unsigned int v25; // ebx
  struct _RTL_CRITICAL_SECTION *v26; // r15
  HANDLE CurrentThread; // rax
  __int64 j; // rbx
  unsigned __int8 v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+28h] [rbp-D8h]
  unsigned int v32; // [rsp+2Ch] [rbp-D4h]
  unsigned int v33; // [rsp+2Ch] [rbp-D4h]
  int v34; // [rsp+30h] [rbp-D0h]
  unsigned int v35; // [rsp+34h] [rbp-CCh]
  __int64 Similar; // [rsp+38h] [rbp-C8h]
  __int64 v37; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v38; // [rsp+48h] [rbp-B8h]
  __int64 v39; // [rsp+48h] [rbp-B8h]
  char *v40; // [rsp+50h] [rbp-B0h]
  _QWORD v41[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v42; // [rsp+68h] [rbp-98h]
  char v43[40]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v44; // [rsp+98h] [rbp-68h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h]
  _QWORD v46[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v47; // [rsp+C0h] [rbp-40h]
  char v48[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v49[52]; // [rsp+F0h] [rbp-10h] BYREF
  int v50; // [rsp+124h] [rbp+24h]
  unsigned __int64 v51[35]; // [rsp+388h] [rbp+288h] BYREF

  memset_0(v49, 0, 0x3B0u);
  memset_0(v41, 0, 0x40u);
  v45 = 0;
  v34 = 0;
  v44 = 0;
  v2 = 0;
  BtDbDatabaseInitialize(v49);
  *(_BYTE *)Parameter = 2;
  PrefetchServiceThreadPrivileges = PfSvGetPrefetchServiceThreadPrivileges(1);
  if ( !PrefetchServiceThreadPrivileges )
  {
    v2 = 1;
    if ( (Parameter[951] & 4) != 0 )
    {
      CurrentThread = GetCurrentThread();
      PfSetIoPriorityThread(CurrentThread);
    }
    v4 = *Parameter;
    if ( ((*Parameter >> 14) & 7) != 0 )
    {
      v34 = 1;
      PrefetchServiceThreadPrivileges = PfSvScenCtxPrefetchStart(
                                          *(_QWORD *)&PfSvcGlobals + 3696LL,
                                          (*Parameter >> 14) & 7,
                                          Parameter[1]);
      if ( PrefetchServiceThreadPrivileges )
        goto LABEL_28;
      v4 = *Parameter;
    }
    if ( (v4 & 0x20000) != 0 )
    {
      if ( (v4 & 0x200000) != 0 )
      {
        if ( !WaitForSingleObject(*((HANDLE *)Parameter + 483), 0x7D0u) )
        {
          PrefetchServiceThreadPrivileges = 1235;
          goto LABEL_28;
        }
        v4 = *Parameter;
      }
      v5 = Parameter + 6;
      v6 = (v4 >> 18) & 7;
      for ( i = 6; i >= v6; --i )
      {
        *((_WORD *)Parameter + 1926) = i;
        v31 = 0;
        Similar = 0;
        v37 = 0;
        BtDbDatabaseCleanup(v49);
        BtDbDatabaseInitialize(v49);
        memset_0(v46, 0, 0x40u);
        v46[0] = Parameter + 6;
        v8 = (_QWORD *)*v5;
        if ( (_QWORD *)*v5 == v5 || !v8 )
        {
          v47 = 3;
          v9 = (unsigned __int64 *)(Parameter + 172);
        }
        else
        {
          v47 = 4;
          v9 = v8 + 9;
        }
        B_TREE<_BTDB_RANGE_TREE_KEY,_BTDB_RANGE_ENTRY,512,BTDB_NODE_POOL,B_TREE_KEY_COMPARATOR<_BTDB_RANGE_TREE_KEY>>::BTreeIteratorAttachEx(
          (__int64)v48,
          v9);
        v46[1] = v10;
        while ( 1 )
        {
          Next = BtDbIteratorGetNext(v46);
          v12 = (_BYTE *)Next;
          if ( !Next )
            break;
          if ( (*(_DWORD *)(Next + 8) & 7) == i )
          {
            v13 = *(_DWORD *)(Next + 4);
            if ( (*v12 & 1) != 0 )
            {
              v14 = v13 >> 20;
              v15 = (char *)(Parameter + 20);
              v16 = 0;
            }
            else
            {
              v14 = v13 >> 12;
              v15 = (char *)(Parameter + 40);
              v16 = 1;
            }
            v40 = v15;
            v38 = (-(__int64)(v16 != 0) & 0xFFFFFFFFFFFFFFE8uLL) + 56;
            v18 = (v14 - 1) % *((_DWORD *)v15 + 10);
            v17 = (v14 - 1) / *((_DWORD *)v15 + 10);
            v19 = v18;
            v32 = v18;
            v35 = v17;
            if ( (unsigned int)v17 >= *((_DWORD *)v15 + 11) )
            {
              PfsForceCrash(3221226528LL, 0, 0);
              v15 = v40;
              v17 = v35;
              v19 = v32;
            }
            v20 = *((_DWORD *)v15 + 7) * v19
                + v38
                + (-(__int64)*((unsigned int *)v15 + 8)
                 & (*((unsigned int *)v15 + 8) + *(_QWORD *)(112 * v17 + *(_QWORD *)v15) + 3LL));
            v21 = v12[1];
            v30 = v21;
            v39 = v20;
            if ( v37 != v20 )
            {
              Similar = BtDbRangesGetSimilar(v49, Parameter + 6, v20, 1);
              if ( !Similar )
              {
LABEL_26:
                PrefetchServiceThreadPrivileges = 8;
                goto LABEL_27;
              }
              v21 = v30;
              v37 = v39;
            }
            v33 = v21 + 1;
            BtDbFillLogEntryForRange(v12, &v44);
            if ( !BtDbRangeCreate(v49, Similar, &v44, v33) )
              goto LABEL_26;
            v31 += v33;
            if ( v31 >= 0x4000 )
            {
              memset_0(v41, 0, 0x40u);
              v42 = 3;
              v41[0] = v49;
              v41[1] = v51;
              B_TREE<_BTDB_RANGE_TREE_KEY,_BTDB_RANGE_ENTRY,512,BTDB_NODE_POOL,B_TREE_KEY_COMPARATOR<_BTDB_RANGE_TREE_KEY>>::BTreeIteratorAttachEx(
                (__int64)v43,
                v51);
              PrefetchServiceThreadPrivileges = BtDbDatabasePrefetch(
                                                  (struct _BTDB_ITERATOR *)v41,
                                                  (struct _PREFETCH_INTERNAL_PARAMS *)(Parameter + 950));
              PrefetchParamsCleanup(Parameter + 950);
              if ( PrefetchServiceThreadPrivileges )
                goto LABEL_27;
              Similar = 0;
              v31 = 0;
              v37 = 0;
              BtDbDatabaseCleanup(v49);
              BtDbDatabaseInitialize(v49);
            }
          }
        }
        if ( v50 )
        {
          BtDbIteratorInitForPrefetch(v41);
          PrefetchServiceThreadPrivileges = BtDbDatabasePrefetch(
                                              (struct _BTDB_ITERATOR *)v41,
                                              (struct _PREFETCH_INTERNAL_PARAMS *)(Parameter + 950));
          PrefetchParamsCleanup(Parameter + 950);
          if ( PrefetchServiceThreadPrivileges )
            break;
        }
      }
LABEL_27:
      v2 = 1;
    }
    else
    {
      for ( j = 0; (unsigned int)j < 4; j = (unsigned int)(j + 1) )
      {
        if ( Parameter[236 * (unsigned int)j + 19] )
        {
          BtDbIteratorInitForPrefetch(v41);
          PrefetchServiceThreadPrivileges = BtDbDatabasePrefetch(
                                              (struct _BTDB_ITERATOR *)v41,
                                              (struct _PREFETCH_INTERNAL_PARAMS *)&Parameter[20 * j + 950]);
          if ( PrefetchServiceThreadPrivileges )
            break;
        }
      }
    }
  }
LABEL_28:
  v22 = *Parameter;
  if ( v34 )
  {
    v23 = *(_DWORD **)&PfSvcGlobals;
    v24 = Parameter[1];
    v25 = (v22 >> 14) & 7;
    v26 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)&PfSvcGlobals + 3720LL);
    EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&PfSvcGlobals + 3720LL));
    if ( v23[940] == v25 && v23[944] == v24 )
    {
      --v23[942];
      ++v23[943];
      if ( !v23[942] && !v23[941] )
        PfSvScenCtxPrefetchNotifyKernel(v25, 1);
    }
    LeaveCriticalSection(v26);
  }
  else if ( (v22 & 0x1C000) != 0 )
  {
    PfSvScenCtxPrefetchFail(*(_QWORD *)&PfSvcGlobals + 3696LL, (v22 >> 14) & 7, Parameter[1]);
  }
  *(_BYTE *)Parameter = 3;
  if ( v2 )
    RevertToSelf();
  BtDbDatabaseCleanup(v49);
  return PrefetchServiceThreadPrivileges;
}

```

## disassembly

```asm
0x18002afe0  push    rbp
0x18002afe2  push    rbx
0x18002afe3  push    rsi
0x18002afe4  push    rdi
0x18002afe5  push    r12
0x18002afe7  push    r13
0x18002afe9  push    r14
0x18002afeb  push    r15
0x18002afed  lea     rbp, [rsp-3B8h]
0x18002aff5  sub     rsp, 4B8h
0x18002affc  mov     rax, cs:__security_cookie
0x18002b003  xor     rax, rsp
0x18002b006  mov     [rbp+3F0h+var_50], rax
0x18002b00d  mov     r14, rcx
0x18002b010  xor     edx, edx; Val
0x18002b012  lea     rcx, [rbp+3F0h+var_400]; void *
0x18002b016  mov     r8d, 3B0h; Size
0x18002b01c  call    memset_0
0x18002b021  xor     edx, edx; Val
0x18002b023  lea     rcx, [rsp+4F0h+var_498]; void *
0x18002b028  lea     r8d, [rdx+40h]; Size
0x18002b02c  call    memset_0
0x18002b031  xor     eax, eax
0x18002b033  lea     rcx, [rbp+3F0h+var_400]; void *
0x18002b037  xorps   xmm0, xmm0
0x18002b03a  mov     [rbp+3F0h+var_448], rax
0x18002b03e  xor     edx, edx
0x18002b040  mov     [rsp+4F0h+var_4C0], eax
0x18002b044  movups  [rbp+3F0h+var_458], xmm0
0x18002b048  xor     r13d, r13d
0x18002b04b  call    BtDbDatabaseInitialize
0x18002b050  lea     r12d, [r13+1]
0x18002b054  mov     byte ptr [r14], 2
0x18002b058  mov     ecx, r12d
0x18002b05b  call    PfSvGetPrefetchServiceThreadPrivileges
0x18002b060  mov     esi, eax
0x18002b062  test    eax, eax
0x18002b064  jnz     loc_18002B303
0x18002b06a  lea     r15, [r14+0ED8h]
0x18002b071  mov     [rsp+4F0h+var_4CC], r12d
0x18002b076  test    byte ptr [r15+4], 4
0x18002b07b  mov     r13d, r12d
0x18002b07e  jnz     loc_18002B39B
0x18002b084  mov     ebx, [r14]
0x18002b087  mov     edx, ebx
0x18002b089  shr     edx, 0Eh
0x18002b08c  and     edx, 7
0x18002b08f  jnz     loc_18002B3B0
0x18002b095  bt      ebx, 11h
0x18002b099  jnb     loc_18002B3DE
0x18002b09f  bt      ebx, 15h
0x18002b0a3  jb      loc_18002B434
0x18002b0a9  shr     ebx, 12h
0x18002b0ac  lea     r12, [r14+18h]
0x18002b0b0  and     ebx, 7
0x18002b0b3  mov     r13d, 6
0x18002b0b9  cmp     r13d, ebx
0x18002b0bc  jl      loc_18002B2FE
0x18002b0c2  xor     eax, eax
0x18002b0c4  mov     [r15+34h], r13w
0x18002b0c9  lea     rcx, [rbp+3F0h+var_400]
0x18002b0cd  mov     [rsp+4F0h+var_4C8], eax
0x18002b0d1  mov     [rsp+4F0h+var_4B8], 0
0x18002b0da  mov     [rsp+4F0h+var_4B0], 0
0x18002b0e3  call    BtDbDatabaseCleanup
0x18002b0e8  xor     edx, edx
0x18002b0ea  lea     rcx, [rbp+3F0h+var_400]; void *
0x18002b0ee  call    BtDbDatabaseInitialize
0x18002b0f3  xor     edx, edx; Val
0x18002b0f5  lea     rcx, [rbp+3F0h+var_440]; void *
0x18002b0f9  lea     r8d, [rdx+40h]; Size
0x18002b0fd  call    memset_0
0x18002b102  mov     [rbp+3F0h+var_440], r12
0x18002b106  mov     rdx, [r12]
0x18002b10a  cmp     rdx, r12
0x18002b10d  jnz     loc_18002B382
0x18002b113  mov     [rbp+3F0h+var_430], 3
0x18002b11a  lea     rdx, [r12+298h]
0x18002b122  lea     rcx, [rbp+3F0h+var_428]
0x18002b126  call    ?BTreeIteratorAttachEx@?$B_TREE@U_BTDB_RANGE_TREE_KEY@@U_BTDB_RANGE_ENTRY@@$0CAA@UBTDB_NODE_POOL@@U?$B_TREE_KEY_COMPARATOR@U_BTDB_RANGE_TREE_KEY@@@@@@SAPEAUNODE@?$B_TREE_HEADER@U_BTDB_RANGE_TREE_KEY@@U_BTDB_RANGE_ENTRY@@@@PEAUITERATOR@1@PEAU1@@Z; B_TREE<_BTDB_RANGE_TREE_KEY,_BTDB_RANGE_ENTRY,512,BTDB_NODE_POOL,B_TREE_KEY_COMPARATOR<_BTDB_RANGE_TREE_KEY>>::BTreeIteratorAttachEx(B_TREE<_BTDB_RANGE_TREE_KEY,_BTDB_RANGE_ENTRY,512,BTDB_NODE_POOL,B_TREE_KEY_COMPARATOR<_BTDB_RANGE_TREE_KEY>>::ITERATOR *,B_TREE<_BTDB_RANGE_TREE_KEY,_BTDB_RANGE_ENTRY,512,BTDB_NODE_POOL,B_TREE_KEY_COMPARATOR<_BTDB_RANGE_TREE_KEY>> *)
0x18002b12b  mov     [rbp+3F0h+var_438], rdx
0x18002b12f  lea     rcx, [rbp+3F0h+var_440]
0x18002b133  call    BtDbIteratorGetNext
0x18002b138  mov     rdi, rax
0x18002b13b  test    rax, rax
0x18002b13e  jz      loc_18002B47C
0x18002b144  mov     ecx, [rax+8]
0x18002b147  and     ecx, 7
0x18002b14a  cmp     ecx, r13d
0x18002b14d  jnz     short loc_18002B12F
0x18002b14f  test    byte ptr [rdi], 1
0x18002b152  mov     eax, [rax+4]
0x18002b155  jz      loc_18002B2B2
0x18002b15b  shr     eax, 14h
0x18002b15e  lea     r8, [r12+38h]
0x18002b163  xor     ecx, ecx
0x18002b165  neg     ecx
0x18002b167  mov     [rsp+4F0h+var_4A0], r8
0x18002b16c  sbb     rcx, rcx
0x18002b16f  xor     edx, edx
0x18002b171  and     rcx, 0FFFFFFFFFFFFFFE8h
0x18002b175  add     rcx, 38h ; '8'
0x18002b179  dec     eax
0x18002b17b  mov     [rsp+4F0h+var_4A8], rcx
0x18002b180  div     dword ptr [r8+28h]
0x18002b184  mov     r9d, edx
0x18002b187  mov     [rsp+4F0h+var_4C4], edx
0x18002b18b  mov     [rsp+4F0h+var_4BC], eax
0x18002b18f  cmp     eax, [r8+2Ch]
0x18002b193  jnb     loc_18002B459
0x18002b199  mov     edx, [r8+20h]
0x18002b19d  imul    r9d, [r8+1Ch]
0x18002b1a2  imul    rcx, rax, 70h ; 'p'
0x18002b1a6  mov     rax, [r8]
0x18002b1a9  mov     rax, [rcx+rax]
0x18002b1ad  add     rax, 3
0x18002b1b1  mov     ecx, r9d
0x18002b1b4  add     rax, rdx
0x18002b1b7  neg     rdx
0x18002b1ba  and     rax, rdx
0x18002b1bd  add     rax, [rsp+4F0h+var_4A8]
0x18002b1c2  add     rax, rcx
0x18002b1c5  mov     cl, [rdi+1]
0x18002b1c8  mov     [rsp+4F0h+var_4D0], cl
0x18002b1cc  mov     [rsp+4F0h+var_4A8], rax
0x18002b1d1  cmp     [rsp+4F0h+var_4B0], rax
0x18002b1d6  jnz     loc_18002B2C7
0x18002b1dc  movzx   eax, cl
0x18002b1df  lea     rdx, [rbp+3F0h+var_458]
0x18002b1e3  inc     eax
0x18002b1e5  mov     rcx, rdi
0x18002b1e8  mov     [rsp+4F0h+var_4C4], eax
0x18002b1ec  call    BtDbFillLogEntryForRange
0x18002b1f1  mov     edi, [rsp+4F0h+var_4C4]
0x18002b1f5  lea     r8, [rbp+3F0h+var_458]
0x18002b1f9  mov     rdx, [rsp+4F0h+var_4B8]
0x18002b1fe  lea     rcx, [rbp+3F0h+var_400]
0x18002b202  mov     r9d, edi
0x18002b205  call    BtDbRangeCreate
0x18002b20a  test    rax, rax
0x18002b20d  jz      loc_18002B2F9
0x18002b213  mov     eax, [rsp+4F0h+var_4C8]
0x18002b217  add     eax, edi
0x18002b219  mov     [rsp+4F0h+var_4C8], eax
0x18002b21d  cmp     eax, 4000h
0x18002b222  jb      loc_18002B12F
0x18002b228  xor     edx, edx; Val
0x18002b22a  lea     rcx, [rsp+4F0h+var_498]; void *
0x18002b22f  lea     r8d, [rdx+40h]; Size
0x18002b233  call    memset_0
0x18002b238  lea     rax, [rbp+3F0h+var_400]
0x18002b23c  mov     [rsp+4F0h+var_488], 3
0x18002b244  mov     [rsp+4F0h+var_498], rax
0x18002b249  lea     rdx, [rbp+3F0h+var_168]
0x18002b250  lea     rax, [rbp+3F0h+var_168]
0x18002b257  lea     rcx, [rsp+4F0h+var_480]
0x18002b25c  mov     [rsp+4F0h+var_490], rax
0x18002b261  call    ?BTreeIteratorAttachEx@?$B_TREE@U_BTDB_RANGE_TREE_KEY@@U_BTDB_RANGE_ENTRY@@$0CAA@UBTDB_NODE_POOL@@U?$B_TREE_KEY_COMPARATOR@U_BTDB_RANGE_TREE_KEY@@@@@@SAPEAUNODE@?$B_TREE_HEADER@U_BTDB_RANGE_TREE_KEY@@U_BTDB_RANGE_ENTRY@@@@PEAUITERATOR@1@PEAU1@@Z; B_TREE<_BTDB_RANGE_TREE_KEY,_BTDB_RANGE_ENTRY,512,BTDB_NODE_POOL,B_TREE_KEY_COMPARATOR<_BTDB_RANGE_TREE_KEY>>::BTreeIteratorAttachEx(B_TREE<_BTDB_RANGE_TREE_KEY,_BTDB_RANGE_ENTRY,512,BTDB_NODE_POOL,B_TREE_KEY_COMPARATOR<_BTDB_RANGE_TREE_KEY>>::ITERATOR *,B_TREE<_BTDB_RANGE_TREE_KEY,_BTDB_RANGE_ENTRY,512,BTDB_NODE_POOL,B_TREE_KEY_COMPARATOR<_BTDB_RANGE_TREE_KEY>> *)
0x18002b266  lea     rcx, [rsp+4F0h+var_498]; struct _BTDB_ITERATOR *
0x18002b26b  mov     rdx, r15; struct _PREFETCH_INTERNAL_PARAMS *
0x18002b26e  call    BtDbDatabasePrefetch
0x18002b273  mov     rcx, r15
0x18002b276  mov     esi, eax
0x18002b278  call    PrefetchParamsCleanup
0x18002b27d  test    esi, esi
0x18002b27f  jnz     short loc_18002B2FE
0x18002b281  xor     eax, eax
0x18002b283  mov     [rsp+4F0h+var_4B8], 0
0x18002b28c  lea     rcx, [rbp+3F0h+var_400]
0x18002b290  mov     [rsp+4F0h+var_4C8], eax
0x18002b294  mov     [rsp+4F0h+var_4B0], 0
0x18002b29d  call    BtDbDatabaseCleanup
0x18002b2a2  xor     edx, edx
0x18002b2a4  lea     rcx, [rbp+3F0h+var_400]; void *
0x18002b2a8  call    BtDbDatabaseInitialize
0x18002b2ad  jmp     loc_18002B12F
0x18002b2b2  shr     eax, 0Ch
0x18002b2b5  lea     r8, [r12+88h]
0x18002b2bd  mov     ecx, 1
0x18002b2c2  jmp     loc_18002B165
0x18002b2c7  mov     r9d, 1
0x18002b2cd  lea     rcx, [rbp+3F0h+var_400]
0x18002b2d1  mov     r8, rax
0x18002b2d4  mov     rdx, r12
0x18002b2d7  call    BtDbRangesGetSimilar
0x18002b2dc  mov     [rsp+4F0h+var_4B8], rax
0x18002b2e1  test    rax, rax
0x18002b2e4  jz      short loc_18002B2F9
0x18002b2e6  mov     rax, [rsp+4F0h+var_4A8]
0x18002b2eb  mov     cl, [rsp+4F0h+var_4D0]
0x18002b2ef  mov     [rsp+4F0h+var_4B0], rax
0x18002b2f4  jmp     loc_18002B1DC
0x18002b2f9  mov     esi, 8
0x18002b2fe  mov     r13d, [rsp+4F0h+var_4CC]
0x18002b303  cmp     [rsp+4F0h+var_4C0], 0
0x18002b308  mov     ebx, [r14]
0x18002b30b  jz      loc_18002B4FB
0x18002b311  mov     rdi, cs:PfSvcGlobals
0x18002b318  mov     r12d, [r14+4]
0x18002b31c  shr     ebx, 0Eh
0x18002b31f  and     ebx, 7
0x18002b322  lea     r15, [rdi+0E88h]
0x18002b329  mov     rcx, r15; lpCriticalSection
0x18002b32c  call    cs:__imp_EnterCriticalSection
0x18002b332  cmp     [rdi+0EB0h], ebx
0x18002b338  jz      loc_18002B4B7
0x18002b33e  mov     rcx, r15; lpCriticalSection
0x18002b341  call    cs:__imp_LeaveCriticalSection
0x18002b347  mov     byte ptr [r14], 3
0x18002b34b  test    r13d, r13d
0x18002b34e  jnz     loc_18002B52B
0x18002b354  lea     rcx, [rbp+3F0h+var_400]
0x18002b358  call    BtDbDatabaseCleanup
0x18002b35d  mov     eax, esi
0x18002b35f  mov     rcx, [rbp+3F0h+var_50]
0x18002b366  xor     rcx, rsp; StackCookie
0x18002b369  call    __security_check_cookie
0x18002b36e  add     rsp, 4B8h
0x18002b375  pop     r15
0x18002b377  pop     r14
0x18002b379  pop     r13
0x18002b37b  pop     r12
0x18002b37d  pop     rdi
0x18002b37e  pop     rsi
0x18002b37f  pop     rbx
0x18002b380  pop     rbp
0x18002b381  retn
0x18002b382  test    rdx, rdx
0x18002b385  jz      loc_18002B113
0x18002b38b  mov     [rbp+3F0h+var_430], 4
0x18002b392  add     rdx, 48h ; 'H'
0x18002b396  jmp     loc_18002B122
0x18002b39b  call    cs:__imp_GetCurrentThread
0x18002b3a1  mov     rcx, rax; ThreadHandle
0x18002b3a4  xor     edx, edx
0x18002b3a6  call    PfSetIoPriorityThread
0x18002b3ab  jmp     loc_18002B084
0x18002b3b0  mov     rcx, cs:PfSvcGlobals
0x18002b3b7  mov     r8d, [r14+4]
0x18002b3bb  add     rcx, 0E70h
0x18002b3c2  mov     [rsp+4F0h+var_4C0], r12d
0x18002b3c7  call    PfSvScenCtxPrefetchStart
0x18002b3cc  mov     esi, eax
0x18002b3ce  test    eax, eax
0x18002b3d0  jnz     loc_18002B303
0x18002b3d6  mov     ebx, [r14]
0x18002b3d9  jmp     loc_18002B095
0x18002b3de  xor     ebx, ebx
0x18002b3e0  cmp     ebx, 4
0x18002b3e3  jnb     loc_18002B303
0x18002b3e9  mov     edi, ebx
0x18002b3eb  imul    rdx, rdi, 3B0h
0x18002b3f2  add     rdx, 18h
0x18002b3f6  add     rdx, r14
0x18002b3f9  cmp     dword ptr [rdx+34h], 0
0x18002b3fd  jz      short loc_18002B42F
0x18002b3ff  lea     rcx, [rsp+4F0h+var_498]
0x18002b404  call    BtDbIteratorInitForPrefetch
0x18002b409  lea     rdx, [rbx+rbx*4]
0x18002b40d  shl     rdx, 4
0x18002b411  lea     rcx, [rsp+4F0h+var_498]; struct _BTDB_ITERATOR *
0x18002b416  add     rdx, 0ED8h
0x18002b41d  add     rdx, r14; struct _PREFETCH_INTERNAL_PARAMS *
0x18002b420  call    BtDbDatabasePrefetch
0x18002b425  mov     esi, eax
0x18002b427  test    eax, eax
0x18002b429  jnz     loc_18002B303
0x18002b42f  add     ebx, r12d
0x18002b432  jmp     short loc_18002B3E0
0x18002b434  mov     rcx, [r15+40h]; hHandle
0x18002b438  mov     edx, 7D0h; dwMilliseconds
0x18002b43d  call    cs:__imp_WaitForSingleObject
0x18002b443  test    eax, eax
0x18002b445  jnz     short loc_18002B451
0x18002b447  mov     esi, 4D3h
0x18002b44c  jmp     loc_18002B303
0x18002b451  mov     ebx, [r14]
0x18002b454  jmp     loc_18002B0A9
0x18002b459  xor     r8d, r8d
0x18002b45c  xor     edx, edx
0x18002b45e  mov     ecx, 0C0000420h
0x18002b463  call    cs:__imp_PfsForceCrash
0x18002b469  mov     r8, [rsp+4F0h+var_4A0]
0x18002b46e  mov     eax, [rsp+4F0h+var_4BC]
0x18002b472  mov     r9d, [rsp+4F0h+var_4C4]
0x18002b477  jmp     loc_18002B199
0x18002b47c  cmp     [rbp+3F0h+var_3CC], 0
0x18002b480  jz      short loc_18002B4AF
0x18002b482  lea     rdx, [rbp+3F0h+var_400]
0x18002b486  lea     rcx, [rsp+4F0h+var_498]
0x18002b48b  call    BtDbIteratorInitForPrefetch
0x18002b490  mov     rdx, r15; struct _PREFETCH_INTERNAL_PARAMS *
0x18002b493  lea     rcx, [rsp+4F0h+var_498]; struct _BTDB_ITERATOR *
0x18002b498  call    BtDbDatabasePrefetch
0x18002b49d  mov     rcx, r15
0x18002b4a0  mov     esi, eax
0x18002b4a2  call    PrefetchParamsCleanup
0x18002b4a7  test    esi, esi
0x18002b4a9  jnz     loc_18002B2FE
0x18002b4af  dec     r13d
  ... truncated ...
```
