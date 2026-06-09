# NfsStandardHeaderDereferenceNoType

- ea: `0x140002170`
- end: `0x1400021a7`
- name: `NfsStandardHeaderDereferenceNoType`
- size: `55`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002f20`
- `0x140004600`
- `0x140005c54`
- `0x140005dc8`
- `0x140006228`
- `0x140006aa0`
- `0x140006ad0`
- `0x1400070c4`
- `0x140007394`
- `0x1400083b8`
- `0x140008f58`
- `0x14000b624`
- `0x14000bb64`
- `0x14000d300`
- `0x140010080`

## callees

- `0x140002170`
- `0x1400122e0`

## pseudocode

```c
__int64 __fastcall NfsStandardHeaderDereferenceNoType(__int64 a1)
{
  unsigned int v2; // eax

  v2 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 4), 0, 0);
  if ( NfsRefHistoryTracingpGlobal )
    NfsReferenceHistoryCaptureRecord((_DWORD *)a1, v2, 1u);
  return (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(a1 + 4));
}

```

## disassembly

```asm
0x140002170  push    rbx
0x140002172  sub     rsp, 20h
0x140002176  xor     edx, edx
0x140002178  mov     rbx, rcx
0x14000217b  xor     eax, eax
0x14000217d  lock cmpxchg [rcx+4], edx
0x140002182  cmp     cs:NfsRefHistoryTracingpGlobal, rdx
0x140002189  jz      short loc_140002196
0x14000218b  lea     r8d, [rdx+1]
0x14000218f  mov     edx, eax
0x140002191  call    NfsReferenceHistoryCaptureRecord
0x140002196  or      eax, 0FFFFFFFFh
0x140002199  lock xadd [rbx+4], eax
0x14000219e  dec     eax
0x1400021a0  add     rsp, 20h
0x1400021a4  pop     rbx
0x1400021a5  retn
```
