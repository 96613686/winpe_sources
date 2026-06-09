# WinHvpEnvUninit

- ea: `0x14001bd84`
- end: `0x14001bdb6`
- name: `WinHvpEnvUninit`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e5ec`
- `0x14002a804`

## callees

- `0x14001bd84`
- `0x14001e420`

## import_xrefs

- `ntoskrnl!IoDeleteDriver` at `0x14001bd94`
- `ntoskrnl!IoDeleteDriver` at `0x14001bd94`

## pseudocode

```c
__int64 WinHvpEnvUninit()
{
  if ( WinHvpHypervisorDriver )
  {
    IoDeleteDriver();
    WinHvpHypervisorDriver = 0;
  }
  return WinHvpDestroyBlackbox();
}

```

## disassembly

```asm
0x14001bd84  sub     rsp, 28h
0x14001bd88  mov     rcx, cs:WinHvpHypervisorDriver
0x14001bd8f  test    rcx, rcx
0x14001bd92  jz      short loc_14001BDAB
0x14001bd94  call    cs:__imp_IoDeleteDriver
0x14001bd9b  nop     dword ptr [rax+rax+00h]
0x14001bda0  mov     cs:WinHvpHypervisorDriver, 0
0x14001bdab  call    WinHvpDestroyBlackbox
0x14001bdb0  add     rsp, 28h
0x14001bdb4  retn
```
