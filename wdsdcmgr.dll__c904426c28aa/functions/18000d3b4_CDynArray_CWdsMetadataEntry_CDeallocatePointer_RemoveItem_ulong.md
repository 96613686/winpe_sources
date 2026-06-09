# CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem(ulong)

- ea: `0x18000d3b4`
- end: `0x18000d403`
- name: `?RemoveItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKK@Z`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a970`
- `0x18000ac50`

## callees

- `0x18000d3b4`
- `0x180015c91`

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
0x18000d3b4  mov     [rsp+arg_0], rbx
0x18000d3b9  push    rdi
0x18000d3ba  sub     rsp, 20h
0x18000d3be  mov     eax, [rcx+0Ch]
0x18000d3c1  xor     ebx, ebx
0x18000d3c3  mov     r10d, edx
0x18000d3c6  mov     rdi, rcx
0x18000d3c9  cmp     edx, eax
0x18000d3cb  jb      short loc_18000D3D4
0x18000d3cd  mov     ebx, 585h
0x18000d3d2  jmp     short loc_18000D3F6
0x18000d3d4  mov     r9, [rcx]
0x18000d3d7  sub     eax, r10d
0x18000d3da  lea     ecx, [r10+1]
0x18000d3de  lea     r8d, [rax-1]
0x18000d3e2  lea     rdx, [r9+rcx*8]; Src
0x18000d3e6  shl     r8, 3; Size
0x18000d3ea  lea     rcx, [r9+r10*8]; void *
0x18000d3ee  call    memmove_0
0x18000d3f3  dec     dword ptr [rdi+0Ch]
0x18000d3f6  mov     eax, ebx
0x18000d3f8  mov     rbx, [rsp+28h+arg_0]
0x18000d3fd  add     rsp, 20h
0x18000d401  pop     rdi
0x18000d402  retn
```
