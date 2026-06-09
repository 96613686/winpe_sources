# CAppCache::UpdateExtraData(ushort const *,CCacheContainer *,uchar const *,ulong)

- ea: `0x1801c30d8`
- end: `0x1801c33df`
- name: `?UpdateExtraData@CAppCache@@QEAAJPEBGPEAVCCacheContainer@@PEBEK@Z`
- size: `775`
- prototype: `__int64 __fastcall(CAppCache *__hidden this, const unsigned __int16 *, struct CCacheContainer *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801bdfa0`

## callees

- `0x180021360`
- `0x18007ec9c`
- `0x180082cc0`
- `0x180083dc4`
- `0x1800861f8`
- `0x1800eee94`
- `0x1800f05dc`
- `0x1800f0640`
- `0x1800fa80c`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801c298c`
- `0x1801c30d8`
- `0x1801c570c`
- `0x1801e1790`
- `0x1801e971c`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x1801c3371`
- `ESENT!JetCommitTransaction` at `0x1801c3371`
- `ESENT!JetUpdate` at `0x1801c3349`
- `ESENT!JetUpdate` at `0x1801c3349`
- `ESENT!JetPrepareUpdate` at `0x1801c32da`
- `ESENT!JetPrepareUpdate` at `0x1801c3327`
- `ESENT!JetPrepareUpdate` at `0x1801c32da`
- `ESENT!JetPrepareUpdate` at `0x1801c3327`
- `ESENT!JetRollback` at `0x1801c323c`
- `ESENT!JetRollback` at `0x1801c3394`
- `ESENT!JetRollback` at `0x1801c323c`
- `ESENT!JetRollback` at `0x1801c3394`
- `ESENT!JetBeginTransaction` at `0x1801c31ff`
- `ESENT!JetBeginTransaction` at `0x1801c31ff`

## string_xrefs

- `0x1801c31d8`: `AppCacheIdIndex`

## pseudocode

