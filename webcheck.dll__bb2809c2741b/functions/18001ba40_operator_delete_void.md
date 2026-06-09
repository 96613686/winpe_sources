# operator delete(void *)

- ea: `0x18001ba40`
- end: `0x18001ba67`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `52`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003090`
- `0x180003480`
- `0x180003a7c`
- `0x180003bd0`
- `0x180003d20`
- `0x180004160`
- `0x180004300`
- `0x180004c30`
- `0x1800084b0`
- `0x180008570`
- `0x180008c30`
- `0x180009640`
- `0x180009738`
- `0x18000acf0`
- `0x18000ad40`
- `0x18000e688`
- `0x18000f970`
- `0x180010f88`
- `0x180011004`
- `0x180011970`
- `0x1800119a0`
- `0x1800130dc`
- `0x180013950`
- `0x180015080`
- `0x1800150c0`
- `0x1800157d8`
- `0x180015cf0`
- `0x180016270`
- `0x1800163a0`
- `0x1800164c0`
- `0x1800164f0`
- `0x180016660`
- `0x180017c80`
- `0x180018984`
- `0x180018d98`
- `0x180019a80`
- `0x18001af30`
- `0x18001af70`
- `0x18001afbc`
- `0x18001b0f8`
- `0x18001b790`
- `0x18001cbfc`
- `0x18001ccc0`
- `0x18001dfd0`
- `0x18001f584`
- `0x180021070`
- `0x180021dd0`
- `0x180023980`
- `0x180023b54`
- `0x180023cc0`

## callees

- `0x18001ba40`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18001ba4d`
- `KERNEL32!GetProcessHeap` at `0x18001ba4d`
- `KERNEL32!HeapFree` at `0x18001ba5b`
- `KERNEL32!HeapFree` at `0x18001ba5b`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
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
0x18001ba40  test    rcx, rcx
0x18001ba43  jz      short locret_18001BA66
0x18001ba45  push    rbx
0x18001ba46  sub     rsp, 20h
0x18001ba4a  mov     rbx, rcx
0x18001ba4d  call    cs:__imp_GetProcessHeap
0x18001ba53  mov     r8, rbx; lpMem
0x18001ba56  xor     edx, edx; dwFlags
0x18001ba58  mov     rcx, rax; hHeap
0x18001ba5b  call    cs:__imp_HeapFree
0x18001ba61  add     rsp, 20h
0x18001ba65  pop     rbx
0x18001ba66  retn
```
