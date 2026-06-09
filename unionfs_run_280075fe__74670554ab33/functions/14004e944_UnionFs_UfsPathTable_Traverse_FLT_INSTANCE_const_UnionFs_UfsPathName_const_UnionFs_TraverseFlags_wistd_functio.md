# UnionFs::UfsPathTable::Traverse(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::TraverseFlags,wistd::function<long (UnionFs::UfsPathTierNode &,UnionFs::UfsPathTierNode *,UnionFs::UFS_TABLE_TRAVERSE_CTX &)> const &,UnionFs::StackEventTracer &)

- ea: `0x14004e944`
- end: `0x14004f169`
- name: `?Traverse@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4TraverseFlags@2@AEBV?$function@$$A6AJAEAVUfsPathTierNode@UnionFs@@PEAV12@AEAUUFS_TABLE_TRAVERSE_CTX@2@@Z@wistd@@AEAVStackEventTracer@2@@Z`
- size: `2085`
- prototype: ``
- caller_count: `5`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001fe90`
- `0x140023b7c`
- `0x14003c3ec`
- `0x14004e794`
- `0x14005bcc0`

## callees

- `0x14000227c`
- `0x14000f7fc`
- `0x14003daf4`
- `0x14004e944`
- `0x14004f4ac`
- `0x14004f5d4`
- `0x14004fb60`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x1400790f0`
- `0x140079a6c`
- `0x140079ab4`
- `0x140079afc`
- `0x140079c48`
- `0x140079d0c`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004ec5f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004ec5f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004ea64`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004ec7f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004ea64`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004ec7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ead3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004eebd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ef64`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f0a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f118`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ead3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004eebd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ef64`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f0a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f118`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004eadf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004eec9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ef70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f0b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f124`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004eadf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004eec9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ef70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f0b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f124`

## string_xrefs

- `0x14004f0c3`: `ORIGIN: Table already run down`
- `0x14004ea8a`: `UnionFs::UfsPathTable::Traverse`
- `0x14004eb66`: `UnionFs::UfsPathTable::Traverse`
- `0x14004ed82`: `UnionFs::UfsPathTable::Traverse`
- `0x14004ee51`: `UnionFs::UfsPathTable::Traverse`
- `0x14004ef00`: `UnionFs::UfsPathTable::Traverse`
- `0x14004ef9a`: `UnionFs::UfsPathTable::Traverse`
- `0x14004f062`: `UnionFs::UfsPathTable::Traverse`
- `0x14004f0d6`: `UnionFs::UfsPathTable::Traverse`
- `0x14004f051`: `ORIGIN: Traversal on volume with no paths.`
- `0x14004ea79`: `API: Appending volume root to currentPath`
- `0x14004eeef`: `API: Appending \ to currentPath`
- `0x14004eedc`: `API: Appending path component to currentPath`
- `0x14004ef89`: `ORIGIN: StartingPath is not in the table`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathTable::Traverse(
        __int64 a1,
        __int64 a2,
        const char *a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  char v6; // r13
  struct _ERESOURCE *v10; // rbx
  __int64 v11; // rdx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v12; // rdx
  __int64 *i; // rdi
  struct _UNICODE_STRING *v14; // r8
  unsigned __int16 v15; // r9
  bool v16; // al
  __int64 v17; // r14
  volatile signed __int32 *v18; // rsi
  NTSTATUS appended; // esi
  struct _UNICODE_STRING *v20; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v21; // rdx
  __int64 v23; // rcx
  struct _UNICODE_STRING *v24; // rdx
  UnionFs::UfsPathTree *v25; // r13
  utl::_RefCountBase *v26; // rcx
  struct UnionFs::UfsPathTierNode *Node; // rdi
  volatile signed __int32 *v28; // r15
  UnionFs::UfsPathTree *v29; // r8
  volatile signed __int32 *v30; // r14
  const char *v31; // r15
  int v32; // eax
  NTSTATUS v33; // r15d
  struct _UNICODE_STRING *v34; // r8
  bool v35; // al
  UnionFs::UfsPathTree *v36; // rcx
  volatile signed __int32 *v37; // rdx
  utl::_RefCountBase *v38; // rcx
  __int64 v39; // rcx
  struct _UNICODE_STRING *v40; // rdx
  int v41; // r9d
  struct FsFltWil::Details::RundownRefCacheAware *v42; // rdx
  const char *v43; // rax
  __int64 v44; // r8
  struct FsFltWil::Details::RundownRefCacheAware *v45; // rdx
  struct _UNICODE_STRING *v46; // rdx
  int v47; // r8d
  int v48; // r9d
  const struct _UNICODE_STRING *v49; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v50; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v51; // rdx
  const char *v52; // [rsp+28h] [rbp-D8h]
  __int16 v53[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v54; // [rsp+44h] [rbp-BCh] BYREF
  struct _ERESOURCE *v55; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v57; // [rsp+60h] [rbp-A0h] BYREF
  const char *v58; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h]
  __int128 v60; // [rsp+80h] [rbp-80h] BYREF
  __int64 v61; // [rsp+90h] [rbp-70h] BYREF
  __int64 v62; // [rsp+98h] [rbp-68h]
  char v63; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING *p_Destination; // [rsp+A8h] [rbp-58h]
  __int128 v65; // [rsp+B0h] [rbp-50h]
  int v66; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING v67; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v68; // [rsp+148h] [rbp+48h]
  _QWORD v69[16]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v70; // [rsp+1D0h] [rbp+D0h]

  v6 = a4;
  v54 = a4;
  v58 = a3;
  v59 = a5;
  v10 = 0;
  if ( (a4 & 8) == 0 )
  {
    v11 = a1 + 32;
    if ( (a4 & 4) != 0 )
      FsFltWil::AcquireResourceExclusive(&v55, v11);
    else
      FsFltWil::AcquireResourceShared(&v55, v11);
    v10 = v55;
  }
  v12 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(a1 + 136);
  v68 = 0;
  FsFltWil::AcquireRundownReference(v69, v12);
  if ( !v69[0] )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED000ALL,
      a6,
      (struct UnionFs::StackEventTracer *)0x45200140B31LL,
      (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
      "ORIGIN: Table already run down",
      v52);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v69, v51);
    if ( v70 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
    return 3236757514LL;
  }
  for ( i = *(__int64 **)(a1 + 8); ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)(a1 + 8) )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000225LL,
        a6,
        (struct UnionFs::StackEventTracer *)0x31C00140B44LL,
        (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
        "ORIGIN: Traversal on volume with no paths.",
        v52);
