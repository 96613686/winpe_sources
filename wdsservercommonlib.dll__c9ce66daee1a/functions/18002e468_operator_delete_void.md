# operator delete(void *)

- ea: `0x18002e468`
- end: `0x18002e48f`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `171`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001db8`
- `0x180002e80`
- `0x180002f20`
- `0x180002fb0`
- `0x180003050`
- `0x180004200`
- `0x180004dc0`
- `0x180005260`
- `0x180005960`
- `0x180006598`
- `0x180006660`
- `0x180006810`
- `0x18000689c`
- `0x1800069c0`
- `0x180006a80`
- `0x180006d40`
- `0x1800072f0`
- `0x1800073a0`
- `0x180007450`
- `0x1800076b0`
- `0x180007790`
- `0x180007a00`
- `0x180007bb0`
- `0x1800090e0`
- `0x18000e200`
- `0x18000e220`
- `0x18000e2f0`
- `0x18000e3a0`
- `0x18000e520`
- `0x18000e770`
- `0x18000eb50`
- `0x18000ec80`
- `0x18000ee60`
- `0x18000f150`
- `0x18000f590`
- `0x18000f940`
- `0x18000fff0`
- `0x1800105e0`
- `0x180010620`
- `0x1800109f0`
- `0x180010b40`
- `0x180011a90`
- `0x180011d00`
- `0x180011f20`
- `0x180012150`
- `0x1800121e0`
- `0x1800123b0`
- `0x180012540`
- `0x1800127a0`
- `0x1800129d0`

## callees

- `0x18002e468`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002e47d`
- `KERNEL32!HeapFree` at `0x18002e47d`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  if ( lpMem )
    HeapFree(hHeap, 0, lpMem);
}

```

## disassembly

```asm
0x18002e468  sub     rsp, 28h
0x18002e46c  test    rcx, rcx
0x18002e46f  jz      short loc_18002E489
0x18002e471  mov     r8, rcx; lpMem
0x18002e474  xor     edx, edx; dwFlags
0x18002e476  mov     rcx, cs:hHeap; hHeap
0x18002e47d  call    cs:__imp_HeapFree
0x18002e484  nop     dword ptr [rax+rax+00h]
0x18002e489  add     rsp, 28h
0x18002e48d  retn
```
