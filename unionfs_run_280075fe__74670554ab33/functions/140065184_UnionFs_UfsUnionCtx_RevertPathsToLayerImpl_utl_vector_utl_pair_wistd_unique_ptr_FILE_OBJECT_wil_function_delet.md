# UnionFs::UfsUnionCtx::RevertPathsToLayerImpl(utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>> &,utl::vector<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsPathCachePayload>>> &,bool,UnionFs::StackEventTracer &)

- ea: `0x140065184`
- end: `0x14006560f`
- name: `?RevertPathsToLayerImpl@UfsUnionCtx@UnionFs@@AEAAJAEAV?$vector@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@2@@utl@@AEAV?$vector@V?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@2@@4@_NAEAVStackEventTracer@2@@Z`
- size: `1163`
- prototype: `__int64 __fastcall(int, int, int, int, UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x140064454`

## callees

- `0x14000f7fc`
- `0x1400424ec`
- `0x1400430fc`
- `0x1400567f4`
- `0x140056a50`
- `0x140056ac4`
- `0x14005cc5c`
- `0x14005daa0`
- `0x140065184`
- `0x140067598`
- `0x140079a24`
- `0x140079da0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400652c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400652fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065360`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065394`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400655b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400655ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400652c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400652fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065360`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065394`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400655b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400655ee`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006554d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140065576`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006554d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140065576`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140065559`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140065582`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140065559`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140065582`
- `FLTMGR!FltIsDirectory` at `0x140065225`
- `FLTMGR!FltIsDirectory` at `0x140065225`
- `FLTMGR!FltSetInformationFile` at `0x1400653e3`
- `FLTMGR!FltSetInformationFile` at `0x1400654a5`
- `FLTMGR!FltSetInformationFile` at `0x1400653e3`
- `FLTMGR!FltSetInformationFile` at `0x1400654a5`
- `FLTMGR!FltClose` at `0x14006544e`
- `FLTMGR!FltClose` at `0x14006544e`

## string_xrefs

