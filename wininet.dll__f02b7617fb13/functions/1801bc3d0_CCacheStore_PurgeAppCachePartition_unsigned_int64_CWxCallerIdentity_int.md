# CCacheStore::PurgeAppCachePartition(unsigned __int64,CWxCallerIdentity *,int)

- ea: `0x1801bc3d0`
- end: `0x1801bc679`
- name: `?PurgeAppCachePartition@CCacheStore@@QEAAJ_KPEAVCWxCallerIdentity@@H@Z`
- size: `681`
- prototype: `__int64 __fastcall(CCacheStore *__hidden this, unsigned __int64, struct CWxCallerIdentity *, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800259c0`
- `0x1800adc3c`

## callees

- `0x18001eaec`
- `0x18001f3a4`
- `0x180021360`
- `0x180025910`
- `0x18007ec9c`
- `0x18007ee10`
- `0x1800861f8`
- `0x180097e10`
- `0x1800e28e0`
- `0x180125918`
- `0x18012be98`
- `0x1801ba330`
- `0x1801bc3d0`
- `0x1801de6f8`
- `0x1801e1790`

## import_xrefs

- `ESENT!JetDeleteTableW` at `0x1801bc5b1`
- `ESENT!JetDeleteTableW` at `0x1801bc60b`
- `ESENT!JetDeleteTableW` at `0x1801bc5b1`
- `ESENT!JetDeleteTableW` at `0x1801bc60b`
- `ESENT!JetDelete` at `0x1801bc632`
- `ESENT!JetDelete` at `0x1801bc632`
- `ESENT!JetCommitTransaction` at `0x1801bc64d`
- `ESENT!JetCommitTransaction` at `0x1801bc64d`
- `ESENT!JetRollback` at `0x1801bc66e`
- `ESENT!JetRollback` at `0x1801bc66e`
- `ESENT!JetBeginTransaction` at `0x1801bc53d`
- `ESENT!JetBeginTransaction` at `0x1801bc53d`

## string_xrefs

- `0x1801bc584`: `AppCacheEx_%I64u`
- `0x1801bc5e5`: `AppCacheEntryEx_%I64u`

## pseudocode

