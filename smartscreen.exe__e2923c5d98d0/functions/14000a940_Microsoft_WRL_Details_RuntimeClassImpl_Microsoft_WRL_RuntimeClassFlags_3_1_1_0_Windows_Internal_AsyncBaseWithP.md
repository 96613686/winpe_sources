# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(void)

- ea: `0x14000a940`
- end: `0x14000a9c2`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `130`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001cbe0`
- `0x14003eee0`
- `0x14003eef0`
- `0x14003ef10`
- `0x14003ef30`
- `0x14003ef50`
- `0x14003ef70`
- `0x14003ef90`

## callees

- `0x14000a940`
- `0x14000ae00`
- `0x140068010`

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
0x14000a940  push    rbx
0x14000a942  sub     rsp, 20h
0x14000a946  mov     rax, [rcx+0E0h]
0x14000a94d  mov     r9, rcx
0x14000a950  test    rax, rax
0x14000a953  js      short loc_14000A9B1
0x14000a955  cmp     eax, 7FFFFFFFh
0x14000a95a  jz      short loc_14000A98E
0x14000a95c  lea     rbx, [rax-1]
0x14000a960  lock cmpxchg [rcx+0E0h], rbx
0x14000a969  jnz     short loc_14000A950
0x14000a96b  test    ebx, ebx
0x14000a96d  jnz     short loc_14000A993
0x14000a96f  test    r9, r9
0x14000a972  jnz     short loc_14000A99B
0x14000a974  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000a97b  test    rcx, rcx
0x14000a97e  jz      short loc_14000A993
0x14000a980  mov     rax, [rcx]
0x14000a983  mov     rax, [rax+10h]
0x14000a987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a98c  jmp     short loc_14000A993
0x14000a98e  mov     ebx, 7FFFFFFEh
0x14000a993  mov     eax, ebx
0x14000a995  add     rsp, 20h
0x14000a999  pop     rbx
0x14000a99a  retn
0x14000a99b  mov     rdx, [r9]
0x14000a99e  mov     rcx, r9
0x14000a9a1  mov     rax, [rdx+58h]
0x14000a9a5  mov     edx, 1
0x14000a9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9af  jmp     short loc_14000A974
0x14000a9b1  lea     rcx, ds:10h[rax*2]; this
0x14000a9b9  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x14000a9be  mov     ebx, eax
0x14000a9c0  jmp     short loc_14000A96B
```
