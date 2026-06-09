# _CUsbCeipTask::Worker_::_1_::catch$2

- ea: `0x180010060`
- end: `0x180010088`
- name: `_CUsbCeipTask::Worker_::_1_::catch$2`
- size: `40`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CUsbCeipTask::Worker_::_1_::catch_2(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = *(_DWORD *)(*(_QWORD *)(a2 + 40) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x180010060  mov     [rsp+arg_8], rdx
0x180010065  push    rbp
0x180010066  sub     rsp, 20h
0x18001006a  mov     rbp, rdx
0x18001006d  mov     rax, [rbp+28h]
0x180010071  mov     ecx, [rax+8]
0x180010074  mov     [rbp+48h], ecx
0x180010077  mov     rax, 0
0x180010081  add     rsp, 20h
0x180010085  pop     rbp
0x180010086  retn
```
