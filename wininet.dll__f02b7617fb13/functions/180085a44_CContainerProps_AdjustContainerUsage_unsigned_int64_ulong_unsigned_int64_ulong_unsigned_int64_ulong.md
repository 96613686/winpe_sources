# CContainerProps::AdjustContainerUsage(unsigned __int64 *,ulong,unsigned __int64,ulong,unsigned __int64,ulong)

- ea: `0x180085a44`
- end: `0x1800861f1`
- name: `?AdjustContainerUsage@CContainerProps@@QEAAJPEA_KK_KK1K@Z`
- size: `1965`
- prototype: `__int64 __usercall@<rax>(CContainerProps *__hidden this@<rcx>, unsigned __int64 *@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, unsigned int, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007c810`
- `0x1800b5bdc`

## callees

- `0x18003fc40`
- `0x18007ec9c`
- `0x180083dc4`
- `0x180085898`
- `0x180085a44`
- `0x180086aa4`
- `0x1800eee94`
- `0x180114fb0`
- `0x18014a7a0`
- `0x1801ac41c`
- `0x1801e1790`
- `0x1801e1b60`
- `0x1801e2f9c`
- `0x1801e3048`
- `0x1801e544c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085e0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085e67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085eea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085f6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085e0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085e67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085eea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085f6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085afa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085ea9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085f2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085afa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085ea9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085f2d`
- `ESENT!JetSetCurrentIndex2W` at `0x18008607c`
- `ESENT!JetSetCurrentIndex2W` at `0x18008607c`
- `ESENT!JetMakeKey` at `0x180085c13`
- `ESENT!JetMakeKey` at `0x180085c13`
- `ESENT!JetSetColumn` at `0x180085d0e`
- `ESENT!JetSetColumn` at `0x180085fee`
- `ESENT!JetSetColumn` at `0x180085d0e`
- `ESENT!JetSetColumn` at `0x180085fee`
- `ESENT!JetCommitTransaction` at `0x180085d6f`
- `ESENT!JetCommitTransaction` at `0x180085d6f`
- `ESENT!JetUpdate` at `0x180085d4a`
- `ESENT!JetUpdate` at `0x180085d4a`
- `ESENT!JetPrepareUpdate` at `0x180085c98`
- `ESENT!JetPrepareUpdate` at `0x180086041`
- `ESENT!JetPrepareUpdate` at `0x180085c98`
- `ESENT!JetPrepareUpdate` at `0x180086041`
- `ESENT!JetRollback` at `0x18008604d`
- `ESENT!JetRollback` at `0x18008604d`
- `ESENT!JetBeginTransaction` at `0x180085baa`
- `ESENT!JetBeginTransaction` at `0x180085baa`
- `ESENT!JetSeek` at `0x180085c34`
- `ESENT!JetSeek` at `0x180085c34`

## pseudocode

