# WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)

- ea: `0x18000e24c`
- end: `0x18000e4cf`
- name: `??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056350`

## callees

- `0x180005504`
- `0x180008b68`
- `0x18000e24c`
- `0x1800143c4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e310`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e31f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e31f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e3c7`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e3c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64),
        HRESULT a2,
        __int64 a3)
{
  char *v4; // rax
  char *v5; // rbx
  _QWORD *v6; // rsi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v9; // esi
  __int64 v10; // rax
  char v11; // bl
  int (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  __int64 v13; // rax
  int (__fastcall *v14)(_QWORD, GUID *, __int64); // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // ebx
  char *v18; // rcx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v21; // [rsp+80h] [rbp+30h] BYREF
  HRESULT v22; // [rsp+88h] [rbp+38h] BYREF
  __int64 dwindex; // [rsp+90h] [rbp+40h] BYREF
  char *v24; // [rsp+98h] [rbp+48h]

  dwindex = a3;
  v22 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[1])(a1);
  v24 = 0;
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    v22 = -2147024882;
    goto LABEL_27;
  }
  v6 = v4 + 8;
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 8));
  *((_DWORD *)v5 + 11) = 1;
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
  *v6 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *v6 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *((_DWORD *)v5 + 12) = 0;
  *((_QWORD *)v5 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)v5 + 7) = Event;
  if ( Event )
  {
    v10 = *(_QWORD *)v5;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = *(_QWORD *)v5;
    if ( v9 < 0 )
    {
      (*(void (__fastcall **)(char *))(v10 + 16))(v5);
      v22 = v9;
      goto LABEL_27;
    }
  }
  (*(void (__fastcall **)(char *))(v10 + 8))(v5);
  v24 = v5;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
  v22 = 0;
  v22 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64), char *))(*a1)[6])(a1, v24);
  if ( v22 >= 0 )
  {
    pHandles[0] = *((HANDLE *)v24 + 7);
    pHandles[1] = 0;
    v11 = 0;
    LODWORD(dwindex) = 0;
    v22 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
    if ( v22 >= 0 && (_DWORD)dwindex )
    {
      v22 = -2147023673;
      v11 = 1;
    }
    v21 = 0;
    if ( v11 )
    {
      v12 = **a1;
      v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v21);
      if ( v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 72LL))(v21);
    }
    if ( v22 >= 0 && *((_DWORD *)v24 + 12) != 1 )
    {
      if ( v21
        || (v14 = **a1,
            v15 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v21),
            v14(a1, &GUID_00000036_0000_0000_c000_000000000046, v15) >= 0) )
      {
        (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v21 + 64LL))(v21, &v22);
      }
    }
    v16 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
LABEL_27:
  v17 = v22;
  v18 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[2])(a1);
  return v17;
}

```

## disassembly

