# WinHvpFreeOverlayPages

- ea: `0x140005d3c`
- end: `0x140005dc6`
- name: `WinHvpFreeOverlayPages`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005ae0`
- `0x140006824`

## callees

- `0x140005e60`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140005da3`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005da3`
- `ntoskrnl!ExAcquireFastMutex` at `0x140005d5e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140005d5e`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x140005d76`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x140005d76`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x140005d90`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x140005d90`

## pseudocode

```c
__int64 __fastcall WinHvpFreeOverlayPages(__int64 a1)
{
  _QWORD *v1; // rax
  struct _MDL *v2; // rbx
  _QWORD Buffer[3]; // [rsp+20h] [rbp-18h] BYREF

  Buffer[0] = a1;
  Buffer[1] = 0;
  ExAcquireFastMutex(&WinHvpOverlayTableLock);
  v1 = RtlLookupElementGenericTable(&WinHvpOverlayTable, Buffer);
  v2 = (struct _MDL *)v1[1];
  RtlDeleteElementGenericTable(&WinHvpOverlayTable, v1);
  ExReleaseFastMutex(&WinHvpOverlayTableLock);
  return WinHvpReclaimAndFreeHypervisorVisiblePages(v2);
}

```

## disassembly

```asm
0x140005d3c  mov     [rsp+arg_0], rbx
0x140005d41  push    rdi
0x140005d42  sub     rsp, 30h
0x140005d46  mov     [rsp+38h+Buffer], rcx
0x140005d4b  mov     dil, dl
0x140005d4e  lea     rcx, WinHvpOverlayTableLock; FastMutex
0x140005d55  mov     [rsp+38h+var_10], 0
0x140005d5e  call    cs:__imp_ExAcquireFastMutex
0x140005d65  nop     dword ptr [rax+rax+00h]
0x140005d6a  lea     rdx, [rsp+38h+Buffer]; Buffer
0x140005d6f  lea     rcx, WinHvpOverlayTable; Table
0x140005d76  call    cs:__imp_RtlLookupElementGenericTable
0x140005d7d  nop     dword ptr [rax+rax+00h]
0x140005d82  mov     rdx, rax; Buffer
0x140005d85  lea     rcx, WinHvpOverlayTable; Table
0x140005d8c  mov     rbx, [rax+8]
0x140005d90  call    cs:__imp_RtlDeleteElementGenericTable
0x140005d97  nop     dword ptr [rax+rax+00h]
0x140005d9c  lea     rcx, WinHvpOverlayTableLock; FastMutex
0x140005da3  call    cs:__imp_ExReleaseFastMutex
0x140005daa  nop     dword ptr [rax+rax+00h]
0x140005daf  mov     dl, dil
0x140005db2  mov     rcx, rbx; MemoryDescriptorList
0x140005db5  call    WinHvpReclaimAndFreeHypervisorVisiblePages
0x140005dba  mov     rbx, [rsp+38h+arg_0]
0x140005dbf  add     rsp, 30h
0x140005dc3  pop     rdi
0x140005dc4  retn
```
