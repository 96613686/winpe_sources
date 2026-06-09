# WofGetVolumeContext

- ea: `0x1400014d0`
- end: `0x140001567`
- name: `WofGetVolumeContext`
- size: `151`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, _QWORD *)`
- caller_count: `33`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b1e8`
- `0x14000b4a4`
- `0x14000edcc`
- `0x1400225f4`
- `0x140022840`
- `0x1400229e4`
- `0x140023390`
- `0x140023bf4`
- `0x140023d80`
- `0x140023ec4`
- `0x140024078`
- `0x140024448`
- `0x140024680`
- `0x1400247b0`
- `0x140024b90`
- `0x140024cb4`
- `0x140024dd4`
- `0x140024f98`
- `0x14002503c`
- `0x14002511c`
- `0x1400325f0`
- `0x1400329c0`
- `0x140033180`
- `0x1400338e0`
- `0x1400346f0`
- `0x1400350c8`
- `0x140036e20`
- `0x140038f90`
- `0x14003b3c0`
- `0x14003b8c0`
- `0x14003d460`
- `0x14003e9fc`
- `0x14003eb10`

## callees

- `0x1400014d0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140001550`
- `ntoskrnl!KeDelayExecutionThread` at `0x140001550`
- `FLTMGR!FltGetInstanceContext` at `0x140001507`
- `FLTMGR!FltGetInstanceContext` at `0x140001507`

## pseudocode

```c
__int64 __fastcall WofGetVolumeContext(PFLT_INSTANCE Instance, _QWORD *a2)
{
  int v4; // edi
  NTSTATUS InstanceContext; // eax
  unsigned int v6; // edx
  PFLT_CONTEXT v7; // rax
  PFLT_CONTEXT Context; // [rsp+48h] [rbp+10h] BYREF
  _LARGE_INTEGER Interval; // [rsp+50h] [rbp+18h] BYREF

  Context = 0;
  Interval.QuadPart = -1000000;
  v4 = 0;
  while ( 1 )
  {
    if ( v4 )
      KeDelayExecutionThread(0, 0, &Interval);
    InstanceContext = FltGetInstanceContext(Instance, &Context);
    v6 = InstanceContext;
    if ( ((InstanceContext + 0x80000000) & 0x80000000) == 0 && InstanceContext != -1073741275 )
      break;
    v7 = Context;
    if ( !Context && (unsigned int)++v4 < 5 )
      continue;
    goto LABEL_8;
  }
  v7 = Context;
LABEL_8:
  *a2 = v7;
  return v6;
}

```

## disassembly

```asm
0x1400014d0  mov     [rsp+arg_0], rbx
0x1400014d5  push    rbp
0x1400014d6  push    rsi
0x1400014d7  push    rdi
0x1400014d8  sub     rsp, 20h
0x1400014dc  mov     rbx, rdx
0x1400014df  mov     [rsp+38h+Context], 0
0x1400014e8  mov     rsi, rcx
0x1400014eb  mov     qword ptr [rsp+38h+Interval], 0FFFFFFFFFFF0BDC0h
0x1400014f4  xor     edi, edi
0x1400014f6  mov     ebp, 80000000h
0x1400014fb  test    edi, edi
0x1400014fd  jnz     short loc_140001547
0x1400014ff  lea     rdx, [rsp+38h+Context]; Context
0x140001504  mov     rcx, rsi; Instance
0x140001507  call    cs:__imp_FltGetInstanceContext
0x14000150e  nop     dword ptr [rax+rax+00h]
0x140001513  mov     edx, eax
0x140001515  lea     ecx, [rax+rbp]
0x140001518  test    ebp, ecx
0x14000151a  jnz     short loc_14000152A
0x14000151c  cmp     eax, 0C0000225h
0x140001521  jz      short loc_14000152A
0x140001523  mov     rax, [rsp+38h+Context]
0x140001528  jmp     short loc_140001534
0x14000152a  mov     rax, [rsp+38h+Context]
0x14000152f  test    rax, rax
0x140001532  jz      short loc_14000155E
0x140001534  mov     [rbx], rax
0x140001537  mov     eax, edx
0x140001539  mov     rbx, [rsp+38h+arg_0]
0x14000153e  add     rsp, 20h
0x140001542  pop     rdi
0x140001543  pop     rsi
0x140001544  pop     rbp
0x140001545  retn
0x140001547  lea     r8, [rsp+38h+Interval]; Interval
0x14000154c  xor     edx, edx; Alertable
0x14000154e  xor     ecx, ecx; WaitMode
0x140001550  call    cs:__imp_KeDelayExecutionThread
0x140001557  nop     dword ptr [rax+rax+00h]
0x14000155c  jmp     short loc_1400014FF
0x14000155e  inc     edi
0x140001560  cmp     edi, 5
0x140001563  jb      short loc_1400014FB
0x140001565  jmp     short loc_140001534
```
