# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)

- ea: `0x1800a02e8`
- end: `0x1800a0432`
- name: `?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z`
- size: `330`
- prototype: `void __high(HSTRING, struct Windows::Internal::ApplicationModel::WindowManagement::WindowId, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800a0f78`

## callees

- `0x180002dbc`
- `0x180036998`
- `0x180044aa4`
- `0x18004cb8c`
- `0x180083924`
- `0x1800875c4`
- `0x18009f498`
- `0x1800a02e8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800a0341`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800a0341`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a03a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a03a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0398`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0398`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
        __int64 a1,
        HSTRING a2,
        int a3,
        __int64 a4)
{
  __int64 v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // ecx
  DWORD v15; // [rsp+50h] [rbp-28h] BYREF
  __int64 v16; // [rsp+58h] [rbp-20h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-18h] BYREF
  __int64 v18; // [rsp+68h] [rbp-10h] BYREF
  int v19; // [rsp+B0h] [rbp+38h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v19);
  v8 = *(_QWORD *)(a1 + 272);
  v9 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  else
    *(_OWORD *)(v8 + 8) = 0;
  *(_DWORD *)v8 = 1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v19);
  v10 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v11 = (int)v10;
  if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL) )
  {
    v16 = a4;
    v19 = a3;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v13 = *(_QWORD *)(a1 + 272);
    v15 = CurrentThreadId;
    v18 = 0;
    if ( !*(_BYTE *)(v13 + 4) || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
      v14 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v11,
      (unsigned int)byte_180120F71,
      v13 + 8,
      v14,
      (__int64)&v18,
      (__int64)&v15,
      (__int64)&StringRawBuffer,
      (__int64)&v19,
      (__int64)&v16);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x1800a02e8  push    rbp
0x1800a02ea  push    rbx
0x1800a02eb  push    rsi
0x1800a02ec  push    rdi
0x1800a02ed  push    r14
0x1800a02ef  push    r15
0x1800a02f1  mov     rbp, rsp
0x1800a02f4  sub     rsp, 78h
0x1800a02f8  mov     r15, rdx
0x1800a02fb  mov     r14, r9
0x1800a02fe  lea     rdx, [rbp+arg_0]
0x1800a0302  mov     ebx, r8d
0x1800a0305  mov     rsi, rcx
0x1800a0308  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800a030d  mov     rdi, [rsi+110h]
0x1800a0314  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1800a0319  mov     r8d, [rax]
0x1800a031c  cmp     r8d, 5
0x1800a0320  jbe     short loc_1800A0349
0x1800a0322  mov     rdx, 400000000000h
0x1800a032c  mov     rcx, rax
0x1800a032f  call    _tlgKeywordOn
0x1800a0334  test    al, al
0x1800a0336  jz      short loc_1800A0349
0x1800a0338  lea     rdx, [rdi+8]; ActivityId
0x1800a033c  mov     ecx, 3; ControlCode
0x1800a0341  call    cs:__imp_EventActivityIdControl
0x1800a0347  jmp     short loc_1800A0350
0x1800a0349  xorps   xmm0, xmm0
0x1800a034c  movups  xmmword ptr [rdi+8], xmm0
0x1800a0350  lea     rcx, [rbp+arg_0]
0x1800a0354  mov     dword ptr [rdi], 1
0x1800a035a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800a035f  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1800a0364  mov     rdi, rax
0x1800a0367  mov     ecx, [rax]
0x1800a0369  cmp     ecx, 5
0x1800a036c  jbe     loc_1800A0413
0x1800a0372  mov     rdx, 400000000000h
0x1800a037c  mov     rcx, rax
0x1800a037f  call    _tlgKeywordOn
0x1800a0384  test    al, al
0x1800a0386  jz      loc_1800A0413
0x1800a038c  xor     edx, edx; length
0x1800a038e  mov     [rbp+var_20], r14
0x1800a0392  mov     rcx, r15; string
0x1800a0395  mov     [rbp+arg_0], ebx
0x1800a0398  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a039e  mov     [rbp+var_18], rax
0x1800a03a2  call    cs:__imp_GetCurrentThreadId
0x1800a03a8  mov     r8, [rsi+110h]
0x1800a03af  mov     [rbp+var_28], eax
0x1800a03b2  mov     [rbp+var_10], 0
0x1800a03ba  cmp     byte ptr [r8+4], 0
0x1800a03bf  jz      short loc_1800A03CE
0x1800a03c1  lea     rcx, [r8+18h]; struct _GUID *
0x1800a03c5  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800a03ca  test    al, al
0x1800a03cc  jz      short loc_1800A03D0
0x1800a03ce  xor     ecx, ecx
0x1800a03d0  lea     rax, [rbp+var_20]
0x1800a03d4  mov     r9, rcx
0x1800a03d7  mov     [rsp+78h+var_38], rax
0x1800a03dc  lea     rdx, byte_180120F71
0x1800a03e3  lea     rax, [rbp+arg_0]
0x1800a03e7  add     r8, 8
0x1800a03eb  mov     [rsp+78h+var_40], rax
0x1800a03f0  mov     rcx, rdi
0x1800a03f3  lea     rax, [rbp+var_18]
0x1800a03f7  mov     [rsp+78h+var_48], rax
0x1800a03fc  lea     rax, [rbp+var_28]
0x1800a0400  mov     [rsp+78h+var_50], rax
0x1800a0405  lea     rax, [rbp+var_10]
0x1800a0409  mov     [rsp+78h+var_58], rax
0x1800a040e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800a0413  lea     rcx, [rsi+120h]; this
0x1800a041a  cmp     dword ptr [rcx+18h], 0
0x1800a041e  jnz     short loc_1800A0425
0x1800a0420  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800a0425  add     rsp, 78h
0x1800a0429  pop     r15
0x1800a042b  pop     r14
0x1800a042d  pop     rdi
0x1800a042e  pop     rsi
0x1800a042f  pop     rbx
0x1800a0430  pop     rbp
0x1800a0431  retn
```
