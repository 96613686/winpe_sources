# StorDelayExecution

- ea: `0x140033880`
- end: `0x14003396e`
- name: `StorDelayExecution`
- size: `238`
- prototype: `__int64 __fastcall(ULONG MicroSeconds)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14004ee60`
- `0x140054e60`
- `0x14005d3f0`
- `0x140076c38`
- `0x140100c90`
- `0x14010552c`
- `0x140105978`
- `0x14010d960`
- `0x14010da68`
- `0x140113d28`
- `0x140115cdc`
- `0x140116704`
- `0x14011698c`
- `0x140116c0c`
- `0x140116e98`
- `0x14012b754`
- `0x14012b8ac`

## callees

- `0x140033880`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14003391d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003391d`
- `ntoskrnl!ExSetTimer` at `0x1400338fd`
- `ntoskrnl!ExSetTimer` at `0x1400338fd`
- `ntoskrnl!ExDeleteTimer` at `0x140033934`
- `ntoskrnl!ExDeleteTimer` at `0x140033934`
- `ntoskrnl!ExAllocateTimer` at `0x1400338db`
- `ntoskrnl!ExAllocateTimer` at `0x1400338db`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033888`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033888`
- `ntoskrnl!KeDelayExecutionThread` at `0x140033960`
- `ntoskrnl!KeDelayExecutionThread` at `0x140033960`
- `HAL!KeStallExecutionProcessor` at `0x140033949`
- `HAL!KeStallExecutionProcessor` at `0x140033949`

## pseudocode

```c
void __fastcall StorDelayExecution(ULONG MicroSeconds)
{
  __int64 v1; // rbx
  __int64 Timer; // rax
  void *v3; // rbx
  union _LARGE_INTEGER Interval; // [rsp+48h] [rbp+10h] BYREF

  v1 = MicroSeconds;
  if ( KeGetCurrentIrql() >= 2u || (unsigned int)v1 < StorMinimumTimeInterval / 0xAu )
  {
    KeStallExecutionProcessor(v1);
  }
  else
  {
    Interval.QuadPart = -10 * v1;
    if ( (unsigned int)v1 < StorMaximumTimeInterval / 0xAu
      && (Timer = ExAllocateTimer(0, 0, 4), (v3 = (void *)Timer) != 0) )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ExSetTimer)(
        Timer,
        (union _LARGE_INTEGER)Interval.QuadPart,
        0,
        0);
      KeWaitForSingleObject(v3, Executive, 0, 0, 0);
      ExDeleteTimer(v3, 0, 0, 0);
    }
    else
    {
      KeDelayExecutionThread(0, 0, &Interval);
    }
  }
}

```

## disassembly

```asm
0x140033880  push    rbx
0x140033882  sub     rsp, 30h
0x140033886  mov     ebx, ecx
0x140033888  call    cs:__imp_KeGetCurrentIrql
0x14003388f  nop     dword ptr [rax+rax+00h]
0x140033894  cmp     al, 2
0x140033896  jnb     loc_140033947
0x14003389c  mov     eax, 0CCCCCCCDh
0x1400338a1  mul     cs:StorMinimumTimeInterval
0x1400338a7  shr     edx, 3
0x1400338aa  cmp     ebx, edx
0x1400338ac  jb      loc_140033947
0x1400338b2  imul    rdx, rbx, -0Ah
0x1400338b6  mov     eax, 0CCCCCCCDh
0x1400338bb  mov     qword ptr [rsp+38h+Interval], rdx
0x1400338c0  mul     cs:StorMaximumTimeInterval
0x1400338c6  shr     edx, 3
0x1400338c9  cmp     ebx, edx
0x1400338cb  jnb     loc_140033957
0x1400338d1  xor     edx, edx
0x1400338d3  xor     ecx, ecx
0x1400338d5  mov     r8d, 4
0x1400338db  call    cs:__imp_ExAllocateTimer
0x1400338e2  nop     dword ptr [rax+rax+00h]
0x1400338e7  mov     rbx, rax
0x1400338ea  test    rax, rax
0x1400338ed  jz      short loc_140033957
0x1400338ef  mov     rdx, qword ptr [rsp+38h+Interval]
0x1400338f4  xor     r9d, r9d
0x1400338f7  xor     r8d, r8d
0x1400338fa  mov     rcx, rax
0x1400338fd  call    cs:__imp_ExSetTimer
0x140033904  nop     dword ptr [rax+rax+00h]
0x140033909  xor     r9d, r9d; Alertable
0x14003390c  mov     [rsp+38h+Timeout], 0; Timeout
0x140033915  xor     r8d, r8d; WaitMode
0x140033918  xor     edx, edx; WaitReason
0x14003391a  mov     rcx, rbx; Object
0x14003391d  call    cs:__imp_KeWaitForSingleObject
0x140033924  nop     dword ptr [rax+rax+00h]
0x140033929  xor     r9d, r9d
0x14003392c  xor     r8d, r8d
0x14003392f  xor     edx, edx
0x140033931  mov     rcx, rbx
0x140033934  call    cs:__imp_ExDeleteTimer
0x14003393b  nop     dword ptr [rax+rax+00h]
0x140033940  add     rsp, 30h
0x140033944  pop     rbx
0x140033945  retn
0x140033947  mov     ecx, ebx; MicroSeconds
0x140033949  call    cs:__imp_KeStallExecutionProcessor
0x140033950  nop     dword ptr [rax+rax+00h]
0x140033955  jmp     short loc_140033940
0x140033957  lea     r8, [rsp+38h+Interval]; Interval
0x14003395c  xor     edx, edx; Alertable
0x14003395e  xor     ecx, ecx; WaitMode
0x140033960  call    cs:__imp_KeDelayExecutionThread
0x140033967  nop     dword ptr [rax+rax+00h]
0x14003396c  jmp     short loc_140033940
```
