# CFSSecurity::`scalar deleting destructor'(uint)

- ea: `0x180005eb0`
- end: `0x180005ee0`
- name: `??_GCFSSecurity@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CFSSecurity *__fastcall(CFSSecurity *hMem, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005e28`
- `0x180005eb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ecc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ecc`

## pseudocode

```c
CFSSecurity *__fastcall CFSSecurity::`scalar deleting destructor'(CFSSecurity *hMem, char a2)
{
  CFSSecurity::~CFSSecurity(hMem);
  if ( (a2 & 1) != 0 )
    LocalFree(hMem);
  return hMem;
}

```

## disassembly

```asm
0x180005eb0  mov     [rsp+arg_0], rbx
0x180005eb5  push    rdi
0x180005eb6  sub     rsp, 20h
0x180005eba  mov     ebx, edx
0x180005ebc  mov     rdi, rcx
0x180005ebf  call    ??1CFSSecurity@@UEAA@XZ; CFSSecurity::~CFSSecurity(void)
0x180005ec4  test    bl, 1
0x180005ec7  jz      short loc_180005ED2
0x180005ec9  mov     rcx, rdi; hMem
0x180005ecc  call    cs:__imp_LocalFree
0x180005ed2  mov     rbx, [rsp+28h+arg_0]
0x180005ed7  mov     rax, rdi
0x180005eda  add     rsp, 20h
0x180005ede  pop     rdi
0x180005edf  retn
```
