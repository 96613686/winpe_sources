# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,CStorageItemResult<Windows::Storage::IStorageFile>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)

- ea: `0x180019424`
- end: `0x18001949a`
- name: `?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@23@V?$CStorageItemResult@UIStorageFile@Storage@Windows@@@@VComTaskPoolHandler@Internal@3@UINilDelegate@73@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180015238`
- `0x180022974`

## callees

- `0x180019424`
- `0x180022a50`
- `0x18005a0f4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001945e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001945e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180019468`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180019468`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,CStorageItemResult<Windows::Storage::IStorageFile>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // ebx

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = *(_DWORD *)(a1 + 408);
  *(_QWORD *)(a1 + 264) = 0;
  if ( GetCurrentThreadId() != v3 )
    SHTaskPoolAllowThreadReuse();
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
  if ( *(int *)(a1 + 168) > 0 )
    Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::DataTransfer::ShareProvider *> *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1 + 8);
  return Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(a1 + 8);
}

```

## disassembly

```asm
0x180019424  mov     [rsp+arg_0], rbx
0x180019429  push    rdi
0x18001942a  sub     rsp, 20h
0x18001942e  mov     rdi, rcx
0x180019431  mov     rcx, [rcx+108h]
0x180019438  test    rcx, rcx
0x18001943b  jz      short loc_18001944D
0x18001943d  mov     rax, [rcx]
0x180019440  mov     edx, 1
0x180019445  mov     rax, [rax]
0x180019448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001944d  mov     ebx, [rdi+198h]
0x180019453  mov     qword ptr [rdi+108h], 0
0x18001945e  call    cs:__imp_GetCurrentThreadId
0x180019464  cmp     eax, ebx
0x180019466  jz      short loc_18001946E
0x180019468  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x18001946e  lock inc dword ptr [rdi+110h]
0x180019475  cmp     dword ptr [rdi+0A8h], 0
0x18001947c  jle     short loc_180019487
0x18001947e  lea     rcx, [rdi+8]
0x180019482  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVShareProvider@DataTransfer@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::DataTransfer::ShareProvider *> *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x180019487  lea     rcx, [rdi+8]
0x18001948b  mov     rbx, [rsp+28h+arg_0]
0x180019490  add     rsp, 20h
0x180019494  pop     rdi
0x180019495  jmp     ?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
