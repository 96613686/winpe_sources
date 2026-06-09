# CCacheContainer::UnlockUrl(ushort const *)

- ea: `0x180023044`
- end: `0x18002350d`
- name: `?UnlockUrl@CCacheContainer@@QEAAJPEBG@Z`
- size: `1225`
- prototype: `__int64 __fastcall(CCacheContainer *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040ed0`

## callees

- `0x180020fc4`
- `0x180021360`
- `0x180023044`
- `0x180023590`
- `0x18007e620`
- `0x18007ec9c`
- `0x180081eb0`
- `0x180082700`
- `0x180083540`
- `0x1800838d8`
- `0x180083d00`
- `0x180083dc4`
- `0x180085460`
- `0x180085898`
- `0x180086aa4`
- `0x1800b4614`
- `0x1800b4f00`
- `0x1800b5bdc`
- `0x1800fc68c`
- `0x1800ffb10`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e0660`
- `0x1801e1790`
- `0x1801e1d20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800233a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800233a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023368`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023368`
- `ESENT!JetDelete` at `0x180023421`
- `ESENT!JetDelete` at `0x180023421`
- `ESENT!JetCommitTransaction` at `0x180023445`
- `ESENT!JetCommitTransaction` at `0x180023445`
- `ESENT!JetRollback` at `0x180023261`
- `ESENT!JetRollback` at `0x180023261`
- `ESENT!JetBeginTransaction` at `0x18002317d`
- `ESENT!JetBeginTransaction` at `0x18002317d`

## pseudocode

