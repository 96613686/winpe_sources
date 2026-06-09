# AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>(void)

- ea: `0x14001f264`
- end: `0x14001f2a5`
- name: `??1?$AutoStubBias@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@QEAA@XZ`
- size: `65`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001c370`
- `0x14001c780`
- `0x140034d60`
- `0x140034fb4`
- `0x140066194`
- `0x140066f20`
- `0x140068680`

## callees

- `0x1400061cc`
- `0x14001f264`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14001f28c`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14001f28c`

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
0x14001f264  push    rbx
0x14001f266  sub     rsp, 30h
0x14001f26a  mov     rbx, rcx
0x14001f26d  xor     edx, edx
0x14001f26f  cmp     [rcx+8], edx
0x14001f272  jl      short loc_14001F298
0x14001f274  mov     rcx, [rcx]
0x14001f277  mov     rax, [rcx]
0x14001f27a  xor     r9d, r9d
0x14001f27d  xor     r8d, r8d
0x14001f280  mov     rax, [rax+28h]
0x14001f284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f289  mov     rcx, [rbx]; pStm
0x14001f28c  call    cs:__imp_CoReleaseMarshalData
0x14001f293  nop     dword ptr [rax+rax+00h]
0x14001f298  mov     rcx, rbx
0x14001f29b  add     rsp, 30h
0x14001f29f  pop     rbx
0x14001f2a0  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
