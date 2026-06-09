# CIndexedDBServerObjectStore::Put(__MIDL_RPCIndexedDB_0004 const *,__MIDL_RPCIndexedDB_0001 const *,__MIDL_RPCIndexedDB_0001 *)

- ea: `0x18002170c`
- end: `0x180021cb2`
- name: `?Put@CIndexedDBServerObjectStore@@QEAAJPEBU__MIDL_RPCIndexedDB_0004@@PEBU__MIDL_RPCIndexedDB_0001@@PEAU3@@Z`
- size: `1446`
- prototype: `__int64 __fastcall(CIndexedDBServerObjectStore *__hidden this, const struct __MIDL_RPCIndexedDB_0004 *, const struct __MIDL_RPCIndexedDB_0001 *, struct __MIDL_RPCIndexedDB_0001 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002b830`

## callees

- `0x18000d5a0`
- `0x18000dd40`
- `0x18000f630`
- `0x18000f810`
- `0x180015a40`
- `0x180015bb0`
- `0x180016b40`
- `0x180017c20`
- `0x18001fdfc`
- `0x18002170c`
- `0x180021cc0`
- `0x180022740`
- `0x180022784`
- `0x180023250`
- `0x180024720`
- `0x18002491c`
- `0x18004ebe0`
- `0x18005111c`
- `0x18005619c`
- `0x180057794`
- `0x18005af04`
- `0x1800766b8`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800217f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021848`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800217f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021848`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021762`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800217bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021762`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800217bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021905`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002192b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021905`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002192b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CIndexedDBServerObjectStore::Put(
        CIndexedDBServerObjectStore *this,
        const struct __MIDL_RPCIndexedDB_0004 *a2,
        const struct __MIDL_RPCIndexedDB_0001 *a3,
        struct __MIDL_RPCIndexedDB_0001 *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  int inserted; // ebx
  __int64 v10; // rdi
  int v11; // ecx
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  unsigned __int64 v13; // rdi
  CEseLayerObjectStore *v14; // r10
  __int64 v15; // rcx
  __int64 v16; // rbx
  const char *v17; // r9
  unsigned __int64 v18; // rdi
  unsigned int v19; // r12d
  bool v20; // si
  const void *v21; // r9
  __int64 v22; // rcx
  char v24; // si
  unsigned int v25; // edx
  __int64 v26; // rsi
  JET_TABLEID v27; // r12
  int v28; // esi
  int *v29; // rcx
  const void *v30; // r8
  unsigned int v31; // r9d
  unsigned __int8 v32; // r12
  double v33; // xmm0_8
  IStream *v34; // rdx
  __int64 *v35; // rsi
  unsigned int v36; // r9d
  unsigned __int64 v37; // rsi
  unsigned int v38; // [rsp+20h] [rbp-89h]
  LPSTREAM ppstm; // [rsp+40h] [rbp-69h] BYREF
  __int64 *v40; // [rsp+48h] [rbp-61h]
  CEseLayerObjectStore *v41; // [rsp+50h] [rbp-59h]
  __int64 v42; // [rsp+58h] [rbp-51h] BYREF
  struct _RTL_CRITICAL_SECTION *v43; // [rsp+60h] [rbp-49h]
  int v44; // [rsp+68h] [rbp-41h]
  unsigned __int64 v45; // [rsp+70h] [rbp-39h]
  double v46; // [rsp+78h] [rbp-31h] BYREF
  void *v47; // [rsp+80h] [rbp-29h]
  char v48[8]; // [rsp+88h] [rbp-21h] BYREF
  __int64 v49; // [rsp+90h] [rbp-19h]
  __int128 v50; // [rsp+98h] [rbp-11h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-1h]
  __int128 v52; // [rsp+B0h] [rbp+7h]
  __int64 v53; // [rsp+C0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  JET_TABLEID v56; // [rsp+128h] [rbp+7Fh] BYREF

  if ( a4 )
  {
    *(_OWORD *)a4 = 0;
    *((_QWORD *)a4 + 2) = 0;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v43 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v44 = 0;
  if ( this != (CIndexedDBServerObjectStore *)-16LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v44 = 1;
  }
  inserted = -2147024891;
  if ( *((_BYTE *)this + 56) )
  {
    inserted = -2140143587;
    v10 = *((_QWORD *)this + 15);
    v11 = *(_DWORD *)(v10 + 160);
    if ( !v11 || (unsigned int)(v11 - 1) > 1 )
      goto LABEL_21;
    v48[0] = 0;
    v49 = v10;
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 88));
    v12 = (struct _RTL_CRITICAL_SECTION *)(v10 + 192);
    EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 192));
    inserted = -2147024891;
    if ( !*(_BYTE *)(v10 + 56)
      || (v13 = *(_QWORD *)(v10 + 168), !*(_BYTE *)(v13 + 8))
      || (inserted = HrJetSetSessionContext(*(_QWORD *)(v13 + 24), v13), inserted < 0) )
    {
      LeaveCriticalSection(v12);
LABEL_20:
      CIndexedDBServerTransaction::CTransactionThreadScope::~CTransactionThreadScope((CIndexedDBServerTransaction::CTransactionThreadScope *)v48);
LABEL_21:
      v8 = v43;
      goto LABEL_22;
    }
    *(_DWORD *)(v13 + 12) = GetCurrentThreadId();
    v48[0] = 1;
    v42 = 0;
    v14 = (CEseLayerObjectStore *)*((_QWORD *)this + 16);
    v41 = v14;
    v15 = *(_QWORD *)(*((_QWORD *)this + 15) + 64LL);
    if ( !a3 )
    {
      inserted = CEseLayerObjectStore::InsertObject(
                   v14,
                   0,
                   a2,
                   a4,
                   (__int64 *)((unsigned __int64)&v42 & -(__int64)(v15 != 0)));
      if ( inserted >= 0 )
      {
LABEL_18:
        *(_BYTE *)(*((_QWORD *)this + 15) + 164LL) = 1;
        v22 = *((_QWORD *)this + 15);
        if ( *(_QWORD *)(v22 + 64) )
          *(_QWORD *)(v22 + 80) += v42;
        goto LABEL_20;
      }
LABEL_15:
      switch ( inserted )
      {
        case -1906378309:
          inserted = -2140143590;
          break;
        case -2147483637:
          inserted = -2140143601;
          break;
        case -1906377716:
          inserted = -2140082174;
          break;
      }
      goto LABEL_20;
    }
    v40 = (__int64 *)((unsigned __int64)&v42 & -(__int64)(v15 != 0));
    v56 = -1;
    v16 = *((_QWORD *)v14 + 6);
    if ( *(_DWORD *)(v16 + 12) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\ese\\transaction.cxx",
        v17);
    v18 = *(_QWORD *)(v16 + 24);
    v19 = *(_DWORD *)(v16 + 32);
    v20 = 0;
    inserted = HrJetBeginTransaction(v18);
    if ( inserted < 0
      || (v20 = 1,
          inserted = HrJetOpenTable(v18, v19, (const unsigned __int16 *)v41 + 28, v21, v38, 0, &v56),
          inserted < 0) )
    {
      CloseTableIfNecessary(v18, &v56, inserted);
      RollbackIfNecessary(v18, v20, inserted);
      goto LABEL_15;
    }
    v26 = *((_QWORD *)v41 + 3);
    v27 = v56;
    v45 = v56;
    if ( !*(_DWORD *)a3 )
    {
      if ( v26 == -56 || !*(_DWORD *)(v26 + 56) )
        goto LABEL_52;
      ppstm = 0;
      inserted = AllocateIStreamFromPbCb(*(unsigned int *)a2, *((const unsigned __int8 **)a2 + 1), &ppstm);
      if ( inserted >= 0 )
      {
        v50 = 0;
        v51 = 0;
        v52 = 0;
        v53 = 0;
        inserted = CEseLayerIndexSchema::ReadFromBlobKeyPathToIndexedDbKey(
                     (CEseLayerIndexSchema *)v26,
                     ppstm,
                     (struct CEseLayerKeyHelper *)&v50);
        if ( inserted >= 0 )
          inserted = CEseLayerIndexSchema::SeekToRowUsingValidKey(
                       (CEseLayerIndexSchema *)v26,
                       v18,
                       v27,
                       (const struct __MIDL_RPCIndexedDB_0001 *)&v50,
                       1u,
                       0);
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        ppstm = 0;
        CEseLayerKeyHelper::~CEseLayerKeyHelper((CEseLayerKeyHelper *)&v50);
      }
LABEL_51:
      if ( inserted != -1906378305 )
      {
        if ( inserted < 0 )
          goto LABEL_28;
        v35 = v40;
        inserted = AdjustCurrentRowQuotaUsage(v18, v56);
        if ( inserted < 0 )
          goto LABEL_28;
        inserted = HrJetDelete(v18, v56);
        if ( inserted < 0 )
          goto LABEL_28;
        goto LABEL_53;
      }
LABEL_52:
      v35 = v40;
LABEL_53:
      inserted = CEseLayerObjectStore::InsertObject(v41, a3, a2, 0, v35);
      if ( inserted >= 0 )
      {
        inserted = HrJetCommitTransaction(v18, 1u);
        if ( inserted >= 0 )
        {
          v24 = 0;
          goto LABEL_29;
        }
      }
LABEL_28:
      v24 = 1;
LABEL_29:
      v25 = v56;
      if ( v56 != -1 && (int)HrJetCloseTable(v18, v56) >= 0 )
        v56 = -1;
      if ( v24 )
        HrJetRollback(v18, v25);
      if ( inserted >= 0 )
      {
        if ( a4 )
          IDBKeyCopy(a3, a4);
        goto LABEL_18;
      }
      goto LABEL_15;
    }
    inserted = HrJetSetCurrentIndex(v18, v56, (const unsigned __int16 *)(v26 + 712));
    if ( inserted < 0 )
      goto LABEL_51;
    v28 = *(_DWORD *)a3;
    v29 = (int *)((char *)a3 + 8);
    if ( *(_DWORD *)a3 == 4 )
    {
      v30 = (const void *)*((_QWORD *)a3 + 2);
      if ( a3 == (const struct __MIDL_RPCIndexedDB_0001 *)-8LL )
        v31 = 0;
      else
        v31 = 2 * *v29;
      ppstm = 0;
    }
    else
    {
      v34 = (const struct __MIDL_RPCIndexedDB_0001 *)((char *)a3 + 8);
      if ( v28 != 3 )
        v34 = 0;
      ppstm = v34;
      if ( v28 == 1 )
      {
        v33 = (double)*v29;
        v31 = 0;
        v30 = 0;
        v32 = 1;
LABEL_50:
        v46 = v33;
        v47 = (void *)((unsigned __int64)&v46 & -(__int64)(v32 != 0));
        inserted = HrJetMakeKey(v18, v45, v30, v31, 1u);
        if ( inserted >= 0 )
        {
          v36 = 8;
          if ( v28 != 3 )
            v36 = 0;
          v37 = v45;
          inserted = HrJetMakeKey(v18, v45, ppstm, v36, 0);
          if ( inserted >= 0 )
          {
            inserted = HrJetMakeKey(v18, v37, v47, 8 * (unsigned int)v32, 0);
            if ( inserted >= 0 )
              inserted = HrJetSeek(v18, v37, 1u);
          }
        }
        goto LABEL_51;
      }
      if ( v28 == 2 )
      {
        v30 = 0;
        v32 = 1;
        v31 = 0;
        goto LABEL_45;
      }
      v31 = 0;
      v30 = 0;
    }
    v32 = 0;
