# StateRepository::Entity::CacheUser::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x1802649b0`
- end: `0x180264e79`
- name: `?Cache_CheckIntegrity@CacheUser@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1225`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180034b4c`
- `0x180062cd8`
- `0x1800a7398`
- `0x1800ae890`
- `0x1800be48c`
- `0x18018f650`
- `0x180190234`
- `0x1802648b8`
- `0x1802649b0`
- `0x180265024`
- `0x1802650ec`
- `0x1802651cc`
- `0x18026544c`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180264c91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180264dc6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180264de9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180264c91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180264dc6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180264de9`

## string_xrefs

- `0x180264a3a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x180264a8b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x180264bb4`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x180264c73`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x180264d7f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x180264d9f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x180264e4a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x180264c53`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-User.hpp`
- `0x180264bf1`: `CacheUser`
- `0x180264e02`: `CacheUser`
- `0x180264cfc`: `SELECT EXISTS(SELECT 1 FROM CacheUser WHERE _CacheUserID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheUser::Cache_CheckIntegrity(
        StateRepository::Database *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        _QWORD *a4)
{
  struct StateRepository::Cache::Manager_NoThrow *v4; // rsi
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  int Next; // eax
  int v10; // ecx
  __int64 v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // r15
  __int64 v14; // r8
  int appended; // esi
  char v16; // r8
  char v17; // r8
  unsigned __int64 v18; // r14
  __int64 v19; // rdx
  __int64 v20; // rdi
  int v21; // eax
  int v22; // edi
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdi
  int v27; // eax
  __int64 v28; // rdx
  char v29; // r8
  int v30; // esi
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  bool *v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  bool *v37; // [rsp+28h] [rbp-D8h]
  bool v38[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v40; // [rsp+48h] [rbp-B8h]
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  int v42[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h]
  unsigned __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v45; // [rsp+78h] [rbp-88h]
  _QWORD *v46; // [rsp+80h] [rbp-80h]
  _OWORD v47[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v48; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v49[72]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h]
  __int64 v51; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v52[72]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v53; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v46 = a4;
  v4 = a2;
  v45 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 370;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 371;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
      (const char *)v6,
      (int)v35);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 372;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v42 = 0;
  v43 = 0;
  v41 = 0;
  v8 = StateRepository::Entity::CacheUser::Find(a1, (struct StateRepository::Statement *)&v41);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
      (const char *)(unsigned int)v8,
      (int)v35);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v41);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v42);
    return v6;
  }
  v38[0] = 0;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  Next = StateRepository::Entity::CacheUser::FindNext(
           (struct StateRepository::Statement *)&v41,
           (struct StateRepository::Entity::CacheUser *)v39,
           v38);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
      (const char *)(unsigned int)Next,
      (int)v35);
    StateRepository::Blob::Reset((StateRepository::Blob *)&v39[1]);
    goto LABEL_28;
  }
  v11 = 0;
  v12 = 0;
  v13 = 0;
  while ( v38[0] )
  {
    v51 = 0;
    memset_0(v52, 0, 0x44u);
    v35 = v38;
    v53 = 0;
    appended = StateRepository::Cache::Entity::User_NoThrow::Get(v4, v39[0], v14, &v51);
    if ( appended < 0 )
    {
      v19 = 391;
      goto LABEL_27;
    }
    if ( v38[0] )
    {
      v44 = 0;
      appended = StateRepository::Entity::CacheUser::Cache_Check(
                   (const struct StateRepository::Entity::CacheUser *)v39,
                   (const struct StateRepository::Cache::Entity::User_NoThrow *)&v51,
                   &v44);
      if ( appended < 0 )
      {
        v19 = 396;
        goto LABEL_27;
      }
      v18 = v44;
      if ( v44 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v42, v39[0], v17);
        if ( appended < 0 )
        {
          v19 = 400;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
            (const char *)(unsigned int)appended,
            (int)v38);
          StateRepository::Blob::Reset((StateRepository::Blob *)&v39[1]);
          v6 = appended;
          goto LABEL_28;
        }
        v11 += v18;
      }
      ++v13;
    }
    else
    {
      appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v42, v39[0], v16);
      if ( appended < 0 )
      {
        v19 = 406;
        goto LABEL_27;
      }
      ++v11;
    }
    appended = StateRepository::Entity::CacheUser::FindNext(
                 (struct StateRepository::Statement *)&v41,
                 (struct StateRepository::Entity::CacheUser *)v39,
                 v38);
    if ( appended < 0 )
    {
      v19 = 408;
      goto LABEL_27;
    }
    v4 = v45;
    ++v12;
  }
  v20 = v12 - v13;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheUser",
      v20,
      *(__int64 *)v42);
  StateRepository::Blob::Reset((StateRepository::Blob *)&v39[1]);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v41);
  StateRepository::TextA::Clear((StateRepository::TextA *)v42);
  v39[0] = 0;
  LODWORD(v39[1]) = 0;
  *(_QWORD *)&v40 = 0;
  v21 = StateRepository::Cache::Entity::UserIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::UserIterator_NoThrow *)v39,
          v4);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x339,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v21,
      (int)v35);
    v23 = 425;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
      (const char *)(unsigned int)v22,
      (int)v35);
    v24 = v39[0];
    v39[0] = 0;
    if ( v24 )
      SRCacheContext_Close(v24);
    v6 = v22;
    goto LABEL_53;
  }
  v48 = 0;
  memset_0(v49, 0, 0x44u);
  v50 = 0;
  v38[0] = 0;
  v22 = StateRepository::Cache::Entity::UserIterator_NoThrow::Get(v39, v25, &v48, v38);
  if ( v22 < 0 )
  {
    v23 = 428;
    goto LABEL_34;
  }
  v26 = 0;
  while ( v38[0] )
  {
    memset(v47, 0, sizeof(v47));
    v27 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheUser WHERE _CacheUserID=? LIMIT 1);",
            0,
            v48,
            (__int64)v38,
            v37);
    v30 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
        (const char *)(unsigned int)v27,
        v36);
      v31 = 432;
      goto LABEL_50;
    }
    if ( !v38[0] )
    {
      v30 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v42, (__int64)v48, v29);
      if ( v30 < 0 )
      {
        v31 = 437;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
          (const char *)(unsigned int)v30,
          v36);
        StateRepository::Blob::Reset((StateRepository::Blob *)((char *)v47 + 8));
        v32 = v39[0];
        v39[0] = 0;
        if ( v32 )
          SRCacheContext_Close(v32);
        v6 = v30;
        goto LABEL_53;
      }
      ++v26;
      ++v11;
    }
    ++LODWORD(v39[1]);
    v30 = StateRepository::Cache::Entity::UserIterator_NoThrow::Get(v39, v28, &v48, v38);
    if ( v30 < 0 )
    {
      v31 = 439;
      goto LABEL_50;
    }
    StateRepository::Blob::Reset((StateRepository::Blob *)((char *)v47 + 8));
  }
  v33 = v39[0];
  v39[0] = 0;
  if ( v33 )
    SRCacheContext_Close(v33);
  if ( v26 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v33,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheUser",
      v26,
      *(__int64 *)v42);
  *v46 = v11;
  StateRepository::TextA::Reset((StateRepository::TextA *)v42);
  return 0;
}

