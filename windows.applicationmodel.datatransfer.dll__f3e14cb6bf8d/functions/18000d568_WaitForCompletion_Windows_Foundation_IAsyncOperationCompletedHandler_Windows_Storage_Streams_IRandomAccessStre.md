# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18000d568`
- end: `0x18000d7f5`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023138`

## callees

- `0x180005504`
- `0x180008b68`
- `0x18000d568`
- `0x1800143c4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d636`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d645`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000d6ed`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000d6ed`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x18000d568  mov     [rsp-28h+dwindex], r8
0x18000d56d  mov     [rsp-28h+arg_8], edx
0x18000d571  push    rbp
0x18000d572  push    rbx
0x18000d573  push    rsi
0x18000d574  push    rdi
0x18000d575  push    r14
0x18000d577  mov     rbp, rsp
0x18000d57a  sub     rsp, 50h
0x18000d57e  mov     rdi, rcx
0x18000d581  mov     [rbp+var_20], rcx
0x18000d585  xor     r14d, r14d
0x18000d588  test    rcx, rcx
0x18000d58b  jz      short loc_18000D59A
0x18000d58d  mov     rax, [rcx]
0x18000d590  mov     rax, [rax+8]
0x18000d594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d599  nop
0x18000d59a  mov     [rbp+arg_18], r14
0x18000d59e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d5a5  mov     ecx, 40h ; '@'; unsigned __int64
0x18000d5aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d5af  mov     rbx, rax
0x18000d5b2  test    rax, rax
0x18000d5b5  jnz     short loc_18000D5C3
0x18000d5b7  mov     [rbp+arg_8], 8007000Eh
0x18000d5be  jmp     loc_18000D7B6
0x18000d5c3  lea     rax, ??_7?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::`vftable'
0x18000d5ca  mov     [rbx], rax
0x18000d5cd  lea     rsi, [rbx+8]
0x18000d5d1  mov     rcx, rsi; this
0x18000d5d4  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000d5d9  mov     dword ptr [rbx+2Ch], 1
0x18000d5e0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>'}
0x18000d5e7  mov     [rbx], rax
0x18000d5ea  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000d5f1  mov     [rsi], rax
0x18000d5f4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d5fb  test    rcx, rcx
0x18000d5fe  jz      short loc_18000D60D
0x18000d600  mov     rax, [rcx]
0x18000d603  mov     rax, [rax+8]
0x18000d607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d60c  nop
0x18000d60d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>'}
0x18000d614  mov     [rbx], rax
0x18000d617  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000d61e  mov     [rsi], rax
0x18000d621  mov     [rbx+30h], r14d
0x18000d625  mov     [rbx+38h], r14
0x18000d629  mov     r9d, 1F0003h; dwDesiredAccess
0x18000d62f  xor     r8d, r8d; dwFlags
0x18000d632  xor     edx, edx; lpName
0x18000d634  xor     ecx, ecx; lpEventAttributes
0x18000d636  call    cs:__imp_CreateEventExW
0x18000d63c  mov     [rbx+38h], rax
0x18000d640  test    rax, rax
0x18000d643  jnz     short loc_18000D676
0x18000d645  call    cs:__imp_GetLastError
0x18000d64b  mov     esi, eax
0x18000d64d  test    eax, eax
0x18000d64f  jle     short loc_18000D65A
0x18000d651  movzx   esi, ax
0x18000d654  or      esi, 80070000h
0x18000d65a  mov     rax, [rbx]
0x18000d65d  test    esi, esi
0x18000d65f  jns     short loc_18000D679
0x18000d661  mov     rcx, rbx
0x18000d664  mov     rax, [rax+10h]
0x18000d668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d66d  nop
0x18000d66e  mov     [rbp+arg_8], esi
0x18000d671  jmp     loc_18000D7B6
0x18000d676  mov     rax, [rbx]
0x18000d679  mov     rcx, rbx
0x18000d67c  mov     rax, [rax+8]
0x18000d680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d685  nop
0x18000d686  mov     [rbp+arg_18], rbx
0x18000d68a  mov     rax, [rbx]
0x18000d68d  mov     rcx, rbx
0x18000d690  mov     rax, [rax+10h]
0x18000d694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d699  nop
0x18000d69a  mov     [rbp+arg_8], r14d
0x18000d69e  mov     rax, [rdi]
0x18000d6a1  mov     rdx, [rbp+arg_18]
0x18000d6a5  mov     rcx, rdi
0x18000d6a8  mov     rax, [rax+30h]
0x18000d6ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6b1  mov     [rbp+arg_8], eax
0x18000d6b4  test    eax, eax
0x18000d6b6  js      loc_18000D7B6
0x18000d6bc  mov     rax, [rbp+arg_18]
0x18000d6c0  mov     rcx, [rax+38h]
0x18000d6c4  mov     [rbp+pHandles], rcx
0x18000d6c8  mov     [rbp+var_10], r14
0x18000d6cc  mov     bl, r14b
0x18000d6cf  mov     dword ptr [rbp+dwindex], r14d
0x18000d6d3  lea     rax, [rbp+dwindex]
0x18000d6d7  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18000d6dc  lea     r9, [rbp+pHandles]; pHandles
0x18000d6e0  mov     r8d, 1; cHandles
0x18000d6e6  or      edx, 0FFFFFFFFh; dwTimeout
0x18000d6e9  lea     ecx, [r8+7]; dwFlags
0x18000d6ed  call    cs:__imp_CoWaitForMultipleHandles
0x18000d6f3  mov     [rbp+arg_8], eax
0x18000d6f6  test    eax, eax
0x18000d6f8  js      short loc_18000D709
0x18000d6fa  cmp     dword ptr [rbp+dwindex], r14d
0x18000d6fe  jz      short loc_18000D709
0x18000d700  mov     [rbp+arg_8], 800704C7h
0x18000d707  mov     bl, 1
0x18000d709  mov     [rbp+arg_0], r14
0x18000d70d  test    bl, bl
0x18000d70f  jz      short loc_18000D749
0x18000d711  mov     rax, [rdi]
0x18000d714  mov     rbx, [rax]
0x18000d717  lea     rcx, [rbp+arg_0]
0x18000d71b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000d720  mov     r8, rax
0x18000d723  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000d72a  mov     rcx, rdi
0x18000d72d  mov     rax, rbx
0x18000d730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d735  test    eax, eax
0x18000d737  js      short loc_18000D749
0x18000d739  mov     rcx, [rbp+arg_0]
0x18000d73d  mov     rax, [rcx]
0x18000d740  mov     rax, [rax+48h]
0x18000d744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d749  cmp     [rbp+arg_8], r14d
0x18000d74d  jl      short loc_18000D79C
0x18000d74f  mov     rax, [rbp+arg_18]
0x18000d753  cmp     dword ptr [rax+30h], 1
0x18000d757  jz      short loc_18000D79C
0x18000d759  cmp     [rbp+arg_0], r14
0x18000d75d  jnz     short loc_18000D787
0x18000d75f  mov     rax, [rdi]
0x18000d762  mov     rbx, [rax]
0x18000d765  lea     rcx, [rbp+arg_0]
0x18000d769  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000d76e  mov     r8, rax
0x18000d771  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000d778  mov     rcx, rdi
0x18000d77b  mov     rax, rbx
0x18000d77e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d783  test    eax, eax
0x18000d785  js      short loc_18000D79C
0x18000d787  mov     rcx, [rbp+arg_0]
0x18000d78b  mov     rax, [rcx]
0x18000d78e  lea     rdx, [rbp+arg_8]
0x18000d792  mov     rax, [rax+40h]
0x18000d796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d79b  nop
0x18000d79c  mov     rcx, [rbp+arg_0]
0x18000d7a0  test    rcx, rcx
0x18000d7a3  jz      short loc_18000D7B6
0x18000d7a5  mov     [rbp+arg_0], r14
0x18000d7a9  mov     rax, [rcx]
0x18000d7ac  mov     rax, [rax+10h]
0x18000d7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7b5  nop
0x18000d7b6  mov     ebx, [rbp+arg_8]
0x18000d7b9  mov     rcx, [rbp+arg_18]
0x18000d7bd  test    rcx, rcx
0x18000d7c0  jz      short loc_18000D7D3
0x18000d7c2  mov     [rbp+arg_18], r14
0x18000d7c6  mov     rax, [rcx]
0x18000d7c9  mov     rax, [rax+10h]
0x18000d7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7d2  nop
0x18000d7d3  test    rdi, rdi
0x18000d7d6  jz      short loc_18000D7E8
0x18000d7d8  mov     rcx, [rdi]
0x18000d7db  mov     rax, [rcx+10h]
0x18000d7df  mov     rcx, rdi
0x18000d7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7e7  nop
0x18000d7e8  mov     eax, ebx
0x18000d7ea  add     rsp, 50h
0x18000d7ee  pop     r14
0x18000d7f0  pop     rdi
0x18000d7f1  pop     rsi
0x18000d7f2  pop     rbx
0x18000d7f3  pop     rbp
0x18000d7f4  retn
```
