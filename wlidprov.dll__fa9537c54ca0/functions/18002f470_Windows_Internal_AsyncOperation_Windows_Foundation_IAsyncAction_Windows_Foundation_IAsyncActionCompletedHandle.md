# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::DisableCausality>::_AfterComplete(void)

- ea: `0x18002f470`
- end: `0x18002f4d4`
- name: `?_AfterComplete@?$AsyncOperation@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@VCNoResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@UDisableCausality@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f4dc`
- `0x18002f760`

## callees

- `0x18002a090`
- `0x18002f470`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f4aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f4aa`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18002f4b4`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18002f4b4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::DisableCausality>::_AfterComplete(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // ebx

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = *(_DWORD *)(a1 + 320);
  *(_QWORD *)(a1 + 264) = 0;
  if ( GetCurrentThreadId() != v3 )
    SHTaskPoolAllowThreadReuse();
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
  return Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::DisableCausality>::FireCompletion(a1 + 8);
}

```

## disassembly

```asm
0x18002f470  mov     [rsp+arg_0], rbx
0x18002f475  push    rdi
0x18002f476  sub     rsp, 20h
0x18002f47a  mov     rdi, rcx
0x18002f47d  mov     rcx, [rcx+108h]
0x18002f484  test    rcx, rcx
0x18002f487  jz      short loc_18002F499
0x18002f489  mov     rax, [rcx]
0x18002f48c  mov     edx, 1
0x18002f491  mov     rax, [rax]
0x18002f494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f499  mov     ebx, [rdi+140h]
0x18002f49f  mov     qword ptr [rdi+108h], 0
0x18002f4aa  call    cs:__imp_GetCurrentThreadId
0x18002f4b0  cmp     eax, ebx
0x18002f4b2  jz      short loc_18002F4BA
0x18002f4b4  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x18002f4ba  lock inc dword ptr [rdi+110h]
0x18002f4c1  lea     rcx, [rdi+8]
0x18002f4c5  mov     rbx, [rsp+28h+arg_0]
0x18002f4ca  add     rsp, 20h
0x18002f4ce  pop     rdi
0x18002f4cf  jmp     ?FireCompletion@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::DisableCausality>::FireCompletion(void)
```
