# FileProvCbCleanupStreamContext

- ea: `0x14003b7f0`
- end: `0x14003b84a`
- name: `FileProvCbCleanupStreamContext`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14003b7f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003b804`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b804`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14003b821`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14003b821`

## pseudocode

```c
void __fastcall FileProvCbCleanupStreamContext(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)(a1 + 32);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *(_QWORD *)(a1 + 32) = 0;
  }
  v3 = *(void **)(a1 + 40);
  if ( v3 )
  {
    ObDereferenceObjectDeferDelete(v3);
    *(_QWORD *)(a1 + 40) = 0;
  }
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x14003b7f0  push    rbx
0x14003b7f2  sub     rsp, 20h
0x14003b7f6  mov     rbx, rcx
0x14003b7f9  mov     rcx, [rcx+20h]; P
0x14003b7fd  test    rcx, rcx
0x14003b800  jz      short loc_14003B818
0x14003b802  xor     edx, edx; Tag
0x14003b804  call    cs:__imp_ExFreePoolWithTag
0x14003b80b  nop     dword ptr [rax+rax+00h]
0x14003b810  mov     qword ptr [rbx+20h], 0
0x14003b818  mov     rcx, [rbx+28h]; Object
0x14003b81c  test    rcx, rcx
0x14003b81f  jz      short loc_14003B835
0x14003b821  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14003b828  nop     dword ptr [rax+rax+00h]
0x14003b82d  mov     qword ptr [rbx+28h], 0
0x14003b835  mov     dword ptr [rbx], 0
0x14003b83b  mov     qword ptr [rbx+18h], 0
0x14003b843  add     rsp, 20h
0x14003b847  pop     rbx
0x14003b848  retn
```
