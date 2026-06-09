# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(void)

- ea: `0x14000a510`
- end: `0x14000a58f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@_N@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `127`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001cca0`
- `0x140036060`
- `0x140036070`
- `0x140036090`
- `0x1400360b0`
- `0x1400360d0`
- `0x1400360f0`
- `0x140036110`

## callees

- `0x14000a510`
- `0x14000a950`
- `0x14006a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<bool>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  __int64 v3; // r9
  unsigned int v4; // ebx
  signed __int64 v5; // rtt

  v2 = *(_QWORD *)(a1 + 224);
  v3 = a1;
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v4 = v2 - 1;
    v5 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 224), v2 - 1, v2);
    if ( v5 == v2 )
      goto LABEL_5;
  }
  v4 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
LABEL_5:
  if ( !v4 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 88LL))(v3, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v4;
}

```

## disassembly

```asm
0x14000a510  push    rbx
0x14000a512  sub     rsp, 20h
0x14000a516  mov     rax, [rcx+0E0h]
0x14000a51d  mov     r9, rcx
0x14000a520  test    rax, rax
0x14000a523  js      short loc_14000A57E
0x14000a525  cmp     eax, 7FFFFFFFh
0x14000a52a  jz      short loc_14000A577
0x14000a52c  lea     rbx, [rax-1]
0x14000a530  lock cmpxchg [rcx+0E0h], rbx
0x14000a539  jnz     short loc_14000A520
0x14000a53b  test    ebx, ebx
0x14000a53d  jnz     short loc_14000A56E
0x14000a53f  test    r9, r9
0x14000a542  jz      short loc_14000A556
0x14000a544  mov     rdx, [r9]
0x14000a547  mov     rcx, r9
0x14000a54a  mov     rax, [rdx+58h]
0x14000a54e  lea     edx, [rbx+1]
0x14000a551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a556  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000a55d  test    rcx, rcx
0x14000a560  jz      short loc_14000A56E
0x14000a562  mov     rax, [rcx]
0x14000a565  mov     rax, [rax+10h]
0x14000a569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a56e  mov     eax, ebx
0x14000a570  add     rsp, 20h
0x14000a574  pop     rbx
0x14000a575  retn
0x14000a577  mov     ebx, 7FFFFFFEh
0x14000a57c  jmp     short loc_14000A56E
0x14000a57e  lea     rcx, ds:10h[rax*2]; this
0x14000a586  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x14000a58b  mov     ebx, eax
0x14000a58d  jmp     short loc_14000A53B
```
