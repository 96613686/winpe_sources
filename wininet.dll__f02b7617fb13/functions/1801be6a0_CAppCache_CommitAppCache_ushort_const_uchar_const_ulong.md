# CAppCache::CommitAppCache(ushort const *,uchar const *,ulong)

- ea: `0x1801be6a0`
- end: `0x1801beacd`
- name: `?CommitAppCache@CAppCache@@AEAAJPEBGPEBEK@Z`
- size: `1069`
- prototype: `__int64 __fastcall(CAppCache *__hidden this, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801bf6f0`

## callees

- `0x180020fc4`
- `0x180021360`
- `0x180025514`
- `0x180025910`
- `0x18007ec9c`
- `0x1800861f8`
- `0x1800c9b40`
- `0x1800ee168`
- `0x1800eee94`
- `0x1800fa844`
- `0x18014a7a0`
- `0x1801b8d4c`
- `0x1801b8f88`
- `0x1801be6a0`
- `0x1801bfa74`
- `0x1801bfc7c`
- `0x1801e13c0`
- `0x1801e1790`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801be92c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801be92c`
- `ESENT!JetRetrieveColumn` at `0x1801be82d`
- `ESENT!JetRetrieveColumn` at `0x1801be82d`
- `ESENT!JetCommitTransaction` at `0x1801bea84`
- `ESENT!JetCommitTransaction` at `0x1801bea84`
- `ESENT!JetUpdate` at `0x1801bea63`
- `ESENT!JetUpdate` at `0x1801bea63`
- `ESENT!JetPrepareUpdate` at `0x1801be7db`
- `ESENT!JetPrepareUpdate` at `0x1801be879`
- `ESENT!JetPrepareUpdate` at `0x1801be7db`
- `ESENT!JetPrepareUpdate` at `0x1801be879`
- `ESENT!JetRollback` at `0x1801be885`
- `ESENT!JetRollback` at `0x1801be885`
- `ESENT!JetBeginTransaction` at `0x1801be7b4`
- `ESENT!JetBeginTransaction` at `0x1801be7b4`

## string_xrefs

- `0x1801be78d`: `AppCacheIdIndex`

## pseudocode

```c
__int64 __fastcall CAppCache::CommitAppCache(
        CAppCacheContainerProperties **this,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  int AppCacheDirectory; // ebx
  int v9; // eax
  unsigned int v10; // r9d
  JET_SESID *v11; // rdi
  JET_ERR v12; // eax
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  CJetContext *v18; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int8 *v19; // [rsp+50h] [rbp-49h] BYREF
  int v20; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v21; // [rsp+5Ch] [rbp-3Dh] BYREF
  unsigned int pcbActual; // [rsp+60h] [rbp-39h] BYREF
  int v23; // [rsp+64h] [rbp-35h] BYREF
  CAppCacheContainerProperties *pvData; // [rsp+68h] [rbp-31h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *v26[2]; // [rsp+78h] [rbp-21h] BYREF
  _QWORD v27[2]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v28; // [rsp+98h] [rbp-1h] BYREF

  v18 = 0;
  pvData = 0;
  pcbActual = 0;
  v20 = 0;
  v23 = 0;
  SystemTimeAsFileTime = 0;
  v28 = a4;
  v19 = 0;
  v21 = 0;
  v27[0] = &Data;
  v27[1] = 0;
  v26[0] = (unsigned __int16 *)&Data;
  v26[1] = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qSqd(
      1036,
      89,
      (unsigned int)WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids,
      (_DWORD)this,
      (__int64)a2,
      (__int64)a3,
      a4);
  AppCacheDirectory = CAppCache::CreateSerializedData((CAppCache *)this, &v19, &v21);
  if ( AppCacheDirectory >= 0 )
  {
    v9 = CAppCacheContainerProperties::AcquireAppCacheContext(this[19], &v18);
    v11 = (JET_SESID *)v18;
    AppCacheDirectory = v9;
    if ( v9 >= 0 )
    {
      AppCacheDirectory = CJetContext::SetCurrentIndex(v18, 0, L"AppCacheIdIndex", v10);
      if ( AppCacheDirectory >= 0 )
      {
        v12 = JetBeginTransaction(v11[2]);
        AppCacheDirectory = HRESULTFromJET_ERR(v12, 1);
        if ( AppCacheDirectory >= 0 )
        {
          v13 = JetPrepareUpdate(v11[2], v11[4], 0);
          AppCacheDirectory = HRESULTFromJET_ERR(v13, 1);
          if ( AppCacheDirectory >= 0 )
          {
            v14 = JetRetrieveColumn(v11[2], v11[4], **(_DWORD **)(v11[5] + 8), &pvData, 8u, &pcbActual, 1u, 0);
            AppCacheDirectory = HRESULTFromJET_ERR(v14, 1);
            if ( AppCacheDirectory < 0 )
              goto LABEL_10;
            AppCacheDirectory = CAppCacheContainerDir::GetAppCacheDirectory(
                                  *((CAppCacheContainerDir **)this[19] + 3),
                                  (unsigned __int64)pvData,
                                  (struct CWxString *)v27);
            if ( AppCacheDirectory < 0 )
              goto LABEL_10;
            AppCacheDirectory = CAppCache::CreateManifestFile((struct CWxString *)v27, a3, a4, (struct CWxString *)v26);
            if ( AppCacheDirectory < 0 )
              goto LABEL_10;
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            v20 = WxComputePrefixHash(a2, 0xFFFFFFFFLL);
            AppCacheDirectory = CJetContext::SetBasicColumn((CJetContext *)v11, 1u, &v20, 4u);
            if ( AppCacheDirectory < 0 )
              goto LABEL_10;
            AppCacheDirectory = CJetContext::SetStringColumn((CJetContext *)v11, 2u, a2);
            if ( AppCacheDirectory < 0
              || (AppCacheDirectory = CJetContext::SetStringColumn((CJetContext *)v11, 3u, v26[0]), AppCacheDirectory < 0)
              || (AppCacheDirectory = CJetContext::SetBinaryColumn((CJetContext *)v11, 4u, v19, v21),
                  AppCacheDirectory < 0)
              || (AppCacheDirectory = CJetContext::SetBasicColumn((CJetContext *)v11, 5u, &v23, 4u),
                  AppCacheDirectory < 0)
              || (AppCacheDirectory = CJetContext::SetBasicColumn((CJetContext *)v11, 6u, &SystemTimeAsFileTime, 8u),
                  AppCacheDirectory < 0)
              || (AppCacheDirectory = CJetContext::SetBasicColumn((CJetContext *)v11, 7u, &v28, 8u),
                  AppCacheDirectory < 0)
              || (v16 = JetUpdate(v11[2], v11[4], 0, 0, 0),
                  AppCacheDirectory = HRESULTFromJET_ERR(v16, 1),
                  AppCacheDirectory < 0) )
            {
LABEL_10:
              JetPrepareUpdate(v11[2], v11[4], 3u);
            }
            else
            {
              v17 = JetCommitTransaction(v11[2], 1u);
              AppCacheDirectory = HRESULTFromJET_ERR(v17, 1);
              if ( AppCacheDirectory >= 0 )
              {
                this[1] = pvData;
                this[15] = (CAppCacheContainerProperties *)SystemTimeAsFileTime;
                CWxString::Transfer((CWxString *)v27, (struct CWxString *)(this + 7));
                CWxString::Transfer((CWxString *)v26, (struct CWxString *)(this + 11));
                goto LABEL_12;
              }
            }
          }
          JetRollback(v11[2], 0);
        }
      }
    }
LABEL_12:
    if ( v11 )
      CJetContextList::ReleaseContext(*((CJetContextList **)this[19] + 1), &v18);
  }
  WxHeapFree<_WX_AVL_TABLE>(&v19);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 90, WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids, (unsigned int)AppCacheDirectory);
  CWxString::_Release((CWxString *)v26);
  CWxString::_Release((CWxString *)v27);
  return (unsigned int)AppCacheDirectory;
}

