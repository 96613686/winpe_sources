# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x18000163c`
- end: `0x1800016d3`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180019824`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800016c8`
- `ntdll!EtwEventWriteTransfer` at `0x1800016c8`

## pseudocode

```c
__int64 __fastcall tlgWriteTransfer_EtwEventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // rax
  unsigned __int16 *v7; // rdx
  _DWORD v9[2]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+38h] [rbp-10h]

  v9[0] = *a2 << 24;
  v9[1] = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  v10 = v6;
  *(_QWORD *)a6 = *(_QWORD *)(a1 + 8);
  *(_DWORD *)(a6 + 8) = **(unsigned __int16 **)(a1 + 8);
  *(_QWORD *)(a6 + 16) = v7;
  *(_DWORD *)(a6 + 12) = 2;
  *(_DWORD *)(a6 + 24) = *v7;
  *(_DWORD *)(a6 + 28) = 1;
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v9, a3);
}

```

## disassembly

```asm
0x18000163c  sub     rsp, 48h
0x180001640  movzx   eax, byte ptr [rdx]
0x180001643  mov     r11, rcx
0x180001646  shl     eax, 18h
0x180001649  mov     r10, r8
0x18000164c  mov     r8, [rsp+48h+arg_28]
0x180001651  mov     [rsp+48h+var_18], eax
0x180001655  movzx   eax, word ptr [rdx+1]
0x180001659  mov     [rsp+48h+var_14], eax
0x18000165d  mov     rax, [rdx+3]
0x180001661  add     rdx, 0Bh
0x180001665  mov     [rsp+48h+var_10], rax
0x18000166a  mov     rax, [rcx+8]
0x18000166e  mov     [r8], rax
0x180001671  mov     rax, [rcx+8]
0x180001675  mov     [rsp+48h+var_20], r8
0x18000167a  movzx   ecx, word ptr [rax]
0x18000167d  mov     [r8+8], ecx
0x180001681  lea     rcx, _TraceLoggingMetadata
0x180001688  mov     [r8+10h], rdx
0x18000168c  mov     dword ptr [r8+0Ch], 2
0x180001694  movzx   eax, word ptr [rdx]
0x180001697  lea     rdx, [rsp+48h+var_18]
0x18000169c  mov     [r8+18h], eax
0x1800016a0  lea     rax, _TraceLoggingMetadataEnd
0x1800016a7  sub     eax, ecx
0x1800016a9  mov     dword ptr [r8+1Ch], 1
0x1800016b1  mov     dword ptr [rsp+48h+arg_28], eax
0x1800016b5  mov     r8, r10
0x1800016b8  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800016bc  mov     eax, [rsp+48h+arg_20]
0x1800016c0  mov     rcx, [r11+20h]
0x1800016c4  mov     [rsp+48h+var_28], eax
0x1800016c8  call    cs:__imp_EtwEventWriteTransfer
0x1800016ce  add     rsp, 48h
0x1800016d2  retn
```
