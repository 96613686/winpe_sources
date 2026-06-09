# CSxSimpleArray<_GUID>::~CSxSimpleArray<_GUID>(void)

- ea: `0x180002028`
- end: `0x18000204b`
- name: `??1?$CSxSimpleArray@U_GUID@@@@AEAA@XZ`
- size: `35`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1800029d8`
- `0x180002e9c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002035`
- `ole32!CoTaskMemFree` at `0x180002035`

## pseudocode

```c
__int64 __fastcall CSxSimpleArray<_GUID>::~CSxSimpleArray<_GUID>(__int64 a1)
{
  __int64 result; // rax

  CoTaskMemFree(*(LPVOID *)(a1 + 8));
  result = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180002028  push    rbx
0x18000202a  sub     rsp, 20h
0x18000202e  mov     rbx, rcx
0x180002031  mov     rcx, [rcx+8]; pv
0x180002035  call    cs:__imp_CoTaskMemFree
0x18000203b  xor     eax, eax
0x18000203d  mov     [rbx+8], rax
0x180002041  mov     [rbx+10h], rax
0x180002045  add     rsp, 20h
0x180002049  pop     rbx
0x18000204a  retn
```