```c
__int64 __fastcall CContainerProps::AdjustContainerUsage(
        CContainerProps *this,
        unsigned __int64 *a2,
        unsigned int a3,
        unsigned __int64 a4,
        unsigned int a5,
        unsigned __int64 a6,
        unsigned int a7)
{
  struct CJetContext *v7; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // r15
  unsigned __int64 v9; // rsi
  unsigned int v12; // ebx
  unsigned __int64 v13; // r8
  __int64 v14; // rcx
  int v15; // eax
  int v16; // edx
  int v17; // ecx
  int v18; // r8d
  JET_ERR updated; // ebx
  JET_TABLEID *v20; // r14
  JET_SESID *v21; // r15
  JET_ERR v22; // eax
  struct CJetContext *v23; // rax
  JET_ERR Key; // eax
  JET_ERR v25; // eax
  JET_ERR v26; // eax
  int v27; // r8d
  __int64 v28; // rax
  JET_ERR v29; // eax
  JET_ERR v30; // eax
  __int64 v31; // rsi
  CJetContext *v32; // r15
  bool v33; // zf
  struct _RTL_CRITICAL_SECTION *v34; // r12
  __int64 v35; // rsi
  int v37; // r15d
  int v38; // r12d
  _DWORD *v39; // rdx
  JET_TABLEID v40; // r14
  JET_SESID v41; // r15
  unsigned __int64 v42; // r12
  __int64 v43; // rcx
  unsigned int v44; // ebx
  JET_COLUMNID v45; // esi
  JET_ERR v46; // eax
  unsigned int v47; // eax
  JET_TABLEID v48; // rdx
  JET_SESID v49; // rcx
  JET_ERR v50; // eax
  unsigned __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 i; // rsi
  unsigned __int64 v54; // rdx
  int v55; // [rsp+58h] [rbp-29h]
  unsigned __int64 *v56; // [rsp+60h] [rbp-21h]
  struct CJetContext *pvData; // [rsp+70h] [rbp-11h] BYREF
  unsigned __int64 v59; // [rsp+78h] [rbp-9h] BYREF

  v7 = 0;
  pvData = 0;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v59 = 0;
  v9 = a4;
  v56 = a2;
  v55 = 0;
  v12 = a5;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    WPP_SF_qdidid((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a2, a3, a4, a5, a6, a7);
    a2 = v56;
  }
  v13 = a6;
  if ( v9 == a6 )
  {
    if ( a5 == a7 )
    {
      updated = 0;
      goto LABEL_77;
    }
    goto LABEL_59;
  }
  if ( a2 )
  {
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      v54 = a2[i];
      if ( (v54 & 0xFFFFFFFFFFFFFFFLL) != 0 && (v54 & 0xE000000000000000uLL) == 0 )
      {
        updated = CContainerProps::AdjustGroupSize(this, v54, a4, v13, 0, 0);
        if ( updated < 0 )
          goto LABEL_77;
        v13 = a6;
      }
      a2 = v56;
    }
    v12 = a5;
    v9 = a4;
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  }
  if ( v12 != a7 )
  {
LABEL_59:
    updated = CContainerProps::UpdateCounts(this, v12, a7);
    if ( updated < 0 )
      goto LABEL_77;
  }
  if ( v8 )
  {
    EnterCriticalSection(v8);
    v55 = 1;
  }
  v14 = *((_QWORD *)this + 3);
  v59 = *((_QWORD *)this + 9);
  v15 = CJetContextList::AcquireContext(*(CJetContextList **)(v14 + 320), &pvData, 0);
  v7 = pvData;
  updated = v15;
  if ( v15 < 0 )
    goto LABEL_77;
  HIDWORD(pvData) = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qdSD(v17, v16, v18, (_DWORD)v7, 0, (__int64)L"ContainerIdIndex", 0);
  v20 = (JET_TABLEID *)((char *)v7 + 32);
  v21 = (JET_SESID *)((char *)v7 + 16);
  if ( *((_DWORD *)v7 + 12) )
  {
    v48 = *v20;
    v49 = *v21;
    *((_DWORD *)v7 + 12) = -1;
    v50 = JetSetCurrentIndex2W(v49, v48, L"ContainerIdIndex", 0);
    updated = HRESULTFromJET_ERR(v50, 1);
    if ( updated >= 0 )
      *((_DWORD *)v7 + 12) = 0;
  }
  else
  {
    updated = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 14, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)updated);
  if ( updated < 0 )
    goto LABEL_77;
  v22 = JetBeginTransaction(*((_QWORD *)v7 + 2));
  updated = HRESULTFromJET_ERR(v22, 1);
  if ( updated < 0 )
    goto LABEL_77;
  v23 = (struct CJetContext *)*((_QWORD *)this + 1);
  pvData = v23;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qP(1036, 28, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, v7, v23);
  Key = JetMakeKey(*v21, *v20, &pvData, 8u, 1u);
  updated = HRESULTFromJET_ERR(Key, 1);
  if ( updated >= 0 )
  {
    v25 = JetSeek(*v21, *v20, 0x21u);
    if ( v25 == -1601 )
    {
      updated = 1;
    }
    else
    {
      updated = HRESULTFromJET_ERR(v25, 1);
      if ( updated >= 0 )
        updated = 0;
    }
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 29, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)updated);
  if ( updated < 0 )
    goto LABEL_74;
  if ( updated )
  {
    updated = -2147418113;
    goto LABEL_74;
  }
  v26 = JetPrepareUpdate(*((_QWORD *)v7 + 2), *((_QWORD *)v7 + 4), 2u);
  updated = HRESULTFromJET_ERR(v26, 1);
  if ( updated < 0 )
    goto LABEL_74;
  if ( a6 != v9 )
  {
    if ( a6 < v9 )
    {
      v51 = v9 - a6;
      if ( v59 < v9 - a6 )
        v52 = -1;
      else
        v52 = v59 - v51;
      v28 = 0;
      if ( v59 >= v51 )
        v28 = v52;
    }
    else
    {
      v28 = -1;
      if ( a6 + v59 - v9 >= v59 )
        v28 = a6 + v59 - v9;
    }
    v59 = v28;
    updated = JetSetColumn(*v21, *v20, *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 5) + 8LL) + 20LL), &v59, 8u, 0, 0);
    if ( updated < 0 )
      goto LABEL_73;
    if ( v56 )
    {
      updated = CJetContext::SetBinaryColumn(
                  v7,
                  0xAu,
                  *((const unsigned __int8 **)this + 21),
                  288 * *((_DWORD *)this + 44));
      if ( updated < 0 )
        goto LABEL_73;
    }
  }
  if ( a5 != a7 )
  {
    v39 = (_DWORD *)*((_QWORD *)this + 20);
    v40 = *v20;
    v41 = *v21;
    v42 = (unsigned __int64)(v39 + 129);
    v43 = *(_QWORD *)(*((_QWORD *)v7 + 5) + 8LL);
    v44 = 4 * *v39;
    v45 = *(_DWORD *)(v43 + 36);
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_iiiqd(v43, (_DWORD)v39, v27, v41, v40, v45, (__int64)(v39 + 129));
    v46 = JetSetColumn(v41, v40, v45, (const void *)(v42 & -(__int64)(v44 != 0)), v44, 0, 0);
    v47 = HRESULTFromJET_ERR(v46, 1);
    updated = v47;
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_d(1036, 21, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v47);
    if ( updated < 0 )
      goto LABEL_73;
  }
  v29 = JetUpdate(*((_QWORD *)v7 + 2), *((_QWORD *)v7 + 4), 0, 0, 0);
  updated = HRESULTFromJET_ERR(v29, 1);
  if ( updated < 0 )
  {
LABEL_73:
    JetPrepareUpdate(*((_QWORD *)v7 + 2), *((_QWORD *)v7 + 4), 3u);
    goto LABEL_74;
  }
  v30 = JetCommitTransaction(*((_QWORD *)v7 + 2), 1u);
  updated = HRESULTFromJET_ERR(v30, 1);
  if ( updated < 0 )
  {
LABEL_74:
    JetRollback(*((_QWORD *)v7 + 2), 0);
LABEL_77:
    v34 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
    goto LABEL_44;
  }
  v31 = *(_QWORD *)(*((_QWORD *)this + 3) + 320LL);
  CCacheStore::EndActivity(*(CCacheStore **)(v31 + 80));
  v32 = v7;
  if ( v7 )
  {
    v7 = 0;
    v38 = 0;
    *((_QWORD *)v32 + 1) = 0;
    if ( v31 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v31 + 8));
      v38 = 1;
    }
    --*(_DWORD *)(v31 + 60);
    if ( (unsigned int)(*(_DWORD *)(v31 + 56) - *(_DWORD *)(v31 + 60)) > *(_DWORD *)(v31 + 64) )
    {
      --*(_DWORD *)(v31 + 56);
      CJetContext::Release(v32);
    }
    else
    {
      *((_QWORD *)v32 + 1) = *(_QWORD *)(v31 + 48);
      *(_QWORD *)(v31 + 48) = v32;
    }
    if ( v38 && v31 != -8 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v31 + 8));
  }
  v33 = (*((_BYTE *)this + 92) & 8) == 0;
  *((_QWORD *)this + 9) = v59;
  if ( !v33 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&CCacheStore::g_ulCacheWriteCountSinceLastCleanup);
    if ( a6 > a4 )
      CWxWorker::Queue(
        *(CWxWorker **)(*((_QWORD *)this + 3) + 240LL),
        (int (*)(struct CWxWorker *, struct CWxWorkContext *, unsigned __int64, void *))CCacheStore::CleanupCallback,
        0,
        0,
        *(_DWORD *)(*((_QWORD *)this + 3) + 344LL),
        0xA4CB800u);
  }
  v34 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  if ( this != (CContainerProps *)-32LL && v55 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    v55 = 0;
  }
LABEL_44:
  v35 = *(_QWORD *)(*((_QWORD *)this + 3) + 320LL);
  if ( v7 )
  {
    CCacheStore::EndActivity(*(CCacheStore **)(v35 + 80));
    v37 = 0;
    *((_QWORD *)v7 + 1) = 0;
    if ( v35 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v35 + 8));
      v37 = 1;
    }
    --*(_DWORD *)(v35 + 60);
    if ( (unsigned int)(*(_DWORD *)(v35 + 56) - *(_DWORD *)(v35 + 60)) > *(_DWORD *)(v35 + 64) )
    {
      --*(_DWORD *)(v35 + 56);
      CJetContext::Release(v7);
    }
    else
    {
      *((_QWORD *)v7 + 1) = *(_QWORD *)(v35 + 48);
      *(_QWORD *)(v35 + 48) = v7;
    }
    if ( v37 && v35 != -8 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v35 + 8));
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 32, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, (unsigned int)updated);
  if ( v55 && v34 )
    LeaveCriticalSection(v34);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180085a44  mov     [rsp-8+arg_10], rbx
0x180085a49  push    rbp
0x180085a4a  push    rsi
0x180085a4b  push    rdi
0x180085a4c  push    r12
0x180085a4e  push    r13
0x180085a50  push    r14
0x180085a52  push    r15
0x180085a54  lea     rbp, [rsp-0Fh]
0x180085a59  sub     rsp, 90h
0x180085a60  mov     rax, cs:__security_cookie
0x180085a67  xor     rax, rsp
0x180085a6a  mov     [rbp+3Fh+var_40], rax
0x180085a6e  xor     edi, edi
0x180085a70  mov     [rbp+3Fh+var_58], r9
0x180085a74  mov     [rbp+3Fh+pvData], rdi
0x180085a78  lea     r15, [rcx+20h]
0x180085a7c  mov     [rbp+3Fh+var_48], rdi
0x180085a80  mov     rsi, r9
0x180085a83  mov     r14d, r8d
0x180085a86  mov     [rbp+3Fh+var_60], rdx
0x180085a8a  mov     r13, rcx
0x180085a8d  mov     [rbp+3Fh+var_6C], 0
0x180085a94  mov     [rbp+3Fh+var_68], 0
0x180085a9b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180085aa2  mov     r12d, [rbp+3Fh+arg_30]
0x180085aa6  mov     ebx, [rbp+3Fh+arg_20]
0x180085aa9  jz      short loc_180085AD3
0x180085aab  mov     rax, [rbp+3Fh+arg_28]
0x180085aaf  mov     [rsp+0C0h+var_80], r12d
0x180085ab4  mov     [rsp+0C0h+var_88], rax
0x180085ab9  mov     dword ptr [rsp+0C0h+psetinfo], ebx
0x180085abd  mov     qword ptr [rsp+0C0h+var_98], r9
0x180085ac2  mov     r9, rdx
0x180085ac5  mov     [rsp+0C0h+grbit], r8d
0x180085aca  call    WPP_SF_qdidid
0x180085acf  mov     rdx, [rbp+3Fh+var_60]
0x180085ad3  mov     r8, [rbp+3Fh+arg_28]
0x180085ad7  cmp     rsi, r8
0x180085ada  jz      loc_180086055
0x180085ae0  test    rdx, rdx
0x180085ae3  jnz     loc_1800860C7
0x180085ae9  cmp     ebx, r12d
0x180085aec  jnz     loc_180085EF5
0x180085af2  test    r15, r15
0x180085af5  jz      short loc_180085B07
0x180085af7  mov     rcx, r15; lpCriticalSection
0x180085afa  call    cs:__imp_EnterCriticalSection
0x180085b00  mov     [rbp+3Fh+var_68], 1
0x180085b07  mov     rcx, [r13+18h]
0x180085b0b  lea     rdx, [rbp+3Fh+pvData]; struct CJetContext **
0x180085b0f  mov     rax, [r13+48h]
0x180085b13  xor     r8d, r8d; int *
0x180085b16  mov     [rbp+3Fh+var_48], rax
0x180085b1a  mov     rcx, [rcx+140h]; this
0x180085b21  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x180085b26  mov     rdi, [rbp+3Fh+pvData]
0x180085b2a  mov     ebx, eax
0x180085b2c  test    eax, eax
0x180085b2e  js      loc_18008613E
0x180085b34  mov     dword ptr [rbp+3Fh+pvData+4], 0
0x180085b3b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180085b42  lea     rbx, aContaineridind; "ContainerIdIndex"
0x180085b49  jz      short loc_180085B68
0x180085b4b  mov     dword ptr [rsp+0C0h+psetinfo], 0
0x180085b53  mov     r9, rdi
0x180085b56  mov     qword ptr [rsp+0C0h+var_98], rbx
0x180085b5b  mov     [rsp+0C0h+grbit], 0
0x180085b63  call    WPP_SF_qdSD
0x180085b68  cmp     dword ptr [rdi+30h], 0
0x180085b6c  lea     r14, [rdi+20h]
0x180085b70  lea     r15, [rdi+10h]
0x180085b74  jnz     loc_180086069
0x180085b7a  xor     ebx, ebx
0x180085b7c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180085b83  jz      short loc_180085B9E
0x180085b85  mov     edx, 0Eh
0x180085b8a  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x180085b91  mov     ecx, 40Ch
0x180085b96  mov     r9d, ebx
0x180085b99  call    WPP_SF_d
0x180085b9e  test    ebx, ebx
0x180085ba0  js      loc_18008614A
0x180085ba6  mov     rcx, [rdi+10h]; sesid
0x180085baa  call    cs:__imp_JetBeginTransaction
0x180085bb0  mov     ecx, eax; int
0x180085bb2  mov     edx, 1; int
0x180085bb7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180085bbc  mov     ebx, eax
0x180085bbe  test    eax, eax
0x180085bc0  js      loc_180086060
0x180085bc6  mov     rax, [r13+8]
0x180085bca  mov     [rbp+3Fh+pvData], rax
0x180085bce  mov     [rbp+3Fh+var_6C], 0
0x180085bd5  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180085bdc  jz      short loc_180085BFC
0x180085bde  mov     edx, 1Ch
0x180085be3  mov     qword ptr [rsp+0C0h+grbit], rax
0x180085be8  mov     ecx, 40Ch
0x180085bed  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x180085bf4  mov     r9, rdi
0x180085bf7  call    WPP_SF_qP
0x180085bfc  mov     rdx, [r14]; tableid
0x180085bff  lea     r8, [rbp+3Fh+pvData]; pvData
0x180085c03  mov     rcx, [r15]; sesid
0x180085c06  mov     ebx, 1
0x180085c0b  mov     [rsp+0C0h+grbit], ebx; grbit
0x180085c0f  lea     r9d, [rbx+7]; cbData
0x180085c13  call    cs:__imp_JetMakeKey
0x180085c19  mov     ecx, eax; int
0x180085c1b  mov     edx, ebx; int
0x180085c1d  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180085c22  mov     ebx, eax
0x180085c24  test    eax, eax
0x180085c26  js      short loc_180085C5A
0x180085c28  mov     rdx, [r14]; tableid
0x180085c2b  mov     r8d, 21h ; '!'; grbit
0x180085c31  mov     rcx, [r15]; sesid
0x180085c34  call    cs:__imp_JetSeek
0x180085c3a  cmp     eax, 0FFFFF9BFh
0x180085c3f  jz      loc_180086156
0x180085c45  mov     edx, 1; int
0x180085c4a  mov     ecx, eax; int
0x180085c4c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180085c51  mov     ebx, eax
0x180085c53  xor     eax, eax
0x180085c55  test    ebx, ebx
0x180085c57  cmovns  ebx, eax
0x180085c5a  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180085c61  jz      short loc_180085C7C
0x180085c63  mov     edx, 1Dh
0x180085c68  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x180085c6f  mov     ecx, 40Ch
0x180085c74  mov     r9d, ebx
0x180085c77  call    WPP_SF_d
0x180085c7c  test    ebx, ebx
0x180085c7e  js      loc_180086160
0x180085c84  jnz     loc_18008616C
0x180085c8a  mov     rdx, [rdi+20h]; tableid
0x180085c8e  mov     r8d, 2; prep
0x180085c94  mov     rcx, [rdi+10h]; sesid
0x180085c98  call    cs:__imp_JetPrepareUpdate
0x180085c9e  mov     ecx, eax; int
0x180085ca0  mov     edx, 1; int
0x180085ca5  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180085caa  mov     ebx, eax
0x180085cac  test    eax, eax
0x180085cae  js      loc_180086047
0x180085cb4  mov     r9, [rbp+3Fh+arg_28]
0x180085cb8  cmp     r9, rsi
0x180085cbb  jz      short loc_180085D29
0x180085cbd  mov     rdx, [rbp+3Fh+var_48]
0x180085cc1  jb      loc_1800860A4
0x180085cc7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180085ccb  mov     rcx, rdx
0x180085cce  sub     rcx, rsi
0x180085cd1  add     rcx, r9
0x180085cd4  cmp     rcx, rdx
0x180085cd7  cmovnb  rax, rcx
0x180085cdb  mov     [rbp+3Fh+var_48], rax
0x180085cdf  lea     r9, [rbp+3Fh+var_48]; pvData
0x180085ce3  mov     rax, [rdi+28h]
0x180085ce7  mov     rdx, [r14]; tableid
0x180085cea  mov     rcx, [r15]; sesid
0x180085ced  mov     [rsp+0C0h+psetinfo], 0; psetinfo
0x180085cf6  mov     r8, [rax+8]
0x180085cfa  mov     [rsp+0C0h+var_98], 0; grbit
0x180085d02  mov     [rsp+0C0h+grbit], 8; cbData
0x180085d0a  mov     r8d, [r8+14h]; columnid
0x180085d0e  call    cs:__imp_JetSetColumn
0x180085d14  mov     ebx, eax
0x180085d16  test    eax, eax
0x180085d18  js      loc_180086186
0x180085d1e  cmp     [rbp+3Fh+var_60], 0
0x180085d23  jnz     loc_180086192
0x180085d29  cmp     [rbp+3Fh+arg_20], r12d
0x180085d2d  jnz     loc_180085F77
0x180085d33  mov     rdx, [rdi+20h]; tableid
0x180085d37  xor     r9d, r9d; cbBookmark
0x180085d3a  mov     rcx, [rdi+10h]; sesid
0x180085d3e  xor     r8d, r8d; pvBookmark
0x180085d41  mov     qword ptr [rsp+0C0h+grbit], 0; pcbActual
0x180085d4a  call    cs:__imp_JetUpdate
0x180085d50  mov     ecx, eax; int
0x180085d52  mov     edx, 1; int
0x180085d57  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180085d5c  mov     ebx, eax
0x180085d5e  test    eax, eax
0x180085d60  js      loc_180086033
0x180085d66  mov     rcx, [rdi+10h]; sesid
0x180085d6a  mov     edx, 1; grbit
0x180085d6f  call    cs:__imp_JetCommitTransaction
0x180085d75  mov     ecx, eax; int
0x180085d77  mov     edx, 1; int
0x180085d7c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180085d81  mov     ebx, eax
0x180085d83  test    eax, eax
0x180085d85  js      loc_180086047
0x180085d8b  mov     rax, [r13+18h]
0x180085d8f  mov     rsi, [rax+140h]
0x180085d96  mov     rcx, [rsi+50h]; this
0x180085d9a  call    ?EndActivity@CCacheStore@@QEAAXXZ; CCacheStore::EndActivity(void)
0x180085d9f  mov     r15, rdi
0x180085da2  test    rdi, rdi
0x180085da5  jnz     loc_180085F18
0x180085dab  test    byte ptr [r13+5Ch], 8
0x180085db0  mov     rax, [rbp+3Fh+var_48]
0x180085db4  mov     [r13+48h], rax
0x180085db8  jz      short loc_180085DFA
0x180085dba  lock inc cs:?g_ulCacheWriteCountSinceLastCleanup@CCacheStore@@0KC; ulong volatile CCacheStore::g_ulCacheWriteCountSinceLastCleanup
0x180085dc1  mov     r15, [rbp+3Fh+var_58]
0x180085dc5  cmp     [rbp+3Fh+arg_28], r15
0x180085dc9  jbe     short loc_180085DFA
0x180085dcb  mov     rcx, [r13+18h]
0x180085dcf  lea     rdx, ?CleanupCallback@CCacheStore@@CAJPEAVCWxWorker@@PEAVCWxWorkContext@@_KPEAX@Z; int (*)(struct CWxWorker *, struct CWxWorkContext *, unsigned __int64, void *)
0x180085dd6  mov     [rsp+0C0h+var_98], 0A4CB800h; unsigned int
0x180085dde  xor     r9d, r9d; unsigned __int64
0x180085de1  xor     r8d, r8d; struct CWxWorkContext *
0x180085de4  mov     eax, [rcx+158h]
0x180085dea  mov     rcx, [rcx+0F0h]; this
0x180085df1  mov     [rsp+0C0h+grbit], eax; unsigned int
0x180085df5  call    ?Queue@CWxWorker@@QEAAJP6AJPEAV1@PEAVCWxWorkContext@@_KPEAX@Z12KK@Z; CWxWorker::Queue(long (*)(CWxWorker *,CWxWorkContext *,unsigned __int64,void *),CWxWorkContext *,unsigned __int64,ulong,ulong)
0x180085dfa  lea     r12, [r13+20h]
0x180085dfe  test    r12, r12
0x180085e01  jz      short loc_180085E19
0x180085e03  cmp     [rbp+3Fh+var_68], 0
0x180085e07  jz      short loc_180085E19
0x180085e09  mov     rcx, r12; lpCriticalSection
0x180085e0c  call    cs:__imp_LeaveCriticalSection
0x180085e12  mov     [rbp+3Fh+var_68], 0
0x180085e19  mov     rax, [r13+18h]
0x180085e1d  mov     rsi, [rax+140h]
0x180085e24  test    rdi, rdi
0x180085e27  jz      short loc_180085E37
0x180085e29  mov     rcx, [rsi+50h]; this
0x180085e2d  call    ?EndActivity@CCacheStore@@QEAAXXZ; CCacheStore::EndActivity(void)
0x180085e32  test    rdi, rdi
0x180085e35  jnz     short loc_180085E96
0x180085e37  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180085e3e  jz      short loc_180085E59
0x180085e40  mov     edx, 20h ; ' '
0x180085e45  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x180085e4c  mov     ecx, 40Ch
0x180085e51  mov     r9d, ebx
0x180085e54  call    WPP_SF_d
0x180085e59  cmp     [rbp+3Fh+var_68], 0
0x180085e5d  jz      short loc_180085E6D
0x180085e5f  test    r12, r12
0x180085e62  jz      short loc_180085E6D
0x180085e64  mov     rcx, r12; lpCriticalSection
0x180085e67  call    cs:__imp_LeaveCriticalSection
0x180085e6d  mov     eax, ebx
0x180085e6f  mov     rcx, [rbp+3Fh+var_40]
0x180085e73  xor     rcx, rsp; StackCookie
0x180085e76  call    __security_check_cookie
0x180085e7b  mov     rbx, [rsp+0C0h+arg_10]
0x180085e83  add     rsp, 90h
0x180085e8a  pop     r15
0x180085e8c  pop     r14
0x180085e8e  pop     r13
0x180085e90  pop     r12
0x180085e92  pop     rdi
0x180085e93  pop     rsi
0x180085e94  pop     rbp
0x180085e95  retn
0x180085e96  xor     r15d, r15d
0x180085e99  lea     r14, [rsi+8]
0x180085e9d  mov     [rdi+8], r15
0x180085ea1  test    r14, r14
0x180085ea4  jz      short loc_180085EB5
0x180085ea6  mov     rcx, r14; lpCriticalSection
0x180085ea9  call    cs:__imp_EnterCriticalSection
0x180085eaf  mov     r15d, 1
0x180085eb5  dec     dword ptr [rsi+3Ch]
0x180085eb8  mov     ecx, [rsi+38h]
0x180085ebb  mov     eax, ecx
0x180085ebd  sub     eax, [rsi+3Ch]
0x180085ec0  cmp     eax, [rsi+40h]
0x180085ec3  ja      loc_1800861DE
0x180085ec9  mov     rax, [rsi+30h]
0x180085ecd  mov     [rdi+8], rax
0x180085ed1  mov     [rsi+30h], rdi
0x180085ed5  test    r15d, r15d
0x180085ed8  jz      loc_180085E37
0x180085ede  test    r14, r14
0x180085ee1  jz      loc_180085E37
0x180085ee7  mov     rcx, r14; lpCriticalSection
0x180085eea  call    cs:__imp_LeaveCriticalSection
0x180085ef0  jmp     loc_180085E37
0x180085ef5  mov     r8d, r12d; unsigned int
0x180085ef8  mov     edx, ebx; unsigned int
0x180085efa  mov     rcx, r13; this
0x180085efd  call    ?UpdateCounts@CContainerProps@@AEAAJKK@Z; CContainerProps::UpdateCounts(ulong,ulong)
0x180085f02  mov     ebx, eax
0x180085f04  test    eax, eax
0x180085f06  jns     loc_180085AF2
0x180085f0c  mov     [rbp+3Fh+var_6C], 43Eh
0x180085f13  jmp     loc_180086060
0x180085f18  xor     edi, edi
0x180085f1a  lea     r14, [rsi+8]
  ... truncated ...
```
