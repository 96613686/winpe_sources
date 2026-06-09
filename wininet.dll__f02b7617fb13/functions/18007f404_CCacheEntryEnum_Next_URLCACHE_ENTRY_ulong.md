# CCacheEntryEnum::Next(_URLCACHE_ENTRY * * *,ulong *)

- ea: `0x18007f404`
- end: `0x18007fbbd`
- name: `?Next@CCacheEntryEnum@@QEAAJPEAPEAPEAU_URLCACHE_ENTRY@@PEAK@Z`
- size: `1977`
- prototype: `__int64 __fastcall(CCacheEntryEnum *__hidden this, struct _URLCACHE_ENTRY ***, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180041470`

## callees

- `0x180021360`
- `0x180025980`
- `0x180027ec0`
- `0x18007ec9c`
- `0x18007f404`
- `0x180080594`
- `0x180080d10`
- `0x180083dc4`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801a830c`
- `0x1801e1790`
- `0x1801e25fc`
- `0x1801e2c8c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f934`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f934`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f49c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f49c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007f670`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007f670`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007f9f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007f9f4`
- `ESENT!JetMakeKey` at `0x18007f516`
- `ESENT!JetMakeKey` at `0x18007f548`
- `ESENT!JetMakeKey` at `0x18007f516`
- `ESENT!JetMakeKey` at `0x18007f548`
- `ESENT!JetRetrieveColumn` at `0x18007f727`
- `ESENT!JetRetrieveColumn` at `0x18007f841`
- `ESENT!JetRetrieveColumn` at `0x18007f727`
- `ESENT!JetRetrieveColumn` at `0x18007f841`
- `ESENT!JetRollback` at `0x18007f8cb`
- `ESENT!JetRollback` at `0x18007f8cb`
- `ESENT!JetBeginTransaction` at `0x18007f4bd`
- `ESENT!JetBeginTransaction` at `0x18007f4bd`
- `ESENT!JetMove` at `0x18007f5b6`
- `ESENT!JetMove` at `0x18007f7ab`
- `ESENT!JetMove` at `0x18007f5b6`
- `ESENT!JetMove` at `0x18007f7ab`
- `ESENT!JetSeek` at `0x18007f575`
- `ESENT!JetSeek` at `0x18007f575`

## pseudocode

```c
__int64 __fastcall CCacheEntryEnum::Next(CCacheEntryEnum *this, struct _URLCACHE_ENTRY ***a2, unsigned int *a3)
{
  struct _URLCACHE_ENTRY *v3; // rbx
  unsigned int *v4; // rax
  struct _RTL_CRITICAL_SECTION *v5; // r12
  struct _URLCACHE_ENTRY **v8; // r13
  __int64 v9; // r14
  CJetContext **v10; // r15
  JET_ERR v11; // eax
  int BinaryColumn; // edi
  int v13; // r12d
  CJetContext *v14; // rcx
  JET_ERR Key; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  __int64 v18; // rcx
  struct _URLCACHE_ENTRY **Heap; // rax
  struct _URLCACHE_ENTRY **v20; // rdi
  struct _URLCACHE_ENTRY *v21; // rax
  struct _URLCACHE_ENTRY *v22; // rdi
  JET_SESID *v23; // rdi
  JET_ERR v24; // eax
  JET_ERR v25; // eax
  JET_SESID *v26; // rdi
  JET_ERR v27; // eax
  unsigned int v28; // edx
  __int64 v30; // r15
  struct _URLCACHE_ENTRY **v31; // rsi
  struct _URLCACHE_ENTRY *v32; // r8
  bool v33; // zf
  unsigned int v34; // r9d
  int v35; // edx
  unsigned int v36; // r8d
  int v37; // [rsp+40h] [rbp-49h]
  struct _URLCACHE_ENTRY *v38; // [rsp+50h] [rbp-39h] BYREF
  struct _URLCACHE_ENTRY **v39; // [rsp+58h] [rbp-31h] BYREF
  unsigned int *v40; // [rsp+60h] [rbp-29h]
  struct _URLCACHE_ENTRY ***v41; // [rsp+68h] [rbp-21h]
  struct _RTL_CRITICAL_SECTION *v42; // [rsp+70h] [rbp-19h]
  unsigned int pcbActual; // [rsp+78h] [rbp-11h] BYREF
  int v44; // [rsp+7Ch] [rbp-Dh]
  int v45; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int8 *v46; // [rsp+88h] [rbp-1h] BYREF
  unsigned int v47; // [rsp+90h] [rbp+7h] BYREF
  __int64 pvData; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v49; // [rsp+A0h] [rbp+17h] BYREF

  v41 = a2;
  v3 = 0;
  v44 = 0;
  v4 = a3;
  v38 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v40 = a3;
  v45 = 0;
  v42 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v37 = 0;
  v8 = 0;
  v47 = 0;
  v9 = 0;
  v46 = 0;
  v39 = 0;
  v49 = 0;
  pvData = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    WPP_SF_qqq(
      1036,
      83,
      (unsigned int)WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids,
      (_DWORD)this,
      (__int64)a2,
      (__int64)a3);
    v4 = v40;
  }
  if ( a2 )
    *a2 = 0;
  if ( v4 )
    *v4 = 0;
  if ( v5 )
  {
    EnterCriticalSection(v5);
    v37 = 1;
  }
  v10 = (CJetContext **)((char *)this + 72);
  if ( !*((_QWORD *)this + 9) )
  {
    BinaryColumn = CJetContextList::AcquireContext(
                     *(CJetContextList **)(*(_QWORD *)(*((_QWORD *)this + 7) + 40LL) + 152LL),
                     (struct CJetContext **)this + 9,
                     0);
    if ( BinaryColumn < 0 )
    {
      v44 = 3250;
      goto LABEL_51;
    }
    BinaryColumn = CJetContext::SetCurrentIndex(*v10, 0, L"HashEntryIdIndex", v34);
    if ( BinaryColumn < 0 )
    {
      v44 = 3255;
      goto LABEL_51;
    }
    *((_QWORD *)this + 13) = 0;
    *((_QWORD *)this + 12) = 0xFFFFFFFFLL;
  }
  v11 = JetBeginTransaction(*((_QWORD *)*v10 + 2));
  BinaryColumn = HRESULTFromJET_ERR(v11, 1);
  if ( BinaryColumn >= 0 )
  {
    v13 = 0;
    if ( *((_QWORD *)this + 12) != 0xFFFFFFFFLL || *((_QWORD *)this + 13) )
    {
      v14 = *v10;
      v49 = *((_QWORD *)this + 12);
      pvData = *((_QWORD *)this + 13);
      Key = JetMakeKey(*((_QWORD *)v14 + 2), *((_QWORD *)v14 + 4), &pvData, 8u, 1u);
      BinaryColumn = HRESULTFromJET_ERR(Key, 1);
      if ( BinaryColumn < 0 )
        goto LABEL_50;
      v16 = JetMakeKey(*((_QWORD *)*v10 + 2), *((_QWORD *)*v10 + 4), &v49, 8u, 0);
      BinaryColumn = HRESULTFromJET_ERR(v16, 1);
      if ( BinaryColumn < 0 )
        goto LABEL_50;
      v17 = JetSeek(*((_QWORD *)*v10 + 2), *((_QWORD *)*v10 + 4), 8u);
      if ( v17 == 1039 )
        goto LABEL_20;
      if ( v17 == -1601 )
      {
        v44 = 3301;
        goto LABEL_83;
      }
      v13 = 1;
    }
    else
    {
      v17 = JetMove(*((_QWORD *)*v10 + 2), *((_QWORD *)*v10 + 4), 0x80000000, 0);
      if ( v17 == -1603 )
      {
        v44 = 3278;
        goto LABEL_83;
      }
    }
    BinaryColumn = HRESULTFromJET_ERR(v17, 1);
    if ( BinaryColumn < 0 )
      goto LABEL_50;
LABEL_20:
    v44 = 0;
    Heap = (struct _URLCACHE_ENTRY **)WxAllocateHeapEx(v18, 256);
    v20 = Heap;
    if ( !Heap )
    {
      BinaryColumn = -2147024882;
      v44 = 3324;
      goto LABEL_50;
    }
    memset_0(Heap, 0, 0x100u);
    v8 = v20;
    v39 = v20;
    pcbActual = 0;
    if ( !v13 )
      goto LABEL_41;
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          v25 = JetMove(*((_QWORD *)*v10 + 2), *((_QWORD *)*v10 + 4), 1, 0);
          if ( v25 == -1603 )
          {
LABEL_48:
            if ( (_DWORD)v9 )
            {
              BinaryColumn = 0;
              v39 = 0;
              *v41 = v8;
              v8 = 0;
              *v40 = v9;
              *((_QWORD *)this + 12) = v49;
              *((_QWORD *)this + 13) = pvData;
              goto LABEL_50;
            }
            v44 = 3429;
LABEL_83:
            BinaryColumn = -2147024637;
LABEL_50:
            JetRollback(*((_QWORD *)*v10 + 2), 0);
            v5 = v42;
            goto LABEL_51;
          }
          BinaryColumn = HRESULTFromJET_ERR(v25, 1);
          if ( BinaryColumn < 0 )
            goto LABEL_50;
LABEL_41:
          v26 = (JET_SESID *)*v10;
          pcbActual = 0;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_dqd(1036, 17, (unsigned int)WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 12, (__int64)&v45);
          v27 = JetRetrieveColumn(
                  v26[2],
                  v26[4],
                  *(_DWORD *)(*(_QWORD *)(v26[5] + 8) + 48LL),
                  &v45,
                  4u,
                  &pcbActual,
                  0,
                  0);
          BinaryColumn = HRESULTFromJET_ERR(v27, 1);
          if ( BinaryColumn >= 0 )
          {
            if ( pcbActual == 4 )
              BinaryColumn = 0;
            else
              BinaryColumn = -2147418113;
          }
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_d(1036, 18, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)BinaryColumn);
          if ( BinaryColumn < 0 )
          {
            v44 = 3353;
            goto LABEL_50;
          }
        }
        while ( (v45 & *((_DWORD *)this + 20)) != v45 );
        if ( !*((_QWORD *)this + 11) )
          break;
        if ( v46 )
          WxFreeHeapEx(&v46);
        BinaryColumn = CJetContext::GetBinaryColumn(*v10, v28, &v46, &v47);
        if ( BinaryColumn < 0 )
        {
          v44 = 3372;
          goto LABEL_50;
        }
        if ( v46 )
        {
          v35 = 0;
          v36 = v47 >> 3;
          if ( v47 >> 3 )
          {
            while ( *(_QWORD *)&v46[8 * v35] != *((_QWORD *)this + 11) )
            {
              if ( ++v35 >= v36 )
                goto LABEL_93;
            }
            break;
          }
LABEL_93:
          if ( v35 != v36 )
            break;
        }
      }
      Free_URLCACHE_ENTRY(0);
      v3 = 0;
      v38 = 0;
      if ( g_fWxHeapExtensionInitialized )
        v21 = (struct _URLCACHE_ENTRY *)((__int64 (__fastcall *)(__int64))qword_180268420)(152);
      else
        v21 = (struct _URLCACHE_ENTRY *)HeapAlloc(g_hWxProcessHeap, 0, 0x98u);
      v22 = v21;
      if ( !v21 )
      {
        BinaryColumn = -2147024882;
        v44 = 3404;
        goto LABEL_50;
      }
      memset_0(v21, 0, 0x98u);
      v3 = v22;
      v38 = v22;
      BinaryColumn = CCacheContainer::GetCacheEntryAtCursor(*((CCacheContainer **)this + 7), *v10, 0, v22);
      if ( BinaryColumn < 0 )
      {
        v44 = 3406;
        goto LABEL_50;
      }
      v23 = (JET_SESID *)*v10;
      pcbActual = 0;
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_dqd(1036, 17, (unsigned int)WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 3, (__int64)&pvData);
      v24 = JetRetrieveColumn(
              v23[2],
              v23[4],
              *(_DWORD *)(*(_QWORD *)(v23[5] + 8) + 12LL),
              &pvData,
              8u,
              &pcbActual,
              0,
              0);
      BinaryColumn = HRESULTFromJET_ERR(v24, 1);
      if ( BinaryColumn >= 0 )
      {
        if ( pcbActual == 8 )
          BinaryColumn = 0;
        else
          BinaryColumn = -2147418113;
      }
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_d(1036, 18, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)BinaryColumn);
      if ( BinaryColumn < 0 )
      {
        v44 = 3411;
        goto LABEL_50;
      }
      v49 = *(_QWORD *)v3;
      v8[v9] = v3;
      v9 = (unsigned int)(v9 + 1);
      v3 = 0;
      v38 = 0;
      if ( (_DWORD)v9 == 32 )
        goto LABEL_48;
    }
  }
