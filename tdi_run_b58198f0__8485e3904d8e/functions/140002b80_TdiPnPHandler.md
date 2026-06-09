# TdiPnPHandler

- ea: `0x140002b80`
- end: `0x140002c17`
- name: `TdiPnPHandler`
- size: `151`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING UpperComponent, PUNICODE_STRING LowerComponent, PUNICODE_STRING BindList, PVOID ReconfigBuffer, UINT ReconfigBufferSize, UINT Operation)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140002b80`
- `0x140002f50`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140002ba7`
- `ntoskrnl!ExAllocatePool2` at `0x140002ba7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002bec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002bec`

## pseudocode

```c
__int64 __fastcall TdiPnPHandler(
        PUNICODE_STRING UpperComponent,
        PUNICODE_STRING LowerComponent,
        PUNICODE_STRING BindList,
        PVOID ReconfigBuffer,
        UINT ReconfigBufferSize,
        UINT Operation)
{
  __int64 Pool2; // rax
  void *v11; // rbx
  unsigned int v12; // edi

  Pool2 = ExAllocatePool2(64, 40, 1799963732);
  v11 = (void *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_QWORD *)Pool2 = UpperComponent;
  *(_QWORD *)(Pool2 + 8) = LowerComponent;
  *(_QWORD *)(Pool2 + 16) = BindList;
  *(_QWORD *)(Pool2 + 24) = ReconfigBuffer;
  *(_DWORD *)(Pool2 + 32) = ReconfigBufferSize;
  *(_DWORD *)(Pool2 + 36) = Operation;
  v12 = TdiHandleSerializedRequest(Pool2, 15);
  ExFreePoolWithTag(v11, 0);
  return v12;
}

```

## disassembly

```asm
0x140002b80  push    rbx
0x140002b82  push    rbp
0x140002b83  push    rsi
0x140002b84  push    rdi
0x140002b85  push    r14
0x140002b87  sub     rsp, 20h
0x140002b8b  mov     rsi, r8
0x140002b8e  mov     rbp, rdx
0x140002b91  mov     r14, rcx
0x140002b94  mov     edx, 28h ; '('
0x140002b99  mov     ecx, 40h ; '@'
0x140002b9e  mov     r8d, 6B494454h
0x140002ba4  mov     rdi, r9
0x140002ba7  call    cs:__imp_ExAllocatePool2
0x140002bae  nop     dword ptr [rax+rax+00h]
0x140002bb3  mov     rbx, rax
0x140002bb6  test    rax, rax
0x140002bb9  jz      short loc_140002C06
0x140002bbb  mov     [rax], r14
0x140002bbe  mov     edx, 0Fh
0x140002bc3  mov     [rax+8], rbp
0x140002bc7  mov     rcx, rbx
0x140002bca  mov     [rax+10h], rsi
0x140002bce  mov     [rax+18h], rdi
0x140002bd2  mov     eax, [rsp+48h+ReconfigBufferSize]
0x140002bd6  mov     [rbx+20h], eax
0x140002bd9  mov     eax, [rsp+48h+Operation]
0x140002bdd  mov     [rbx+24h], eax
0x140002be0  call    TdiHandleSerializedRequest
0x140002be5  xor     edx, edx; Tag
0x140002be7  mov     rcx, rbx; P
0x140002bea  mov     edi, eax
0x140002bec  call    cs:__imp_ExFreePoolWithTag
0x140002bf3  nop     dword ptr [rax+rax+00h]
0x140002bf8  mov     eax, edi
0x140002bfa  add     rsp, 20h
0x140002bfe  pop     r14
0x140002c00  pop     rdi
0x140002c01  pop     rsi
0x140002c02  pop     rbp
0x140002c03  pop     rbx
0x140002c04  retn
0x140002c06  mov     eax, 0C000009Ah
0x140002c0b  add     rsp, 20h
0x140002c0f  pop     r14
0x140002c11  pop     rdi
0x140002c12  pop     rsi
0x140002c13  pop     rbp
0x140002c14  pop     rbx
0x140002c15  retn
```
