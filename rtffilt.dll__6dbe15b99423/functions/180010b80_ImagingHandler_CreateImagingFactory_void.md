# ImagingHandler::CreateImagingFactory(void)

- ea: `0x180010b80`
- end: `0x180010e0b`
- name: `?CreateImagingFactory@ImagingHandler@@QEAAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180014030`

## callees

- `0x180006e80`
- `0x18000e47c`
- `0x18000f574`
- `0x18000fc3c`
- `0x18000fdb4`
- `0x1800103e4`
- `0x180010b80`
- `0x180011384`
- `0x1800156e4`
- `0x180015820`
- `0x180018c9c`
- `0x180018f38`
- `0x1800198bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010c3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010c3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010bcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010de7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010bcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010de7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010d27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010d27`

## string_xrefs

- `0x180010d42`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`

## pseudocode

```c
__int64 __fastcall ImagingHandler::CreateImagingFactory(LPVOID *ppv)
{
  volatile signed __int32 **inited; // rax
  volatile signed __int32 *v3; // rbx
  void *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 *Local; // rax
  _QWORD *v8; // rbx
  LPVOID *v9; // r9
  unsigned __int64 v10; // rdx
  char *v11; // rdi
  __int64 v12; // rbx
  HRESULT Instance; // eax
  unsigned int v14; // edi
  _BYTE *v15; // rbx
  char *v16; // rax
  char *v17; // rbx
  void *v18; // rbx
  _BYTE v20[16]; // [rsp+30h] [rbp-50h] BYREF
  void **v21; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v22[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v23; // [rsp+58h] [rbp-28h]
  DWORD CurrentThreadId; // [rsp+60h] [rbp-20h]
  __int64 v25; // [rsp+68h] [rbp-18h]
  char v26; // [rsp+70h] [rbp-10h]
  LPVOID v27; // [rsp+78h] [rbp-8h]
  LPVOID v28; // [rsp+A8h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp+30h] BYREF

  inited = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>,>(&pv);
  v3 = *inited;
  *inited = 0;
  v4 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 78, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(v4);
    CoTaskMemFree(v4);
  }
  tip2::details::shared_data<1,0,0>::start(v3 + 2, v20);
  v21 = &tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::`vftable';
  v22[0] = 0;
  v22[1] = &v21;
  v23 = 0;
  CurrentThreadId = 0;
  v25 = 0;
  v26 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v5) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v6,
                         v5);
    v22[0] = Local;
    if ( Local )
    {
      v23 = *Local;
      *Local = (__int64)v22;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v22[0] = 0;
  }
  v27 = (LPVOID)v3;
  if ( v3 )
  {
    _InterlockedIncrement(v3 + 78);
    if ( _InterlockedExchangeAdd(v3 + 78, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(v3);
      CoTaskMemFree((LPVOID)v3);
    }
  }
  v8 = v27;
  v28 = v27;
  if ( v27 )
    _InterlockedIncrement((volatile signed __int32 *)v27 + 78);
  tip2::details::shared_data<1,0,0>::begin_update(v8 + 1);
  v9 = ppv + 6;
  if ( v8 + 34 != ppv + 6 )
  {
    v10 = (unsigned __int64)ppv[8];
    if ( (unsigned __int64)ppv[9] > 7 )
      v9 = (LPVOID *)*v9;
    if ( v10 > v8[37] )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>();
    }
    else
    {
      if ( v8[37] <= 7u )
        v11 = (char *)(v8 + 34);
      else
        v11 = (char *)v8[34];
      v8[36] = v10;
      v12 = 2 * v10;
      memmove_0(v11, v9, 2 * v10);
      *(_WORD *)&v11[v12] = 0;
    }
  }
  tip2::test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(&v28);
  if ( *ppv )
    winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(ppv);
  Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, ppv);
  v14 = Instance;
  if ( Instance < 0 )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
      (const wchar_t *)0x24,
      (unsigned int)L"ImagingHandler::Init : Failed to init WICImagingFactory, hr(0x%08x)",
      (const wchar_t *)(unsigned int)Instance);
    v15 = v27;
    v28 = v27;
    if ( v27 )
      _InterlockedIncrement((volatile signed __int32 *)v27 + 78);
    tip2::details::shared_data<1,0,0>::begin_update(v15 + 8);
    v15[304] = 0;
    tip2::test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(&v28);
  }
  v16 = (char *)v27;
  v28 = v27;
  if ( v27 )
    _InterlockedIncrement((volatile signed __int32 *)v27 + 78);
  v17 = v16 + 8;
  tip2::details::shared_data<1,0,0>::begin_update(v16 + 8);
  *((_DWORD *)v17 + 16) |= 0xB00u;
  if ( *((_QWORD *)v17 + 30) )
    tip2::details::shared_data<1,0,0>::complete_helper(v17, 10);
  tip2::test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(&v28);
  v18 = v27;
  if ( v27 && _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 78, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(v18);
    CoTaskMemFree(v18);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v22);
  return v14;
}

```

## disassembly

```asm
0x180010b80  mov     [rsp-18h+arg_0], rbx
0x180010b85  push    rbp
0x180010b86  push    rsi
0x180010b87  push    rdi
0x180010b88  mov     rbp, rsp
0x180010b8b  sub     rsp, 80h
0x180010b92  mov     rsi, rcx
0x180010b95  lea     rcx, [rbp+pv]
0x180010b99  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>,>(void)
0x180010b9e  mov     rbx, [rax]
0x180010ba1  mov     qword ptr [rax], 0
0x180010ba8  mov     rdi, [rbp+pv]
0x180010bac  test    rdi, rdi
0x180010baf  jz      short loc_180010BD2
0x180010bb1  or      eax, 0FFFFFFFFh
0x180010bb4  lock xadd [rdi+138h], eax
0x180010bbc  cmp     eax, 1
0x180010bbf  jnz     short loc_180010BD2
0x180010bc1  mov     rcx, rdi
0x180010bc4  call    ??1?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(void)
0x180010bc9  mov     rcx, rdi; pv
0x180010bcc  call    cs:__imp_CoTaskMemFree
0x180010bd2  lea     rcx, [rbx+8]
0x180010bd6  lea     rdx, [rbp+var_50]
0x180010bda  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x180010bdf  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::`vftable'
0x180010be6  mov     [rbp+var_40], rax
0x180010bea  mov     [rbp+var_38], 0
0x180010bf2  lea     rax, [rbp+var_40]
0x180010bf6  mov     [rbp+var_30], rax
0x180010bfa  mov     [rbp+var_28], 0
0x180010c02  mov     [rbp+var_20], 0
0x180010c09  mov     [rbp+var_18], 0
0x180010c11  mov     [rbp+var_10], 0
0x180010c15  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180010c1d  jz      short loc_180010C48
0x180010c1f  mov     dl, 1
0x180010c21  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180010c26  mov     [rbp+var_38], rax
0x180010c2a  test    rax, rax
0x180010c2d  jz      short loc_180010C50
0x180010c2f  mov     rcx, [rax]
0x180010c32  mov     [rbp+var_28], rcx
0x180010c36  lea     rcx, [rbp+var_38]
0x180010c3a  mov     [rax], rcx
0x180010c3d  call    cs:__imp_GetCurrentThreadId
0x180010c43  mov     [rbp+var_20], eax
0x180010c46  jmp     short loc_180010C50
0x180010c48  mov     [rbp+var_38], 0
0x180010c50  mov     [rbp+var_8], rbx
0x180010c54  test    rbx, rbx
0x180010c57  jz      short loc_180010C82
0x180010c59  lock inc dword ptr [rbx+138h]
0x180010c60  or      eax, 0FFFFFFFFh
0x180010c63  lock xadd [rbx+138h], eax
0x180010c6b  cmp     eax, 1
0x180010c6e  jnz     short loc_180010C82
0x180010c70  mov     rcx, rbx
0x180010c73  call    ??1?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(void)
0x180010c78  mov     rcx, rbx; pv
0x180010c7b  call    cs:__imp_CoTaskMemFree
0x180010c81  nop
0x180010c82  mov     rbx, [rbp+var_8]
0x180010c86  mov     [rbp+arg_8], rbx
0x180010c8a  test    rbx, rbx
0x180010c8d  jz      short loc_180010C96
0x180010c8f  lock inc dword ptr [rbx+138h]
0x180010c96  lea     rcx, [rbx+8]
0x180010c9a  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180010c9f  nop
0x180010ca0  lea     r9, [rsi+30h]
0x180010ca4  lea     rcx, [rbx+110h]
0x180010cab  cmp     rcx, r9
0x180010cae  jz      short loc_180010CF7
0x180010cb0  mov     rdx, [r9+10h]
0x180010cb4  cmp     qword ptr [r9+18h], 7
0x180010cb9  jbe     short loc_180010CBE
0x180010cbb  mov     r9, [r9]
0x180010cbe  cmp     rdx, [rcx+18h]
0x180010cc2  ja      short loc_180010CF1
0x180010cc4  cmp     qword ptr [rcx+18h], 7
0x180010cc9  jbe     short loc_180010CD0
0x180010ccb  mov     rdi, [rcx]
0x180010cce  jmp     short loc_180010CD3
0x180010cd0  mov     rdi, rcx
0x180010cd3  mov     [rcx+10h], rdx
0x180010cd7  lea     rbx, [rdx+rdx]
0x180010cdb  mov     r8, rbx; Size
0x180010cde  mov     rdx, r9; Src
0x180010ce1  mov     rcx, rdi; void *
0x180010ce4  call    memmove_0
0x180010ce9  xor     eax, eax
0x180010ceb  mov     [rbx+rdi], ax
0x180010cef  jmp     short loc_180010CF7
0x180010cf1  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x180010cf6  nop
0x180010cf7  lea     rcx, [rbp+arg_8]
0x180010cfb  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(void)
0x180010d00  cmp     qword ptr [rsi], 0
0x180010d04  jz      short loc_180010D0E
0x180010d06  mov     rcx, rsi
0x180010d09  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180010d0e  mov     [rsp+80h+ppv], rsi; ppv
0x180010d13  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180010d1a  xor     edx, edx; pUnkOuter
0x180010d1c  lea     r8d, [rdx+1]; dwClsContext
0x180010d20  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180010d27  call    cs:__imp_CoCreateInstance
0x180010d2d  mov     edi, eax
0x180010d2f  test    eax, eax
0x180010d31  jns     short loc_180010D7B
0x180010d33  mov     r9d, eax; wchar_t *
0x180010d36  lea     r8, aImaginghandler_2; "ImagingHandler::Init : Failed to init W"...
0x180010d3d  mov     edx, 24h ; '$'; wchar_t *
0x180010d42  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180010d49  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180010d4e  mov     rbx, [rbp+var_8]
0x180010d52  mov     [rbp+arg_8], rbx
0x180010d56  test    rbx, rbx
0x180010d59  jz      short loc_180010D62
0x180010d5b  lock inc dword ptr [rbx+138h]
0x180010d62  lea     rcx, [rbx+8]
0x180010d66  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180010d6b  mov     byte ptr [rbx+130h], 0
0x180010d72  lea     rcx, [rbp+arg_8]
0x180010d76  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(void)
0x180010d7b  mov     rax, [rbp+var_8]
0x180010d7f  mov     [rbp+arg_8], rax
0x180010d83  test    rax, rax
0x180010d86  jz      short loc_180010D8F
0x180010d88  lock inc dword ptr [rax+138h]
0x180010d8f  lea     rbx, [rax+8]
0x180010d93  mov     rcx, rbx
0x180010d96  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180010d9b  or      dword ptr [rbx+40h], 0B00h
0x180010da2  cmp     qword ptr [rbx+0F0h], 0
0x180010daa  jz      short loc_180010DB9
0x180010dac  mov     edx, 0Ah
0x180010db1  mov     rcx, rbx
0x180010db4  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x180010db9  lea     rcx, [rbp+arg_8]
0x180010dbd  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(void)
0x180010dc2  nop
0x180010dc3  mov     rbx, [rbp+var_8]
0x180010dc7  test    rbx, rbx
0x180010dca  jz      short loc_180010DED
0x180010dcc  or      eax, 0FFFFFFFFh
0x180010dcf  lock xadd [rbx+138h], eax
0x180010dd7  cmp     eax, 1
0x180010dda  jnz     short loc_180010DED
0x180010ddc  mov     rcx, rbx
0x180010ddf  call    ??1?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(void)
0x180010de4  mov     rcx, rbx; pv
0x180010de7  call    cs:__imp_CoTaskMemFree
0x180010ded  lea     rcx, [rbp+var_38]; this
0x180010df1  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180010df6  mov     eax, edi
0x180010df8  mov     rbx, [rsp+80h+arg_0]
0x180010e00  add     rsp, 80h
0x180010e07  pop     rdi
0x180010e08  pop     rsi
0x180010e09  pop     rbp
0x180010e0a  retn
```
