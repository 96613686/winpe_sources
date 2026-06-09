# WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18000dfb8`
- end: `0x18000e245`
- name: `??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@_K_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@_K_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@_K_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022f2c`
- `0x180064ba0`
- `0x180078cb0`

## callees

- `0x180005504`
- `0x180008b68`
- `0x18000dfb8`
- `0x1800143c4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e086`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e095`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e13d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e13d`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>'};
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>'::`2'::FTMEventDelegate::`vftable';
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
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64), HANDLE *))(*a1)[8])(a1, v22);
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
0x18000dfb8  mov     [rsp-28h+dwindex], r8
0x18000dfbd  mov     [rsp-28h+arg_8], edx
0x18000dfc1  push    rbp
0x18000dfc2  push    rbx
0x18000dfc3  push    rsi
0x18000dfc4  push    rdi
0x18000dfc5  push    r14
0x18000dfc7  mov     rbp, rsp
0x18000dfca  sub     rsp, 50h
0x18000dfce  mov     rdi, rcx
0x18000dfd1  mov     [rbp+var_20], rcx
0x18000dfd5  xor     r14d, r14d
0x18000dfd8  test    rcx, rcx
0x18000dfdb  jz      short loc_18000DFEA
0x18000dfdd  mov     rax, [rcx]
0x18000dfe0  mov     rax, [rax+8]
0x18000dfe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfe9  nop
0x18000dfea  mov     [rbp+arg_18], r14
0x18000dfee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dff5  mov     ecx, 40h ; '@'; unsigned __int64
0x18000dffa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dfff  mov     rbx, rax
0x18000e002  test    rax, rax
0x18000e005  jnz     short loc_18000E013
0x18000e007  mov     [rbp+arg_8], 8007000Eh
0x18000e00e  jmp     loc_18000E206
0x18000e013  lea     rax, ??_7?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::`vftable'
0x18000e01a  mov     [rbx], rax
0x18000e01d  lea     rsi, [rbx+8]
0x18000e021  mov     rcx, rsi; this
0x18000e024  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000e029  mov     dword ptr [rbx+2Ch], 1
0x18000e030  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@_K_K@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@_K_K@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>'}
0x18000e037  mov     [rbx], rax
0x18000e03a  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@_K_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@_K_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@_K_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e041  mov     [rsi], rax
0x18000e044  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e04b  test    rcx, rcx
0x18000e04e  jz      short loc_18000E05D
0x18000e050  mov     rax, [rcx]
0x18000e053  mov     rax, [rax+8]
0x18000e057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e05c  nop
0x18000e05d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@_K_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@_K_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@_K_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationWithProgressCompletedHandler@_K_K@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>'}
0x18000e064  mov     [rbx], rax
0x18000e067  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@_K_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@_K_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@_K_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e06e  mov     [rsi], rax
0x18000e071  mov     [rbx+30h], r14d
0x18000e075  mov     [rbx+38h], r14
0x18000e079  mov     r9d, 1F0003h; dwDesiredAccess
0x18000e07f  xor     r8d, r8d; dwFlags
0x18000e082  xor     edx, edx; lpName
0x18000e084  xor     ecx, ecx; lpEventAttributes
0x18000e086  call    cs:__imp_CreateEventExW
0x18000e08c  mov     [rbx+38h], rax
0x18000e090  test    rax, rax
0x18000e093  jnz     short loc_18000E0C6
0x18000e095  call    cs:__imp_GetLastError
0x18000e09b  mov     esi, eax
0x18000e09d  test    eax, eax
0x18000e09f  jle     short loc_18000E0AA
0x18000e0a1  movzx   esi, ax
0x18000e0a4  or      esi, 80070000h
0x18000e0aa  mov     rax, [rbx]
0x18000e0ad  test    esi, esi
0x18000e0af  jns     short loc_18000E0C9
0x18000e0b1  mov     rcx, rbx
0x18000e0b4  mov     rax, [rax+10h]
0x18000e0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0bd  nop
0x18000e0be  mov     [rbp+arg_8], esi
0x18000e0c1  jmp     loc_18000E206
0x18000e0c6  mov     rax, [rbx]
0x18000e0c9  mov     rcx, rbx
0x18000e0cc  mov     rax, [rax+8]
0x18000e0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d5  nop
0x18000e0d6  mov     [rbp+arg_18], rbx
0x18000e0da  mov     rax, [rbx]
0x18000e0dd  mov     rcx, rbx
0x18000e0e0  mov     rax, [rax+10h]
0x18000e0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0e9  nop
0x18000e0ea  mov     [rbp+arg_8], r14d
0x18000e0ee  mov     rax, [rdi]
0x18000e0f1  mov     rdx, [rbp+arg_18]
0x18000e0f5  mov     rcx, rdi
0x18000e0f8  mov     rax, [rax+40h]
0x18000e0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e101  mov     [rbp+arg_8], eax
0x18000e104  test    eax, eax
0x18000e106  js      loc_18000E206
0x18000e10c  mov     rax, [rbp+arg_18]
0x18000e110  mov     rcx, [rax+38h]
0x18000e114  mov     [rbp+pHandles], rcx
0x18000e118  mov     [rbp+var_10], r14
0x18000e11c  mov     bl, r14b
0x18000e11f  mov     dword ptr [rbp+dwindex], r14d
0x18000e123  lea     rax, [rbp+dwindex]
0x18000e127  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18000e12c  lea     r9, [rbp+pHandles]; pHandles
0x18000e130  mov     r8d, 1; cHandles
0x18000e136  or      edx, 0FFFFFFFFh; dwTimeout
0x18000e139  lea     ecx, [r8+7]; dwFlags
0x18000e13d  call    cs:__imp_CoWaitForMultipleHandles
0x18000e143  mov     [rbp+arg_8], eax
0x18000e146  test    eax, eax
0x18000e148  js      short loc_18000E159
0x18000e14a  cmp     dword ptr [rbp+dwindex], r14d
0x18000e14e  jz      short loc_18000E159
0x18000e150  mov     [rbp+arg_8], 800704C7h
0x18000e157  mov     bl, 1
0x18000e159  mov     [rbp+arg_0], r14
0x18000e15d  test    bl, bl
0x18000e15f  jz      short loc_18000E199
0x18000e161  mov     rax, [rdi]
0x18000e164  mov     rbx, [rax]
0x18000e167  lea     rcx, [rbp+arg_0]
0x18000e16b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000e170  mov     r8, rax
0x18000e173  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e17a  mov     rcx, rdi
0x18000e17d  mov     rax, rbx
0x18000e180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e185  test    eax, eax
0x18000e187  js      short loc_18000E199
0x18000e189  mov     rcx, [rbp+arg_0]
0x18000e18d  mov     rax, [rcx]
0x18000e190  mov     rax, [rax+48h]
0x18000e194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e199  cmp     [rbp+arg_8], r14d
0x18000e19d  jl      short loc_18000E1EC
0x18000e19f  mov     rax, [rbp+arg_18]
0x18000e1a3  cmp     dword ptr [rax+30h], 1
0x18000e1a7  jz      short loc_18000E1EC
0x18000e1a9  cmp     [rbp+arg_0], r14
0x18000e1ad  jnz     short loc_18000E1D7
0x18000e1af  mov     rax, [rdi]
0x18000e1b2  mov     rbx, [rax]
0x18000e1b5  lea     rcx, [rbp+arg_0]
0x18000e1b9  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000e1be  mov     r8, rax
0x18000e1c1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e1c8  mov     rcx, rdi
0x18000e1cb  mov     rax, rbx
0x18000e1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1d3  test    eax, eax
0x18000e1d5  js      short loc_18000E1EC
0x18000e1d7  mov     rcx, [rbp+arg_0]
0x18000e1db  mov     rax, [rcx]
0x18000e1de  lea     rdx, [rbp+arg_8]
0x18000e1e2  mov     rax, [rax+40h]
0x18000e1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1eb  nop
0x18000e1ec  mov     rcx, [rbp+arg_0]
0x18000e1f0  test    rcx, rcx
0x18000e1f3  jz      short loc_18000E206
0x18000e1f5  mov     [rbp+arg_0], r14
0x18000e1f9  mov     rax, [rcx]
0x18000e1fc  mov     rax, [rax+10h]
0x18000e200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e205  nop
0x18000e206  mov     ebx, [rbp+arg_8]
0x18000e209  mov     rcx, [rbp+arg_18]
0x18000e20d  test    rcx, rcx
0x18000e210  jz      short loc_18000E223
0x18000e212  mov     [rbp+arg_18], r14
0x18000e216  mov     rax, [rcx]
0x18000e219  mov     rax, [rax+10h]
0x18000e21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e222  nop
0x18000e223  test    rdi, rdi
0x18000e226  jz      short loc_18000E238
0x18000e228  mov     rcx, [rdi]
0x18000e22b  mov     rax, [rcx+10h]
0x18000e22f  mov     rcx, rdi
0x18000e232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e237  nop
0x18000e238  mov     eax, ebx
0x18000e23a  add     rsp, 50h
0x18000e23e  pop     r14
0x18000e240  pop     rdi
0x18000e241  pop     rsi
0x18000e242  pop     rbx
0x18000e243  pop     rbp
0x18000e244  retn
```
