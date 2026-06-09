# std::_Tree_buy<ComTaskHost *,std::allocator<ComTaskHost *>>::_Buynode0(void)

- ea: `0x140005880`
- end: `0x1400058c3`
- name: `?_Buynode0@?$_Tree_buy@PEAVComTaskHost@@V?$allocator@PEAVComTaskHost@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@XZ`
- size: `67`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140005854`

## callees

- `0x140005880`
- `0x140007f24`
- `0x140008258`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_buy<ComTaskHost *>::_Buynode0(_QWORD *a1)
{
  _QWORD *result; // rax

  result = operator new(0x28u);
  if ( !result )
    std::_Xbad_alloc();
  try
  {
    *result = *a1;
    result[1] = *a1;
    result[2] = *a1;
  }
  catch ( ... )
  {
    operator delete(result);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x140005880  push    rbx
0x140005882  sub     rsp, 20h
0x140005886  mov     rbx, rcx
0x140005889  mov     ecx, 28h ; '('; Size
0x14000588e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005893  mov     rdx, rax
0x140005896  mov     [rsp+28h+arg_8], rax
0x14000589b  test    rax, rax
0x14000589e  jnz     short loc_1400058A6
0x1400058a0  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1400058a6  mov     rax, [rbx]
0x1400058a9  mov     [rdx], rax
0x1400058ac  mov     rax, [rbx]
0x1400058af  mov     [rdx+8], rax
0x1400058b3  mov     rax, [rbx]
0x1400058b6  mov     [rdx+10h], rax
0x1400058ba  mov     rax, rdx
0x1400058bd  add     rsp, 20h
0x1400058c1  pop     rbx
0x1400058c2  retn
```
