# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180024490`
- end: `0x180024766`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `726`
- prototype: `__int64(__int64, DWORD, int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025930`

## callees

- `0x18000299c`
- `0x1800067c8`
- `0x180008934`
- `0x18000a21c`
- `0x180024490`
- `0x18002476c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024550`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024592`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024592`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002457d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002457d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002467c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002467c`

## string_xrefs

- `0x1800245db`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x180024611`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x18002463a`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x18002468f`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::Devices::Radios::RadioAccessStatus> *>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::Devices::Radios::RadioAccessStatus> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180024490  mov     rax, rsp
0x180024493  mov     [rax+8], rbx
0x180024497  mov     [rax+20h], r9
0x18002449b  mov     [rax+18h], r8d
0x18002449f  mov     [rax+10h], edx
0x1800244a2  push    rbp
0x1800244a3  push    rsi
0x1800244a4  push    rdi
0x1800244a5  push    r14
0x1800244a7  push    r15
0x1800244a9  mov     rbp, rsp
0x1800244ac  sub     rsp, 40h
0x1800244b0  mov     r14, rcx
0x1800244b3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800244ba  mov     ecx, 40h ; '@'; unsigned __int64
0x1800244bf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800244c4  mov     rbx, rax
0x1800244c7  test    rax, rax
0x1800244ca  jnz     short loc_1800244D6
0x1800244cc  mov     edi, 8007000Eh
0x1800244d1  jmp     loc_180024633
0x1800244d6  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x1800244dd  mov     [rbx], rax
0x1800244e0  lea     rdi, [rbx+8]
0x1800244e4  mov     rcx, rdi
0x1800244e7  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x1800244ec  mov     dword ptr [rbx+2Ch], 1
0x1800244f3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>'}
0x1800244fa  mov     [rbx], rax
0x1800244fd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180024504  mov     [rdi], rax
0x180024507  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002450e  test    rcx, rcx
0x180024511  jz      short loc_180024520
0x180024513  mov     rax, [rcx]
0x180024516  mov     rax, [rax+8]
0x18002451a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002451f  nop
0x180024520  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>'}
0x180024527  mov     [rbx], rax
0x18002452a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180024531  mov     [rdi], rax
0x180024534  mov     dword ptr [rbx+30h], 0
0x18002453b  mov     qword ptr [rbx+38h], 0
0x180024543  mov     r9d, 1F0003h; dwDesiredAccess
0x180024549  xor     r8d, r8d; dwFlags
0x18002454c  xor     edx, edx; lpName
0x18002454e  xor     ecx, ecx; lpEventAttributes
0x180024550  call    cs:__imp_CreateEventExW
0x180024556  mov     rsi, rax
0x180024559  test    rax, rax
0x18002455c  jz      loc_1800245FF
0x180024562  call    cs:__imp_GetLastError
0x180024568  mov     rdi, [rbx+38h]
0x18002456c  test    rdi, rdi
0x18002456f  jz      short loc_180024598
0x180024571  call    cs:__imp_GetLastError
0x180024577  mov     r15d, eax
0x18002457a  mov     rcx, rdi; hObject
0x18002457d  call    cs:__imp_CloseHandle
0x180024583  mov     rcx, [rbp+28h]; this
0x180024587  test    eax, eax
0x180024589  jz      loc_18002475B
0x18002458f  mov     ecx, r15d; dwErrCode
0x180024592  call    cs:__imp_SetLastError
0x180024598  mov     [rbx+38h], rsi
0x18002459c  mov     rax, [rbx]
0x18002459f  mov     rcx, rbx
0x1800245a2  mov     rax, [rax+8]
0x1800245a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245ab  nop
0x1800245ac  mov     rax, [rbx]
0x1800245af  mov     rcx, rbx
0x1800245b2  mov     rax, [rax+10h]
0x1800245b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245bb  nop
0x1800245bc  mov     rax, [r14]
0x1800245bf  mov     rdx, rbx
0x1800245c2  mov     rcx, r14
0x1800245c5  mov     rax, [rax+30h]
0x1800245c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245ce  mov     edi, eax
0x1800245d0  test    eax, eax
0x1800245d2  jns     short loc_180024653
0x1800245d4  mov     rcx, [rbp+28h]; this
0x1800245d8  mov     r9d, eax; char *
0x1800245db  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800245e2  mov     edx, 649h; void *
0x1800245e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800245ec  nop
0x1800245ed  mov     rcx, [rbx]
0x1800245f0  mov     rax, [rcx+10h]
0x1800245f4  mov     rcx, rbx
0x1800245f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245fc  nop
0x1800245fd  jmp     short loc_18002464C
0x1800245ff  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180024604  mov     edi, eax
0x180024606  test    eax, eax
0x180024608  jns     short loc_18002459C
0x18002460a  mov     rcx, [rbp+28h]; this
0x18002460e  mov     r9d, eax; char *
0x180024611  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024618  mov     edx, 62Bh; void *
0x18002461d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024622  nop
0x180024623  mov     rax, [rbx]
0x180024626  mov     rcx, rbx
0x180024629  mov     rax, [rax+10h]
0x18002462d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024632  nop
0x180024633  mov     rcx, [rbp+28h]; this
0x180024637  mov     r9d, edi; char *
0x18002463a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024641  mov     edx, 648h; void *
0x180024646  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002464b  nop
0x18002464c  mov     eax, edi
0x18002464e  jmp     loc_18002474A
0x180024653  mov     rax, [rbx+38h]
0x180024657  mov     [rbp+pHandles], rax
0x18002465b  mov     [rbp+dwindex], 0
0x180024662  lea     rax, [rbp+dwindex]
0x180024666  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18002466b  lea     r9, [rbp+pHandles]; pHandles
0x18002466f  mov     r8d, 1; cHandles
0x180024675  or      edx, 0FFFFFFFFh; dwTimeout
0x180024678  lea     ecx, [r8+7]; dwFlags
0x18002467c  call    cs:__imp_CoWaitForMultipleHandles
0x180024682  mov     edi, eax
0x180024684  test    eax, eax
0x180024686  jns     short loc_1800246B3
0x180024688  mov     rcx, [rbp+28h]; this
0x18002468c  mov     r9d, eax; char *
0x18002468f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024696  mov     edx, 655h; void *
0x18002469b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246a0  nop
0x1800246a1  mov     rcx, [rbx]
0x1800246a4  mov     rax, [rcx+10h]
0x1800246a8  mov     rcx, rbx
0x1800246ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246b0  nop
0x1800246b1  jmp     short loc_18002464C
0x1800246b3  mov     eax, [rbx+30h]
0x1800246b6  cmp     eax, 1
0x1800246b9  jz      short loc_180024738
0x1800246bb  mov     [rbp+arg_18], 0
0x1800246c3  mov     rax, [r14]
0x1800246c6  lea     r8, [rbp+arg_18]
0x1800246ca  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800246d1  mov     rcx, r14
0x1800246d4  mov     rax, [rax]
0x1800246d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246dc  mov     edi, eax
0x1800246de  test    eax, eax
0x1800246e0  js      short loc_180024705
0x1800246e2  mov     [rbp+arg_10], 8000FFFFh
0x1800246e9  mov     rcx, [rbp+arg_18]
0x1800246ed  mov     rax, [rcx]
0x1800246f0  lea     rdx, [rbp+arg_10]
0x1800246f4  mov     rax, [rax+40h]
0x1800246f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246fd  mov     edi, eax
0x1800246ff  test    eax, eax
0x180024701  cmovns  edi, [rbp+arg_10]
0x180024705  mov     rcx, [rbp+arg_18]
0x180024709  test    rcx, rcx
0x18002470c  jz      short loc_180024723
0x18002470e  mov     [rbp+arg_18], 0
0x180024716  mov     rax, [rcx]
0x180024719  mov     rax, [rax+10h]
0x18002471d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024722  nop
0x180024723  mov     rax, [rbx]
0x180024726  mov     rcx, rbx
0x180024729  mov     rax, [rax+10h]
0x18002472d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024732  nop
0x180024733  jmp     loc_18002464C
0x180024738  mov     rax, [rbx]
0x18002473b  mov     rcx, rbx
0x18002473e  mov     rax, [rax+10h]
0x180024742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024747  nop
0x180024748  xor     eax, eax
0x18002474a  mov     rbx, [rsp+40h+arg_0]
0x18002474f  add     rsp, 40h
0x180024753  pop     r15
0x180024755  pop     r14
0x180024757  pop     rdi
0x180024758  pop     rsi
0x180024759  pop     rbp
0x18002475a  retn
0x18002475b  mov     edx, 0A0Bh; void *
0x180024760  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
