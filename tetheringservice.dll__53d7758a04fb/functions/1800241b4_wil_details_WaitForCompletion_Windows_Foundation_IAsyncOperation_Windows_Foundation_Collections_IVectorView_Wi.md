# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x1800241b4`
- end: `0x18002448a`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `726`
- prototype: `__int64(__int64, DWORD, int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025ae0`

## callees

- `0x18000299c`
- `0x1800067c8`
- `0x180008934`
- `0x18000a21c`
- `0x1800241b4`
- `0x18002476c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024274`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024295`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800242b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800242b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800242a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800242a1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800243a0`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800243a0`

## string_xrefs

- `0x1800242ff`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x180024335`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x18002435e`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x1800243b3`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *>(
        __int64 a1,
        DWORD a2,
        int a3,
        ...)
{
  char *v4; // rbx
  unsigned int v5; // edi
  wil::details *v6; // rcx
  HANDLE Event; // rsi
  void *v8; // rdi
  DWORD LastError; // r15d
  unsigned int v10; // r8d
  const char *v11; // r9
  int v12; // eax
  int LastErrorFailHr; // eax
  HRESULT v15; // eax
  __int64 v16; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD dwindex; // [rsp+78h] [rbp+38h] BYREF
  int v22; // [rsp+80h] [rbp+40h] BYREF
  __int64 v23; // [rsp+88h] [rbp+48h] BYREF
  va_list va; // [rsp+88h] [rbp+48h]
  va_list va1; // [rsp+90h] [rbp+50h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v23 = va_arg(va1, _QWORD);
  v22 = a3;
  dwindex = a2;
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v5 = -2147024882;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)v5,
      lpdwindex);
    return v5;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 8);
  *((_DWORD *)v4 + 11) = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>'};
  *((_QWORD *)v4 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *>'::`2'::CompletionDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *>'::`2'::CompletionDelegate::`vftable';
  *((_DWORD *)v4 + 12) = 0;
  *((_QWORD *)v4 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v8 = (void *)*((_QWORD *)v4 + 7);
    if ( v8 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
      SetLastError(LastError);
    }
    *((_QWORD *)v4 + 7) = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
    v5 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwindex);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
      goto LABEL_14;
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  v12 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a1 + 48LL))(a1, v4);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v12,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  pHandles = (HANDLE)*((_QWORD *)v4 + 7);
  dwindex = 0;
  v15 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x655,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v15,
      lpdwindexa);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  if ( *((_DWORD *)v4 + 12) != 1 )
  {
    v23 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
           a1,
           &GUID_00000036_0000_0000_c000_000000000046,
           (__int64 *)va);
    if ( (v5 & 0x80000000) == 0 )
    {
      v22 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 64LL))(v23, &v22);
      if ( (v5 & 0x80000000) == 0 )
        v5 = v22;
    }
    v16 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x1800241b4  mov     rax, rsp
0x1800241b7  mov     [rax+8], rbx
0x1800241bb  mov     [rax+20h], r9
0x1800241bf  mov     [rax+18h], r8d
0x1800241c3  mov     [rax+10h], edx
0x1800241c6  push    rbp
0x1800241c7  push    rsi
0x1800241c8  push    rdi
0x1800241c9  push    r14
0x1800241cb  push    r15
0x1800241cd  mov     rbp, rsp
0x1800241d0  sub     rsp, 40h
0x1800241d4  mov     r14, rcx
0x1800241d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800241de  mov     ecx, 40h ; '@'; unsigned __int64
0x1800241e3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800241e8  mov     rbx, rax
0x1800241eb  test    rax, rax
0x1800241ee  jnz     short loc_1800241FA
0x1800241f0  mov     edi, 8007000Eh
0x1800241f5  jmp     loc_180024357
0x1800241fa  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x180024201  mov     [rbx], rax
0x180024204  lea     rdi, [rbx+8]
0x180024208  mov     rcx, rdi
0x18002420b  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180024210  mov     dword ptr [rbx+2Ch], 1
0x180024217  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>'}
0x18002421e  mov     [rbx], rax
0x180024221  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180024228  mov     [rdi], rax
0x18002422b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180024232  test    rcx, rcx
0x180024235  jz      short loc_180024244
0x180024237  mov     rax, [rcx]
0x18002423a  mov     rax, [rax+8]
0x18002423e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024243  nop
0x180024244  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>'}
0x18002424b  mov     [rbx], rax
0x18002424e  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180024255  mov     [rdi], rax
0x180024258  mov     dword ptr [rbx+30h], 0
0x18002425f  mov     qword ptr [rbx+38h], 0
0x180024267  mov     r9d, 1F0003h; dwDesiredAccess
0x18002426d  xor     r8d, r8d; dwFlags
0x180024270  xor     edx, edx; lpName
0x180024272  xor     ecx, ecx; lpEventAttributes
0x180024274  call    cs:__imp_CreateEventExW
0x18002427a  mov     rsi, rax
0x18002427d  test    rax, rax
0x180024280  jz      loc_180024323
0x180024286  call    cs:__imp_GetLastError
0x18002428c  mov     rdi, [rbx+38h]
0x180024290  test    rdi, rdi
0x180024293  jz      short loc_1800242BC
0x180024295  call    cs:__imp_GetLastError
0x18002429b  mov     r15d, eax
0x18002429e  mov     rcx, rdi; hObject
0x1800242a1  call    cs:__imp_CloseHandle
0x1800242a7  mov     rcx, [rbp+28h]; this
0x1800242ab  test    eax, eax
0x1800242ad  jz      loc_18002447F
0x1800242b3  mov     ecx, r15d; dwErrCode
0x1800242b6  call    cs:__imp_SetLastError
0x1800242bc  mov     [rbx+38h], rsi
0x1800242c0  mov     rax, [rbx]
0x1800242c3  mov     rcx, rbx
0x1800242c6  mov     rax, [rax+8]
0x1800242ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242cf  nop
0x1800242d0  mov     rax, [rbx]
0x1800242d3  mov     rcx, rbx
0x1800242d6  mov     rax, [rax+10h]
0x1800242da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242df  nop
0x1800242e0  mov     rax, [r14]
0x1800242e3  mov     rdx, rbx
0x1800242e6  mov     rcx, r14
0x1800242e9  mov     rax, [rax+30h]
0x1800242ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242f2  mov     edi, eax
0x1800242f4  test    eax, eax
0x1800242f6  jns     short loc_180024377
0x1800242f8  mov     rcx, [rbp+28h]; this
0x1800242fc  mov     r9d, eax; char *
0x1800242ff  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024306  mov     edx, 649h; void *
0x18002430b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024310  nop
0x180024311  mov     rcx, [rbx]
0x180024314  mov     rax, [rcx+10h]
0x180024318  mov     rcx, rbx
0x18002431b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024320  nop
0x180024321  jmp     short loc_180024370
0x180024323  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180024328  mov     edi, eax
0x18002432a  test    eax, eax
0x18002432c  jns     short loc_1800242C0
0x18002432e  mov     rcx, [rbp+28h]; this
0x180024332  mov     r9d, eax; char *
0x180024335  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002433c  mov     edx, 62Bh; void *
0x180024341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024346  nop
0x180024347  mov     rax, [rbx]
0x18002434a  mov     rcx, rbx
0x18002434d  mov     rax, [rax+10h]
0x180024351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024356  nop
0x180024357  mov     rcx, [rbp+28h]; this
0x18002435b  mov     r9d, edi; char *
0x18002435e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024365  mov     edx, 648h; void *
0x18002436a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002436f  nop
0x180024370  mov     eax, edi
0x180024372  jmp     loc_18002446E
0x180024377  mov     rax, [rbx+38h]
0x18002437b  mov     [rbp+pHandles], rax
0x18002437f  mov     [rbp+dwindex], 0
0x180024386  lea     rax, [rbp+dwindex]
0x18002438a  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18002438f  lea     r9, [rbp+pHandles]; pHandles
0x180024393  mov     r8d, 1; cHandles
0x180024399  or      edx, 0FFFFFFFFh; dwTimeout
0x18002439c  lea     ecx, [r8+7]; dwFlags
0x1800243a0  call    cs:__imp_CoWaitForMultipleHandles
0x1800243a6  mov     edi, eax
0x1800243a8  test    eax, eax
0x1800243aa  jns     short loc_1800243D7
0x1800243ac  mov     rcx, [rbp+28h]; this
0x1800243b0  mov     r9d, eax; char *
0x1800243b3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800243ba  mov     edx, 655h; void *
0x1800243bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800243c4  nop
0x1800243c5  mov     rcx, [rbx]
0x1800243c8  mov     rax, [rcx+10h]
0x1800243cc  mov     rcx, rbx
0x1800243cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243d4  nop
0x1800243d5  jmp     short loc_180024370
0x1800243d7  mov     eax, [rbx+30h]
0x1800243da  cmp     eax, 1
0x1800243dd  jz      short loc_18002445C
0x1800243df  mov     [rbp+arg_18], 0
0x1800243e7  mov     rax, [r14]
0x1800243ea  lea     r8, [rbp+arg_18]
0x1800243ee  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800243f5  mov     rcx, r14
0x1800243f8  mov     rax, [rax]
0x1800243fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024400  mov     edi, eax
0x180024402  test    eax, eax
0x180024404  js      short loc_180024429
0x180024406  mov     [rbp+arg_10], 8000FFFFh
0x18002440d  mov     rcx, [rbp+arg_18]
0x180024411  mov     rax, [rcx]
0x180024414  lea     rdx, [rbp+arg_10]
0x180024418  mov     rax, [rax+40h]
0x18002441c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024421  mov     edi, eax
0x180024423  test    eax, eax
0x180024425  cmovns  edi, [rbp+arg_10]
0x180024429  mov     rcx, [rbp+arg_18]
0x18002442d  test    rcx, rcx
0x180024430  jz      short loc_180024447
0x180024432  mov     [rbp+arg_18], 0
0x18002443a  mov     rax, [rcx]
0x18002443d  mov     rax, [rax+10h]
0x180024441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024446  nop
0x180024447  mov     rax, [rbx]
0x18002444a  mov     rcx, rbx
0x18002444d  mov     rax, [rax+10h]
0x180024451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024456  nop
0x180024457  jmp     loc_180024370
0x18002445c  mov     rax, [rbx]
0x18002445f  mov     rcx, rbx
0x180024462  mov     rax, [rax+10h]
0x180024466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002446b  nop
0x18002446c  xor     eax, eax
0x18002446e  mov     rbx, [rsp+40h+arg_0]
0x180024473  add     rsp, 40h
0x180024477  pop     r15
0x180024479  pop     r14
0x18002447b  pop     rdi
0x18002447c  pop     rsi
0x18002447d  pop     rbp
0x18002447e  retn
0x18002447f  mov     edx, 0A0Bh; void *
0x180024484  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
