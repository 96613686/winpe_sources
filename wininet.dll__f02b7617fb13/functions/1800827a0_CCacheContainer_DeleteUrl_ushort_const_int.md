# CCacheContainer::DeleteUrl(ushort const *,int)

- ea: `0x1800827a0`
- end: `0x180082cb9`
- name: `?DeleteUrl@CCacheContainer@@QEAAJPEBGH@Z`
- size: `1305`
- prototype: `int(CCacheContainer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180041320`

## callees

- `0x180020fc4`
- `0x180023590`
- `0x18007e620`
- `0x18007ec9c`
- `0x180082700`
- `0x1800827a0`
- `0x180083540`
- `0x1800838d8`
- `0x180083dc4`
- `0x180085460`
- `0x180085898`
- `0x1800861f8`
- `0x180086aa4`
- `0x1800b48c0`
- `0x1800b5bdc`
- `0x1800fc68c`
- `0x1800ffb10`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801e1b60`
- `0x1801e1d20`
- `0x1801e1de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082ba6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082ba6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082b61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082b61`
- `ESENT!JetSetCurrentIndex2W` at `0x180082be7`
- `ESENT!JetSetCurrentIndex2W` at `0x180082be7`
- `ESENT!JetCommitTransaction` at `0x1800829d9`
- `ESENT!JetCommitTransaction` at `0x1800829d9`
- `ESENT!JetRollback` at `0x180082a6e`
- `ESENT!JetRollback` at `0x180082a6e`
- `ESENT!JetBeginTransaction` at `0x180082925`
- `ESENT!JetBeginTransaction` at `0x180082925`

## pseudocode

```c
__int64 __fastcall CCacheContainer::DeleteUrl(CCacheContainer *this, const unsigned __int16 *a2, int a3)
{
  CJetContext *v6; // rsi
  int v7; // r15d
  int v8; // ecx
  int v9; // r8d
  int v10; // ecx
  CContainerProps **v11; // rbx
  signed int updated; // edi
  __int64 v13; // rdx
  unsigned __int64 v14; // r15
  int v15; // eax
  int v16; // edx
  JET_ERR v17; // eax
  int v18; // eax
  JET_ERR v19; // eax
  signed int v20; // eax
  __int64 v21; // r14
  int v23; // r12d
  JET_TABLEID v24; // rdx
  JET_SESID v25; // rcx
  JET_ERR v26; // eax
  int v27; // [rsp+40h] [rbp-C0h]
  CJetContext *v28; // [rsp+50h] [rbp-B0h] BYREF
  struct CInFlightEntry *v29; // [rsp+58h] [rbp-A8h] BYREF
  int v30[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v34[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v35[80]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v36[16]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v37[24]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v38[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v39[16]; // [rsp+120h] [rbp+20h] BYREF

  v28 = 0;
  v27 = 0;
  v29 = 0;
  v30[0] = 0;
  v6 = 0;
  v7 = 0;
  memset_0(v31, 0, 0xC0u);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qSl(v8, 32, (unsigned int)WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (_DWORD)this, (__int64)a2, a3);
  v10 = *((_DWORD *)this + 8) & 2;
  v11 = (CContainerProps **)((char *)this + 40);
  updated = v10 == 0 ? 0x80070005 : 0;
  if ( v10 )
  {
    updated = CContainerProps::UpdateLastAccessTime(*v11);
    if ( updated >= 0 )
    {
      v14 = WxComputeUrlHash(a2, v13);
      updated = CInFlightLocks::AcquireLock(*((CInFlightLocks **)*v11 + 18), v14, &v29);
      if ( updated < 0 )
      {
        v7 = 0;
        goto LABEL_23;
      }
      v15 = CJetContextList::AcquireContext(*((CJetContextList **)*v11 + 19), &v28, 0);
      v6 = v28;
      updated = v15;
      if ( v15 >= 0 )
      {
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_qdSD(v10, v16, v9, (_DWORD)v28, 0, (__int64)L"HashEntryIdIndex", 0);
        if ( *((_DWORD *)v6 + 12) )
        {
          v24 = *((_QWORD *)v6 + 4);
          v25 = *((_QWORD *)v6 + 2);
          *((_DWORD *)v6 + 12) = -1;
          v26 = JetSetCurrentIndex2W(v25, v24, L"HashEntryIdIndex", 0);
          updated = HRESULTFromJET_ERR(v26, 1);
          if ( updated >= 0 )
            *((_DWORD *)v6 + 12) = 0;
        }
        else
        {
          updated = 0;
        }
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_d(1036, 14, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)updated);
        if ( updated >= 0 )
        {
          v17 = JetBeginTransaction(*((_QWORD *)v6 + 2));
          updated = HRESULTFromJET_ERR(v17, 1);
          if ( updated >= 0 )
          {
            v27 = 1;
            v18 = SeekToEntry(v6, a2, v14);
            updated = v18;
            if ( v18 >= 0 )
            {
              if ( v18 )
              {
                updated = -2147024894;
              }
              else
              {
                updated = GetEntryFixedInfoAtCursor(
                            *((_QWORD *)v6 + 2),
                            *((_QWORD *)v6 + 4),
                            *(unsigned int **)(*((_QWORD *)v6 + 5) + 8LL),
                            (struct ENTRY_INFO *)v31);
                if ( updated >= 0 )
                {
                  updated = GetEntryFilenameGroupInfoAtCursor(
                              *((_QWORD *)v6 + 2),
                              *((_QWORD *)v6 + 4),
                              *(unsigned int **)(*((_QWORD *)v6 + 5) + 8LL),
                              (struct ENTRY_INFO *)v31);
                  if ( updated >= 0 )
                  {
                    updated = CCacheContainer::DeleteEntryAtCursor(this, v6, (struct ENTRY_INFO *)v31, v30);
                    if ( updated >= 0 )
                    {
                      v19 = JetCommitTransaction(*((_QWORD *)v6 + 2), 1u);
                      updated = HRESULTFromJET_ERR(v19, 1);
                      if ( updated >= 0 )
                      {
                        v7 = 0;
                        CJetContextList::ReleaseContext(*((CJetContextList **)*v11 + 19), &v28);
                        if ( v30[0] )
                        {
                          v20 = CContainerProps::DeleteEntryFile(*v11, (struct ENTRY_INFO *)v31, 1, a3, 1, 0);
                          v6 = v28;
                          updated = v20;
                        }
                        else
                        {
                          v6 = v28;
                          updated = -2147024864;
                        }
                        goto LABEL_23;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      v7 = v27;
    }
  }
LABEL_23:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_ISD(v10, 33, v9, *((_QWORD *)this + 3), (__int64)a2, updated);
  if ( v7 )
    JetRollback(*((_QWORD *)v6 + 2), 0);
  v21 = *((_QWORD *)*v11 + 19);
  if ( v6 )
  {
    CCacheStore::EndActivity(*(CCacheStore **)(v21 + 80));
    v23 = 0;
    *((_QWORD *)v6 + 1) = 0;
    if ( v21 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v21 + 8));
      v23 = 1;
    }
    --*(_DWORD *)(v21 + 60);
    if ( (unsigned int)(*(_DWORD *)(v21 + 56) - *(_DWORD *)(v21 + 60)) > *(_DWORD *)(v21 + 64) )
    {
      --*(_DWORD *)(v21 + 56);
      CJetContext::Release(v6);
    }
    else
    {
      *((_QWORD *)v6 + 1) = *(_QWORD *)(v21 + 48);
      *(_QWORD *)(v21 + 48) = v6;
    }
    if ( v23 && v21 != -8 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v21 + 8));
  }
  CInFlightLocks::ReleaseLock(*((CInFlightLocks **)*v11 + 18), &v29);
  WxHeapFree<_WX_AVL_TABLE>(v32);
  WxHeapFree<_WX_AVL_TABLE>(v33);
  WxHeapFree<_WX_AVL_TABLE>(v34);
  WxHeapFree<_WX_AVL_TABLE>(v35);
  WxHeapFree<_WX_AVL_TABLE>(v36);
  WxHeapFree<_WX_AVL_TABLE>(v37);
  WxHeapFree<unsigned __int64>(v38);
  WxHeapFree<_WX_AVL_TABLE>(v39);
  memset_0(v31, 0, 0xC0u);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 34, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (unsigned int)updated);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800827a0  mov     [rsp-8+arg_18], rbx
0x1800827a5  push    rbp
0x1800827a6  push    rsi
0x1800827a7  push    rdi
0x1800827a8  push    r12
0x1800827aa  push    r13
0x1800827ac  push    r14
0x1800827ae  push    r15
0x1800827b0  lea     rbp, [rsp-40h]
0x1800827b5  sub     rsp, 140h
0x1800827bc  mov     rax, cs:__security_cookie
0x1800827c3  xor     rax, rsp
0x1800827c6  mov     [rbp+70h+var_40], rax
0x1800827ca  xor     eax, eax
0x1800827cc  mov     r12d, r8d
0x1800827cf  mov     r13, rdx
0x1800827d2  mov     [rsp+170h+var_124], eax
0x1800827d6  mov     r14, rcx
0x1800827d9  mov     [rsp+170h+var_120], rax
0x1800827de  xor     edx, edx; Val
0x1800827e0  mov     [rsp+170h+var_130], eax
0x1800827e4  mov     r8d, 0C0h; Size
0x1800827ea  mov     [rsp+170h+var_118], rax
0x1800827ef  lea     rcx, [rsp+170h+var_100]; void *
0x1800827f4  mov     [rsp+170h+var_110], eax
0x1800827f8  mov     esi, eax
0x1800827fa  mov     r15d, eax
0x1800827fd  call    memset_0
0x180082802  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180082809  jz      short loc_180082827
0x18008280b  lea     edx, [rsi+20h]
0x18008280e  mov     [rsp+170h+var_148], r12d
0x180082813  mov     r9, r14
0x180082816  mov     qword ptr [rsp+170h+var_150], r13
0x18008281b  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x180082822  call    WPP_SF_qSl
0x180082827  mov     ecx, [r14+20h]
0x18008282b  mov     [rsp+170h+var_124], esi
0x18008282f  and     ecx, 2
0x180082832  jz      loc_180082C30
0x180082838  mov     eax, ecx
0x18008283a  lea     rbx, [r14+28h]
0x18008283e  neg     eax
0x180082840  sbb     edi, edi
0x180082842  not     edi
0x180082844  and     edi, 80070005h
0x18008284a  test    ecx, ecx
0x18008284c  jz      loc_180082C19
0x180082852  mov     rcx, [rbx]; this
0x180082855  call    ?UpdateLastAccessTime@CContainerProps@@QEAAJXZ; CContainerProps::UpdateLastAccessTime(void)
0x18008285a  mov     edi, eax
0x18008285c  test    eax, eax
0x18008285e  js      loc_180082C3D
0x180082864  mov     rcx, r13
0x180082867  call    WxComputeUrlHash
0x18008286c  mov     rcx, [rbx]
0x18008286f  lea     r8, [rsp+170h+var_118]; struct CInFlightEntry **
0x180082874  mov     rdx, rax; unsigned __int64
0x180082877  mov     r15, rax
0x18008287a  mov     rcx, [rcx+90h]; this
0x180082881  call    ?AcquireLock@CInFlightLocks@@QEAAJ_KPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::AcquireLock(unsigned __int64,CInFlightEntry * *)
0x180082886  mov     edi, eax
0x180082888  test    eax, eax
0x18008288a  js      loc_180082C4A
0x180082890  mov     rcx, [rbx]
0x180082893  lea     rdx, [rsp+170h+var_120]; struct CJetContext **
0x180082898  xor     r8d, r8d; int *
0x18008289b  mov     rcx, [rcx+98h]; this
0x1800828a2  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800828a7  mov     rsi, [rsp+170h+var_120]
0x1800828ac  mov     edi, eax
0x1800828ae  test    eax, eax
0x1800828b0  js      loc_180082C5A
0x1800828b6  mov     [rsp+170h+var_124], 0
0x1800828be  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800828c5  lea     rdi, aHashentryidind; "HashEntryIdIndex"
0x1800828cc  jz      short loc_1800828EB
0x1800828ce  mov     [rsp+170h+var_140], 0
0x1800828d6  mov     r9, rsi
0x1800828d9  mov     qword ptr [rsp+170h+var_148], rdi
0x1800828de  mov     [rsp+170h+var_150], 0
0x1800828e6  call    WPP_SF_qdSD
0x1800828eb  cmp     dword ptr [rsi+30h], 0
0x1800828ef  jnz     loc_180082BD2
0x1800828f5  xor     edi, edi
0x1800828f7  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800828fe  jz      short loc_180082919
0x180082900  mov     edx, 0Eh
0x180082905  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x18008290c  mov     ecx, 40Ch
0x180082911  mov     r9d, edi
0x180082914  call    WPP_SF_d
0x180082919  test    edi, edi
0x18008291b  js      loc_180082C67
0x180082921  mov     rcx, [rsi+10h]; sesid
0x180082925  call    cs:__imp_JetBeginTransaction
0x18008292b  mov     ecx, eax; int
0x18008292d  mov     edx, 1; int
0x180082932  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180082937  mov     edi, eax
0x180082939  test    eax, eax
0x18008293b  js      loc_180082BBE
0x180082941  mov     r8, r15; unsigned __int64
0x180082944  mov     [rsp+170h+var_130], 1
0x18008294c  mov     rdx, r13; unsigned __int16 *
0x18008294f  mov     rcx, rsi; struct CJetContext *
0x180082952  call    ?SeekToEntry@@YAJPEAVCJetContext@@PEBG_K@Z; SeekToEntry(CJetContext *,ushort const *,unsigned __int64)
0x180082957  mov     edi, eax
0x180082959  test    eax, eax
0x18008295b  js      loc_180082BC8
0x180082961  jnz     loc_180082BB1
0x180082967  mov     r8, [rsi+28h]
0x18008296b  lea     r9, [rsp+170h+var_100]; struct ENTRY_INFO *
0x180082970  mov     rdx, [rsi+20h]; unsigned __int64
0x180082974  mov     rcx, [rsi+10h]; unsigned __int64
0x180082978  mov     r8, [r8+8]; unsigned int *
0x18008297c  call    ?GetEntryFixedInfoAtCursor@@YAJ_K0PEAKPEAUENTRY_INFO@@@Z; GetEntryFixedInfoAtCursor(unsigned __int64,unsigned __int64,ulong *,ENTRY_INFO *)
0x180082981  mov     edi, eax
0x180082983  test    eax, eax
0x180082985  js      loc_180082C74
0x18008298b  mov     r8, [rsi+28h]
0x18008298f  lea     r9, [rsp+170h+var_100]; struct ENTRY_INFO *
0x180082994  mov     rdx, [rsi+20h]; unsigned __int64
0x180082998  mov     rcx, [rsi+10h]; sesid
0x18008299c  mov     r8, [r8+8]; unsigned int *
0x1800829a0  call    ?GetEntryFilenameGroupInfoAtCursor@@YAJ_K0PEAKPEAUENTRY_INFO@@@Z; GetEntryFilenameGroupInfoAtCursor(unsigned __int64,unsigned __int64,ulong *,ENTRY_INFO *)
0x1800829a5  mov     edi, eax
0x1800829a7  test    eax, eax
0x1800829a9  js      loc_180082C0F
0x1800829af  lea     r9, [rsp+170h+var_110]; int *
0x1800829b4  mov     rdx, rsi; struct CJetContext *
0x1800829b7  lea     r8, [rsp+170h+var_100]; struct ENTRY_INFO *
0x1800829bc  mov     rcx, r14; this
0x1800829bf  call    ?DeleteEntryAtCursor@CCacheContainer@@AEAAJPEAVCJetContext@@PEAUENTRY_INFO@@PEAH@Z; CCacheContainer::DeleteEntryAtCursor(CJetContext *,ENTRY_INFO *,int *)
0x1800829c4  mov     edi, eax
0x1800829c6  test    eax, eax
0x1800829c8  js      loc_180082C26
0x1800829ce  mov     rcx, [rsi+10h]; sesid
0x1800829d2  mov     edi, 1
0x1800829d7  mov     edx, edi; grbit
0x1800829d9  call    cs:__imp_JetCommitTransaction
0x1800829df  mov     ecx, eax; int
0x1800829e1  mov     edx, edi; int
0x1800829e3  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800829e8  mov     edi, eax
0x1800829ea  test    eax, eax
0x1800829ec  js      loc_180082BBE
0x1800829f2  mov     rcx, [rbx]
0x1800829f5  lea     rdx, [rsp+170h+var_120]; struct CJetContext **
0x1800829fa  xor     r15d, r15d
0x1800829fd  mov     rcx, [rcx+98h]; this
0x180082a04  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x180082a09  cmp     [rsp+170h+var_110], r15d
0x180082a0e  jz      loc_180082C81
0x180082a14  mov     rcx, [rbx]; this
0x180082a17  lea     eax, [r15+1]
0x180082a1b  mov     r8d, eax; int
0x180082a1e  mov     [rsp+170h+var_148], r15d; int
0x180082a23  mov     r9d, r12d; int
0x180082a26  mov     [rsp+170h+var_150], eax; int
0x180082a2a  lea     rdx, [rsp+170h+var_100]; struct ENTRY_INFO *
0x180082a2f  call    ?DeleteEntryFile@CContainerProps@@QEAAJPEAUENTRY_INFO@@HHHH@Z; CContainerProps::DeleteEntryFile(ENTRY_INFO *,int,int,int,int)
0x180082a34  mov     rsi, [rsp+170h+var_120]
0x180082a39  mov     edi, eax
0x180082a3b  test    eax, eax
0x180082a3d  js      loc_180082C98
0x180082a43  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180082a4a  jz      short loc_180082A63
0x180082a4c  mov     r9, [r14+18h]
0x180082a50  mov     edx, 21h ; '!'
0x180082a55  mov     [rsp+170h+var_148], edi
0x180082a59  mov     qword ptr [rsp+170h+var_150], r13
0x180082a5e  call    WPP_SF_ISD
0x180082a63  test    r15d, r15d
0x180082a66  jz      short loc_180082A74
0x180082a68  mov     rcx, [rsi+10h]; sesid
0x180082a6c  xor     edx, edx; grbit
0x180082a6e  call    cs:__imp_JetRollback
0x180082a74  mov     rax, [rbx]
0x180082a77  mov     r14, [rax+98h]
0x180082a7e  test    rsi, rsi
0x180082a81  jz      short loc_180082A95
0x180082a83  mov     rcx, [r14+50h]; this
0x180082a87  call    ?EndActivity@CCacheStore@@QEAAXXZ; CCacheStore::EndActivity(void)
0x180082a8c  test    rsi, rsi
0x180082a8f  jnz     loc_180082B4E
0x180082a95  mov     rcx, [rbx]
0x180082a98  lea     rdx, [rsp+170h+var_118]; struct CInFlightEntry **
0x180082a9d  mov     rcx, [rcx+90h]; this
0x180082aa4  call    ?ReleaseLock@CInFlightLocks@@QEAAXPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::ReleaseLock(CInFlightEntry * *)
0x180082aa9  lea     rcx, [rbp+70h+var_F0]
0x180082aad  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x180082ab2  lea     rcx, [rbp+70h+var_E8]
0x180082ab6  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x180082abb  lea     rcx, [rbp+70h+var_E0]
0x180082abf  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x180082ac4  lea     rcx, [rbp+70h+var_D8]
0x180082ac8  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x180082acd  lea     rcx, [rbp+70h+var_88]
0x180082ad1  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x180082ad6  lea     rcx, [rbp+70h+var_78]
0x180082ada  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x180082adf  lea     rcx, [rbp+70h+var_60]
0x180082ae3  call    ??$WxHeapFree@_K@@YAXPEAPEA_K@Z; WxHeapFree<unsigned __int64>(unsigned __int64 * *)
0x180082ae8  lea     rcx, [rbp+70h+var_50]
0x180082aec  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x180082af1  xor     edx, edx; Val
0x180082af3  lea     rcx, [rsp+170h+var_100]; void *
0x180082af8  mov     r8d, 0C0h; Size
0x180082afe  call    memset_0
0x180082b03  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180082b0a  jz      short loc_180082B25
0x180082b0c  mov     edx, 22h ; '"'
0x180082b11  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x180082b18  mov     ecx, 40Ch
0x180082b1d  mov     r9d, edi
0x180082b20  call    WPP_SF_d
0x180082b25  mov     eax, edi
0x180082b27  mov     rcx, [rbp+70h+var_40]
0x180082b2b  xor     rcx, rsp; StackCookie
0x180082b2e  call    __security_check_cookie
0x180082b33  mov     rbx, [rsp+170h+arg_18]
0x180082b3b  add     rsp, 140h
0x180082b42  pop     r15
0x180082b44  pop     r14
0x180082b46  pop     r13
0x180082b48  pop     r12
0x180082b4a  pop     rdi
0x180082b4b  pop     rsi
0x180082b4c  pop     rbp
0x180082b4d  retn
0x180082b4e  xor     r12d, r12d
0x180082b51  lea     r15, [r14+8]
0x180082b55  mov     [rsi+8], r12
0x180082b59  test    r15, r15
0x180082b5c  jz      short loc_180082B6D
0x180082b5e  mov     rcx, r15; lpCriticalSection
0x180082b61  call    cs:__imp_EnterCriticalSection
0x180082b67  mov     r12d, 1
0x180082b6d  dec     dword ptr [r14+3Ch]
0x180082b71  mov     ecx, [r14+38h]
0x180082b75  mov     eax, ecx
0x180082b77  sub     eax, [r14+3Ch]
0x180082b7b  cmp     eax, [r14+40h]
0x180082b7f  ja      loc_180082CA5
0x180082b85  mov     rax, [r14+30h]
0x180082b89  mov     [rsi+8], rax
0x180082b8d  mov     [r14+30h], rsi
0x180082b91  test    r12d, r12d
0x180082b94  jz      loc_180082A95
0x180082b9a  test    r15, r15
0x180082b9d  jz      loc_180082A95
0x180082ba3  mov     rcx, r15; lpCriticalSection
0x180082ba6  call    cs:__imp_LeaveCriticalSection
0x180082bac  jmp     loc_180082A95
0x180082bb1  mov     edi, 80070002h
0x180082bb6  mov     [rsp+170h+var_124], 566h
0x180082bbe  mov     r15d, [rsp+170h+var_130]
0x180082bc3  jmp     loc_180082A43
0x180082bc8  mov     [rsp+170h+var_124], 562h
0x180082bd0  jmp     short loc_180082BBE
0x180082bd2  mov     rdx, [rsi+20h]; tableid
0x180082bd6  xor     r9d, r9d; grbit
0x180082bd9  mov     rcx, [rsi+10h]; sesid
0x180082bdd  mov     r8, rdi; szIndexName
0x180082be0  mov     dword ptr [rsi+30h], 0FFFFFFFFh
0x180082be7  call    cs:__imp_JetSetCurrentIndex2W
0x180082bed  mov     ecx, eax; int
0x180082bef  mov     edx, 1; int
0x180082bf4  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180082bf9  mov     edi, eax
0x180082bfb  test    eax, eax
0x180082bfd  js      loc_1800828F7
0x180082c03  mov     dword ptr [rsi+30h], 0
0x180082c0a  jmp     loc_1800828F7
0x180082c0f  mov     [rsp+170h+var_124], 569h
0x180082c17  jmp     short loc_180082BBE
0x180082c19  mov     [rsp+170h+var_124], 54Ah
0x180082c21  jmp     loc_180082A43
0x180082c26  mov     [rsp+170h+var_124], 56Eh
0x180082c2e  jmp     short loc_180082BBE
0x180082c30  mov     [rsp+170h+var_124], 0C33h
0x180082c38  jmp     loc_180082838
0x180082c3d  mov     [rsp+170h+var_124], 54Fh
0x180082c45  jmp     loc_180082A43
0x180082c4a  mov     [rsp+170h+var_124], 555h
0x180082c52  mov     r15d, esi
0x180082c55  jmp     loc_180082A43
0x180082c5a  mov     [rsp+170h+var_124], 55Bh
0x180082c62  jmp     loc_180082BBE
0x180082c67  mov     [rsp+170h+var_124], 55Ch
0x180082c6f  jmp     loc_180082BBE
0x180082c74  mov     [rsp+170h+var_124], 568h
0x180082c7c  jmp     loc_180082BBE
0x180082c81  mov     rsi, [rsp+170h+var_120]
0x180082c86  mov     edi, 80070020h
0x180082c8b  mov     [rsp+170h+var_124], 57Eh
0x180082c93  jmp     loc_180082A43
0x180082c98  mov     [rsp+170h+var_124], 584h
0x180082ca0  jmp     loc_180082A43
  ... truncated ...
```
