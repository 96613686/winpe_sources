# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>,Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18000d7fc`
- end: `0x18000da89`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVBasicProperties@FileProperties@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVBasicProperties@FileProperties@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVBasicProperties@FileProperties@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ae40`

## callees

- `0x180005504`
- `0x180008b68`
- `0x18000d7fc`
- `0x1800143c4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d8ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d8ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8d9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000d981`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000d981`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>,Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *>>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>'};
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>,Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>,Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>,Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *>>'::`2'::FTMEventDelegate::`vftable';
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
0x18000d7fc  mov     [rsp-28h+dwindex], r8
0x18000d801  mov     [rsp-28h+arg_8], edx
0x18000d805  push    rbp
0x18000d806  push    rbx
0x18000d807  push    rsi
0x18000d808  push    rdi
0x18000d809  push    r14
0x18000d80b  mov     rbp, rsp
0x18000d80e  sub     rsp, 50h
0x18000d812  mov     rdi, rcx
0x18000d815  mov     [rbp+var_20], rcx
0x18000d819  xor     r14d, r14d
0x18000d81c  test    rcx, rcx
0x18000d81f  jz      short loc_18000D82E
0x18000d821  mov     rax, [rcx]
0x18000d824  mov     rax, [rax+8]
0x18000d828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d82d  nop
0x18000d82e  mov     [rbp+arg_18], r14
0x18000d832  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d839  mov     ecx, 40h ; '@'; unsigned __int64
0x18000d83e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d843  mov     rbx, rax
0x18000d846  test    rax, rax
0x18000d849  jnz     short loc_18000D857
0x18000d84b  mov     [rbp+arg_8], 8007000Eh
0x18000d852  jmp     loc_18000DA4A
0x18000d857  lea     rax, ??_7?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::`vftable'
0x18000d85e  mov     [rbx], rax
0x18000d861  lea     rsi, [rbx+8]
0x18000d865  mov     rcx, rsi; this
0x18000d868  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000d86d  mov     dword ptr [rbx+2Ch], 1
0x18000d874  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVBasicProperties@FileProperties@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVBasicProperties@FileProperties@Storage@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>'}
0x18000d87b  mov     [rbx], rax
0x18000d87e  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVBasicProperties@FileProperties@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVBasicProperties@FileProperties@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVBasicProperties@FileProperties@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>,Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000d885  mov     [rsi], rax
0x18000d888  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d88f  test    rcx, rcx
0x18000d892  jz      short loc_18000D8A1
0x18000d894  mov     rax, [rcx]
0x18000d897  mov     rax, [rax+8]
0x18000d89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8a0  nop
0x18000d8a1  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVBasicProperties@FileProperties@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVBasicProperties@FileProperties@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVBasicProperties@FileProperties@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVBasicProperties@FileProperties@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>,Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>'}
0x18000d8a8  mov     [rbx], rax
0x18000d8ab  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVBasicProperties@FileProperties@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVBasicProperties@FileProperties@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVBasicProperties@FileProperties@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::FileProperties::BasicProperties *>,Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::FileProperties::BasicProperties *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000d8b2  mov     [rsi], rax
0x18000d8b5  mov     [rbx+30h], r14d
0x18000d8b9  mov     [rbx+38h], r14
0x18000d8bd  mov     r9d, 1F0003h; dwDesiredAccess
0x18000d8c3  xor     r8d, r8d; dwFlags
0x18000d8c6  xor     edx, edx; lpName
0x18000d8c8  xor     ecx, ecx; lpEventAttributes
0x18000d8ca  call    cs:__imp_CreateEventExW
0x18000d8d0  mov     [rbx+38h], rax
0x18000d8d4  test    rax, rax
0x18000d8d7  jnz     short loc_18000D90A
0x18000d8d9  call    cs:__imp_GetLastError
0x18000d8df  mov     esi, eax
0x18000d8e1  test    eax, eax
0x18000d8e3  jle     short loc_18000D8EE
0x18000d8e5  movzx   esi, ax
0x18000d8e8  or      esi, 80070000h
0x18000d8ee  mov     rax, [rbx]
0x18000d8f1  test    esi, esi
0x18000d8f3  jns     short loc_18000D90D
0x18000d8f5  mov     rcx, rbx
0x18000d8f8  mov     rax, [rax+10h]
0x18000d8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d901  nop
0x18000d902  mov     [rbp+arg_8], esi
0x18000d905  jmp     loc_18000DA4A
0x18000d90a  mov     rax, [rbx]
0x18000d90d  mov     rcx, rbx
0x18000d910  mov     rax, [rax+8]
0x18000d914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d919  nop
0x18000d91a  mov     [rbp+arg_18], rbx
0x18000d91e  mov     rax, [rbx]
0x18000d921  mov     rcx, rbx
0x18000d924  mov     rax, [rax+10h]
0x18000d928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d92d  nop
0x18000d92e  mov     [rbp+arg_8], r14d
0x18000d932  mov     rax, [rdi]
0x18000d935  mov     rdx, [rbp+arg_18]
0x18000d939  mov     rcx, rdi
0x18000d93c  mov     rax, [rax+30h]
0x18000d940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d945  mov     [rbp+arg_8], eax
0x18000d948  test    eax, eax
0x18000d94a  js      loc_18000DA4A
0x18000d950  mov     rax, [rbp+arg_18]
0x18000d954  mov     rcx, [rax+38h]
0x18000d958  mov     [rbp+pHandles], rcx
0x18000d95c  mov     [rbp+var_10], r14
0x18000d960  mov     bl, r14b
0x18000d963  mov     dword ptr [rbp+dwindex], r14d
0x18000d967  lea     rax, [rbp+dwindex]
0x18000d96b  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18000d970  lea     r9, [rbp+pHandles]; pHandles
0x18000d974  mov     r8d, 1; cHandles
0x18000d97a  or      edx, 0FFFFFFFFh; dwTimeout
0x18000d97d  lea     ecx, [r8+7]; dwFlags
0x18000d981  call    cs:__imp_CoWaitForMultipleHandles
0x18000d987  mov     [rbp+arg_8], eax
0x18000d98a  test    eax, eax
0x18000d98c  js      short loc_18000D99D
0x18000d98e  cmp     dword ptr [rbp+dwindex], r14d
0x18000d992  jz      short loc_18000D99D
0x18000d994  mov     [rbp+arg_8], 800704C7h
0x18000d99b  mov     bl, 1
0x18000d99d  mov     [rbp+arg_0], r14
0x18000d9a1  test    bl, bl
0x18000d9a3  jz      short loc_18000D9DD
0x18000d9a5  mov     rax, [rdi]
0x18000d9a8  mov     rbx, [rax]
0x18000d9ab  lea     rcx, [rbp+arg_0]
0x18000d9af  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000d9b4  mov     r8, rax
0x18000d9b7  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000d9be  mov     rcx, rdi
0x18000d9c1  mov     rax, rbx
0x18000d9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9c9  test    eax, eax
0x18000d9cb  js      short loc_18000D9DD
0x18000d9cd  mov     rcx, [rbp+arg_0]
0x18000d9d1  mov     rax, [rcx]
0x18000d9d4  mov     rax, [rax+48h]
0x18000d9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9dd  cmp     [rbp+arg_8], r14d
0x18000d9e1  jl      short loc_18000DA30
0x18000d9e3  mov     rax, [rbp+arg_18]
0x18000d9e7  cmp     dword ptr [rax+30h], 1
0x18000d9eb  jz      short loc_18000DA30
0x18000d9ed  cmp     [rbp+arg_0], r14
0x18000d9f1  jnz     short loc_18000DA1B
0x18000d9f3  mov     rax, [rdi]
0x18000d9f6  mov     rbx, [rax]
0x18000d9f9  lea     rcx, [rbp+arg_0]
0x18000d9fd  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000da02  mov     r8, rax
0x18000da05  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000da0c  mov     rcx, rdi
0x18000da0f  mov     rax, rbx
0x18000da12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da17  test    eax, eax
0x18000da19  js      short loc_18000DA30
0x18000da1b  mov     rcx, [rbp+arg_0]
0x18000da1f  mov     rax, [rcx]
0x18000da22  lea     rdx, [rbp+arg_8]
0x18000da26  mov     rax, [rax+40h]
0x18000da2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da2f  nop
0x18000da30  mov     rcx, [rbp+arg_0]
0x18000da34  test    rcx, rcx
0x18000da37  jz      short loc_18000DA4A
0x18000da39  mov     [rbp+arg_0], r14
0x18000da3d  mov     rax, [rcx]
0x18000da40  mov     rax, [rax+10h]
0x18000da44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da49  nop
0x18000da4a  mov     ebx, [rbp+arg_8]
0x18000da4d  mov     rcx, [rbp+arg_18]
0x18000da51  test    rcx, rcx
0x18000da54  jz      short loc_18000DA67
0x18000da56  mov     [rbp+arg_18], r14
0x18000da5a  mov     rax, [rcx]
0x18000da5d  mov     rax, [rax+10h]
0x18000da61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da66  nop
0x18000da67  test    rdi, rdi
0x18000da6a  jz      short loc_18000DA7C
0x18000da6c  mov     rcx, [rdi]
0x18000da6f  mov     rax, [rcx+10h]
0x18000da73  mov     rcx, rdi
0x18000da76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da7b  nop
0x18000da7c  mov     eax, ebx
0x18000da7e  add     rsp, 50h
0x18000da82  pop     r14
0x18000da84  pop     rdi
0x18000da85  pop     rsi
0x18000da86  pop     rbx
0x18000da87  pop     rbp
0x18000da88  retn
```
