# WinHvpEnvInit

- ea: `0x14001bd40`
- end: `0x14001bd7c`
- name: `WinHvpEnvInit`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002a804`

## callees

- `0x14001e2a0`

## import_xrefs

- `ntoskrnl!IoCreateDriver` at `0x14001bd6a`
- `ntoskrnl!IoCreateDriver` at `0x14001bd6a`

## pseudocode

```c
__int64 WinHvpEnvInit()
{
  _QWORD v1[3]; // [rsp+20h] [rbp-18h] BYREF

  WinHvpCreateBlackbox();
  v1[0] = 1966108;
  v1[1] = L"\\Driver\\WinHvr";
  return IoCreateDriver(v1, WinHvpHypervisorDriverInitialization);
}

```

## disassembly

```asm
0x14001bd40  sub     rsp, 38h
0x14001bd44  call    WinHvpCreateBlackbox
0x14001bd49  lea     rax, aDriverWinhvr; "\\Driver\\WinHvr"
0x14001bd50  mov     [rsp+38h+var_18], 1E001Ch
0x14001bd59  lea     rdx, WinHvpHypervisorDriverInitialization
0x14001bd60  mov     [rsp+38h+var_10], rax
0x14001bd65  lea     rcx, [rsp+38h+var_18]
0x14001bd6a  call    cs:__imp_IoCreateDriver
0x14001bd71  nop     dword ptr [rax+rax+00h]
0x14001bd76  add     rsp, 38h
0x14001bd7a  retn
```
