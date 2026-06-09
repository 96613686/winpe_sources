# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)

- ea: `0x1400366d8`
- end: `0x140036769`
- name: `?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z`
- size: `145`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000f6b4`
- `0x14000f870`
- `0x140011630`
- `0x14001ec58`
- `0x140035a60`
- `0x1400368e4`
- `0x1400393b8`
- `0x14003f900`

## callees

- `0x1400061cc`
- `0x14000fa34`
- `0x1400366d8`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x1400366fd`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x1400366fd`

## pseudocode

```c
bool __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        __int64 a1,
        signed __int32 a2)
{
  bool v2; // bl
  void (__fastcall *v4)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int); // rax
  GUID v6; // [rsp+40h] [rbp-18h] BYREF

  v2 = 0;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 60), a2, 0) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)(a1 + 48));
    GetRestrictedErrorInfo(a1 + 48);
    v2 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
           a1,
           3);
    if ( v2 )
    {
      if ( Microsoft::WRL::gCausality )
      {
        v4 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 64LL);
        v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        v4(Microsoft::WRL::gCausality, 2, 2, &v6, a1, 4);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400366d8  mov     [rsp+arg_0], rbx
0x1400366dd  push    rdi
0x1400366de  sub     rsp, 50h
0x1400366e2  xor     bl, bl
0x1400366e4  mov     rdi, rcx
0x1400366e7  xor     eax, eax
0x1400366e9  lock cmpxchg [rcx+3Ch], edx
0x1400366ee  jnz     short loc_14003675B
0x1400366f0  add     rcx, 30h ; '0'
0x1400366f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400366f9  lea     rcx, [rdi+30h]
0x1400366fd  call    cs:__imp_GetRestrictedErrorInfo
0x140036704  nop     dword ptr [rax+rax+00h]
0x140036709  mov     edx, 3
0x14003670e  mov     rcx, rdi
0x140036711  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x140036716  mov     bl, al
0x140036718  test    al, al
0x14003671a  jz      short loc_14003675B
0x14003671c  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140036723  test    rcx, rcx
0x140036726  jz      short loc_14003675B
0x140036728  mov     rdx, [rcx]
0x14003672b  lea     r9, [rsp+58h+var_18]
0x140036730  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x140036737  mov     [rsp+58h+var_30], 4
0x14003673f  mov     [rsp+58h+var_38], rdi
0x140036744  mov     rax, [rdx+40h]
0x140036748  mov     edx, 2
0x14003674d  mov     r8d, edx
0x140036750  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x140036756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003675b  mov     al, bl
0x14003675d  mov     rbx, [rsp+58h+arg_0]
0x140036762  add     rsp, 50h
0x140036766  pop     rdi
0x140036767  retn
```
