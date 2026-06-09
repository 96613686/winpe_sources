# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18000da90`
- end: `0x18000dd1d`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006fcc`

## callees

- `0x180005504`
- `0x180008b68`
- `0x18000da90`
- `0x1800143c4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000db5e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000db5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db6d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000dc15`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000dc15`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x18000da90  mov     [rsp-28h+dwindex], r8
0x18000da95  mov     [rsp-28h+arg_8], edx
0x18000da99  push    rbp
0x18000da9a  push    rbx
0x18000da9b  push    rsi
0x18000da9c  push    rdi
0x18000da9d  push    r14
0x18000da9f  mov     rbp, rsp
0x18000daa2  sub     rsp, 50h
0x18000daa6  mov     rdi, rcx
0x18000daa9  mov     [rbp+var_20], rcx
0x18000daad  xor     r14d, r14d
0x18000dab0  test    rcx, rcx
0x18000dab3  jz      short loc_18000DAC2
0x18000dab5  mov     rax, [rcx]
0x18000dab8  mov     rax, [rax+8]
0x18000dabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dac1  nop
0x18000dac2  mov     [rbp+arg_18], r14
0x18000dac6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dacd  mov     ecx, 40h ; '@'; unsigned __int64
0x18000dad2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dad7  mov     rbx, rax
0x18000dada  test    rax, rax
0x18000dadd  jnz     short loc_18000DAEB
0x18000dadf  mov     [rbp+arg_8], 8007000Eh
0x18000dae6  jmp     loc_18000DCDE
0x18000daeb  lea     rax, ??_7?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::`vftable'
0x18000daf2  mov     [rbx], rax
0x18000daf5  lea     rsi, [rbx+8]
0x18000daf9  mov     rcx, rsi; this
0x18000dafc  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000db01  mov     dword ptr [rbx+2Ch], 1
0x18000db08  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x18000db0f  mov     [rbx], rax
0x18000db12  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000db19  mov     [rsi], rax
0x18000db1c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000db23  test    rcx, rcx
0x18000db26  jz      short loc_18000DB35
0x18000db28  mov     rax, [rcx]
0x18000db2b  mov     rax, [rax+8]
0x18000db2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db34  nop
0x18000db35  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x18000db3c  mov     [rbx], rax
0x18000db3f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000db46  mov     [rsi], rax
0x18000db49  mov     [rbx+30h], r14d
0x18000db4d  mov     [rbx+38h], r14
0x18000db51  mov     r9d, 1F0003h; dwDesiredAccess
0x18000db57  xor     r8d, r8d; dwFlags
0x18000db5a  xor     edx, edx; lpName
0x18000db5c  xor     ecx, ecx; lpEventAttributes
0x18000db5e  call    cs:__imp_CreateEventExW
0x18000db64  mov     [rbx+38h], rax
0x18000db68  test    rax, rax
0x18000db6b  jnz     short loc_18000DB9E
0x18000db6d  call    cs:__imp_GetLastError
0x18000db73  mov     esi, eax
0x18000db75  test    eax, eax
0x18000db77  jle     short loc_18000DB82
0x18000db79  movzx   esi, ax
0x18000db7c  or      esi, 80070000h
0x18000db82  mov     rax, [rbx]
0x18000db85  test    esi, esi
0x18000db87  jns     short loc_18000DBA1
0x18000db89  mov     rcx, rbx
0x18000db8c  mov     rax, [rax+10h]
0x18000db90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db95  nop
0x18000db96  mov     [rbp+arg_8], esi
0x18000db99  jmp     loc_18000DCDE
0x18000db9e  mov     rax, [rbx]
0x18000dba1  mov     rcx, rbx
0x18000dba4  mov     rax, [rax+8]
0x18000dba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbad  nop
0x18000dbae  mov     [rbp+arg_18], rbx
0x18000dbb2  mov     rax, [rbx]
0x18000dbb5  mov     rcx, rbx
0x18000dbb8  mov     rax, [rax+10h]
0x18000dbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc1  nop
0x18000dbc2  mov     [rbp+arg_8], r14d
0x18000dbc6  mov     rax, [rdi]
0x18000dbc9  mov     rdx, [rbp+arg_18]
0x18000dbcd  mov     rcx, rdi
0x18000dbd0  mov     rax, [rax+30h]
0x18000dbd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbd9  mov     [rbp+arg_8], eax
0x18000dbdc  test    eax, eax
0x18000dbde  js      loc_18000DCDE
0x18000dbe4  mov     rax, [rbp+arg_18]
0x18000dbe8  mov     rcx, [rax+38h]
0x18000dbec  mov     [rbp+pHandles], rcx
0x18000dbf0  mov     [rbp+var_10], r14
0x18000dbf4  mov     bl, r14b
0x18000dbf7  mov     dword ptr [rbp+dwindex], r14d
0x18000dbfb  lea     rax, [rbp+dwindex]
0x18000dbff  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18000dc04  lea     r9, [rbp+pHandles]; pHandles
0x18000dc08  mov     r8d, 1; cHandles
0x18000dc0e  or      edx, 0FFFFFFFFh; dwTimeout
0x18000dc11  lea     ecx, [r8+7]; dwFlags
0x18000dc15  call    cs:__imp_CoWaitForMultipleHandles
0x18000dc1b  mov     [rbp+arg_8], eax
0x18000dc1e  test    eax, eax
0x18000dc20  js      short loc_18000DC31
0x18000dc22  cmp     dword ptr [rbp+dwindex], r14d
0x18000dc26  jz      short loc_18000DC31
0x18000dc28  mov     [rbp+arg_8], 800704C7h
0x18000dc2f  mov     bl, 1
0x18000dc31  mov     [rbp+arg_0], r14
0x18000dc35  test    bl, bl
0x18000dc37  jz      short loc_18000DC71
0x18000dc39  mov     rax, [rdi]
0x18000dc3c  mov     rbx, [rax]
0x18000dc3f  lea     rcx, [rbp+arg_0]
0x18000dc43  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000dc48  mov     r8, rax
0x18000dc4b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000dc52  mov     rcx, rdi
0x18000dc55  mov     rax, rbx
0x18000dc58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc5d  test    eax, eax
0x18000dc5f  js      short loc_18000DC71
0x18000dc61  mov     rcx, [rbp+arg_0]
0x18000dc65  mov     rax, [rcx]
0x18000dc68  mov     rax, [rax+48h]
0x18000dc6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc71  cmp     [rbp+arg_8], r14d
0x18000dc75  jl      short loc_18000DCC4
0x18000dc77  mov     rax, [rbp+arg_18]
0x18000dc7b  cmp     dword ptr [rax+30h], 1
0x18000dc7f  jz      short loc_18000DCC4
0x18000dc81  cmp     [rbp+arg_0], r14
0x18000dc85  jnz     short loc_18000DCAF
0x18000dc87  mov     rax, [rdi]
0x18000dc8a  mov     rbx, [rax]
0x18000dc8d  lea     rcx, [rbp+arg_0]
0x18000dc91  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000dc96  mov     r8, rax
0x18000dc99  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000dca0  mov     rcx, rdi
0x18000dca3  mov     rax, rbx
0x18000dca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcab  test    eax, eax
0x18000dcad  js      short loc_18000DCC4
0x18000dcaf  mov     rcx, [rbp+arg_0]
0x18000dcb3  mov     rax, [rcx]
0x18000dcb6  lea     rdx, [rbp+arg_8]
0x18000dcba  mov     rax, [rax+40h]
0x18000dcbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcc3  nop
0x18000dcc4  mov     rcx, [rbp+arg_0]
0x18000dcc8  test    rcx, rcx
0x18000dccb  jz      short loc_18000DCDE
0x18000dccd  mov     [rbp+arg_0], r14
0x18000dcd1  mov     rax, [rcx]
0x18000dcd4  mov     rax, [rax+10h]
0x18000dcd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcdd  nop
0x18000dcde  mov     ebx, [rbp+arg_8]
0x18000dce1  mov     rcx, [rbp+arg_18]
0x18000dce5  test    rcx, rcx
0x18000dce8  jz      short loc_18000DCFB
0x18000dcea  mov     [rbp+arg_18], r14
0x18000dcee  mov     rax, [rcx]
0x18000dcf1  mov     rax, [rax+10h]
0x18000dcf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcfa  nop
0x18000dcfb  test    rdi, rdi
0x18000dcfe  jz      short loc_18000DD10
0x18000dd00  mov     rcx, [rdi]
0x18000dd03  mov     rax, [rcx+10h]
0x18000dd07  mov     rcx, rdi
0x18000dd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd0f  nop
0x18000dd10  mov     eax, ebx
0x18000dd12  add     rsp, 50h
0x18000dd16  pop     r14
0x18000dd18  pop     rdi
0x18000dd19  pop     rsi
0x18000dd1a  pop     rbx
0x18000dd1b  pop     rbp
0x18000dd1c  retn
```
