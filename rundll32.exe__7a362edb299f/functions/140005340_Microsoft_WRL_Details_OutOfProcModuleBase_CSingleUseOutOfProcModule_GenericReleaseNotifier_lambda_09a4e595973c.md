# Microsoft::WRL::Details::OutOfProcModuleBase_CSingleUseOutOfProcModule_::GenericReleaseNotifier__lambda_09a4e595973cd2309585cc06f08bbda7___::Invoke

- ea: `0x140005340`
- end: `0x140005354`
- name: `Microsoft::WRL::Details::OutOfProcModuleBase_CSingleUseOutOfProcModule_::GenericReleaseNotifier__lambda_09a4e595973cd2309585cc06f08bbda7___::Invoke`
- size: `20`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x14000534d`

## pseudocode

```c
BOOL __fastcall Microsoft::WRL::Details::OutOfProcModuleBase_CSingleUseOutOfProcModule_::GenericReleaseNotifier__lambda_09a4e595973cd2309585cc06f08bbda7___::Invoke(
        __int64 a1)
{
  return PostThreadMessageW(*(_DWORD *)(a1 + 16), 0x12u, 0, 0);
}

```

## disassembly

```asm
0x140005340  mov     ecx, [rcx+10h]
0x140005343  xor     r9d, r9d
0x140005346  xor     r8d, r8d
0x140005349  lea     edx, [r9+12h]
0x14000534d  jmp     cs:__imp_PostThreadMessageW
```
