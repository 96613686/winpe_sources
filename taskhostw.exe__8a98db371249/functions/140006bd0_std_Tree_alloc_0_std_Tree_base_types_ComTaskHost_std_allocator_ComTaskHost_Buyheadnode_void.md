# std::_Tree_alloc<0,std::_Tree_base_types<ComTaskHost *,std::allocator<ComTaskHost *>>>::_Buyheadnode(void)

- ea: `0x140006bd0`
- end: `0x140006c09`
- name: `?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@PEAVComTaskHost@@V?$allocator@PEAVComTaskHost@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@XZ`
- size: `57`
- prototype: `_QWORD *()`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006b50`

## callees

- `0x140006bd0`
- `0x140007f24`
- `0x140008258`

## pseudocode

```c
_QWORD *std::_Tree_alloc<0,std::_Tree_base_types<ComTaskHost *>>::_Buyheadnode()
{
  _QWORD *result; // rax

  result = operator new(0x28u);
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
0x140006bd0  mov     [rsp+arg_0], rcx
0x140006bd5  sub     rsp, 28h
0x140006bd9  mov     ecx, 28h ; '('; Size
0x140006bde  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006be3  mov     [rsp+28h+arg_0], rax
0x140006be8  test    rax, rax
0x140006beb  jz      short loc_140006C03
0x140006bed  mov     [rax], rax
0x140006bf0  mov     [rax+8], rax
0x140006bf4  mov     [rax+10h], rax
0x140006bf8  mov     word ptr [rax+18h], 101h
0x140006bfe  add     rsp, 28h
0x140006c02  retn
0x140006c03  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
