# std::_List_alloc<0,std::_List_base_types<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>>::_Buynode0(std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *,std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *)

- ea: `0x18001ccb4`
- end: `0x18001cd0a`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@2@PEAU32@0@Z`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012f80`
- `0x18001486c`

## callees

- `0x180001374`
- `0x180001518`
- `0x18001ccb4`

## pseudocode

```c
_QWORD *__fastcall std::_List_alloc<0,std::_List_base_types<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Buynode0(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *result; // rax

  result = operator new(0xA0u);
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
0x18001ccb4  mov     [rsp+arg_0], rcx
0x18001ccb9  push    rdi
0x18001ccba  sub     rsp, 30h
0x18001ccbe  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001ccc7  mov     [rsp+38h+arg_8], rbx
0x18001cccc  mov     rdi, r8
0x18001cccf  mov     rbx, rdx
0x18001ccd2  mov     ecx, 0A0h; Size
0x18001ccd7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ccdc  mov     [rsp+38h+arg_0], rax
0x18001cce1  test    rax, rax
0x18001cce4  jz      short loc_18001CD04
0x18001cce6  test    rbx, rbx
0x18001cce9  jnz     short loc_18001CCF1
0x18001cceb  mov     rbx, rax
0x18001ccee  mov     rdi, rax
0x18001ccf1  mov     [rax], rbx
0x18001ccf4  mov     [rax+8], rdi
0x18001ccf8  mov     rbx, [rsp+38h+arg_8]
0x18001ccfd  add     rsp, 30h
0x18001cd01  pop     rdi
0x18001cd02  retn
0x18001cd04  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