```c
__int64 __fastcall CAppCache::UpdateExtraData(
        CFileListMap **this,
        const unsigned __int16 *a2,
        struct CCacheContainer *a3,
        const unsigned __int8 *a4,
        unsigned int a5)
{
  int v9; // ecx
  int Entry; // eax
  int updated; // ebx
  int v12; // eax
  unsigned int v13; // r9d
  JET_SESID *v14; // rdi
  JET_ERR v15; // eax
  int v16; // eax
  JET_SESID v18; // rcx
  JET_ERR v19; // eax
  JET_ERR v20; // eax
  JET_ERR v21; // eax
  JET_ERR v22; // eax
  char *v23; // [rsp+48h] [rbp-69h] BYREF
  __int64 v24; // [rsp+50h] [rbp-61h]
  struct CJetContext *v25; // [rsp+58h] [rbp-59h] BYREF
  _BYTE v26[52]; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v27; // [rsp+94h] [rbp-1Dh]
  const unsigned __int8 *v28; // [rsp+A8h] [rbp-9h]

  v23 = (char *)(this + 16);
  v24 = 0;
  v25 = 0;
  memset_0(v26, 0, 0x50u);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qSqqd(
      v9,
      73,
      (unsigned int)WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids,
      (_DWORD)this,
      (__int64)a2,
      (__int64)a3,
      (__int64)a4,
      a5);
  AutoSrw::LockShared((AutoSrw *)&v23);
  Entry = CFileListMap::FindEntry(this[5], a2, 0);
  updated = Entry;
  if ( Entry >= 0 )
  {
    if ( !Entry )
    {
      updated = -2147024894;
      goto LABEL_13;
    }
    v12 = CJetContextList::AcquireContext(*((CJetContextList **)this[19] + 2), &v25, 0);
    v14 = (JET_SESID *)v25;
    updated = v12;
    if ( v12 < 0 )
      goto LABEL_11;
    updated = CJetContext::SetCurrentIndex(v25, 1u, L"AppCacheIdIndex", v13);
    if ( updated < 0 )
      goto LABEL_11;
    v15 = JetBeginTransaction(v14[2]);
    updated = HRESULTFromJET_ERR(v15, 1);
    if ( updated < 0 )
      goto LABEL_11;
    v16 = CAppCache::SeekToAppCacheUrl((CAppCache *)this, (struct CJetContext *)v14, a2);
    updated = v16;
    if ( v16 < 0 )
      goto LABEL_10;
    v18 = v14[2];
    if ( v16 )
    {
      v22 = JetRollback(v18, 0);
      updated = HRESULTFromJET_ERR(v22, 1);
      if ( updated < 0 )
        goto LABEL_10;
      v28 = a4;
      v27 = a5;
      updated = CCacheContainer::UpdateUrl(a3, a2, (const struct _URLCACHE_UPDATE_DATA *)v26, 0x80u);
      if ( updated < 0 )
      {
LABEL_11:
        if ( v14 )
          CJetContextList::ReleaseContext(*((CJetContextList **)this[19] + 2), &v25);
        goto LABEL_13;
      }
    }
    else
    {
      v19 = JetPrepareUpdate(v18, v14[4], 2u);
      updated = HRESULTFromJET_ERR(v19, 1);
      if ( updated < 0 )
      {
LABEL_10:
        JetRollback(v14[2], 0);
        goto LABEL_11;
      }
      updated = CJetContext::SetBinaryColumn((CJetContext *)v14, 0xEu, a4, a5);
      if ( updated < 0 )
      {
LABEL_23:
        JetPrepareUpdate(v14[2], v14[4], 3u);
        goto LABEL_10;
      }
      v20 = JetUpdate(v14[2], v14[4], 0, 0, 0);
      if ( v20 == -1102 )
      {
        updated = 0;
        goto LABEL_23;
      }
      updated = HRESULTFromJET_ERR(v20, 1);
      if ( updated < 0 )
        goto LABEL_23;
      v21 = JetCommitTransaction(v14[2], 1u);
      updated = HRESULTFromJET_ERR(v21, 1);
      if ( updated < 0 )
        goto LABEL_10;
    }
    updated = 0;
    goto LABEL_11;
  }
LABEL_13:
  AutoSrw::UnlockShared((AutoSrw *)&v23);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 74, WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids, (unsigned int)updated);
  if ( (_DWORD)v24 )
    AutoSrw::UnlockShared((AutoSrw *)&v23);
  if ( HIDWORD(v24) )
    AutoSrw::UnlockExclusive((AutoSrw *)&v23);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1801c30d8  push    rbp
0x1801c30da  push    rbx
0x1801c30db  push    rsi
0x1801c30dc  push    rdi
0x1801c30dd  push    r12
0x1801c30df  push    r13
0x1801c30e1  push    r14
0x1801c30e3  push    r15
0x1801c30e5  lea     rbp, [rsp-17h]
0x1801c30ea  sub     rsp, 0C8h
0x1801c30f1  mov     rax, cs:__security_cookie
0x1801c30f8  xor     rax, rsp
0x1801c30fb  mov     [rbp+4Fh+var_50], rax
0x1801c30ff  lea     rax, [rcx+80h]
0x1801c3106  mov     [rbp+4Fh+var_BC], 0
0x1801c310d  mov     r14, rdx
0x1801c3110  mov     [rbp+4Fh+var_B8], rax
0x1801c3114  xor     edx, edx; Val
0x1801c3116  mov     [rbp+4Fh+var_B0], 0
0x1801c311e  mov     r13, r8
0x1801c3121  mov     [rbp+4Fh+var_A8], 0
0x1801c3129  mov     rsi, rcx
0x1801c312c  mov     r15, r9
0x1801c312f  lea     rcx, [rbp+4Fh+var_A0]; void *
0x1801c3133  lea     r8d, [rdx+50h]; Size
0x1801c3137  call    memset_0
0x1801c313c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801c3143  mov     r12d, [rbp+4Fh+arg_20]
0x1801c3147  jz      short loc_1801C3171
0x1801c3149  mov     [rsp+100h+var_C8], r12d
0x1801c314e  lea     r8, WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids
0x1801c3155  mov     [rsp+100h+var_D0], r15
0x1801c315a  mov     edx, 49h ; 'I'
0x1801c315f  mov     [rsp+100h+var_D8], r13
0x1801c3164  mov     r9, rsi
0x1801c3167  mov     [rsp+100h+pcbActual], r14
0x1801c316c  call    WPP_SF_qSqqd
0x1801c3171  lea     rcx, [rbp+4Fh+var_B8]; this
0x1801c3175  call    ?LockShared@AutoSrw@@QEAAXXZ; AutoSrw::LockShared(void)
0x1801c317a  mov     rcx, [rsi+28h]; this
0x1801c317e  xor     r8d, r8d; struct CFileListEntry **
0x1801c3181  mov     rdx, r14; unsigned __int16 *
0x1801c3184  call    ?FindEntry@CFileListMap@@QEAAJPEBGPEAPEAVCFileListEntry@@@Z; CFileListMap::FindEntry(ushort const *,CFileListEntry * *)
0x1801c3189  mov     ebx, eax
0x1801c318b  test    eax, eax
0x1801c318d  jns     short loc_1801C319B
0x1801c318f  mov     [rbp+4Fh+var_BC], 9D4h
0x1801c3196  jmp     loc_1801C325B
0x1801c319b  jnz     short loc_1801C31AE
0x1801c319d  mov     ebx, 80070002h
0x1801c31a2  mov     [rbp+4Fh+var_BC], 9D5h
0x1801c31a9  jmp     loc_1801C325B
0x1801c31ae  mov     rcx, [rsi+98h]
0x1801c31b5  lea     rdx, [rbp+4Fh+var_A8]; struct CJetContext **
0x1801c31b9  xor     r8d, r8d; int *
0x1801c31bc  mov     rcx, [rcx+10h]; this
0x1801c31c0  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1801c31c5  mov     rdi, [rbp+4Fh+var_A8]
0x1801c31c9  mov     ebx, eax
0x1801c31cb  test    eax, eax
0x1801c31cd  jns     short loc_1801C31D8
0x1801c31cf  mov     [rbp+4Fh+var_BC], 9DBh
0x1801c31d6  jmp     short loc_1801C3242
0x1801c31d8  lea     r8, aAppcacheidinde; "AppCacheIdIndex"
0x1801c31df  mov     edx, 1; unsigned int
0x1801c31e4  mov     rcx, rdi; this
0x1801c31e7  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801c31ec  mov     ebx, eax
0x1801c31ee  test    eax, eax
0x1801c31f0  jns     short loc_1801C31FB
0x1801c31f2  mov     [rbp+4Fh+var_BC], 9DEh
0x1801c31f9  jmp     short loc_1801C3242
0x1801c31fb  mov     rcx, [rdi+10h]; sesid
0x1801c31ff  call    cs:__imp_JetBeginTransaction
0x1801c3205  mov     ecx, eax; int
0x1801c3207  mov     edx, 1; int
0x1801c320c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c3211  mov     ebx, eax
0x1801c3213  test    eax, eax
0x1801c3215  js      short loc_1801C3242
0x1801c3217  mov     r8, r14; unsigned __int16 *
0x1801c321a  mov     rdx, rdi; struct CJetContext *
0x1801c321d  mov     rcx, rsi; this
0x1801c3220  call    ?SeekToAppCacheUrl@CAppCache@@AEAAJPEAVCJetContext@@PEBG@Z; CAppCache::SeekToAppCacheUrl(CJetContext *,ushort const *)
0x1801c3225  mov     ebx, eax
0x1801c3227  test    eax, eax
0x1801c3229  jns     loc_1801C32C6
0x1801c322f  mov     [rbp+4Fh+var_BC], 9E4h
0x1801c3236  mov     rcx, [rdi+10h]; sesid
0x1801c323a  xor     edx, edx; grbit
0x1801c323c  call    cs:__imp_JetRollback
0x1801c3242  test    rdi, rdi
0x1801c3245  jz      short loc_1801C325B
0x1801c3247  mov     rcx, [rsi+98h]
0x1801c324e  lea     rdx, [rbp+4Fh+var_A8]; struct CJetContext **
0x1801c3252  mov     rcx, [rcx+10h]; this
0x1801c3256  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1801c325b  lea     rcx, [rbp+4Fh+var_B8]; this
0x1801c325f  call    ?UnlockShared@AutoSrw@@QEAAXXZ; AutoSrw::UnlockShared(void)
0x1801c3264  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801c326b  jz      short loc_1801C3286
0x1801c326d  mov     edx, 4Ah ; 'J'
0x1801c3272  lea     r8, WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids
0x1801c3279  mov     ecx, 40Ch
0x1801c327e  mov     r9d, ebx
0x1801c3281  call    WPP_SF_d
0x1801c3286  cmp     dword ptr [rbp+4Fh+var_B0], 0
0x1801c328a  jz      short loc_1801C3295
0x1801c328c  lea     rcx, [rbp+4Fh+var_B8]; this
0x1801c3290  call    ?UnlockShared@AutoSrw@@QEAAXXZ; AutoSrw::UnlockShared(void)
0x1801c3295  cmp     dword ptr [rbp+4Fh+var_B0+4], 0
0x1801c3299  jz      short loc_1801C32A4
0x1801c329b  lea     rcx, [rbp+4Fh+var_B8]; this
0x1801c329f  call    ?UnlockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::UnlockExclusive(void)
0x1801c32a4  mov     eax, ebx
0x1801c32a6  mov     rcx, [rbp+4Fh+var_50]
0x1801c32aa  xor     rcx, rsp; StackCookie
0x1801c32ad  call    __security_check_cookie
0x1801c32b2  add     rsp, 0C8h
0x1801c32b9  pop     r15
0x1801c32bb  pop     r14
0x1801c32bd  pop     r13
0x1801c32bf  pop     r12
0x1801c32c1  pop     rdi
0x1801c32c2  pop     rsi
0x1801c32c3  pop     rbx
0x1801c32c4  pop     rbp
0x1801c32c5  retn
0x1801c32c6  mov     rcx, [rdi+10h]; sesid
0x1801c32ca  jnz     loc_1801C3392
0x1801c32d0  mov     rdx, [rdi+20h]; tableid
0x1801c32d4  mov     r8d, 2; prep
0x1801c32da  call    cs:__imp_JetPrepareUpdate
0x1801c32e0  mov     r14d, 1
0x1801c32e6  mov     ecx, eax; int
0x1801c32e8  mov     edx, r14d; int
0x1801c32eb  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c32f0  mov     ebx, eax
0x1801c32f2  test    eax, eax
0x1801c32f4  js      loc_1801C3236
0x1801c32fa  mov     r9d, r12d; unsigned int
0x1801c32fd  lea     edx, [r14+0Dh]; unsigned int
0x1801c3301  mov     r8, r15; unsigned __int8 *
0x1801c3304  mov     rcx, rdi; this
0x1801c3307  call    ?SetBinaryColumn@CJetContext@@QEAAJKPEBEK@Z; CJetContext::SetBinaryColumn(ulong,uchar const *,ulong)
0x1801c330c  mov     ebx, eax
0x1801c330e  test    eax, eax
0x1801c3310  jns     short loc_1801C3332
0x1801c3312  mov     [rbp+4Fh+var_BC], 9EFh
0x1801c3319  mov     rdx, [rdi+20h]; tableid
0x1801c331d  mov     r8d, 3; prep
0x1801c3323  mov     rcx, [rdi+10h]; sesid
0x1801c3327  call    cs:__imp_JetPrepareUpdate
0x1801c332d  jmp     loc_1801C3236
0x1801c3332  mov     rdx, [rdi+20h]; tableid
0x1801c3336  xor     r9d, r9d; cbBookmark
0x1801c3339  mov     rcx, [rdi+10h]; sesid
0x1801c333d  xor     r8d, r8d; pvBookmark
0x1801c3340  mov     [rsp+100h+pcbActual], 0; pcbActual
0x1801c3349  call    cs:__imp_JetUpdate
0x1801c334f  cmp     eax, 0FFFFFBB2h
0x1801c3354  jnz     short loc_1801C335A
0x1801c3356  xor     ebx, ebx
0x1801c3358  jmp     short loc_1801C3319
0x1801c335a  mov     edx, r14d; int
0x1801c335d  mov     ecx, eax; int
0x1801c335f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c3364  mov     ebx, eax
0x1801c3366  test    eax, eax
0x1801c3368  js      short loc_1801C3319
0x1801c336a  mov     rcx, [rdi+10h]; sesid
0x1801c336e  mov     edx, r14d; grbit
0x1801c3371  call    cs:__imp_JetCommitTransaction
0x1801c3377  mov     ecx, eax; int
0x1801c3379  mov     edx, r14d; int
0x1801c337c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c3381  mov     ebx, eax
0x1801c3383  test    eax, eax
0x1801c3385  js      loc_1801C3236
0x1801c338b  xor     ebx, ebx
0x1801c338d  jmp     loc_1801C3242
0x1801c3392  xor     edx, edx; grbit
0x1801c3394  call    cs:__imp_JetRollback
0x1801c339a  mov     ecx, eax; int
0x1801c339c  mov     edx, 1; int
0x1801c33a1  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c33a6  mov     ebx, eax
0x1801c33a8  test    eax, eax
0x1801c33aa  js      loc_1801C3236
0x1801c33b0  mov     r9d, 80h; unsigned int
0x1801c33b6  mov     [rbp+4Fh+var_58], r15
0x1801c33ba  lea     r8, [rbp+4Fh+var_A0]; struct _URLCACHE_UPDATE_DATA *
0x1801c33be  mov     [rbp+4Fh+var_6C], r12d
0x1801c33c2  mov     rdx, r14; unsigned __int16 *
0x1801c33c5  mov     rcx, r13; this
0x1801c33c8  call    ?UpdateUrl@CCacheContainer@@QEAAJPEBGPEBU_URLCACHE_UPDATE_DATA@@K@Z; CCacheContainer::UpdateUrl(ushort const *,_URLCACHE_UPDATE_DATA const *,ulong)
0x1801c33cd  mov     ebx, eax
0x1801c33cf  test    eax, eax
0x1801c33d1  jns     short loc_1801C338B
0x1801c33d3  mov     [rbp+4Fh+var_BC], 0A17h
0x1801c33da  jmp     loc_1801C3242
```
