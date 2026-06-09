# AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>(void)

- ea: `0x14001e178`
- end: `0x14001e1b3`
- name: `??1?$AutoStubBias@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@QEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001b410`
- `0x14001b760`
- `0x1400338f0`
- `0x140033b30`
- `0x140064454`
- `0x140065101`
- `0x14006685f`

## callees

- `0x140005e4c`
- `0x14001e178`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14001e1a0`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14001e1a0`

## pseudocode

```c
__int64 __fastcall AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>>(
        int *a1)
{
  if ( a1[2] >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)a1 + 40LL))(*(_QWORD *)a1, 0, 0, 0);
    CoReleaseMarshalData(*(LPSTREAM *)a1);
  }
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)a1);
}

```

## disassembly

```asm
0x14001e178  push    rbx
0x14001e17a  sub     rsp, 30h
0x14001e17e  mov     rbx, rcx
0x14001e181  xor     edx, edx
0x14001e183  cmp     [rcx+8], edx
0x14001e186  jl      short loc_14001E1A6
0x14001e188  mov     rcx, [rcx]
0x14001e18b  mov     rax, [rcx]
0x14001e18e  xor     r9d, r9d
0x14001e191  xor     r8d, r8d
0x14001e194  mov     rax, [rax+28h]
0x14001e198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e19d  mov     rcx, [rbx]; pStm
0x14001e1a0  call    cs:__imp_CoReleaseMarshalData
0x14001e1a6  mov     rcx, rbx
0x14001e1a9  add     rsp, 30h
0x14001e1ad  pop     rbx
0x14001e1ae  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
