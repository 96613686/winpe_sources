# _TzautoupdateWorker::InitializeFinders_::_1_::dtor$0

- ea: `0x18001c65b`
- end: `0x18001c681`
- name: `_TzautoupdateWorker::InitializeFinders_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800046f0`
- `0x18001c65b`

## pseudocode

```c
void __fastcall TzautoupdateWorker::InitializeFinders_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    std::vector<std::unique_ptr<Finder>>::~vector<std::unique_ptr<Finder>>(*(_QWORD **)(a2 + 104));
  }
}

```

## disassembly

```asm
0x18001c65b  push    rbp
0x18001c65d  sub     rsp, 20h
0x18001c661  mov     rbp, rdx
0x18001c664  mov     eax, [rbp+20h]
0x18001c667  and     eax, 1
0x18001c66a  test    eax, eax
0x18001c66c  jz      short loc_18001C67B
0x18001c66e  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18001c672  mov     rcx, [rbp+68h]
0x18001c676  call    ??1?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<Finder>>::~vector<std::unique_ptr<Finder>>(void)
0x18001c67b  add     rsp, 20h
0x18001c67f  pop     rbp
0x18001c680  retn
```
