# std::_Tree<std::_Tmap_traits<_GUID,ulong,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Alloc_sentinel_and_proxy(void)

- ea: `0x1800057d8`
- end: `0x180005805`
- name: `?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@KUGUIDComparer@CUsbHubSqm@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@$0A@@std@@@std@@IEAAXXZ`
- size: `45`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006320`

## callees

- `0x18000246c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<_GUID,unsigned long,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::_Alloc_sentinel_and_proxy(
        _QWORD *a1)
{
  _QWORD *result; // rax

  result = operator new(0x30u);
  *result = result;
  result[1] = result;
  result[2] = result;
  *((_WORD *)result + 12) = 257;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x1800057d8  push    rbx
0x1800057da  sub     rsp, 20h
0x1800057de  mov     rbx, rcx
0x1800057e1  mov     ecx, 30h ; '0'; Size
0x1800057e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800057eb  mov     [rax], rax
0x1800057ee  mov     [rax+8], rax
0x1800057f2  mov     [rax+10h], rax
0x1800057f6  mov     word ptr [rax+18h], 101h
0x1800057fc  mov     [rbx], rax
0x1800057ff  add     rsp, 20h
0x180005803  pop     rbx
0x180005804  retn
```
