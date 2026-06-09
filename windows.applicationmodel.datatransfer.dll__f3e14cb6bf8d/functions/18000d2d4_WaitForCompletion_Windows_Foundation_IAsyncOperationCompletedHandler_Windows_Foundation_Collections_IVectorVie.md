# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18000d2d4`
- end: `0x18000d561`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007028`

## callees

- `0x180005504`
- `0x180008b68`
- `0x18000d2d4`
- `0x1800143c4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d3a2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d3a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3b1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000d459`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000d459`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64),
        HRESULT a2,
        __int64 a3)
{
  _DWORD *v4; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // esi
  __int64 v8; // rax
  char v9; // bl
  int (__fastcall *v10)(_QWORD, GUID *, __int64); // rbx
  __int64 v11; // rax
  int (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  HANDLE *v16; // rcx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+80h] [rbp+30h] BYREF
  HRESULT v20; // [rsp+88h] [rbp+38h] BYREF
  __int64 dwindex; // [rsp+90h] [rbp+40h] BYREF
  HANDLE *v22; // [rsp+98h] [rbp+48h]

  dwindex = a3;
  v20 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[1])(a1);
  v22 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v4[12] = 0;
  *((_QWORD *)v4 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)v4 + 7) = Event;
  if ( Event )
  {
    v8 = *(_QWORD *)v4;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = *(_QWORD *)v4;
    if ( v7 < 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(v8 + 16))(v4);
      v20 = v7;
      goto LABEL_27;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(v8 + 8))(v4);
  v22 = (HANDLE *)v4;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  v20 = 0;
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64), HANDLE *))(*a1)[6])(a1, v22);
  if ( v20 >= 0 )
  {
    pHandles[0] = v22[7];
    pHandles[1] = 0;
    v9 = 0;
    LODWORD(dwindex) = 0;
    v20 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
    if ( v20 >= 0 && (_DWORD)dwindex )
    {
      v20 = -2147023673;
      v9 = 1;
    }
    v19 = 0;
    if ( v9 )
    {
      v10 = **a1;
      v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v19);
      if ( v10(a1, &GUID_00000036_0000_0000_c000_000000000046, v11) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 72LL))(v19);
    }
    if ( v20 >= 0 && *((_DWORD *)v22 + 12) != 1 )
    {
      if ( v19
        || (v12 = **a1,
            v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v19),
            v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0) )
      {
        (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v19 + 64LL))(v19, &v20);
      }
    }
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
LABEL_27:
  v15 = v20;
  v16 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*((void (__fastcall **)(HANDLE *))*v16 + 2))(v16);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[2])(a1);
  return v15;
}

