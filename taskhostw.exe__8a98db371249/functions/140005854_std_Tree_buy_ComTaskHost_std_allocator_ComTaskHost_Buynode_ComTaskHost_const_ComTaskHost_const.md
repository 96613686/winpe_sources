# std::_Tree_buy<ComTaskHost *,std::allocator<ComTaskHost *>>::_Buynode<ComTaskHost * const &>(ComTaskHost * const &)

- ea: `0x140005854`
- end: `0x14000587a`
- name: `??$_Buynode@AEBQEAVComTaskHost@@@?$_Tree_buy@PEAVComTaskHost@@V?$allocator@PEAVComTaskHost@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@1@AEBQEAVComTaskHost@@@Z`
- size: `38`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005340`
- `0x140005650`

## callees

- `0x140005880`

## pseudocode

```c
__int64 __fastcall std::_Tree_buy<ComTaskHost *>::_Buynode<ComTaskHost * const &>(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax

  result = std::_Tree_buy<ComTaskHost *>::_Buynode0();
  *(_WORD *)(result + 24) = 0;
  *(_QWORD *)(result + 32) = *a2;
  return result;
}

```

## disassembly

```asm
0x140005854  push    rbx
0x140005856  sub     rsp, 20h
0x14000585a  mov     rbx, rdx
0x14000585d  call    ?_Buynode0@?$_Tree_buy@PEAVComTaskHost@@V?$allocator@PEAVComTaskHost@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@XZ; std::_Tree_buy<ComTaskHost *>::_Buynode0(void)
0x140005862  mov     [rsp+28h+arg_8], rax
0x140005867  mov     word ptr [rax+18h], 0
0x14000586d  mov     rcx, [rbx]
0x140005870  mov     [rax+20h], rcx
0x140005874  add     rsp, 20h
0x140005878  pop     rbx
0x140005879  retn
```
