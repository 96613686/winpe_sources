# CThemeManagerService::`scalar deleting destructor'(uint)

- ea: `0x18000ce10`
- end: `0x18000ce4a`
- name: `??_GCThemeManagerService@@UEAAPEAXI@Z`
- size: `58`
- prototype: `CService *__fastcall(CService *hMem, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000ce10`
- `0x18000eba0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce36`

## pseudocode

```c
CService *__fastcall CThemeManagerService::`scalar deleting destructor'(CService *hMem, char a2)
{
  *(_QWORD *)hMem = &CThemeManagerService::`vftable';
  CService::~CService(hMem);
  if ( (a2 & 1) != 0 )
    LocalFree(hMem);
  return hMem;
}

```

## disassembly

```asm
0x18000ce10  mov     [rsp+arg_0], rbx
0x18000ce15  push    rdi
0x18000ce16  sub     rsp, 20h
0x18000ce1a  lea     rax, ??_7CThemeManagerService@@6B@; const CThemeManagerService::`vftable'
0x18000ce21  mov     ebx, edx
0x18000ce23  mov     [rcx], rax
0x18000ce26  mov     rdi, rcx
0x18000ce29  call    ??1CService@@MEAA@XZ; CService::~CService(void)
0x18000ce2e  test    bl, 1
0x18000ce31  jz      short loc_18000CE3C
0x18000ce33  mov     rcx, rdi; hMem
0x18000ce36  call    cs:__imp_LocalFree
0x18000ce3c  mov     rbx, [rsp+28h+arg_0]
0x18000ce41  mov     rax, rdi
0x18000ce44  add     rsp, 20h
0x18000ce48  pop     rdi
0x18000ce49  retn
```
