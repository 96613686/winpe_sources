# UnionFs::UfsTombstoneManager::DeserializePayload(UnionFs::UfsUnionCtx &,UnionFs::UFS_PAYLOAD_INFORMATION const &,utl::shared_ptr<UnionFs::UfsTablePayload> &,UnionFs::StackEventTracer &)

- ea: `0x14005b4d0`
- end: `0x14005bc06`
- name: `?DeserializePayload@UfsTombstoneManager@UnionFs@@EEBAJAEAVUfsUnionCtx@2@AEBUUFS_PAYLOAD_INFORMATION@2@AEAV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `1846`
- prototype: `__int64 __fastcall(int, int, int, int, struct UnionFs::StackEventTracer *)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140001008`
- `0x140001b64`
- `0x140001c08`
- `0x14000f7fc`
- `0x140036128`
- `0x140041040`
- `0x140043bdc`
- `0x140043dc0`
- `0x140056afc`
- `0x14005ac38`
- `0x14005b4d0`
- `0x140079a24`
- `0x140079c48`
- `0x140079da0`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005b68b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b935`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b95f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005baee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bb18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bb8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bbb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b68b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b935`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b95f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005baee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bb18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bb8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bbb7`

## string_xrefs

- `0x14005b63f`: `PUSH: Combining scratchRootPathWithVolume, payloadScratchPath`
- `0x14005b51d`: `UnionFs::UfsTombstoneManager::DeserializePayload`
- `0x14005b650`: `UnionFs::UfsTombstoneManager::DeserializePayload`
- `0x14005b761`: `UnionFs::UfsTombstoneManager::DeserializePayload`
- `0x14005b8f9`: `UnionFs::UfsTombstoneManager::DeserializePayload`
- `0x14005b9f3`: `UnionFs::UfsTombstoneManager::DeserializePayload`
- `0x14005baab`: `UnionFs::UfsTombstoneManager::DeserializePayload`
- `0x14005b8e8`: `PUSH: Allocating original path name`
- `0x14005b7bc`: `PayloadInfo paths`
- `0x14005b9fe`: `PayloadInfo original path`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsTombstoneManager::DeserializePayload(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        utl::_RefCountBase **a4,
        struct UnionFs::StackEventTracer *a5)
{
  unsigned __int64 *v8; // rdx
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  UnionFs::UfsLayerCtx *v11; // rdi
  unsigned __int16 NormalizedLayerRootPath; // si
  int v13; // edi
  struct _UNICODE_STRING *v14; // rdx
  struct _UNICODE_STRING *v15; // rbx
  struct _UNICODE_STRING *v17; // rbx
  int *v18; // r8
  unsigned __int16 v19; // r11
  PWSTR Buffer; // rdx
  USHORT Length; // r10
  PWSTR v22; // rcx
  USHORT v23; // r9
  char *v24; // rdi
  unsigned __int64 *v25; // rdx
  __int64 *v26; // rax
  volatile signed __int32 *v27; // rdi
  __int64 v28; // rsi
  unsigned int inited; // esi
  int v30; // r8d
  int v31; // r9d
  struct _UNICODE_STRING *v32; // rdx
  struct _UNICODE_STRING *v33; // rdi
  utl::_RefCountBase **v34; // rax
  __int64 v35; // r8
  utl::_RefCountBase *v36; // rax
  struct _UNICODE_STRING *v37; // rdx
  struct _UNICODE_STRING *v38; // rdx
  utl::_RefCountBase *v39; // rsi
  utl::_RefCountBase *v40; // rax
  utl::_RefCountBase *v41; // rcx
  char *v42; // [rsp+28h] [rbp-D8h]
  char v43; // [rsp+50h] [rbp-B0h] BYREF
  char v44; // [rsp+51h] [rbp-AFh]
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v46; // [rsp+60h] [rbp-A0h] BYREF
  FsFltWil::Details *v47; // [rsp+68h] [rbp-98h] BYREF
  utl::_RefCountBase *v48[2]; // [rsp+70h] [rbp-90h] BYREF
  char v49[8]; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v50; // [rsp+88h] [rbp-78h] BYREF
  const char *v51; // [rsp+98h] [rbp-68h] BYREF
  utl::_RefCountBase *v52; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING v53; // [rsp+A8h] [rbp-58h] BYREF
  const char *v54; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v55; // [rsp+C0h] [rbp-40h]
  char v56; // [rsp+D0h] [rbp-30h] BYREF
  const char *v57; // [rsp+F0h] [rbp-10h]
  __int64 v58; // [rsp+F8h] [rbp-8h]
  const char *v59; // [rsp+100h] [rbp+0h]
  __int64 v60; // [rsp+108h] [rbp+8h]
  const char *v61; // [rsp+110h] [rbp+10h]
  __int64 v62; // [rsp+118h] [rbp+18h]
  PVOID *p_P; // [rsp+120h] [rbp+20h]
  __int64 v64; // [rsp+128h] [rbp+28h]
  _DWORD *v65; // [rsp+130h] [rbp+30h]
  __int64 v66; // [rsp+138h] [rbp+38h]
  PWSTR v67; // [rsp+140h] [rbp+40h]
  _DWORD v68[2]; // [rsp+148h] [rbp+48h] BYREF
  _DWORD *v69; // [rsp+150h] [rbp+50h]
  __int64 v70; // [rsp+158h] [rbp+58h]
  PWSTR v71; // [rsp+160h] [rbp+60h]
  _DWORD v72[2]; // [rsp+168h] [rbp+68h] BYREF
  _DWORD *v73; // [rsp+170h] [rbp+70h]
  __int64 v74; // [rsp+178h] [rbp+78h]
  int *v75; // [rsp+180h] [rbp+80h]
  _DWORD v76[2]; // [rsp+188h] [rbp+88h] BYREF
  PVOID *v77; // [rsp+190h] [rbp+90h]
  __int64 v78; // [rsp+198h] [rbp+98h]

  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x80000008000LL) != 0
    && (qword_14009E190 & 0x80000008000LL) == qword_14009E190 )
  {
    *(_QWORD *)v49 = "UnionFs::UfsTombstoneManager::DeserializePayload";
    v47 = (FsFltWil::Details *)"ENTER";
    LODWORD(v46) = 417;
    P = "onecore\\base\\fs\\unionfs\\sys\\tombstonemanager.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)&dword_140099014,
      0x8000,
      (unsigned int)"onecore\\base\\fs\\unionfs\\sys\\tombstonemanager.cpp",
      (__int64)&v47,
      (__int64)v49,
      (__int64)&P,
      (__int64)&v46);
  }
  v44 = 1;
  v53 = 0;
  FsFltWil::AcquirePushLockShared(&v47, a2 + 72);
  v9 = *(_QWORD *)(a2 + 48);
  v10 = *(volatile signed __int32 **)(v9 + 8);
  v11 = *(UnionFs::UfsLayerCtx **)v9;
  if ( v10 )
    _InterlockedIncrement(v10 + 2);
  if ( v47 )
    FsFltWil::Details::ReleasePushLockShared(v47, v8);
  NormalizedLayerRootPath = UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(v11, &v53, 1);
  if ( v10 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v10);
  v50.Length = *(_WORD *)(a3 + 6);
  v50.MaximumLength = v50.Length;
  *(_DWORD *)(&v50.MaximumLength + 1) = 0;
  v50.Buffer = (PWSTR)(a3 + 16);
  P = 0;
  v13 = UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(&v53, &v50, a5);
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      (int)a5,
      (struct UnionFs::StackEventTracer *)0x363001F01BELL,
      (unsigned __int64)"UnionFs::UfsTombstoneManager::DeserializePayload",
      "PUSH: Combining scratchRootPathWithVolume, payloadScratchPath",
      v42);
    v15 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v15, v14);
      ExFreePoolWithTag(v15, 0);
    }
    if ( v44 )
    {
      v44 = 0;
      lambda_5b245752e8f3b4e8ac0321749780f77a_::operator()(&v43);
    }
    return (unsigned int)v13;
  }
  v17 = (struct _UNICODE_STRING *)P;
  v55 = *(_OWORD *)P;
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x8000) != 0
    && (qword_14009E190 & 0x8000) == qword_14009E190 )
  {
    v18 = (int *)*((_QWORD *)&v55 + 1);
    LOWORD(v46) = NormalizedLayerRootPath;
    if ( *((_QWORD *)&v55 + 1) )
    {
      v19 = v55;
    }
    else
    {
      v19 = 0;
      v18 = &dword_14007EEC4;
    }
    Buffer = v50.Buffer;
    if ( v50.Buffer )
    {
      Length = v50.Length;
    }
    else
    {
      Length = 0;
      Buffer = (PWSTR)&dword_14007EEC4;
    }
    v22 = v53.Buffer;
    if ( v53.Buffer )
    {
      v23 = v53.Length;
    }
    else
    {
      v23 = 0;
      v22 = (PWSTR)&dword_14007EEC4;
    }
    v67 = v22;
    v77 = &v46;
    v75 = v18;
    v73 = v76;
    v76[0] = v19;
    v69 = v72;
    v72[0] = Length;
    v65 = v68;
    v68[0] = v23;
    p_P = &P;
    v61 = "onecore\\base\\fs\\unionfs\\sys\\tombstonemanager.cpp";
    v57 = "PayloadInfo paths";
    v71 = Buffer;
    v59 = "UnionFs::UfsTombstoneManager::DeserializePayload";
    v42 = &v56;
    LODWORD(P) = 454;
    v78 = 2;
    v74 = 2;
    v76[1] = 0;
    v70 = 2;
    v72[1] = 0;
    v66 = 2;
    v68[1] = 0;
    v64 = 4;
    v62 = 49;
    v60 = 49;
    v58 = 18;
    tlgWriteTransfer_EtwWriteTransfer(&dword_14009E178, &unk_140098E40, 0, 0, 13);
  }
  v24 = 0;
  v46 = 0;
  if ( *(_WORD *)(a3 + 4) == 4 )
  {
    LOWORD(v48[0]) = *(_WORD *)(a3 + 8);
    WORD1(v48[0]) = v48[0];
    HIDWORD(v48[0]) = 0;
    v48[1] = (utl::_RefCountBase *)(a3 + *(unsigned int *)(a3 + 12));
    FsFltWil::AcquirePushLockShared(&v47, a2 + 72);
    v26 = *(__int64 **)(a2 + 48);
    v27 = (volatile signed __int32 *)v26[1];
    v28 = *v26;
    if ( v27 )
      _InterlockedIncrement(v27 + 2);
    if ( v47 )
      FsFltWil::Details::ReleasePushLockShared(v47, v25);
    inited = UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(*(_QWORD *)(v28 + 16), v48, &v46, a5);
    if ( v27 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v27);
    if ( (inited & 0x80000000) != 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)inited,
        (int)a5,
        (struct UnionFs::StackEventTracer *)0x36A001F01DBLL,
        (unsigned __int64)"UnionFs::UfsTombstoneManager::DeserializePayload",
        "PUSH: Allocating original path name",
        v42);
      v33 = (struct _UNICODE_STRING *)v46;
      if ( v46 )
      {
        if ( !*((_BYTE *)v46 + 16) )
          *(_OWORD *)v46 = 0;
        FsFltWil::Details::FreeUnicodeString(v33, v32);
        ExFreePoolWithTag(v33, 0);
      }
      if ( v17 )
      {
        if ( !LOBYTE(v17[1].Length) )
          *v17 = 0;
        FsFltWil::Details::FreeUnicodeString(v17, v32);
        ExFreePoolWithTag(v17, 0);
      }
      if ( !v44 )
        return inited;
      v44 = 0;
