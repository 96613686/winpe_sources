# _tlgWriteAgg

- ea: `0x1800114e0`
- end: `0x180011565`
- name: `_tlgWriteAgg`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x180001180`
- `0x180001338`

## callees

- `0x18001156c`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        struct _EVENT_DATA_DESCRIPTOR *a5)
{
  ULONGLONG v5; // rax
  unsigned __int16 *v6; // rdx
  EVENT_DESCRIPTOR v8; // [rsp+20h] [rbp-18h] BYREF

  *(_DWORD *)&v8.Id = *a2 << 24;
  *(_DWORD *)&v8.Level = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = (unsigned __int16 *)(a2 + 11);
  v8.Keyword = v5;
  a5->Ptr = *(_QWORD *)(a1 + 8);
  a5->Size = **(unsigned __int16 **)(a1 + 8);
  a5[1].Ptr = (ULONGLONG)v6;
  a5->Reserved = 2;
  a5[1].Size = *v6;
  a5[1].Reserved = 1;
  return TlgAggregateAbsorbEvent(a1, &v8, a4, a5);
}

```

## disassembly

```asm
0x1800114e0  sub     rsp, 38h
0x1800114e4  movzx   eax, byte ptr [rdx]
0x1800114e7  mov     r11, rcx
0x1800114ea  shl     eax, 18h
0x1800114ed  mov     r8d, r9d
0x1800114f0  mov     r9, [rsp+38h+arg_20]
0x1800114f5  mov     [rsp+38h+var_18], eax
0x1800114f9  movzx   eax, word ptr [rdx+1]
0x1800114fd  mov     [rsp+38h+var_14], eax
0x180011501  mov     rax, [rdx+3]
0x180011505  add     rdx, 0Bh
0x180011509  mov     [rsp+38h+var_10], rax
0x18001150e  mov     rax, [rcx+8]
0x180011512  mov     [r9], rax
0x180011515  mov     rax, [rcx+8]
0x180011519  movzx   ecx, word ptr [rax]
0x18001151c  mov     [r9+8], ecx
0x180011520  lea     rcx, _TraceLoggingMetadata
0x180011527  mov     [r9+10h], rdx
0x18001152b  mov     dword ptr [r9+0Ch], 2
0x180011533  movzx   eax, word ptr [rdx]
0x180011536  lea     rdx, [rsp+38h+var_18]
0x18001153b  mov     [r9+18h], eax
0x18001153f  lea     rax, _TraceLoggingMetadataEnd
0x180011546  sub     eax, ecx
0x180011548  mov     dword ptr [r9+1Ch], 1
0x180011550  mov     dword ptr [rsp+38h+arg_20], eax
0x180011554  mov     rcx, r11
0x180011557  mov     eax, dword ptr [rsp+38h+arg_20]
0x18001155b  call    TlgAggregateAbsorbEvent
0x180011560  add     rsp, 38h
0x180011564  retn
```
