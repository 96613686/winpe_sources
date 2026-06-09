# _GetXmlFilePath_::_1_::catch$0

- ea: `0x18001be8e`
- end: `0x18001bebe`
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
0x18001be8e  mov     [rsp+arg_8], rdx
0x18001be93  push    rbp
0x18001be94  sub     rsp, 20h
0x18001be98  mov     rbp, rdx
0x18001be9b  mov     rax, [rbp+28h]
0x18001be9f  mov     qword ptr [rax], 0
0x18001bea6  mov     dword ptr [rbp+20h], 8
0x18001bead  mov     rax, 0
0x18001beb7  add     rsp, 20h
0x18001bebb  pop     rbp
0x18001bebc  retn
```
