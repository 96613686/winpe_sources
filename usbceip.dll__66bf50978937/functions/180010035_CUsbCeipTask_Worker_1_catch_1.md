# _CUsbCeipTask::Worker_::_1_::catch$1

- ea: `0x180010035`
- end: `0x18001005a`
- name: `_CUsbCeipTask::Worker_::_1_::catch$1`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CUsbCeipTask::Worker_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x180010035  mov     [rsp+arg_8], rdx
0x18001003a  push    rbp
0x18001003b  sub     rsp, 20h
0x18001003f  mov     rbp, rdx
0x180010042  mov     dword ptr [rbp+48h], 8007000Eh
0x180010049  mov     rax, 0
0x180010053  add     rsp, 20h
0x180010057  pop     rbp
0x180010058  retn
```
