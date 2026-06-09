# wvr::mi_creator::__Mi__Type_Creator__<wvr::MSFT_SrJob>::create(mi::MiInstance &&)

- ea: `0x18001ff90`
- end: `0x18001ffb7`
- name: `?create@?$__Mi__Type_Creator__@VMSFT_SrJob@wvr@@@mi_creator@wvr@@SA?AVMSFT_SrJob@3@$$QEAVMiInstance@mi@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d8d4`

## callees

- `0x180021560`
- `0x1800267e8`

## pseudocode

```c
__int64 __fastcall wvr::mi_creator::__Mi__Type_Creator__<wvr::MSFT_SrJob>::create(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  _BYTE v5[72]; // [rsp+20h] [rbp-48h] BYREF

  v3 = mi::MiInstance::MiInstance((__int64)v5, a2);
  wvr::MSFT_SrJob::MSFT_SrJob(a1, v3);
  return a1;
}

```

## disassembly

```asm
0x18001ff90  push    rbx
0x18001ff92  sub     rsp, 60h
0x18001ff96  mov     rbx, rcx
0x18001ff99  lea     rcx, [rsp+68h+var_48]
0x18001ff9e  call    ??0MiInstance@mi@@QEAA@$$QEAV01@@Z; mi::MiInstance::MiInstance(mi::MiInstance &&)
0x18001ffa3  mov     rdx, rax
0x18001ffa6  mov     rcx, rbx
0x18001ffa9  call    ??0MSFT_SrJob@wvr@@IEAA@VMiInstance@mi@@@Z; wvr::MSFT_SrJob::MSFT_SrJob(mi::MiInstance)
0x18001ffae  mov     rax, rbx
0x18001ffb1  add     rsp, 60h
0x18001ffb5  pop     rbx
0x18001ffb6  retn
```