LABEL_51:
  Free_URLCACHE_ENTRY(v3);
  if ( v8 && (_DWORD)v9 )
  {
    v30 = 0;
    do
    {
      v31 = &v8[v30];
      Free_URLCACHE_ENTRY(*v31);
      if ( v31 )
      {
        v32 = *v31;
        if ( *v31 )
        {
          v33 = g_fWxHeapExtensionInitialized == 0;
          *v31 = 0;
          if ( v33 )
            HeapFree(g_hWxProcessHeap, 0, v32);
          else
            g_WxHeapExtensionInterfaces(v32);
          *v31 = 0;
        }
      }
      v30 = (unsigned int)(v30 + 1);
    }
    while ( (unsigned int)v30 < (unsigned int)v9 );
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 84, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (unsigned int)BinaryColumn);
  if ( v8 )
    WxFreeHeapEx(&v39);
  if ( v3 )
    WxFreeHeapEx(&v38);
  if ( v46 )
    WxFreeHeapEx(&v46);
  if ( v37 && v5 )
    LeaveCriticalSection(v5);
  return (unsigned int)BinaryColumn;
}

```

## disassembly

```asm
0x18007f404  mov     [rsp-8+arg_18], rbx
0x18007f409  push    rbp
0x18007f40a  push    rsi
0x18007f40b  push    rdi
0x18007f40c  push    r12
0x18007f40e  push    r13
0x18007f410  push    r14
0x18007f412  push    r15
0x18007f414  lea     rbp, [rsp-27h]
0x18007f419  sub     rsp, 0B0h
0x18007f420  mov     rax, cs:__security_cookie
0x18007f427  xor     rax, rsp
0x18007f42a  mov     [rbp+57h+var_38], rax
0x18007f42e  xor     r15d, r15d
0x18007f431  mov     [rbp+57h+var_78], rdx
0x18007f435  mov     ebx, r15d
0x18007f438  mov     [rbp+57h+var_64], r15d
0x18007f43c  mov     rax, r8
0x18007f43f  mov     [rbp+57h+var_90], rbx
0x18007f443  lea     r12, [rcx+10h]
0x18007f447  mov     [rbp+57h+var_80], rax
0x18007f44b  mov     rdi, rdx
0x18007f44e  mov     [rbp+57h+var_60], r15d
0x18007f452  mov     rsi, rcx
0x18007f455  mov     [rbp+57h+var_70], r12
0x18007f459  mov     [rbp+57h+var_A0], r15d
0x18007f45d  mov     r13d, r15d
0x18007f460  mov     [rbp+57h+var_50], r15d
0x18007f464  mov     r14d, r15d
0x18007f467  mov     [rbp+57h+var_58], r15
0x18007f46b  mov     [rbp+57h+var_88], r15
0x18007f46f  mov     [rbp+57h+var_40], r15
0x18007f473  mov     [rbp+57h+pvData], r15
0x18007f477  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007f47e  jnz     loc_18007F976
0x18007f484  test    rdi, rdi
0x18007f487  jz      short loc_18007F48C
0x18007f489  mov     [rdi], r15
0x18007f48c  test    rax, rax
0x18007f48f  jz      short loc_18007F494
0x18007f491  mov     [rax], r15d
0x18007f494  test    r12, r12
0x18007f497  jz      short loc_18007F4A9
0x18007f499  mov     rcx, r12; lpCriticalSection
0x18007f49c  call    cs:__imp_EnterCriticalSection
0x18007f4a2  mov     [rbp+57h+var_A0], 1
0x18007f4a9  lea     r15, [rsi+48h]
0x18007f4ad  cmp     [r15], rbx
0x18007f4b0  jz      loc_18007FA0E
0x18007f4b6  mov     rcx, [r15]
0x18007f4b9  mov     rcx, [rcx+10h]; sesid
0x18007f4bd  call    cs:__imp_JetBeginTransaction
0x18007f4c3  mov     ecx, eax; int
0x18007f4c5  mov     edx, 1; int
0x18007f4ca  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18007f4cf  mov     edi, eax
0x18007f4d1  test    eax, eax
0x18007f4d3  js      loc_18007F8D5
0x18007f4d9  mov     rax, [rsi+60h]
0x18007f4dd  xor     r12d, r12d
0x18007f4e0  mov     ecx, 0FFFFFFFFh
0x18007f4e5  cmp     rax, rcx
0x18007f4e8  jz      loc_18007F598
0x18007f4ee  mov     rcx, [r15]
0x18007f4f1  lea     r8, [rbp+57h+pvData]; pvData
0x18007f4f5  mov     [rbp+57h+var_40], rax
0x18007f4f9  mov     edi, 1
0x18007f4fe  mov     rax, [rsi+68h]
0x18007f502  mov     [rbp+57h+pvData], rax
0x18007f506  mov     rdx, [rcx+20h]; tableid
0x18007f50a  mov     rcx, [rcx+10h]; sesid
0x18007f50e  lea     r9d, [rdi+7]; cbData
0x18007f512  mov     [rsp+0E0h+grbit], edi; grbit
0x18007f516  call    cs:__imp_JetMakeKey
0x18007f51c  mov     ecx, eax; int
0x18007f51e  mov     edx, edi; int
0x18007f520  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18007f525  mov     edi, eax
0x18007f527  test    eax, eax
0x18007f529  js      loc_18007F8C2
0x18007f52f  mov     rcx, [r15]
0x18007f532  lea     r8, [rbp+57h+var_40]; pvData
0x18007f536  mov     r9d, 8; cbData
0x18007f53c  mov     [rsp+0E0h+grbit], ebx; grbit
0x18007f540  mov     rdx, [rcx+20h]; tableid
0x18007f544  mov     rcx, [rcx+10h]; sesid
0x18007f548  call    cs:__imp_JetMakeKey
0x18007f54e  mov     ecx, eax; int
0x18007f550  mov     edx, 1; int
0x18007f555  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18007f55a  mov     edi, eax
0x18007f55c  test    eax, eax
0x18007f55e  js      loc_18007F8C2
0x18007f564  mov     rcx, [r15]
0x18007f567  mov     r8d, 8; grbit
0x18007f56d  mov     rdx, [rcx+20h]; tableid
0x18007f571  mov     rcx, [rcx+10h]; sesid
0x18007f575  call    cs:__imp_JetSeek
0x18007f57b  cmp     eax, 40Fh
0x18007f580  jz      short loc_18007F5DD
0x18007f582  cmp     eax, 0FFFFF9BFh
0x18007f587  jz      loc_18007FAAB
0x18007f58d  mov     r12d, 1
0x18007f593  mov     edx, r12d
0x18007f596  jmp     short loc_18007F5CC
0x18007f598  cmp     [rsi+68h], rbx
0x18007f59c  jnz     loc_18007F4EE
0x18007f5a2  mov     rcx, [r15]
0x18007f5a5  xor     r9d, r9d; grbit
0x18007f5a8  mov     r8d, 80000000h; cRow
0x18007f5ae  mov     rdx, [rcx+20h]; tableid
0x18007f5b2  mov     rcx, [rcx+10h]; sesid
0x18007f5b6  call    cs:__imp_JetMove
0x18007f5bc  cmp     eax, 0FFFFF9BDh
0x18007f5c1  jz      loc_18007FB4F
0x18007f5c7  mov     edx, 1; int
0x18007f5cc  mov     ecx, eax; int
0x18007f5ce  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18007f5d3  mov     edi, eax
0x18007f5d5  test    eax, eax
0x18007f5d7  js      loc_18007F8C2
0x18007f5dd  mov     edx, 100h
0x18007f5e2  mov     [rbp+57h+var_64], ebx
0x18007f5e5  call    WxAllocateHeapEx
0x18007f5ea  mov     rdi, rax
0x18007f5ed  test    rax, rax
0x18007f5f0  jz      loc_18007FB5B
0x18007f5f6  xor     edx, edx; Val
0x18007f5f8  mov     r8d, 100h; Size
0x18007f5fe  mov     rcx, rax; void *
0x18007f601  call    memset_0
0x18007f606  mov     r13, rdi
0x18007f609  mov     [rbp+57h+var_88], rdi
0x18007f60d  mov     [rbp+57h+var_68], ebx
0x18007f610  test    r12d, r12d
0x18007f613  jz      loc_18007F963
0x18007f619  xor     r12d, r12d
0x18007f61c  jmp     loc_18007F796
0x18007f621  test    edi, edi
0x18007f623  js      loc_18007FBA3
0x18007f629  mov     eax, [rsi+50h]
0x18007f62c  and     eax, [rbp+57h+var_60]
0x18007f62f  cmp     eax, [rbp+57h+var_60]
0x18007f632  jnz     loc_18007F796
0x18007f638  cmp     [rsi+58h], r12
0x18007f63c  jnz     loc_18007FAD0
0x18007f642  xor     ecx, ecx; struct _URLCACHE_ENTRY *
0x18007f644  call    ?Free_URLCACHE_ENTRY@@YAXPEAU_URLCACHE_ENTRY@@@Z; Free_URLCACHE_ENTRY(_URLCACHE_ENTRY *)
0x18007f649  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r12d; int g_fWxHeapExtensionInitialized
0x18007f650  mov     rbx, r12
0x18007f653  mov     [rbp+57h+var_90], rbx
0x18007f657  mov     [rbp+57h+var_94], r12d
0x18007f65b  jnz     loc_18007FA95
0x18007f661  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18007f668  xor     edx, edx; dwFlags
0x18007f66a  mov     r8d, 98h; dwBytes
0x18007f670  call    cs:__imp_HeapAlloc
0x18007f676  mov     rdi, rax
0x18007f679  test    rax, rax
0x18007f67c  jz      loc_18007FB8B
0x18007f682  xor     edx, edx; Val
0x18007f684  mov     r8d, 98h; Size
0x18007f68a  mov     rcx, rax; void *
0x18007f68d  call    memset_0
0x18007f692  mov     rbx, rdi
0x18007f695  mov     [rbp+57h+var_90], rbx
0x18007f699  mov     rdx, [r15]; struct CJetContext *
0x18007f69c  mov     r9, rdi; struct _URLCACHE_ENTRY *
0x18007f69f  mov     rcx, [rsi+38h]; this
0x18007f6a3  xor     r8d, r8d; int
0x18007f6a6  call    ?GetCacheEntryAtCursor@CCacheContainer@@QEAAJPEAVCJetContext@@HPEAU_URLCACHE_ENTRY@@@Z; CCacheContainer::GetCacheEntryAtCursor(CJetContext *,int,_URLCACHE_ENTRY *)
0x18007f6ab  mov     edi, eax
0x18007f6ad  test    eax, eax
0x18007f6af  js      loc_18007FA5B
0x18007f6b5  mov     rdi, [r15]
0x18007f6b8  mov     [rbp+57h+var_94], r12d
0x18007f6bc  mov     [rbp+57h+var_68], r12d
0x18007f6c0  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007f6c7  jz      short loc_18007F6F4
0x18007f6c9  mov     edx, 11h
0x18007f6ce  mov     dword ptr [rsp+0E0h+pcbActual], 8
0x18007f6d6  lea     rax, [rbp+57h+pvData]
0x18007f6da  mov     ecx, 40Ch
0x18007f6df  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x18007f6e6  mov     qword ptr [rsp+0E0h+grbit], rax
0x18007f6eb  lea     r9d, [rdx-0Eh]
0x18007f6ef  call    WPP_SF_dqd
0x18007f6f4  mov     rax, [rdi+28h]
0x18007f6f8  lea     r9, [rbp+57h+pvData]; pvData
0x18007f6fc  mov     rdx, [rdi+20h]; tableid
0x18007f700  mov     rcx, [rdi+10h]; sesid
0x18007f704  mov     [rsp+0E0h+pretinfo], r12; pretinfo
0x18007f709  mov     r8, [rax+8]
0x18007f70d  lea     rax, [rbp+57h+var_68]
0x18007f711  mov     [rsp+0E0h+var_B0], r12d; grbit
0x18007f716  mov     [rsp+0E0h+pcbActual], rax; pcbActual
0x18007f71b  mov     [rsp+0E0h+grbit], 8; cbData
0x18007f723  mov     r8d, [r8+0Ch]; columnid
0x18007f727  call    cs:__imp_JetRetrieveColumn
0x18007f72d  mov     ecx, eax; int
0x18007f72f  mov     edx, 1; int
0x18007f734  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18007f739  mov     edi, eax
0x18007f73b  test    eax, eax
0x18007f73d  js      short loc_18007F74C
0x18007f73f  cmp     [rbp+57h+var_68], 8
0x18007f743  jnz     loc_18007FA78
0x18007f749  mov     edi, r12d
0x18007f74c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007f753  jz      short loc_18007F76E
0x18007f755  mov     edx, 12h
0x18007f75a  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x18007f761  mov     ecx, 40Ch
0x18007f766  mov     r9d, edi
0x18007f769  call    WPP_SF_d
0x18007f76e  test    edi, edi
0x18007f770  js      loc_18007FB7F
0x18007f776  mov     rax, [rbx]
0x18007f779  mov     [rbp+57h+var_40], rax
0x18007f77d  mov     [r13+r14*8+0], rbx
0x18007f782  inc     r14d
0x18007f785  mov     rbx, r12
0x18007f788  mov     [rbp+57h+var_90], rbx
0x18007f78c  cmp     r14d, 20h ; ' '
0x18007f790  jz      loc_18007F891
0x18007f796  mov     rcx, [r15]
0x18007f799  xor     r9d, r9d; grbit
0x18007f79c  mov     rdx, [rcx+20h]; tableid
0x18007f7a0  lea     edi, [r9+1]
0x18007f7a4  mov     rcx, [rcx+10h]; sesid
0x18007f7a8  mov     r8d, edi; cRow
0x18007f7ab  call    cs:__imp_JetMove
0x18007f7b1  cmp     eax, 0FFFFF9BDh
0x18007f7b6  jz      loc_18007F891
0x18007f7bc  mov     edx, edi; int
0x18007f7be  mov     ecx, eax; int
0x18007f7c0  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18007f7c5  mov     edi, eax
0x18007f7c7  test    eax, eax
0x18007f7c9  js      loc_18007F8C2
0x18007f7cf  mov     rdi, [r15]
0x18007f7d2  mov     [rbp+57h+var_94], r12d
0x18007f7d6  mov     [rbp+57h+var_68], r12d
0x18007f7da  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007f7e1  jz      short loc_18007F80E
0x18007f7e3  mov     edx, 11h
0x18007f7e8  mov     dword ptr [rsp+0E0h+pcbActual], 4
0x18007f7f0  lea     rax, [rbp+57h+var_60]
0x18007f7f4  mov     ecx, 40Ch
0x18007f7f9  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x18007f800  mov     qword ptr [rsp+0E0h+grbit], rax
0x18007f805  lea     r9d, [rdx-5]
0x18007f809  call    WPP_SF_dqd
0x18007f80e  mov     rax, [rdi+28h]
0x18007f812  lea     r9, [rbp+57h+var_60]; pvData
0x18007f816  mov     rdx, [rdi+20h]; tableid
0x18007f81a  mov     rcx, [rdi+10h]; sesid
0x18007f81e  mov     [rsp+0E0h+pretinfo], r12; pretinfo
0x18007f823  mov     r8, [rax+8]
0x18007f827  lea     rax, [rbp+57h+var_68]
0x18007f82b  mov     [rsp+0E0h+var_B0], r12d; grbit
0x18007f830  mov     [rsp+0E0h+pcbActual], rax; pcbActual
0x18007f835  mov     [rsp+0E0h+grbit], 4; cbData
0x18007f83d  mov     r8d, [r8+30h]; columnid
0x18007f841  call    cs:__imp_JetRetrieveColumn
0x18007f847  mov     ecx, eax; int
0x18007f849  mov     edx, 1; int
0x18007f84e  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18007f853  mov     edi, eax
0x18007f855  test    eax, eax
0x18007f857  js      short loc_18007F866
0x18007f859  cmp     [rbp+57h+var_68], 4
0x18007f85d  jnz     loc_18007FA67
0x18007f863  mov     edi, r12d
0x18007f866  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007f86d  jz      loc_18007F621
0x18007f873  mov     edx, 12h
0x18007f878  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x18007f87f  mov     ecx, 40Ch
0x18007f884  mov     r9d, edi
0x18007f887  call    WPP_SF_d
0x18007f88c  jmp     loc_18007F621
0x18007f891  test    r14d, r14d
0x18007f894  jz      loc_18007FB73
0x18007f89a  mov     rax, [rbp+57h+var_78]
0x18007f89e  mov     edi, r12d
0x18007f8a1  mov     [rbp+57h+var_88], r12
0x18007f8a5  mov     [rax], r13
0x18007f8a8  mov     r13, r12
0x18007f8ab  mov     rax, [rbp+57h+var_80]
0x18007f8af  mov     [rax], r14d
0x18007f8b2  mov     rax, [rbp+57h+var_40]
0x18007f8b6  mov     [rsi+60h], rax
0x18007f8ba  mov     rax, [rbp+57h+pvData]
0x18007f8be  mov     [rsi+68h], rax
0x18007f8c2  mov     rcx, [r15]
0x18007f8c5  xor     edx, edx; grbit
0x18007f8c7  mov     rcx, [rcx+10h]; sesid
0x18007f8cb  call    cs:__imp_JetRollback
0x18007f8d1  mov     r12, [rbp+57h+var_70]
  ... truncated ...
```
