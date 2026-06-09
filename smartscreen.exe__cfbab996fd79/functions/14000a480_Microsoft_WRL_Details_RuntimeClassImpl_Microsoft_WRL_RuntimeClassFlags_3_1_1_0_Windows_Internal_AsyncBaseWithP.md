# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(void)

- ea: `0x14000a480`
- end: `0x14000a503`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `131`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001db70`
- `0x140040600`
- `0x140040610`
- `0x140040630`
- `0x140040650`
- `0x140040670`
- `0x140040690`
- `0x1400406b0`

## callees

- `0x14000a480`
- `0x14000a950`
- `0x14006a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(
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
0x14000a480  push    rbx
0x14000a482  sub     rsp, 20h
0x14000a486  mov     rax, [rcx+0E0h]
0x14000a48d  mov     r9, rcx
0x14000a490  test    rax, rax
0x14000a493  js      short loc_14000A4F2
0x14000a495  cmp     eax, 7FFFFFFFh
0x14000a49a  jz      short loc_14000A4CE
0x14000a49c  lea     rbx, [rax-1]
0x14000a4a0  lock cmpxchg [rcx+0E0h], rbx
0x14000a4a9  jnz     short loc_14000A490
0x14000a4ab  test    ebx, ebx
0x14000a4ad  jnz     short loc_14000A4D3
0x14000a4af  test    r9, r9
0x14000a4b2  jnz     short loc_14000A4DC
0x14000a4b4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000a4bb  test    rcx, rcx
0x14000a4be  jz      short loc_14000A4D3
0x14000a4c0  mov     rax, [rcx]
0x14000a4c3  mov     rax, [rax+10h]
0x14000a4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4cc  jmp     short loc_14000A4D3
0x14000a4ce  mov     ebx, 7FFFFFFEh
0x14000a4d3  mov     eax, ebx
0x14000a4d5  add     rsp, 20h
0x14000a4d9  pop     rbx
0x14000a4da  retn
0x14000a4dc  mov     rdx, [r9]
0x14000a4df  mov     rcx, r9
0x14000a4e2  mov     rax, [rdx+58h]
0x14000a4e6  mov     edx, 1
0x14000a4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4f0  jmp     short loc_14000A4B4
0x14000a4f2  lea     rcx, ds:10h[rax*2]; this
0x14000a4fa  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x14000a4ff  mov     ebx, eax
0x14000a501  jmp     short loc_14000A4AB
```
