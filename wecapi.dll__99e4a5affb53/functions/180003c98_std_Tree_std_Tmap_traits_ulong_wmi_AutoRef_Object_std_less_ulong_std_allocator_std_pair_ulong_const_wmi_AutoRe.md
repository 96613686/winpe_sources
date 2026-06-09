# std::_Tree<std::_Tmap_traits<ulong,wmi::AutoRef<Object>,std::less<ulong>,std::allocator<std::pair<ulong const,wmi::AutoRef<Object>>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<ulong const,wmi::AutoRef<Object>>,void *> *)

- ea: `0x180003c98`
- end: `0x180003cdc`
- name: `?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@KV?$AutoRef@VObject@@@wmi@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@PEAX@2@@Z`
- size: `68`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002b60`
- `0x18000be96`
- `0x18000bebc`

## callees

- `0x1800026c0`
- `0x180003c98`
- `0x18000d010`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned long,wmi::AutoRef<Object>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,wmi::AutoRef<Object>>>,0>>::_Destroy_if_not_nil(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // rcx

  v2 = a2[5];
  if ( v2 && _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 1);
  a2[5] = 0;
  operator delete(a2);
}

```

## disassembly

```asm
0x180003c98  push    rbx
0x180003c9a  sub     rsp, 20h
0x180003c9e  mov     rcx, [rdx+28h]
0x180003ca2  mov     rbx, rdx
0x180003ca5  test    rcx, rcx
0x180003ca8  jz      short loc_180003CC7
0x180003caa  or      eax, 0FFFFFFFFh
0x180003cad  lock xadd [rcx+8], eax
0x180003cb2  cmp     eax, 1
0x180003cb5  jnz     short loc_180003CC7
0x180003cb7  mov     rax, [rcx]
0x180003cba  mov     edx, 1
0x180003cbf  mov     rax, [rax]
0x180003cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cc7  mov     rcx, rbx; void *
0x180003cca  mov     qword ptr [rbx+28h], 0
0x180003cd2  add     rsp, 20h
0x180003cd6  pop     rbx
0x180003cd7  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
