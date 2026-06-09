# std::_Ref_count_obj2<std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>>::`scalar deleting destructor'(uint)

- ea: `0x180010500`
- end: `0x18001052b`
- name: `??_G?$_Ref_count_obj2@V?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@@std@@UEAAPEAXI@Z`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800022a4`
- `0x180010500`

## pseudocode

```c
_QWORD *__fastcall std::_Ref_count_obj2<std::vector<winrt::com_ptr<IStream>>>::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &std::_Ref_count_obj2<std::vector<winrt::com_ptr<IStream>>>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010500  push    rbx
0x180010502  sub     rsp, 20h
0x180010506  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<winrt::com_ptr<IStream>>>::`vftable'
0x18001050d  mov     rbx, rcx
0x180010510  mov     [rcx], rax
0x180010513  test    dl, 1
0x180010516  jz      short loc_180010522
0x180010518  mov     edx, 28h ; '('
0x18001051d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010522  mov     rax, rbx
0x180010525  add     rsp, 20h
0x180010529  pop     rbx
0x18001052a  retn
```
