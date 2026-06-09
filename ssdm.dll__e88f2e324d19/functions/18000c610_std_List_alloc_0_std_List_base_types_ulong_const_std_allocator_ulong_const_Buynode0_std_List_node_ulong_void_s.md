# std::_List_alloc<0,std::_List_base_types<ulong const,std::allocator<ulong const>>>::_Buynode0(std::_List_node<ulong,void *> *,std::_List_node<ulong,void *> *)

- ea: `0x18000c610`
- end: `0x18000c65c`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@$$CBKV?$allocator@$$CBK@std@@@std@@@std@@QEAAPEAU?$_List_node@KPEAX@2@PEAU32@0@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800042fc`
- `0x18000bfcc`
- `0x18000c89c`
- `0x18000c9a8`

## callees

- `0x180002a88`
- `0x180002bc8`
- `0x18000c610`

## pseudocode

```c
_QWORD *__fastcall std::_List_alloc<0,std::_List_base_types<unsigned long const>>::_Buynode0(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *result; // rax

  result = operator new(0x18u);
  if ( !result )
    std::_Xbad_alloc();
  if ( !a2 )
  {
    a2 = result;
    a3 = result;
  }
  *result = a2;
  result[1] = a3;
  return result;
}

```

## disassembly

```asm
0x18000c610  mov     [rsp+arg_8], rbx
0x18000c615  mov     [rsp+arg_0], rcx
0x18000c61a  push    rdi
0x18000c61b  sub     rsp, 20h
0x18000c61f  mov     rdi, r8
0x18000c622  mov     rbx, rdx
0x18000c625  mov     ecx, 18h; Size
0x18000c62a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c62f  mov     [rsp+28h+arg_0], rax
0x18000c634  test    rax, rax
0x18000c637  jz      short loc_18000C656
0x18000c639  test    rbx, rbx
0x18000c63c  jnz     short loc_18000C644
0x18000c63e  mov     rbx, rax
0x18000c641  mov     rdi, rax
0x18000c644  mov     [rax], rbx
0x18000c647  mov     [rax+8], rdi
0x18000c64b  mov     rbx, [rsp+28h+arg_8]
0x18000c650  add     rsp, 20h
0x18000c654  pop     rdi
0x18000c655  retn
0x18000c656  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
