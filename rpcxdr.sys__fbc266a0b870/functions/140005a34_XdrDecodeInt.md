# XdrDecodeInt

- ea: `0x140005a34`
- end: `0x140005a6a`
- name: `XdrDecodeInt`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x140002974`
- `0x140002f50`
- `0x140003d68`
- `0x140003dbc`
- `0x140003e94`
- `0x140003f80`
- `0x140004164`
- `0x1400042c4`
- `0x14000449c`

## callees

- `0x14000220c`
- `0x140005a34`
- `0x140005a70`
- `0x14001530c`

## pseudocode

```c
__int64 __fastcall XdrDecodeInt(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9

  v3 = a1;
  if ( *(int *)(a1 + 264) < 0 || (unsigned int)OncRpcBufMgrGetCurrentValidLengthRemaining(a1 + 32, a2, a3, a1) < 4 )
    return XdrDecodeIntSlow(v3);
  else
    return XdrDecodeIntUnsafe(v3);
}

```

## disassembly

```asm
0x140005a34  sub     rsp, 28h
0x140005a38  cmp     dword ptr [rcx+108h], 0
0x140005a3f  mov     r9, rcx
0x140005a42  jl      short loc_140005A5C
0x140005a44  add     rcx, 20h ; ' '
0x140005a48  call    OncRpcBufMgrGetCurrentValidLengthRemaining
0x140005a4d  cmp     eax, 4
0x140005a50  jb      short loc_140005A5C
0x140005a52  mov     rcx, r9
0x140005a55  call    XdrDecodeIntUnsafe
0x140005a5a  jmp     short loc_140005A64
0x140005a5c  mov     rcx, r9
0x140005a5f  call    XdrDecodeIntSlow
0x140005a64  add     rsp, 28h
0x140005a68  retn
```
