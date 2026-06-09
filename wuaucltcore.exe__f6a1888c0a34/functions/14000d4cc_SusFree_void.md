# SusFree(void *)

- ea: `0x14000d4cc`
- end: `0x14000d4f3`
- name: `?SusFree@@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `41`
- callee_count: `1`
- tags: ``

## callers

- `0x140007a70`
- `0x140007a9c`
- `0x1400080bc`
- `0x1400109ec`
- `0x140010f3c`
- `0x1400111a4`
- `0x140013600`
- `0x140013a74`
- `0x140013bbc`
- `0x140013cf0`
- `0x140013d70`
- `0x140013de4`
- `0x140013e54`
- `0x140013ec4`
- `0x140014cac`
- `0x1400150cc`
- `0x14001565c`
- `0x14001593c`
- `0x140015dec`
- `0x14001601c`
- `0x1400164c8`
- `0x1400168cc`
- `0x140016cd4`
- `0x140016ef8`
- `0x1400170dc`
- `0x140017624`
- `0x140017b48`
- `0x140017f58`
- `0x1400183a0`
- `0x140018528`
- `0x140019090`
- `0x1400191d0`
- `0x140019330`
- `0x140019460`
- `0x1400195a0`
- `0x1400196b0`
- `0x1400199a0`
- `0x140019a84`
- `0x140019ddc`
- `0x14001a5dc`
- `0x140022080`

## callees

- `0x14000d4cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d4e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d4e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d4d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d4d9`

## pseudocode

```c
void __fastcall SusFree(void *lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x14000d4cc  test    rcx, rcx
0x14000d4cf  jz      short locret_14000D4F2
0x14000d4d1  push    rbx
0x14000d4d2  sub     rsp, 20h
0x14000d4d6  mov     rbx, rcx
0x14000d4d9  call    cs:__imp_GetProcessHeap
0x14000d4df  mov     r8, rbx; lpMem
0x14000d4e2  xor     edx, edx; dwFlags
0x14000d4e4  mov     rcx, rax; hHeap
0x14000d4e7  call    cs:__imp_HeapFree
0x14000d4ed  add     rsp, 20h
0x14000d4f1  pop     rbx
0x14000d4f2  retn
```
