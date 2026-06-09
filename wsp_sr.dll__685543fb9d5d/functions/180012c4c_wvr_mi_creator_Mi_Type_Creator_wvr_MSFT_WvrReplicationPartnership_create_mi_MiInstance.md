# wvr::mi_creator::__Mi__Type_Creator__<wvr::MSFT_WvrReplicationPartnership>::create(mi::MiInstance &&)

- ea: `0x180012c4c`
- end: `0x180012c74`
- name: `?create@?$__Mi__Type_Creator__@VMSFT_WvrReplicationPartnership@wvr@@@mi_creator@wvr@@SA?AVMSFT_WvrReplicationPartnership@3@$$QEAVMiInstance@mi@@@Z`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180011784`
- `0x180012f18`
- `0x18001d42c`

## callees

- `0x18002119c`
- `0x180026b2c`

## pseudocode

```c
__int64 __fastcall wvr::mi_creator::__Mi__Type_Creator__<wvr::MSFT_WvrReplicationPartnership>::create(__int64 a1)
{
  __int64 v2; // rax
  _BYTE v4[72]; // [rsp+20h] [rbp-48h] BYREF

  v2 = mi::MiInstance::MiInstance(v4);
  wvr::MSFT_WvrReplicationPartnership::MSFT_WvrReplicationPartnership(a1, v2);
  return a1;
}

```

## disassembly

```asm
0x180012c4c  push    rbx
0x180012c4e  sub     rsp, 60h
0x180012c52  mov     rbx, rcx
0x180012c55  lea     rcx, [rsp+68h+var_48]
0x180012c5a  call    ??0MiInstance@mi@@QEAA@$$QEAV01@@Z; mi::MiInstance::MiInstance(mi::MiInstance &&)
0x180012c5f  mov     rdx, rax
0x180012c62  mov     rcx, rbx
0x180012c65  call    ??0MSFT_WvrReplicationPartnership@wvr@@IEAA@VMiInstance@mi@@@Z; wvr::MSFT_WvrReplicationPartnership::MSFT_WvrReplicationPartnership(mi::MiInstance)
0x180012c6a  mov     rax, rbx
0x180012c6d  add     rsp, 60h
0x180012c71  pop     rbx
0x180012c72  retn
```
