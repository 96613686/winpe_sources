# ATL::CComObject<CWscAdmin>::`vector deleting destructor'(uint)

- ea: `0x180003690`
- end: `0x1800036bf`
- name: `??_E?$CComObject@VCWscAdmin@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001cc8`
- `0x1800035bc`
- `0x180003690`

## pseudocode

```c
CWscAdmin *__fastcall ATL::CComObject<CWscAdmin>::`vector deleting destructor'(CWscAdmin *Block, char a2)
{
  ATL::CComObject<CWscAdmin>::~CComObject<CWscAdmin>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003690  mov     [rsp+arg_0], rbx
0x180003695  push    rdi
0x180003696  sub     rsp, 20h
0x18000369a  mov     ebx, edx
0x18000369c  mov     rdi, rcx
0x18000369f  call    ??1?$CComObject@VCWscAdmin@@@ATL@@UEAA@XZ; ATL::CComObject<CWscAdmin>::~CComObject<CWscAdmin>(void)
0x1800036a4  test    bl, 1
0x1800036a7  jz      short loc_1800036B1
0x1800036a9  mov     rcx, rdi; Block
0x1800036ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800036b1  mov     rbx, [rsp+28h+arg_0]
0x1800036b6  mov     rax, rdi
0x1800036b9  add     rsp, 20h
0x1800036bd  pop     rdi
0x1800036be  retn
```
