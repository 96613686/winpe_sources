# std::vector<std::unique_ptr<Finder,std::default_delete<Finder>>,std::allocator<std::unique_ptr<Finder,std::default_delete<Finder>>>>::~vector<std::unique_ptr<Finder,std::default_delete<Finder>>,std::allocator<std::unique_ptr<Finder,std::default_delete<Finder>>>>(void)

- ea: `0x1800046f0`
- end: `0x180004730`
- name: `??1?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001b578`
- `0x18001c504`
- `0x18001c65b`

## callees

- `0x1800046f0`
- `0x18000ad08`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000470d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000470d`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<Finder>>::~vector<std::unique_ptr<Finder>>(_QWORD *a1)
{
  if ( *a1 )
  {
    std::vector<std::unique_ptr<Finder>>::_Destroy(a1, *a1, a1[1]);
    operator delete((void *)*a1);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x1800046f0  push    rbx
0x1800046f2  sub     rsp, 20h
0x1800046f6  mov     rdx, [rcx]
0x1800046f9  mov     rbx, rcx
0x1800046fc  test    rdx, rdx
0x1800046ff  jz      short loc_18000472A
0x180004701  mov     r8, [rcx+8]
0x180004705  call    ?_Destroy@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@2@0@Z; std::vector<std::unique_ptr<Finder>>::_Destroy(std::unique_ptr<Finder> *,std::unique_ptr<Finder> *)
0x18000470a  mov     rcx, [rbx]
0x18000470d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004713  mov     qword ptr [rbx], 0
0x18000471a  mov     qword ptr [rbx+8], 0
0x180004722  mov     qword ptr [rbx+10h], 0
0x18000472a  add     rsp, 20h
0x18000472e  pop     rbx
0x18000472f  retn
```