```

## disassembly

```asm
0x18000d2d4  mov     [rsp-28h+dwindex], r8
0x18000d2d9  mov     [rsp-28h+arg_8], edx
0x18000d2dd  push    rbp
0x18000d2de  push    rbx
0x18000d2df  push    rsi
0x18000d2e0  push    rdi
0x18000d2e1  push    r14
0x18000d2e3  mov     rbp, rsp
0x18000d2e6  sub     rsp, 50h
0x18000d2ea  mov     rdi, rcx
0x18000d2ed  mov     [rbp+var_20], rcx
0x18000d2f1  xor     r14d, r14d
0x18000d2f4  test    rcx, rcx
0x18000d2f7  jz      short loc_18000D306
0x18000d2f9  mov     rax, [rcx]
0x18000d2fc  mov     rax, [rax+8]
0x18000d300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d305  nop
0x18000d306  mov     [rbp+arg_18], r14
0x18000d30a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d311  mov     ecx, 40h ; '@'; unsigned __int64
0x18000d316  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d31b  mov     rbx, rax
0x18000d31e  test    rax, rax
0x18000d321  jnz     short loc_18000D32F
0x18000d323  mov     [rbp+arg_8], 8007000Eh
0x18000d32a  jmp     loc_18000D522
0x18000d32f  lea     rax, ??_7?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::`vftable'
0x18000d336  mov     [rbx], rax
0x18000d339  lea     rsi, [rbx+8]
0x18000d33d  mov     rcx, rsi; this
0x18000d340  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000d345  mov     dword ptr [rbx+2Ch], 1
0x18000d34c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>'}
0x18000d353  mov     [rbx], rax
0x18000d356  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000d35d  mov     [rsi], rax
0x18000d360  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d367  test    rcx, rcx
0x18000d36a  jz      short loc_18000D379
0x18000d36c  mov     rax, [rcx]
0x18000d36f  mov     rax, [rax+8]
0x18000d373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d378  nop
0x18000d379  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>'}
0x18000d380  mov     [rbx], rax
0x18000d383  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000d38a  mov     [rsi], rax
0x18000d38d  mov     [rbx+30h], r14d
0x18000d391  mov     [rbx+38h], r14
0x18000d395  mov     r9d, 1F0003h; dwDesiredAccess
0x18000d39b  xor     r8d, r8d; dwFlags
0x18000d39e  xor     edx, edx; lpName
0x18000d3a0  xor     ecx, ecx; lpEventAttributes
0x18000d3a2  call    cs:__imp_CreateEventExW
0x18000d3a8  mov     [rbx+38h], rax
0x18000d3ac  test    rax, rax
0x18000d3af  jnz     short loc_18000D3E2
0x18000d3b1  call    cs:__imp_GetLastError
0x18000d3b7  mov     esi, eax
0x18000d3b9  test    eax, eax
0x18000d3bb  jle     short loc_18000D3C6
0x18000d3bd  movzx   esi, ax
0x18000d3c0  or      esi, 80070000h
0x18000d3c6  mov     rax, [rbx]
0x18000d3c9  test    esi, esi
0x18000d3cb  jns     short loc_18000D3E5
0x18000d3cd  mov     rcx, rbx
0x18000d3d0  mov     rax, [rax+10h]
0x18000d3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d9  nop
0x18000d3da  mov     [rbp+arg_8], esi
0x18000d3dd  jmp     loc_18000D522
0x18000d3e2  mov     rax, [rbx]
0x18000d3e5  mov     rcx, rbx
0x18000d3e8  mov     rax, [rax+8]
0x18000d3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3f1  nop
0x18000d3f2  mov     [rbp+arg_18], rbx
0x18000d3f6  mov     rax, [rbx]
0x18000d3f9  mov     rcx, rbx
0x18000d3fc  mov     rax, [rax+10h]
0x18000d400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d405  nop
0x18000d406  mov     [rbp+arg_8], r14d
0x18000d40a  mov     rax, [rdi]
0x18000d40d  mov     rdx, [rbp+arg_18]
0x18000d411  mov     rcx, rdi
0x18000d414  mov     rax, [rax+30h]
0x18000d418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d41d  mov     [rbp+arg_8], eax
0x18000d420  test    eax, eax
0x18000d422  js      loc_18000D522
0x18000d428  mov     rax, [rbp+arg_18]
0x18000d42c  mov     rcx, [rax+38h]
0x18000d430  mov     [rbp+pHandles], rcx
0x18000d434  mov     [rbp+var_10], r14
0x18000d438  mov     bl, r14b
0x18000d43b  mov     dword ptr [rbp+dwindex], r14d
0x18000d43f  lea     rax, [rbp+dwindex]
0x18000d443  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18000d448  lea     r9, [rbp+pHandles]; pHandles
0x18000d44c  mov     r8d, 1; cHandles
0x18000d452  or      edx, 0FFFFFFFFh; dwTimeout
0x18000d455  lea     ecx, [r8+7]; dwFlags
0x18000d459  call    cs:__imp_CoWaitForMultipleHandles
0x18000d45f  mov     [rbp+arg_8], eax
0x18000d462  test    eax, eax
0x18000d464  js      short loc_18000D475
0x18000d466  cmp     dword ptr [rbp+dwindex], r14d
0x18000d46a  jz      short loc_18000D475
0x18000d46c  mov     [rbp+arg_8], 800704C7h
0x18000d473  mov     bl, 1
0x18000d475  mov     [rbp+arg_0], r14
0x18000d479  test    bl, bl
0x18000d47b  jz      short loc_18000D4B5
0x18000d47d  mov     rax, [rdi]
0x18000d480  mov     rbx, [rax]
0x18000d483  lea     rcx, [rbp+arg_0]
0x18000d487  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000d48c  mov     r8, rax
0x18000d48f  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000d496  mov     rcx, rdi
0x18000d499  mov     rax, rbx
0x18000d49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4a1  test    eax, eax
0x18000d4a3  js      short loc_18000D4B5
0x18000d4a5  mov     rcx, [rbp+arg_0]
0x18000d4a9  mov     rax, [rcx]
0x18000d4ac  mov     rax, [rax+48h]
0x18000d4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4b5  cmp     [rbp+arg_8], r14d
0x18000d4b9  jl      short loc_18000D508
0x18000d4bb  mov     rax, [rbp+arg_18]
0x18000d4bf  cmp     dword ptr [rax+30h], 1
0x18000d4c3  jz      short loc_18000D508
0x18000d4c5  cmp     [rbp+arg_0], r14
0x18000d4c9  jnz     short loc_18000D4F3
0x18000d4cb  mov     rax, [rdi]
0x18000d4ce  mov     rbx, [rax]
0x18000d4d1  lea     rcx, [rbp+arg_0]
0x18000d4d5  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000d4da  mov     r8, rax
0x18000d4dd  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000d4e4  mov     rcx, rdi
0x18000d4e7  mov     rax, rbx
0x18000d4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4ef  test    eax, eax
0x18000d4f1  js      short loc_18000D508
0x18000d4f3  mov     rcx, [rbp+arg_0]
0x18000d4f7  mov     rax, [rcx]
0x18000d4fa  lea     rdx, [rbp+arg_8]
0x18000d4fe  mov     rax, [rax+40h]
0x18000d502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d507  nop
0x18000d508  mov     rcx, [rbp+arg_0]
0x18000d50c  test    rcx, rcx
0x18000d50f  jz      short loc_18000D522
0x18000d511  mov     [rbp+arg_0], r14
0x18000d515  mov     rax, [rcx]
0x18000d518  mov     rax, [rax+10h]
0x18000d51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d521  nop
0x18000d522  mov     ebx, [rbp+arg_8]
0x18000d525  mov     rcx, [rbp+arg_18]
0x18000d529  test    rcx, rcx
0x18000d52c  jz      short loc_18000D53F
0x18000d52e  mov     [rbp+arg_18], r14
0x18000d532  mov     rax, [rcx]
0x18000d535  mov     rax, [rax+10h]
0x18000d539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53e  nop
0x18000d53f  test    rdi, rdi
0x18000d542  jz      short loc_18000D554
0x18000d544  mov     rcx, [rdi]
0x18000d547  mov     rax, [rcx+10h]
0x18000d54b  mov     rcx, rdi
0x18000d54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d553  nop
0x18000d554  mov     eax, ebx
0x18000d556  add     rsp, 50h
0x18000d55a  pop     r14
0x18000d55c  pop     rdi
0x18000d55d  pop     rsi
0x18000d55e  pop     rbx
0x18000d55f  pop     rbp
0x18000d560  retn
```
