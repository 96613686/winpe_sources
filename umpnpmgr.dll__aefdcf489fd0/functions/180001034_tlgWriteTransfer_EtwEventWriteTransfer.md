# _tlgWriteTransfer_EtwEventWriteTransfer

- ea: `0x180001034`
- end: `0x1800010d1`
- name: `_tlgWriteTransfer_EtwEventWriteTransfer`
- size: `157`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001002c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800010c6`
- `ntdll!EtwEventWriteTransfer` at `0x1800010c6`

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
  *(_QWORD *)a6 = off_180023060;
  *(_DWORD *)(a6 + 8) = *(unsigned __int16 *)off_180023060;
  *(_QWORD *)(a6 + 16) = v7;
  *(_DWORD *)(a6 + 12) = 2;
  *(_DWORD *)(a6 + 24) = *v7;
  *(_DWORD *)(a6 + 28) = 1;
  return ((__int64 (__fastcall *)(__int64, _DWORD *, _QWORD, _QWORD, int, __int64))EtwEventWriteTransfer)(
           qword_180023078,
           v9,
           0,
           0,
           9,
           a6);
}

```

## disassembly

```asm
0x180001034  sub     rsp, 48h
0x180001038  movzx   eax, byte ptr [rdx]
0x18000103b  xor     r9d, r9d
0x18000103e  mov     r8, [rsp+48h+arg_28]
0x180001043  shl     eax, 18h
0x180001046  mov     [rsp+48h+var_18], eax
0x18000104a  movzx   eax, word ptr [rdx+1]
0x18000104e  mov     [rsp+48h+var_14], eax
0x180001052  mov     rax, [rdx+3]
0x180001056  add     rdx, 0Bh
0x18000105a  mov     [rsp+48h+var_10], rax
0x18000105f  mov     rax, cs:off_180023060
0x180001066  mov     [r8], rax
0x180001069  mov     rax, cs:off_180023060
0x180001070  mov     [rsp+48h+var_20], r8
0x180001075  mov     [rsp+48h+var_28], 9
0x18000107d  movzx   ecx, word ptr [rax]
0x180001080  mov     [r8+8], ecx
0x180001084  lea     rcx, _TraceLoggingMetadata
0x18000108b  mov     [r8+10h], rdx
0x18000108f  mov     dword ptr [r8+0Ch], 2
0x180001097  movzx   eax, word ptr [rdx]
0x18000109a  lea     rdx, [rsp+48h+var_18]
0x18000109f  mov     [r8+18h], eax
0x1800010a3  lea     rax, _TraceLoggingMetadataEnd
0x1800010aa  sub     eax, ecx
0x1800010ac  mov     dword ptr [r8+1Ch], 1
0x1800010b4  mov     [rsp+48h+arg_20], eax
0x1800010b8  xor     r8d, r8d
0x1800010bb  mov     eax, [rsp+48h+arg_20]
0x1800010bf  mov     rcx, cs:qword_180023078
0x1800010c6  call    cs:__imp_EtwEventWriteTransfer
0x1800010cc  add     rsp, 48h
0x1800010d0  retn
```
