# std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::_Get_deleter(type_info const &)

- ea: `0x18000d620`
- end: `0x18000d64d`
- name: `?_Get_deleter@?$_Ref_count_del@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002ce0`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::_Get_deleter(
        __int64 a1,
        const struct type_info *a2)
{
  return (a1 + 24)
       & -(__int64)((unsigned int)__crtTypeinfoOperatorEquality_Stub(
                                    a2,
                                    (const struct type_info *)&std::default_delete<SharedMemory> `RTTI Type Descriptor') != 0);
}

```

## disassembly

```asm
0x18000d620  push    rbx
0x18000d622  sub     rsp, 20h
0x18000d626  mov     rax, rdx
0x18000d629  mov     rbx, rcx
0x18000d62c  mov     rcx, rax; struct type_info *
0x18000d62f  lea     rdx, ??_R0?AU?$default_delete@VSharedMemory@@@std@@@8; struct type_info *
0x18000d636  call    ?__crtTypeinfoOperatorEquality_Stub@@YAHAEBVtype_info@@0@Z; __crtTypeinfoOperatorEquality_Stub(type_info const &,type_info const &)
0x18000d63b  neg     eax
0x18000d63d  lea     rcx, [rbx+18h]
0x18000d641  sbb     rax, rax
0x18000d644  and     rax, rcx
0x18000d647  add     rsp, 20h
0x18000d64b  pop     rbx
0x18000d64c  retn
```
