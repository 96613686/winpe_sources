# CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem(ulong)

- ea: `0x18000bb00`
- end: `0x18000bb4f`
- name: `?RemoveItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKK@Z`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008da0`
- `0x18000b960`

## callees

- `0x18000bb00`
- `0x18000cc1c`

## pseudocode

```c
__int64 __fastcall CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem(__int64 a1, unsigned int a2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( a2 < *(_DWORD *)(a1 + 12) )
  {
    memmove_0(
      (void *)(*(_QWORD *)a1 + 8LL * a2),
      (const void *)(*(_QWORD *)a1 + 8LL * (a2 + 1)),
      8LL * (*(_DWORD *)(a1 + 12) + ~a2));
    --*(_DWORD *)(a1 + 12);
  }
  else
  {
    return 1413;
  }
  return v2;
}

```

## disassembly

```asm
0x18000bb00  mov     [rsp+arg_0], rbx
0x18000bb05  push    rdi
0x18000bb06  sub     rsp, 20h
0x18000bb0a  xor     ebx, ebx
0x18000bb0c  mov     eax, edx
0x18000bb0e  mov     rdi, rcx
0x18000bb11  cmp     edx, [rcx+0Ch]
0x18000bb14  jb      short loc_18000BB1D
0x18000bb16  mov     ebx, 585h
0x18000bb1b  jmp     short loc_18000BB41
0x18000bb1d  mov     r9, [rcx]
0x18000bb20  mov     r8d, eax
0x18000bb23  not     r8d
0x18000bb26  add     r8d, [rcx+0Ch]
0x18000bb2a  lea     ecx, [rax+1]
0x18000bb2d  shl     r8, 3; Size
0x18000bb31  lea     rdx, [r9+rcx*8]; Src
0x18000bb35  lea     rcx, [r9+rax*8]; void *
0x18000bb39  call    memmove_0
0x18000bb3e  dec     dword ptr [rdi+0Ch]
0x18000bb41  mov     eax, ebx
0x18000bb43  mov     rbx, [rsp+28h+arg_0]
0x18000bb48  add     rsp, 20h
0x18000bb4c  pop     rdi
0x18000bb4d  retn
```