LABEL_50:
      lambda_5b245752e8f3b4e8ac0321749780f77a_::operator()(&v43);
      return inited;
    }
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x8000) != 0
      && (qword_14009E190 & 0x8000) == qword_14009E190 )
    {
      v34 = v48;
      LODWORD(P) = 479;
      if ( !v48[1] )
        v34 = (utl::_RefCountBase **)&FsTlEmptyUnicodeString;
      v47 = (FsFltWil::Details *)v34;
      *(_QWORD *)v49 = "onecore\\base\\fs\\unionfs\\sys\\tombstonemanager.cpp";
      v54 = "UnionFs::UfsTombstoneManager::DeserializePayload";
      v51 = "PayloadInfo original path";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
        (unsigned int)&FsTlEmptyUnicodeString,
        (unsigned int)word_140098DEA,
        v30,
        v31,
        (__int64)&v51,
        (__int64)&v54,
        (__int64)v49,
        (__int64)&P,
        (__int64)&v47);
    }
    v24 = (char *)v46;
  }
  v35 = *(unsigned __int16 *)(a3 + 4);
  v36 = *(utl::_RefCountBase **)a2;
  *(_OWORD *)v48 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v36 + 2);
  v52 = *(utl::_RefCountBase **)a2;
  v51 = (const char *)a2;
  inited = UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone(&v51, v17, v35, v48, a5);
  if ( v52 )
    utl::_RefCountBase::_DecStrong(v52);
  if ( (inited & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)inited,
      (int)a5,
      (struct UnionFs::StackEventTracer *)0x2C0001F01EDLL,
      (unsigned __int64)"UnionFs::UfsTombstoneManager::DeserializePayload",
      "PUSH: Allocating tombstone",
      v24);
    if ( v48[1] )
      utl::_RefCountBase::_DecStrong(v48[1]);
    if ( v24 )
    {
      if ( !v24[16] )
        *(_OWORD *)v24 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v24, v38);
      ExFreePoolWithTag(v24, 0);
    }
    if ( v17 )
    {
      if ( !LOBYTE(v17[1].Length) )
        *v17 = 0;
      FsFltWil::Details::FreeUnicodeString(v17, v38);
      ExFreePoolWithTag(v17, 0);
    }
    if ( !v44 )
      return inited;
    v44 = 0;
    goto LABEL_50;
  }
  v39 = v48[1];
  v40 = v48[0];
  if ( v48[1] )
    _InterlockedIncrement((volatile signed __int32 *)v48[1] + 2);
  v41 = a4[1];
  *a4 = v40;
  a4[1] = v39;
  if ( v41 )
    utl::_RefCountBase::_DecStrong(v41);
  if ( v39 )
    utl::_RefCountBase::_DecStrong(v39);
  if ( v24 )
  {
    if ( !v24[16] )
      *(_OWORD *)v24 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v24, v37);
    ExFreePoolWithTag(v24, 0);
  }
  if ( v17 )
  {
    if ( !LOBYTE(v17[1].Length) )
      *v17 = 0;
    FsFltWil::Details::FreeUnicodeString(v17, v37);
    ExFreePoolWithTag(v17, 0);
  }
  if ( v44 )
  {
    v44 = 0;
    lambda_5b245752e8f3b4e8ac0321749780f77a_::operator()(&v43);
  }
  return 0;
}

