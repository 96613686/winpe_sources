# srstor::mi_creator::__Mi__Type_Creator__<srstor::MSFT_Volume>::create(mi::MiInstance &&)

- ea: `0x180029660`
- end: `0x180029687`
- name: `?create@?$__Mi__Type_Creator__@VMSFT_Volume@srstor@@@mi_creator@srstor@@SA?AVMSFT_Volume@3@$$QEAVMiInstance@mi@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800298e4`

## callees

- `0x1800267e8`
- `0x180029248`

## pseudocode

```c
__int64 __fastcall srstor::mi_creator::__Mi__Type_Creator__<srstor::MSFT_Volume>::create(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  _BYTE v5[72]; // [rsp+20h] [rbp-48h] BYREF

  v3 = mi::MiInstance::MiInstance((__int64)v5, a2);
  srstor::MSFT_Volume::MSFT_Volume(a1, v3);
  return a1;
}

```

## disassembly

```asm
0x180029660  push    rbx
0x180029662  sub     rsp, 60h
0x180029666  mov     rbx, rcx
0x180029669  lea     rcx, [rsp+68h+var_48]
0x18002966e  call    ??0MiInstance@mi@@QEAA@$$QEAV01@@Z; mi::MiInstance::MiInstance(mi::MiInstance &&)
0x180029673  mov     rdx, rax
0x180029676  mov     rcx, rbx
0x180029679  call    ??0MSFT_Volume@srstor@@IEAA@VMiInstance@mi@@@Z; srstor::MSFT_Volume::MSFT_Volume(mi::MiInstance)
0x18002967e  mov     rax, rbx
0x180029681  add     rsp, 60h
0x180029685  pop     rbx
0x180029686  retn
```
