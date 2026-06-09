# _GetXmlFilePath_::_1_::catch$0

- ea: `0x18001d3ba`
- end: `0x18001d3ea`
- name: `_GetXmlFilePath_::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall GetXmlFilePath_::_1_::catch_0(__int64 a1, __int64 a2)
{
  **(_QWORD **)(a2 + 40) = 0;
  *(_DWORD *)(a2 + 32) = 8;
  return 0;
}

```

## disassembly

```asm
0x18001d3ba  mov     [rsp+arg_8], rdx
0x18001d3bf  push    rbp
0x18001d3c0  sub     rsp, 20h
0x18001d3c4  mov     rbp, rdx
0x18001d3c7  mov     rax, [rbp+28h]
0x18001d3cb  mov     qword ptr [rax], 0
0x18001d3d2  mov     dword ptr [rbp+20h], 8
0x18001d3d9  mov     rax, 0
0x18001d3e3  add     rsp, 20h
0x18001d3e7  pop     rbp
0x18001d3e8  retn
```
