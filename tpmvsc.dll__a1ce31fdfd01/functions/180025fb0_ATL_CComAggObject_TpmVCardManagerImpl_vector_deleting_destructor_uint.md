# ATL::CComAggObject<TpmVCardManagerImpl>::`vector deleting destructor'(uint)

- ea: `0x180025fb0`
- end: `0x180025fe4`
- name: `??_E?$CComAggObject@VTpmVCardManagerImpl@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002360`
- `0x180025828`
- `0x180025fb0`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<TpmVCardManagerImpl>::`vector deleting destructor'(void *Block, char a2)
{
  ATL::CComAggObject<TpmVCardManagerImpl>::~CComAggObject<TpmVCardManagerImpl>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180025fb0  mov     [rsp+arg_0], rbx
0x180025fb5  push    rdi
0x180025fb6  sub     rsp, 20h
0x180025fba  mov     ebx, edx
0x180025fbc  mov     rdi, rcx
0x180025fbf  call    ??1?$CComAggObject@VTpmVCardManagerImpl@@@ATL@@UEAA@XZ; ATL::CComAggObject<TpmVCardManagerImpl>::~CComAggObject<TpmVCardManagerImpl>(void)
0x180025fc4  test    bl, 1
0x180025fc7  jz      short loc_180025FD6
0x180025fc9  mov     edx, 20h ; ' '
0x180025fce  mov     rcx, rdi; Block
0x180025fd1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025fd6  mov     rbx, [rsp+28h+arg_0]
0x180025fdb  mov     rax, rdi
0x180025fde  add     rsp, 20h
0x180025fe2  pop     rdi
0x180025fe3  retn
```
