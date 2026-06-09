# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x14007a2e0`
- end: `0x14007a56d`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14007c310`
- `0x14007de14`

## callees

- `0x140007914`
- `0x14002f920`
- `0x1400461d8`
- `0x14007a2e0`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x14007a3ae`
- `KERNEL32!CreateEventExW` at `0x14007a3ae`
- `KERNEL32!GetLastError` at `0x14007a3bd`
- `KERNEL32!GetLastError` at `0x14007a3bd`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14007a465`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14007a465`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
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
0x14007a2e0  mov     [rsp-28h+dwindex], r8
0x14007a2e5  mov     [rsp-28h+arg_8], edx
0x14007a2e9  push    rbp
0x14007a2ea  push    rbx
0x14007a2eb  push    rsi
0x14007a2ec  push    rdi
0x14007a2ed  push    r14
0x14007a2ef  mov     rbp, rsp
0x14007a2f2  sub     rsp, 50h
0x14007a2f6  mov     rdi, rcx
0x14007a2f9  mov     [rbp+var_20], rcx
0x14007a2fd  xor     r14d, r14d
0x14007a300  test    rcx, rcx
0x14007a303  jz      short loc_14007A312
0x14007a305  mov     rax, [rcx]
0x14007a308  mov     rax, [rax+8]
0x14007a30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a311  nop
0x14007a312  mov     [rbp+arg_18], r14
0x14007a316  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14007a31d  mov     ecx, 40h ; '@'; unsigned __int64
0x14007a322  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14007a327  mov     rbx, rax
0x14007a32a  test    rax, rax
0x14007a32d  jnz     short loc_14007A33B
0x14007a32f  mov     [rbp+arg_8], 8007000Eh
0x14007a336  jmp     loc_14007A52E
0x14007a33b  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>::`vftable'
0x14007a342  mov     [rbx], rax
0x14007a345  lea     rsi, [rbx+8]
0x14007a349  mov     rcx, rsi; this
0x14007a34c  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x14007a351  mov     dword ptr [rbx+2Ch], 1
0x14007a358  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x14007a35f  mov     [rbx], rax
0x14007a362  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14007a369  mov     [rsi], rax
0x14007a36c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14007a373  test    rcx, rcx
0x14007a376  jz      short loc_14007A385
0x14007a378  mov     rax, [rcx]
0x14007a37b  mov     rax, [rax+8]
0x14007a37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a384  nop
0x14007a385  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x14007a38c  mov     [rbx], rax
0x14007a38f  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14007a396  mov     [rsi], rax
0x14007a399  mov     [rbx+30h], r14d
0x14007a39d  mov     [rbx+38h], r14
0x14007a3a1  mov     r9d, 1F0003h; dwDesiredAccess
0x14007a3a7  xor     r8d, r8d; dwFlags
0x14007a3aa  xor     edx, edx; lpName
0x14007a3ac  xor     ecx, ecx; lpEventAttributes
0x14007a3ae  call    cs:__imp_CreateEventExW
0x14007a3b4  mov     [rbx+38h], rax
0x14007a3b8  test    rax, rax
0x14007a3bb  jnz     short loc_14007A3EE
0x14007a3bd  call    cs:__imp_GetLastError
0x14007a3c3  mov     esi, eax
0x14007a3c5  test    eax, eax
0x14007a3c7  jle     short loc_14007A3D2
0x14007a3c9  movzx   esi, ax
0x14007a3cc  or      esi, 80070000h
0x14007a3d2  mov     rax, [rbx]
0x14007a3d5  test    esi, esi
0x14007a3d7  jns     short loc_14007A3F1
0x14007a3d9  mov     rcx, rbx
0x14007a3dc  mov     rax, [rax+10h]
0x14007a3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a3e5  nop
0x14007a3e6  mov     [rbp+arg_8], esi
0x14007a3e9  jmp     loc_14007A52E
0x14007a3ee  mov     rax, [rbx]
0x14007a3f1  mov     rcx, rbx
0x14007a3f4  mov     rax, [rax+8]
0x14007a3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a3fd  nop
0x14007a3fe  mov     [rbp+arg_18], rbx
0x14007a402  mov     rax, [rbx]
0x14007a405  mov     rcx, rbx
0x14007a408  mov     rax, [rax+10h]
0x14007a40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a411  nop
0x14007a412  mov     [rbp+arg_8], r14d
0x14007a416  mov     rax, [rdi]
0x14007a419  mov     rdx, [rbp+arg_18]
0x14007a41d  mov     rcx, rdi
0x14007a420  mov     rax, [rax+30h]
0x14007a424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a429  mov     [rbp+arg_8], eax
0x14007a42c  test    eax, eax
0x14007a42e  js      loc_14007A52E
0x14007a434  mov     rax, [rbp+arg_18]
0x14007a438  mov     rcx, [rax+38h]
0x14007a43c  mov     [rbp+pHandles], rcx
0x14007a440  mov     [rbp+var_10], r14
0x14007a444  mov     bl, r14b
0x14007a447  mov     dword ptr [rbp+dwindex], r14d
0x14007a44b  lea     rax, [rbp+dwindex]
0x14007a44f  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x14007a454  lea     r9, [rbp+pHandles]; pHandles
0x14007a458  mov     r8d, 1; cHandles
0x14007a45e  or      edx, 0FFFFFFFFh; dwTimeout
0x14007a461  lea     ecx, [r8+7]; dwFlags
0x14007a465  call    cs:__imp_CoWaitForMultipleHandles
0x14007a46b  mov     [rbp+arg_8], eax
0x14007a46e  test    eax, eax
0x14007a470  js      short loc_14007A481
0x14007a472  cmp     dword ptr [rbp+dwindex], r14d
0x14007a476  jz      short loc_14007A481
0x14007a478  mov     [rbp+arg_8], 800704C7h
0x14007a47f  mov     bl, 1
0x14007a481  mov     [rbp+arg_0], r14
0x14007a485  test    bl, bl
0x14007a487  jz      short loc_14007A4C1
0x14007a489  mov     rax, [rdi]
0x14007a48c  mov     rbx, [rax]
0x14007a48f  lea     rcx, [rbp+arg_0]
0x14007a493  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x14007a498  mov     r8, rax
0x14007a49b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14007a4a2  mov     rcx, rdi
0x14007a4a5  mov     rax, rbx
0x14007a4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a4ad  test    eax, eax
0x14007a4af  js      short loc_14007A4C1
0x14007a4b1  mov     rcx, [rbp+arg_0]
0x14007a4b5  mov     rax, [rcx]
0x14007a4b8  mov     rax, [rax+48h]
0x14007a4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a4c1  cmp     [rbp+arg_8], r14d
0x14007a4c5  jl      short loc_14007A514
0x14007a4c7  mov     rax, [rbp+arg_18]
0x14007a4cb  cmp     dword ptr [rax+30h], 1
0x14007a4cf  jz      short loc_14007A514
0x14007a4d1  cmp     [rbp+arg_0], r14
0x14007a4d5  jnz     short loc_14007A4FF
0x14007a4d7  mov     rax, [rdi]
0x14007a4da  mov     rbx, [rax]
0x14007a4dd  lea     rcx, [rbp+arg_0]
0x14007a4e1  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x14007a4e6  mov     r8, rax
0x14007a4e9  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14007a4f0  mov     rcx, rdi
0x14007a4f3  mov     rax, rbx
0x14007a4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a4fb  test    eax, eax
0x14007a4fd  js      short loc_14007A514
0x14007a4ff  mov     rcx, [rbp+arg_0]
0x14007a503  mov     rax, [rcx]
0x14007a506  lea     rdx, [rbp+arg_8]
0x14007a50a  mov     rax, [rax+40h]
0x14007a50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a513  nop
0x14007a514  mov     rcx, [rbp+arg_0]
0x14007a518  test    rcx, rcx
0x14007a51b  jz      short loc_14007A52E
0x14007a51d  mov     [rbp+arg_0], r14
0x14007a521  mov     rax, [rcx]
0x14007a524  mov     rax, [rax+10h]
0x14007a528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a52d  nop
0x14007a52e  mov     ebx, [rbp+arg_8]
0x14007a531  mov     rcx, [rbp+arg_18]
0x14007a535  test    rcx, rcx
0x14007a538  jz      short loc_14007A54B
0x14007a53a  mov     [rbp+arg_18], r14
0x14007a53e  mov     rax, [rcx]
0x14007a541  mov     rax, [rax+10h]
0x14007a545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a54a  nop
0x14007a54b  test    rdi, rdi
0x14007a54e  jz      short loc_14007A560
0x14007a550  mov     rcx, [rdi]
0x14007a553  mov     rax, [rcx+10h]
0x14007a557  mov     rcx, rdi
0x14007a55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a55f  nop
0x14007a560  mov     eax, ebx
0x14007a562  add     rsp, 50h
0x14007a566  pop     r14
0x14007a568  pop     rdi
0x14007a569  pop     rsi
0x14007a56a  pop     rbx
0x14007a56b  pop     rbp
0x14007a56c  retn
```