```c
__int64 __fastcall CCacheContainer::UnlockUrl(CCacheContainer *this, const unsigned __int16 *a2)
{
  CJetContext *v2; // rdi
  int v5; // r15d
  int v6; // r8d
  int v7; // ecx
  signed int updated; // ebx
  __int64 v9; // rdx
  unsigned __int64 v10; // rsi
  int v11; // eax
  unsigned int v12; // r9d
  JET_ERR v13; // eax
  int v14; // eax
  __int64 v15; // rsi
  int v17; // r15d
  JET_ERR v18; // eax
  JET_ERR v19; // eax
  unsigned int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh]
  CJetContext *v22; // [rsp+38h] [rbp-C8h] BYREF
  struct CInFlightEntry *v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+4Ch] [rbp-B4h]
  CClientLocks *v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v26[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v29[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[12]; // [rsp+88h] [rbp-78h] BYREF
  int v31; // [rsp+94h] [rbp-6Ch]
  _BYTE v32[16]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v33[24]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v34[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v35[16]; // [rsp+110h] [rbp+10h] BYREF

  v2 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v25 = 0;
  v20 = 0;
  v5 = 0;
  memset_0(v26, 0, 0xC0u);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qS(1036, 35, (unsigned int)WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (_DWORD)this, (__int64)a2);
  v7 = *((_DWORD *)this + 8) & 5;
  v24 = 0;
  if ( v7 != 5 )
    v24 = 3123;
  updated = v7 != 5 ? 0x80070005 : 0;
  if ( v7 == 5 )
  {
    updated = CContainerProps::UpdateLastAccessTime(*((CContainerProps **)this + 5));
    if ( updated < 0 )
    {
      v21 = 1459;
    }
    else
    {
      v10 = WxComputeUrlHash(a2, v9);
      updated = CInFlightLocks::AcquireLock(*(CInFlightLocks **)(*((_QWORD *)this + 5) + 144LL), v10, &v23);
      if ( updated < 0 )
      {
        v21 = 1462;
      }
      else
      {
        v11 = CJetContextList::AcquireContext(*(CJetContextList **)(*((_QWORD *)this + 5) + 152LL), &v22, 0);
        v2 = v22;
        updated = v11;
        if ( v11 < 0 )
        {
          v21 = 1468;
        }
        else
        {
          updated = CJetContext::SetCurrentIndex(v22, 0, L"HashEntryIdIndex", v12);
          if ( updated < 0 )
          {
            v21 = 1469;
          }
          else
          {
            v13 = JetBeginTransaction(*((_QWORD *)v2 + 2));
            updated = HRESULTFromJET_ERR(v13, 1);
            if ( updated >= 0 )
            {
              v5 = 1;
              v14 = SeekToEntry(v2, a2, v10);
              updated = v14;
              if ( v14 < 0 )
              {
                v21 = 1478;
              }
              else if ( v14 )
              {
                updated = -2147024894;
                v21 = 1482;
              }
              else
              {
                updated = GetEntryFixedInfoAtCursor(
                            *((_QWORD *)v2 + 2),
                            *((_QWORD *)v2 + 4),
                            *(unsigned int **)(*((_QWORD *)v2 + 5) + 8LL),
                            (struct ENTRY_INFO *)v26);
                if ( updated < 0 )
                {
                  v21 = 1487;
                }
                else
                {
                  updated = CCacheContainer::GetClientLocks(this, &v25);
                  if ( updated < 0 )
                  {
                    v21 = 1489;
                  }
                  else
                  {
                    updated = CClientLocks::UnlockEntry(v25, v26[0], &v20);
                    if ( updated < 0 )
                    {
                      v21 = 1490;
                    }
                    else if ( !v20 && (v31 & 0x400000) != 0 )
                    {
                      updated = GetEntryFilenameGroupInfoAtCursor(
                                  *((_QWORD *)v2 + 2),
                                  *((_QWORD *)v2 + 4),
                                  *(unsigned int **)(*((_QWORD *)v2 + 5) + 8LL),
                                  (struct ENTRY_INFO *)v26);
                      if ( updated < 0 )
                      {
                        v21 = 1511;
                      }
                      else
                      {
                        v18 = JetDelete(*((_QWORD *)v2 + 2), *((_QWORD *)v2 + 4));
                        updated = HRESULTFromJET_ERR(v18, 1);
                        if ( updated >= 0 )
                        {
                          v19 = JetCommitTransaction(*((_QWORD *)v2 + 2), 1u);
                          updated = HRESULTFromJET_ERR(v19, 1);
                          if ( updated >= 0 )
                          {
                            v5 = 0;
                            CContainerProps::ReleaseEntryContext(*((CContainerProps **)this + 5), &v22);
                            updated = CContainerProps::DeleteEntryFile(
                                        *((CContainerProps **)this + 5),
                                        (struct ENTRY_INFO *)v26,
                                        1,
                                        1,
                                        1,
                                        0);
                            if ( updated < 0 )
                              v21 = 1530;
                            v2 = v22;
                          }
                        }
                      }
                    }
                    else
                    {
                      updated = 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v21 = 1454;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_ISD(v7, 36, v6, *((_QWORD *)this + 3), (__int64)a2, updated);
  if ( v5 )
    JetRollback(*((_QWORD *)v2 + 2), 0);
  v15 = *(_QWORD *)(*((_QWORD *)this + 5) + 152LL);
  if ( v2 )
  {
    CCacheStore::EndActivity(*(CCacheStore **)(v15 + 80));
    v17 = 0;
    *((_QWORD *)v2 + 1) = 0;
    if ( v15 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
      v17 = 1;
    }
    --*(_DWORD *)(v15 + 60);
    if ( (unsigned int)(*(_DWORD *)(v15 + 56) - *(_DWORD *)(v15 + 60)) > *(_DWORD *)(v15 + 64) )
    {
      --*(_DWORD *)(v15 + 56);
      CJetContext::Release(v2);
    }
    else
    {
      *((_QWORD *)v2 + 1) = *(_QWORD *)(v15 + 48);
      *(_QWORD *)(v15 + 48) = v2;
    }
    if ( v17 && v15 != -8 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
  }
  CInFlightLocks::ReleaseLock(*(CInFlightLocks **)(*((_QWORD *)this + 5) + 144LL), &v23);
  WxHeapFree<_WX_AVL_TABLE>(v27);
  WxHeapFree<_WX_AVL_TABLE>(v28);
  WxHeapFree<_WX_AVL_TABLE>(v29);
  WxHeapFree<_WX_AVL_TABLE>(v30);
  WxHeapFree<_WX_AVL_TABLE>(v32);
  WxHeapFree<_WX_AVL_TABLE>(v33);
  WxHeapFree<unsigned __int64>(v34);
  WxHeapFree<_WX_AVL_TABLE>(v35);
  memset_0(v26, 0, 0xC0u);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 37, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (unsigned int)updated);
  if ( v25 )
    CClientLocks::Release(v25);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180023044  mov     [rsp-8+arg_10], rbx
0x180023049  mov     [rsp-8+arg_18], rsi
0x18002304e  push    rbp
0x18002304f  push    rdi
0x180023050  push    r13
0x180023052  push    r14
0x180023054  push    r15
0x180023056  lea     rbp, [rsp-30h]
0x18002305b  sub     rsp, 130h
0x180023062  mov     rax, cs:__security_cookie
0x180023069  xor     rax, rsp
0x18002306c  mov     [rbp+50h+var_30], rax
0x180023070  xor     edi, edi
0x180023072  mov     [rsp+150h+var_11C], 0
0x18002307a  mov     r14, rdx
0x18002307d  mov     [rsp+150h+var_118], rdi
0x180023082  mov     r13, rcx
0x180023085  mov     [rsp+150h+var_110], rdi
0x18002308a  xor     edx, edx; Val
0x18002308c  mov     [rsp+150h+var_100], rdi
0x180023091  lea     rcx, [rsp+150h+var_F0]; void *
0x180023096  mov     [rsp+150h+var_120], edi
0x18002309a  xor     r15d, r15d
0x18002309d  mov     r8d, 0C0h; Size
0x1800230a3  call    memset_0
0x1800230a8  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800230af  jz      short loc_1800230CD
0x1800230b1  lea     edx, [rdi+23h]
0x1800230b4  mov     qword ptr [rsp+150h+var_130], r14
0x1800230b9  mov     ecx, 40Ch
0x1800230be  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x1800230c5  mov     r9, r13
0x1800230c8  call    WPP_SF_qS
0x1800230cd  mov     ecx, [r13+20h]
0x1800230d1  and     ecx, 5
0x1800230d4  mov     [rsp+150h+var_104], edi
0x1800230d8  cmp     ecx, 5
0x1800230db  jnz     loc_18002349D
0x1800230e1  lea     eax, [rcx-5]
0x1800230e4  neg     eax
0x1800230e6  sbb     ebx, ebx
0x1800230e8  and     ebx, 80070005h
0x1800230ee  cmp     ecx, 5
0x1800230f1  jnz     loc_1800233B4
0x1800230f7  mov     rcx, [r13+28h]; this
0x1800230fb  call    ?UpdateLastAccessTime@CContainerProps@@QEAAJXZ; CContainerProps::UpdateLastAccessTime(void)
0x180023100  mov     ebx, eax
0x180023102  test    eax, eax
0x180023104  js      loc_1800234AA
0x18002310a  mov     rcx, r14
0x18002310d  call    WxComputeUrlHash
0x180023112  mov     rcx, [r13+28h]
0x180023116  lea     r8, [rsp+150h+var_110]; struct CInFlightEntry **
0x18002311b  mov     rdx, rax; unsigned __int64
0x18002311e  mov     rsi, rax
0x180023121  mov     rcx, [rcx+90h]; this
0x180023128  call    ?AcquireLock@CInFlightLocks@@QEAAJ_KPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::AcquireLock(unsigned __int64,CInFlightEntry * *)
0x18002312d  mov     ebx, eax
0x18002312f  test    eax, eax
0x180023131  js      loc_18002322E
0x180023137  mov     rcx, [r13+28h]
0x18002313b  lea     rdx, [rsp+150h+var_118]; struct CJetContext **
0x180023140  xor     r8d, r8d; int *
0x180023143  mov     rcx, [rcx+98h]; this
0x18002314a  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x18002314f  mov     rdi, [rsp+150h+var_118]
0x180023154  mov     ebx, eax
0x180023156  test    eax, eax
0x180023158  js      loc_1800234B7
0x18002315e  lea     r8, aHashentryidind; "HashEntryIdIndex"
0x180023165  xor     edx, edx; unsigned int
0x180023167  mov     rcx, rdi; this
0x18002316a  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x18002316f  mov     ebx, eax
0x180023171  test    eax, eax
0x180023173  js      loc_1800234C4
0x180023179  mov     rcx, [rdi+10h]; sesid
0x18002317d  call    cs:__imp_JetBeginTransaction
0x180023183  mov     ecx, eax; int
0x180023185  mov     edx, 1; int
0x18002318a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18002318f  mov     ebx, eax
0x180023191  test    eax, eax
0x180023193  js      loc_180023236
0x180023199  mov     r8, rsi; unsigned __int64
0x18002319c  mov     rdx, r14; unsigned __int16 *
0x18002319f  mov     rcx, rdi; struct CJetContext *
0x1800231a2  mov     r15d, 1
0x1800231a8  call    ?SeekToEntry@@YAJPEAVCJetContext@@PEBG_K@Z; SeekToEntry(CJetContext *,ushort const *,unsigned __int64)
0x1800231ad  mov     ebx, eax
0x1800231af  test    eax, eax
0x1800231b1  js      loc_1800233CE
0x1800231b7  jnz     loc_1800234D1
0x1800231bd  mov     r8, [rdi+28h]
0x1800231c1  lea     r9, [rsp+150h+var_F0]; struct ENTRY_INFO *
0x1800231c6  mov     rdx, [rdi+20h]; unsigned __int64
0x1800231ca  mov     rcx, [rdi+10h]; unsigned __int64
0x1800231ce  mov     r8, [r8+8]; unsigned int *
0x1800231d2  call    ?GetEntryFixedInfoAtCursor@@YAJ_K0PEAKPEAUENTRY_INFO@@@Z; GetEntryFixedInfoAtCursor(unsigned __int64,unsigned __int64,ulong *,ENTRY_INFO *)
0x1800231d7  mov     ebx, eax
0x1800231d9  test    eax, eax
0x1800231db  js      loc_1800233E8
0x1800231e1  lea     rdx, [rsp+150h+var_100]; struct CClientLocks **
0x1800231e6  mov     rcx, r13; this
0x1800231e9  call    ?GetClientLocks@CCacheContainer@@AEAAJPEAPEAVCClientLocks@@@Z; CCacheContainer::GetClientLocks(CClientLocks * *)
0x1800231ee  mov     ebx, eax
0x1800231f0  test    eax, eax
0x1800231f2  js      loc_1800233DB
0x1800231f8  mov     rdx, [rsp+150h+var_F0]; unsigned __int64
0x1800231fd  lea     r8, [rsp+150h+var_120]; unsigned int *
0x180023202  mov     rcx, [rsp+150h+var_100]; this
0x180023207  call    ?UnlockEntry@CClientLocks@@QEAAJ_KPEAK@Z; CClientLocks::UnlockEntry(unsigned __int64,ulong *)
0x18002320c  mov     ebx, eax
0x18002320e  test    eax, eax
0x180023210  js      loc_1800233C1
0x180023216  cmp     [rsp+150h+var_120], 0
0x18002321b  jnz     short loc_18002322A
0x18002321d  test    [rbp+50h+var_BC], 400000h
0x180023224  jnz     loc_1800233F5
0x18002322a  xor     ebx, ebx
0x18002322c  jmp     short loc_180023236
0x18002322e  mov     [rsp+150h+var_11C], 5B6h
0x180023236  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18002323d  jz      short loc_180023256
0x18002323f  mov     r9, [r13+18h]
0x180023243  mov     edx, 24h ; '$'
0x180023248  mov     [rsp+150h+var_128], ebx
0x18002324c  mov     qword ptr [rsp+150h+var_130], r14
0x180023251  call    WPP_SF_ISD
0x180023256  test    r15d, r15d
0x180023259  jz      short loc_180023267
0x18002325b  mov     rcx, [rdi+10h]; sesid
0x18002325f  xor     edx, edx; grbit
0x180023261  call    cs:__imp_JetRollback
0x180023267  mov     rax, [r13+28h]
0x18002326b  mov     rsi, [rax+98h]
0x180023272  test    rdi, rdi
0x180023275  jz      short loc_180023289
0x180023277  mov     rcx, [rsi+50h]; this
0x18002327b  call    ?EndActivity@CCacheStore@@QEAAXXZ; CCacheStore::EndActivity(void)
0x180023280  test    rdi, rdi
0x180023283  jnz     loc_180023355
0x180023289  mov     rcx, [r13+28h]
0x18002328d  lea     rdx, [rsp+150h+var_110]; struct CInFlightEntry **
0x180023292  mov     rcx, [rcx+90h]; this
0x180023299  call    ?ReleaseLock@CInFlightLocks@@QEAAXPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::ReleaseLock(CInFlightEntry * *)
0x18002329e  lea     rcx, [rsp+150h+var_E0]
0x1800232a3  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1800232a8  lea     rcx, [rsp+150h+var_D8]
0x1800232ad  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1800232b2  lea     rcx, [rbp+50h+var_D0]
0x1800232b6  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1800232bb  lea     rcx, [rbp+50h+var_C8]
0x1800232bf  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1800232c4  lea     rcx, [rbp+50h+var_78]
0x1800232c8  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1800232cd  lea     rcx, [rbp+50h+var_68]
0x1800232d1  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1800232d6  lea     rcx, [rbp+50h+var_50]
0x1800232da  call    ??$WxHeapFree@_K@@YAXPEAPEA_K@Z; WxHeapFree<unsigned __int64>(unsigned __int64 * *)
0x1800232df  lea     rcx, [rbp+50h+var_40]
0x1800232e3  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1800232e8  xor     edx, edx; Val
0x1800232ea  lea     rcx, [rsp+150h+var_F0]; void *
0x1800232ef  mov     r8d, 0C0h; Size
0x1800232f5  call    memset_0
0x1800232fa  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180023301  jz      short loc_18002331C
0x180023303  mov     edx, 25h ; '%'
0x180023308  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x18002330f  mov     ecx, 40Ch
0x180023314  mov     r9d, ebx
0x180023317  call    WPP_SF_d
0x18002331c  mov     rcx, [rsp+150h+var_100]; this
0x180023321  test    rcx, rcx
0x180023324  jz      short loc_18002332B
0x180023326  call    ?Release@CClientLocks@@QEAAKXZ; CClientLocks::Release(void)
0x18002332b  mov     eax, ebx
0x18002332d  mov     rcx, [rbp+50h+var_30]
0x180023331  xor     rcx, rsp; StackCookie
0x180023334  call    __security_check_cookie
0x180023339  lea     r11, [rsp+150h+var_20]
0x180023341  mov     rbx, [r11+40h]
0x180023345  mov     rsi, [r11+48h]
0x180023349  mov     rsp, r11
0x18002334c  pop     r15
0x18002334e  pop     r14
0x180023350  pop     r13
0x180023352  pop     rdi
0x180023353  pop     rbp
0x180023354  retn
0x180023355  xor     r15d, r15d
0x180023358  lea     r14, [rsi+8]
0x18002335c  mov     [rdi+8], r15
0x180023360  test    r14, r14
0x180023363  jz      short loc_180023374
0x180023365  mov     rcx, r14; lpCriticalSection
0x180023368  call    cs:__imp_EnterCriticalSection
0x18002336e  mov     r15d, 1
0x180023374  dec     dword ptr [rsi+3Ch]
0x180023377  mov     ecx, [rsi+38h]
0x18002337a  mov     eax, ecx
0x18002337c  sub     eax, [rsi+3Ch]
0x18002337f  cmp     eax, [rsi+40h]
0x180023382  ja      loc_1800234FA
0x180023388  mov     rax, [rsi+30h]
0x18002338c  mov     [rdi+8], rax
0x180023390  mov     [rsi+30h], rdi
0x180023394  test    r15d, r15d
0x180023397  jz      loc_180023289
0x18002339d  test    r14, r14
0x1800233a0  jz      loc_180023289
0x1800233a6  mov     rcx, r14; lpCriticalSection
0x1800233a9  call    cs:__imp_LeaveCriticalSection
0x1800233af  jmp     loc_180023289
0x1800233b4  mov     [rsp+150h+var_11C], 5AEh
0x1800233bc  jmp     loc_180023236
0x1800233c1  mov     [rsp+150h+var_11C], 5D2h
0x1800233c9  jmp     loc_180023236
0x1800233ce  mov     [rsp+150h+var_11C], 5C6h
0x1800233d6  jmp     loc_180023236
0x1800233db  mov     [rsp+150h+var_11C], 5D1h
0x1800233e3  jmp     loc_180023236
0x1800233e8  mov     [rsp+150h+var_11C], 5CFh
0x1800233f0  jmp     loc_180023236
0x1800233f5  mov     r8, [rdi+28h]
0x1800233f9  lea     r9, [rsp+150h+var_F0]; struct ENTRY_INFO *
0x1800233fe  mov     rdx, [rdi+20h]; unsigned __int64
0x180023402  mov     rcx, [rdi+10h]; sesid
0x180023406  mov     r8, [r8+8]; unsigned int *
0x18002340a  call    ?GetEntryFilenameGroupInfoAtCursor@@YAJ_K0PEAKPEAUENTRY_INFO@@@Z; GetEntryFilenameGroupInfoAtCursor(unsigned __int64,unsigned __int64,ulong *,ENTRY_INFO *)
0x18002340f  mov     ebx, eax
0x180023411  test    eax, eax
0x180023413  js      loc_1800234E3
0x180023419  mov     rdx, [rdi+20h]; tableid
0x18002341d  mov     rcx, [rdi+10h]; sesid
0x180023421  call    cs:__imp_JetDelete
0x180023427  mov     edx, r15d; int
0x18002342a  mov     esi, r15d
0x18002342d  mov     ecx, eax; int
0x18002342f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180023434  mov     ebx, eax
0x180023436  test    eax, eax
0x180023438  js      loc_180023236
0x18002343e  mov     rcx, [rdi+10h]; sesid
0x180023442  mov     edx, r15d; grbit
0x180023445  call    cs:__imp_JetCommitTransaction
0x18002344b  mov     ecx, eax; int
0x18002344d  mov     edx, r15d; int
0x180023450  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180023455  mov     ebx, eax
0x180023457  test    eax, eax
0x180023459  js      loc_180023236
0x18002345f  mov     rcx, [r13+28h]; this
0x180023463  lea     rdx, [rsp+150h+var_118]; struct CJetContext **
0x180023468  xor     r15d, r15d
0x18002346b  call    ?ReleaseEntryContext@CContainerProps@@QEAAXPEAPEAVCJetContext@@@Z; CContainerProps::ReleaseEntryContext(CJetContext * *)
0x180023470  mov     rcx, [r13+28h]; this
0x180023474  lea     rdx, [rsp+150h+var_F0]; struct ENTRY_INFO *
0x180023479  mov     r9d, esi; int
0x18002347c  mov     [rsp+150h+var_128], r15d; int
0x180023481  mov     r8d, esi; int
0x180023484  mov     [rsp+150h+var_130], esi; int
0x180023488  call    ?DeleteEntryFile@CContainerProps@@QEAAJPEAUENTRY_INFO@@HHHH@Z; CContainerProps::DeleteEntryFile(ENTRY_INFO *,int,int,int,int)
0x18002348d  mov     ebx, eax
0x18002348f  test    eax, eax
0x180023491  js      short loc_1800234F0
0x180023493  mov     rdi, [rsp+150h+var_118]
0x180023498  jmp     loc_180023236
0x18002349d  mov     [rsp+150h+var_104], 0C33h
0x1800234a5  jmp     loc_1800230E1
0x1800234aa  mov     [rsp+150h+var_11C], 5B3h
0x1800234b2  jmp     loc_180023236
0x1800234b7  mov     [rsp+150h+var_11C], 5BCh
0x1800234bf  jmp     loc_180023236
0x1800234c4  mov     [rsp+150h+var_11C], 5BDh
0x1800234cc  jmp     loc_180023236
0x1800234d1  mov     ebx, 80070002h
0x1800234d6  mov     [rsp+150h+var_11C], 5CAh
0x1800234de  jmp     loc_180023236
0x1800234e3  mov     [rsp+150h+var_11C], 5E7h
0x1800234eb  jmp     loc_180023236
0x1800234f0  mov     [rsp+150h+var_11C], 5FAh
0x1800234f8  jmp     short loc_180023493
0x1800234fa  lea     eax, [rcx-1]
0x1800234fd  mov     rcx, rdi; this
0x180023500  mov     [rsi+38h], eax
0x180023503  call    ?Release@CJetContext@@QEAAKXZ; CJetContext::Release(void)
0x180023508  jmp     loc_180023394
```
