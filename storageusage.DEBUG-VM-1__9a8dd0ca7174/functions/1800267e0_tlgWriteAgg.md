# _tlgWriteAgg

- ea: `0x1800267e0`
- end: `0x180026865`
- name: `_tlgWriteAgg`
- size: `133`
- prototype: ``
- caller_count: `52`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025b0`
- `0x180006600`
- `0x1800067d0`
- `0x1800069a0`
- `0x180006bc0`
- `0x180006e00`
- `0x180007050`
- `0x180007240`
- `0x180007450`
- `0x180007660`
- `0x1800078b0`
- `0x180007ad0`
- `0x180007cd0`
- `0x180007f20`
- `0x1800081a4`
- `0x180008430`
- `0x180008680`
- `0x1800088d0`
- `0x180008b20`
- `0x180008d70`
- `0x180008fb0`
- `0x1800091f0`
- `0x180009440`
- `0x1800096e0`
- `0x180009960`
- `0x180009bf0`
- `0x180009e50`
- `0x18000a0a0`
- `0x18000a2f0`
- `0x18000a530`
- `0x18000a780`
- `0x18000a9d0`
- `0x18000ac30`
- `0x18000ae90`
- `0x18000b0e0`
- `0x18000b350`
- `0x18000b510`
- `0x18000b760`
- `0x18000b990`
- `0x18000bbd0`
- `0x18000be20`
- `0x18000c070`
- `0x18000c2a0`
- `0x18000c530`
- `0x18000c770`
- `0x18000c9c0`
- `0x18000cc20`
- `0x18000ce60`
- `0x18000d0a0`
- `0x18000d2f0`

## callees

- `0x180026408`

## pseudocode

```c
__int64 __fastcall tlgWriteAgg(__int64 a1, unsigned __int8 *a2, __int64 a3, unsigned int a4, __int64 a5)
{
  __int64 v5; // rax
  unsigned __int16 *v6; // rdx
  _DWORD v8[2]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h]

  v8[0] = *a2 << 24;
  v8[1] = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = (unsigned __int16 *)(a2 + 11);
  v9 = v5;
  *(_QWORD *)a5 = *(_QWORD *)(a1 + 8);
  *(_DWORD *)(a5 + 8) = **(unsigned __int16 **)(a1 + 8);
  *(_QWORD *)(a5 + 16) = v6;
  *(_DWORD *)(a5 + 12) = 2;
  *(_DWORD *)(a5 + 24) = *v6;
  *(_DWORD *)(a5 + 28) = 1;
  return TlgAggregateAbsorbEvent(a1, v8, a4);
}

```

## disassembly

```asm
0x1800267e0  sub     rsp, 38h
0x1800267e4  movzx   eax, byte ptr [rdx]
0x1800267e7  mov     r11, rcx
0x1800267ea  shl     eax, 18h
0x1800267ed  mov     r8d, r9d
0x1800267f0  mov     r9, [rsp+38h+arg_20]
0x1800267f5  mov     [rsp+38h+var_18], eax
0x1800267f9  movzx   eax, word ptr [rdx+1]
0x1800267fd  mov     [rsp+38h+var_14], eax
0x180026801  mov     rax, [rdx+3]
0x180026805  add     rdx, 0Bh
0x180026809  mov     [rsp+38h+var_10], rax
0x18002680e  mov     rax, [rcx+8]
0x180026812  mov     [r9], rax
0x180026815  mov     rax, [rcx+8]
0x180026819  movzx   ecx, word ptr [rax]
0x18002681c  mov     [r9+8], ecx
0x180026820  lea     rcx, _TraceLoggingMetadata
0x180026827  mov     [r9+10h], rdx
0x18002682b  mov     dword ptr [r9+0Ch], 2
0x180026833  movzx   eax, word ptr [rdx]
0x180026836  lea     rdx, [rsp+38h+var_18]
0x18002683b  mov     [r9+18h], eax
0x18002683f  lea     rax, _TraceLoggingMetadataEnd
0x180026846  sub     eax, ecx
0x180026848  mov     dword ptr [r9+1Ch], 1
0x180026850  mov     dword ptr [rsp+38h+arg_20], eax
0x180026854  mov     rcx, r11
0x180026857  mov     eax, dword ptr [rsp+38h+arg_20]
0x18002685b  call    TlgAggregateAbsorbEvent
0x180026860  add     rsp, 38h
0x180026864  retn
```
