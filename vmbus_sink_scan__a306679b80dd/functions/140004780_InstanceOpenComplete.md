# InstanceOpenComplete

- ea: `0x140004780`
- end: `0x1400047e9`
- name: `InstanceOpenComplete`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140002e20`
- `0x140002ed0`
- `0x140004780`
- `0x140017190`

## pseudocode

```c
__int64 __fastcall InstanceOpenComplete(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // edi
  __int64 v5; // rsi

  v3 = a2;
  InstanceWaitLockAcquire(a1, a2, a3);
  v5 = *(_QWORD *)(a1 + 80);
  *(_QWORD *)(a1 + 80) = 0;
  if ( v3 >= 0 )
    *(_BYTE *)(a1 + 304) = 1;
  InstanceWaitLockRelease(a1);
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           v5,
           (unsigned int)v3);
}

```

## disassembly

```asm
0x140004780  mov     [rsp+arg_0], rbx
0x140004785  mov     [rsp+arg_8], rsi
0x14000478a  push    rdi
0x14000478b  sub     rsp, 20h
0x14000478f  mov     edi, edx
0x140004791  mov     rbx, rcx
0x140004794  call    InstanceWaitLockAcquire
0x140004799  mov     rsi, [rbx+50h]
0x14000479d  mov     qword ptr [rbx+50h], 0
0x1400047a5  test    edi, edi
0x1400047a7  js      short loc_1400047B0
0x1400047a9  mov     byte ptr [rbx+130h], 1
0x1400047b0  mov     rcx, rbx
0x1400047b3  call    InstanceWaitLockRelease
0x1400047b8  mov     rax, cs:WdfFunctions_01033
0x1400047bf  mov     r8d, edi
0x1400047c2  mov     rcx, cs:WdfDriverGlobals
0x1400047c9  mov     rdx, rsi
0x1400047cc  mov     rax, [rax+838h]
0x1400047d3  call    _guard_dispatch_icall
0x1400047d8  mov     rbx, [rsp+28h+arg_0]
0x1400047dd  mov     rsi, [rsp+28h+arg_8]
0x1400047e2  add     rsp, 20h
0x1400047e6  pop     rdi
0x1400047e7  retn
```
