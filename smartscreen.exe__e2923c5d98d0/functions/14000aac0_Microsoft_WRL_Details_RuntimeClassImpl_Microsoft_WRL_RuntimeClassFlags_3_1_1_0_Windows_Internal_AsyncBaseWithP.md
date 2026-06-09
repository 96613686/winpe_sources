# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(void)

- ea: `0x14000aac0`
- end: `0x14000ab3c`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `124`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001bc30`
- `0x14003ee10`
- `0x14003ee20`
- `0x14003ee40`
- `0x14003ee60`
- `0x14003ee80`
- `0x14003eea0`
- `0x14003eec0`

## callees

- `0x14000aac0`
- `0x14000ae00`
- `0x140068010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  __int64 v3; // r9
  unsigned int v4; // ebx
  signed __int64 v6; // rtt

  v2 = *(_QWORD *)(a1 + 224);
  v3 = a1;
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v4 = v2 - 1;
    v6 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 224), v2 - 1, v2);
    if ( v6 == v2 )
      goto LABEL_7;
  }
  v4 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
LABEL_7:
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
0x14000aac0  push    rbx
0x14000aac2  sub     rsp, 20h
0x14000aac6  mov     rax, [rcx+0E0h]
0x14000aacd  mov     r9, rcx
0x14000aad0  test    rax, rax
0x14000aad3  js      short loc_14000AB2B
0x14000aad5  cmp     eax, 7FFFFFFFh
0x14000aada  jnz     short loc_14000AAE7
0x14000aadc  lea     ebx, [rax-1]
0x14000aadf  mov     eax, ebx
0x14000aae1  add     rsp, 20h
0x14000aae5  pop     rbx
0x14000aae6  retn
0x14000aae7  lea     rbx, [rax-1]
0x14000aaeb  lock cmpxchg [rcx+0E0h], rbx
0x14000aaf4  jnz     short loc_14000AAD0
0x14000aaf6  test    ebx, ebx
0x14000aaf8  jnz     short loc_14000AADF
0x14000aafa  test    r9, r9
0x14000aafd  jz      short loc_14000AB11
0x14000aaff  mov     rdx, [r9]
0x14000ab02  mov     rcx, r9
0x14000ab05  mov     rax, [rdx+58h]
0x14000ab09  lea     edx, [rbx+1]
0x14000ab0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab11  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000ab18  test    rcx, rcx
0x14000ab1b  jz      short loc_14000AADF
0x14000ab1d  mov     rax, [rcx]
0x14000ab20  mov     rax, [rax+10h]
0x14000ab24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab29  jmp     short loc_14000AADF
0x14000ab2b  lea     rcx, ds:10h[rax*2]; this
0x14000ab33  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x14000ab38  mov     ebx, eax
0x14000ab3a  jmp     short loc_14000AAF6
```
