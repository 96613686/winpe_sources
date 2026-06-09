# operator delete(void *)

- ea: `0x18001a9a8`
- end: `0x18001a9e3`
- name: `??3@YAXPEAX@Z`
- size: `59`
- prototype: `void __fastcall(void *)`
- caller_count: `117`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800022f0`
- `0x180002810`
- `0x1800029f4`
- `0x180002c70`
- `0x180003868`
- `0x180003d30`
- `0x180004184`
- `0x18000480c`
- `0x180004ff8`
- `0x180005360`
- `0x1800053a0`
- `0x180005a4c`
- `0x180005f18`
- `0x180006488`
- `0x1800067f0`
- `0x180006bc4`
- `0x180006e48`
- `0x1800070ac`
- `0x180007a24`
- `0x18000881c`
- `0x1800088f0`
- `0x180008bd8`
- `0x180009130`
- `0x1800092cc`
- `0x18000967c`
- `0x180009ab8`
- `0x18000a3c4`
- `0x18000a5a4`
- `0x18000a880`
- `0x18000aa44`
- `0x18000aed0`
- `0x18000b0c4`
- `0x18000b290`
- `0x18000b430`
- `0x18000b560`
- `0x18000b8e8`
- `0x18000bdd4`
- `0x18000c024`
- `0x18000c404`
- `0x18000d6d0`
- `0x18000de34`
- `0x18000e528`
- `0x18000e968`
- `0x18000ee88`
- `0x18000ef44`
- `0x18000f1f4`
- `0x18000f560`
- `0x18000f5cc`
- `0x18000f688`
- `0x18000fddc`

## callees

- `0x18001a9a8`
- `0x180026d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001a9ca`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
  {
    if ( g_HpAllocator )
      HeapFree(hHeap, 0, a1);
    else
      ((void (*)(void))qword_180033680)();
  }
}

```

## disassembly

```asm
0x18001a9a8  sub     rsp, 28h
0x18001a9ac  test    rcx, rcx
0x18001a9af  jz      short loc_18001A9DE
0x18001a9b1  cmp     cs:?g_HpAllocator@@3VCHpAllocator@@A, 0; CHpAllocator g_HpAllocator
0x18001a9b8  jz      short loc_18001A9D1
0x18001a9ba  mov     r8, rcx
0x18001a9bd  xor     edx, edx
0x18001a9bf  mov     rcx, cs:hHeap
0x18001a9c6  add     rsp, 28h
0x18001a9ca  jmp     cs:__imp_HeapFree
0x18001a9d1  mov     rax, cs:qword_180033680
0x18001a9d8  call    cs:__guard_dispatch_icall_fptr
0x18001a9de  add     rsp, 28h
0x18001a9e2  retn
```