- `0x140065316`: `API: FltIsDirectory on scratch item`
- `0x140065251`: `ORIGIN: Pushing scratch directory`
- `0x14006528c`: `UnionFs::UfsUnionCtx::RevertPathsToLayerImpl`
- `0x14006531d`: `UnionFs::UfsUnionCtx::RevertPathsToLayerImpl`
- `0x140065410`: `UnionFs::UfsUnionCtx::RevertPathsToLayerImpl`
- `0x1400654cb`: `UnionFs::UfsUnionCtx::RevertPathsToLayerImpl`
- `0x1400653fb`: `API: Setting delete on close on scratch file`
- `0x1400654b5`: `API: Setting delete on close on scratch directory`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsUnionCtx::RevertPathsToLayerImpl(
        __int64 a1,
        struct _FILE_OBJECT ***a2,
        UnionFs::UfsPathCachePayload ***a3,
        unsigned __int8 a4,
        UnionFs::StackEventTracer *a5)
{
  unsigned __int64 *v8; // rdx
  __int64 *v9; // rax
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rsi
  struct _ERESOURCE *v12; // rcx
  struct _FLT_INSTANCE *v13; // r14
  struct _FILE_OBJECT **v14; // rbx
  struct _FILE_OBJECT **v15; // rdi
  struct _FILE_OBJECT *v16; // rcx
  NTSTATUS v17; // esi
  const char *v18; // rax
  __int64 v19; // r8
  __int64 v20; // rcx
  PVOID v21; // rbx
  signed __int64 v22; // r8
  __int64 v24; // rcx
  PVOID v25; // rbx
  signed __int64 v26; // r8
  PFILE_OBJECT *v27; // rbx
  PFILE_OBJECT *v28; // rdi
  const char *v29; // rax
  __int64 v30; // r8
  _QWORD *v31; // rbx
  _QWORD *v32; // rdi
  void *v33; // rcx
  _BYTE *v34; // r15
  PFILE_OBJECT *v35; // rbx
  PFILE_OBJECT *v36; // rdi
  UnionFs::StackEventTracer *v37; // rsi
  NTSTATUS v38; // eax
  UnionFs::UfsPathCachePayload **v39; // rdi
  UnionFs::UfsPathCachePayload **v40; // rsi
  UnionFs::UfsPathCachePayload *v41; // r14
  struct _ERESOURCE *v42; // rax
  signed __int64 v43; // r8
  const char *v44; // [rsp+28h] [rbp-58h]
  PVOID v45[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v46; // [rsp+40h] [rbp-40h]
  PVOID P[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v48; // [rsp+58h] [rbp-28h]
  _QWORD v49[2]; // [rsp+60h] [rbp-20h] BYREF
  char v50; // [rsp+70h] [rbp-10h]
  int FileInformation; // [rsp+C0h] [rbp+40h] BYREF
  PERESOURCE Resource; // [rsp+C8h] [rbp+48h] BYREF
  unsigned __int8 IsDirectory; // [rsp+D8h] [rbp+58h] BYREF

  IsDirectory = a4;
  FsFltWil::AcquirePushLockShared(&Resource, a1 + 72);
  v9 = *(__int64 **)(a1 + 48);
  v10 = (volatile signed __int32 *)v9[1];
  v11 = *v9;
  if ( v10 )
    _InterlockedIncrement(v10 + 2);
  v12 = Resource;
  if ( Resource )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Resource, v8);
  v13 = **(struct _FLT_INSTANCE ***)(v11 + 8);
  if ( v10 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v10);
  v14 = *a2;
  v15 = a2[1];
  *(__m128i *)v45 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v46 = -1;
  *(_OWORD *)P = *(_OWORD *)v45;
  v48 = -1;
  while ( v14 != v15 )
  {
    v16 = *v14;
    IsDirectory = 0;
    v17 = FltIsDirectory(v16, v13, &IsDirectory);
    if ( v17 < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v17,
        (int)a5,
        (struct UnionFs::StackEventTracer *)0x57D002007E1LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayerImpl",
        "API: FltIsDirectory on scratch item",
        v44);
LABEL_24:
      v25 = P[0];
      if ( P[0] != (PVOID)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
          v24,
          P[0],
          ((char *)P[1] - (char *)P[0]) >> 4);
        if ( v25 )
          ExFreePoolWithTag(v25, 0);
      }
      if ( v45[0] != (PVOID)-1LL )
      {
        v26 = (char *)v45[1] - (char *)v45[0];
        v45[1] = v45[0];
        utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
          v24,
          v45[0],
          v26 >> 4);
        if ( v45[0] )
          ExFreePoolWithTag(v45[0], 0);
      }
      return (unsigned int)v17;
    }
    if ( IsDirectory )
    {
      if ( !(unsigned __int8)utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::push_back(
                               P,
                               v14) )
      {
        v18 = "ORIGIN: Pushing scratch directory";
        v19 = 0x57E002007E8LL;
        goto LABEL_16;
      }
    }
    else if ( !(unsigned __int8)utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::push_back(
                                  v45,
                                  v14) )
    {
      v18 = "ORIGIN: Pushing scratch file";
      v19 = 0x57F002007F0LL;
LABEL_16:
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a5,
        (struct UnionFs::StackEventTracer *)v19,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayerImpl",
        v18,
        v44);
      v21 = P[0];
      if ( P[0] != (PVOID)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
          v20,
          P[0],
          ((char *)P[1] - (char *)P[0]) >> 4);
        if ( v21 )
          ExFreePoolWithTag(v21, 0);
      }
      if ( v45[0] != (PVOID)-1LL )
      {
        v22 = (char *)v45[1] - (char *)v45[0];
        v45[1] = v45[0];
        utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
          v20,
          v45[0],
          v22 >> 4);
        if ( v45[0] )
          ExFreePoolWithTag(v45[0], 0);
      }
      return 3221225626LL;
    }
    v14 += 2;
  }
  v27 = (PFILE_OBJECT *)v45[0];
  v28 = (PFILE_OBJECT *)v45[1];
  v49[0] = v45;
  v49[1] = v13;
  v50 = 1;
  FileInformation = 3;
  while ( v27 != v28 )
  {
    v17 = FltSetInformationFile(v13, *v27, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
    if ( v17 < 0 )
    {
      v29 = "API: Setting delete on close on scratch file";
      v30 = 0x5820020081FLL;
LABEL_36:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v17,
        (int)a5,
        (struct UnionFs::StackEventTracer *)v30,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayerImpl",
        v29,
        v44);
      v50 = 0;
      lambda_d87ac1b29ae67a20fae0bafbd19cef00_::operator()(v49);
      goto LABEL_24;
    }
    v27 += 2;
  }
  v31 = v45[0];
  v32 = v45[1];
  while ( v31 != v32 )
  {
    v33 = (void *)v31[1];
    v31[1] = 0;
    v17 = FltClose(v33);
    if ( v17 < 0 )
    {
      v29 = "API: Closing scratch file handle";
      v30 = 0x58300200834LL;
      goto LABEL_36;
    }
    v31 += 2;
  }
  v34 = P[0];
  v35 = (PFILE_OBJECT *)P[1];
  v36 = (PFILE_OBJECT *)P[0];
  v37 = a5;
  while ( v36 != v35 )
  {
    v38 = FltSetInformationFile(v13, *v36, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
    if ( v38 < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v38,
        (int)v37,
        (struct UnionFs::StackEventTracer *)0x5D00020084ALL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayerImpl",
        "API: Setting delete on close on scratch directory",
        v44);
      UnionFs::StackEventTracer::LogError(v37);
      *(_DWORD *)v37 = 0;
      *((_WORD *)v37 + 274) = 0;
    }
    v36 += 2;
  }
  v39 = *a3;
  v40 = a3[1];
  while ( v39 != v40 )
  {
    (*(void (__fastcall **)(UnionFs::UfsPathCachePayload *, PERESOURCE *))(*(_QWORD *)*v39 + 16LL))(*v39, &Resource);
    v41 = *v39;
    UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(*v39, 0x58400200854LL);
    UnionFs::UfsPathCachePayload::RevertSoftTombstone(v41);
    v42 = Resource;
    v12 = 0;
    Resource = 0;
    if ( v42 )
    {
      ExReleaseResourceLite(v42);
      KeLeaveCriticalRegion();
      v12 = Resource;
    }
    Resource = 0;
    if ( v12 )
    {
      ExReleaseResourceLite(v12);
      KeLeaveCriticalRegion();
    }
    v39 += 2;
  }
  if ( v34 != (_BYTE *)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
      v12,
      v34,
      ((char *)v35 - v34) >> 4);
    if ( v34 )
      ExFreePoolWithTag(v34, 0);
  }
  if ( v45[0] != (PVOID)-1LL )
  {
    v43 = (char *)v45[1] - (char *)v45[0];
    v45[1] = v45[0];
    utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
      v12,
      v45[0],
      v43 >> 4);
    if ( v45[0] )
      ExFreePoolWithTag(v45[0], 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140065184  mov     [rsp-38h+IsDirectory], r9b
0x140065189  push    rbp
0x14006518a  push    rbx
0x14006518b  push    rsi
0x14006518c  push    rdi
0x14006518d  push    r12
0x14006518f  push    r14
0x140065191  push    r15
0x140065193  mov     rbp, rsp
0x140065196  sub     rsp, 80h
0x14006519d  mov     rdi, rdx
0x1400651a0  mov     rbx, rcx
0x1400651a3  lea     rdx, [rcx+48h]
0x1400651a7  mov     r12, r8
0x1400651aa  lea     rcx, [rbp+Resource]
0x1400651ae  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400651b3  mov     rax, [rbx+30h]
0x1400651b7  mov     rbx, [rax+8]
0x1400651bb  mov     rsi, [rax]
0x1400651be  test    rbx, rbx
0x1400651c1  jz      short loc_1400651C7
0x1400651c3  lock inc dword ptr [rbx+8]
0x1400651c7  mov     rcx, [rbp+Resource]; this
0x1400651cb  test    rcx, rcx
0x1400651ce  jz      short loc_1400651D5
0x1400651d0  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400651d5  mov     rax, [rsi+8]
0x1400651d9  mov     r14, [rax]
0x1400651dc  test    rbx, rbx
0x1400651df  jz      short loc_1400651E9
0x1400651e1  mov     rcx, rbx; this
0x1400651e4  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400651e9  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400651f1  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400651f5  mov     rbx, [rdi]
0x1400651f8  mov     rdi, [rdi+8]
0x1400651fc  movdqu  xmmword ptr [rbp+var_50], xmm0
0x140065201  mov     [rbp+var_40], r15
0x140065205  movdqu  xmmword ptr [rbp+P], xmm0
0x14006520a  mov     [rbp+var_28], r15
0x14006520e  cmp     rbx, rdi
0x140065211  jz      loc_1400653A7
0x140065217  mov     rcx, [rbx]; FileObject
0x14006521a  lea     r8, [rbp+IsDirectory]; IsDirectory
0x14006521e  mov     rdx, r14; Instance
0x140065221  mov     [rbp+IsDirectory], 0
0x140065225  call    cs:__imp_FltIsDirectory
0x14006522c  nop     dword ptr [rax+rax+00h]
0x140065231  mov     esi, eax
0x140065233  test    eax, eax
0x140065235  js      loc_140065312
0x14006523b  cmp     [rbp+IsDirectory], 0
0x14006523f  mov     rdx, rbx
0x140065242  jz      short loc_140065264
0x140065244  lea     rcx, [rbp+P]
0x140065248  call    ?push_back@?$vector@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@2@@utl@@QEAA_N$$QEAU?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@2@@Z; utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::push_back(utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x14006524d  test    al, al
0x14006524f  jnz     short loc_140065271
0x140065251  lea     rax, aOriginPushingS_1; "ORIGIN: Pushing scratch directory"
0x140065258  mov     r8, 57E002007E8h
0x140065262  jmp     short loc_140065288
0x140065264  lea     rcx, [rbp+var_50]
0x140065268  call    ?push_back@?$vector@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@2@@utl@@QEAA_N$$QEAU?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@2@@Z; utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::push_back(utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x14006526d  test    al, al
0x14006526f  jz      short loc_140065277
0x140065271  add     rbx, 10h
0x140065275  jmp     short loc_14006520E
0x140065277  lea     rax, aOriginPushingS_0; "ORIGIN: Pushing scratch file"
0x14006527e  mov     r8, 57F002007F0h; struct UnionFs::StackEventTracer *
0x140065288  mov     rdx, [rbp+arg_20]; int
0x14006528c  lea     r9, aUnionfsUfsunio_16; "UnionFs::UfsUnionCtx::RevertPathsToLaye"...
0x140065293  mov     ecx, 0C000009Ah; this
0x140065298  mov     qword ptr [rsp+80h+FileInformationClass], rax; char *
0x14006529d  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400652a2  mov     rbx, [rbp+P]
0x1400652a6  cmp     rbx, r15
0x1400652a9  jz      short loc_1400652D4
0x1400652ab  mov     r8, [rbp+P+8]
0x1400652af  mov     rdx, rbx
0x1400652b2  sub     r8, rbx
0x1400652b5  sar     r8, 4
0x1400652b9  call    ??$_RangeDestroyApc@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@0@PEAU?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>> &,utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> *,unsigned __int64)
0x1400652be  test    rbx, rbx
0x1400652c1  jz      short loc_1400652D4
0x1400652c3  xor     edx, edx; Tag
0x1400652c5  mov     rcx, rbx; P
0x1400652c8  call    cs:__imp_ExFreePoolWithTag
0x1400652cf  nop     dword ptr [rax+rax+00h]
0x1400652d4  mov     rdx, [rbp+var_50]
0x1400652d8  cmp     rdx, r15
0x1400652db  jz      short loc_140065308
0x1400652dd  mov     r8, [rbp+var_50+8]
0x1400652e1  sub     r8, rdx
0x1400652e4  mov     [rbp+var_50+8], rdx
0x1400652e8  sar     r8, 4
0x1400652ec  call    ??$_RangeDestroyApc@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@0@PEAU?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>> &,utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> *,unsigned __int64)
0x1400652f1  mov     rcx, [rbp+var_50]; P
0x1400652f5  test    rcx, rcx
0x1400652f8  jz      short loc_140065308
0x1400652fa  xor     edx, edx; Tag
0x1400652fc  call    cs:__imp_ExFreePoolWithTag
0x140065303  nop     dword ptr [rax+rax+00h]
0x140065308  mov     eax, 0C000009Ah
0x14006530d  jmp     loc_1400655FC
0x140065312  mov     rdx, [rbp+arg_20]; int
0x140065316  lea     rax, aApiFltisdirect_1; "API: FltIsDirectory on scratch item"
0x14006531d  lea     r9, aUnionfsUfsunio_16; "UnionFs::UfsUnionCtx::RevertPathsToLaye"...
0x140065324  mov     qword ptr [rsp+80h+FileInformationClass], rax; char *
0x140065329  mov     r8, 57D002007E1h; struct UnionFs::StackEventTracer *
0x140065333  mov     ecx, esi; this
0x140065335  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006533a  mov     rbx, [rbp+P]
0x14006533e  cmp     rbx, r15
0x140065341  jz      short loc_14006536C
0x140065343  mov     r8, [rbp+P+8]
0x140065347  mov     rdx, rbx
0x14006534a  sub     r8, rbx
0x14006534d  sar     r8, 4
0x140065351  call    ??$_RangeDestroyApc@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@0@PEAU?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>> &,utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> *,unsigned __int64)
0x140065356  test    rbx, rbx
0x140065359  jz      short loc_14006536C
0x14006535b  xor     edx, edx; Tag
0x14006535d  mov     rcx, rbx; P
0x140065360  call    cs:__imp_ExFreePoolWithTag
0x140065367  nop     dword ptr [rax+rax+00h]
0x14006536c  mov     rdx, [rbp+var_50]
0x140065370  cmp     rdx, r15
0x140065373  jz      short loc_1400653A0
0x140065375  mov     r8, [rbp+var_50+8]
0x140065379  sub     r8, rdx
0x14006537c  mov     [rbp+var_50+8], rdx
0x140065380  sar     r8, 4
0x140065384  call    ??$_RangeDestroyApc@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@0@PEAU?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>> &,utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> *,unsigned __int64)
0x140065389  mov     rcx, [rbp+var_50]; P
0x14006538d  test    rcx, rcx
0x140065390  jz      short loc_1400653A0
0x140065392  xor     edx, edx; Tag
0x140065394  call    cs:__imp_ExFreePoolWithTag
0x14006539b  nop     dword ptr [rax+rax+00h]
0x1400653a0  mov     eax, esi
0x1400653a2  jmp     loc_1400655FC
0x1400653a7  mov     rbx, [rbp+var_50]
0x1400653ab  lea     rax, [rbp+var_50]
0x1400653af  mov     rdi, [rbp+var_50+8]
0x1400653b3  mov     [rbp+var_20], rax
0x1400653b7  mov     [rbp+var_18], r14
0x1400653bb  mov     [rbp+var_10], 1
0x1400653bf  mov     [rbp+FileInformation], 3
0x1400653c6  cmp     rbx, rdi
0x1400653c9  jz      short loc_140065435
0x1400653cb  mov     rdx, [rbx]; FileObject
0x1400653ce  lea     r8, [rbp+FileInformation]; FileInformation
0x1400653d2  mov     r9d, 4; Length
0x1400653d8  mov     [rsp+80h+FileInformationClass], 40h ; '@'; FileInformationClass
0x1400653e0  mov     rcx, r14; Instance
0x1400653e3  call    cs:__imp_FltSetInformationFile
0x1400653ea  nop     dword ptr [rax+rax+00h]
0x1400653ef  mov     esi, eax
0x1400653f1  test    eax, eax
0x1400653f3  js      short loc_1400653FB
0x1400653f5  add     rbx, 10h
0x1400653f9  jmp     short loc_1400653C6
0x1400653fb  lea     rax, aApiSettingDele; "API: Setting delete on close on scratch"...
0x140065402  mov     r8, 5820020081Fh; struct UnionFs::StackEventTracer *
0x14006540c  mov     rdx, [rbp+arg_20]; int
0x140065410  lea     r9, aUnionfsUfsunio_16; "UnionFs::UfsUnionCtx::RevertPathsToLaye"...
0x140065417  mov     ecx, esi; this
0x140065419  mov     qword ptr [rsp+80h+FileInformationClass], rax; char *
0x14006541e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140065423  lea     rcx, [rbp+var_20]
0x140065427  mov     [rbp+var_10], 0
0x14006542b  call    _lambda_d87ac1b29ae67a20fae0bafbd19cef00___operator__
0x140065430  jmp     loc_14006533A
0x140065435  mov     rbx, [rbp+var_50]
0x140065439  mov     rdi, [rbp+var_50+8]
0x14006543d  cmp     rbx, rdi
0x140065440  jz      short loc_140065479
0x140065442  mov     rcx, [rbx+8]; FileHandle
0x140065446  mov     qword ptr [rbx+8], 0
0x14006544e  call    cs:__imp_FltClose
0x140065455  nop     dword ptr [rax+rax+00h]
0x14006545a  mov     esi, eax
0x14006545c  test    eax, eax
0x14006545e  js      short loc_140065466
0x140065460  add     rbx, 10h
0x140065464  jmp     short loc_14006543D
0x140065466  lea     rax, aApiClosingScra; "API: Closing scratch file handle"
0x14006546d  mov     r8, 58300200834h
0x140065477  jmp     short loc_14006540C
0x140065479  mov     r15, [rbp+P]
0x14006547d  mov     rbx, [rbp+P+8]
0x140065481  mov     rdi, r15
0x140065484  mov     rsi, [rbp+arg_20]
0x140065488  cmp     rdi, rbx
0x14006548b  jz      short loc_1400654F9
0x14006548d  mov     rdx, [rdi]; FileObject
0x140065490  lea     r8, [rbp+FileInformation]; FileInformation
0x140065494  mov     r9d, 4; Length
0x14006549a  mov     [rsp+80h+FileInformationClass], 40h ; '@'; FileInformationClass
0x1400654a2  mov     rcx, r14; Instance
0x1400654a5  call    cs:__imp_FltSetInformationFile
0x1400654ac  nop     dword ptr [rax+rax+00h]
0x1400654b1  test    eax, eax
0x1400654b3  jns     short loc_1400654F3
0x1400654b5  lea     rcx, aApiSettingDele_0; "API: Setting delete on close on scratch"...
0x1400654bc  mov     r8, 5D00020084Ah; struct UnionFs::StackEventTracer *
0x1400654c6  mov     qword ptr [rsp+80h+FileInformationClass], rcx; char *
0x1400654cb  lea     r9, aUnionfsUfsunio_16; "UnionFs::UfsUnionCtx::RevertPathsToLaye"...
0x1400654d2  mov     ecx, eax; this
0x1400654d4  mov     rdx, rsi; int
0x1400654d7  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400654dc  mov     rcx, rsi; this
0x1400654df  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x1400654e4  xor     eax, eax
0x1400654e6  mov     dword ptr [rsi], 0
0x1400654ec  mov     [rsi+224h], ax
0x1400654f3  add     rdi, 10h
0x1400654f7  jmp     short loc_140065488
0x1400654f9  mov     rdi, [r12]
0x1400654fd  mov     rsi, [r12+8]
0x140065502  cmp     rdi, rsi
0x140065505  jz      loc_140065597
0x14006550b  mov     rcx, [rdi]
0x14006550e  lea     rdx, [rbp+Resource]
0x140065512  mov     rax, [rcx]
0x140065515  mov     rax, [rax+10h]
0x140065519  call    _guard_dispatch_icall
0x14006551e  mov     r14, [rdi]
0x140065521  mov     rdx, 58400200854h
0x14006552b  mov     rcx, r14
0x14006552e  call    ?InvalidateNoRevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAAXT_TAGGED_SOURCE@@@Z; UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(_TAGGED_SOURCE)
0x140065533  mov     rcx, r14; this
0x140065536  call    ?RevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAA_NXZ; UnionFs::UfsPathCachePayload::RevertSoftTombstone(void)
0x14006553b  mov     rax, [rbp+Resource]
0x14006553f  xor     ecx, ecx
0x140065541  mov     [rbp+Resource], rcx
0x140065545  test    rax, rax
0x140065548  jz      short loc_140065569
0x14006554a  mov     rcx, rax; Resource
0x14006554d  call    cs:__imp_ExReleaseResourceLite
0x140065554  nop     dword ptr [rax+rax+00h]
0x140065559  call    cs:__imp_KeLeaveCriticalRegion
0x140065560  nop     dword ptr [rax+rax+00h]
0x140065565  mov     rcx, [rbp+Resource]; Resource
0x140065569  mov     [rbp+Resource], 0
0x140065571  test    rcx, rcx
0x140065574  jz      short loc_14006558E
0x140065576  call    cs:__imp_ExReleaseResourceLite
0x14006557d  nop     dword ptr [rax+rax+00h]
0x140065582  call    cs:__imp_KeLeaveCriticalRegion
0x140065589  nop     dword ptr [rax+rax+00h]
0x14006558e  add     rdi, 10h
0x140065592  jmp     loc_140065502
0x140065597  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x14006559b  jz      short loc_1400655C5
0x14006559d  sub     rbx, r15
0x1400655a0  mov     rdx, r15
0x1400655a3  sar     rbx, 4
0x1400655a7  mov     r8, rbx
0x1400655aa  call    ??$_RangeDestroyApc@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@0@PEAU?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>> &,utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> *,unsigned __int64)
0x1400655af  test    r15, r15
0x1400655b2  jz      short loc_1400655C5
0x1400655b4  xor     edx, edx; Tag
0x1400655b6  mov     rcx, r15; P
0x1400655b9  call    cs:__imp_ExFreePoolWithTag
0x1400655c0  nop     dword ptr [rax+rax+00h]
0x1400655c5  mov     rdx, [rbp+var_50]
0x1400655c9  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400655cd  jz      short loc_1400655FA
0x1400655cf  mov     r8, [rbp+var_50+8]
0x1400655d3  sub     r8, rdx
0x1400655d6  mov     [rbp+var_50+8], rdx
0x1400655da  sar     r8, 4
0x1400655de  call    ??$_RangeDestroyApc@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@0@PEAU?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>> &,utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> *,unsigned __int64)
0x1400655e3  mov     rcx, [rbp+var_50]; P
0x1400655e7  test    rcx, rcx
0x1400655ea  jz      short loc_1400655FA
0x1400655ec  xor     edx, edx; Tag
0x1400655ee  call    cs:__imp_ExFreePoolWithTag
0x1400655f5  nop     dword ptr [rax+rax+00h]
0x1400655fa  xor     eax, eax
0x1400655fc  add     rsp, 80h
0x140065603  pop     r15
0x140065605  pop     r14
0x140065607  pop     r12
0x140065609  pop     rdi
0x14006560a  pop     rsi
0x14006560b  pop     rbx
0x14006560c  pop     rbp
0x14006560d  retn
```
