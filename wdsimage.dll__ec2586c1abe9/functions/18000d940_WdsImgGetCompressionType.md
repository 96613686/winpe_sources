# WdsImgGetCompressionType

- ea: `0x18000d940`
- end: `0x18000d949`
- name: `WdsImgGetCompressionType`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall WdsImgGetCompressionType(__int64 a1, _DWORD *a2)
{
  *a2 = 259;
  return 0;
}

```

## disassembly

```asm
0x18000d940  mov     dword ptr [rdx], 103h
0x18000d946  xor     eax, eax
0x18000d948  retn
```