```

## disassembly

```asm
0x1802649b0  push    rbp
0x1802649b2  push    rbx
0x1802649b3  push    rsi
0x1802649b4  push    rdi
0x1802649b5  push    r13
0x1802649b7  push    r14
0x1802649b9  push    r15
0x1802649bb  lea     rbp, [rsp-80h]
0x1802649c0  sub     rsp, 180h
0x1802649c7  mov     rax, cs:__security_cookie
0x1802649ce  xor     rax, rsp
0x1802649d1  mov     [rbp+0B0h+var_40], rax
0x1802649d5  xor     r14d, r14d
0x1802649d8  mov     [rbp+0B0h+var_130], r9
0x1802649dc  mov     rsi, rdx
0x1802649df  mov     [rsp+1B0h+var_138], rdx
0x1802649e4  mov     r13, rcx
0x1802649e7  cmp     [rcx], r14
0x1802649ea  jz      loc_180264E39
0x1802649f0  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x1802649f5  test    al, al
0x1802649f7  jz      short loc_180264A08
0x1802649f9  mov     ebx, 8067000Bh
0x1802649fe  mov     edx, 173h
0x180264a03  jmp     loc_180264E43
0x180264a08  cmp     [rsi], r14
0x180264a0b  jz      loc_180264E32
0x180264a11  lea     rdx, [rsp+1B0h+var_158]; struct StateRepository::Statement *
0x180264a16  mov     qword ptr [rsp+1B0h+var_150], r14
0x180264a1b  mov     rcx, r13; struct StateRepository::Database *
0x180264a1e  mov     [rsp+1B0h+var_148], r14
0x180264a23  mov     [rsp+1B0h+var_158], r14
0x180264a28  call    ?Find@CacheUser@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheUser::Find(StateRepository::Database &,StateRepository::Statement &)
0x180264a2d  mov     ebx, eax
0x180264a2f  test    eax, eax
0x180264a31  jns     short loc_180264A53
0x180264a33  mov     rcx, [rbp+0B8h]; this
0x180264a3a  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x180264a41  mov     r9d, eax; char *
0x180264a44  mov     edx, 17Fh; void *
0x180264a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180264a4e  jmp     loc_180264BCF
0x180264a53  xorps   xmm0, xmm0
0x180264a56  mov     [rsp+1B0h+var_180], r14b
0x180264a5b  xorps   xmm1, xmm1
0x180264a5e  lea     r8, [rsp+1B0h+var_180]; bool *
0x180264a63  lea     rdx, [rsp+1B0h+var_178]; struct StateRepository::Entity::CacheUser *
0x180264a68  lea     rcx, [rsp+1B0h+var_158]; struct StateRepository::Statement *
0x180264a6d  movdqu  xmmword ptr [rsp+1B0h+var_178], xmm0
0x180264a73  movdqu  [rsp+1B0h+var_168], xmm1
0x180264a79  call    ?FindNext@CacheUser@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheUser::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheUser &,bool &)
0x180264a7e  mov     ebx, eax
0x180264a80  test    eax, eax
0x180264a82  jns     short loc_180264AAE
0x180264a84  mov     rcx, [rbp+0B8h]; this
0x180264a8b  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x180264a92  mov     r9d, eax; char *
0x180264a95  mov     edx, 182h; void *
0x180264a9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180264a9f  lea     rcx, [rsp+1B0h+var_178+8]; this
0x180264aa4  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x180264aa9  jmp     loc_180264BCF
0x180264aae  mov     rbx, r14
0x180264ab1  mov     rdi, r14
0x180264ab4  mov     r15, r14
0x180264ab7  cmp     [rsp+1B0h+var_180], r14b
0x180264abc  jz      loc_180264BDE
0x180264ac2  xor     edx, edx; Val
0x180264ac4  mov     [rbp+0B0h+var_A0], r14
0x180264ac8  lea     rcx, [rbp+0B0h+var_98]; void *
0x180264acc  lea     r8d, [rdx+44h]; Size
0x180264ad0  call    memset_0
0x180264ad5  mov     rdx, [rsp+1B0h+var_178]
0x180264ada  lea     rax, [rsp+1B0h+var_180]
0x180264adf  lea     r9, [rbp+0B0h+var_A0]
0x180264ae3  mov     [rsp+1B0h+var_190], rax; int
0x180264ae8  mov     rcx, rsi
0x180264aeb  mov     [rbp+0B0h+var_50], r14
0x180264aef  call    ?Get@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x180264af4  mov     esi, eax
0x180264af6  test    eax, eax
0x180264af8  js      loc_180264BA8
0x180264afe  cmp     [rsp+1B0h+var_180], r14b
0x180264b03  jz      short loc_180264B4D
0x180264b05  lea     r8, [rsp+1B0h+var_140]; unsigned __int64 *
0x180264b0a  mov     [rsp+1B0h+var_140], r14
0x180264b0f  lea     rdx, [rbp+0B0h+var_A0]; struct StateRepository::Cache::Entity::User_NoThrow *
0x180264b13  lea     rcx, [rsp+1B0h+var_178]; struct StateRepository::Entity::CacheUser *
0x180264b18  call    ?Cache_Check@CacheUser@Entity@StateRepository@@CAJAEBV123@AEBVUser_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheUser::Cache_Check(StateRepository::Entity::CacheUser const &,StateRepository::Cache::Entity::User_NoThrow const &,unsigned __int64 &)
0x180264b1d  mov     esi, eax
0x180264b1f  test    eax, eax
0x180264b21  js      short loc_180264B93
0x180264b23  mov     r14, [rsp+1B0h+var_140]
0x180264b28  test    r14, r14
0x180264b2b  jz      short loc_180264B45
0x180264b2d  mov     rdx, [rsp+1B0h+var_178]; __int64
0x180264b32  lea     rcx, [rsp+1B0h+var_150]; this
0x180264b37  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180264b3c  mov     esi, eax
0x180264b3e  test    eax, eax
0x180264b40  js      short loc_180264B8C
0x180264b42  add     rbx, r14
0x180264b45  inc     r15
0x180264b48  xor     r14d, r14d
0x180264b4b  jmp     short loc_180264B65
0x180264b4d  mov     rdx, [rsp+1B0h+var_178]; __int64
0x180264b52  lea     rcx, [rsp+1B0h+var_150]; this
0x180264b57  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180264b5c  mov     esi, eax
0x180264b5e  test    eax, eax
0x180264b60  js      short loc_180264BA1
0x180264b62  inc     rbx
0x180264b65  lea     r8, [rsp+1B0h+var_180]; bool *
0x180264b6a  lea     rdx, [rsp+1B0h+var_178]; struct StateRepository::Entity::CacheUser *
0x180264b6f  lea     rcx, [rsp+1B0h+var_158]; struct StateRepository::Statement *
0x180264b74  call    ?FindNext@CacheUser@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheUser::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheUser &,bool &)
0x180264b79  mov     esi, eax
0x180264b7b  test    eax, eax
0x180264b7d  js      short loc_180264B9A
0x180264b7f  mov     rsi, [rsp+1B0h+var_138]
0x180264b84  inc     rdi
0x180264b87  jmp     loc_180264AB7
0x180264b8c  mov     edx, 190h
0x180264b91  jmp     short loc_180264BAD
0x180264b93  mov     edx, 18Ch
0x180264b98  jmp     short loc_180264BAD
0x180264b9a  mov     edx, 198h
0x180264b9f  jmp     short loc_180264BAD
0x180264ba1  mov     edx, 196h
0x180264ba6  jmp     short loc_180264BAD
0x180264ba8  mov     edx, 187h; void *
0x180264bad  mov     rcx, [rbp+0B8h]; this
0x180264bb4  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x180264bbb  mov     r9d, esi; char *
0x180264bbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180264bc3  lea     rcx, [rsp+1B0h+var_178+8]; this
0x180264bc8  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x180264bcd  mov     ebx, esi
0x180264bcf  lea     rcx, [rsp+1B0h+var_158]; this
0x180264bd4  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180264bd9  jmp     loc_180264DCE
0x180264bde  sub     rdi, r15
0x180264be1  jz      short loc_180264C0C
0x180264be3  test    cs:byte_1804DF881, 20h
0x180264bea  jz      short loc_180264C0C
0x180264bec  mov     rax, qword ptr [rsp+1B0h+var_150]
0x180264bf1  lea     r8, aCacheuser; "CacheUser"
0x180264bf8  mov     r9, rdi
0x180264bfb  mov     [rsp+1B0h+var_190], rax; int
0x180264c00  lea     rdx, CacheIntegrity_MissingCacheEntries
0x180264c07  call    McTemplateU0sxs_EventWriteTransfer
0x180264c0c  lea     rcx, [rsp+1B0h+var_178+8]; this
0x180264c11  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x180264c16  lea     rcx, [rsp+1B0h+var_158]; this
0x180264c1b  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180264c20  lea     rcx, [rsp+1B0h+var_150]; this
0x180264c25  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x180264c2a  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x180264c2d  mov     [rsp+1B0h+var_178], r14
0x180264c32  lea     rcx, [rsp+1B0h+var_178]; this
0x180264c37  mov     dword ptr [rsp+1B0h+var_178+8], r14d
0x180264c3c  mov     qword ptr [rsp+1B0h+var_168], r14
0x180264c41  call    ?Open@UserIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::UserIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x180264c46  mov     edi, eax
0x180264c48  test    eax, eax
0x180264c4a  jns     short loc_180264C9E
0x180264c4c  mov     rcx, [rbp+0B8h]; this
0x180264c53  lea     r8, aOnecoreBaseApp_139; "onecore\\base\\appmodel\\StateRepositor"...
0x180264c5a  mov     r9d, eax; char *
0x180264c5d  mov     edx, 339h; void *
0x180264c62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180264c67  mov     edx, 1A9h; void *
0x180264c6c  mov     rcx, [rbp+0B8h]; this
0x180264c73  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x180264c7a  mov     r9d, edi; char *
0x180264c7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180264c82  mov     rcx, [rsp+1B0h+var_178]
0x180264c87  mov     [rsp+1B0h+var_178], r14
0x180264c8c  test    rcx, rcx
0x180264c8f  jz      short loc_180264C97
0x180264c91  call    cs:__imp_SRCacheContext_Close
0x180264c97  mov     ebx, edi
0x180264c99  jmp     loc_180264DCE
0x180264c9e  xor     edx, edx; Val
0x180264ca0  mov     [rbp+0B0h+var_100], r14
0x180264ca4  lea     rcx, [rbp+0B0h+var_F8]; void *
0x180264ca8  lea     r8d, [rdx+44h]; Size
0x180264cac  call    memset_0
0x180264cb1  lea     r9, [rsp+1B0h+var_180]
0x180264cb6  mov     [rbp+0B0h+var_B0], r14
0x180264cba  lea     r8, [rbp+0B0h+var_100]
0x180264cbe  mov     [rsp+1B0h+var_180], r14b
0x180264cc3  lea     rcx, [rsp+1B0h+var_178]
0x180264cc8  call    ?Get@UserIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@User_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::UserIterator_NoThrow::Get(StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x180264ccd  mov     edi, eax
0x180264ccf  test    eax, eax
0x180264cd1  jns     short loc_180264CDA
0x180264cd3  mov     edx, 1ACh
0x180264cd8  jmp     short loc_180264C6C
0x180264cda  mov     rdi, r14
0x180264cdd  cmp     [rsp+1B0h+var_180], r14b
0x180264ce2  jz      loc_180264DDA
0x180264ce8  mov     r9, [rbp+0B0h+var_100]; char *
0x180264cec  lea     rax, [rsp+1B0h+var_180]
0x180264cf1  xorps   xmm0, xmm0
0x180264cf4  mov     [rsp+1B0h+var_190], rax; int
0x180264cf9  xorps   xmm1, xmm1
0x180264cfc  lea     rdx, aSelectExistsSe_281; "SELECT EXISTS(SELECT 1 FROM CacheUser W"...
0x180264d03  xor     r8d, r8d; char *
0x180264d06  mov     rcx, r13; this
0x180264d09  movdqu  [rbp+0B0h+var_128], xmm0
0x180264d0e  movdqu  [rbp+0B0h+var_118], xmm1
0x180264d13  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x180264d18  mov     esi, eax
0x180264d1a  test    eax, eax
0x180264d1c  js      short loc_180264D78
0x180264d1e  cmp     [rsp+1B0h+var_180], r14b
0x180264d23  jnz     short loc_180264D3F
0x180264d25  mov     rdx, [rbp+0B0h+var_100]; __int64
0x180264d29  lea     rcx, [rsp+1B0h+var_150]; this
0x180264d2e  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180264d33  mov     esi, eax
0x180264d35  test    eax, eax
0x180264d37  js      short loc_180264D6A
0x180264d39  inc     rdi
0x180264d3c  inc     rbx
0x180264d3f  inc     dword ptr [rsp+1B0h+var_178+8]
0x180264d43  lea     r9, [rsp+1B0h+var_180]
0x180264d48  lea     r8, [rbp+0B0h+var_100]
0x180264d4c  lea     rcx, [rsp+1B0h+var_178]
0x180264d51  call    ?Get@UserIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@User_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::UserIterator_NoThrow::Get(StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x180264d56  mov     esi, eax
0x180264d58  test    eax, eax
0x180264d5a  js      short loc_180264D71
0x180264d5c  lea     rcx, [rbp+0B0h+var_128+8]; this
0x180264d60  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x180264d65  jmp     loc_180264CDD
0x180264d6a  mov     edx, 1B5h
0x180264d6f  jmp     short loc_180264D98
0x180264d71  mov     edx, 1B7h
0x180264d76  jmp     short loc_180264D98
0x180264d78  mov     rcx, [rbp+0B8h]; this
0x180264d7f  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x180264d86  mov     r9d, esi; char *
0x180264d89  mov     edx, 57h ; 'W'; void *
0x180264d8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180264d93  mov     edx, 1B0h; void *
0x180264d98  mov     rcx, [rbp+0B8h]; this
0x180264d9f  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x180264da6  mov     r9d, esi; char *
0x180264da9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180264dae  lea     rcx, [rbp+0B0h+var_128+8]; this
0x180264db2  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x180264db7  mov     rcx, [rsp+1B0h+var_178]
0x180264dbc  mov     [rsp+1B0h+var_178], r14
0x180264dc1  test    rcx, rcx
0x180264dc4  jz      short loc_180264DCC
0x180264dc6  call    cs:__imp_SRCacheContext_Close
0x180264dcc  mov     ebx, esi
0x180264dce  lea     rcx, [rsp+1B0h+var_150]; this
0x180264dd3  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180264dd8  jmp     short loc_180264E59
0x180264dda  mov     rcx, [rsp+1B0h+var_178]
0x180264ddf  mov     [rsp+1B0h+var_178], r14
0x180264de4  test    rcx, rcx
0x180264de7  jz      short loc_180264DEF
0x180264de9  call    cs:__imp_SRCacheContext_Close
0x180264def  test    rdi, rdi
0x180264df2  jz      short loc_180264E1D
0x180264df4  test    cs:byte_1804DF881, 20h
0x180264dfb  jz      short loc_180264E1D
0x180264dfd  mov     rax, qword ptr [rsp+1B0h+var_150]
0x180264e02  lea     r8, aCacheuser; "CacheUser"
0x180264e09  mov     r9, rdi
0x180264e0c  mov     [rsp+1B0h+var_190], rax
0x180264e11  lea     rdx, CacheIntegrity_UnexpectedCacheEntries
0x180264e18  call    McTemplateU0sxs_EventWriteTransfer
0x180264e1d  mov     rax, [rbp+0B0h+var_130]
0x180264e21  lea     rcx, [rsp+1B0h+var_150]; this
0x180264e26  mov     [rax], rbx
0x180264e29  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180264e2e  xor     eax, eax
0x180264e30  jmp     short loc_180264E5B
0x180264e32  mov     edx, 174h
0x180264e37  jmp     short loc_180264E3E
0x180264e39  mov     edx, 172h; void *
0x180264e3e  mov     ebx, 8007139Fh
0x180264e43  mov     rcx, [rbp+0B8h]; this
0x180264e4a  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x180264e51  mov     r9d, ebx; char *
0x180264e54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180264e59  mov     eax, ebx
0x180264e5b  mov     rcx, [rbp+0B0h+var_40]
0x180264e5f  xor     rcx, rsp; StackCookie
0x180264e62  call    __security_check_cookie
0x180264e67  add     rsp, 180h
0x180264e6e  pop     r15
0x180264e70  pop     r14
0x180264e72  pop     r13
0x180264e74  pop     rdi
  ... truncated ...
```