```c
__int64 __fastcall CCacheStore::PurgeAppCachePartition(
        CCacheStore *this,
        __int64 a2,
        struct CWxCallerIdentity *a3,
        int a4)
{
  int IsAppCacheContainerInUse; // eax
  unsigned int v9; // ebx
  unsigned int v10; // edi
  unsigned int v12; // r9d
  struct CJetContext *v13; // rsi
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  JET_ERR v18; // eax
  struct CJetContext *v19; // [rsp+48h] [rbp-28h] BYREF
  JET_PCWSTR szTableName[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+60h] [rbp-10h] BYREF
  __int64 v22; // [rsp+68h] [rbp-8h]

  szTableName[0] = &Data;
  v19 = 0;
  szTableName[1] = 0;
  v22 = 0;
  v21 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qiql((_DWORD)this, a2, (_DWORD)a3, (_DWORD)this, a2, (__int64)a3);
  AutoCritSec::Attach((AutoCritSec *)&v21, (struct WxCriticalSection *)(*((_QWORD *)this + 56) + 24LL));
  AutoCritSec::Lock((AutoCritSec *)&v21);
  IsAppCacheContainerInUse = CAppCacheContainerMap::IsAppCacheContainerInUse(*((CAppCacheContainerMap **)this + 56), a3);
  v9 = IsAppCacheContainerInUse;
  if ( IsAppCacheContainerInUse < 0 )
    goto LABEL_4;
  if ( !IsAppCacheContainerInUse )
  {
    v10 = 1;
    v9 = 1;
    goto LABEL_5;
  }
  IsAppCacheContainerInUse = CCacheStore::AcquirePartitionContext(this, &v19);
  v9 = IsAppCacheContainerInUse;
  if ( IsAppCacheContainerInUse < 0 )
    goto LABEL_4;
  v13 = v19;
  IsAppCacheContainerInUse = CJetContext::SetCurrentIndex(v19, 1u, L"PartitionIndex", v12);
  v9 = IsAppCacheContainerInUse;
  if ( IsAppCacheContainerInUse < 0 )
    goto LABEL_4;
  v14 = JetBeginTransaction(*((_QWORD *)v13 + 2));
  IsAppCacheContainerInUse = HRESULTFromJET_ERR(v14, 1);
  v9 = IsAppCacheContainerInUse;
  if ( IsAppCacheContainerInUse < 0 )
    goto LABEL_4;
  IsAppCacheContainerInUse = CCacheStore::SeekToPartition(v13, a3, 0);
  v9 = IsAppCacheContainerInUse;
  if ( IsAppCacheContainerInUse < 0 )
  {
LABEL_27:
    v10 = IsAppCacheContainerInUse;
    goto LABEL_28;
  }
  if ( !IsAppCacheContainerInUse )
  {
    IsAppCacheContainerInUse = CWxString::Format((CWxString *)szTableName, L"AppCacheEx_%I64u", a2);
    v9 = IsAppCacheContainerInUse;
    if ( IsAppCacheContainerInUse < 0 )
      goto LABEL_27;
    v15 = JetDeleteTableW(*((_QWORD *)v13 + 2), *((_DWORD *)v13 + 6), szTableName[0]);
    if ( v15 != -1305 )
    {
      IsAppCacheContainerInUse = HRESULTFromJET_ERR(v15, 1);
      v9 = IsAppCacheContainerInUse;
      if ( IsAppCacheContainerInUse < 0 )
        goto LABEL_27;
    }
    CWxString::Empty((CWxString *)szTableName);
    IsAppCacheContainerInUse = CWxString::Format((CWxString *)szTableName, L"AppCacheEntryEx_%I64u", a2);
    v9 = IsAppCacheContainerInUse;
    if ( IsAppCacheContainerInUse < 0 )
      goto LABEL_27;
    v16 = JetDeleteTableW(*((_QWORD *)v13 + 2), *((_DWORD *)v13 + 6), szTableName[0]);
    if ( v16 != -1305 )
    {
      IsAppCacheContainerInUse = HRESULTFromJET_ERR(v16, 1);
      v9 = IsAppCacheContainerInUse;
      if ( IsAppCacheContainerInUse < 0 )
        goto LABEL_27;
    }
    if ( a4 )
    {
      v17 = JetDelete(*((_QWORD *)v13 + 2), *((_QWORD *)v13 + 4));
      IsAppCacheContainerInUse = HRESULTFromJET_ERR(v17, 1);
      v9 = IsAppCacheContainerInUse;
      if ( IsAppCacheContainerInUse < 0 )
        goto LABEL_27;
    }
    v18 = JetCommitTransaction(*((_QWORD *)v13 + 2), 1u);
    IsAppCacheContainerInUse = HRESULTFromJET_ERR(v18, 1);
    v9 = IsAppCacheContainerInUse;
    if ( IsAppCacheContainerInUse < 0 )
      goto LABEL_27;
LABEL_4:
    v10 = IsAppCacheContainerInUse;
    goto LABEL_5;
  }
  v9 = 0;
  v10 = 0;
LABEL_28:
  JetRollback(*((_QWORD *)v13 + 2), 0);
LABEL_5:
  CJetContextList::ReleaseContext(*((CJetContextList **)this + 55), &v19);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 21, WPP_e92de34c5eaa325d4e2e9cbe3aa0c6fa_Traceguids, v9);
  if ( (_DWORD)v22 )
    AutoCritSec::Unlock((AutoCritSec *)&v21);
  CWxString::_Release((CWxString *)szTableName);
  return v10;
}

```

## disassembly

