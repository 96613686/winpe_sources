# srstor::mi_creator::__Mi__Type_Creator__<srstor::MSFT_Volume>::create(mi::MiInstance &&)

- ea: `0x180029b00`
- end: `0x180029b28`
- name: `?create@?$__Mi__Type_Creator__@VMSFT_Volume@srstor@@@mi_creator@srstor@@SA?AVMSFT_Volume@3@$$QEAVMiInstance@mi@@@Z`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180029d8c`

## callees

- `0x180026b2c`
- `0x1800296d4`

## pseudocode

```c
__int64 __fastcall srstor::mi_creator::__Mi__Type_Creator__<srstor::MSFT_Volume>::create(__int64 a1)
{
  __int64 v2; // rax
  _BYTE v4[72]; // [rsp+20h] [rbp-48h] BYREF

  v2 = mi::MiInstance::MiInstance(v4);
  srstor::MSFT_Volume::MSFT_Volume(a1, v2);
  return a1;
}

```

## disassembly

```asm
0x180029b00  push    rbx
0x180029b02  sub     rsp, 60h
0x180029b06  mov     rbx, rcx
0x180029b09  lea     rcx, [rsp+68h+var_48]
0x180029b0e  call    ??0MiInstance@mi@@QEAA@$$QEAV01@@Z; mi::MiInstance::MiInstance(mi::MiInstance &&)
0x180029b13  mov     rdx, rax
0x180029b16  mov     rcx, rbx
0x180029b19  call    ??0MSFT_Volume@srstor@@IEAA@VMiInstance@mi@@@Z; srstor::MSFT_Volume::MSFT_Volume(mi::MiInstance)
0x180029b1e  mov     rax, rbx
0x180029b21  add     rsp, 60h
0x180029b25  pop     rbx
0x180029b26  retn
```
