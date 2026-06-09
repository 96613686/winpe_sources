# OutpDequeuePacket

- ea: `0x140006920`
- end: `0x1400069b9`
- name: `OutpDequeuePacket`
- size: `153`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006700`
- `0x140009a34`
- `0x140009d8c`

## callees

- `0x140006920`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x140006981`
- `HAL!KeQueryPerformanceCounter` at `0x140006981`

## pseudocode

```c
__int64 __fastcall OutpDequeuePacket(__int64 a1, __int64 *a2)
{
  __int64 *v4; // rcx
  __int64 **v5; // rax
  __int64 result; // rax
  bool v7; // zf

  v4 = (__int64 *)*a2;
  if ( *(__int64 **)(*a2 + 8) != a2 || (v5 = (__int64 **)a2[1], *v5 != a2) )
    __fastfail(3u);
  *v5 = v4;
  v4[1] = (__int64)v5;
  result = a1 + 272;
  if ( *(_QWORD *)result == result && *(_DWORD *)(a1 + 264) )
    *(_DWORD *)(a1 + 264) = 1;
  if ( *((_DWORD *)a2 + 4) == 1 && *(a2 - 3) && KmclPerformanceCounterTimingCounters )
  {
    result = *(_QWORD *)&KeQueryPerformanceCounter(0) - *(a2 - 3);
    v7 = KmclPerformanceCounterTimingCounters == 0;
    *(a2 - 3) = result;
    if ( !v7 )
      *(_QWORD *)(a1 + 496) += result;
  }
  return result;
}

```

## disassembly

```asm
0x140006920  mov     [rsp+arg_0], rbx
0x140006925  push    rdi
0x140006926  sub     rsp, 20h
0x14000692a  mov     rdi, rcx
0x14000692d  mov     rbx, rdx
0x140006930  mov     rcx, [rdx]
0x140006933  cmp     [rcx+8], rdx
0x140006937  jnz     short loc_1400069B2
0x140006939  mov     rax, [rdx+8]
0x14000693d  cmp     [rax], rdx
0x140006940  jnz     short loc_1400069B2
0x140006942  mov     [rax], rcx
0x140006945  mov     [rcx+8], rax
0x140006949  lea     rax, [rdi+110h]
0x140006950  cmp     [rax], rax
0x140006953  jnz     short loc_140006968
0x140006955  cmp     dword ptr [rdi+108h], 0
0x14000695c  jz      short loc_140006968
0x14000695e  mov     dword ptr [rdi+108h], 1
0x140006968  cmp     dword ptr [rdx+10h], 1
0x14000696c  jnz     short loc_1400069A6
0x14000696e  cmp     qword ptr [rdx-18h], 0
0x140006973  jz      short loc_1400069A6
0x140006975  cmp     cs:KmclPerformanceCounterTimingCounters, 0
0x14000697d  jz      short loc_1400069A6
0x14000697f  xor     ecx, ecx; PerformanceFrequency
0x140006981  call    cs:__imp_KeQueryPerformanceCounter
0x140006988  nop     dword ptr [rax+rax+00h]
0x14000698d  sub     rax, [rbx-18h]
0x140006991  cmp     cs:KmclPerformanceCounterTimingCounters, 0
0x140006999  mov     [rbx-18h], rax
0x14000699d  jz      short loc_1400069A6
0x14000699f  add     [rdi+1F0h], rax
0x1400069a6  mov     rbx, [rsp+28h+arg_0]
0x1400069ab  add     rsp, 20h
0x1400069af  pop     rdi
0x1400069b0  retn
0x1400069b2  mov     ecx, 3
0x1400069b7  int     29h; Win8: RtlFailFast(ecx)
```
