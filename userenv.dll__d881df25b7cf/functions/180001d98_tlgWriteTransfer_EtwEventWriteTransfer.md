# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180001d98`
- end: `0x180001e36`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001044`
- `0x18000116c`
- `0x1800012a4`
- `0x180001558`
- `0x1800015e8`
- `0x18000188c`
- `0x180001b84`
- `0x180013424`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180001e24`
- `ntdll!EtwEventWriteTransfer` at `0x180001e24`

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
0x180001d98  sub     rsp, 48h
0x180001d9c  movzx   eax, byte ptr [rdx]
0x180001d9f  mov     r11, rcx
0x180001da2  shl     eax, 18h
0x180001da5  mov     r10, r8
0x180001da8  mov     r8, [rsp+48h+arg_28]
0x180001dad  mov     [rsp+48h+var_18], eax
0x180001db1  movzx   eax, word ptr [rdx+1]
0x180001db5  mov     [rsp+48h+var_14], eax
0x180001db9  mov     rax, [rdx+3]
0x180001dbd  add     rdx, 0Bh
0x180001dc1  mov     [rsp+48h+var_10], rax
0x180001dc6  mov     rax, [rcx+8]
0x180001dca  mov     [r8], rax
0x180001dcd  mov     rax, [rcx+8]
0x180001dd1  mov     [rsp+48h+var_20], r8
0x180001dd6  movzx   ecx, word ptr [rax]
0x180001dd9  mov     [r8+8], ecx
0x180001ddd  lea     rcx, _TraceLoggingMetadata
0x180001de4  mov     [r8+10h], rdx
0x180001de8  mov     dword ptr [r8+0Ch], 2
0x180001df0  movzx   eax, word ptr [rdx]
0x180001df3  lea     rdx, [rsp+48h+var_18]
0x180001df8  mov     [r8+18h], eax
0x180001dfc  lea     rax, _TraceLoggingMetadataEnd
0x180001e03  sub     eax, ecx
0x180001e05  mov     dword ptr [r8+1Ch], 1
0x180001e0d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001e11  mov     r8, r10
0x180001e14  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001e18  mov     eax, [rsp+48h+arg_20]
0x180001e1c  mov     rcx, [r11+20h]
0x180001e20  mov     [rsp+48h+var_28], eax
0x180001e24  call    cs:__imp_EtwEventWriteTransfer
0x180001e2b  nop     dword ptr [rax+rax+00h]
0x180001e30  add     rsp, 48h
0x180001e34  retn
```
