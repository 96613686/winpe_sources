# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)

- ea: `0x1800a0438`
- end: `0x1800a055a`
- name: `?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z`
- size: `290`
- prototype: `void(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800a1348`

## callees

- `0x180002cf8`
- `0x180036998`
- `0x180044aa4`
- `0x18004cb8c`
- `0x180083924`
- `0x1800875c4`
- `0x18009f498`
- `0x1800a0438`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800a0484`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800a0484`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a04dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a04dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a04d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a04d1`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        HSTRING a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // ecx
  DWORD v11; // [rsp+60h] [rbp+8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v11);
  v4 = *((_QWORD *)this + 34);
  v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v11);
  v6 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v7 = (int)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v11 = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v7,
      (unsigned int)&unk_180120C58,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&v11,
      (__int64)&StringRawBuffer);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800a0438  push    rbx
0x1800a043a  push    rsi
0x1800a043b  push    rdi
0x1800a043c  sub     rsp, 40h
0x1800a0440  mov     rsi, rdx
0x1800a0443  mov     rdi, rcx
0x1800a0446  lea     rdx, [rsp+58h+arg_0]
0x1800a044b  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800a0450  mov     rbx, [rdi+110h]
0x1800a0457  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1800a045c  mov     r8d, [rax]
0x1800a045f  cmp     r8d, 5
0x1800a0463  jbe     short loc_1800A048C
0x1800a0465  mov     rdx, 200000000000h
0x1800a046f  mov     rcx, rax
0x1800a0472  call    _tlgKeywordOn
0x1800a0477  test    al, al
0x1800a0479  jz      short loc_1800A048C
0x1800a047b  lea     rdx, [rbx+8]; ActivityId
0x1800a047f  mov     ecx, 3; ControlCode
0x1800a0484  call    cs:__imp_EventActivityIdControl
0x1800a048a  jmp     short loc_1800A0493
0x1800a048c  xorps   xmm0, xmm0
0x1800a048f  movups  xmmword ptr [rbx+8], xmm0
0x1800a0493  lea     rcx, [rsp+58h+arg_0]
0x1800a0498  mov     dword ptr [rbx], 1
0x1800a049e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800a04a3  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1800a04a8  mov     rbx, rax
0x1800a04ab  mov     ecx, [rax]
0x1800a04ad  cmp     ecx, 5
0x1800a04b0  jbe     loc_1800A0540
0x1800a04b6  mov     rdx, 200000000000h
0x1800a04c0  mov     rcx, rax
0x1800a04c3  call    _tlgKeywordOn
0x1800a04c8  test    al, al
0x1800a04ca  jz      short loc_1800A0540
0x1800a04cc  xor     edx, edx; length
0x1800a04ce  mov     rcx, rsi; string
0x1800a04d1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a04d7  mov     [rsp+58h+arg_10], rax
0x1800a04dc  call    cs:__imp_GetCurrentThreadId
0x1800a04e2  mov     r8, [rdi+110h]
0x1800a04e9  mov     [rsp+58h+arg_0], eax
0x1800a04ed  mov     [rsp+58h+arg_18], 0
0x1800a04f6  cmp     byte ptr [r8+4], 0
0x1800a04fb  jz      short loc_1800A050A
0x1800a04fd  lea     rcx, [r8+18h]; struct _GUID *
0x1800a0501  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800a0506  test    al, al
0x1800a0508  jz      short loc_1800A050C
0x1800a050a  xor     ecx, ecx
0x1800a050c  lea     rax, [rsp+58h+arg_10]
0x1800a0511  mov     r9, rcx
0x1800a0514  mov     [rsp+58h+var_28], rax
0x1800a0519  lea     rdx, unk_180120C58
0x1800a0520  lea     rax, [rsp+58h+arg_0]
0x1800a0525  add     r8, 8
0x1800a0529  mov     [rsp+58h+var_30], rax
0x1800a052e  mov     rcx, rbx
0x1800a0531  lea     rax, [rsp+58h+arg_18]
0x1800a0536  mov     [rsp+58h+var_38], rax
0x1800a053b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800a0540  lea     rcx, [rdi+120h]; this
0x1800a0547  cmp     dword ptr [rcx+18h], 0
0x1800a054b  jnz     short loc_1800A0552
0x1800a054d  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800a0552  add     rsp, 40h
0x1800a0556  pop     rdi
0x1800a0557  pop     rsi
0x1800a0558  pop     rbx
0x1800a0559  retn
```
