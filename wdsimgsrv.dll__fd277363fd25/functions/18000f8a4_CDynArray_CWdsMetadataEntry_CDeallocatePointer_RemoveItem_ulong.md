# CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem(ulong)

- ea: `0x18000f8a4`
- end: `0x18000f8f4`
- name: `?RemoveItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKK@Z`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e5f8`
- `0x18000f5f8`

## callees

- `0x1800025e4`
- `0x18000f8a4`

## pseudocode

```c
__int64 __fastcall CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem(__int64 a1, unsigned int a2)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx

  v2 = *(_DWORD *)(a1 + 12);
  v3 = 0;
  if ( a2 < v2 )
  {
    memmove_0((void *)(*(_QWORD *)a1 + 8LL * a2), (const void *)(*(_QWORD *)a1 + 8LL * (a2 + 1)), 8LL * (v2 - a2 - 1));
    --*(_DWORD *)(a1 + 12);
  }
  else
  {
    return 1413;
  }
  return v3;
}

```

## disassembly

```asm
0x18000f8a4  mov     [rsp+arg_0], rbx
0x18000f8a9  push    rdi
0x18000f8aa  sub     rsp, 20h
0x18000f8ae  mov     eax, [rcx+0Ch]
0x18000f8b1  xor     ebx, ebx
0x18000f8b3  mov     r10d, edx
0x18000f8b6  mov     rdi, rcx
0x18000f8b9  cmp     edx, eax
0x18000f8bb  jb      short loc_18000F8C4
0x18000f8bd  mov     ebx, 585h
0x18000f8c2  jmp     short loc_18000F8E6
0x18000f8c4  mov     r9, [rcx]
0x18000f8c7  sub     eax, r10d
0x18000f8ca  lea     ecx, [r10+1]
0x18000f8ce  lea     r8d, [rax-1]
0x18000f8d2  lea     rdx, [r9+rcx*8]; Src
0x18000f8d6  shl     r8, 3; Size
0x18000f8da  lea     rcx, [r9+r10*8]; void *
0x18000f8de  call    memmove_0
0x18000f8e3  dec     dword ptr [rdi+0Ch]
0x18000f8e6  mov     eax, ebx
0x18000f8e8  mov     rbx, [rsp+28h+arg_0]
0x18000f8ed  add     rsp, 20h
0x18000f8f1  pop     rdi
0x18000f8f2  retn
```
