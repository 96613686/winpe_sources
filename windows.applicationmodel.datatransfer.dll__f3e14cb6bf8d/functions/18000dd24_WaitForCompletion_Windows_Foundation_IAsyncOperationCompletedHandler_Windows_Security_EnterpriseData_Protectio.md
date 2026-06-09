# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>(Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18000dd24`
- end: `0x18000dfb1`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ff50`

## callees

- `0x180005504`
- `0x180008b68`
- `0x18000dd24`
- `0x1800143c4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000ddf2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000ddf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de01`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000dea9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000dea9`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Windows::Foundation::IAsyncOperation<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Windows::Foundation::IAsyncOperation<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x18000dd24  mov     [rsp-28h+dwindex], r8
0x18000dd29  mov     [rsp-28h+arg_8], edx
0x18000dd2d  push    rbp
0x18000dd2e  push    rbx
0x18000dd2f  push    rsi
0x18000dd30  push    rdi
0x18000dd31  push    r14
0x18000dd33  mov     rbp, rsp
0x18000dd36  sub     rsp, 50h
0x18000dd3a  mov     rdi, rcx
0x18000dd3d  mov     [rbp+var_20], rcx
0x18000dd41  xor     r14d, r14d
0x18000dd44  test    rcx, rcx
0x18000dd47  jz      short loc_18000DD56
0x18000dd49  mov     rax, [rcx]
0x18000dd4c  mov     rax, [rax+8]
0x18000dd50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd55  nop
0x18000dd56  mov     [rbp+arg_18], r14
0x18000dd5a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dd61  mov     ecx, 40h ; '@'; unsigned __int64
0x18000dd66  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dd6b  mov     rbx, rax
0x18000dd6e  test    rax, rax
0x18000dd71  jnz     short loc_18000DD7F
0x18000dd73  mov     [rbp+arg_8], 8007000Eh
0x18000dd7a  jmp     loc_18000DF72
0x18000dd7f  lea     rax, ??_7?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::`vftable'
0x18000dd86  mov     [rbx], rax
0x18000dd89  lea     rsi, [rbx+8]
0x18000dd8d  mov     rcx, rsi; this
0x18000dd90  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000dd95  mov     dword ptr [rbx+2Ch], 1
0x18000dd9c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>'}
0x18000dda3  mov     [rbx], rax
0x18000dda6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ddad  mov     [rsi], rax
0x18000ddb0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ddb7  test    rcx, rcx
0x18000ddba  jz      short loc_18000DDC9
0x18000ddbc  mov     rax, [rcx]
0x18000ddbf  mov     rax, [rax+8]
0x18000ddc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddc8  nop
0x18000ddc9  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>(Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>'}
0x18000ddd0  mov     [rbx], rax
0x18000ddd3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ddda  mov     [rsi], rax
0x18000dddd  mov     [rbx+30h], r14d
0x18000dde1  mov     [rbx+38h], r14
0x18000dde5  mov     r9d, 1F0003h; dwDesiredAccess
0x18000ddeb  xor     r8d, r8d; dwFlags
0x18000ddee  xor     edx, edx; lpName
0x18000ddf0  xor     ecx, ecx; lpEventAttributes
0x18000ddf2  call    cs:__imp_CreateEventExW
0x18000ddf8  mov     [rbx+38h], rax
0x18000ddfc  test    rax, rax
0x18000ddff  jnz     short loc_18000DE32
0x18000de01  call    cs:__imp_GetLastError
0x18000de07  mov     esi, eax
0x18000de09  test    eax, eax
0x18000de0b  jle     short loc_18000DE16
0x18000de0d  movzx   esi, ax
0x18000de10  or      esi, 80070000h
0x18000de16  mov     rax, [rbx]
0x18000de19  test    esi, esi
0x18000de1b  jns     short loc_18000DE35
0x18000de1d  mov     rcx, rbx
0x18000de20  mov     rax, [rax+10h]
0x18000de24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de29  nop
0x18000de2a  mov     [rbp+arg_8], esi
0x18000de2d  jmp     loc_18000DF72
0x18000de32  mov     rax, [rbx]
0x18000de35  mov     rcx, rbx
0x18000de38  mov     rax, [rax+8]
0x18000de3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de41  nop
0x18000de42  mov     [rbp+arg_18], rbx
0x18000de46  mov     rax, [rbx]
0x18000de49  mov     rcx, rbx
0x18000de4c  mov     rax, [rax+10h]
0x18000de50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de55  nop
0x18000de56  mov     [rbp+arg_8], r14d
0x18000de5a  mov     rax, [rdi]
0x18000de5d  mov     rdx, [rbp+arg_18]
0x18000de61  mov     rcx, rdi
0x18000de64  mov     rax, [rax+30h]
0x18000de68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de6d  mov     [rbp+arg_8], eax
0x18000de70  test    eax, eax
0x18000de72  js      loc_18000DF72
0x18000de78  mov     rax, [rbp+arg_18]
0x18000de7c  mov     rcx, [rax+38h]
0x18000de80  mov     [rbp+pHandles], rcx
0x18000de84  mov     [rbp+var_10], r14
0x18000de88  mov     bl, r14b
0x18000de8b  mov     dword ptr [rbp+dwindex], r14d
0x18000de8f  lea     rax, [rbp+dwindex]
0x18000de93  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18000de98  lea     r9, [rbp+pHandles]; pHandles
0x18000de9c  mov     r8d, 1; cHandles
0x18000dea2  or      edx, 0FFFFFFFFh; dwTimeout
0x18000dea5  lea     ecx, [r8+7]; dwFlags
0x18000dea9  call    cs:__imp_CoWaitForMultipleHandles
0x18000deaf  mov     [rbp+arg_8], eax
0x18000deb2  test    eax, eax
0x18000deb4  js      short loc_18000DEC5
0x18000deb6  cmp     dword ptr [rbp+dwindex], r14d
0x18000deba  jz      short loc_18000DEC5
0x18000debc  mov     [rbp+arg_8], 800704C7h
0x18000dec3  mov     bl, 1
0x18000dec5  mov     [rbp+arg_0], r14
0x18000dec9  test    bl, bl
0x18000decb  jz      short loc_18000DF05
0x18000decd  mov     rax, [rdi]
0x18000ded0  mov     rbx, [rax]
0x18000ded3  lea     rcx, [rbp+arg_0]
0x18000ded7  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000dedc  mov     r8, rax
0x18000dedf  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000dee6  mov     rcx, rdi
0x18000dee9  mov     rax, rbx
0x18000deec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000def1  test    eax, eax
0x18000def3  js      short loc_18000DF05
0x18000def5  mov     rcx, [rbp+arg_0]
0x18000def9  mov     rax, [rcx]
0x18000defc  mov     rax, [rax+48h]
0x18000df00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df05  cmp     [rbp+arg_8], r14d
0x18000df09  jl      short loc_18000DF58
0x18000df0b  mov     rax, [rbp+arg_18]
0x18000df0f  cmp     dword ptr [rax+30h], 1
0x18000df13  jz      short loc_18000DF58
0x18000df15  cmp     [rbp+arg_0], r14
0x18000df19  jnz     short loc_18000DF43
0x18000df1b  mov     rax, [rdi]
0x18000df1e  mov     rbx, [rax]
0x18000df21  lea     rcx, [rbp+arg_0]
0x18000df25  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000df2a  mov     r8, rax
0x18000df2d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000df34  mov     rcx, rdi
0x18000df37  mov     rax, rbx
0x18000df3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df3f  test    eax, eax
0x18000df41  js      short loc_18000DF58
0x18000df43  mov     rcx, [rbp+arg_0]
0x18000df47  mov     rax, [rcx]
0x18000df4a  lea     rdx, [rbp+arg_8]
0x18000df4e  mov     rax, [rax+40h]
0x18000df52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df57  nop
0x18000df58  mov     rcx, [rbp+arg_0]
0x18000df5c  test    rcx, rcx
0x18000df5f  jz      short loc_18000DF72
0x18000df61  mov     [rbp+arg_0], r14
0x18000df65  mov     rax, [rcx]
0x18000df68  mov     rax, [rax+10h]
0x18000df6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df71  nop
0x18000df72  mov     ebx, [rbp+arg_8]
0x18000df75  mov     rcx, [rbp+arg_18]
0x18000df79  test    rcx, rcx
0x18000df7c  jz      short loc_18000DF8F
0x18000df7e  mov     [rbp+arg_18], r14
0x18000df82  mov     rax, [rcx]
0x18000df85  mov     rax, [rax+10h]
0x18000df89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df8e  nop
0x18000df8f  test    rdi, rdi
0x18000df92  jz      short loc_18000DFA4
0x18000df94  mov     rcx, [rdi]
0x18000df97  mov     rax, [rcx+10h]
0x18000df9b  mov     rcx, rdi
0x18000df9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfa3  nop
0x18000dfa4  mov     eax, ebx
0x18000dfa6  add     rsp, 50h
0x18000dfaa  pop     r14
0x18000dfac  pop     rdi
0x18000dfad  pop     rsi
0x18000dfae  pop     rbx
0x18000dfaf  pop     rbp
0x18000dfb0  retn
```
