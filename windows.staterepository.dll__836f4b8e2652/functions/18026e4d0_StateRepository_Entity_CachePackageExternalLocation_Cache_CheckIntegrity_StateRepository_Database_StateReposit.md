# StateRepository::Entity::CachePackageExternalLocation::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x18026e4d0`
- end: `0x18026e9d1`
- name: `?Cache_CheckIntegrity@CachePackageExternalLocation@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1281`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x18008b498`
- `0x1800a6a90`
- `0x1800ae890`
- `0x18026544c`
- `0x18026e374`
- `0x18026e4d0`
- `0x18026ea94`
- `0x18026eb5c`
- `0x18026ec3c`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026e7bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026e91a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026e952`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026e7bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026e91a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026e952`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026e68a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026e6f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026e81a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026e905`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026e93d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026e68a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026e6f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026e81a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026e905`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026e93d`

## string_xrefs

- `0x18026e545`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18026e591`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18026e699`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18026e6d9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18026e799`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18026e7f9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18026e8c3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18026e8e0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18026e9ae`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18026e781`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18026e726`: `CachePackageExternalLocation`
- `0x18026e96a`: `CachePackageExternalLocation`
- `0x18026e849`: `SELECT EXISTS(SELECT 1 FROM CachePackageExternalLocation WHERE _CachePackageExternalLocationID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageExternalLocation::Cache_CheckIntegrity(
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
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // r14
  int v15; // esi
  char v16; // r8
  char v17; // r8
  unsigned __int64 v18; // r15
  int appended; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdi
  int v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // edi
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdi
  int v30; // eax
  __int64 v31; // rdx
  char v32; // r8
  int v33; // esi
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  bool *v40; // [rsp+20h] [rbp-99h]
  int v41; // [rsp+20h] [rbp-99h]
  int v42; // [rsp+20h] [rbp-99h]
  bool *v43; // [rsp+28h] [rbp-91h]
  __int64 v44; // [rsp+30h] [rbp-89h] BYREF
  int v45; // [rsp+38h] [rbp-81h]
  __int64 v46; // [rsp+40h] [rbp-79h]
  char *v47[2]; // [rsp+48h] [rbp-71h] BYREF
  __int128 v48; // [rsp+58h] [rbp-61h] BYREF
  __int64 v49; // [rsp+68h] [rbp-51h]
  __int64 v50; // [rsp+70h] [rbp-49h] BYREF
  int v51[2]; // [rsp+78h] [rbp-41h] BYREF
  __int64 v52; // [rsp+80h] [rbp-39h]
  __int128 v53; // [rsp+88h] [rbp-31h] BYREF
  __int128 v54; // [rsp+98h] [rbp-21h]
  unsigned __int64 v55; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v56; // [rsp+B0h] [rbp-9h]
  __int128 v57; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v58; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  bool v60; // [rsp+120h] [rbp+67h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v61; // [rsp+128h] [rbp+6Fh]
  _QWORD *v62; // [rsp+138h] [rbp+7Fh]

  v62 = a4;
  v61 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 433;
    goto LABEL_71;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 434;
LABEL_72:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
      (const char *)v6,
      (int)v40);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 435;
LABEL_71:
    v6 = -2147019873;
    goto LABEL_72;
  }
  *(_QWORD *)v51 = 0;
  v52 = 0;
  v50 = 0;
  v8 = StateRepository::Entity::CachePackageExternalLocation::Find(a1, (struct StateRepository::Statement *)&v50);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
      (const char *)(unsigned int)v8,
      (int)v40);
LABEL_32:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v50);
LABEL_60:
    StateRepository::TextA::Reset((StateRepository::TextA *)v51);
    return v6;
  }
  v49 = 0;
  v60 = 0;
  *(_OWORD *)v47 = 0;
  v48 = 0;
  Next = StateRepository::Entity::CachePackageExternalLocation::FindNext(
           (struct StateRepository::Statement *)&v50,
           (struct StateRepository::Entity::CachePackageExternalLocation *)v47,
           &v60);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C1,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
      (const char *)(unsigned int)Next,
      (int)v40);
    StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v48 + 8));
    goto LABEL_32;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v60 )
  {
    v40 = &v60;
    v53 = 0;
    v54 = 0;
    v15 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(v4, v47[0], v11, &v53);
    if ( v15 < 0 )
    {
      v21 = 454;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
        (const char *)(unsigned int)v15,
        (int)&v60);
      v20 = *((_QWORD *)&v54 + 1);
      *((_QWORD *)&v54 + 1) = 0;
LABEL_29:
      if ( v20 )
        SRCache_Free(v20);
      StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v48 + 8));
      v6 = v15;
      goto LABEL_32;
    }
    if ( v60 )
    {
      v55 = 0;
      v15 = StateRepository::Entity::CachePackageExternalLocation::Cache_Check(
              (const struct StateRepository::Entity::CachePackageExternalLocation *)v47,
              (const struct StateRepository::Cache::Entity::PackageExternalLocation_NoThrow *)&v53,
              &v55);
      if ( v15 < 0 )
      {
        v21 = 459;
        goto LABEL_28;
      }
      v18 = v55;
      if ( v55 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v51, (__int64)v47[0], v17);
        v15 = appended;
        if ( appended < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CF,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
            (const char *)(unsigned int)appended,
            (int)&v60);
          v20 = *((_QWORD *)&v54 + 1);
          *((_QWORD *)&v54 + 1) = 0;
          goto LABEL_29;
        }
        v12 += v18;
      }
      ++v14;
    }
    else
    {
      v15 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v51, (__int64)v47[0], v16);
      if ( v15 < 0 )
      {
        v21 = 469;
        goto LABEL_28;
      }
      ++v12;
    }
    v15 = StateRepository::Entity::CachePackageExternalLocation::FindNext(
            (struct StateRepository::Statement *)&v50,
            (struct StateRepository::Entity::CachePackageExternalLocation *)v47,
            &v60);
    if ( v15 < 0 )
    {
      v21 = 471;
      goto LABEL_28;
    }
    v10 = *((_QWORD *)&v54 + 1);
    ++v13;
    v4 = v61;
    *((_QWORD *)&v54 + 1) = 0;
    if ( v10 )
      SRCache_Free(v10);
  }
  v22 = v13 - v14;
  if ( v22 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CachePackageExternalLocation",
      v22,
      *(__int64 *)v51);
  StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v48 + 8));
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v50);
  StateRepository::TextA::Clear((StateRepository::TextA *)v51);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v23 = StateRepository::Cache::Entity::PackageExternalLocationIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::PackageExternalLocationIterator_NoThrow *)&v44,
          v4);
  v25 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v23,
      (int)v40);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
      (const char *)v25,
      v41);
LABEL_38:
    v26 = v44;
    v44 = 0;
    if ( v26 )
      SRCacheContext_Close(v26);
    v6 = v25;
    goto LABEL_60;
  }
  v60 = 0;
  *(_OWORD *)v47 = 0;
  v48 = 0;
  v27 = StateRepository::Cache::Entity::PackageExternalLocationIterator_NoThrow::Get(&v44, v24, v47, &v60);
  v25 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
      (const char *)(unsigned int)v27,
      (int)v40);
    v28 = *((_QWORD *)&v48 + 1);
    *((_QWORD *)&v48 + 1) = 0;
    if ( v28 )
      SRCache_Free(v28);
    goto LABEL_38;
  }
  v29 = 0;
  while ( v60 )
  {
    v58 = 0;
    v56 = 0;
    v57 = 0;
    v30 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CachePackageExternalLocation WHERE _CachePac"
                                                "kageExternalLocationID=? LIMIT 1);",
            0,
            v47[0],
            (__int64)&v60,
            v43);
    v33 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
        (const char *)(unsigned int)v30,
        v42);
      v34 = 495;
      goto LABEL_55;
    }
    if ( !v60 )
    {
      v33 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v51, (__int64)v47[0], v32);
      if ( v33 < 0 )
      {
        v34 = 500;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
          (const char *)(unsigned int)v33,
          v42);
        StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v57 + 8));
        v35 = *((_QWORD *)&v48 + 1);
        *((_QWORD *)&v48 + 1) = 0;
        if ( v35 )
          SRCache_Free(v35);
        v36 = v44;
        v44 = 0;
        if ( v36 )
          SRCacheContext_Close(v36);
        v6 = v33;
        goto LABEL_60;
      }
      ++v29;
      ++v12;
    }
    ++v45;
    v33 = StateRepository::Cache::Entity::PackageExternalLocationIterator_NoThrow::Get(&v44, v31, v47, &v60);
    if ( v33 < 0 )
    {
      v34 = 502;
      goto LABEL_55;
    }
    StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v57 + 8));
  }
  v37 = *((_QWORD *)&v48 + 1);
  *((_QWORD *)&v48 + 1) = 0;
  if ( v37 )
    SRCache_Free(v37);
  v38 = v44;
  v44 = 0;
  if ( v38 )
    SRCacheContext_Close(v38);
  if ( v29 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v38,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CachePackageExternalLocation",
      v29,
      *(__int64 *)v51);
  *v62 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v51);
  return 0;
}

```