LABEL_99:
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v69, v50);
      if ( v70 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
      if ( v10 )
      {
        ExReleaseResourceLite(v10);
        KeLeaveCriticalRegion();
      }
      return 3221226021LL;
    }
    if ( *(_QWORD *)i[3] == a2 )
      break;
  }
  FsFltWil::MakeUniqueUnicodeString(&Destination, *((unsigned __int16 *)i + 16), 1279685446);
  v14 = (struct _UNICODE_STRING *)*((unsigned __int16 *)a3 + 12);
  v57 = *(_OWORD *)a3;
  v67 = 0;
  v16 = UnionFs::Utils::WalkPath((UnionFs::Utils *)&v57, &v67, v14, v15);
  v17 = i[2];
  v18 = 0;
  LOBYTE(v53[0]) = v16;
  if ( !v67.Length )
  {
    appended = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)(v17 + 32));
    if ( appended < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)appended,
        a6,
        (struct UnionFs::StackEventTracer *)0x31D00140B5CLL,
        (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
        "API: Appending volume root to currentPath",
        v52);
LABEL_14:
      FsFltWil::Details::FreeUnicodeString(&Destination, v20);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v69, v21);
      if ( v70 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
      if ( v10 )
      {
        ExReleaseResourceLite(v10);
        KeLeaveCriticalRegion();
      }
      return (unsigned int)appended;
    }
    if ( (v6 & 2) == 0 )
    {
      p_Destination = &Destination;
      v61 = v59;
      v62 = a6;
      v23 = *(_QWORD *)(v59 + 112);
      v63 = 0;
      v66 = 0;
      v55 = 0;
      v65 = 0;
      if ( !v23 )
        wistd::__throw_bad_function_call(0);
      appended = (*(__int64 (__fastcall **)(__int64, __int64, struct _ERESOURCE **, __int64 *))(*(_QWORD *)v23 + 32LL))(
                   v23,
                   v17,
                   &v55,
                   &v61);
      if ( appended < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)appended,
          a6,
          (struct UnionFs::StackEventTracer *)0x31E00140B65LL,
          (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
          "PUSH: TraverseCallback on volume root node",
          v52);
        goto LABEL_14;
      }
      if ( (unsigned int)(v66 - 1) <= 1 )
        goto LABEL_72;
    }
    v25 = *(UnionFs::UfsPathTree **)(v17 + 48);
    v18 = *(volatile signed __int32 **)(v17 + 56);
    if ( (*(_DWORD *)a1 & 2) == 0 )
    {
      if ( v18 )
        _InterlockedIncrement(v18 + 2);
      if ( !UnionFs::UfsPathTree::IsEmpty(v25) )
        MicrosoftTelemetryAssertTriggeredMsgKM("volumeRootNode->GetDescendantTree()->IsEmpty()");
      goto LABEL_29;
    }
    if ( v18 )
      _InterlockedIncrement(v18 + 2);
    if ( v25 )
    {
      Node = 0;
      v28 = v18;
LABEL_65:
      if ( !UnionFs::UfsPathTree::IsEmpty(v25) )
      {
        v61 = v59;
        v62 = a6;
        p_Destination = &Destination;
        v63 = v41;
        v65 = 0;
        v66 = v41;
        appended = UnionFs::UfsPathTree::WalkTree(v25, (struct UnionFs::UFS_TABLE_TRAVERSE_CTX *)&v61, Node);
        if ( appended < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)appended,
            a6,
            (struct UnionFs::StackEventTracer *)0x31F00140BE6LL,
            (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
            "PUSH: Walking from starting location",
            v52);
          if ( v28 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v28);
          goto LABEL_14;
        }
      }
