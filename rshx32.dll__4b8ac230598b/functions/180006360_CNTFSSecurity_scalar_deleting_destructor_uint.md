# CNTFSSecurity::`scalar deleting destructor'(uint)

- ea: `0x180006360`
- end: `0x180006390`
- name: `??_GCNTFSSecurity@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CNTFSSecurity *__fastcall(CNTFSSecurity *hMem, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006284`
- `0x180006360`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000637c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000637c`

## pseudocode

```c
CNTFSSecurity *__fastcall CNTFSSecurity::`scalar deleting destructor'(CNTFSSecurity *hMem, char a2)
{
  CNTFSSecurity::~CNTFSSecurity(hMem);
  if ( (a2 & 1) != 0 )
    LocalFree(hMem);
  return hMem;
}

```

## disassembly

```asm
0x180006360  mov     [rsp+arg_0], rbx
0x180006365  push    rdi
0x180006366  sub     rsp, 20h
0x18000636a  mov     ebx, edx
0x18000636c  mov     rdi, rcx
0x18000636f  call    ??1CNTFSSecurity@@UEAA@XZ; CNTFSSecurity::~CNTFSSecurity(void)
0x180006374  test    bl, 1
0x180006377  jz      short loc_180006382
0x180006379  mov     rcx, rdi; hMem
0x18000637c  call    cs:__imp_LocalFree
0x180006382  mov     rbx, [rsp+28h+arg_0]
0x180006387  mov     rax, rdi
0x18000638a  add     rsp, 20h
0x18000638e  pop     rdi
0x18000638f  retn
```