```asm
0x1801bc3d0  mov     [rsp-38h+arg_18], rbx
0x1801bc3d5  push    rbp
0x1801bc3d6  push    rsi
0x1801bc3d7  push    rdi
0x1801bc3d8  push    r12
0x1801bc3da  push    r13
0x1801bc3dc  push    r14
0x1801bc3de  push    r15
0x1801bc3e0  mov     rbp, rsp
0x1801bc3e3  sub     rsp, 70h
0x1801bc3e7  lea     rax, Data
0x1801bc3ee  mov     [rbp+var_2C], 0
0x1801bc3f5  mov     [rbp+szTableName], rax
0x1801bc3f9  mov     r13d, r9d
0x1801bc3fc  mov     r14, r8
0x1801bc3ff  mov     [rbp+var_28], 0
0x1801bc407  mov     r12, rdx
0x1801bc40a  mov     [rbp+var_18], 0
0x1801bc412  mov     r15, rcx
0x1801bc415  mov     [rbp+var_8], 0
0x1801bc41d  mov     [rbp+var_10], 0
0x1801bc425  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801bc42c  jz      short loc_1801BC445
0x1801bc42e  mov     [rsp+70h+var_40], r9d
0x1801bc433  mov     r9, rcx
0x1801bc436  mov     [rsp+70h+var_48], r8
0x1801bc43b  mov     [rsp+70h+var_50], rdx
0x1801bc440  call    WPP_SF_qiql
0x1801bc445  mov     rdx, [r15+1C0h]
0x1801bc44c  lea     rcx, [rbp+var_10]; this
0x1801bc450  add     rdx, 18h; struct WxCriticalSection *
0x1801bc454  call    ?Attach@AutoCritSec@@QEAAXPEAVWxCriticalSection@@@Z; AutoCritSec::Attach(WxCriticalSection *)
0x1801bc459  lea     rcx, [rbp+var_10]; this
0x1801bc45d  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x1801bc462  mov     rcx, [r15+1C0h]; this
0x1801bc469  mov     rdx, r14; struct CWxCallerIdentity *
0x1801bc46c  call    ?IsAppCacheContainerInUse@CAppCacheContainerMap@@QEAAJPEAVCWxCallerIdentity@@@Z; CAppCacheContainerMap::IsAppCacheContainerInUse(CWxCallerIdentity *)
0x1801bc471  mov     ebx, eax
0x1801bc473  test    eax, eax
0x1801bc475  jns     short loc_1801BC4E4
0x1801bc477  mov     [rbp+var_2C], 16Dh
0x1801bc47e  mov     edi, eax
0x1801bc480  mov     rcx, [r15+1B8h]; this
0x1801bc487  lea     rdx, [rbp+var_28]; struct CJetContext **
0x1801bc48b  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1801bc490  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801bc497  jz      short loc_1801BC4B2
0x1801bc499  mov     edx, 15h
0x1801bc49e  lea     r8, WPP_e92de34c5eaa325d4e2e9cbe3aa0c6fa_Traceguids
0x1801bc4a5  mov     ecx, 40Ch
0x1801bc4aa  mov     r9d, ebx
0x1801bc4ad  call    WPP_SF_d
0x1801bc4b2  cmp     dword ptr [rbp+var_8], 0
0x1801bc4b6  jz      short loc_1801BC4C1
0x1801bc4b8  lea     rcx, [rbp+var_10]; this
0x1801bc4bc  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x1801bc4c1  lea     rcx, [rbp+szTableName]; this
0x1801bc4c5  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1801bc4ca  mov     rbx, [rsp+70h+arg_18]
0x1801bc4d2  mov     eax, edi
0x1801bc4d4  add     rsp, 70h
0x1801bc4d8  pop     r15
0x1801bc4da  pop     r14
0x1801bc4dc  pop     r13
0x1801bc4de  pop     r12
0x1801bc4e0  pop     rdi
0x1801bc4e1  pop     rsi
0x1801bc4e2  pop     rbp
0x1801bc4e3  retn
0x1801bc4e4  jnz     short loc_1801BC4EF
0x1801bc4e6  mov     edi, 1
0x1801bc4eb  mov     ebx, edi
0x1801bc4ed  jmp     short loc_1801BC480
0x1801bc4ef  lea     rdx, [rbp+var_28]; struct CJetContext **
0x1801bc4f3  mov     rcx, r15; this
0x1801bc4f6  call    ?AcquirePartitionContext@CCacheStore@@QEAAJPEAPEAVCJetContext@@@Z; CCacheStore::AcquirePartitionContext(CJetContext * *)
0x1801bc4fb  mov     ebx, eax
0x1801bc4fd  test    eax, eax
0x1801bc4ff  jns     short loc_1801BC50D
0x1801bc501  mov     [rbp+var_2C], 178h
0x1801bc508  jmp     loc_1801BC47E
0x1801bc50d  mov     rsi, [rbp+var_28]
0x1801bc511  lea     r8, szIndexName; "PartitionIndex"
0x1801bc518  mov     edi, 1
0x1801bc51d  mov     rcx, rsi; this
0x1801bc520  mov     edx, edi; unsigned int
0x1801bc522  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801bc527  mov     ebx, eax
0x1801bc529  test    eax, eax
0x1801bc52b  jns     short loc_1801BC539
0x1801bc52d  mov     [rbp+var_2C], 179h
0x1801bc534  jmp     loc_1801BC47E
0x1801bc539  mov     rcx, [rsi+10h]; sesid
0x1801bc53d  call    cs:__imp_JetBeginTransaction
0x1801bc543  mov     ecx, eax; int
0x1801bc545  mov     edx, edi; int
0x1801bc547  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bc54c  mov     ebx, eax
0x1801bc54e  test    eax, eax
0x1801bc550  js      loc_1801BC47E
0x1801bc556  xor     r8d, r8d
0x1801bc559  mov     rdx, r14
0x1801bc55c  mov     rcx, rsi
0x1801bc55f  call    ?SeekToPartition@CCacheStore@@SAJPEAVCJetContext@@PEAVCWxCallerIdentity@@W4PartitionType@@@Z; CCacheStore::SeekToPartition(CJetContext *,CWxCallerIdentity *,PartitionType)
0x1801bc564  mov     ebx, eax
0x1801bc566  test    eax, eax
0x1801bc568  jns     short loc_1801BC576
0x1801bc56a  mov     [rbp+var_2C], 17Eh
0x1801bc571  jmp     loc_1801BC666
0x1801bc576  jz      short loc_1801BC581
0x1801bc578  xor     ebx, ebx
0x1801bc57a  xor     edi, edi
0x1801bc57c  jmp     loc_1801BC668
0x1801bc581  mov     r8, r12
0x1801bc584  lea     rdx, ?c_wszAppCacheTable@@3QBGB; "AppCacheEx_%I64u"
0x1801bc58b  lea     rcx, [rbp+szTableName]; this
0x1801bc58f  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x1801bc594  mov     ebx, eax
0x1801bc596  test    eax, eax
0x1801bc598  jns     short loc_1801BC5A6
0x1801bc59a  mov     [rbp+var_2C], 18Bh
0x1801bc5a1  jmp     loc_1801BC666
0x1801bc5a6  mov     r8, [rbp+szTableName]; szTableName
0x1801bc5aa  mov     edx, [rsi+18h]; dbid
0x1801bc5ad  mov     rcx, [rsi+10h]; sesid
0x1801bc5b1  call    cs:__imp_JetDeleteTableW
0x1801bc5b7  mov     r14d, 0FFFFFAE7h
0x1801bc5bd  cmp     eax, r14d
0x1801bc5c0  jz      short loc_1801BC5D5
0x1801bc5c2  mov     edx, edi; int
0x1801bc5c4  mov     ecx, eax; int
0x1801bc5c6  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bc5cb  mov     ebx, eax
0x1801bc5cd  test    eax, eax
0x1801bc5cf  js      loc_1801BC666
0x1801bc5d5  lea     rcx, [rbp+szTableName]; this
0x1801bc5d9  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x1801bc5de  lea     rcx, [rbp+szTableName]; this
0x1801bc5e2  mov     r8, r12
0x1801bc5e5  lea     rdx, ?c_wszAppCacheEntryTable@@3QBGB; "AppCacheEntryEx_%I64u"
0x1801bc5ec  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x1801bc5f1  mov     ebx, eax
0x1801bc5f3  test    eax, eax
0x1801bc5f5  jns     short loc_1801BC600
0x1801bc5f7  mov     [rbp+var_2C], 19Dh
0x1801bc5fe  jmp     short loc_1801BC666
0x1801bc600  mov     r8, [rbp+szTableName]; szTableName
0x1801bc604  mov     edx, [rsi+18h]; dbid
0x1801bc607  mov     rcx, [rsi+10h]; sesid
0x1801bc60b  call    cs:__imp_JetDeleteTableW
0x1801bc611  cmp     eax, r14d
0x1801bc614  jz      short loc_1801BC625
0x1801bc616  mov     edx, edi; int
0x1801bc618  mov     ecx, eax; int
0x1801bc61a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bc61f  mov     ebx, eax
0x1801bc621  test    eax, eax
0x1801bc623  js      short loc_1801BC666
0x1801bc625  test    r13d, r13d
0x1801bc628  jz      short loc_1801BC647
0x1801bc62a  mov     rdx, [rsi+20h]; tableid
0x1801bc62e  mov     rcx, [rsi+10h]; sesid
0x1801bc632  call    cs:__imp_JetDelete
0x1801bc638  mov     ecx, eax; int
0x1801bc63a  mov     edx, edi; int
0x1801bc63c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bc641  mov     ebx, eax
0x1801bc643  test    eax, eax
0x1801bc645  js      short loc_1801BC666
0x1801bc647  mov     rcx, [rsi+10h]; sesid
0x1801bc64b  mov     edx, edi; grbit
0x1801bc64d  call    cs:__imp_JetCommitTransaction
0x1801bc653  mov     ecx, eax; int
0x1801bc655  mov     edx, edi; int
0x1801bc657  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bc65c  mov     ebx, eax
0x1801bc65e  test    eax, eax
0x1801bc660  jns     loc_1801BC47E
0x1801bc666  mov     edi, eax
0x1801bc668  mov     rcx, [rsi+10h]; sesid
0x1801bc66c  xor     edx, edx; grbit
0x1801bc66e  call    cs:__imp_JetRollback
0x1801bc674  jmp     loc_1801BC480
```