```asm
0x18000e24c  mov     [rsp-28h+dwindex], r8
0x18000e251  mov     [rsp-28h+arg_8], edx
0x18000e255  push    rbp
0x18000e256  push    rbx
0x18000e257  push    rsi
0x18000e258  push    rdi
0x18000e259  push    r14
0x18000e25b  mov     rbp, rsp
0x18000e25e  sub     rsp, 50h
0x18000e262  mov     rdi, rcx
0x18000e265  mov     [rbp+var_20], rcx
0x18000e269  xor     r14d, r14d
0x18000e26c  test    rcx, rcx
0x18000e26f  jz      short loc_18000E27E
0x18000e271  mov     rax, [rcx]
0x18000e274  mov     rax, [rax+8]
0x18000e278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e27d  nop
0x18000e27e  mov     [rbp+arg_18], r14
0x18000e282  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e289  mov     ecx, 40h ; '@'; unsigned __int64
0x18000e28e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e293  mov     rbx, rax
0x18000e296  test    rax, rax
0x18000e299  jnz     short loc_18000E2A7
0x18000e29b  mov     [rbp+arg_8], 8007000Eh
0x18000e2a2  jmp     loc_18000E490
0x18000e2a7  lea     rsi, [rax+8]
0x18000e2ab  mov     rcx, rsi; this
0x18000e2ae  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000e2b3  mov     dword ptr [rbx+2Ch], 1
0x18000e2ba  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18000e2c1  mov     [rbx], rax
0x18000e2c4  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e2cb  mov     [rsi], rax
0x18000e2ce  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e2d5  test    rcx, rcx
0x18000e2d8  jz      short loc_18000E2E7
0x18000e2da  mov     rax, [rcx]
0x18000e2dd  mov     rax, [rax+8]
0x18000e2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2e6  nop
0x18000e2e7  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18000e2ee  mov     [rbx], rax
0x18000e2f1  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e2f8  mov     [rsi], rax
0x18000e2fb  mov     [rbx+30h], r14d
0x18000e2ff  mov     [rbx+38h], r14
0x18000e303  mov     r9d, 1F0003h; dwDesiredAccess
0x18000e309  xor     r8d, r8d; dwFlags
0x18000e30c  xor     edx, edx; lpName
0x18000e30e  xor     ecx, ecx; lpEventAttributes
0x18000e310  call    cs:__imp_CreateEventExW
0x18000e316  mov     [rbx+38h], rax
0x18000e31a  test    rax, rax
0x18000e31d  jnz     short loc_18000E350
0x18000e31f  call    cs:__imp_GetLastError
0x18000e325  mov     esi, eax
0x18000e327  test    eax, eax
0x18000e329  jle     short loc_18000E334
0x18000e32b  movzx   esi, ax
0x18000e32e  or      esi, 80070000h
0x18000e334  mov     rax, [rbx]
0x18000e337  test    esi, esi
0x18000e339  jns     short loc_18000E353
0x18000e33b  mov     rcx, rbx
0x18000e33e  mov     rax, [rax+10h]
0x18000e342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e347  nop
0x18000e348  mov     [rbp+arg_8], esi
0x18000e34b  jmp     loc_18000E490
0x18000e350  mov     rax, [rbx]
0x18000e353  mov     rcx, rbx
0x18000e356  mov     rax, [rax+8]
0x18000e35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e35f  nop
0x18000e360  mov     [rbp+arg_18], rbx
0x18000e364  mov     rax, [rbx]
0x18000e367  mov     rcx, rbx
0x18000e36a  mov     rax, [rax+10h]
0x18000e36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e373  nop
0x18000e374  mov     [rbp+arg_8], r14d
0x18000e378  mov     rax, [rdi]
0x18000e37b  mov     rdx, [rbp+arg_18]
0x18000e37f  mov     rcx, rdi
0x18000e382  mov     rax, [rax+30h]
0x18000e386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e38b  mov     [rbp+arg_8], eax
0x18000e38e  test    eax, eax
0x18000e390  js      loc_18000E490
0x18000e396  mov     rax, [rbp+arg_18]
0x18000e39a  mov     rcx, [rax+38h]
0x18000e39e  mov     [rbp+pHandles], rcx
0x18000e3a2  mov     [rbp+var_10], r14
0x18000e3a6  mov     bl, r14b
0x18000e3a9  mov     dword ptr [rbp+dwindex], r14d
0x18000e3ad  lea     rax, [rbp+dwindex]
0x18000e3b1  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18000e3b6  lea     r9, [rbp+pHandles]; pHandles
0x18000e3ba  mov     r8d, 1; cHandles
0x18000e3c0  or      edx, 0FFFFFFFFh; dwTimeout
0x18000e3c3  lea     ecx, [r8+7]; dwFlags
0x18000e3c7  call    cs:__imp_CoWaitForMultipleHandles
0x18000e3cd  mov     [rbp+arg_8], eax
0x18000e3d0  test    eax, eax
0x18000e3d2  js      short loc_18000E3E3
0x18000e3d4  cmp     dword ptr [rbp+dwindex], r14d
0x18000e3d8  jz      short loc_18000E3E3
0x18000e3da  mov     [rbp+arg_8], 800704C7h
0x18000e3e1  mov     bl, 1
0x18000e3e3  mov     [rbp+arg_0], r14
0x18000e3e7  test    bl, bl
0x18000e3e9  jz      short loc_18000E423
0x18000e3eb  mov     rax, [rdi]
0x18000e3ee  mov     rbx, [rax]
0x18000e3f1  lea     rcx, [rbp+arg_0]
0x18000e3f5  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000e3fa  mov     r8, rax
0x18000e3fd  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e404  mov     rcx, rdi
0x18000e407  mov     rax, rbx
0x18000e40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e40f  test    eax, eax
0x18000e411  js      short loc_18000E423
0x18000e413  mov     rcx, [rbp+arg_0]
0x18000e417  mov     rax, [rcx]
0x18000e41a  mov     rax, [rax+48h]
0x18000e41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e423  cmp     [rbp+arg_8], r14d
0x18000e427  jl      short loc_18000E476
0x18000e429  mov     rax, [rbp+arg_18]
0x18000e42d  cmp     dword ptr [rax+30h], 1
0x18000e431  jz      short loc_18000E476
0x18000e433  cmp     [rbp+arg_0], r14
0x18000e437  jnz     short loc_18000E461
0x18000e439  mov     rax, [rdi]
0x18000e43c  mov     rbx, [rax]
0x18000e43f  lea     rcx, [rbp+arg_0]
0x18000e443  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18000e448  mov     r8, rax
0x18000e44b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e452  mov     rcx, rdi
0x18000e455  mov     rax, rbx
0x18000e458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e45d  test    eax, eax
0x18000e45f  js      short loc_18000E476
0x18000e461  mov     rcx, [rbp+arg_0]
0x18000e465  mov     rax, [rcx]
0x18000e468  lea     rdx, [rbp+arg_8]
0x18000e46c  mov     rax, [rax+40h]
0x18000e470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e475  nop
0x18000e476  mov     rcx, [rbp+arg_0]
0x18000e47a  test    rcx, rcx
0x18000e47d  jz      short loc_18000E490
0x18000e47f  mov     [rbp+arg_0], r14
0x18000e483  mov     rax, [rcx]
0x18000e486  mov     rax, [rax+10h]
0x18000e48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e48f  nop
0x18000e490  mov     ebx, [rbp+arg_8]
0x18000e493  mov     rcx, [rbp+arg_18]
0x18000e497  test    rcx, rcx
0x18000e49a  jz      short loc_18000E4AD
0x18000e49c  mov     [rbp+arg_18], r14
0x18000e4a0  mov     rax, [rcx]
0x18000e4a3  mov     rax, [rax+10h]
0x18000e4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ac  nop
0x18000e4ad  test    rdi, rdi
0x18000e4b0  jz      short loc_18000E4C2
0x18000e4b2  mov     rcx, [rdi]
0x18000e4b5  mov     rax, [rcx+10h]
0x18000e4b9  mov     rcx, rdi
0x18000e4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4c1  nop
0x18000e4c2  mov     eax, ebx
0x18000e4c4  add     rsp, 50h
0x18000e4c8  pop     r14
0x18000e4ca  pop     rdi
0x18000e4cb  pop     rsi
0x18000e4cc  pop     rbx
0x18000e4cd  pop     rbp
0x18000e4ce  retn
```
