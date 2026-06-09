# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>(void)

- ea: `0x180003c54`
- end: `0x180003c91`
- name: `??1?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA@XZ`
- size: `61`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003ea8`
- `0x180006868`

## callees

- `0x180003c54`
- `0x180003d18`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003c66`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003c66`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>(
        _QWORD *a1)
{
  void *v2; // rcx

  v2 = (void *)a1[2];
  if ( v2 )
  {
    operator delete(v2);
    a1[2] = 0;
    a1[3] = 0;
    a1[4] = 0;
  }
  return std::list<unsigned __int64>::~list<unsigned __int64>(a1);
}

```

## disassembly

```asm
0x180003c54  push    rbx
0x180003c56  sub     rsp, 20h
0x180003c5a  mov     rbx, rcx
0x180003c5d  mov     rcx, [rcx+10h]
0x180003c61  test    rcx, rcx
0x180003c64  jz      short loc_180003C84
0x180003c66  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003c6c  mov     qword ptr [rbx+10h], 0
0x180003c74  mov     qword ptr [rbx+18h], 0
0x180003c7c  mov     qword ptr [rbx+20h], 0
0x180003c84  mov     rcx, rbx
0x180003c87  add     rsp, 20h
0x180003c8b  pop     rbx
0x180003c8c  jmp     ??1?$list@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::list<unsigned __int64>::~list<unsigned __int64>(void)
```
