# CService::`vector deleting destructor'(uint)

- ea: `0x18000ec50`
- end: `0x18000ec80`
- name: `??_ECService@@MEAAPEAXI@Z`
- size: `48`
- prototype: `CService *__fastcall(CService *hMem, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000eba0`
- `0x18000ec50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec6c`

## pseudocode

```c
CService *__fastcall CService::`vector deleting destructor'(CService *hMem, char a2)
{
  CService::~CService(hMem);
  if ( (a2 & 1) != 0 )
    LocalFree(hMem);
  return hMem;
}

```

## disassembly

```asm
0x18000ec50  mov     [rsp+arg_0], rbx
0x18000ec55  push    rdi
0x18000ec56  sub     rsp, 20h
0x18000ec5a  mov     ebx, edx
0x18000ec5c  mov     rdi, rcx
0x18000ec5f  call    ??1CService@@MEAA@XZ; CService::~CService(void)
0x18000ec64  test    bl, 1
0x18000ec67  jz      short loc_18000EC72
0x18000ec69  mov     rcx, rdi; hMem
0x18000ec6c  call    cs:__imp_LocalFree
0x18000ec72  mov     rbx, [rsp+28h+arg_0]
0x18000ec77  mov     rax, rdi
0x18000ec7a  add     rsp, 20h
0x18000ec7e  pop     rdi
0x18000ec7f  retn
```
