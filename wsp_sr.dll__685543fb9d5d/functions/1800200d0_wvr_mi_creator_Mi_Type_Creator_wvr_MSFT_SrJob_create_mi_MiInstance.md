# wvr::mi_creator::__Mi__Type_Creator__<wvr::MSFT_SrJob>::create(mi::MiInstance &&)

- ea: `0x1800200d0`
- end: `0x1800200f8`
- name: `?create@?$__Mi__Type_Creator__@VMSFT_SrJob@wvr@@@mi_creator@wvr@@SA?AVMSFT_SrJob@3@$$QEAVMiInstance@mi@@@Z`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d9f8`

## callees

- `0x1800216f0`
- `0x180026b2c`

## pseudocode

```c
__int64 __fastcall wvr::mi_creator::__Mi__Type_Creator__<wvr::MSFT_SrJob>::create(__int64 a1)
{
  __int64 v2; // rax
  _BYTE v4[72]; // [rsp+20h] [rbp-48h] BYREF

  v2 = mi::MiInstance::MiInstance(v4);
  wvr::MSFT_SrJob::MSFT_SrJob(a1, v2);
  return a1;
}

```

## disassembly

```asm
0x1800200d0  push    rbx
0x1800200d2  sub     rsp, 60h
0x1800200d6  mov     rbx, rcx
0x1800200d9  lea     rcx, [rsp+68h+var_48]
0x1800200de  call    ??0MiInstance@mi@@QEAA@$$QEAV01@@Z; mi::MiInstance::MiInstance(mi::MiInstance &&)
0x1800200e3  mov     rdx, rax
0x1800200e6  mov     rcx, rbx
0x1800200e9  call    ??0MSFT_SrJob@wvr@@IEAA@VMiInstance@mi@@@Z; wvr::MSFT_SrJob::MSFT_SrJob(mi::MiInstance)
0x1800200ee  mov     rax, rbx
0x1800200f1  add     rsp, 60h
0x1800200f5  pop     rbx
0x1800200f6  retn
```
