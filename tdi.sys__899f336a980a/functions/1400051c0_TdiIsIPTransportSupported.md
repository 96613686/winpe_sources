# TdiIsIPTransportSupported

- ea: `0x1400051c0`
- end: `0x1400051e7`
- name: `TdiIsIPTransportSupported`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `ntoskrnl!RtlCheckRegistryKey` at `0x1400051d0`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400051d0`

## pseudocode

```c
bool TdiIsIPTransportSupported()
{
  return RtlCheckRegistryKey(1u, (PWSTR)L"Tdx") == 0;
}

```

## disassembly

```asm
0x1400051c0  sub     rsp, 28h
0x1400051c4  lea     rdx, Path; "Tdx"
0x1400051cb  mov     ecx, 1; RelativeTo
0x1400051d0  call    cs:__imp_RtlCheckRegistryKey
0x1400051d7  nop     dword ptr [rax+rax+00h]
0x1400051dc  test    eax, eax
0x1400051de  setz    al
0x1400051e1  add     rsp, 28h
0x1400051e5  retn
```
