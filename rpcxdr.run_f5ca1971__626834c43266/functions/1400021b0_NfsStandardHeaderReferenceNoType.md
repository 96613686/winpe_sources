# NfsStandardHeaderReferenceNoType

- ea: `0x1400021b0`
- end: `0x1400021df`
- name: `NfsStandardHeaderReferenceNoType`
- size: `47`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x140002288`
- `0x140002514`
- `0x140004c50`
- `0x140006170`
- `0x140006228`
- `0x140006b70`
- `0x140007640`
- `0x140007b48`
- `0x14000a18c`
- `0x14000b340`
- `0x14000bb64`
- `0x14000d300`
- `0x14000f770`

## callees

- `0x1400021b0`
- `0x1400122e0`

## pseudocode

```c
__int64 __fastcall NfsStandardHeaderReferenceNoType(__int64 a1)
{
  signed __int32 v1; // ebx

  v1 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 1u);
  if ( NfsRefHistoryTracingpGlobal )
    NfsReferenceHistoryCaptureRecord((_DWORD *)a1, v1 + 1, 0);
  return (unsigned int)(v1 + 1);
}

```

## disassembly

```asm
0x1400021b0  push    rbx
0x1400021b2  sub     rsp, 20h
0x1400021b6  mov     ebx, 1
0x1400021bb  lock xadd [rcx+4], ebx
0x1400021c0  cmp     cs:NfsRefHistoryTracingpGlobal, 0
0x1400021c8  jz      short loc_1400021D5
0x1400021ca  xor     r8d, r8d
0x1400021cd  lea     edx, [rbx+1]
0x1400021d0  call    NfsReferenceHistoryCaptureRecord
0x1400021d5  lea     eax, [rbx+1]
0x1400021d8  add     rsp, 20h
0x1400021dc  pop     rbx
0x1400021dd  retn
```
