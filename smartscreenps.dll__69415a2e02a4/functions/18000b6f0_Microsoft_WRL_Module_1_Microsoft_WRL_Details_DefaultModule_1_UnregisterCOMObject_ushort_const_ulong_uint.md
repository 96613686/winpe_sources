# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x18000b6f0`
- end: `0x18000b712`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b6fb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b6fb`

## pseudocode

```c
__int64 Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject()
{
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000b6f0  sub     rsp, 28h
0x18000b6f4  xor     edx, edx
0x18000b6f6  mov     ecx, 80004001h
0x18000b6fb  call    cs:__imp_RoOriginateError
0x18000b702  nop     dword ptr [rax+rax+00h]
0x18000b707  mov     eax, 80004001h
0x18000b70c  add     rsp, 28h
0x18000b710  retn
```
