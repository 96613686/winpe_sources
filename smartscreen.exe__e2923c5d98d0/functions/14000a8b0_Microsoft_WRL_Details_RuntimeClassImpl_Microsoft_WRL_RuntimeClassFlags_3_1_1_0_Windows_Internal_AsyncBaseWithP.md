# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncAction,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(void)

- ea: `0x14000a8b0`
- end: `0x14000a930`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UIAsyncAction@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `128`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001d2b0`
- `0x140037c70`
- `0x140037c80`
- `0x140037ca0`
- `0x140037cc0`
- `0x140037ce0`
- `0x140037d00`
- `0x140037d20`

## callees

- `0x14000a8b0`
- `0x14000ae00`
- `0x140068010`

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
0x14000a8b0  push    rbx
0x14000a8b2  sub     rsp, 20h
0x14000a8b6  mov     rax, [rcx+0E0h]
0x14000a8bd  mov     r9, rcx
0x14000a8c0  test    rax, rax
0x14000a8c3  js      short loc_14000A91F
0x14000a8c5  cmp     eax, 7FFFFFFFh
0x14000a8ca  jz      short loc_14000A918
0x14000a8cc  lea     rbx, [rax-1]
0x14000a8d0  lock cmpxchg [rcx+0E0h], rbx
0x14000a8d9  jnz     short loc_14000A8C0
0x14000a8db  test    ebx, ebx
0x14000a8dd  jnz     short loc_14000A902
0x14000a8df  test    r9, r9
0x14000a8e2  jz      short loc_14000A8F6
0x14000a8e4  mov     rdx, [r9]
0x14000a8e7  mov     rcx, r9
0x14000a8ea  mov     rax, [rdx+58h]
0x14000a8ee  lea     edx, [rbx+1]
0x14000a8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8f6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000a8fd  test    rcx, rcx
0x14000a900  jnz     short loc_14000A90A
0x14000a902  mov     eax, ebx
0x14000a904  add     rsp, 20h
0x14000a908  pop     rbx
0x14000a909  retn
0x14000a90a  mov     rax, [rcx]
0x14000a90d  mov     rax, [rax+10h]
0x14000a911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a916  jmp     short loc_14000A902
0x14000a918  mov     ebx, 7FFFFFFEh
0x14000a91d  jmp     short loc_14000A902
0x14000a91f  lea     rcx, ds:10h[rax*2]; this
0x14000a927  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x14000a92c  mov     ebx, eax
0x14000a92e  jmp     short loc_14000A8DB
```
