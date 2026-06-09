# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncAction,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(void)

- ea: `0x14000a3f0`
- end: `0x14000a471`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UIAsyncAction@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001e330`
- `0x1400391f0`
- `0x140039200`
- `0x140039220`
- `0x140039240`
- `0x140039260`
- `0x140039280`
- `0x1400392a0`

## callees

- `0x14000a3f0`
- `0x14000a950`
- `0x14006a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncAction,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(
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
0x14000a3f0  push    rbx
0x14000a3f2  sub     rsp, 20h
0x14000a3f6  mov     rax, [rcx+0E0h]
0x14000a3fd  mov     r9, rcx
0x14000a400  test    rax, rax
0x14000a403  js      short loc_14000A460
0x14000a405  cmp     eax, 7FFFFFFFh
0x14000a40a  jz      short loc_14000A459
0x14000a40c  lea     rbx, [rax-1]
0x14000a410  lock cmpxchg [rcx+0E0h], rbx
0x14000a419  jnz     short loc_14000A400
0x14000a41b  test    ebx, ebx
0x14000a41d  jnz     short loc_14000A442
0x14000a41f  test    r9, r9
0x14000a422  jz      short loc_14000A436
0x14000a424  mov     rdx, [r9]
0x14000a427  mov     rcx, r9
0x14000a42a  mov     rax, [rdx+58h]
0x14000a42e  lea     edx, [rbx+1]
0x14000a431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a436  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000a43d  test    rcx, rcx
0x14000a440  jnz     short loc_14000A44B
0x14000a442  mov     eax, ebx
0x14000a444  add     rsp, 20h
0x14000a448  pop     rbx
0x14000a449  retn
0x14000a44b  mov     rax, [rcx]
0x14000a44e  mov     rax, [rax+10h]
0x14000a452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a457  jmp     short loc_14000A442
0x14000a459  mov     ebx, 7FFFFFFEh
0x14000a45e  jmp     short loc_14000A442
0x14000a460  lea     rcx, ds:10h[rax*2]; this
0x14000a468  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x14000a46d  mov     ebx, eax
0x14000a46f  jmp     short loc_14000A41B
```
