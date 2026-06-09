# srstor::mi_creator::__Mi__Type_Creator__<srstor::MSFT_StorageNode>::create(mi::MiInstance &&)

- ea: `0x180029ad0`
- end: `0x180029af8`
- name: `?create@?$__Mi__Type_Creator__@VMSFT_StorageNode@srstor@@@mi_creator@srstor@@SA?AVMSFT_StorageNode@3@$$QEAVMiInstance@mi@@@Z`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180029720`

## callees

- `0x180026b2c`
- `0x18002a1b0`

## pseudocode

```c
__int64 __fastcall srstor::mi_creator::__Mi__Type_Creator__<srstor::MSFT_StorageNode>::create(__int64 a1)
{
  __int64 v2; // rax
  _BYTE v4[72]; // [rsp+20h] [rbp-48h] BYREF

  v2 = mi::MiInstance::MiInstance(v4);
  srstor::MSFT_StorageNode::MSFT_StorageNode(a1, v2);
  return a1;
}

```

## disassembly

```asm
0x180029ad0  push    rbx
0x180029ad2  sub     rsp, 60h
0x180029ad6  mov     rbx, rcx
0x180029ad9  lea     rcx, [rsp+68h+var_48]
0x180029ade  call    ??0MiInstance@mi@@QEAA@$$QEAV01@@Z; mi::MiInstance::MiInstance(mi::MiInstance &&)
0x180029ae3  mov     rdx, rax
0x180029ae6  mov     rcx, rbx
0x180029ae9  call    ??0MSFT_StorageNode@srstor@@IEAA@VMiInstance@mi@@@Z; srstor::MSFT_StorageNode::MSFT_StorageNode(mi::MiInstance)
0x180029aee  mov     rax, rbx
0x180029af1  add     rsp, 60h
0x180029af5  pop     rbx
0x180029af6  retn
```
