# CBlobStore::BlobPurgeExpiredEntriesInTable(CCacheStore *,unsigned __int64,CWxCallerIdentity *)

- ea: `0x1800ae1dc`
- end: `0x1800ae4f1`
- name: `?BlobPurgeExpiredEntriesInTable@CBlobStore@@QEAAJPEAVCCacheStore@@_KPEAVCWxCallerIdentity@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CBlobStore *__hidden this, struct CCacheStore *, unsigned __int64, struct CWxCallerIdentity *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800aee7c`

## callees

- `0x180021360`
- `0x1800422d0`
- `0x1800440c8`
- `0x18007ec9c`
- `0x18007ee10`
- `0x180083dc4`
- `0x1800861f8`
- `0x1800aca44`
- `0x1800ae1dc`
- `0x1800ae4f8`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e53d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ae2ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ae2ab`
- `ESENT!JetSetColumn` at `0x1800ae36e`
- `ESENT!JetSetColumn` at `0x1800ae36e`
- `ESENT!JetCommitTransaction` at `0x1800ae4b9`
- `ESENT!JetCommitTransaction` at `0x1800ae4b9`
- `ESENT!JetUpdate` at `0x1800ae395`
- `ESENT!JetUpdate` at `0x1800ae395`
- `ESENT!JetPrepareUpdate` at `0x1800ae323`
- `ESENT!JetPrepareUpdate` at `0x1800ae3bd`
- `ESENT!JetPrepareUpdate` at `0x1800ae323`
- `ESENT!JetPrepareUpdate` at `0x1800ae3bd`
- `ESENT!JetRollback` at `0x1800ae3c9`
- `ESENT!JetRollback` at `0x1800ae3c9`
- `ESENT!JetBeginTransaction` at `0x1800ae2db`
- `ESENT!JetBeginTransaction` at `0x1800ae2db`

## pseudocode

```c
__int64 __fastcall CBlobStore::BlobPurgeExpiredEntriesInTable(
        CBlobStore *this,
        CJetContextList **a2,
        unsigned __int64 a3,
        struct CWxCallerIdentity *a4)
{
  JET_SESID *v4; // rdi
  int v9; // r8d
  JET_ERR v10; // ebx
  unsigned int v11; // r9d
  JET_ERR v12; // eax
  int v13; // eax
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  JET_ERR v17; // eax
  struct CJetContext *v18; // [rsp+48h] [rbp-28h] BYREF
  struct CBlobContainerProps *v19; // [rsp+50h] [rbp-20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-18h] BYREF

