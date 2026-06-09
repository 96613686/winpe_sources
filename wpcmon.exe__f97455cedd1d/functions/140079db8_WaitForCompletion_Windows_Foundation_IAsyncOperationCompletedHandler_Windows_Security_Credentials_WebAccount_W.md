# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x140079db8`
- end: `0x14007a045`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14007c310`

## callees

- `0x140007914`
- `0x14002f920`
- `0x1400461d8`
- `0x140079db8`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x140079e86`
- `KERNEL32!CreateEventExW` at `0x140079e86`
- `KERNEL32!GetLastError` at `0x140079e95`
- `KERNEL32!GetLastError` at `0x140079e95`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140079f3d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140079f3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>'::`2'::FTMEventDelegate::`vftable';
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
0x140079db8  mov     [rsp-28h+dwindex], r8
0x140079dbd  mov     [rsp-28h+arg_8], edx
0x140079dc1  push    rbp
0x140079dc2  push    rbx
0x140079dc3  push    rsi
0x140079dc4  push    rdi
0x140079dc5  push    r14
0x140079dc7  mov     rbp, rsp
0x140079dca  sub     rsp, 50h
0x140079dce  mov     rdi, rcx
0x140079dd1  mov     [rbp+var_20], rcx
0x140079dd5  xor     r14d, r14d
0x140079dd8  test    rcx, rcx
0x140079ddb  jz      short loc_140079DEA
0x140079ddd  mov     rax, [rcx]
0x140079de0  mov     rax, [rax+8]
0x140079de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079de9  nop
0x140079dea  mov     [rbp+arg_18], r14
0x140079dee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140079df5  mov     ecx, 40h ; '@'; unsigned __int64
0x140079dfa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140079dff  mov     rbx, rax
0x140079e02  test    rax, rax
0x140079e05  jnz     short loc_140079E13
0x140079e07  mov     [rbp+arg_8], 8007000Eh
0x140079e0e  jmp     loc_14007A006
0x140079e13  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>::`vftable'
0x140079e1a  mov     [rbx], rax
0x140079e1d  lea     rsi, [rbx+8]
0x140079e21  mov     rcx, rsi; this
0x140079e24  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x140079e29  mov     dword ptr [rbx+2Ch], 1
0x140079e30  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'}
0x140079e37  mov     [rbx], rax
0x140079e3a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140079e41  mov     [rsi], rax
0x140079e44  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140079e4b  test    rcx, rcx
0x140079e4e  jz      short loc_140079E5D
0x140079e50  mov     rax, [rcx]
0x140079e53  mov     rax, [rax+8]
0x140079e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079e5c  nop
0x140079e5d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'}
0x140079e64  mov     [rbx], rax
0x140079e67  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140079e6e  mov     [rsi], rax
0x140079e71  mov     [rbx+30h], r14d
0x140079e75  mov     [rbx+38h], r14
0x140079e79  mov     r9d, 1F0003h; dwDesiredAccess
0x140079e7f  xor     r8d, r8d; dwFlags
0x140079e82  xor     edx, edx; lpName
0x140079e84  xor     ecx, ecx; lpEventAttributes
0x140079e86  call    cs:__imp_CreateEventExW
0x140079e8c  mov     [rbx+38h], rax
0x140079e90  test    rax, rax
0x140079e93  jnz     short loc_140079EC6
0x140079e95  call    cs:__imp_GetLastError
0x140079e9b  mov     esi, eax
0x140079e9d  test    eax, eax
0x140079e9f  jle     short loc_140079EAA
0x140079ea1  movzx   esi, ax
0x140079ea4  or      esi, 80070000h
0x140079eaa  mov     rax, [rbx]
0x140079ead  test    esi, esi
0x140079eaf  jns     short loc_140079EC9
0x140079eb1  mov     rcx, rbx
0x140079eb4  mov     rax, [rax+10h]
0x140079eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079ebd  nop
0x140079ebe  mov     [rbp+arg_8], esi
0x140079ec1  jmp     loc_14007A006
0x140079ec6  mov     rax, [rbx]
0x140079ec9  mov     rcx, rbx
0x140079ecc  mov     rax, [rax+8]
0x140079ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079ed5  nop
0x140079ed6  mov     [rbp+arg_18], rbx
0x140079eda  mov     rax, [rbx]
0x140079edd  mov     rcx, rbx
0x140079ee0  mov     rax, [rax+10h]
0x140079ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079ee9  nop
0x140079eea  mov     [rbp+arg_8], r14d
0x140079eee  mov     rax, [rdi]
0x140079ef1  mov     rdx, [rbp+arg_18]
0x140079ef5  mov     rcx, rdi
0x140079ef8  mov     rax, [rax+30h]
0x140079efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079f01  mov     [rbp+arg_8], eax
0x140079f04  test    eax, eax
0x140079f06  js      loc_14007A006
0x140079f0c  mov     rax, [rbp+arg_18]
0x140079f10  mov     rcx, [rax+38h]
0x140079f14  mov     [rbp+pHandles], rcx
0x140079f18  mov     [rbp+var_10], r14
0x140079f1c  mov     bl, r14b
0x140079f1f  mov     dword ptr [rbp+dwindex], r14d
0x140079f23  lea     rax, [rbp+dwindex]
0x140079f27  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x140079f2c  lea     r9, [rbp+pHandles]; pHandles
0x140079f30  mov     r8d, 1; cHandles
0x140079f36  or      edx, 0FFFFFFFFh; dwTimeout
0x140079f39  lea     ecx, [r8+7]; dwFlags
0x140079f3d  call    cs:__imp_CoWaitForMultipleHandles
0x140079f43  mov     [rbp+arg_8], eax
0x140079f46  test    eax, eax
0x140079f48  js      short loc_140079F59
0x140079f4a  cmp     dword ptr [rbp+dwindex], r14d
0x140079f4e  jz      short loc_140079F59
0x140079f50  mov     [rbp+arg_8], 800704C7h
0x140079f57  mov     bl, 1
0x140079f59  mov     [rbp+arg_0], r14
0x140079f5d  test    bl, bl
0x140079f5f  jz      short loc_140079F99
0x140079f61  mov     rax, [rdi]
0x140079f64  mov     rbx, [rax]
0x140079f67  lea     rcx, [rbp+arg_0]
0x140079f6b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x140079f70  mov     r8, rax
0x140079f73  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140079f7a  mov     rcx, rdi
0x140079f7d  mov     rax, rbx
0x140079f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079f85  test    eax, eax
0x140079f87  js      short loc_140079F99
0x140079f89  mov     rcx, [rbp+arg_0]
0x140079f8d  mov     rax, [rcx]
0x140079f90  mov     rax, [rax+48h]
0x140079f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079f99  cmp     [rbp+arg_8], r14d
0x140079f9d  jl      short loc_140079FEC
0x140079f9f  mov     rax, [rbp+arg_18]
0x140079fa3  cmp     dword ptr [rax+30h], 1
0x140079fa7  jz      short loc_140079FEC
0x140079fa9  cmp     [rbp+arg_0], r14
0x140079fad  jnz     short loc_140079FD7
0x140079faf  mov     rax, [rdi]
0x140079fb2  mov     rbx, [rax]
0x140079fb5  lea     rcx, [rbp+arg_0]
0x140079fb9  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x140079fbe  mov     r8, rax
0x140079fc1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140079fc8  mov     rcx, rdi
0x140079fcb  mov     rax, rbx
0x140079fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079fd3  test    eax, eax
0x140079fd5  js      short loc_140079FEC
0x140079fd7  mov     rcx, [rbp+arg_0]
0x140079fdb  mov     rax, [rcx]
0x140079fde  lea     rdx, [rbp+arg_8]
0x140079fe2  mov     rax, [rax+40h]
0x140079fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079feb  nop
0x140079fec  mov     rcx, [rbp+arg_0]
0x140079ff0  test    rcx, rcx
0x140079ff3  jz      short loc_14007A006
0x140079ff5  mov     [rbp+arg_0], r14
0x140079ff9  mov     rax, [rcx]
0x140079ffc  mov     rax, [rax+10h]
0x14007a000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a005  nop
0x14007a006  mov     ebx, [rbp+arg_8]
0x14007a009  mov     rcx, [rbp+arg_18]
0x14007a00d  test    rcx, rcx
0x14007a010  jz      short loc_14007A023
0x14007a012  mov     [rbp+arg_18], r14
0x14007a016  mov     rax, [rcx]
0x14007a019  mov     rax, [rax+10h]
0x14007a01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a022  nop
0x14007a023  test    rdi, rdi
0x14007a026  jz      short loc_14007A038
0x14007a028  mov     rcx, [rdi]
0x14007a02b  mov     rax, [rcx+10h]
0x14007a02f  mov     rcx, rdi
0x14007a032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a037  nop
0x14007a038  mov     eax, ebx
0x14007a03a  add     rsp, 50h
0x14007a03e  pop     r14
0x14007a040  pop     rdi
0x14007a041  pop     rsi
0x14007a042  pop     rbx
0x14007a043  pop     rbp
0x14007a044  retn
```
