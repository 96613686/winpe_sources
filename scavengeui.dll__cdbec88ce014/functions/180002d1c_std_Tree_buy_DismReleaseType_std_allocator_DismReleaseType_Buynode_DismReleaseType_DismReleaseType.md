# std::_Tree_buy<_DismReleaseType,std::allocator<_DismReleaseType>>::_Buynode<_DismReleaseType>(_DismReleaseType &&)

- ea: `0x180002d1c`
- end: `0x180002d40`
- name: `??$_Buynode@W4_DismReleaseType@@@?$_Tree_buy@W4_DismReleaseType@@V?$allocator@W4_DismReleaseType@@@std@@@std@@QEAAPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@1@$$QEAW4_DismReleaseType@@@Z`
- size: `36`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d48`

## callees

- `0x1800037d8`

## pseudocode

```c
__int64 __fastcall std::_Tree_buy<enum _DismReleaseType>::_Buynode<enum _DismReleaseType>(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax

  result = std::_Tree_buy<enum _DismReleaseType>::_Buynode0();
  *(_WORD *)(result + 24) = 0;
  *(_DWORD *)(result + 28) = *a2;
  return result;
}

```

## disassembly

```asm
0x180002d1c  push    rbx
0x180002d1e  sub     rsp, 20h
0x180002d22  mov     rbx, rdx
0x180002d25  call    ?_Buynode0@?$_Tree_buy@W4_DismReleaseType@@V?$allocator@W4_DismReleaseType@@@std@@@std@@QEAAPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@2@XZ; std::_Tree_buy<_DismReleaseType>::_Buynode0(void)
0x180002d2a  mov     [rsp+28h+arg_8], rax
0x180002d2f  mov     word ptr [rax+18h], 0
0x180002d35  mov     ecx, [rbx]
0x180002d37  mov     [rax+1Ch], ecx
0x180002d3a  add     rsp, 20h
0x180002d3e  pop     rbx
0x180002d3f  retn
```
