# CThreadInfo::DoWork(void)

- ea: `0x180010f28`
- end: `0x180011302`
- name: `?DoWork@CThreadInfo@@QEAAJXZ`
- size: `986`
- prototype: `__int64 __fastcall(CThreadInfo *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180014030`

## callees

- `0x180001ed4`
- `0x18000f9c0`
- `0x18000fcd4`
- `0x18000fe3c`
- `0x1800103e4`
- `0x180010f28`
- `0x180011994`
- `0x180011cd8`
- `0x180015308`
- `0x1800156e4`
- `0x180015820`
- `0x180015fc0`
- `0x180018c9c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010fce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010fce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011295`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180010fb5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180010fb5`

## string_xrefs

- `0x180010fae`: `MsftEdit.dll`
- `0x180010fc4`: `CreateTextServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThreadInfo::DoWork(CThreadInfo *this)
{
  _QWORD *v2; // rsi
  int AllTheContent; // ebx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  unsigned __int64 v6; // rcx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // rcx
  void *v10; // rbx
  __int64 v11; // rax
  _BYTE *v12; // rsi
  char *v13; // rax
  char *v14; // rsi
  void *v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _OWORD v20[2]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v21[8]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v22[48]; // [rsp+58h] [rbp-1h] BYREF
  LPVOID v23; // [rsp+88h] [rbp+2Fh]
  unsigned __int64 v24; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+6Fh] BYREF
  __int64 v26; // [rsp+D0h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp+7Fh] BYREF

  v26 = 0;
  v25 = 0;
  v2 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v24 = (unsigned __int64)v2;
  if ( v2 )
  {
    *v2 = &CRtfITextHost::`vftable';
    _InterlockedIncrement(&g_cInstances);
    *((_DWORD *)v2 + 2) = 1;
  }
  else
  {
    v2 = 0;
  }
  *((_QWORD *)this + 6) = v2;
  AllTheContent = -2147024882;
  if ( v2 )
    AllTheContent = 0;
  v24 = 0;
  if ( v2 )
  {
    v24 = 0;
    AllTheContent = -2147467259;
    LibraryW = (HMODULE)*((_QWORD *)this + 5);
    if ( LibraryW || (LibraryW = LoadLibraryW(L"MsftEdit.dll"), (*((_QWORD *)this + 5) = LibraryW) != 0) )
    {
      ProcAddress = GetProcAddress(LibraryW, "CreateTextServices");
      if ( ProcAddress )
        AllTheContent = ((__int64 (__fastcall *)(_QWORD, _QWORD *, unsigned __int64 *))ProcAddress)(0, v2, &v24);
    }
    if ( AllTheContent >= 0 )
    {
      if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v24)(
             (LPVOID)v24,
             &GUID_8cc497c0_a1df_11ce_8098_00aa0047be5d,
             &v26) < 0
        || (AllTheContent = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v24)(
                              (LPVOID)v24,
                              &IID_ITextServices,
                              &v25),
            AllTheContent < 0) )
      {
        AllTheContent = -2147215613;
      }
    }
  }
  v6 = v24;
  v24 = 0;
  if ( v6 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( AllTheContent >= 0 )
  {
    v24 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned __int64 *))(*(_QWORD *)v25 + 24LL))(
           v25,
           1145,
           0,
           0,
           &v24) >= 0 )
    {
      v24 |= 0x400u;
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 24LL))(v25, 1144, 0);
    }
    if ( *((_DWORD *)this + 6) )
    {
      DWORD2(v20[0]) = 0;
      *(_QWORD *)&v20[0] = *((_QWORD *)this + 4);
      *(_QWORD *)((char *)v20 + 12) = EditStreamCallback;
      v24 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64, _OWORD *, unsigned __int64 *))(*(_QWORD *)v25 + 24LL))(
        v25,
        1097,
        2,
        v20,
        &v24);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
      *((_QWORD *)this + 4) = 0;
    }
    else
    {
      memset(v20, 0, 24);
      strcpy((char *)v20, "\b");
      *((_QWORD *)&v20[0] + 1) = *((_QWORD *)this + 4);
      (*(void (__fastcall **)(__int64, _OWORD *, __int64, __int64))(*(_QWORD *)v26 + 128LL))(v26, v20, 304, 1200);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_51365605>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_51365605>::GetImpl'::`2'::impl) )
    {
      pv = 0;
      v8 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::ensure_data(&pv);
      tip2::details::shared_data<1,0,0>::start(*v8 + 8LL, v20);
      tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(
        v21,
        &pv);
      v10 = pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(v10);
        CoTaskMemFree(v10);
      }
      v20[0] = 0;
      v11 = *((_QWORD *)this + 1);
      if ( v11 )
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
      v20[0] = *(_OWORD *)this;
      AllTheContent = CThreadInfo::GetAllTheContent(v9, &v26, *((_QWORD *)this + 2), v20);
      if ( AllTheContent >= 0 )
      {
        v12 = v23;
        v24 = (unsigned __int64)v23;
        if ( v23 )
          _InterlockedIncrement((volatile signed __int32 *)v23 + 70);
        tip2::details::shared_data<1,0,0>::begin_update(v12 + 8);
        v12[272] = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(&v24);
      }
      v13 = (char *)v23;
      v24 = (unsigned __int64)v23;
      if ( v23 )
        _InterlockedIncrement((volatile signed __int32 *)v23 + 70);
      v14 = v13 + 8;
      tip2::details::shared_data<1,0,0>::begin_update(v13 + 8);
      *((_DWORD *)v14 + 16) |= 0xB00u;
      if ( *((_QWORD *)v14 + 30) )
        tip2::details::shared_data<1,0,0>::complete_helper(v14, 10);
      tip2::test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(&v24);
      v15 = v23;
      if ( v23 && _InterlockedExchangeAdd((volatile signed __int32 *)v23 + 70, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(v15);
        CoTaskMemFree(v15);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v22);
    }
    else
    {
      AllTheContent = CThreadInfo::GetAllTheText(v7, &v26, *((_QWORD *)this + 2));
    }
  }
  v16 = v25;
  v25 = 0;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v17 = v26;
  v26 = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v18 = *((_QWORD *)this + 6);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    *((_QWORD *)this + 6) = 0;
  }
  return (unsigned int)AllTheContent;
}

