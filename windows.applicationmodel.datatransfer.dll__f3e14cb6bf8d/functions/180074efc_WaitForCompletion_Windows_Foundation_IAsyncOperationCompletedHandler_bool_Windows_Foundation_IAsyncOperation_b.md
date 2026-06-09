# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180074efc`
- end: `0x180075189`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078cb0`

## callees

- `0x180005504`
- `0x180008b68`
- `0x1800143c4`
- `0x180074efc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180074fca`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180074fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074fd9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180075081`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180075081`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'};
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::`vftable';
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
0x180074efc  mov     [rsp-28h+dwindex], r8
0x180074f01  mov     [rsp-28h+arg_8], edx
0x180074f05  push    rbp
0x180074f06  push    rbx
0x180074f07  push    rsi
0x180074f08  push    rdi
0x180074f09  push    r14
0x180074f0b  mov     rbp, rsp
0x180074f0e  sub     rsp, 50h
0x180074f12  mov     rdi, rcx
0x180074f15  mov     [rbp+var_20], rcx
0x180074f19  xor     r14d, r14d
0x180074f1c  test    rcx, rcx
0x180074f1f  jz      short loc_180074F2E
0x180074f21  mov     rax, [rcx]
0x180074f24  mov     rax, [rax+8]
0x180074f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074f2d  nop
0x180074f2e  mov     [rbp+arg_18], r14
0x180074f32  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180074f39  mov     ecx, 40h ; '@'; unsigned __int64
0x180074f3e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180074f43  mov     rbx, rax
0x180074f46  test    rax, rax
0x180074f49  jnz     short loc_180074F57
0x180074f4b  mov     [rbp+arg_8], 8007000Eh
0x180074f52  jmp     loc_18007514A
0x180074f57  lea     rax, ??_7?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::`vftable'
0x180074f5e  mov     [rbx], rax
0x180074f61  lea     rsi, [rbx+8]
0x180074f65  mov     rcx, rsi; this
0x180074f68  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180074f6d  mov     dword ptr [rbx+2Ch], 1
0x180074f74  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x180074f7b  mov     [rbx], rax
0x180074f7e  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180074f85  mov     [rsi], rax
0x180074f88  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180074f8f  test    rcx, rcx
0x180074f92  jz      short loc_180074FA1
0x180074f94  mov     rax, [rcx]
0x180074f97  mov     rax, [rax+8]
0x180074f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074fa0  nop
0x180074fa1  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@_N@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x180074fa8  mov     [rbx], rax
0x180074fab  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180074fb2  mov     [rsi], rax
0x180074fb5  mov     [rbx+30h], r14d
0x180074fb9  mov     [rbx+38h], r14
0x180074fbd  mov     r9d, 1F0003h; dwDesiredAccess
0x180074fc3  xor     r8d, r8d; dwFlags
0x180074fc6  xor     edx, edx; lpName
0x180074fc8  xor     ecx, ecx; lpEventAttributes
0x180074fca  call    cs:__imp_CreateEventExW
0x180074fd0  mov     [rbx+38h], rax
0x180074fd4  test    rax, rax
0x180074fd7  jnz     short loc_18007500A
0x180074fd9  call    cs:__imp_GetLastError
0x180074fdf  mov     esi, eax
0x180074fe1  test    eax, eax
0x180074fe3  jle     short loc_180074FEE
0x180074fe5  movzx   esi, ax
0x180074fe8  or      esi, 80070000h
0x180074fee  mov     rax, [rbx]
0x180074ff1  test    esi, esi
0x180074ff3  jns     short loc_18007500D
0x180074ff5  mov     rcx, rbx
0x180074ff8  mov     rax, [rax+10h]
0x180074ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075001  nop
0x180075002  mov     [rbp+arg_8], esi
0x180075005  jmp     loc_18007514A
0x18007500a  mov     rax, [rbx]
0x18007500d  mov     rcx, rbx
0x180075010  mov     rax, [rax+8]
0x180075014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075019  nop
0x18007501a  mov     [rbp+arg_18], rbx
0x18007501e  mov     rax, [rbx]
0x180075021  mov     rcx, rbx
0x180075024  mov     rax, [rax+10h]
0x180075028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007502d  nop
0x18007502e  mov     [rbp+arg_8], r14d
0x180075032  mov     rax, [rdi]
0x180075035  mov     rdx, [rbp+arg_18]
0x180075039  mov     rcx, rdi
0x18007503c  mov     rax, [rax+30h]
0x180075040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075045  mov     [rbp+arg_8], eax
0x180075048  test    eax, eax
0x18007504a  js      loc_18007514A
0x180075050  mov     rax, [rbp+arg_18]
0x180075054  mov     rcx, [rax+38h]
0x180075058  mov     [rbp+pHandles], rcx
0x18007505c  mov     [rbp+var_10], r14
0x180075060  mov     bl, r14b
0x180075063  mov     dword ptr [rbp+dwindex], r14d
0x180075067  lea     rax, [rbp+dwindex]
0x18007506b  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180075070  lea     r9, [rbp+pHandles]; pHandles
0x180075074  mov     r8d, 1; cHandles
0x18007507a  or      edx, 0FFFFFFFFh; dwTimeout
0x18007507d  lea     ecx, [r8+7]; dwFlags
0x180075081  call    cs:__imp_CoWaitForMultipleHandles
0x180075087  mov     [rbp+arg_8], eax
0x18007508a  test    eax, eax
0x18007508c  js      short loc_18007509D
0x18007508e  cmp     dword ptr [rbp+dwindex], r14d
0x180075092  jz      short loc_18007509D
0x180075094  mov     [rbp+arg_8], 800704C7h
0x18007509b  mov     bl, 1
0x18007509d  mov     [rbp+arg_0], r14
0x1800750a1  test    bl, bl
0x1800750a3  jz      short loc_1800750DD
0x1800750a5  mov     rax, [rdi]
0x1800750a8  mov     rbx, [rax]
0x1800750ab  lea     rcx, [rbp+arg_0]
0x1800750af  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x1800750b4  mov     r8, rax
0x1800750b7  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800750be  mov     rcx, rdi
0x1800750c1  mov     rax, rbx
0x1800750c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800750c9  test    eax, eax
0x1800750cb  js      short loc_1800750DD
0x1800750cd  mov     rcx, [rbp+arg_0]
0x1800750d1  mov     rax, [rcx]
0x1800750d4  mov     rax, [rax+48h]
0x1800750d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800750dd  cmp     [rbp+arg_8], r14d
0x1800750e1  jl      short loc_180075130
0x1800750e3  mov     rax, [rbp+arg_18]
0x1800750e7  cmp     dword ptr [rax+30h], 1
0x1800750eb  jz      short loc_180075130
0x1800750ed  cmp     [rbp+arg_0], r14
0x1800750f1  jnz     short loc_18007511B
0x1800750f3  mov     rax, [rdi]
0x1800750f6  mov     rbx, [rax]
0x1800750f9  lea     rcx, [rbp+arg_0]
0x1800750fd  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180075102  mov     r8, rax
0x180075105  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18007510c  mov     rcx, rdi
0x18007510f  mov     rax, rbx
0x180075112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075117  test    eax, eax
0x180075119  js      short loc_180075130
0x18007511b  mov     rcx, [rbp+arg_0]
0x18007511f  mov     rax, [rcx]
0x180075122  lea     rdx, [rbp+arg_8]
0x180075126  mov     rax, [rax+40h]
0x18007512a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007512f  nop
0x180075130  mov     rcx, [rbp+arg_0]
0x180075134  test    rcx, rcx
0x180075137  jz      short loc_18007514A
0x180075139  mov     [rbp+arg_0], r14
0x18007513d  mov     rax, [rcx]
0x180075140  mov     rax, [rax+10h]
0x180075144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075149  nop
0x18007514a  mov     ebx, [rbp+arg_8]
0x18007514d  mov     rcx, [rbp+arg_18]
0x180075151  test    rcx, rcx
0x180075154  jz      short loc_180075167
0x180075156  mov     [rbp+arg_18], r14
0x18007515a  mov     rax, [rcx]
0x18007515d  mov     rax, [rax+10h]
0x180075161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075166  nop
0x180075167  test    rdi, rdi
0x18007516a  jz      short loc_18007517C
0x18007516c  mov     rcx, [rdi]
0x18007516f  mov     rax, [rcx+10h]
0x180075173  mov     rcx, rdi
0x180075176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007517b  nop
0x18007517c  mov     eax, ebx
0x18007517e  add     rsp, 50h
0x180075182  pop     r14
0x180075184  pop     rdi
0x180075185  pop     rsi
0x180075186  pop     rbx
0x180075187  pop     rbp
0x180075188  retn
```
