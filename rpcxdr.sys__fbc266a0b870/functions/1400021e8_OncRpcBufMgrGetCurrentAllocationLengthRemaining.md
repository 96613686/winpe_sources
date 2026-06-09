# OncRpcBufMgrGetCurrentAllocationLengthRemaining

- ea: `0x1400021e8`
- end: `0x140002204`
- name: `OncRpcBufMgrGetCurrentAllocationLengthRemaining`
- size: `28`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140005b40`
- `0x140009700`
- `0x14000993c`
- `0x14000d1d0`
- `0x14000df80`

## callees

- `0x1400021e8`
- `0x140002230`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrGetCurrentAllocationLengthRemaining(__int64 a1)
{
  _DWORD *v1; // rcx

  v1 = *(_DWORD **)(a1 + 40);
  if ( v1 )
    return OncRpcBufMgrGetDescriptorAllocationLengthRemaining(v1);
  else
    return 0;
}

```

## disassembly

```asm
0x1400021e8  sub     rsp, 28h
0x1400021ec  mov     rcx, [rcx+28h]
0x1400021f0  test    rcx, rcx
0x1400021f3  jnz     short loc_1400021F9
0x1400021f5  xor     eax, eax
0x1400021f7  jmp     short loc_1400021FE
0x1400021f9  call    OncRpcBufMgrGetDescriptorAllocationLengthRemaining
0x1400021fe  add     rsp, 28h
0x140002202  retn
```