LABEL_45:
    v33 = *(double *)v29;
    goto LABEL_50;
  }
LABEL_22:
  if ( v44 && v8 )
    LeaveCriticalSection(v8);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18002170c  mov     [rsp-8+arg_10], rbx
0x180021711  mov     [rsp-8+arg_8], rdx
0x180021716  push    rbp
0x180021717  push    rsi
0x180021718  push    rdi
0x180021719  push    r12
0x18002171b  push    r13
0x18002171d  push    r14
0x18002171f  push    r15
0x180021721  lea     rbp, [rsp-27h]
0x180021726  sub     rsp, 0D0h
0x18002172d  mov     r15, r9
0x180021730  mov     r13, r8
0x180021733  mov     r12, rdx
0x180021736  mov     r14, rcx
0x180021739  test    r9, r9
0x18002173c  jz      short loc_18002174B
0x18002173e  xorps   xmm0, xmm0
0x180021741  xor     eax, eax
0x180021743  movups  xmmword ptr [r9], xmm0
0x180021747  mov     [r9+10h], rax
0x18002174b  lea     rdi, [rcx+10h]
0x18002174f  mov     [rbp+57h+var_A0], rdi
0x180021753  mov     [rbp+57h+var_98], 0
0x18002175a  test    rdi, rdi
0x18002175d  jz      short loc_18002176F
0x18002175f  mov     rcx, rdi; lpCriticalSection
0x180021762  call    cs:__imp_EnterCriticalSection
0x180021768  mov     [rbp+57h+var_98], 1
0x18002176f  mov     ebx, 80070005h
0x180021774  mov     al, [r14+38h]
0x180021778  nop
0x180021779  test    al, al
0x18002177b  jz      loc_1800218F7
0x180021781  mov     ebx, 8070001Dh
0x180021786  mov     rdi, [r14+78h]
0x18002178a  mov     ecx, [rdi+0A0h]
0x180021790  test    ecx, ecx
0x180021792  jz      loc_1800218F3
0x180021798  sub     ecx, 1
0x18002179b  jz      short loc_1800217A6
0x18002179d  cmp     ecx, 1
0x1800217a0  jnz     loc_1800218F3
0x1800217a6  mov     [rbp+57h+var_78], 0
0x1800217aa  mov     [rbp+57h+var_70], rdi
0x1800217ae  lock inc dword ptr [rdi+58h]
0x1800217b2  lea     rsi, [rdi+0C0h]
0x1800217b9  mov     rcx, rsi; lpCriticalSection
0x1800217bc  call    cs:__imp_EnterCriticalSection
0x1800217c2  mov     ebx, 80070005h
0x1800217c7  mov     al, [rdi+38h]
0x1800217ca  nop
0x1800217cb  test    al, al
0x1800217cd  jz      loc_180021928
0x1800217d3  mov     rdi, [rdi+0A8h]
0x1800217da  cmp     byte ptr [rdi+8], 0
0x1800217de  jz      loc_180021928
0x1800217e4  mov     rdx, rdi; unsigned __int64
0x1800217e7  mov     rcx, [rdi+18h]; unsigned __int64
0x1800217eb  call    ?HrJetSetSessionContext@@YAJ_K0@Z; HrJetSetSessionContext(unsigned __int64,unsigned __int64)
0x1800217f0  mov     ebx, eax
0x1800217f2  test    eax, eax
0x1800217f4  js      short loc_1800217FF
0x1800217f6  call    cs:__imp_GetCurrentThreadId
0x1800217fc  mov     [rdi+0Ch], eax
0x1800217ff  test    ebx, ebx
0x180021801  js      loc_180021928
0x180021807  mov     [rbp+57h+var_78], 1
0x18002180b  mov     [rbp+57h+var_A8], 0
0x180021813  mov     r10, [r14+80h]
0x18002181a  mov     [rbp+57h+var_B0], r10
0x18002181e  mov     rax, [r14+78h]
0x180021822  mov     rcx, [rax+40h]
0x180021826  test    r13, r13
0x180021829  jz      short loc_1800218A8
0x18002182b  neg     rcx
0x18002182e  sbb     rax, rax
0x180021831  lea     rcx, [rbp+57h+var_A8]
0x180021835  and     rax, rcx
0x180021838  mov     [rbp+57h+var_B8], rax
0x18002183c  mov     [rbp+57h+arg_18], 0FFFFFFFFFFFFFFFFh
0x180021844  mov     rbx, [r10+30h]
0x180021848  call    cs:__imp_GetCurrentThreadId
0x18002184e  mov     rcx, [rbp+5Fh]; this
0x180021852  cmp     [rbx+0Ch], eax
0x180021855  jnz     loc_180021B82
0x18002185b  mov     rdi, [rbx+18h]
0x18002185f  mov     r12d, [rbx+20h]
0x180021863  xor     sil, sil
0x180021866  mov     rcx, rdi; unsigned __int64
0x180021869  call    ?HrJetBeginTransaction@@YAJ_K@Z; HrJetBeginTransaction(unsigned __int64)
0x18002186e  mov     ebx, eax
0x180021870  test    eax, eax
0x180021872  jns     loc_180021995
0x180021878  mov     r8d, ebx; int
0x18002187b  lea     rdx, [rbp+57h+arg_18]; unsigned __int64 *
0x18002187f  mov     rcx, rdi; unsigned __int64
0x180021882  call    ?CloseTableIfNecessary@@YAJ_KPEA_KJ@Z; CloseTableIfNecessary(unsigned __int64,unsigned __int64 *,long)
0x180021887  mov     r8d, ebx; int
0x18002188a  mov     dl, sil; bool
0x18002188d  mov     rcx, rdi; unsigned __int64
0x180021890  call    ?RollbackIfNecessary@@YAJ_K_NJ@Z; RollbackIfNecessary(unsigned __int64,bool,long)
0x180021895  cmp     ebx, 8E5EF9BBh
0x18002189b  jnz     loc_180021C89
0x1800218a1  mov     ebx, 8070001Ah
0x1800218a6  jmp     short loc_1800218EA
0x1800218a8  neg     rcx
0x1800218ab  sbb     rax, rax
0x1800218ae  lea     rcx, [rbp+57h+var_A8]
0x1800218b2  and     rax, rcx
0x1800218b5  mov     qword ptr [rsp+100h+var_E0], rax; __int64 *
0x1800218ba  mov     r9, r15; struct __MIDL_RPCIndexedDB_0001 *
0x1800218bd  mov     r8, r12; struct __MIDL_RPCIndexedDB_0004 *
0x1800218c0  xor     edx, edx; struct __MIDL_RPCIndexedDB_0001 *
0x1800218c2  mov     rcx, r10; this
0x1800218c5  call    ?InsertObject@CEseLayerObjectStore@@QEAAJPEBU__MIDL_RPCIndexedDB_0001@@PEBU__MIDL_RPCIndexedDB_0004@@PEAU2@PEA_J@Z; CEseLayerObjectStore::InsertObject(__MIDL_RPCIndexedDB_0001 const *,__MIDL_RPCIndexedDB_0004 const *,__MIDL_RPCIndexedDB_0001 *,__int64 *)
0x1800218ca  mov     ebx, eax
0x1800218cc  test    eax, eax
0x1800218ce  js      short loc_180021895
0x1800218d0  mov     rax, [r14+78h]
0x1800218d4  mov     byte ptr [rax+0A4h], 1
0x1800218db  mov     rcx, [r14+78h]
0x1800218df  cmp     qword ptr [rcx+40h], 0
0x1800218e4  jnz     loc_180021C7C
0x1800218ea  lea     rcx, [rbp+57h+var_78]; this
0x1800218ee  call    ??1CTransactionThreadScope@CIndexedDBServerTransaction@@QEAA@XZ; CIndexedDBServerTransaction::CTransactionThreadScope::~CTransactionThreadScope(void)
0x1800218f3  mov     rdi, [rbp+57h+var_A0]
0x1800218f7  cmp     [rbp+57h+var_98], 0
0x1800218fb  jz      short loc_18002190B
0x1800218fd  test    rdi, rdi
0x180021900  jz      short loc_18002190B
0x180021902  mov     rcx, rdi; lpCriticalSection
0x180021905  call    cs:__imp_LeaveCriticalSection
0x18002190b  mov     eax, ebx
0x18002190d  mov     rbx, [rsp+100h+arg_10]
0x180021915  add     rsp, 0D0h
0x18002191c  pop     r15
0x18002191e  pop     r14
0x180021920  pop     r13
0x180021922  pop     r12
0x180021924  pop     rdi
0x180021925  pop     rsi
0x180021926  pop     rbp
0x180021927  retn
0x180021928  mov     rcx, rsi; lpCriticalSection
0x18002192b  call    cs:__imp_LeaveCriticalSection
0x180021931  jmp     short loc_1800218EA
0x180021933  mov     rdx, [rbp+57h+arg_18]; unsigned __int64
0x180021937  mov     rcx, rdi; unsigned __int64
0x18002193a  call    ?HrJetDelete@@YAJ_K0@Z; HrJetDelete(unsigned __int64,unsigned __int64)
0x18002193f  mov     ebx, eax
0x180021941  test    eax, eax
0x180021943  jns     loc_180021AA3
0x180021949  mov     sil, [rbp+57h+arg_0]
0x18002194d  mov     rdx, [rbp+57h+arg_18]; unsigned __int64
0x180021951  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180021955  jz      short loc_18002196B
0x180021957  mov     rcx, rdi; unsigned __int64
0x18002195a  call    ?HrJetCloseTable@@YAJ_K0@Z; HrJetCloseTable(unsigned __int64,unsigned __int64)
0x18002195f  test    eax, eax
0x180021961  js      short loc_18002196B
0x180021963  mov     [rbp+57h+arg_18], 0FFFFFFFFFFFFFFFFh
0x18002196b  test    sil, sil
0x18002196e  jnz     loc_180021C6F
0x180021974  test    ebx, ebx
0x180021976  js      loc_180021895
0x18002197c  test    r15, r15
0x18002197f  jz      loc_1800218D0
0x180021985  mov     rdx, r15; struct __MIDL_RPCIndexedDB_0001 *
0x180021988  mov     rcx, r13; struct __MIDL_RPCIndexedDB_0001 *
0x18002198b  call    ?IDBKeyCopy@@YAXQEBU__MIDL_RPCIndexedDB_0001@@PEAU1@@Z; IDBKeyCopy(__MIDL_RPCIndexedDB_0001 const * const,__MIDL_RPCIndexedDB_0001 *)
0x180021990  jmp     loc_1800218D0
0x180021995  mov     sil, 1
0x180021998  mov     r8, [rbp+57h+var_B0]
0x18002199c  add     r8, 38h ; '8'; unsigned __int16 *
0x1800219a0  lea     rax, [rbp+57h+arg_18]
0x1800219a4  mov     [rsp+100h+var_D0], rax; JET_TABLEID *
0x1800219a9  mov     [rsp+100h+var_D8], 0; JET_GRBIT
0x1800219b1  mov     edx, r12d; unsigned int
0x1800219b4  mov     rcx, rdi; unsigned __int64
0x1800219b7  call    ?HrJetOpenTable@@YAJ_KKPEBGPEBXKKPEA_K@Z; HrJetOpenTable(unsigned __int64,ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x1800219bc  mov     ebx, eax
0x1800219be  test    eax, eax
0x1800219c0  js      loc_180021878
0x1800219c6  mov     [rbp+57h+arg_0], sil
0x1800219ca  mov     rax, [rbp+57h+var_B0]
0x1800219ce  mov     rsi, [rax+18h]
0x1800219d2  mov     r12, [rbp+57h+arg_18]
0x1800219d6  mov     [rbp+57h+var_90], r12
0x1800219da  xor     ecx, ecx
0x1800219dc  cmp     [r13+0], ecx
0x1800219e0  jz      loc_180021B94
0x1800219e6  lea     r8, [rsi+2C8h]; unsigned __int16 *
0x1800219ed  mov     rdx, r12; unsigned __int64
0x1800219f0  mov     rcx, rdi; unsigned __int64
0x1800219f3  call    ?HrJetSetCurrentIndex@@YAJ_K0PEBG@Z; HrJetSetCurrentIndex(unsigned __int64,unsigned __int64,ushort const *)
0x1800219f8  mov     ebx, eax
0x1800219fa  test    eax, eax
0x1800219fc  js      loc_180021A93
0x180021a02  mov     esi, [r13+0]
0x180021a06  lea     rcx, [r13+8]
0x180021a0a  cmp     esi, 4
0x180021a0d  jnz     short loc_180021A33
0x180021a0f  mov     r8, [r13+10h]
0x180021a13  test    rcx, rcx
0x180021a16  jz      loc_180021B0B
0x180021a1c  mov     r9d, [rcx]
0x180021a1f  add     r9d, r9d
0x180021a22  mov     [rbp+57h+ppstm], 0
0x180021a2a  xor     r12b, r12b
0x180021a2d  movsd   xmm0, qword ptr [rcx]
0x180021a31  jmp     short loc_180021A5D
0x180021a33  mov     rdx, rcx
0x180021a36  xor     eax, eax
0x180021a38  cmp     esi, 3
0x180021a3b  cmovnz  rdx, rax
0x180021a3f  mov     [rbp+57h+ppstm], rdx
0x180021a43  cmp     esi, 1
0x180021a46  jnz     loc_180021AE4
0x180021a4c  movd    xmm0, dword ptr [rcx]
0x180021a50  cvtdq2pd xmm0, xmm0
0x180021a54  xor     r9d, r9d; unsigned int
0x180021a57  xor     r8d, r8d; void *
0x180021a5a  mov     r12b, 1
0x180021a5d  movsd   [rbp+57h+var_88], xmm0
0x180021a62  mov     al, r12b
0x180021a65  neg     al
0x180021a67  sbb     rax, rax
0x180021a6a  lea     rcx, [rbp+57h+var_88]
0x180021a6e  and     rax, rcx
0x180021a71  mov     [rbp+57h+var_80], rax
0x180021a75  mov     [rsp+100h+var_E0], 1; JET_GRBIT
0x180021a7d  mov     rdx, [rbp+57h+var_90]; unsigned __int64
0x180021a81  mov     rcx, rdi; unsigned __int64
0x180021a84  call    ?HrJetMakeKey@@YAJ_K0PEBXKK@Z; HrJetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x180021a89  mov     ebx, eax
0x180021a8b  test    eax, eax
0x180021a8d  jns     loc_180021B13
0x180021a93  cmp     ebx, 8E5EF9BFh
0x180021a99  jnz     loc_180021C42
0x180021a9f  mov     rsi, [rbp+57h+var_B8]
0x180021aa3  mov     qword ptr [rsp+100h+var_E0], rsi; __int64 *
0x180021aa8  xor     r9d, r9d; struct __MIDL_RPCIndexedDB_0001 *
0x180021aab  mov     r8, [rbp+57h+arg_8]; struct __MIDL_RPCIndexedDB_0004 *
0x180021aaf  mov     rdx, r13; struct __MIDL_RPCIndexedDB_0001 *
0x180021ab2  mov     rcx, [rbp+57h+var_B0]; this
0x180021ab6  call    ?InsertObject@CEseLayerObjectStore@@QEAAJPEBU__MIDL_RPCIndexedDB_0001@@PEBU__MIDL_RPCIndexedDB_0004@@PEAU2@PEA_J@Z; CEseLayerObjectStore::InsertObject(__MIDL_RPCIndexedDB_0001 const *,__MIDL_RPCIndexedDB_0004 const *,__MIDL_RPCIndexedDB_0001 *,__int64 *)
0x180021abb  mov     ebx, eax
0x180021abd  test    eax, eax
0x180021abf  js      loc_180021949
0x180021ac5  mov     edx, 1; unsigned int
0x180021aca  mov     rcx, rdi; unsigned __int64
0x180021acd  call    ?HrJetCommitTransaction@@YAJ_KK@Z; HrJetCommitTransaction(unsigned __int64,ulong)
0x180021ad2  mov     ebx, eax
0x180021ad4  test    eax, eax
0x180021ad6  js      loc_180021949
0x180021adc  xor     sil, sil
0x180021adf  jmp     loc_18002194D
0x180021ae4  cmp     esi, 2
0x180021ae7  jz      short loc_180021AF4
0x180021ae9  xor     r9d, r9d
0x180021aec  xor     r8d, r8d
0x180021aef  jmp     loc_180021A2A
0x180021af4  cmp     esi, 1
0x180021af7  jz      loc_180021A4C
0x180021afd  xor     r8d, r8d
0x180021b00  mov     r12b, 1
0x180021b03  xor     r9d, r9d
0x180021b06  jmp     loc_180021A2D
0x180021b0b  xor     r9d, r9d
0x180021b0e  jmp     loc_180021A22
0x180021b13  xor     eax, eax
0x180021b15  lea     r9d, [rax+8]
0x180021b19  cmp     esi, 3
0x180021b1c  cmovnz  r9d, eax; unsigned int
0x180021b20  mov     [rsp+100h+var_E0], eax; JET_GRBIT
0x180021b24  mov     r8, [rbp+57h+ppstm]; void *
0x180021b28  mov     rsi, [rbp+57h+var_90]
0x180021b2c  mov     rdx, rsi; unsigned __int64
0x180021b2f  mov     rcx, rdi; unsigned __int64
0x180021b32  call    ?HrJetMakeKey@@YAJ_K0PEBXKK@Z; HrJetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x180021b37  mov     ebx, eax
0x180021b39  test    eax, eax
0x180021b3b  js      loc_180021A93
0x180021b41  movzx   r9d, r12b
0x180021b45  shl     r9d, 3; unsigned int
0x180021b49  mov     [rsp+100h+var_E0], 0; JET_GRBIT
0x180021b51  mov     r8, [rbp+57h+var_80]; void *
0x180021b55  mov     rdx, rsi; unsigned __int64
0x180021b58  mov     rcx, rdi; unsigned __int64
0x180021b5b  call    ?HrJetMakeKey@@YAJ_K0PEBXKK@Z; HrJetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x180021b60  mov     ebx, eax
0x180021b62  test    eax, eax
0x180021b64  js      loc_180021A93
0x180021b6a  mov     r8d, 1; unsigned int
0x180021b70  mov     rdx, rsi; unsigned __int64
0x180021b73  mov     rcx, rdi; unsigned __int64
0x180021b76  call    ?HrJetSeek@@YAJ_K0K@Z; HrJetSeek(unsigned __int64,unsigned __int64,ulong)
0x180021b7b  mov     ebx, eax
0x180021b7d  jmp     loc_180021A93
  ... truncated ...
```