```

## disassembly

```asm
0x180010f28  push    rbp
0x180010f2a  push    rbx
0x180010f2b  push    rsi
0x180010f2c  push    rdi
0x180010f2d  push    r14
0x180010f2f  lea     rbp, [rsp-37h]
0x180010f34  sub     rsp, 90h
0x180010f3b  mov     rdi, rcx
0x180010f3e  xor     r14d, r14d
0x180010f41  mov     [rbp+57h+arg_10], r14
0x180010f45  mov     [rbp+57h+arg_8], r14
0x180010f49  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010f50  lea     ecx, [r14+10h]; unsigned __int64
0x180010f54  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010f59  mov     rsi, rax
0x180010f5c  mov     [rbp+57h+arg_0], rax
0x180010f60  test    rax, rax
0x180010f63  jz      short loc_180010F7F
0x180010f65  lea     rax, ??_7CRtfITextHost@@6B@; const CRtfITextHost::`vftable'
0x180010f6c  mov     [rsi], rax
0x180010f6f  lock inc cs:?g_cInstances@@3JA; long g_cInstances
0x180010f76  mov     dword ptr [rsi+8], 1
0x180010f7d  jmp     short loc_180010F82
0x180010f7f  mov     rsi, r14
0x180010f82  mov     [rdi+30h], rsi
0x180010f86  mov     ebx, 8007000Eh
0x180010f8b  test    rsi, rsi
0x180010f8e  cmovnz  ebx, r14d
0x180010f92  mov     [rbp+57h+arg_0], r14
0x180010f96  jz      loc_180011030
0x180010f9c  mov     [rbp+57h+arg_0], r14
0x180010fa0  mov     ebx, 80004005h
0x180010fa5  mov     rax, [rdi+28h]
0x180010fa9  test    rax, rax
0x180010fac  jnz     short loc_180010FC4
0x180010fae  lea     rcx, LibFileName; "MsftEdit.dll"
0x180010fb5  call    cs:__imp_LoadLibraryW
0x180010fbb  mov     [rdi+28h], rax
0x180010fbf  test    rax, rax
0x180010fc2  jz      short loc_180010FE9
0x180010fc4  lea     rdx, aCreatetextserv; "CreateTextServices"
0x180010fcb  mov     rcx, rax; hModule
0x180010fce  call    cs:__imp_GetProcAddress
0x180010fd4  test    rax, rax
0x180010fd7  jz      short loc_180010FE9
0x180010fd9  lea     r8, [rbp+57h+arg_0]
0x180010fdd  mov     rdx, rsi
0x180010fe0  xor     ecx, ecx
0x180010fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fe7  mov     ebx, eax
0x180010fe9  test    ebx, ebx
0x180010feb  js      short loc_180011030
0x180010fed  mov     rcx, [rbp+57h+arg_0]
0x180010ff1  mov     rax, [rcx]
0x180010ff4  lea     r8, [rbp+57h+arg_10]
0x180010ff8  lea     rdx, _GUID_8cc497c0_a1df_11ce_8098_00aa0047be5d
0x180010fff  mov     rax, [rax]
0x180011002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011007  test    eax, eax
0x180011009  js      short loc_18001102B
0x18001100b  mov     rcx, [rbp+57h+arg_0]
0x18001100f  mov     rax, [rcx]
0x180011012  lea     r8, [rbp+57h+arg_8]
0x180011016  lea     rdx, IID_ITextServices
0x18001101d  mov     rax, [rax]
0x180011020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011025  mov     ebx, eax
0x180011027  test    eax, eax
0x180011029  jns     short loc_180011030
0x18001102b  mov     ebx, 80041703h
0x180011030  mov     rcx, [rbp+57h+arg_0]
0x180011034  mov     [rbp+57h+arg_0], r14
0x180011038  test    rcx, rcx
0x18001103b  jz      short loc_18001104A
0x18001103d  mov     rax, [rcx]
0x180011040  mov     rax, [rax+10h]
0x180011044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011049  nop
0x18001104a  test    ebx, ebx
0x18001104c  js      loc_1800112A5
0x180011052  mov     [rbp+57h+arg_0], r14
0x180011056  mov     rcx, [rbp+57h+arg_8]
0x18001105a  mov     rax, [rcx]
0x18001105d  lea     rdx, [rbp+57h+arg_0]
0x180011061  mov     [rsp+0B0h+var_90], rdx
0x180011066  xor     r9d, r9d
0x180011069  xor     r8d, r8d
0x18001106c  mov     edx, 479h
0x180011071  mov     rax, [rax+18h]
0x180011075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001107a  test    eax, eax
0x18001107c  js      short loc_1800110AC
0x18001107e  mov     r9, [rbp+57h+arg_0]
0x180011082  bts     r9, 0Ah
0x180011087  mov     [rbp+57h+arg_0], r9
0x18001108b  mov     rcx, [rbp+57h+arg_8]
0x18001108f  mov     rax, [rcx]
0x180011092  lea     rdx, [rbp+57h+arg_0]
0x180011096  mov     [rsp+0B0h+var_90], rdx
0x18001109b  xor     r8d, r8d
0x18001109e  mov     edx, 478h
0x1800110a3  mov     rax, [rax+18h]
0x1800110a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110ac  mov     ebx, 8
0x1800110b1  cmp     [rdi+18h], r14d
0x1800110b5  jz      short loc_18001110E
0x1800110b7  mov     dword ptr [rbp+57h+var_80+8], r14d
0x1800110bb  mov     rax, [rdi+20h]
0x1800110bf  mov     qword ptr [rbp+57h+var_80], rax
0x1800110c3  lea     rax, ?EditStreamCallback@@YAK_KPEAEJPEAJ@Z; EditStreamCallback(unsigned __int64,uchar *,long,long *)
0x1800110ca  mov     qword ptr [rbp+57h+var_80+0Ch], rax
0x1800110ce  mov     [rbp+57h+arg_0], r14
0x1800110d2  mov     rcx, [rbp+57h+arg_8]
0x1800110d6  mov     rax, [rcx]
0x1800110d9  lea     rdx, [rbp+57h+arg_0]
0x1800110dd  mov     [rsp+0B0h+var_90], rdx
0x1800110e2  lea     r9, [rbp+57h+var_80]
0x1800110e6  mov     edx, 449h
0x1800110eb  lea     r8d, [rbx-6]
0x1800110ef  mov     rax, [rax+18h]
0x1800110f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110f8  mov     rcx, [rdi+20h]
0x1800110fc  mov     rax, [rcx]
0x1800110ff  mov     rax, [rax+10h]
0x180011103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011108  mov     [rdi+20h], r14
0x18001110c  jmp     short loc_18001114A
0x18001110e  xorps   xmm0, xmm0
0x180011111  xor     eax, eax
0x180011113  movups  [rbp+57h+var_80], xmm0
0x180011117  mov     [rbp+57h+var_70], rax
0x18001111b  mov     word ptr [rbp+57h+var_80], bx
0x18001111f  mov     rax, [rdi+20h]
0x180011123  mov     qword ptr [rbp+57h+var_80+8], rax
0x180011127  mov     rcx, [rbp+57h+arg_10]
0x18001112b  mov     rax, [rcx]
0x18001112e  mov     r9d, 4B0h
0x180011134  mov     r8d, 130h
0x18001113a  lea     rdx, [rbp+57h+var_80]
0x18001113e  mov     rax, [rax+80h]
0x180011145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001114a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_51365605@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_51365605@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51365605> `wil::Feature<__WilFeatureTraits_Feature_51365605>::GetImpl(void)'::`2'::impl
0x180011151  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_51365605@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51365605>::__private_IsEnabled(void)
0x180011156  test    al, al
0x180011158  jnz     short loc_18001116E
0x18001115a  mov     r8, [rdi+10h]
0x18001115e  lea     rdx, [rbp+57h+arg_10]
0x180011162  call    ?GetAllTheText@CThreadInfo@@AEAAJAEAV?$XInterface@UITextDocument@@@@PEAVCAllRuns@@@Z; CThreadInfo::GetAllTheText(XInterface<ITextDocument> &,CAllRuns *)
0x180011167  mov     ebx, eax
0x180011169  jmp     loc_1800112A5
0x18001116e  mov     [rbp+57h+pv], r14
0x180011172  lea     rcx, [rbp+57h+pv]
0x180011176  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::ensure_data(void)
0x18001117b  mov     rcx, [rax]
0x18001117e  add     rcx, rbx
0x180011181  lea     rdx, [rbp+57h+var_80]
0x180011185  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x18001118a  lea     rdx, [rbp+57h+pv]
0x18001118e  lea     rcx, [rbp+57h+var_60]
0x180011192  call    ??0?$test_watcher@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>,wil::err_returncode_policy> &)
0x180011197  mov     rbx, [rbp+57h+pv]
0x18001119b  test    rbx, rbx
0x18001119e  jz      short loc_1800111C2
0x1800111a0  or      eax, 0FFFFFFFFh
0x1800111a3  lock xadd [rbx+118h], eax
0x1800111ab  cmp     eax, 1
0x1800111ae  jnz     short loc_1800111C2
0x1800111b0  mov     rcx, rbx
0x1800111b3  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x1800111b8  mov     rcx, rbx; pv
0x1800111bb  call    cs:__imp_CoTaskMemFree
0x1800111c1  nop
0x1800111c2  xorps   xmm0, xmm0
0x1800111c5  movdqu  [rbp+57h+var_80], xmm0
0x1800111ca  mov     rax, [rdi+8]
0x1800111ce  test    rax, rax
0x1800111d1  jz      short loc_1800111D7
0x1800111d3  lock inc dword ptr [rax+8]
0x1800111d7  mov     rax, [rdi]
0x1800111da  mov     qword ptr [rbp+57h+var_80], rax
0x1800111de  mov     rax, [rdi+8]
0x1800111e2  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800111e6  lea     r9, [rbp+57h+var_80]
0x1800111ea  mov     r8, [rdi+10h]
0x1800111ee  lea     rdx, [rbp+57h+arg_10]
0x1800111f2  call    ?GetAllTheContent@CThreadInfo@@AEAAJAEAV?$XInterface@UITextDocument@@@@PEAVCAllRuns@@V?$shared_ptr@V?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@@std@@@Z; CThreadInfo::GetAllTheContent(XInterface<ITextDocument> &,CAllRuns *,std::shared_ptr<std::vector<winrt::com_ptr<IStream>>>)
0x1800111f7  mov     ebx, eax
0x1800111f9  test    eax, eax
0x1800111fb  js      short loc_18001122A
0x1800111fd  mov     rsi, [rbp+57h+var_28]
0x180011201  mov     [rbp+57h+arg_0], rsi
0x180011205  test    rsi, rsi
0x180011208  jz      short loc_180011211
0x18001120a  lock inc dword ptr [rsi+118h]
0x180011211  lea     rcx, [rsi+8]
0x180011215  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18001121a  mov     byte ptr [rsi+110h], 1
0x180011221  lea     rcx, [rbp+57h+arg_0]
0x180011225  call    ??1?$test_data_control@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(void)
0x18001122a  mov     rax, [rbp+57h+var_28]
0x18001122e  mov     [rbp+57h+arg_0], rax
0x180011232  test    rax, rax
0x180011235  jz      short loc_18001123E
0x180011237  lock inc dword ptr [rax+118h]
0x18001123e  lea     rsi, [rax+8]
0x180011242  mov     rcx, rsi
0x180011245  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18001124a  or      dword ptr [rsi+40h], 0B00h
0x180011251  cmp     [rsi+0F0h], r14
0x180011258  jz      short loc_180011267
0x18001125a  mov     edx, 0Ah
0x18001125f  mov     rcx, rsi
0x180011262  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x180011267  lea     rcx, [rbp+57h+arg_0]
0x18001126b  call    ??1?$test_data_control@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(void)
0x180011270  nop
0x180011271  mov     rsi, [rbp+57h+var_28]
0x180011275  test    rsi, rsi
0x180011278  jz      short loc_18001129B
0x18001127a  or      eax, 0FFFFFFFFh
0x18001127d  lock xadd [rsi+118h], eax
0x180011285  cmp     eax, 1
0x180011288  jnz     short loc_18001129B
0x18001128a  mov     rcx, rsi
0x18001128d  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x180011292  mov     rcx, rsi; pv
0x180011295  call    cs:__imp_CoTaskMemFree
0x18001129b  lea     rcx, [rbp+57h+var_58]; this
0x18001129f  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800112a4  nop
0x1800112a5  mov     rcx, [rbp+57h+arg_8]
0x1800112a9  mov     [rbp+57h+arg_8], r14
0x1800112ad  test    rcx, rcx
0x1800112b0  jz      short loc_1800112BF
0x1800112b2  mov     rax, [rcx]
0x1800112b5  mov     rax, [rax+10h]
0x1800112b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112be  nop
0x1800112bf  mov     rcx, [rbp+57h+arg_10]
0x1800112c3  mov     [rbp+57h+arg_10], r14
0x1800112c7  test    rcx, rcx
0x1800112ca  jz      short loc_1800112D9
0x1800112cc  mov     rax, [rcx]
0x1800112cf  mov     rax, [rax+10h]
0x1800112d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112d8  nop
0x1800112d9  mov     rcx, [rdi+30h]
0x1800112dd  test    rcx, rcx
0x1800112e0  jz      short loc_1800112F2
0x1800112e2  mov     rax, [rcx]
0x1800112e5  mov     rax, [rax+10h]
0x1800112e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ee  mov     [rdi+30h], r14
0x1800112f2  mov     eax, ebx
0x1800112f4  add     rsp, 90h
0x1800112fb  pop     r14
0x1800112fd  pop     rdi
0x1800112fe  pop     rsi
0x1800112ff  pop     rbx
0x180011300  pop     rbp
0x180011301  retn
```