```

## disassembly

```asm
0x14005b4d0  mov     [rsp-8+arg_0], rbx
0x14005b4d5  push    rbp
0x14005b4d6  push    rsi
0x14005b4d7  push    rdi
0x14005b4d8  push    r12
0x14005b4da  push    r13
0x14005b4dc  push    r14
0x14005b4de  push    r15
0x14005b4e0  lea     rbp, [rsp-0B0h]
0x14005b4e8  sub     rsp, 1B0h
0x14005b4ef  mov     rax, cs:__security_cookie
0x14005b4f6  xor     rax, rsp
0x14005b4f9  mov     [rbp+0E0h+var_40], rax
0x14005b500  mov     eax, cs:dword_14009E178
0x14005b506  mov     r13, r9
0x14005b509  mov     r14, [rbp+0E0h+arg_20]
0x14005b510  mov     r12, rdx
0x14005b513  lea     r9, aOnecoreBaseFsU_0; "onecore\\base\\fs\\unionfs\\sys\\tombst"...
0x14005b51a  mov     r15, r8
0x14005b51d  lea     rdx, aUnionfsUfstomb_5; "UnionFs::UfsTombstoneManager::Deseriali"...
0x14005b524  cmp     eax, 5
0x14005b527  jbe     short loc_14005B5A1
0x14005b529  mov     rcx, cs:qword_14009E190
0x14005b530  mov     r8, 80000008000h
0x14005b53a  mov     rax, cs:qword_14009E188
0x14005b541  test    r8, rax
0x14005b544  jz      short loc_14005B5A1
0x14005b546  mov     rax, rcx
0x14005b549  and     rax, r8
0x14005b54c  cmp     rax, rcx
0x14005b54f  jnz     short loc_14005B5A1
0x14005b551  lea     rax, aEnter; "ENTER"
0x14005b558  mov     qword ptr [rbp+0E0h+var_160], rdx
0x14005b55c  mov     [rsp+1E0h+var_178], rax
0x14005b561  lea     rdx, dword_140099014
0x14005b568  lea     rax, [rsp+1E0h+var_180]
0x14005b56d  mov     dword ptr [rsp+1E0h+var_180], 1A1h
0x14005b575  mov     [rsp+1E0h+var_1A8], rax
0x14005b57a  lea     rax, [rsp+1E0h+P]
0x14005b57f  mov     [rsp+1E0h+var_1B0], rax
0x14005b584  lea     rax, [rbp+0E0h+var_160]
0x14005b588  mov     [rsp+1E0h+var_1B8], rax; char *
0x14005b58d  lea     rax, [rsp+1E0h+var_178]
0x14005b592  mov     [rsp+1E0h+var_1C0], rax
0x14005b597  mov     [rsp+1E0h+P], r9
0x14005b59c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14005b5a1  xorps   xmm0, xmm0
0x14005b5a4  mov     [rsp+1E0h+var_18F], 1
0x14005b5a9  lea     rdx, [r12+48h]
0x14005b5ae  lea     rcx, [rsp+1E0h+var_178]
0x14005b5b3  movups  xmmword ptr [rbp+0E0h+var_138.Length], xmm0
0x14005b5b7  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14005b5bc  mov     rax, [r12+30h]
0x14005b5c1  mov     rbx, [rax+8]
0x14005b5c5  mov     rdi, [rax]
0x14005b5c8  test    rbx, rbx
0x14005b5cb  jz      short loc_14005B5D1
0x14005b5cd  lock inc dword ptr [rbx+8]
0x14005b5d1  mov     rcx, [rsp+1E0h+var_178]; this
0x14005b5d6  test    rcx, rcx
0x14005b5d9  jz      short loc_14005B5E0
0x14005b5db  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14005b5e0  mov     r8b, 1; bool
0x14005b5e3  lea     rdx, [rbp+0E0h+var_138]; struct _UNICODE_STRING *
0x14005b5e7  mov     rcx, rdi; this
0x14005b5ea  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x14005b5ef  movzx   esi, ax
0x14005b5f2  test    rbx, rbx
0x14005b5f5  jz      short loc_14005B5FF
0x14005b5f7  mov     rcx, rbx; this
0x14005b5fa  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14005b5ff  movzx   ecx, word ptr [r15+6]
0x14005b604  lea     r9, [rsp+1E0h+P]
0x14005b609  mov     [rbp+0E0h+var_158.Length], cx
0x14005b60d  lea     rdx, [rbp+0E0h+var_158]; struct _UNICODE_STRING *
0x14005b611  mov     [rbp+0E0h+var_158.MaximumLength], cx
0x14005b615  xor     eax, eax
0x14005b617  lea     rcx, [r15+10h]
0x14005b61b  mov     dword ptr [rbp+0E0h+var_158+4], eax
0x14005b61e  mov     [rbp+0E0h+var_158.Buffer], rcx
0x14005b622  movzx   r8d, si
0x14005b626  lea     rcx, [rbp+0E0h+var_138]; struct _UNICODE_STRING *
0x14005b62a  mov     [rsp+1E0h+P], rax
0x14005b62f  mov     [rsp+1E0h+var_1C0], r14; struct UnionFs::StackEventTracer *
0x14005b634  call    ?AllocAndInitWithCombinedPaths@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@0GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14005b639  mov     edi, eax
0x14005b63b  test    eax, eax
0x14005b63d  jns     short loc_14005B6B4
0x14005b63f  lea     rax, aPushCombiningS_2; "PUSH: Combining scratchRootPathWithVolu"...
0x14005b646  mov     r8, 363001F01BEh; struct UnionFs::StackEventTracer *
0x14005b650  lea     r9, aUnionfsUfstomb_5; "UnionFs::UfsTombstoneManager::Deseriali"...
0x14005b657  mov     [rsp+1E0h+var_1C0], rax; char *
0x14005b65c  mov     rdx, r14; int
0x14005b65f  mov     ecx, edi; this
0x14005b661  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005b666  mov     rbx, [rsp+1E0h+P]
0x14005b66b  xor     esi, esi
0x14005b66d  test    rbx, rbx
0x14005b670  jz      short loc_14005B697
0x14005b672  cmp     [rbx+10h], sil
0x14005b676  jnz     short loc_14005B67E
0x14005b678  xorps   xmm0, xmm0
0x14005b67b  movups  xmmword ptr [rbx], xmm0
0x14005b67e  mov     rcx, rbx; UnicodeString
0x14005b681  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14005b686  xor     edx, edx; Tag
0x14005b688  mov     rcx, rbx; P
0x14005b68b  call    cs:__imp_ExFreePoolWithTag
0x14005b692  nop     dword ptr [rax+rax+00h]
0x14005b697  cmp     [rsp+1E0h+var_18F], sil
0x14005b69c  jz      short loc_14005B6AD
0x14005b69e  lea     rcx, [rsp+1E0h+var_190]
0x14005b6a3  mov     [rsp+1E0h+var_18F], sil
0x14005b6a8  call    _lambda_5b245752e8f3b4e8ac0321749780f77a___operator__
0x14005b6ad  mov     eax, edi
0x14005b6af  jmp     loc_14005BBDB
0x14005b6b4  mov     rbx, [rsp+1E0h+P]
0x14005b6b9  mov     edx, 8000h
0x14005b6be  mov     eax, cs:dword_14009E178
0x14005b6c4  mov     r8d, 4
0x14005b6ca  movups  xmm0, xmmword ptr [rbx]
0x14005b6cd  movdqu  [rbp+0E0h+var_120], xmm0
0x14005b6d2  cmp     eax, 5
0x14005b6d5  jbe     loc_14005B852
0x14005b6db  mov     rcx, cs:qword_14009E190
0x14005b6e2  mov     rax, cs:qword_14009E188
0x14005b6e9  test    rdx, rax
0x14005b6ec  jz      loc_14005B852
0x14005b6f2  mov     rax, rcx
0x14005b6f5  and     rax, rdx
0x14005b6f8  cmp     rax, rcx
0x14005b6fb  jnz     loc_14005B852
0x14005b701  mov     r8, qword ptr [rbp+0E0h+var_120+8]
0x14005b705  mov     rax, cs:off_14007ED98
0x14005b70c  mov     word ptr [rsp+1E0h+var_180], si
0x14005b711  xor     esi, esi
0x14005b713  test    r8, r8
0x14005b716  jz      short loc_14005B71F
0x14005b718  movzx   r11d, word ptr [rbp+0E0h+var_120]
0x14005b71d  jmp     short loc_14005B725
0x14005b71f  mov     r11d, esi
0x14005b722  mov     r8, rax
0x14005b725  mov     rdx, [rbp+0E0h+var_158.Buffer]
0x14005b729  test    rdx, rdx
0x14005b72c  jz      short loc_14005B735
0x14005b72e  movzx   r10d, [rbp+0E0h+var_158.Length]
0x14005b733  jmp     short loc_14005B73B
0x14005b735  mov     r10d, esi
0x14005b738  mov     rdx, rax
0x14005b73b  mov     rcx, [rbp+0E0h+var_138.Buffer]
0x14005b73f  test    rcx, rcx
0x14005b742  jz      short loc_14005B74B
0x14005b744  movzx   r9d, [rbp+0E0h+var_138.Length]
0x14005b749  jmp     short loc_14005B751
0x14005b74b  mov     r9d, esi
0x14005b74e  mov     rcx, rax
0x14005b751  mov     [rbp+0E0h+var_A0], rcx
0x14005b755  lea     rax, [rsp+1E0h+var_180]
0x14005b75a  mov     [rbp+0E0h+var_50], rax
0x14005b761  lea     rcx, aUnionfsUfstomb_5; "UnionFs::UfsTombstoneManager::Deseriali"...
0x14005b768  lea     rax, [rbp+0E0h+var_58]
0x14005b76f  mov     [rbp+0E0h+var_60], r8
0x14005b776  mov     [rbp+0E0h+var_70], rax
0x14005b77a  xor     r8d, r8d
0x14005b77d  movzx   eax, r11w
0x14005b781  mov     [rbp+0E0h+var_58], eax
0x14005b787  lea     rax, [rbp+0E0h+var_78]
0x14005b78b  mov     [rbp+0E0h+var_90], rax
0x14005b78f  movzx   eax, r10w
0x14005b793  mov     [rbp+0E0h+var_78], eax
0x14005b796  lea     rax, [rbp+0E0h+var_98]
0x14005b79a  mov     [rbp+0E0h+var_B0], rax
0x14005b79e  movzx   eax, r9w
0x14005b7a2  xor     r9d, r9d
0x14005b7a5  mov     [rbp+0E0h+var_98], eax
0x14005b7a8  lea     rax, [rsp+1E0h+P]
0x14005b7ad  mov     [rbp+0E0h+var_C0], rax
0x14005b7b1  lea     rax, aOnecoreBaseFsU_0; "onecore\\base\\fs\\unionfs\\sys\\tombst"...
0x14005b7b8  mov     [rbp+0E0h+var_D0], rax
0x14005b7bc  lea     rax, aPayloadinfoPat; "PayloadInfo paths"
0x14005b7c3  mov     [rbp+0E0h+var_F0], rax
0x14005b7c7  lea     rax, [rbp+0E0h+var_110]
0x14005b7cb  mov     [rbp+0E0h+var_80], rdx
0x14005b7cf  lea     rdx, unk_140098E40
0x14005b7d6  mov     [rbp+0E0h+var_E0], rcx
0x14005b7da  lea     rcx, dword_14009E178
0x14005b7e1  mov     [rsp+1E0h+var_1B8], rax
0x14005b7e6  mov     dword ptr [rsp+1E0h+var_1C0], 0Dh
0x14005b7ee  mov     dword ptr [rsp+1E0h+P], 1C6h
0x14005b7f6  mov     [rbp+0E0h+var_48], 2
0x14005b801  mov     [rbp+0E0h+var_68], 2
0x14005b809  mov     [rbp+0E0h+var_54], esi
0x14005b80f  mov     [rbp+0E0h+var_88], 2
0x14005b817  mov     [rbp+0E0h+var_74], esi
0x14005b81a  mov     [rbp+0E0h+var_A8], 2
0x14005b822  mov     [rbp+0E0h+var_94], esi
0x14005b825  mov     [rbp+0E0h+var_B8], 4
0x14005b82d  mov     [rbp+0E0h+var_C8], 31h ; '1'
0x14005b835  mov     [rbp+0E0h+var_D8], 31h ; '1'
0x14005b83d  mov     [rbp+0E0h+var_E8], 12h
0x14005b845  call    _tlgWriteTransfer_EtwWriteTransfer
0x14005b84a  mov     r8d, 4
0x14005b850  jmp     short loc_14005B854
0x14005b852  xor     esi, esi
0x14005b854  mov     rdi, rsi
0x14005b857  mov     [rsp+1E0h+var_180], rsi
0x14005b85c  cmp     [r15+4], r8w
0x14005b861  jnz     loc_14005BA42
0x14005b867  movzx   eax, word ptr [r15+8]
0x14005b86c  lea     rdx, [r12+48h]
0x14005b871  mov     word ptr [rsp+1E0h+var_170], ax
0x14005b876  lea     rcx, [rsp+1E0h+var_178]
0x14005b87b  mov     word ptr [rsp+1E0h+var_170+2], ax
0x14005b880  xor     eax, eax
0x14005b882  mov     dword ptr [rsp+1E0h+var_170+4], eax
0x14005b886  mov     eax, [r15+0Ch]
0x14005b88a  add     rax, r15
0x14005b88d  mov     [rsp+1E0h+var_170+8], rax
0x14005b892  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14005b897  mov     rax, [r12+30h]
0x14005b89c  mov     rdi, [rax+8]
0x14005b8a0  mov     rsi, [rax]
0x14005b8a3  test    rdi, rdi
0x14005b8a6  jz      short loc_14005B8AC
0x14005b8a8  lock inc dword ptr [rdi+8]
0x14005b8ac  mov     rcx, [rsp+1E0h+var_178]; this
0x14005b8b1  test    rcx, rcx
0x14005b8b4  jz      short loc_14005B8BB
0x14005b8b6  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14005b8bb  mov     rcx, [rsi+10h]
0x14005b8bf  lea     r8, [rsp+1E0h+var_180]
0x14005b8c4  mov     r9, r14
0x14005b8c7  lea     rdx, [rsp+1E0h+var_170]
0x14005b8cc  call    ?AllocAndInitWithCombinedPaths@UfsPathName@UnionFs@@SAJAEBV12@AEBU_UNICODE_STRING@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(UnionFs::UfsPathName const &,_UNICODE_STRING const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14005b8d1  mov     esi, eax
0x14005b8d3  test    rdi, rdi
0x14005b8d6  jz      short loc_14005B8E0
0x14005b8d8  mov     rcx, rdi; this
0x14005b8db  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14005b8e0  test    esi, esi
0x14005b8e2  jns     loc_14005B988
0x14005b8e8  lea     rax, aPushAllocating_36; "PUSH: Allocating original path name"
0x14005b8ef  mov     r8, 36A001F01DBh; struct UnionFs::StackEventTracer *
0x14005b8f9  lea     r9, aUnionfsUfstomb_5; "UnionFs::UfsTombstoneManager::Deseriali"...
0x14005b900  mov     [rsp+1E0h+var_1C0], rax; char *
0x14005b905  mov     rdx, r14; int
0x14005b908  mov     ecx, esi; this
0x14005b90a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005b90f  mov     rdi, [rsp+1E0h+var_180]
0x14005b914  xor     r14d, r14d
0x14005b917  test    rdi, rdi
0x14005b91a  jz      short loc_14005B941
0x14005b91c  cmp     [rdi+10h], r14b
0x14005b920  jnz     short loc_14005B928
0x14005b922  xorps   xmm0, xmm0
0x14005b925  movups  xmmword ptr [rdi], xmm0
0x14005b928  mov     rcx, rdi; UnicodeString
0x14005b92b  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14005b930  xor     edx, edx; Tag
0x14005b932  mov     rcx, rdi; P
0x14005b935  call    cs:__imp_ExFreePoolWithTag
0x14005b93c  nop     dword ptr [rax+rax+00h]
0x14005b941  test    rbx, rbx
0x14005b944  jz      short loc_14005B96B
0x14005b946  cmp     [rbx+10h], r14b
0x14005b94a  jnz     short loc_14005B952
0x14005b94c  xorps   xmm0, xmm0
0x14005b94f  movups  xmmword ptr [rbx], xmm0
0x14005b952  mov     rcx, rbx; UnicodeString
0x14005b955  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14005b95a  xor     edx, edx; Tag
0x14005b95c  mov     rcx, rbx; P
0x14005b95f  call    cs:__imp_ExFreePoolWithTag
0x14005b966  nop     dword ptr [rax+rax+00h]
0x14005b96b  cmp     [rsp+1E0h+var_18F], r14b
0x14005b970  jz      short loc_14005B981
0x14005b972  mov     [rsp+1E0h+var_18F], r14b
0x14005b977  lea     rcx, [rsp+1E0h+var_190]
0x14005b97c  call    _lambda_5b245752e8f3b4e8ac0321749780f77a___operator__
0x14005b981  mov     eax, esi
0x14005b983  jmp     loc_14005BBDB
0x14005b988  mov     eax, cs:dword_14009E178
0x14005b98e  cmp     eax, 5
0x14005b991  jbe     loc_14005BA3D
0x14005b997  mov     rcx, cs:qword_14009E190
0x14005b99e  mov     edx, 8000h
0x14005b9a3  mov     rax, cs:qword_14009E188
0x14005b9aa  test    rdx, rax
0x14005b9ad  jz      loc_14005BA3D
0x14005b9b3  mov     rax, rcx
0x14005b9b6  and     rax, rdx
0x14005b9b9  cmp     rax, rcx
0x14005b9bc  jnz     short loc_14005BA3D
0x14005b9be  cmp     [rsp+1E0h+var_170+8], 0
0x14005b9c4  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x14005b9cb  lea     rax, [rsp+1E0h+var_170]
0x14005b9d0  mov     dword ptr [rsp+1E0h+P], 1DFh
0x14005b9d8  cmovz   rax, rcx
0x14005b9dc  lea     rdx, word_140098DEA
0x14005b9e3  mov     [rsp+1E0h+var_178], rax
  ... truncated ...
```
