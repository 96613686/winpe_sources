# std::_Tree_alloc<0,std::_Tree_base_types<_DismReleaseType,std::allocator<_DismReleaseType>>>::_Buyheadnode(void)

- ea: `0x180003798`
- end: `0x1800037d1`
- name: `?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@W4_DismReleaseType@@V?$allocator@W4_DismReleaseType@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@2@XZ`
- size: `57`
- prototype: `_QWORD *()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003300`

## callees

- `0x180001064`
- `0x180001398`
- `0x180003798`

## pseudocode

```c
_QWORD *std::_Tree_alloc<0,std::_Tree_base_types<enum _DismReleaseType>>::_Buyheadnode()
{
  _QWORD *result; // rax

  result = operator new(0x20u);
  if ( !result )
    std::_Xbad_alloc();
  *result = result;
  result[1] = result;
  result[2] = result;
  *((_WORD *)result + 12) = 257;
  return result;
}

```

## disassembly

```asm
0x180003798  mov     [rsp+arg_0], rcx
0x18000379d  sub     rsp, 28h
0x1800037a1  mov     ecx, 20h ; ' '; Size
0x1800037a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800037ab  mov     [rsp+28h+arg_0], rax
0x1800037b0  test    rax, rax
0x1800037b3  jz      short loc_1800037CB
0x1800037b5  mov     [rax], rax
0x1800037b8  mov     [rax+8], rax
0x1800037bc  mov     [rax+10h], rax
0x1800037c0  mov     word ptr [rax+18h], 101h
0x1800037c6  add     rsp, 28h
0x1800037ca  retn
0x1800037cb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
