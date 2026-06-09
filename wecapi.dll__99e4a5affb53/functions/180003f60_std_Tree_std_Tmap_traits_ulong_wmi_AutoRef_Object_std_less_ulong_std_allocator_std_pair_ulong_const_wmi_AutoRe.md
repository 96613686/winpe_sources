# std::_Tree<std::_Tmap_traits<ulong,wmi::AutoRef<Object>,std::less<ulong>,std::allocator<std::pair<ulong const,wmi::AutoRef<Object>>>,0>>::clear(void)

- ea: `0x180003f60`
- end: `0x180003ffc`
- name: `?clear@?$_Tree@V?$_Tmap_traits@KV?$AutoRef@VObject@@@wmi@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@4@$0A@@std@@@std@@QEAAXXZ`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000330c`
- `0x18000346c`

## callees

- `0x1800026c0`
- `0x180003ce4`
- `0x180003f60`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned long,wmi::AutoRef<Object>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,wmi::AutoRef<Object>>>,0>>::clear(
        _QWORD *a1)
{
  _QWORD *v2; // rdi
  _QWORD *i; // rsi
  __int64 v4; // rcx
  __int64 result; // rax

  v2 = *(_QWORD **)(*a1 + 8LL);
  for ( i = v2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<unsigned long,wmi::AutoRef<Object>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,wmi::AutoRef<Object>>>,0>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
    v4 = v2[5];
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
    v2[5] = 0;
    operator delete(v2);
  }
  *(_QWORD *)(*a1 + 8LL) = *a1;
  *(_QWORD *)*a1 = *a1;
  result = *a1;
  *(_QWORD *)(*a1 + 16LL) = *a1;
  a1[1] = 0;
  return result;
}

```

## disassembly

```asm
0x180003f60  mov     [rsp+arg_8], rbx
0x180003f65  mov     [rsp+arg_10], rsi
0x180003f6a  push    rdi
0x180003f6b  sub     rsp, 20h
0x180003f6f  mov     rbx, rcx
0x180003f72  mov     rax, [rcx]
0x180003f75  mov     rdi, [rax+8]
0x180003f79  mov     rsi, rdi
0x180003f7c  cmp     byte ptr [rdi+19h], 0
0x180003f80  jnz     short loc_180003FD0
0x180003f82  mov     rdx, [rsi+10h]
0x180003f86  mov     rcx, rbx
0x180003f89  call    ?_Erase@?$_Tree@V?$_Tmap_traits@KV?$AutoRef@VObject@@@wmi@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ulong,wmi::AutoRef<Object>,std::less<ulong>,std::allocator<std::pair<ulong const,wmi::AutoRef<Object>>>,0>>::_Erase(std::_Tree_node<std::pair<ulong const,wmi::AutoRef<Object>>,void *> *)
0x180003f8e  mov     rsi, [rsi]
0x180003f91  mov     rcx, [rdi+28h]
0x180003f95  test    rcx, rcx
0x180003f98  jz      short loc_180003FB7
0x180003f9a  or      eax, 0FFFFFFFFh
0x180003f9d  lock xadd [rcx+8], eax
0x180003fa2  cmp     eax, 1
0x180003fa5  jnz     short loc_180003FB7
0x180003fa7  mov     rax, [rcx]
0x180003faa  mov     edx, 1
0x180003faf  mov     rax, [rax]
0x180003fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fb7  mov     qword ptr [rdi+28h], 0
0x180003fbf  mov     rcx, rdi; void *
0x180003fc2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003fc7  mov     rdi, rsi
0x180003fca  cmp     byte ptr [rsi+19h], 0
0x180003fce  jz      short loc_180003F82
0x180003fd0  mov     rax, [rbx]
0x180003fd3  mov     [rax+8], rax
0x180003fd7  mov     rax, [rbx]
0x180003fda  mov     [rax], rax
0x180003fdd  mov     rax, [rbx]
0x180003fe0  mov     [rax+10h], rax
0x180003fe4  mov     qword ptr [rbx+8], 0
0x180003fec  mov     rbx, [rsp+28h+arg_8]
0x180003ff1  mov     rsi, [rsp+28h+arg_10]
0x180003ff6  add     rsp, 20h
0x180003ffa  pop     rdi
0x180003ffb  retn
```
