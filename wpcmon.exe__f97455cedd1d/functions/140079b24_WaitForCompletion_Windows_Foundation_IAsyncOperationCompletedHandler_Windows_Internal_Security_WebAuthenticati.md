# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x140079b24`
- end: `0x140079db1`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14007bb94`

## callees

- `0x140007914`
- `0x14002f920`
- `0x1400461d8`
- `0x140079b24`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x140079bf2`
- `KERNEL32!CreateEventExW` at `0x140079bf2`
- `KERNEL32!GetLastError` at `0x140079c01`
- `KERNEL32!GetLastError` at `0x140079c01`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140079ca9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140079ca9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  _DWORD *v4; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // esi
  __int64 v8; // rax
  char v9; // bl
  int (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v11; // rax
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v13; // rax
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
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v22 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>'::`2'::FTMEventDelegate::`vftable';
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
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HANDLE *))(*a1)[6])(a1, v22);
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
      v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19);
      if ( v10(a1, &GUID_00000036_0000_0000_c000_000000000046, v11) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 72LL))(v19);
    }
    if ( v20 >= 0 && *((_DWORD *)v22 + 12) != 1 )
    {
      if ( v19
        || (v12 = **a1,
            v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19),
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
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v15;
}

```

## disassembly

```asm
0x140079b24  mov     [rsp-28h+dwindex], r8
0x140079b29  mov     [rsp-28h+arg_8], edx
0x140079b2d  push    rbp
0x140079b2e  push    rbx
0x140079b2f  push    rsi
0x140079b30  push    rdi
0x140079b31  push    r14
0x140079b33  mov     rbp, rsp
0x140079b36  sub     rsp, 50h
0x140079b3a  mov     rdi, rcx
0x140079b3d  mov     [rbp+var_20], rcx
0x140079b41  xor     r14d, r14d
0x140079b44  test    rcx, rcx
0x140079b47  jz      short loc_140079B56
0x140079b49  mov     rax, [rcx]
0x140079b4c  mov     rax, [rax+8]
0x140079b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079b55  nop
0x140079b56  mov     [rbp+arg_18], r14
0x140079b5a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140079b61  mov     ecx, 40h ; '@'; unsigned __int64
0x140079b66  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140079b6b  mov     rbx, rax
0x140079b6e  test    rax, rax
0x140079b71  jnz     short loc_140079B7F
0x140079b73  mov     [rbp+arg_8], 8007000Eh
0x140079b7a  jmp     loc_140079D72
0x140079b7f  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable'
0x140079b86  mov     [rbx], rax
0x140079b89  lea     rsi, [rbx+8]
0x140079b8d  mov     rcx, rsi; this
0x140079b90  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x140079b95  mov     dword ptr [rbx+2Ch], 1
0x140079b9c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'}
0x140079ba3  mov     [rbx], rax
0x140079ba6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140079bad  mov     [rsi], rax
0x140079bb0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140079bb7  test    rcx, rcx
0x140079bba  jz      short loc_140079BC9
0x140079bbc  mov     rax, [rcx]
0x140079bbf  mov     rax, [rax+8]
0x140079bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079bc8  nop
0x140079bc9  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'}
0x140079bd0  mov     [rbx], rax
0x140079bd3  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140079bda  mov     [rsi], rax
0x140079bdd  mov     [rbx+30h], r14d
0x140079be1  mov     [rbx+38h], r14
0x140079be5  mov     r9d, 1F0003h; dwDesiredAccess
0x140079beb  xor     r8d, r8d; dwFlags
0x140079bee  xor     edx, edx; lpName
0x140079bf0  xor     ecx, ecx; lpEventAttributes
0x140079bf2  call    cs:__imp_CreateEventExW
0x140079bf8  mov     [rbx+38h], rax
0x140079bfc  test    rax, rax
0x140079bff  jnz     short loc_140079C32
0x140079c01  call    cs:__imp_GetLastError
0x140079c07  mov     esi, eax
0x140079c09  test    eax, eax
0x140079c0b  jle     short loc_140079C16
0x140079c0d  movzx   esi, ax
0x140079c10  or      esi, 80070000h
0x140079c16  mov     rax, [rbx]
0x140079c19  test    esi, esi
0x140079c1b  jns     short loc_140079C35
0x140079c1d  mov     rcx, rbx
0x140079c20  mov     rax, [rax+10h]
0x140079c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079c29  nop
0x140079c2a  mov     [rbp+arg_8], esi
0x140079c2d  jmp     loc_140079D72
0x140079c32  mov     rax, [rbx]
0x140079c35  mov     rcx, rbx
0x140079c38  mov     rax, [rax+8]
0x140079c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079c41  nop
0x140079c42  mov     [rbp+arg_18], rbx
0x140079c46  mov     rax, [rbx]
0x140079c49  mov     rcx, rbx
0x140079c4c  mov     rax, [rax+10h]
0x140079c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079c55  nop
0x140079c56  mov     [rbp+arg_8], r14d
0x140079c5a  mov     rax, [rdi]
0x140079c5d  mov     rdx, [rbp+arg_18]
0x140079c61  mov     rcx, rdi
0x140079c64  mov     rax, [rax+30h]
0x140079c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079c6d  mov     [rbp+arg_8], eax
0x140079c70  test    eax, eax
0x140079c72  js      loc_140079D72
0x140079c78  mov     rax, [rbp+arg_18]
0x140079c7c  mov     rcx, [rax+38h]
0x140079c80  mov     [rbp+pHandles], rcx
0x140079c84  mov     [rbp+var_10], r14
0x140079c88  mov     bl, r14b
0x140079c8b  mov     dword ptr [rbp+dwindex], r14d
0x140079c8f  lea     rax, [rbp+dwindex]
0x140079c93  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x140079c98  lea     r9, [rbp+pHandles]; pHandles
0x140079c9c  mov     r8d, 1; cHandles
0x140079ca2  or      edx, 0FFFFFFFFh; dwTimeout
0x140079ca5  lea     ecx, [r8+7]; dwFlags
0x140079ca9  call    cs:__imp_CoWaitForMultipleHandles
0x140079caf  mov     [rbp+arg_8], eax
0x140079cb2  test    eax, eax
0x140079cb4  js      short loc_140079CC5
0x140079cb6  cmp     dword ptr [rbp+dwindex], r14d
0x140079cba  jz      short loc_140079CC5
0x140079cbc  mov     [rbp+arg_8], 800704C7h
0x140079cc3  mov     bl, 1
0x140079cc5  mov     [rbp+arg_0], r14
0x140079cc9  test    bl, bl
0x140079ccb  jz      short loc_140079D05
0x140079ccd  mov     rax, [rdi]
0x140079cd0  mov     rbx, [rax]
0x140079cd3  lea     rcx, [rbp+arg_0]
0x140079cd7  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x140079cdc  mov     r8, rax
0x140079cdf  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140079ce6  mov     rcx, rdi
0x140079ce9  mov     rax, rbx
0x140079cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079cf1  test    eax, eax
0x140079cf3  js      short loc_140079D05
0x140079cf5  mov     rcx, [rbp+arg_0]
0x140079cf9  mov     rax, [rcx]
0x140079cfc  mov     rax, [rax+48h]
0x140079d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079d05  cmp     [rbp+arg_8], r14d
0x140079d09  jl      short loc_140079D58
0x140079d0b  mov     rax, [rbp+arg_18]
0x140079d0f  cmp     dword ptr [rax+30h], 1
0x140079d13  jz      short loc_140079D58
0x140079d15  cmp     [rbp+arg_0], r14
0x140079d19  jnz     short loc_140079D43
0x140079d1b  mov     rax, [rdi]
0x140079d1e  mov     rbx, [rax]
0x140079d21  lea     rcx, [rbp+arg_0]
0x140079d25  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x140079d2a  mov     r8, rax
0x140079d2d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140079d34  mov     rcx, rdi
0x140079d37  mov     rax, rbx
0x140079d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079d3f  test    eax, eax
0x140079d41  js      short loc_140079D58
0x140079d43  mov     rcx, [rbp+arg_0]
0x140079d47  mov     rax, [rcx]
0x140079d4a  lea     rdx, [rbp+arg_8]
0x140079d4e  mov     rax, [rax+40h]
0x140079d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079d57  nop
0x140079d58  mov     rcx, [rbp+arg_0]
0x140079d5c  test    rcx, rcx
0x140079d5f  jz      short loc_140079D72
0x140079d61  mov     [rbp+arg_0], r14
0x140079d65  mov     rax, [rcx]
0x140079d68  mov     rax, [rax+10h]
0x140079d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079d71  nop
0x140079d72  mov     ebx, [rbp+arg_8]
0x140079d75  mov     rcx, [rbp+arg_18]
0x140079d79  test    rcx, rcx
0x140079d7c  jz      short loc_140079D8F
0x140079d7e  mov     [rbp+arg_18], r14
0x140079d82  mov     rax, [rcx]
0x140079d85  mov     rax, [rax+10h]
0x140079d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079d8e  nop
0x140079d8f  test    rdi, rdi
0x140079d92  jz      short loc_140079DA4
0x140079d94  mov     rcx, [rdi]
0x140079d97  mov     rax, [rcx+10h]
0x140079d9b  mov     rcx, rdi
0x140079d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079da3  nop
0x140079da4  mov     eax, ebx
0x140079da6  add     rsp, 50h
0x140079daa  pop     r14
0x140079dac  pop     rdi
0x140079dad  pop     rsi
0x140079dae  pop     rbx
0x140079daf  pop     rbp
0x140079db0  retn
```
