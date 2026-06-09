# DBIndexedRestrictionFilter::GetRowCount(TableHandleInfo *,ulong *)

- ea: `0x180003210`
- end: `0x180003417`
- name: `?GetRowCount@DBIndexedRestrictionFilter@@UEAAJPEAUTableHandleInfo@@PEAK@Z`
- size: `519`
- prototype: `int(DBIndexedRestrictionFilter *__hidden this, struct TableHandleInfo *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003210`
- `0x180003420`
- `0x180003518`
- `0x1800068f0`
- `0x18000f530`
- `0x180011ed0`
- `0x18002d548`
- `0x18006f180`
- `0x1800c6010`

## import_xrefs

- `ESENT!JetIndexRecordCount` at `0x18000330c`
- `ESENT!JetIndexRecordCount` at `0x18000330c`
- `ESENT!JetRollback` at `0x180003395`
- `ESENT!JetRollback` at `0x180003395`
- `ESENT!JetCommitTransaction2` at `0x180003364`
- `ESENT!JetCommitTransaction2` at `0x180003364`
- `ESENT!JetBeginTransaction2` at `0x18000325a`
- `ESENT!JetBeginTransaction2` at `0x18000325a`

## string_xrefs

- `0x180003335`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x18000334d`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x1800033ac`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall DBIndexedRestrictionFilter::GetRowCount(
        DBIndexedRestrictionFilter *this,
        struct TableHandleInfo *a2,
        unsigned int *a3)
{
  JET_SESID v6; // rdi
  int v7; // ebx
  int v8; // esi
  JET_ERR v9; // eax
  unsigned int HresultFromJetError; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // ebx
  int v15; // eax
  __int64 v16; // r8
  unsigned int v17; // ebp
  int v18; // eax
  JET_ERR v19; // ebp
  __int64 v20; // rcx
  int v21; // ebx
  JET_ERR v22; // eax
  unsigned int v23; // eax
  __int64 v24; // r9
  __int64 v25; // r9
  JET_SESID v26; // [rsp+30h] [rbp-58h] BYREF
  __int64 v27; // [rsp+38h] [rbp-50h]

  *a3 = 0;
  if ( (*((_DWORD *)this + 2) & 0x10000000) != 0 )
  {
    v13 = -2147024809;
    Log_UnistoreHREvent_1(2147942487LL, 0, a3, 2722);
    return v13;
  }
  v6 = *((_QWORD *)a2 + 1);
  v7 = 0;
  v26 = v6;
  v27 = 0;
  v8 = 0;
  v9 = JetBeginTransaction2(v6, 1u);
  if ( v9 )
  {
    if ( v9 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v9);
      v12 = 2726;
LABEL_5:
      v13 = HresultFromJetError;
      Log_UnistoreHREvent_1(HresultFromJetError, 0, v11, v12);
LABEL_6:
      auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v26);
      return v13;
    }
  }
  else
  {
    v7 = 1;
    v27 = 0x100000001LL;
    v8 = 1;
  }
  v15 = (*(__int64 (__fastcall **)(DBIndexedRestrictionFilter *, struct TableHandleInfo *))(*(_QWORD *)this + 56LL))(
          this,
          a2);
  v17 = v15;
  if ( v15 == -2147024871 )
    goto LABEL_21;
  if ( v15 < 0 )
  {
    v25 = 2732;
LABEL_29:
    Log_UnistoreHREvent_1(v17, 1, v16, v25);
    v13 = v17;
    goto LABEL_6;
  }
  v18 = (*(__int64 (__fastcall **)(DBIndexedRestrictionFilter *, struct TableHandleInfo *, _QWORD))(*(_QWORD *)this
                                                                                                  + 144LL))(
          this,
          a2,
          0);
  v17 = v18;
  if ( v18 == -2147024871 )
  {
LABEL_21:
    v13 = 0;
    goto LABEL_6;
  }
  if ( v18 < 0 )
  {
    v25 = 2737;
    goto LABEL_29;
  }
  v19 = JetIndexRecordCount(*((_QWORD *)a2 + 1), *((_QWORD *)a2 + 2), a3, 0);
  CheckCorruption(v19);
  if ( v19 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v19);
    v12 = 2744;
    goto LABEL_5;
  }
  if ( v7 )
  {
    if ( v8 )
    {
      if ( v6 == -1 )
        Log_AssertionEvent(v20, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h", 464);
      v21 = JetCommitTransaction2(v6, 0, 0, 0);
      if ( !v21 )
        return 0;
      auto_JET_TRANSACTION::Rollback((auto_JET_TRANSACTION *)&v26);
      if ( v21 >= 0 )
        return 0;
      v23 = MakeHresultFromJetError(v21);
      v24 = 431;
      goto LABEL_24;
    }
    v22 = JetRollback(v6, 0);
    if ( v22 < 0 )
    {
      v23 = MakeHresultFromJetError(v22);
      v24 = 435;
LABEL_24:
      Log_UnistoreHREvent_0(
        v23,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        v24);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003210  push    rbx
0x180003212  push    rbp
0x180003213  push    rsi
0x180003214  push    rdi
0x180003215  push    r12
0x180003217  push    r13
0x180003219  push    r14
0x18000321b  push    r15
0x18000321d  sub     rsp, 48h
0x180003221  mov     dword ptr [r8], 0
0x180003228  mov     r12, r8
0x18000322b  test    dword ptr [rcx+8], 10000000h
0x180003232  mov     r14, rdx
0x180003235  mov     r15, rcx
0x180003238  jnz     loc_1800033BE
0x18000323e  mov     rdi, [rdx+8]
0x180003242  xor     ebx, ebx
0x180003244  mov     rcx, rdi; sesid
0x180003247  mov     [rsp+88h+var_58], rdi
0x18000324c  mov     [rsp+88h+var_50], rbx
0x180003251  xor     esi, esi
0x180003253  lea     r13d, [rbx+1]
0x180003257  mov     edx, r13d; grbit
0x18000325a  call    cs:__imp_JetBeginTransaction2
0x180003260  test    eax, eax
0x180003262  jz      short loc_18000329B
0x180003264  jns     short loc_1800032AA
0x180003266  mov     ecx, eax; int
0x180003268  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000326d  mov     r9d, 0AA6h
0x180003273  xor     edx, edx
0x180003275  mov     ecx, eax
0x180003277  mov     ebx, eax
0x180003279  call    Log_UnistoreHREvent_1
0x18000327e  lea     rcx, [rsp+88h+var_58]; this
0x180003283  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x180003288  mov     eax, ebx
0x18000328a  add     rsp, 48h
0x18000328e  pop     r15
0x180003290  pop     r14
0x180003292  pop     r13
0x180003294  pop     r12
0x180003296  pop     rdi
0x180003297  pop     rsi
0x180003298  pop     rbp
0x180003299  pop     rbx
0x18000329a  retn
0x18000329b  mov     ebx, r13d
0x18000329e  mov     dword ptr [rsp+88h+var_50+4], r13d
0x1800032a3  mov     dword ptr [rsp+88h+var_50], ebx
0x1800032a7  mov     esi, r13d
0x1800032aa  mov     rax, [r15]
0x1800032ad  mov     rdx, r14
0x1800032b0  mov     rcx, r15
0x1800032b3  mov     rax, [rax+38h]
0x1800032b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032bc  mov     ebp, eax
0x1800032be  cmp     eax, 80070019h
0x1800032c3  jz      loc_180003389
0x1800032c9  test    eax, eax
0x1800032cb  js      loc_1800033E9
0x1800032d1  mov     rax, [r15]
0x1800032d4  xor     r8d, r8d
0x1800032d7  mov     rdx, r14
0x1800032da  mov     rcx, r15
0x1800032dd  mov     rax, [rax+90h]
0x1800032e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e9  mov     ebp, eax
0x1800032eb  cmp     eax, 80070019h
0x1800032f0  jz      loc_180003389
0x1800032f6  test    eax, eax
0x1800032f8  js      loc_1800033F1
0x1800032fe  mov     rdx, [r14+10h]; tableid
0x180003302  xor     r9d, r9d; crecMax
0x180003305  mov     rcx, [r14+8]; sesid
0x180003309  mov     r8, r12; pcrec
0x18000330c  call    cs:__imp_JetIndexRecordCount
0x180003312  mov     ecx, eax; int
0x180003314  mov     ebp, eax
0x180003316  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x18000331b  test    ebp, ebp
0x18000331d  js      loc_1800033D7
0x180003323  test    ebx, ebx
0x180003325  jz      short loc_180003382
0x180003327  test    esi, esi
0x180003329  jz      short loc_180003390
0x18000332b  test    ebx, ebx
0x18000332d  jnz     short loc_180003341
0x18000332f  mov     r8d, 1CFh
0x180003335  lea     rdx, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x18000333c  call    Log_AssertionEvent
0x180003341  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180003345  jnz     short loc_180003359
0x180003347  mov     r8d, 1D0h
0x18000334d  lea     rdx, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180003354  call    Log_AssertionEvent
0x180003359  xor     r9d, r9d
0x18000335c  xor     r8d, r8d
0x18000335f  xor     edx, edx
0x180003361  mov     rcx, rdi
0x180003364  call    cs:__imp_JetCommitTransaction2
0x18000336a  mov     ebx, eax
0x18000336c  test    eax, eax
0x18000336e  jz      short loc_180003382
0x180003370  lea     rcx, [rsp+88h+var_58]; this
0x180003375  call    ?Rollback@auto_JET_TRANSACTION@@QEAAXXZ; auto_JET_TRANSACTION::Rollback(void)
0x18000337a  test    ebx, ebx
0x18000337c  js      loc_180003408
0x180003382  xor     eax, eax
0x180003384  jmp     loc_18000328A
0x180003389  xor     ebx, ebx
0x18000338b  jmp     loc_18000327E
0x180003390  xor     edx, edx; grbit
0x180003392  mov     rcx, rdi; sesid
0x180003395  call    cs:__imp_JetRollback
0x18000339b  test    eax, eax
0x18000339d  jns     short loc_180003382
0x18000339f  mov     ecx, eax; int
0x1800033a1  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800033a6  mov     r9d, 1B3h
0x1800033ac  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800033b3  xor     edx, edx
0x1800033b5  mov     ecx, eax
0x1800033b7  call    Log_UnistoreHREvent_0
0x1800033bc  jmp     short loc_180003382
0x1800033be  mov     ebx, 80070057h
0x1800033c3  xor     edx, edx
0x1800033c5  mov     ecx, ebx
0x1800033c7  mov     r9d, 0AA2h
0x1800033cd  call    Log_UnistoreHREvent_1
0x1800033d2  jmp     loc_180003288
0x1800033d7  mov     ecx, ebp; int
0x1800033d9  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800033de  mov     r9d, 0AB8h
0x1800033e4  jmp     loc_180003273
0x1800033e9  mov     r9d, 0AACh
0x1800033ef  jmp     short loc_1800033F7
0x1800033f1  mov     r9d, 0AB1h
0x1800033f7  mov     edx, r13d
0x1800033fa  mov     ecx, ebp
0x1800033fc  call    Log_UnistoreHREvent_1
0x180003401  mov     ebx, ebp
0x180003403  jmp     loc_18000327E
0x180003408  mov     ecx, ebx; int
0x18000340a  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000340f  mov     r9d, 1AFh
0x180003415  jmp     short loc_1800033AC
```