  v4 = 0;
  v18 = 0;
  v19 = 0;
  SystemTimeAsFileTime = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qqi(
      (_DWORD)this,
      18,
      (unsigned int)WPP_5a95f2a397ca3ed9078c668ec868fb04_Traceguids,
      (_DWORD)this,
      (__int64)a2);
  if ( !a2 )
  {
    v10 = -2147024809;
    goto LABEL_20;
  }
  if ( a4 )
  {
    if ( (unsigned int)CCacheStore::IsTerminating((CCacheStore *)a2) )
    {
      v10 = 0;
    }
    else
    {
      v10 = CBlobStore::AcquireBlobContainerProps(this, a3, v9, a4, &v19);
      if ( v10 >= 0 )
      {
        v10 = CBlobContainerProps::Purge(v19, 0);
        if ( v10 >= 0 )
        {
          v10 = CJetContextList::AcquireContext(a2[55], &v18, 0);
          if ( v10 < 0 )
          {
            v4 = (JET_SESID *)v18;
          }
          else
          {
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            v4 = (JET_SESID *)v18;
            v10 = CJetContext::SetCurrentIndex(v18, 1u, L"PartitionIndex", v11);
            if ( v10 >= 0 )
            {
              v12 = JetBeginTransaction(v4[2]);
              v10 = HRESULTFromJET_ERR(v12, 1);
              if ( v10 >= 0 )
              {
                v13 = CCacheStore::SeekToPartition(v4, a4, 4);
                v10 = v13;
                if ( v13 < 0 )
                  goto LABEL_17;
                if ( v13 == 1 )
                {
                  v10 = 1;
                  goto LABEL_17;
                }
                v14 = JetPrepareUpdate(v4[2], v4[4], 2u);
                v10 = HRESULTFromJET_ERR(v14, 1);
                if ( v10 < 0 )
                {
LABEL_17:
                  JetRollback(v4[2], 0);
                  goto LABEL_32;
                }
                v10 = JetSetColumn(
                        v4[2],
                        v4[4],
                        *(_DWORD *)(*(_QWORD *)(v4[5] + 8) + 20LL),
                        &SystemTimeAsFileTime,
                        8u,
                        0,
                        0);
                if ( v10 < 0 || (v15 = JetUpdate(v4[2], v4[4], 0, 0, 0), v10 = HRESULTFromJET_ERR(v15, 1), v10 < 0) )
                {
                  JetPrepareUpdate(v4[2], v4[4], 3u);
                  goto LABEL_17;
                }
                v17 = JetCommitTransaction(v4[2], 1u);
                v10 = HRESULTFromJET_ERR(v17, 1);
                if ( v10 < 0 )
                  goto LABEL_17;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v10 = -2147024809;
  }
LABEL_32:
  if ( v4 )
    CJetContextList::ReleaseContext(a2[55], &v18);
LABEL_20:
  CBlobStore::ReleaseBlobContainerProps(this, &v19);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 19, WPP_5a95f2a397ca3ed9078c668ec868fb04_Traceguids, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800ae1dc  push    rbp
0x1800ae1de  push    rbx
0x1800ae1df  push    rsi
0x1800ae1e0  push    rdi
0x1800ae1e1  push    r13
0x1800ae1e3  push    r14
0x1800ae1e5  push    r15
0x1800ae1e7  mov     rbp, rsp
0x1800ae1ea  sub     rsp, 70h
0x1800ae1ee  mov     rax, cs:__security_cookie
0x1800ae1f5  xor     rax, rsp
0x1800ae1f8  mov     [rbp+var_10], rax
0x1800ae1fc  xor     edi, edi
0x1800ae1fe  mov     [rbp+var_2C], 0
0x1800ae205  mov     [rbp+var_28], rdi
0x1800ae209  mov     r14, r9
0x1800ae20c  mov     rbx, r8
0x1800ae20f  mov     [rbp+var_20], 0
0x1800ae217  mov     rsi, rdx
0x1800ae21a  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800ae222  mov     r15, rcx
0x1800ae225  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ae22c  jnz     loc_1800AE43D
0x1800ae232  test    rsi, rsi
0x1800ae235  jz      loc_1800AE460
0x1800ae23b  test    r14, r14
0x1800ae23e  jz      loc_1800AE46E
0x1800ae244  mov     rcx, rsi; this
0x1800ae247  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1800ae24c  test    eax, eax
0x1800ae24e  jnz     loc_1800AE47C
0x1800ae254  lea     rax, [rbp+var_20]
0x1800ae258  mov     r9, r14; struct CWxCallerIdentity *
0x1800ae25b  mov     rdx, rbx; unsigned __int64
0x1800ae25e  mov     qword ptr [rsp+70h+cbData], rax; struct CBlobContainerProps **
0x1800ae263  mov     rcx, r15; this
0x1800ae266  call    ?AcquireBlobContainerProps@CBlobStore@@QEAAJ_KHPEAVCWxCallerIdentity@@PEAPEAVCBlobContainerProps@@@Z; CBlobStore::AcquireBlobContainerProps(unsigned __int64,int,CWxCallerIdentity *,CBlobContainerProps * *)
0x1800ae26b  mov     ebx, eax
0x1800ae26d  test    eax, eax
0x1800ae26f  js      loc_1800AE480
0x1800ae275  mov     rcx, [rbp+var_20]; this
0x1800ae279  xor     edx, edx; int
0x1800ae27b  call    ?Purge@CBlobContainerProps@@QEAAJH@Z; CBlobContainerProps::Purge(int)
0x1800ae280  mov     ebx, eax
0x1800ae282  test    eax, eax
0x1800ae284  js      loc_1800AE3E4
0x1800ae28a  mov     rcx, [rsi+1B8h]; this
0x1800ae291  lea     rdx, [rbp+var_28]; struct CJetContext **
0x1800ae295  xor     r8d, r8d; int *
0x1800ae298  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800ae29d  mov     ebx, eax
0x1800ae29f  test    eax, eax
0x1800ae2a1  js      loc_1800AE3D4
0x1800ae2a7  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800ae2ab  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ae2b1  mov     rdi, [rbp+var_28]
0x1800ae2b5  lea     r8, szIndexName; "PartitionIndex"
0x1800ae2bc  mov     r13d, 1
0x1800ae2c2  mov     rcx, rdi; this
0x1800ae2c5  mov     edx, r13d; unsigned int
0x1800ae2c8  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1800ae2cd  mov     ebx, eax
0x1800ae2cf  test    eax, eax
0x1800ae2d1  js      loc_1800AE489
0x1800ae2d7  mov     rcx, [rdi+10h]; sesid
0x1800ae2db  call    cs:__imp_JetBeginTransaction
0x1800ae2e1  mov     ecx, eax; int
0x1800ae2e3  mov     edx, r13d; int
0x1800ae2e6  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ae2eb  mov     ebx, eax
0x1800ae2ed  test    eax, eax
0x1800ae2ef  js      loc_1800AE4D3
0x1800ae2f5  lea     r8d, [r13+3]
0x1800ae2f9  mov     rdx, r14
0x1800ae2fc  mov     rcx, rdi
0x1800ae2ff  call    ?SeekToPartition@CCacheStore@@SAJPEAVCJetContext@@PEAVCWxCallerIdentity@@W4PartitionType@@@Z; CCacheStore::SeekToPartition(CJetContext *,CWxCallerIdentity *,PartitionType)
0x1800ae304  mov     ebx, eax
0x1800ae306  test    eax, eax
0x1800ae308  js      loc_1800AE492
0x1800ae30e  cmp     eax, r13d
0x1800ae311  jz      loc_1800AE49E
0x1800ae317  mov     rdx, [rdi+20h]; tableid
0x1800ae31b  lea     r8d, [r13+1]; prep
0x1800ae31f  mov     rcx, [rdi+10h]; sesid
0x1800ae323  call    cs:__imp_JetPrepareUpdate
0x1800ae329  mov     ecx, eax; int
0x1800ae32b  mov     edx, r13d; int
0x1800ae32e  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ae333  mov     ebx, eax
0x1800ae335  test    eax, eax
0x1800ae337  js      loc_1800AE3C3
0x1800ae33d  mov     rax, [rdi+28h]
0x1800ae341  lea     r9, [rbp+SystemTimeAsFileTime]; pvData
0x1800ae345  mov     rdx, [rdi+20h]; tableid
0x1800ae349  mov     rcx, [rdi+10h]; sesid
0x1800ae34d  mov     [rsp+70h+psetinfo], 0; psetinfo
0x1800ae356  mov     r8, [rax+8]
0x1800ae35a  mov     [rsp+70h+grbit], 0; grbit
0x1800ae362  mov     [rsp+70h+cbData], 8; cbData
0x1800ae36a  mov     r8d, [r8+14h]; columnid
0x1800ae36e  call    cs:__imp_JetSetColumn
0x1800ae374  mov     ebx, eax
0x1800ae376  test    eax, eax
0x1800ae378  js      loc_1800AE4A6
0x1800ae37e  mov     rdx, [rdi+20h]; tableid
0x1800ae382  xor     r9d, r9d; cbBookmark
0x1800ae385  mov     rcx, [rdi+10h]; sesid
0x1800ae389  xor     r8d, r8d; pvBookmark
0x1800ae38c  mov     qword ptr [rsp+70h+cbData], 0; pcbActual
0x1800ae395  call    cs:__imp_JetUpdate
0x1800ae39b  mov     ecx, eax; int
0x1800ae39d  mov     edx, r13d; int
0x1800ae3a0  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ae3a5  mov     ebx, eax
0x1800ae3a7  test    eax, eax
0x1800ae3a9  jns     loc_1800AE4B2
0x1800ae3af  mov     rdx, [rdi+20h]; tableid
0x1800ae3b3  mov     r8d, 3; prep
0x1800ae3b9  mov     rcx, [rdi+10h]; sesid
0x1800ae3bd  call    cs:__imp_JetPrepareUpdate
0x1800ae3c3  mov     rcx, [rdi+10h]; sesid
0x1800ae3c7  xor     edx, edx; grbit
0x1800ae3c9  call    cs:__imp_JetRollback
0x1800ae3cf  jmp     loc_1800AE4D3
0x1800ae3d4  mov     rdi, [rbp+var_28]
0x1800ae3d8  mov     [rbp+var_2C], 0EEh
0x1800ae3df  jmp     loc_1800AE4D3
0x1800ae3e4  mov     [rbp+var_2C], 0E8h
0x1800ae3eb  jmp     loc_1800AE4D3
0x1800ae3f0  lea     rdx, [rbp+var_20]; struct CBlobContainerProps **
0x1800ae3f4  mov     rcx, r15; this
0x1800ae3f7  call    ?ReleaseBlobContainerProps@CBlobStore@@QEAAXPEAPEAVCBlobContainerProps@@@Z; CBlobStore::ReleaseBlobContainerProps(CBlobContainerProps * *)
0x1800ae3fc  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ae403  jnz     short loc_1800AE422
0x1800ae405  mov     eax, ebx
0x1800ae407  mov     rcx, [rbp+var_10]
0x1800ae40b  xor     rcx, rsp; StackCookie
0x1800ae40e  call    __security_check_cookie
0x1800ae413  add     rsp, 70h
0x1800ae417  pop     r15
0x1800ae419  pop     r14
0x1800ae41b  pop     r13
0x1800ae41d  pop     rdi
0x1800ae41e  pop     rsi
0x1800ae41f  pop     rbx
0x1800ae420  pop     rbp
0x1800ae421  retn
0x1800ae422  mov     edx, 13h
0x1800ae427  lea     r8, WPP_5a95f2a397ca3ed9078c668ec868fb04_Traceguids
0x1800ae42e  mov     ecx, 40Ch
0x1800ae433  mov     r9d, ebx
0x1800ae436  call    WPP_SF_d
0x1800ae43b  jmp     short loc_1800AE405
0x1800ae43d  mov     edx, 12h
0x1800ae442  mov     qword ptr [rsp+70h+grbit], rbx
0x1800ae447  mov     r9, r15
0x1800ae44a  mov     qword ptr [rsp+70h+cbData], rsi
0x1800ae44f  lea     r8, WPP_5a95f2a397ca3ed9078c668ec868fb04_Traceguids
0x1800ae456  call    WPP_SF_qqi
0x1800ae45b  jmp     loc_1800AE232
0x1800ae460  mov     ebx, 80070057h
0x1800ae465  mov     [rbp+var_2C], 0DBh
0x1800ae46c  jmp     short loc_1800AE3F0
0x1800ae46e  mov     ebx, 80070057h
0x1800ae473  mov     [rbp+var_2C], 0DCh
0x1800ae47a  jmp     short loc_1800AE4D3
0x1800ae47c  xor     ebx, ebx
0x1800ae47e  jmp     short loc_1800AE4D3
0x1800ae480  mov     [rbp+var_2C], 0E6h
0x1800ae487  jmp     short loc_1800AE4D3
0x1800ae489  mov     [rbp+var_2C], 0F4h
0x1800ae490  jmp     short loc_1800AE4D3
0x1800ae492  mov     [rbp+var_2C], 0FBh
0x1800ae499  jmp     loc_1800AE3C3
0x1800ae49e  mov     ebx, r13d
0x1800ae4a1  jmp     loc_1800AE3C3
0x1800ae4a6  mov     [rbp+var_2C], 109h
0x1800ae4ad  jmp     loc_1800AE3AF
0x1800ae4b2  mov     rcx, [rdi+10h]; sesid
0x1800ae4b6  mov     edx, r13d; grbit
0x1800ae4b9  call    cs:__imp_JetCommitTransaction
0x1800ae4bf  mov     ecx, eax; int
0x1800ae4c1  mov     edx, r13d; int
0x1800ae4c4  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ae4c9  mov     ebx, eax
0x1800ae4cb  test    eax, eax
0x1800ae4cd  js      loc_1800AE3C3
0x1800ae4d3  test    rdi, rdi
0x1800ae4d6  jz      loc_1800AE3F0
0x1800ae4dc  mov     rcx, [rsi+1B8h]; this
0x1800ae4e3  lea     rdx, [rbp+var_28]; struct CJetContext **
0x1800ae4e7  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800ae4ec  jmp     loc_1800AE3F0
```