```

## disassembly

```asm
0x1801be6a0  push    rbp
0x1801be6a2  push    rbx
0x1801be6a3  push    rsi
0x1801be6a4  push    rdi
0x1801be6a5  push    r12
0x1801be6a7  push    r13
0x1801be6a9  push    r14
0x1801be6ab  push    r15
0x1801be6ad  lea     rbp, [rsp-1Fh]
0x1801be6b2  sub     rsp, 0B8h
0x1801be6b9  mov     rax, cs:__security_cookie
0x1801be6c0  xor     rax, rsp
0x1801be6c3  mov     [rbp+57h+var_50], rax
0x1801be6c7  xor     r13d, r13d
0x1801be6ca  mov     r14d, r9d
0x1801be6cd  lea     rax, Data
0x1801be6d4  mov     [rbp+57h+var_AC], r13d
0x1801be6d8  mov     [rbp+57h+var_A8], r13
0x1801be6dc  mov     r12, r8
0x1801be6df  mov     [rbp+57h+pvData], r13
0x1801be6e3  mov     r15, rdx
0x1801be6e6  mov     [rbp+57h+var_90], r13d
0x1801be6ea  mov     rsi, rcx
0x1801be6ed  mov     [rbp+57h+var_98], r13d
0x1801be6f1  mov     [rbp+57h+var_8C], r13d
0x1801be6f5  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1801be6f9  mov     [rbp+57h+var_58], r14
0x1801be6fd  mov     [rbp+57h+var_A0], r13
0x1801be701  mov     [rbp+57h+var_94], r13d
0x1801be705  mov     [rbp+57h+var_68], rax
0x1801be709  mov     [rbp+57h+var_60], r13
0x1801be70d  mov     [rbp+57h+var_78], rax
0x1801be711  mov     [rbp+57h+var_70], r13
0x1801be715  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801be71c  jz      short loc_1801BE745
0x1801be71e  mov     [rsp+0F0h+grbit], r14d
0x1801be723  lea     edx, [r13+59h]
0x1801be727  mov     [rsp+0F0h+pcbActual], r8
0x1801be72c  mov     ecx, 40Ch
0x1801be731  lea     r8, WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids
0x1801be738  mov     qword ptr [rsp+0F0h+cbData], r15
0x1801be73d  mov     r9, rsi
0x1801be740  call    WPP_SF_qSqd
0x1801be745  lea     r8, [rbp+57h+var_94]; unsigned int *
0x1801be749  mov     rcx, rsi; this
0x1801be74c  lea     rdx, [rbp+57h+var_A0]; unsigned __int8 **
0x1801be750  call    ?CreateSerializedData@CAppCache@@AEAAJPEAPEAEPEAK@Z; CAppCache::CreateSerializedData(uchar * *,ulong *)
0x1801be755  mov     ebx, eax
0x1801be757  test    eax, eax
0x1801be759  jns     short loc_1801BE767
0x1801be75b  mov     [rbp+57h+var_AC], 0BF6h
0x1801be762  jmp     loc_1801BE8A4
0x1801be767  mov     rcx, [rsi+98h]; this
0x1801be76e  lea     rdx, [rbp+57h+var_A8]; struct CJetContext **
0x1801be772  call    ?AcquireAppCacheContext@CAppCacheContainerProperties@@QEAAJPEAPEAVCJetContext@@@Z; CAppCacheContainerProperties::AcquireAppCacheContext(CJetContext * *)
0x1801be777  mov     rdi, [rbp+57h+var_A8]
0x1801be77b  mov     ebx, eax
0x1801be77d  test    eax, eax
0x1801be77f  jns     short loc_1801BE78D
0x1801be781  mov     [rbp+57h+var_AC], 0BF8h
0x1801be788  jmp     loc_1801BE88B
0x1801be78d  lea     r8, aAppcacheidinde; "AppCacheIdIndex"
0x1801be794  xor     edx, edx; unsigned int
0x1801be796  mov     rcx, rdi; this
0x1801be799  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801be79e  mov     ebx, eax
0x1801be7a0  test    eax, eax
0x1801be7a2  jns     short loc_1801BE7B0
0x1801be7a4  mov     [rbp+57h+var_AC], 0BFBh
0x1801be7ab  jmp     loc_1801BE88B
0x1801be7b0  mov     rcx, [rdi+10h]; sesid
0x1801be7b4  call    cs:__imp_JetBeginTransaction
0x1801be7ba  mov     ecx, eax; int
0x1801be7bc  mov     edx, 1; int
0x1801be7c1  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801be7c6  mov     ebx, eax
0x1801be7c8  test    eax, eax
0x1801be7ca  js      loc_1801BE88B
0x1801be7d0  mov     rdx, [rdi+20h]; tableid
0x1801be7d4  xor     r8d, r8d; prep
0x1801be7d7  mov     rcx, [rdi+10h]; sesid
0x1801be7db  call    cs:__imp_JetPrepareUpdate
0x1801be7e1  mov     ecx, eax; int
0x1801be7e3  mov     edx, 1; int
0x1801be7e8  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801be7ed  mov     ebx, eax
0x1801be7ef  test    eax, eax
0x1801be7f1  js      loc_1801BE87F
0x1801be7f7  mov     rax, [rdi+28h]
0x1801be7fb  lea     r9, [rbp+57h+pvData]; pvData
0x1801be7ff  mov     rdx, [rdi+20h]; tableid
0x1801be803  mov     ebx, 1
0x1801be808  mov     rcx, [rdi+10h]; sesid
0x1801be80c  mov     [rsp+0F0h+pretinfo], r13; pretinfo
0x1801be811  mov     r8, [rax+8]
0x1801be815  lea     rax, [rbp+57h+var_90]
0x1801be819  mov     [rsp+0F0h+grbit], ebx; grbit
0x1801be81d  mov     [rsp+0F0h+pcbActual], rax; pcbActual
0x1801be822  mov     [rsp+0F0h+cbData], 8; cbData
0x1801be82a  mov     r8d, [r8]; columnid
0x1801be82d  call    cs:__imp_JetRetrieveColumn
0x1801be833  mov     ecx, eax; int
0x1801be835  mov     edx, ebx; int
0x1801be837  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801be83c  mov     ebx, eax
0x1801be83e  test    eax, eax
0x1801be840  js      short loc_1801BE86B
0x1801be842  mov     rcx, [rsi+98h]
0x1801be849  lea     r8, [rbp+57h+var_68]; struct CWxString *
0x1801be84d  mov     rdx, [rbp+57h+pvData]; unsigned __int64
0x1801be851  mov     rcx, [rcx+18h]; this
0x1801be855  call    ?GetAppCacheDirectory@CAppCacheContainerDir@@QEAAJ_KPEAVCWxString@@@Z; CAppCacheContainerDir::GetAppCacheDirectory(unsigned __int64,CWxString *)
0x1801be85a  mov     ebx, eax
0x1801be85c  test    eax, eax
0x1801be85e  jns     loc_1801BE903
0x1801be864  mov     [rbp+57h+var_AC], 0C17h
0x1801be86b  mov     rdx, [rdi+20h]; tableid
0x1801be86f  mov     r8d, 3; prep
0x1801be875  mov     rcx, [rdi+10h]; sesid
0x1801be879  call    cs:__imp_JetPrepareUpdate
0x1801be87f  mov     rcx, [rdi+10h]; sesid
0x1801be883  xor     edx, edx; grbit
0x1801be885  call    cs:__imp_JetRollback
0x1801be88b  test    rdi, rdi
0x1801be88e  jz      short loc_1801BE8A4
0x1801be890  mov     rcx, [rsi+98h]
0x1801be897  lea     rdx, [rbp+57h+var_A8]; struct CJetContext **
0x1801be89b  mov     rcx, [rcx+8]; this
0x1801be89f  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1801be8a4  lea     rcx, [rbp+57h+var_A0]
0x1801be8a8  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1801be8ad  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801be8b4  jz      short loc_1801BE8CF
0x1801be8b6  mov     edx, 5Ah ; 'Z'
0x1801be8bb  lea     r8, WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids
0x1801be8c2  mov     ecx, 40Ch
0x1801be8c7  mov     r9d, ebx
0x1801be8ca  call    WPP_SF_d
0x1801be8cf  lea     rcx, [rbp+57h+var_78]; this
0x1801be8d3  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1801be8d8  lea     rcx, [rbp+57h+var_68]; this
0x1801be8dc  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1801be8e1  mov     eax, ebx
0x1801be8e3  mov     rcx, [rbp+57h+var_50]
0x1801be8e7  xor     rcx, rsp; StackCookie
0x1801be8ea  call    __security_check_cookie
0x1801be8ef  add     rsp, 0B8h
0x1801be8f6  pop     r15
0x1801be8f8  pop     r14
0x1801be8fa  pop     r13
0x1801be8fc  pop     r12
0x1801be8fe  pop     rdi
0x1801be8ff  pop     rsi
0x1801be900  pop     rbx
0x1801be901  pop     rbp
0x1801be902  retn
0x1801be903  lea     r9, [rbp+57h+var_78]; struct CWxString *
0x1801be907  mov     r8d, r14d; unsigned int
0x1801be90a  mov     rdx, r12; unsigned __int8 *
0x1801be90d  lea     rcx, [rbp+57h+var_68]; struct CWxString *
0x1801be911  call    ?CreateManifestFile@CAppCache@@CAJPEAVCWxString@@PEBEK0@Z; CAppCache::CreateManifestFile(CWxString *,uchar const *,ulong,CWxString *)
0x1801be916  mov     ebx, eax
0x1801be918  test    eax, eax
0x1801be91a  jns     short loc_1801BE928
0x1801be91c  mov     [rbp+57h+var_AC], 0C20h
0x1801be923  jmp     loc_1801BE86B
0x1801be928  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801be92c  call    cs:__imp_GetSystemTimeAsFileTime
0x1801be932  or      edx, 0FFFFFFFFh
0x1801be935  mov     rcx, r15
0x1801be938  call    WxComputePrefixHash
0x1801be93d  mov     r12d, 4
0x1801be943  mov     [rbp+57h+var_98], eax
0x1801be946  mov     r9d, r12d; unsigned int
0x1801be949  lea     r8, [rbp+57h+var_98]; void *
0x1801be94d  mov     rcx, rdi; this
0x1801be950  lea     r14d, [r12-3]
0x1801be955  mov     edx, r14d; unsigned int
0x1801be958  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801be95d  mov     ebx, eax
0x1801be95f  test    eax, eax
0x1801be961  jns     short loc_1801BE96F
0x1801be963  mov     [rbp+57h+var_AC], 0C27h
0x1801be96a  jmp     loc_1801BE86B
0x1801be96f  mov     r8, r15; unsigned __int16 *
0x1801be972  mov     edx, 2; unsigned int
0x1801be977  mov     rcx, rdi; this
0x1801be97a  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x1801be97f  mov     ebx, eax
0x1801be981  test    eax, eax
0x1801be983  jns     short loc_1801BE991
0x1801be985  mov     [rbp+57h+var_AC], 0C2Ah
0x1801be98c  jmp     loc_1801BE86B
0x1801be991  mov     r8, [rbp+57h+var_78]; unsigned __int16 *
0x1801be995  mov     edx, 3; unsigned int
0x1801be99a  mov     rcx, rdi; this
0x1801be99d  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x1801be9a2  mov     ebx, eax
0x1801be9a4  test    eax, eax
0x1801be9a6  jns     short loc_1801BE9B4
0x1801be9a8  mov     [rbp+57h+var_AC], 0C2Dh
0x1801be9af  jmp     loc_1801BE86B
0x1801be9b4  mov     r9d, [rbp+57h+var_94]; unsigned int
0x1801be9b8  mov     edx, r12d; unsigned int
0x1801be9bb  mov     r8, [rbp+57h+var_A0]; unsigned __int8 *
0x1801be9bf  mov     rcx, rdi; this
0x1801be9c2  call    ?SetBinaryColumn@CJetContext@@QEAAJKPEBEK@Z; CJetContext::SetBinaryColumn(ulong,uchar const *,ulong)
0x1801be9c7  mov     ebx, eax
0x1801be9c9  test    eax, eax
0x1801be9cb  jns     short loc_1801BE9D9
0x1801be9cd  mov     [rbp+57h+var_AC], 0C31h
0x1801be9d4  jmp     loc_1801BE86B
0x1801be9d9  mov     r9d, r12d; unsigned int
0x1801be9dc  lea     r8, [rbp+57h+var_8C]; void *
0x1801be9e0  mov     edx, 5; unsigned int
0x1801be9e5  mov     rcx, rdi; this
0x1801be9e8  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801be9ed  mov     ebx, eax
0x1801be9ef  test    eax, eax
0x1801be9f1  jns     short loc_1801BE9FF
0x1801be9f3  mov     [rbp+57h+var_AC], 0C35h
0x1801be9fa  jmp     loc_1801BE86B
0x1801be9ff  mov     r15d, 8
0x1801bea05  lea     r8, [rbp+57h+SystemTimeAsFileTime]; void *
0x1801bea09  mov     r9d, r15d; unsigned int
0x1801bea0c  mov     rcx, rdi; this
0x1801bea0f  lea     edx, [r15-2]; unsigned int
0x1801bea13  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801bea18  mov     ebx, eax
0x1801bea1a  test    eax, eax
0x1801bea1c  jns     short loc_1801BEA2A
0x1801bea1e  mov     [rbp+57h+var_AC], 0C39h
0x1801bea25  jmp     loc_1801BE86B
0x1801bea2a  mov     r9d, r15d; unsigned int
0x1801bea2d  lea     r8, [rbp+57h+var_58]; void *
0x1801bea31  mov     edx, 7; unsigned int
0x1801bea36  mov     rcx, rdi; this
0x1801bea39  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801bea3e  mov     ebx, eax
0x1801bea40  test    eax, eax
0x1801bea42  jns     short loc_1801BEA50
0x1801bea44  mov     [rbp+57h+var_AC], 0C3Dh
0x1801bea4b  jmp     loc_1801BE86B
0x1801bea50  mov     rdx, [rdi+20h]; tableid
0x1801bea54  xor     r9d, r9d; cbBookmark
0x1801bea57  mov     rcx, [rdi+10h]; sesid
0x1801bea5b  xor     r8d, r8d; pvBookmark
0x1801bea5e  mov     qword ptr [rsp+0F0h+cbData], r13; pcbActual
0x1801bea63  call    cs:__imp_JetUpdate
0x1801bea69  mov     ecx, eax; int
0x1801bea6b  mov     edx, r14d; int
0x1801bea6e  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bea73  mov     ebx, eax
0x1801bea75  test    eax, eax
0x1801bea77  js      loc_1801BE86B
0x1801bea7d  mov     rcx, [rdi+10h]; sesid
0x1801bea81  mov     edx, r14d; grbit
0x1801bea84  call    cs:__imp_JetCommitTransaction
0x1801bea8a  mov     ecx, eax; int
0x1801bea8c  mov     edx, r14d; int
0x1801bea8f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bea94  mov     ebx, eax
0x1801bea96  test    eax, eax
0x1801bea98  js      loc_1801BE87F
0x1801bea9e  mov     rax, [rbp+57h+pvData]
0x1801beaa2  lea     rdx, [rsi+38h]; struct CWxString *
0x1801beaa6  mov     [rsi+8], rax
0x1801beaaa  lea     rcx, [rbp+57h+var_68]; this
0x1801beaae  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1801beab2  mov     [rsi+78h], rax
0x1801beab6  call    ?Transfer@CWxString@@QEAAXPEAV1@@Z; CWxString::Transfer(CWxString *)
0x1801beabb  lea     rdx, [rsi+58h]; struct CWxString *
0x1801beabf  lea     rcx, [rbp+57h+var_78]; this
0x1801beac3  call    ?Transfer@CWxString@@QEAAXPEAV1@@Z; CWxString::Transfer(CWxString *)
0x1801beac8  jmp     loc_1801BE88B
```