## disassembly

```asm
0x18026e4d0  mov     [rsp-8+arg_18], r9
0x18026e4d5  mov     [rsp-8+arg_8], rdx
0x18026e4da  push    rbp
0x18026e4db  push    rbx
0x18026e4dc  push    rsi
0x18026e4dd  push    rdi
0x18026e4de  push    r12
0x18026e4e0  push    r14
0x18026e4e2  push    r15
0x18026e4e4  lea     rbp, [rsp-27h]
0x18026e4e9  sub     rsp, 0E0h
0x18026e4f0  xor     r15d, r15d
0x18026e4f3  mov     rsi, rdx
0x18026e4f6  mov     r12, rcx
0x18026e4f9  cmp     [rcx], r15
0x18026e4fc  jz      loc_18026E9A0
0x18026e502  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18026e507  test    al, al
0x18026e509  jz      short loc_18026E51A
0x18026e50b  mov     ebx, 8067000Bh
0x18026e510  mov     edx, 1B2h
0x18026e515  jmp     loc_18026E9AA
0x18026e51a  cmp     [rsi], r15
0x18026e51d  jz      loc_18026E999
0x18026e523  lea     rdx, [rbp+57h+var_A0]; struct StateRepository::Statement *
0x18026e527  mov     qword ptr [rbp+57h+var_98], r15
0x18026e52b  mov     rcx, r12; struct StateRepository::Database *
0x18026e52e  mov     [rbp+57h+var_90], r15
0x18026e532  mov     [rbp+57h+var_A0], r15
0x18026e536  call    ?Find@CachePackageExternalLocation@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CachePackageExternalLocation::Find(StateRepository::Database &,StateRepository::Statement &)
0x18026e53b  mov     ebx, eax
0x18026e53d  test    eax, eax
0x18026e53f  jns     short loc_18026E55E
0x18026e541  mov     rcx, [rbp+5Fh]; this
0x18026e545  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18026e54c  mov     r9d, eax; char *
0x18026e54f  mov     edx, 1BEh; void *
0x18026e554  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e559  jmp     loc_18026E706
0x18026e55e  xorps   xmm0, xmm0
0x18026e561  mov     [rbp+57h+var_A8], r15
0x18026e565  xorps   xmm1, xmm1
0x18026e568  mov     [rbp+57h+arg_0], r15b
0x18026e56c  lea     r8, [rbp+57h+arg_0]; bool *
0x18026e570  lea     rdx, [rbp+57h+var_C8]; struct StateRepository::Entity::CachePackageExternalLocation *
0x18026e574  lea     rcx, [rbp+57h+var_A0]; this
0x18026e578  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x18026e57d  movdqu  [rbp+57h+var_B8], xmm1
0x18026e582  call    ?FindNext@CachePackageExternalLocation@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageExternalLocation::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageExternalLocation &,bool &)
0x18026e587  mov     ebx, eax
0x18026e589  test    eax, eax
0x18026e58b  jns     short loc_18026E5B3
0x18026e58d  mov     rcx, [rbp+5Fh]; this
0x18026e591  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18026e598  mov     r9d, eax; char *
0x18026e59b  mov     edx, 1C1h; void *
0x18026e5a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e5a5  lea     rcx, [rbp+57h+var_B8+8]; this
0x18026e5a9  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026e5ae  jmp     loc_18026E706
0x18026e5b3  mov     rbx, r15
0x18026e5b6  mov     rdi, r15
0x18026e5b9  mov     r14, r15
0x18026e5bc  cmp     [rbp+57h+arg_0], r15b
0x18026e5c0  jz      loc_18026E714
0x18026e5c6  mov     rdx, [rbp+57h+var_C8]
0x18026e5ca  lea     rax, [rbp+57h+arg_0]
0x18026e5ce  xorps   xmm0, xmm0
0x18026e5d1  mov     [rsp+110h+var_F0], rax; int
0x18026e5d6  xorps   xmm1, xmm1
0x18026e5d9  lea     r9, [rbp+57h+var_88]
0x18026e5dd  mov     rcx, rsi
0x18026e5e0  movdqu  [rbp+57h+var_88], xmm0
0x18026e5e5  movdqu  [rbp+57h+var_78], xmm1
0x18026e5ea  call    ?Get@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18026e5ef  mov     esi, eax
0x18026e5f1  test    eax, eax
0x18026e5f3  js      loc_18026E6D0
0x18026e5f9  cmp     [rbp+57h+arg_0], r15b
0x18026e5fd  jz      short loc_18026E645
0x18026e5ff  lea     r8, [rbp+57h+var_68]; unsigned __int64 *
0x18026e603  mov     [rbp+57h+var_68], r15
0x18026e607  lea     rdx, [rbp+57h+var_88]; struct StateRepository::Cache::Entity::PackageExternalLocation_NoThrow *
0x18026e60b  lea     rcx, [rbp+57h+var_C8]; struct StateRepository::Entity::CachePackageExternalLocation *
0x18026e60f  call    ?Cache_Check@CachePackageExternalLocation@Entity@StateRepository@@CAJAEBV123@AEBVPackageExternalLocation_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CachePackageExternalLocation::Cache_Check(StateRepository::Entity::CachePackageExternalLocation const &,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow const &,unsigned __int64 &)
0x18026e614  mov     esi, eax
0x18026e616  test    eax, eax
0x18026e618  js      loc_18026E6BB
0x18026e61e  mov     r15, [rbp+57h+var_68]
0x18026e622  test    r15, r15
0x18026e625  jz      short loc_18026E63D
0x18026e627  mov     rdx, [rbp+57h+var_C8]; __int64
0x18026e62b  lea     rcx, [rbp+57h+var_98]; this
0x18026e62f  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026e634  mov     esi, eax
0x18026e636  test    eax, eax
0x18026e638  js      short loc_18026E695
0x18026e63a  add     rbx, r15
0x18026e63d  inc     r14
0x18026e640  xor     r15d, r15d
0x18026e643  jmp     short loc_18026E65B
0x18026e645  mov     rdx, [rbp+57h+var_C8]; __int64
0x18026e649  lea     rcx, [rbp+57h+var_98]; this
0x18026e64d  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026e652  mov     esi, eax
0x18026e654  test    eax, eax
0x18026e656  js      short loc_18026E6C9
0x18026e658  inc     rbx
0x18026e65b  lea     r8, [rbp+57h+arg_0]; bool *
0x18026e65f  lea     rdx, [rbp+57h+var_C8]; struct StateRepository::Entity::CachePackageExternalLocation *
0x18026e663  lea     rcx, [rbp+57h+var_A0]; this
0x18026e667  call    ?FindNext@CachePackageExternalLocation@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageExternalLocation::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageExternalLocation &,bool &)
0x18026e66c  mov     esi, eax
0x18026e66e  test    eax, eax
0x18026e670  js      short loc_18026E6C2
0x18026e672  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x18026e676  inc     rdi
0x18026e679  mov     rsi, [rbp+57h+arg_8]
0x18026e67d  mov     qword ptr [rbp+57h+var_78+8], r15
0x18026e681  test    rcx, rcx
0x18026e684  jz      loc_18026E5BC
0x18026e68a  call    cs:__imp_SRCache_Free
0x18026e690  jmp     loc_18026E5BC
0x18026e695  mov     rcx, [rbp+5Fh]; this
0x18026e699  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18026e6a0  mov     r9d, esi; char *
0x18026e6a3  mov     edx, 1CFh; void *
0x18026e6a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e6ad  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x18026e6b1  mov     qword ptr [rbp+57h+var_78+8], 0
0x18026e6b9  jmp     short loc_18026E6F0
0x18026e6bb  mov     edx, 1CBh
0x18026e6c0  jmp     short loc_18026E6D5
0x18026e6c2  mov     edx, 1D7h
0x18026e6c7  jmp     short loc_18026E6D5
0x18026e6c9  mov     edx, 1D5h
0x18026e6ce  jmp     short loc_18026E6D5
0x18026e6d0  mov     edx, 1C6h; void *
0x18026e6d5  mov     rcx, [rbp+5Fh]; this
0x18026e6d9  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18026e6e0  mov     r9d, esi; char *
0x18026e6e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e6e8  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x18026e6ec  mov     qword ptr [rbp+57h+var_78+8], r15
0x18026e6f0  test    rcx, rcx
0x18026e6f3  jz      short loc_18026E6FB
0x18026e6f5  call    cs:__imp_SRCache_Free
0x18026e6fb  lea     rcx, [rbp+57h+var_B8+8]; this
0x18026e6ff  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026e704  mov     ebx, esi
0x18026e706  lea     rcx, [rbp+57h+var_A0]; this
0x18026e70a  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026e70f  jmp     loc_18026E922
0x18026e714  sub     rdi, r14
0x18026e717  jz      short loc_18026E741
0x18026e719  test    cs:byte_1804DF881, 20h
0x18026e720  jz      short loc_18026E741
0x18026e722  mov     rax, qword ptr [rbp+57h+var_98]
0x18026e726  lea     r8, aCachepackageex_0; "CachePackageExternalLocation"
0x18026e72d  mov     r9, rdi
0x18026e730  mov     [rsp+110h+var_F0], rax; int
0x18026e735  lea     rdx, CacheIntegrity_MissingCacheEntries
0x18026e73c  call    McTemplateU0sxs_EventWriteTransfer
0x18026e741  lea     rcx, [rbp+57h+var_B8+8]; this
0x18026e745  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026e74a  lea     rcx, [rbp+57h+var_A0]; this
0x18026e74e  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026e753  lea     rcx, [rbp+57h+var_98]; this
0x18026e757  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x18026e75c  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18026e75f  mov     [rsp+110h+var_E0], r15
0x18026e764  lea     rcx, [rsp+110h+var_E0]; this
0x18026e769  mov     [rsp+110h+var_D8], r15d
0x18026e76e  mov     [rbp+57h+var_D0], r15
0x18026e772  call    ?Open@PackageExternalLocationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::PackageExternalLocationIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x18026e777  mov     edi, eax
0x18026e779  test    eax, eax
0x18026e77b  jns     short loc_18026E7C9
0x18026e77d  mov     rcx, [rbp+5Fh]; this
0x18026e781  lea     r8, aOnecoreBaseApp_86; "onecore\\base\\appmodel\\StateRepositor"...
0x18026e788  mov     r9d, eax; char *
0x18026e78b  mov     edx, 255h; void *
0x18026e790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e795  mov     rcx, [rbp+5Fh]; this
0x18026e799  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18026e7a0  mov     r9d, edi; char *
0x18026e7a3  mov     edx, 1E8h; void *
0x18026e7a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e7ad  mov     rcx, [rsp+110h+var_E0]
0x18026e7b2  mov     [rsp+110h+var_E0], r15
0x18026e7b7  test    rcx, rcx
0x18026e7ba  jz      short loc_18026E7C2
0x18026e7bc  call    cs:__imp_SRCacheContext_Close
0x18026e7c2  mov     ebx, edi
0x18026e7c4  jmp     loc_18026E922
0x18026e7c9  xorps   xmm0, xmm0
0x18026e7cc  mov     [rbp+57h+arg_0], r15b
0x18026e7d0  xorps   xmm1, xmm1
0x18026e7d3  lea     r9, [rbp+57h+arg_0]
0x18026e7d7  lea     r8, [rbp+57h+var_C8]
0x18026e7db  lea     rcx, [rsp+110h+var_E0]
0x18026e7e0  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x18026e7e5  movdqu  [rbp+57h+var_B8], xmm1
0x18026e7ea  call    ?Get@PackageExternalLocationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageExternalLocation_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocationIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18026e7ef  mov     edi, eax
0x18026e7f1  test    eax, eax
0x18026e7f3  jns     short loc_18026E822
0x18026e7f5  mov     rcx, [rbp+5Fh]; this
0x18026e7f9  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18026e800  mov     r9d, eax; char *
0x18026e803  mov     edx, 1EBh; void *
0x18026e808  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e80d  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x18026e811  mov     qword ptr [rbp+57h+var_B8+8], r15
0x18026e815  test    rcx, rcx
0x18026e818  jz      short loc_18026E7AD
0x18026e81a  call    cs:__imp_SRCache_Free
0x18026e820  jmp     short loc_18026E7AD
0x18026e822  mov     rdi, r15
0x18026e825  cmp     [rbp+57h+arg_0], r15b
0x18026e829  jz      loc_18026E930
0x18026e82f  mov     r9, [rbp+57h+var_C8]; char *
0x18026e833  lea     rax, [rbp+57h+arg_0]
0x18026e837  xorps   xmm0, xmm0
0x18026e83a  mov     [rsp+110h+var_F0], rax; int
0x18026e83f  xorps   xmm1, xmm1
0x18026e842  mov     [rbp+57h+var_40], r15
0x18026e846  xor     r8d, r8d; char *
0x18026e849  lea     rdx, aSelectExistsSe_266; "SELECT EXISTS(SELECT 1 FROM CachePackag"...
0x18026e850  mov     rcx, r12; this
0x18026e853  movdqu  [rbp+57h+var_60], xmm0
0x18026e858  movdqu  [rbp+57h+var_50], xmm1
0x18026e85d  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18026e862  mov     esi, eax
0x18026e864  test    eax, eax
0x18026e866  js      short loc_18026E8BF
0x18026e868  cmp     [rbp+57h+arg_0], r15b
0x18026e86c  jnz     short loc_18026E887
0x18026e86e  mov     rdx, [rbp+57h+var_C8]; __int64
0x18026e872  lea     rcx, [rbp+57h+var_98]; this
0x18026e876  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026e87b  mov     esi, eax
0x18026e87d  test    eax, eax
0x18026e87f  js      short loc_18026E8B1
0x18026e881  inc     rdi
0x18026e884  inc     rbx
0x18026e887  inc     [rsp+110h+var_D8]
0x18026e88b  lea     r9, [rbp+57h+arg_0]
0x18026e88f  lea     r8, [rbp+57h+var_C8]
0x18026e893  lea     rcx, [rsp+110h+var_E0]
0x18026e898  call    ?Get@PackageExternalLocationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageExternalLocation_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocationIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18026e89d  mov     esi, eax
0x18026e89f  test    eax, eax
0x18026e8a1  js      short loc_18026E8B8
0x18026e8a3  lea     rcx, [rbp+57h+var_50+8]; this
0x18026e8a7  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026e8ac  jmp     loc_18026E825
0x18026e8b1  mov     edx, 1F4h
0x18026e8b6  jmp     short loc_18026E8DC
0x18026e8b8  mov     edx, 1F6h
0x18026e8bd  jmp     short loc_18026E8DC
0x18026e8bf  mov     rcx, [rbp+5Fh]; this
0x18026e8c3  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18026e8ca  mov     r9d, esi; char *
0x18026e8cd  mov     edx, 52h ; 'R'; void *
0x18026e8d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e8d7  mov     edx, 1EFh; void *
0x18026e8dc  mov     rcx, [rbp+5Fh]; this
0x18026e8e0  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18026e8e7  mov     r9d, esi; char *
0x18026e8ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026e8ef  lea     rcx, [rbp+57h+var_50+8]; this
0x18026e8f3  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026e8f8  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x18026e8fc  mov     qword ptr [rbp+57h+var_B8+8], r15
0x18026e900  test    rcx, rcx
0x18026e903  jz      short loc_18026E90B
0x18026e905  call    cs:__imp_SRCache_Free
0x18026e90b  mov     rcx, [rsp+110h+var_E0]
0x18026e910  mov     [rsp+110h+var_E0], r15
0x18026e915  test    rcx, rcx
0x18026e918  jz      short loc_18026E920
0x18026e91a  call    cs:__imp_SRCacheContext_Close
0x18026e920  mov     ebx, esi
0x18026e922  lea     rcx, [rbp+57h+var_98]; this
0x18026e926  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026e92b  jmp     loc_18026E9BD
0x18026e930  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x18026e934  mov     qword ptr [rbp+57h+var_B8+8], r15
0x18026e938  test    rcx, rcx
0x18026e93b  jz      short loc_18026E943
0x18026e93d  call    cs:__imp_SRCache_Free
0x18026e943  mov     rcx, [rsp+110h+var_E0]
0x18026e948  mov     [rsp+110h+var_E0], r15
0x18026e94d  test    rcx, rcx
0x18026e950  jz      short loc_18026E958
0x18026e952  call    cs:__imp_SRCacheContext_Close
0x18026e958  test    rdi, rdi
0x18026e95b  jz      short loc_18026E985
0x18026e95d  test    cs:byte_1804DF881, 20h
  ... truncated ...
```
