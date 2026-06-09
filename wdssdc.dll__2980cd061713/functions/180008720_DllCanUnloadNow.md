# DllCanUnloadNow

- ea: `0x180008720`
- end: `0x18000874a`
- name: `DllCanUnloadNow`
- size: `42`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x180008720  sub     rsp, 28h
0x180008724  mov     rax, cs:?_AtlModule@@3VCWdsSimpleDeviceControllerModule@@A; CWdsSimpleDeviceControllerModule _AtlModule
0x18000872b  lea     rcx, ?_AtlModule@@3VCWdsSimpleDeviceControllerModule@@A; CWdsSimpleDeviceControllerModule _AtlModule
0x180008732  mov     rax, [rax+18h]
0x180008736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000873b  xor     ecx, ecx
0x18000873d  test    eax, eax
0x18000873f  setnz   cl
0x180008742  mov     eax, ecx
0x180008744  add     rsp, 28h
0x180008748  retn
```
