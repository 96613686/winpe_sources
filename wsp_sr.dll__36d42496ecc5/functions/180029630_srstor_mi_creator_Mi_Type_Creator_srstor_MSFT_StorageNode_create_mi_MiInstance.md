# srstor::mi_creator::__Mi__Type_Creator__<srstor::MSFT_StorageNode>::create(mi::MiInstance &&)

- ea: `0x180029630`
- end: `0x180029657`
- name: `?create@?$__Mi__Type_Creator__@VMSFT_StorageNode@srstor@@@mi_creator@srstor@@SA?AVMSFT_StorageNode@3@$$QEAVMiInstance@mi@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180029294`

## callees

- `0x1800267e8`
- `0x180029d00`

## pseudocode

```c
__int64 __fastcall srstor::mi_creator::__Mi__Type_Creator__<srstor::MSFT_StorageNode>::create(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  _BYTE v5[72]; // [rsp+20h] [rbp-48h] BYREF

  v3 = mi::MiInstance::MiInstance((__int64)v5, a2);
  srstor::MSFT_StorageNode::MSFT_StorageNode(a1, v3);
  return a1;
}

```

## disassembly

```asm
0x180029630  push    rbx
0x180029632  sub     rsp, 60h
0x180029636  mov     rbx, rcx
0x180029639  lea     rcx, [rsp+68h+var_48]
0x18002963e  call    ??0MiInstance@mi@@QEAA@$$QEAV01@@Z; mi::MiInstance::MiInstance(mi::MiInstance &&)
0x180029643  mov     rdx, rax
0x180029646  mov     rcx, rbx
0x180029649  call    ??0MSFT_StorageNode@srstor@@IEAA@VMiInstance@mi@@@Z; srstor::MSFT_StorageNode::MSFT_StorageNode(mi::MiInstance)
0x18002964e  mov     rax, rbx
0x180029651  add     rsp, 60h
0x180029655  pop     rbx
0x180029656  retn
```
