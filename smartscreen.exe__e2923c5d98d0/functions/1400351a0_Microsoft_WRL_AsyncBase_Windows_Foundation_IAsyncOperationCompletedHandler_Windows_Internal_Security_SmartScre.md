# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)

- ea: `0x1400351a0`
- end: `0x14003522a`
- name: `?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z`
- size: `138`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000ee74`
- `0x14000f030`
- `0x140010d20`
- `0x14001dbe0`
- `0x140034550`
- `0x140035398`
- `0x140037e34`
- `0x14003e1e0`

## callees

- `0x140005e4c`
- `0x14000f1f0`
- `0x1400351a0`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x1400351c5`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x1400351c5`

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
0x1400351a0  mov     [rsp+arg_0], rbx
0x1400351a5  push    rdi
0x1400351a6  sub     rsp, 50h
0x1400351aa  xor     bl, bl
0x1400351ac  mov     rdi, rcx
0x1400351af  xor     eax, eax
0x1400351b1  lock cmpxchg [rcx+3Ch], edx
0x1400351b6  jnz     short loc_14003521D
0x1400351b8  add     rcx, 30h ; '0'
0x1400351bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400351c1  lea     rcx, [rdi+30h]
0x1400351c5  call    cs:__imp_GetRestrictedErrorInfo
0x1400351cb  mov     edx, 3
0x1400351d0  mov     rcx, rdi
0x1400351d3  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1400351d8  mov     bl, al
0x1400351da  test    al, al
0x1400351dc  jz      short loc_14003521D
0x1400351de  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1400351e5  test    rcx, rcx
0x1400351e8  jz      short loc_14003521D
0x1400351ea  mov     rdx, [rcx]
0x1400351ed  lea     r9, [rsp+58h+var_18]
0x1400351f2  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1400351f9  mov     [rsp+58h+var_30], 4
0x140035201  mov     [rsp+58h+var_38], rdi
0x140035206  mov     rax, [rdx+40h]
0x14003520a  mov     edx, 2
0x14003520f  mov     r8d, edx
0x140035212  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x140035218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003521d  mov     al, bl
0x14003521f  mov     rbx, [rsp+58h+arg_0]
0x140035224  add     rsp, 50h
0x140035228  pop     rdi
0x140035229  retn
```
