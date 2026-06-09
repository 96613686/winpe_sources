# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180001010`
- end: `0x1800010a7`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800010b0`
- `0x1800010f8`
- `0x180001158`
- `0x18000140c`
- `0x18000188c`
- `0x180001938`
- `0x180001998`
- `0x180001c70`
- `0x180001d44`
- `0x18000f444`
- `0x180028ff8`
- `0x180029078`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000109c`
- `ntdll!EtwEventWriteTransfer` at `0x18000109c`

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
  return ((__int64 (__fastcall *)(_QWORD, _DWORD *, __int64, __int64, int, __int64))EtwEventWriteTransfer)(
           *(_QWORD *)(a1 + 32),
           v9,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 48h
0x180001014  movzx   eax, byte ptr [rdx]
0x180001017  mov     r11, rcx
0x18000101a  shl     eax, 18h
0x18000101d  mov     r10, r8
0x180001020  mov     r8, [rsp+48h+arg_28]
0x180001025  mov     [rsp+48h+var_18], eax
0x180001029  movzx   eax, word ptr [rdx+1]
0x18000102d  mov     [rsp+48h+var_14], eax
0x180001031  mov     rax, [rdx+3]
0x180001035  add     rdx, 0Bh
0x180001039  mov     [rsp+48h+var_10], rax
0x18000103e  mov     rax, [rcx+8]
0x180001042  mov     [r8], rax
0x180001045  mov     rax, [rcx+8]
0x180001049  mov     [rsp+48h+var_20], r8
0x18000104e  movzx   ecx, word ptr [rax]
0x180001051  mov     [r8+8], ecx
0x180001055  lea     rcx, _TraceLoggingMetadata
0x18000105c  mov     [r8+10h], rdx
0x180001060  mov     dword ptr [r8+0Ch], 2
0x180001068  movzx   eax, word ptr [rdx]
0x18000106b  lea     rdx, [rsp+48h+var_18]
0x180001070  mov     [r8+18h], eax
0x180001074  lea     rax, _TraceLoggingMetadataEnd
0x18000107b  sub     eax, ecx
0x18000107d  mov     dword ptr [r8+1Ch], 1
0x180001085  mov     dword ptr [rsp+48h+arg_28], eax
0x180001089  mov     r8, r10
0x18000108c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001090  mov     eax, [rsp+48h+arg_20]
0x180001094  mov     rcx, [r11+20h]
0x180001098  mov     [rsp+48h+var_28], eax
0x18000109c  call    cs:__imp_EtwEventWriteTransfer
0x1800010a2  add     rsp, 48h
0x1800010a6  retn
```
