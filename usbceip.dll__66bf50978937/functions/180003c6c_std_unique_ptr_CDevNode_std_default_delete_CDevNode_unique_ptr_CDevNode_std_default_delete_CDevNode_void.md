# std::unique_ptr<CDevNode,std::default_delete<CDevNode>>::~unique_ptr<CDevNode,std::default_delete<CDevNode>>(void)

- ea: `0x180003c6c`
- end: `0x180003c82`
- name: `??1?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x180003cf4`
- `0x1800041b4`
- `0x180004388`
- `0x180005314`
- `0x180005a48`
- `0x180006d2c`
- `0x180007b44`
- `0x180008290`
- `0x18000b5c8`
- `0x18001008e`
- `0x1800100e8`
- `0x18001018a`
- `0x1800101e4`
- `0x180010378`
- `0x18001039c`
- `0x1800104b1`
- `0x180010576`
- `0x180010600`
- `0x180010838`

## callees

- `0x180003c6c`
- `0x180003cc4`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<CDevNode>::operator()();
  return result;
}

```

## disassembly

```asm
0x180003c6c  sub     rsp, 28h
0x180003c70  mov     rdx, [rcx]
0x180003c73  test    rdx, rdx
0x180003c76  jz      short loc_180003C7D
0x180003c78  call    ??R?$default_delete@VCDevNode@@@std@@QEBAXPEAVCDevNode@@@Z; std::default_delete<CDevNode>::operator()(CDevNode *)
0x180003c7d  add     rsp, 28h
0x180003c81  retn
```
