# wvr::mi_creator::__Mi__Type_Creator__<wvr::MSFT_WvrReplicationPartnership>::create(mi::MiInstance &&)

- ea: `0x180012d7c`
- end: `0x180012da3`
- name: `?create@?$__Mi__Type_Creator__@VMSFT_WvrReplicationPartnership@wvr@@@mi_creator@wvr@@SA?AVMSFT_WvrReplicationPartnership@3@$$QEAVMiInstance@mi@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800118c0`
- `0x180013048`
- `0x18001d308`

## callees

- `0x180021010`
- `0x1800267e8`

## pseudocode

```c
__int64 __fastcall wvr::mi_creator::__Mi__Type_Creator__<wvr::MSFT_WvrReplicationPartnership>::create(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax
  _BYTE v5[72]; // [rsp+20h] [rbp-48h] BYREF

  v3 = mi::MiInstance::MiInstance((__int64)v5, a2);
  wvr::MSFT_WvrReplicationPartnership::MSFT_WvrReplicationPartnership(a1, v3);
  return a1;
}

```

## disassembly

```asm
0x180012d7c  push    rbx
0x180012d7e  sub     rsp, 60h
0x180012d82  mov     rbx, rcx
0x180012d85  lea     rcx, [rsp+68h+var_48]
0x180012d8a  call    ??0MiInstance@mi@@QEAA@$$QEAV01@@Z; mi::MiInstance::MiInstance(mi::MiInstance &&)
0x180012d8f  mov     rdx, rax
0x180012d92  mov     rcx, rbx
0x180012d95  call    ??0MSFT_WvrReplicationPartnership@wvr@@IEAA@VMiInstance@mi@@@Z; wvr::MSFT_WvrReplicationPartnership::MSFT_WvrReplicationPartnership(mi::MiInstance)
0x180012d9a  mov     rax, rbx
0x180012d9d  add     rsp, 60h
0x180012da1  pop     rbx
0x180012da2  retn
```
