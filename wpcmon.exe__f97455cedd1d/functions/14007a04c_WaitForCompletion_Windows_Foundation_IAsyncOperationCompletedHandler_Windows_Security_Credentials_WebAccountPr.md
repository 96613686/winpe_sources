# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x14007a04c`
- end: `0x14007a2d9`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140079ac8`

## callees

- `0x140007914`
- `0x14002f920`
- `0x1400461d8`
- `0x14007a04c`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x14007a11a`
- `KERNEL32!CreateEventExW` at `0x14007a11a`
- `KERNEL32!GetLastError` at `0x14007a129`
- `KERNEL32!GetLastError` at `0x14007a129`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14007a1d1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14007a1d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
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
0x14007a04c  mov     [rsp-28h+dwindex], r8
0x14007a051  mov     [rsp-28h+arg_8], edx
0x14007a055  push    rbp
0x14007a056  push    rbx
0x14007a057  push    rsi
0x14007a058  push    rdi
0x14007a059  push    r14
0x14007a05b  mov     rbp, rsp
0x14007a05e  sub     rsp, 50h
0x14007a062  mov     rdi, rcx
0x14007a065  mov     [rbp+var_20], rcx
0x14007a069  xor     r14d, r14d
0x14007a06c  test    rcx, rcx
0x14007a06f  jz      short loc_14007A07E
0x14007a071  mov     rax, [rcx]
0x14007a074  mov     rax, [rax+8]
0x14007a078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a07d  nop
0x14007a07e  mov     [rbp+arg_18], r14
0x14007a082  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14007a089  mov     ecx, 40h ; '@'; unsigned __int64
0x14007a08e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14007a093  mov     rbx, rax
0x14007a096  test    rax, rax
0x14007a099  jnz     short loc_14007A0A7
0x14007a09b  mov     [rbp+arg_8], 8007000Eh
0x14007a0a2  jmp     loc_14007A29A
0x14007a0a7  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>::`vftable'
0x14007a0ae  mov     [rbx], rax
0x14007a0b1  lea     rsi, [rbx+8]
0x14007a0b5  mov     rcx, rsi; this
0x14007a0b8  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x14007a0bd  mov     dword ptr [rbx+2Ch], 1
0x14007a0c4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x14007a0cb  mov     [rbx], rax
0x14007a0ce  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14007a0d5  mov     [rsi], rax
0x14007a0d8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14007a0df  test    rcx, rcx
0x14007a0e2  jz      short loc_14007A0F1
0x14007a0e4  mov     rax, [rcx]
0x14007a0e7  mov     rax, [rax+8]
0x14007a0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a0f0  nop
0x14007a0f1  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x14007a0f8  mov     [rbx], rax
0x14007a0fb  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14007a102  mov     [rsi], rax
0x14007a105  mov     [rbx+30h], r14d
0x14007a109  mov     [rbx+38h], r14
0x14007a10d  mov     r9d, 1F0003h; dwDesiredAccess
0x14007a113  xor     r8d, r8d; dwFlags
0x14007a116  xor     edx, edx; lpName
0x14007a118  xor     ecx, ecx; lpEventAttributes
0x14007a11a  call    cs:__imp_CreateEventExW
0x14007a120  mov     [rbx+38h], rax
0x14007a124  test    rax, rax
0x14007a127  jnz     short loc_14007A15A
0x14007a129  call    cs:__imp_GetLastError
0x14007a12f  mov     esi, eax
0x14007a131  test    eax, eax
0x14007a133  jle     short loc_14007A13E
0x14007a135  movzx   esi, ax
0x14007a138  or      esi, 80070000h
0x14007a13e  mov     rax, [rbx]
0x14007a141  test    esi, esi
0x14007a143  jns     short loc_14007A15D
0x14007a145  mov     rcx, rbx
0x14007a148  mov     rax, [rax+10h]
0x14007a14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a151  nop
0x14007a152  mov     [rbp+arg_8], esi
0x14007a155  jmp     loc_14007A29A
0x14007a15a  mov     rax, [rbx]
0x14007a15d  mov     rcx, rbx
0x14007a160  mov     rax, [rax+8]
0x14007a164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a169  nop
0x14007a16a  mov     [rbp+arg_18], rbx
0x14007a16e  mov     rax, [rbx]
0x14007a171  mov     rcx, rbx
0x14007a174  mov     rax, [rax+10h]
0x14007a178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a17d  nop
0x14007a17e  mov     [rbp+arg_8], r14d
0x14007a182  mov     rax, [rdi]
0x14007a185  mov     rdx, [rbp+arg_18]
0x14007a189  mov     rcx, rdi
0x14007a18c  mov     rax, [rax+30h]
0x14007a190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a195  mov     [rbp+arg_8], eax
0x14007a198  test    eax, eax
0x14007a19a  js      loc_14007A29A
0x14007a1a0  mov     rax, [rbp+arg_18]
0x14007a1a4  mov     rcx, [rax+38h]
0x14007a1a8  mov     [rbp+pHandles], rcx
0x14007a1ac  mov     [rbp+var_10], r14
0x14007a1b0  mov     bl, r14b
0x14007a1b3  mov     dword ptr [rbp+dwindex], r14d
0x14007a1b7  lea     rax, [rbp+dwindex]
0x14007a1bb  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x14007a1c0  lea     r9, [rbp+pHandles]; pHandles
0x14007a1c4  mov     r8d, 1; cHandles
0x14007a1ca  or      edx, 0FFFFFFFFh; dwTimeout
0x14007a1cd  lea     ecx, [r8+7]; dwFlags
0x14007a1d1  call    cs:__imp_CoWaitForMultipleHandles
0x14007a1d7  mov     [rbp+arg_8], eax
0x14007a1da  test    eax, eax
0x14007a1dc  js      short loc_14007A1ED
0x14007a1de  cmp     dword ptr [rbp+dwindex], r14d
0x14007a1e2  jz      short loc_14007A1ED
0x14007a1e4  mov     [rbp+arg_8], 800704C7h
0x14007a1eb  mov     bl, 1
0x14007a1ed  mov     [rbp+arg_0], r14
0x14007a1f1  test    bl, bl
0x14007a1f3  jz      short loc_14007A22D
0x14007a1f5  mov     rax, [rdi]
0x14007a1f8  mov     rbx, [rax]
0x14007a1fb  lea     rcx, [rbp+arg_0]
0x14007a1ff  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x14007a204  mov     r8, rax
0x14007a207  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14007a20e  mov     rcx, rdi
0x14007a211  mov     rax, rbx
0x14007a214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a219  test    eax, eax
0x14007a21b  js      short loc_14007A22D
0x14007a21d  mov     rcx, [rbp+arg_0]
0x14007a221  mov     rax, [rcx]
0x14007a224  mov     rax, [rax+48h]
0x14007a228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a22d  cmp     [rbp+arg_8], r14d
0x14007a231  jl      short loc_14007A280
0x14007a233  mov     rax, [rbp+arg_18]
0x14007a237  cmp     dword ptr [rax+30h], 1
0x14007a23b  jz      short loc_14007A280
0x14007a23d  cmp     [rbp+arg_0], r14
0x14007a241  jnz     short loc_14007A26B
0x14007a243  mov     rax, [rdi]
0x14007a246  mov     rbx, [rax]
0x14007a249  lea     rcx, [rbp+arg_0]
0x14007a24d  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x14007a252  mov     r8, rax
0x14007a255  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14007a25c  mov     rcx, rdi
0x14007a25f  mov     rax, rbx
0x14007a262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a267  test    eax, eax
0x14007a269  js      short loc_14007A280
0x14007a26b  mov     rcx, [rbp+arg_0]
0x14007a26f  mov     rax, [rcx]
0x14007a272  lea     rdx, [rbp+arg_8]
0x14007a276  mov     rax, [rax+40h]
0x14007a27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a27f  nop
0x14007a280  mov     rcx, [rbp+arg_0]
0x14007a284  test    rcx, rcx
0x14007a287  jz      short loc_14007A29A
0x14007a289  mov     [rbp+arg_0], r14
0x14007a28d  mov     rax, [rcx]
0x14007a290  mov     rax, [rax+10h]
0x14007a294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a299  nop
0x14007a29a  mov     ebx, [rbp+arg_8]
0x14007a29d  mov     rcx, [rbp+arg_18]
0x14007a2a1  test    rcx, rcx
0x14007a2a4  jz      short loc_14007A2B7
0x14007a2a6  mov     [rbp+arg_18], r14
0x14007a2aa  mov     rax, [rcx]
0x14007a2ad  mov     rax, [rax+10h]
0x14007a2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a2b6  nop
0x14007a2b7  test    rdi, rdi
0x14007a2ba  jz      short loc_14007A2CC
0x14007a2bc  mov     rcx, [rdi]
0x14007a2bf  mov     rax, [rcx+10h]
0x14007a2c3  mov     rcx, rdi
0x14007a2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a2cb  nop
0x14007a2cc  mov     eax, ebx
0x14007a2ce  add     rsp, 50h
0x14007a2d2  pop     r14
0x14007a2d4  pop     rdi
0x14007a2d5  pop     rsi
0x14007a2d6  pop     rbx
0x14007a2d7  pop     rbp
0x14007a2d8  retn
```
