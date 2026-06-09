# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x140011630`
- end: `0x140011707`
- name: `?OnStart@?$AsyncOperation@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@VCNoResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140011630`
- `0x14001f344`
- `0x1400366d8`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011667`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1400116ad`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1400116ad`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
        __int64 a1)
{
  unsigned int v2; // ebx
  DWORD CurrentThreadId; // eax

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 256) + 8LL))(
         *(_QWORD *)(a1 + 256),
         0,
         0,
         a1 + 280);
  if ( (v2 & 0x80000000) != 0 )
  {
LABEL_4:
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      a1,
      v2);
    return v2;
  }
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 312) = CurrentThreadId;
  v2 = SHTaskPoolQueueTask(
         *(unsigned int *)(a1 + 304),
         *(unsigned int *)(a1 + 308),
         CurrentThreadId,
         0,
         (a1 + 200) & -(__int64)(a1 != 8),
         0);
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)(a1 + 248) )
    {
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        a1,
        v2);
      return 0;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
      a1 - 8,
      1,
      v2);
    goto LABEL_4;
  }
  return v2;
}

```

## disassembly

```asm
0x140011630  mov     [rsp+arg_0], rbx
0x140011635  mov     [rsp+arg_8], rsi
0x14001163a  push    rdi
0x14001163b  sub     rsp, 30h
0x14001163f  mov     rdi, rcx
0x140011642  xor     r8d, r8d
0x140011645  mov     rcx, [rcx+100h]
0x14001164c  xor     edx, edx
0x14001164e  lea     r9, [rdi+118h]
0x140011655  mov     rax, [rcx]
0x140011658  mov     rax, [rax+8]
0x14001165c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011661  mov     ebx, eax
0x140011663  test    eax, eax
0x140011665  js      short loc_1400116D2
0x140011667  call    cs:__imp_GetCurrentThreadId
0x14001166e  nop     dword ptr [rax+rax+00h]
0x140011673  lea     rdx, [rdi+0C8h]
0x14001167a  mov     [rsp+38h+var_10], 0
0x140011683  lea     rcx, [rdi-8]
0x140011687  mov     [rdi+138h], eax
0x14001168d  neg     rcx
0x140011690  mov     ecx, [rdi+130h]
0x140011696  sbb     r8, r8
0x140011699  xor     r9d, r9d
0x14001169c  and     r8, rdx
0x14001169f  mov     edx, [rdi+134h]
0x1400116a5  mov     [rsp+38h+var_18], r8
0x1400116aa  mov     r8d, eax
0x1400116ad  call    cs:__imp_SHTaskPoolQueueTask
0x1400116b4  nop     dword ptr [rax+rax+00h]
0x1400116b9  mov     ebx, eax
0x1400116bb  test    eax, eax
0x1400116bd  js      short loc_1400116DE
0x1400116bf  mov     rsi, [rsp+38h+arg_8]
0x1400116c4  mov     eax, ebx
0x1400116c6  mov     rbx, [rsp+38h+arg_0]
0x1400116cb  add     rsp, 30h
0x1400116cf  pop     rdi
0x1400116d0  retn
0x1400116d2  mov     edx, ebx
0x1400116d4  mov     rcx, rdi
0x1400116d7  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1400116dc  jmp     short loc_1400116BF
0x1400116de  mov     eax, [rdi+0F8h]
0x1400116e4  test    eax, eax
0x1400116e6  jnz     short loc_1400116F9
0x1400116e8  mov     r8d, ebx
0x1400116eb  lea     edx, [rax+1]
0x1400116ee  lea     rcx, [rdi-8]
0x1400116f2  call    ?_Run@?$AsyncOperation@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@VCNoResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)
0x1400116f7  jmp     short loc_1400116D2
0x1400116f9  mov     edx, ebx
0x1400116fb  mov     rcx, rdi
0x1400116fe  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x140011703  xor     ebx, ebx
0x140011705  jmp     short loc_1400116BF
```
