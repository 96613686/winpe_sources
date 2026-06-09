# ATL::CComObject<CTDCCtl>::`vector deleting destructor'(uint)

- ea: `0x18000f130`
- end: `0x18000f15f`
- name: `??_E?$CComObject@VCTDCCtl@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f120`

## callees

- `0x180001194`
- `0x18000efb8`
- `0x18000f130`

## pseudocode

```c
CTDCCtl *__fastcall ATL::CComObject<CTDCCtl>::`vector deleting destructor'(CTDCCtl *Block, char a2)
{
  ATL::CComObject<CTDCCtl>::~CComObject<CTDCCtl>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000f130  mov     [rsp+arg_0], rbx
0x18000f135  push    rdi
0x18000f136  sub     rsp, 20h
0x18000f13a  mov     ebx, edx
0x18000f13c  mov     rdi, rcx
0x18000f13f  call    ??1?$CComObject@VCTDCCtl@@@ATL@@UEAA@XZ; ATL::CComObject<CTDCCtl>::~CComObject<CTDCCtl>(void)
0x18000f144  test    bl, 1
0x18000f147  jz      short loc_18000F151
0x18000f149  mov     rcx, rdi; Block
0x18000f14c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f151  mov     rbx, [rsp+28h+arg_0]
0x18000f156  mov     rax, rdi
0x18000f159  add     rsp, 20h
0x18000f15d  pop     rdi
0x18000f15e  retn
```
