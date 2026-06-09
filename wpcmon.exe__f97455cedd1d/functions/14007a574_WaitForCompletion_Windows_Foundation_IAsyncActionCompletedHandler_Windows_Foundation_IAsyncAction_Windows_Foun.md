# WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)

- ea: `0x14007a574`
- end: `0x14007a7f7`
- name: `??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `643`
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
- `0x14007a574`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x14007a638`
- `KERNEL32!CreateEventExW` at `0x14007a638`
- `KERNEL32!GetLastError` at `0x14007a647`
- `KERNEL32!GetLastError` at `0x14007a647`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14007a6ef`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14007a6ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
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
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v13; // rax
  int (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v15; // rax
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
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
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
  *v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
  v22 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), char *))(*a1)[6])(a1, v24);
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
      v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v21);
      if ( v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 72LL))(v21);
    }
    if ( v22 >= 0 && *((_DWORD *)v24 + 12) != 1 )
    {
      if ( v21
        || (v14 = **a1,
            v15 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v21),
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
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v17;
}

```

## disassembly

```asm
0x14007a574  mov     [rsp-28h+dwindex], r8
0x14007a579  mov     [rsp-28h+arg_8], edx
0x14007a57d  push    rbp
0x14007a57e  push    rbx
0x14007a57f  push    rsi
0x14007a580  push    rdi
0x14007a581  push    r14
0x14007a583  mov     rbp, rsp
0x14007a586  sub     rsp, 50h
0x14007a58a  mov     rdi, rcx
0x14007a58d  mov     [rbp+var_20], rcx
0x14007a591  xor     r14d, r14d
0x14007a594  test    rcx, rcx
0x14007a597  jz      short loc_14007A5A6
0x14007a599  mov     rax, [rcx]
0x14007a59c  mov     rax, [rax+8]
0x14007a5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a5a5  nop
0x14007a5a6  mov     [rbp+arg_18], r14
0x14007a5aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14007a5b1  mov     ecx, 40h ; '@'; unsigned __int64
0x14007a5b6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14007a5bb  mov     rbx, rax
0x14007a5be  test    rax, rax
0x14007a5c1  jnz     short loc_14007A5CF
0x14007a5c3  mov     [rbp+arg_8], 8007000Eh
0x14007a5ca  jmp     loc_14007A7B8
0x14007a5cf  lea     rsi, [rax+8]
0x14007a5d3  mov     rcx, rsi; this
0x14007a5d6  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x14007a5db  mov     dword ptr [rbx+2Ch], 1
0x14007a5e2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x14007a5e9  mov     [rbx], rax
0x14007a5ec  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14007a5f3  mov     [rsi], rax
0x14007a5f6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14007a5fd  test    rcx, rcx
0x14007a600  jz      short loc_14007A60F
0x14007a602  mov     rax, [rcx]
0x14007a605  mov     rax, [rax+8]
0x14007a609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a60e  nop
0x14007a60f  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x14007a616  mov     [rbx], rax
0x14007a619  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14007a620  mov     [rsi], rax
0x14007a623  mov     [rbx+30h], r14d
0x14007a627  mov     [rbx+38h], r14
0x14007a62b  mov     r9d, 1F0003h; dwDesiredAccess
0x14007a631  xor     r8d, r8d; dwFlags
0x14007a634  xor     edx, edx; lpName
0x14007a636  xor     ecx, ecx; lpEventAttributes
0x14007a638  call    cs:__imp_CreateEventExW
0x14007a63e  mov     [rbx+38h], rax
0x14007a642  test    rax, rax
0x14007a645  jnz     short loc_14007A678
0x14007a647  call    cs:__imp_GetLastError
0x14007a64d  mov     esi, eax
0x14007a64f  test    eax, eax
0x14007a651  jle     short loc_14007A65C
0x14007a653  movzx   esi, ax
0x14007a656  or      esi, 80070000h
0x14007a65c  mov     rax, [rbx]
0x14007a65f  test    esi, esi
0x14007a661  jns     short loc_14007A67B
0x14007a663  mov     rcx, rbx
0x14007a666  mov     rax, [rax+10h]
0x14007a66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a66f  nop
0x14007a670  mov     [rbp+arg_8], esi
0x14007a673  jmp     loc_14007A7B8
0x14007a678  mov     rax, [rbx]
0x14007a67b  mov     rcx, rbx
0x14007a67e  mov     rax, [rax+8]
0x14007a682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a687  nop
0x14007a688  mov     [rbp+arg_18], rbx
0x14007a68c  mov     rax, [rbx]
0x14007a68f  mov     rcx, rbx
0x14007a692  mov     rax, [rax+10h]
0x14007a696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a69b  nop
0x14007a69c  mov     [rbp+arg_8], r14d
0x14007a6a0  mov     rax, [rdi]
0x14007a6a3  mov     rdx, [rbp+arg_18]
0x14007a6a7  mov     rcx, rdi
0x14007a6aa  mov     rax, [rax+30h]
0x14007a6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a6b3  mov     [rbp+arg_8], eax
0x14007a6b6  test    eax, eax
0x14007a6b8  js      loc_14007A7B8
0x14007a6be  mov     rax, [rbp+arg_18]
0x14007a6c2  mov     rcx, [rax+38h]
0x14007a6c6  mov     [rbp+pHandles], rcx
0x14007a6ca  mov     [rbp+var_10], r14
0x14007a6ce  mov     bl, r14b
0x14007a6d1  mov     dword ptr [rbp+dwindex], r14d
0x14007a6d5  lea     rax, [rbp+dwindex]
0x14007a6d9  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x14007a6de  lea     r9, [rbp+pHandles]; pHandles
0x14007a6e2  mov     r8d, 1; cHandles
0x14007a6e8  or      edx, 0FFFFFFFFh; dwTimeout
0x14007a6eb  lea     ecx, [r8+7]; dwFlags
0x14007a6ef  call    cs:__imp_CoWaitForMultipleHandles
0x14007a6f5  mov     [rbp+arg_8], eax
0x14007a6f8  test    eax, eax
0x14007a6fa  js      short loc_14007A70B
0x14007a6fc  cmp     dword ptr [rbp+dwindex], r14d
0x14007a700  jz      short loc_14007A70B
0x14007a702  mov     [rbp+arg_8], 800704C7h
0x14007a709  mov     bl, 1
0x14007a70b  mov     [rbp+arg_0], r14
0x14007a70f  test    bl, bl
0x14007a711  jz      short loc_14007A74B
0x14007a713  mov     rax, [rdi]
0x14007a716  mov     rbx, [rax]
0x14007a719  lea     rcx, [rbp+arg_0]
0x14007a71d  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x14007a722  mov     r8, rax
0x14007a725  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14007a72c  mov     rcx, rdi
0x14007a72f  mov     rax, rbx
0x14007a732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a737  test    eax, eax
0x14007a739  js      short loc_14007A74B
0x14007a73b  mov     rcx, [rbp+arg_0]
0x14007a73f  mov     rax, [rcx]
0x14007a742  mov     rax, [rax+48h]
0x14007a746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a74b  cmp     [rbp+arg_8], r14d
0x14007a74f  jl      short loc_14007A79E
0x14007a751  mov     rax, [rbp+arg_18]
0x14007a755  cmp     dword ptr [rax+30h], 1
0x14007a759  jz      short loc_14007A79E
0x14007a75b  cmp     [rbp+arg_0], r14
0x14007a75f  jnz     short loc_14007A789
0x14007a761  mov     rax, [rdi]
0x14007a764  mov     rbx, [rax]
0x14007a767  lea     rcx, [rbp+arg_0]
0x14007a76b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x14007a770  mov     r8, rax
0x14007a773  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14007a77a  mov     rcx, rdi
0x14007a77d  mov     rax, rbx
0x14007a780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a785  test    eax, eax
0x14007a787  js      short loc_14007A79E
0x14007a789  mov     rcx, [rbp+arg_0]
0x14007a78d  mov     rax, [rcx]
0x14007a790  lea     rdx, [rbp+arg_8]
0x14007a794  mov     rax, [rax+40h]
0x14007a798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a79d  nop
0x14007a79e  mov     rcx, [rbp+arg_0]
0x14007a7a2  test    rcx, rcx
0x14007a7a5  jz      short loc_14007A7B8
0x14007a7a7  mov     [rbp+arg_0], r14
0x14007a7ab  mov     rax, [rcx]
0x14007a7ae  mov     rax, [rax+10h]
0x14007a7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a7b7  nop
0x14007a7b8  mov     ebx, [rbp+arg_8]
0x14007a7bb  mov     rcx, [rbp+arg_18]
0x14007a7bf  test    rcx, rcx
0x14007a7c2  jz      short loc_14007A7D5
0x14007a7c4  mov     [rbp+arg_18], r14
0x14007a7c8  mov     rax, [rcx]
0x14007a7cb  mov     rax, [rax+10h]
0x14007a7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a7d4  nop
0x14007a7d5  test    rdi, rdi
0x14007a7d8  jz      short loc_14007A7EA
0x14007a7da  mov     rcx, [rdi]
0x14007a7dd  mov     rax, [rcx+10h]
0x14007a7e1  mov     rcx, rdi
0x14007a7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a7e9  nop
0x14007a7ea  mov     eax, ebx
0x14007a7ec  add     rsp, 50h
0x14007a7f0  pop     r14
0x14007a7f2  pop     rdi
0x14007a7f3  pop     rsi
0x14007a7f4  pop     rbx
0x14007a7f5  pop     rbp
0x14007a7f6  retn
```
