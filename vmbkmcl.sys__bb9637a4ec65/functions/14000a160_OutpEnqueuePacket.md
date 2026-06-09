# OutpEnqueuePacket

- ea: `0x14000a160`
- end: `0x14000a1c3`
- name: `OutpEnqueuePacket`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400037e0`
- `0x140004cc0`
- `0x140005750`

## callees

- `0x14000a160`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14000a182`
- `HAL!KeQueryPerformanceCounter` at `0x14000a182`

## pseudocode

```c
__int64 __fastcall OutpEnqueuePacket(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  _QWORD *v5; // rcx

  if ( *(_DWORD *)(a2 + 16) == 1 && KmclPerformanceCounterTimingCounters )
    *(LARGE_INTEGER *)(a2 - 24) = KeQueryPerformanceCounter(0);
  result = a1 + 272;
  v5 = *(_QWORD **)(a1 + 280);
  if ( *v5 != a1 + 272 )
    __fastfail(3u);
  *(_QWORD *)a2 = result;
  *(_QWORD *)(a2 + 8) = v5;
  *v5 = a2;
  *(_QWORD *)(a1 + 280) = a2;
  return result;
}

```

## disassembly

```asm
0x14000a160  mov     [rsp+arg_0], rbx
0x14000a165  push    rdi
0x14000a166  sub     rsp, 20h
0x14000a16a  cmp     dword ptr [rdx+10h], 1
0x14000a16e  mov     rbx, rdx
0x14000a171  mov     rdi, rcx
0x14000a174  jnz     short loc_14000A192
0x14000a176  cmp     cs:KmclPerformanceCounterTimingCounters, 0
0x14000a17e  jz      short loc_14000A192
0x14000a180  xor     ecx, ecx; PerformanceFrequency
0x14000a182  call    cs:__imp_KeQueryPerformanceCounter
0x14000a189  nop     dword ptr [rax+rax+00h]
0x14000a18e  mov     [rbx-18h], rax
0x14000a192  lea     rax, [rdi+110h]
0x14000a199  mov     rcx, [rax+8]
0x14000a19d  cmp     [rcx], rax
0x14000a1a0  jz      short loc_14000A1A9
0x14000a1a2  mov     ecx, 3
0x14000a1a7  int     29h; Win8: RtlFailFast(ecx)
0x14000a1a9  mov     [rbx], rax
0x14000a1ac  mov     [rbx+8], rcx
0x14000a1b0  mov     [rcx], rbx
0x14000a1b3  mov     [rax+8], rbx
0x14000a1b7  mov     rbx, [rsp+28h+arg_0]
0x14000a1bc  add     rsp, 20h
0x14000a1c0  pop     rdi
0x14000a1c1  retn
```