LABEL_69:
      if ( v28 )
      {
        v26 = (utl::_RefCountBase *)v28;
LABEL_71:
        utl::_RefCountBase::_DecStrong(v26);
      }
      goto LABEL_72;
    }
    v6 = v54;
  }
  v29 = *(UnionFs::UfsPathTree **)(v17 + 48);
  v30 = *(volatile signed __int32 **)(v17 + 56);
  v55 = (struct _ERESOURCE *)v29;
  if ( v30 )
    _InterlockedIncrement(v30 + 2);
  v31 = v58;
  v32 = v6 & 1;
  Node = 0;
  v54 = v32;
  while ( 2 )
  {
    *(_QWORD *)&v60 = Node;
    BYTE8(v57) = v32 != 0;
    *(_QWORD *)&v57 = &v67;
    *(_DWORD *)((char *)&v57 + 9) = 0;
    *(_WORD *)((char *)&v57 + 13) = 0;
    HIBYTE(v57) = 0;
    Node = UnionFs::UfsPathTree::FindNode(v29, (const struct UnionFs::UFS_COMPARE_KEY *)&v57);
    if ( !Node )
    {
      v57 = *(_OWORD *)(v31 + 40);
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000225LL,
        a6,
        (struct UnionFs::StackEventTracer *)0x17000140BD3LL,
        (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
        "ORIGIN: StartingPath is not in the table",
        v52);
      if ( (unsigned int)dword_14009E178 > 2 )
      {
        v49 = (const struct _UNICODE_STRING *)&v57;
        v54 = 368;
        if ( !*((_QWORD *)&v57 + 1) )
          v49 = &FsTlEmptyUnicodeString;
        v58 = "UnionFs::UfsPathTable::Traverse";
        *(_QWORD *)&v60 = v49;
        v53[0] = 3027;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapBuffer<_UNICODE_STRING>>(
          (unsigned int)&FsTlEmptyUnicodeString,
          (unsigned int)&unk_140097B70,
          v47,
          v48,
          (__int64)&v58,
          (__int64)&v54,
          (__int64)v53,
          (__int64)&v60);
      }
      if ( v30 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
      if ( v18 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v18);
      FsFltWil::Details::FreeUnicodeString(&Destination, v46);
      goto LABEL_99;
    }
    v33 = RtlAppendUnicodeToString(&Destination, L"\\");
    if ( v33 < 0 )
    {
      v43 = "API: Appending \\ to currentPath";
      v44 = 0x18200140B96LL;
      goto LABEL_79;
    }
    v33 = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)Node + 2);
    if ( v33 < 0 )
    {
      v43 = "API: Appending path component to currentPath";
      v44 = 0x18600140B9CLL;
LABEL_79:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v33,
        a6,
        (struct UnionFs::StackEventTracer *)v44,
        (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
        v43,
        v52);
      goto LABEL_80;
    }
    if ( LOBYTE(v53[0]) )
    {
      v31 = v58;
      v34 = (struct _UNICODE_STRING *)*((unsigned __int16 *)v58 + 12);
      v60 = *(_OWORD *)v58;
      v35 = UnionFs::Utils::WalkPath((UnionFs::Utils *)&v60, &v67, v34, 0);
      v36 = (UnionFs::UfsPathTree *)*((_QWORD *)Node + 6);
      LOBYTE(v53[0]) = v35;
      if ( !v36 )
        goto LABEL_48;
      v37 = (volatile signed __int32 *)*((_QWORD *)Node + 7);
      if ( v37 )
        _InterlockedIncrement(v37 + 2);
      v29 = v36;
      v55 = (struct _ERESOURCE *)v36;
      v38 = (utl::_RefCountBase *)v30;
      v30 = v37;
      if ( v38 )
      {
        utl::_RefCountBase::_DecStrong(v38);
LABEL_48:
        v29 = (UnionFs::UfsPathTree *)v55;
      }
      v32 = v54;
      continue;
    }
    break;
  }
  if ( (*((_DWORD *)Node + 6) & 1) != 0 || (v6 & 2) != 0 )
    goto LABEL_58;
  v61 = v59;
  p_Destination = &Destination;
  v39 = *(_QWORD *)(v59 + 112);
  v62 = a6;
  v63 = 0;
  v66 = 0;
  v65 = 0;
  if ( !v39 )
    wistd::__throw_bad_function_call(0);
  v33 = (*(__int64 (__fastcall **)(__int64, struct UnionFs::UfsPathTierNode *, __int128 *, __int64 *))(*(_QWORD *)v39 + 32LL))(
          v39,
          Node,
          &v60,
          &v61);
  if ( v33 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v33,
      a6,
      (struct UnionFs::StackEventTracer *)0x16900140BACLL,
      (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
      "PUSH: TraverseCallback on starting location",
      v52);
LABEL_80:
    if ( v30 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
    if ( v18 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v18);
    FsFltWil::Details::FreeUnicodeString(&Destination, v40);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v69, v45);
    if ( v70 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
    return (unsigned int)v33;
  }
  if ( (unsigned int)(v66 - 1) > 1 )
  {
LABEL_58:
    v28 = (volatile signed __int32 *)*((_QWORD *)Node + 7);
    v25 = (UnionFs::UfsPathTree *)*((_QWORD *)Node + 6);
    if ( v28 )
      _InterlockedIncrement(v28 + 2);
    if ( v18 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v18);
    if ( v30 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
    if ( v25 )
      goto LABEL_65;
    goto LABEL_69;
  }
  if ( v30 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
LABEL_29:
  if ( v18 )
  {
    v26 = (utl::_RefCountBase *)v18;
    goto LABEL_71;
  }
LABEL_72:
  FsFltWil::Details::FreeUnicodeString(&Destination, v24);
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v69, v42);
  if ( v70 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
  if ( v10 )
  {
    ExReleaseResourceLite(v10);
    KeLeaveCriticalRegion();
  }
  return 0;
}

```

## disassembly

```asm
0x14004e944  mov     [rsp-8+arg_8], rbx
0x14004e949  push    rbp
0x14004e94a  push    rsi
0x14004e94b  push    rdi
0x14004e94c  push    r12
0x14004e94e  push    r13
0x14004e950  push    r14
0x14004e952  push    r15
0x14004e954  lea     rbp, [rsp-0E0h]
0x14004e95c  sub     rsp, 1E0h
0x14004e963  mov     rax, cs:__security_cookie
0x14004e96a  xor     rax, rsp
0x14004e96d  mov     [rbp+110h+var_38], rax
0x14004e974  mov     rax, [rbp+110h+arg_20]
0x14004e97b  xor     edi, edi
0x14004e97d  mov     r12, qword ptr [rbp+110h+arg_28]
0x14004e984  mov     r13d, r9d
0x14004e987  mov     [rsp+210h+var_1CC], r9d
0x14004e98c  mov     r14, r8
0x14004e98f  mov     [rsp+210h+var_1A0], r8
0x14004e994  mov     rsi, rdx
0x14004e997  mov     [rsp+210h+var_198], rax
0x14004e99c  mov     r15, rcx
0x14004e99f  mov     ebx, edi
0x14004e9a1  test    r9b, 8
0x14004e9a5  jnz     short loc_14004E9C7
0x14004e9a7  lea     rdx, [rcx+20h]
0x14004e9ab  lea     rcx, [rsp+210h+var_1C8]
0x14004e9b0  test    r13b, 4
0x14004e9b4  jz      short loc_14004E9BD
0x14004e9b6  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x14004e9bb  jmp     short loc_14004E9C2
0x14004e9bd  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x14004e9c2  mov     rbx, [rsp+210h+var_1C8]
0x14004e9c7  mov     rdx, [r15+88h]; RunRefCacheAware
0x14004e9ce  lea     r9, [rbp+110h+var_138]
0x14004e9d2  mov     r8b, 1
0x14004e9d5  mov     [rbp+110h+var_C8], rdi
0x14004e9d9  lea     rcx, [rbp+110h+var_C0]; void *
0x14004e9dd  call    ?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z; FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)
0x14004e9e2  cmp     [rbp+110h+var_C0], rdi
0x14004e9e6  jz      loc_14004F0C3
0x14004e9ec  lea     rax, [r15+8]
0x14004e9f0  mov     rdi, [rax]
0x14004e9f3  cmp     rdi, rax
0x14004e9f6  jz      loc_14004F051
0x14004e9fc  mov     rcx, [rdi+18h]
0x14004ea00  cmp     [rcx], rsi
0x14004ea03  jz      short loc_14004EA0A
0x14004ea05  mov     rdi, [rdi]
0x14004ea08  jmp     short loc_14004E9F3
0x14004ea0a  movzx   edx, word ptr [rdi+20h]
0x14004ea0e  lea     rcx, [rsp+210h+Destination]
0x14004ea13  mov     r8d, 4C467346h
0x14004ea19  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14004ea1e  movups  xmm1, xmmword ptr [r14]
0x14004ea22  movzx   r8d, word ptr [r14+18h]; struct _UNICODE_STRING *
0x14004ea27  lea     rdx, [rbp+110h+var_148]; struct _UNICODE_STRING *
0x14004ea2b  xorps   xmm0, xmm0
0x14004ea2e  lea     rcx, [rsp+210h+var_1B0]; this
0x14004ea33  movdqu  [rsp+210h+var_1B0], xmm1
0x14004ea39  movups  xmmword ptr [rbp+110h+var_148.Length], xmm0
0x14004ea3d  call    ?WalkPath@Utils@UnionFs@@YA_NAEBU_UNICODE_STRING@@AEAU3@G@Z; UnionFs::Utils::WalkPath(_UNICODE_STRING const &,_UNICODE_STRING &,ushort)
0x14004ea42  mov     r14, [rdi+10h]
0x14004ea46  xor     r9d, r9d
0x14004ea49  mov     esi, r9d
0x14004ea4c  mov     byte ptr [rsp+210h+var_1D0], al
0x14004ea50  cmp     [rbp+110h+var_148.Length], r9w
0x14004ea55  jnz     loc_14004EBEE
0x14004ea5b  lea     rdx, [r14+20h]; Source
0x14004ea5f  lea     rcx, [rsp+210h+Destination]; Destination
0x14004ea64  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004ea6b  nop     dword ptr [rax+rax+00h]
0x14004ea70  xor     r9d, r9d
0x14004ea73  mov     esi, eax
0x14004ea75  test    eax, eax
0x14004ea77  jns     short loc_14004EAF2
0x14004ea79  lea     rax, aApiAppendingVo; "API: Appending volume root to currentPa"...
0x14004ea80  mov     r8, 31D00140B5Ch; struct UnionFs::StackEventTracer *
0x14004ea8a  lea     r9, aUnionfsUfspath_63; "UnionFs::UfsPathTable::Traverse"
0x14004ea91  mov     [rsp+210h+var_1F0], rax; char *
0x14004ea96  mov     rdx, r12; int
0x14004ea99  mov     ecx, esi; this
0x14004ea9b  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004eaa0  lea     rcx, [rsp+210h+Destination]; UnicodeString
0x14004eaa5  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004eaaa  lea     rcx, [rbp+110h+var_C0]; this
0x14004eaae  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004eab3  mov     rcx, [rbp+110h+var_40]
0x14004eaba  test    rcx, rcx
0x14004eabd  jz      short loc_14004EACB
0x14004eabf  mov     rax, [rcx]
0x14004eac2  mov     rax, [rax+18h]
0x14004eac6  call    _guard_dispatch_icall
0x14004eacb  test    rbx, rbx
0x14004eace  jz      short loc_14004EAEB
0x14004ead0  mov     rcx, rbx; Resource
0x14004ead3  call    cs:__imp_ExReleaseResourceLite
0x14004eada  nop     dword ptr [rax+rax+00h]
0x14004eadf  call    cs:__imp_KeLeaveCriticalRegion
0x14004eae6  nop     dword ptr [rax+rax+00h]
0x14004eaeb  mov     eax, esi
0x14004eaed  jmp     loc_14004F132
0x14004eaf2  test    r13b, 2
0x14004eaf6  jnz     loc_14004EB8F
0x14004eafc  mov     rax, [rsp+210h+var_198]
0x14004eb01  lea     rcx, [rsp+210h+Destination]
0x14004eb06  mov     [rbp+110h+var_168], rcx
0x14004eb0a  xorps   xmm0, xmm0
0x14004eb0d  mov     [rbp+110h+var_180], rax
0x14004eb11  mov     [rbp+110h+var_178], r12
0x14004eb15  mov     rcx, [rax+70h]; this
0x14004eb19  mov     [rbp+110h+var_170], r9b
0x14004eb1d  mov     [rbp+110h+var_150], r9d
0x14004eb21  mov     [rsp+210h+var_1C8], r9
0x14004eb26  movdqu  [rbp+110h+var_160], xmm0
0x14004eb2b  test    rcx, rcx
0x14004eb2e  jz      loc_14004F163
0x14004eb34  mov     rax, [rcx]
0x14004eb37  lea     r9, [rbp+110h+var_180]
0x14004eb3b  lea     r8, [rsp+210h+var_1C8]
0x14004eb40  mov     rdx, r14
0x14004eb43  mov     rax, [rax+20h]
0x14004eb47  call    _guard_dispatch_icall
0x14004eb4c  xor     r9d, r9d
0x14004eb4f  mov     esi, eax
0x14004eb51  test    eax, eax
0x14004eb53  jns     short loc_14004EB81
0x14004eb55  lea     rax, aPushTraverseca; "PUSH: TraverseCallback on volume root n"...
0x14004eb5c  mov     r8, 31E00140B65h; struct UnionFs::StackEventTracer *
0x14004eb66  lea     r9, aUnionfsUfspath_63; "UnionFs::UfsPathTable::Traverse"
0x14004eb6d  mov     [rsp+210h+var_1F0], rax; char *
0x14004eb72  mov     rdx, r12; int
0x14004eb75  mov     ecx, esi; this
0x14004eb77  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004eb7c  jmp     loc_14004EAA0
0x14004eb81  mov     eax, [rbp+110h+var_150]
0x14004eb84  dec     eax
0x14004eb86  cmp     eax, 1
0x14004eb89  jbe     loc_14004EE8A
0x14004eb8f  mov     eax, [r15]
0x14004eb92  mov     r13, [r14+30h]
0x14004eb96  mov     rsi, [r14+38h]
0x14004eb9a  test    al, 2
0x14004eb9c  jnz     short loc_14004EBD0
0x14004eb9e  test    rsi, rsi
0x14004eba1  jz      short loc_14004EBA7
0x14004eba3  lock inc dword ptr [rsi+8]
0x14004eba7  mov     rcx, r13; this
0x14004ebaa  call    ?IsEmpty@UfsPathTree@UnionFs@@QEAA_NXZ; UnionFs::UfsPathTree::IsEmpty(void)
0x14004ebaf  test    al, al
0x14004ebb1  jnz     short loc_14004EBBF
0x14004ebb3  lea     rcx, aVolumerootnode; "volumeRootNode->GetDescendantTree()->Is"...
0x14004ebba  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14004ebbf  test    rsi, rsi
0x14004ebc2  jz      loc_14004EE8A
0x14004ebc8  mov     rcx, rsi
0x14004ebcb  jmp     loc_14004EE85
0x14004ebd0  test    rsi, rsi
0x14004ebd3  jz      short loc_14004EBD9
0x14004ebd5  lock inc dword ptr [rsi+8]
0x14004ebd9  test    r13, r13
0x14004ebdc  jz      short loc_14004EBE9
0x14004ebde  mov     rdi, r9
0x14004ebe1  mov     r15, rsi
0x14004ebe4  jmp     loc_14004EDF9
0x14004ebe9  mov     r13d, [rsp+210h+var_1CC]
0x14004ebee  mov     r8, [r14+30h]
0x14004ebf2  mov     r14, [r14+38h]
0x14004ebf6  mov     [rsp+210h+var_1C8], r8
0x14004ebfb  test    r14, r14
0x14004ebfe  jz      short loc_14004EC05
0x14004ec00  lock inc dword ptr [r14+8]
0x14004ec05  mov     r15, [rsp+210h+var_1A0]
0x14004ec0a  mov     eax, r13d
0x14004ec0d  and     eax, 1
0x14004ec10  mov     rdi, r9
0x14004ec13  mov     [rsp+210h+var_1CC], eax
0x14004ec17  test    eax, eax
0x14004ec19  mov     qword ptr [rbp+110h+var_190], rdi
0x14004ec1d  lea     rcx, [rbp+110h+var_148]
0x14004ec21  setnz   byte ptr [rsp+210h+var_1B0+8]
0x14004ec26  mov     qword ptr [rsp+210h+var_1B0], rcx
0x14004ec2b  xor     eax, eax
0x14004ec2d  lea     rdx, [rsp+210h+var_1B0]; struct UnionFs::UFS_COMPARE_KEY *
0x14004ec32  mov     rcx, r8; this
0x14004ec35  mov     dword ptr [rsp+210h+var_1B0+9], eax
0x14004ec39  mov     word ptr [rsp+210h+var_1B0+0Dh], ax
0x14004ec3e  mov     byte ptr [rsp+210h+var_1B0+0Fh], al
0x14004ec42  call    ?FindNode@UfsPathTree@UnionFs@@QEAAPEAVUfsPathTierNode@2@AEBUUFS_COMPARE_KEY@2@@Z; UnionFs::UfsPathTree::FindNode(UnionFs::UFS_COMPARE_KEY const &)
0x14004ec47  mov     rdi, rax
0x14004ec4a  test    rax, rax
0x14004ec4d  jz      loc_14004EF84
0x14004ec53  lea     rdx, Source; "\\"
0x14004ec5a  lea     rcx, [rsp+210h+Destination]; Destination
0x14004ec5f  call    cs:__imp_RtlAppendUnicodeToString
0x14004ec66  nop     dword ptr [rax+rax+00h]
0x14004ec6b  mov     r15d, eax
0x14004ec6e  test    eax, eax
0x14004ec70  js      loc_14004EEEF
0x14004ec76  lea     rdx, [rdi+20h]; Source
0x14004ec7a  lea     rcx, [rsp+210h+Destination]; Destination
0x14004ec7f  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004ec86  nop     dword ptr [rax+rax+00h]
0x14004ec8b  xor     r9d, r9d; unsigned __int16
0x14004ec8e  mov     r15d, eax
0x14004ec91  test    eax, eax
0x14004ec93  js      loc_14004EEDC
0x14004ec99  cmp     byte ptr [rsp+210h+var_1D0], r9b
0x14004ec9e  jz      short loc_14004ED00
0x14004eca0  mov     r15, [rsp+210h+var_1A0]
0x14004eca5  lea     rdx, [rbp+110h+var_148]; struct _UNICODE_STRING *
0x14004eca9  lea     rcx, [rbp+110h+var_190]; this
0x14004ecad  movups  xmm0, xmmword ptr [r15]
0x14004ecb1  movzx   r8d, word ptr [r15+18h]; struct _UNICODE_STRING *
0x14004ecb6  movdqu  [rbp+110h+var_190], xmm0
0x14004ecbb  call    ?WalkPath@Utils@UnionFs@@YA_NAEBU_UNICODE_STRING@@AEAU3@G@Z; UnionFs::Utils::WalkPath(_UNICODE_STRING const &,_UNICODE_STRING &,ushort)
0x14004ecc0  mov     rcx, [rdi+30h]
0x14004ecc4  mov     byte ptr [rsp+210h+var_1D0], al
0x14004ecc8  test    rcx, rcx
0x14004eccb  jz      short loc_14004ECF2
0x14004eccd  mov     rdx, [rdi+38h]
0x14004ecd1  test    rdx, rdx
0x14004ecd4  jz      short loc_14004ECDA
0x14004ecd6  lock inc dword ptr [rdx+8]
0x14004ecda  mov     r8, rcx
0x14004ecdd  mov     [rsp+210h+var_1C8], rcx
0x14004ece2  mov     rcx, r14; this
0x14004ece5  mov     r14, rdx
0x14004ece8  test    rcx, rcx
0x14004eceb  jz      short loc_14004ECF7
0x14004eced  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004ecf2  mov     r8, [rsp+210h+var_1C8]
0x14004ecf7  mov     eax, [rsp+210h+var_1CC]
0x14004ecfb  jmp     loc_14004EC17
0x14004ed00  mov     eax, [rdi+18h]
0x14004ed03  test    al, 1
0x14004ed05  jnz     loc_14004EDBE
0x14004ed0b  test    r13b, 2
0x14004ed0f  jnz     loc_14004EDBE
0x14004ed15  mov     rcx, [rsp+210h+var_198]
0x14004ed1a  lea     rax, [rsp+210h+Destination]
0x14004ed1f  mov     [rbp+110h+var_180], rcx
0x14004ed23  xorps   xmm0, xmm0
0x14004ed26  mov     [rbp+110h+var_168], rax
0x14004ed2a  mov     rax, qword ptr [rbp+110h+var_190]
0x14004ed2e  mov     rcx, [rcx+70h]; this
0x14004ed32  mov     [rbp+110h+var_178], r12
0x14004ed36  mov     [rbp+110h+var_170], r9b
0x14004ed3a  mov     [rbp+110h+var_150], r9d
0x14004ed3e  mov     qword ptr [rbp+110h+var_190], rax
0x14004ed42  movdqu  [rbp+110h+var_160], xmm0
0x14004ed47  test    rcx, rcx
0x14004ed4a  jz      loc_14004F15D
0x14004ed50  mov     rax, [rcx]
0x14004ed53  lea     r9, [rbp+110h+var_180]
0x14004ed57  lea     r8, [rbp+110h+var_190]
0x14004ed5b  mov     rdx, rdi
0x14004ed5e  mov     rax, [rax+20h]
0x14004ed62  call    _guard_dispatch_icall
0x14004ed67  xor     r9d, r9d
0x14004ed6a  mov     r15d, eax
0x14004ed6d  test    eax, eax
0x14004ed6f  jns     short loc_14004ED9E
0x14004ed71  lea     rax, aPushTraverseca_0; "PUSH: TraverseCallback on starting loca"...
0x14004ed78  mov     r8, 16900140BACh; struct UnionFs::StackEventTracer *
0x14004ed82  lea     r9, aUnionfsUfspath_63; "UnionFs::UfsPathTable::Traverse"
0x14004ed89  mov     [rsp+210h+var_1F0], rax; char *
0x14004ed8e  mov     rdx, r12; int
0x14004ed91  mov     ecx, r15d; this
0x14004ed94  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004ed99  jmp     loc_14004EF17
0x14004ed9e  mov     eax, [rbp+110h+var_150]
0x14004eda1  dec     eax
0x14004eda3  cmp     eax, 1
0x14004eda6  ja      short loc_14004EDBE
0x14004eda8  test    r14, r14
0x14004edab  jz      loc_14004EBBF
0x14004edb1  mov     rcx, r14; this
0x14004edb4  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004edb9  jmp     loc_14004EBBF
0x14004edbe  mov     r15, [rdi+38h]
0x14004edc2  mov     r13, [rdi+30h]
0x14004edc6  test    r15, r15
0x14004edc9  jz      short loc_14004EDD0
0x14004edcb  lock inc dword ptr [r15+8]
0x14004edd0  test    rsi, rsi
0x14004edd3  jz      short loc_14004EDE0
0x14004edd5  mov     rcx, rsi; this
0x14004edd8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004eddd  xor     r9d, r9d
0x14004ede0  test    r14, r14
0x14004ede3  jz      short loc_14004EDF0
0x14004ede5  mov     rcx, r14; this
0x14004ede8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004eded  xor     r9d, r9d
0x14004edf0  test    r13, r13
0x14004edf3  jz      loc_14004EE7D
0x14004edf9  mov     rcx, r13; this
0x14004edfc  call    ?IsEmpty@UfsPathTree@UnionFs@@QEAA_NXZ; UnionFs::UfsPathTree::IsEmpty(void)
  ... truncated ...
```
