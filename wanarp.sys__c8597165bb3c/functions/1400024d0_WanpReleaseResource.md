# WanpReleaseResource

- ea: `0x1400024d0`
- end: `0x1400024fd`
- name: `WanpReleaseResource`
- size: `45`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x1400028b0`
- `0x140002e60`
- `0x1400042f0`
- `0x14000e6f8`
- `0x14000f250`
- `0x14000f9c8`
- `0x140010448`
- `0x140011618`
- `0x1400120fc`
- `0x1400124bc`
- `0x140012e3c`
- `0x14001324c`
- `0x140013708`
- `0x140017130`
- `0x140017550`
- `0x140017738`
- `0x140019bc0`
- `0x14001a078`

## callees

- `0x1400024d0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400024eb`
- `ntoskrnl!KeSetEvent` at `0x1400024eb`

## pseudocode

```c
LONG __fastcall WanpReleaseResource(__int64 a1)
{
  LONG result; // eax

  result = _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF);
  if ( result != 1 )
    return KeSetEvent((PRKEVENT)(a1 + 8), 0, 0);
  return result;
}

```

## disassembly

```asm
0x1400024d0  sub     rsp, 28h
0x1400024d4  mov     eax, 0FFFFFFFFh
0x1400024d9  lock xadd [rcx], eax
0x1400024dd  cmp     eax, 1
0x1400024e0  jz      short loc_1400024F7
0x1400024e2  add     rcx, 8; Event
0x1400024e6  xor     r8d, r8d; Wait
0x1400024e9  xor     edx, edx; Increment
0x1400024eb  call    cs:__imp_KeSetEvent
0x1400024f2  nop     dword ptr [rax+rax+00h]
0x1400024f7  add     rsp, 28h
0x1400024fb  retn
```
