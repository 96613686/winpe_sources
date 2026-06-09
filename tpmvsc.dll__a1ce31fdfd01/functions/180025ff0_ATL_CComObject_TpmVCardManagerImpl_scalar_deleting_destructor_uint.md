# ATL::CComObject<TpmVCardManagerImpl>::`scalar deleting destructor'(uint)

- ea: `0x180025ff0`
- end: `0x180026024`
- name: `??_G?$CComObject@VTpmVCardManagerImpl@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002360`
- `0x180025854`
- `0x180025ff0`

## pseudocode

```c
void *__fastcall ATL::CComObject<TpmVCardManagerImpl>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<TpmVCardManagerImpl>::~CComObject<TpmVCardManagerImpl>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180025ff0  mov     [rsp+arg_0], rbx
0x180025ff5  push    rdi
0x180025ff6  sub     rsp, 20h
0x180025ffa  mov     ebx, edx
0x180025ffc  mov     rdi, rcx
0x180025fff  call    ??1?$CComObject@VTpmVCardManagerImpl@@@ATL@@UEAA@XZ; ATL::CComObject<TpmVCardManagerImpl>::~CComObject<TpmVCardManagerImpl>(void)
0x180026004  test    bl, 1
0x180026007  jz      short loc_180026016
0x180026009  mov     edx, 10h
0x18002600e  mov     rcx, rdi; Block
0x180026011  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026016  mov     rbx, [rsp+28h+arg_0]
0x18002601b  mov     rax, rdi
0x18002601e  add     rsp, 20h
0x180026022  pop     rdi
0x180026023  retn
```
