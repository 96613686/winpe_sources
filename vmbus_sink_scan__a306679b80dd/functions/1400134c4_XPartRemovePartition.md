# XPartRemovePartition

- ea: `0x1400134c4`
- end: `0x140013604`
- name: `XPartRemovePartition`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140013a24`
- `0x14002e584`
- `0x14002ee70`

## callees

- `0x14001269c`
- `0x140012794`
- `0x140012a30`
- `0x1400134c4`
- `0x140017190`
- `0x14002d908`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14001357f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001357f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001351a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001351a`
- `ntoskrnl!KeInitializeEvent` at `0x1400135bb`
- `ntoskrnl!KeInitializeEvent` at `0x1400135bb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400135f1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400135f1`

## pseudocode

```c
NTSTATUS __fastcall XPartRemovePartition(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rax
  void (__fastcall *v7)(__int64); // rax
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qic(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, *(_QWORD *)(a1 + 120));
  }
  ExAcquireFastMutex(&FastMutex);
  v4 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 )
  {
    if ( *(_QWORD *)(v4 + 8) != a1 || (v5 = *(_QWORD **)(a1 + 8), *v5 != a1) )
LABEL_10:
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
  }
  v6 = qword_1400206D8;
  if ( *(__int64 **)(qword_1400206D8 + 8) != &qword_1400206D8 )
    goto LABEL_10;
  *(_QWORD *)(a1 + 8) = &qword_1400206D8;
  *(_QWORD *)a1 = v6;
  *(_QWORD *)(v6 + 8) = a1;
  qword_1400206D8 = a1;
  *(_BYTE *)(a1 + 320) = 1;
  ExReleaseFastMutex(&FastMutex);
  v7 = *(void (__fastcall **)(__int64))(a1 + 1024);
  if ( v7 )
    v7(a1);
  ChCleanupPartition(a1);
  XPartCleanupMessages(a1);
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  *(_QWORD *)(a1 + 192) = &Event;
  XPartDeref(a1);
  return KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x1400134c4  push    rbx
0x1400134c6  sub     rsp, 50h
0x1400134ca  xorps   xmm0, xmm0
0x1400134cd  xor     eax, eax
0x1400134cf  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x1400134d4  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x1400134d9  mov     rbx, rcx
0x1400134dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400134e3  lea     rax, WPP_GLOBAL_Control
0x1400134ea  cmp     rcx, rax
0x1400134ed  jz      short loc_140013513
0x1400134ef  test    dword ptr [rcx+2Ch], 1000000h
0x1400134f6  jz      short loc_140013513
0x1400134f8  cmp     byte ptr [rcx+29h], 4
0x1400134fc  jb      short loc_140013513
0x1400134fe  mov     rax, [rbx+78h]
0x140013502  mov     r9, rbx
0x140013505  mov     rcx, [rcx+18h]
0x140013509  mov     [rsp+58h+Timeout], rax
0x14001350e  call    WPP_SF_qic
0x140013513  lea     rcx, FastMutex; FastMutex
0x14001351a  call    cs:__imp_ExAcquireFastMutex
0x140013521  nop     dword ptr [rax+rax+00h]
0x140013526  mov     rax, [rbx]
0x140013529  test    rax, rax
0x14001352c  jz      short loc_140013544
0x14001352e  cmp     [rax+8], rbx
0x140013532  jnz     short loc_140013558
0x140013534  mov     rcx, [rbx+8]
0x140013538  cmp     [rcx], rbx
0x14001353b  jnz     short loc_140013558
0x14001353d  mov     [rcx], rax
0x140013540  mov     [rax+8], rcx
0x140013544  mov     rax, cs:qword_1400206D8
0x14001354b  lea     rcx, qword_1400206D8
0x140013552  cmp     [rax+8], rcx
0x140013556  jz      short loc_14001355F
0x140013558  mov     ecx, 3
0x14001355d  int     29h; Win8: RtlFailFast(ecx)
0x14001355f  mov     [rbx+8], rcx
0x140013563  lea     rcx, FastMutex; FastMutex
0x14001356a  mov     [rbx], rax
0x14001356d  mov     [rax+8], rbx
0x140013571  mov     cs:qword_1400206D8, rbx
0x140013578  mov     byte ptr [rbx+140h], 1
0x14001357f  call    cs:__imp_ExReleaseFastMutex
0x140013586  nop     dword ptr [rax+rax+00h]
0x14001358b  mov     rax, [rbx+400h]
0x140013592  test    rax, rax
0x140013595  jz      short loc_14001359F
0x140013597  mov     rcx, rbx
0x14001359a  call    _guard_dispatch_icall
0x14001359f  mov     rcx, rbx
0x1400135a2  call    ChCleanupPartition
0x1400135a7  mov     rcx, rbx
0x1400135aa  call    XPartCleanupMessages
0x1400135af  xor     r8d, r8d; State
0x1400135b2  lea     rcx, [rsp+58h+Event]; Event
0x1400135b7  lea     edx, [r8+1]; Type
0x1400135bb  call    cs:__imp_KeInitializeEvent
0x1400135c2  nop     dword ptr [rax+rax+00h]
0x1400135c7  lea     rax, [rsp+58h+Event]
0x1400135cc  mov     rcx, rbx
0x1400135cf  mov     [rbx+0C0h], rax
0x1400135d6  call    XPartDeref
0x1400135db  xor     r9d, r9d; Alertable
0x1400135de  mov     [rsp+58h+Timeout], 0; Timeout
0x1400135e7  xor     r8d, r8d; WaitMode
0x1400135ea  lea     rcx, [rsp+58h+Event]; Object
0x1400135ef  xor     edx, edx; WaitReason
0x1400135f1  call    cs:__imp_KeWaitForSingleObject
0x1400135f8  nop     dword ptr [rax+rax+00h]
0x1400135fd  add     rsp, 50h
0x140013601  pop     rbx
0x140013602  retn
```
