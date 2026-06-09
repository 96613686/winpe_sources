# RtmDllStartup

- ea: `0x180007e44`
- end: `0x180007e64`
- name: `RtmDllStartup`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007840`

## callees

- `0x180007e44`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x180007e4f`
- `ntdll!RtlInitializeResource` at `0x180007e4f`

## pseudocode

```c
__int64 RtmDllStartup()
{
  RtlInitializeResource(&Resource);
  return 1;
}

```

## disassembly

```asm
0x180007e44  sub     rsp, 28h
0x180007e48  lea     rcx, Resource; Resource
0x180007e4f  call    cs:__imp_RtlInitializeResource
0x180007e55  nop
0x180007e56  mov     eax, 1
0x180007e5b  jmp     short loc_180007E5F
0x180007e5d  xor     eax, eax
0x180007e5f  add     rsp, 28h
0x180007e63  retn
```
