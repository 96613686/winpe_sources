# WinSAT::TimeGate::TimeGate(_LARGE_INTEGER)

- ea: `0x140060520`
- end: `0x14006056e`
- name: `??0TimeGate@WinSAT@@QEAA@T_LARGE_INTEGER@@@Z`
- size: `78`
- prototype: `union _LARGE_INTEGER *__fastcall(union _LARGE_INTEGER *this, union _LARGE_INTEGER)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140061b44`

## import_xrefs

- `KERNEL32!GetThreadPriority` at `0x140060548`
- `KERNEL32!GetThreadPriority` at `0x140060548`
- `KERNEL32!GetCurrentThread` at `0x14006053f`
- `KERNEL32!GetCurrentThread` at `0x140060551`
- `KERNEL32!GetCurrentThread` at `0x14006053f`
- `KERNEL32!GetCurrentThread` at `0x140060551`
- `KERNEL32!SetThreadPriority` at `0x14006055f`
- `KERNEL32!SetThreadPriority` at `0x14006055f`
- `WINMM!timeBeginPeriod` at `0x140060539`
- `WINMM!timeBeginPeriod` at `0x140060539`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
union _LARGE_INTEGER *__fastcall WinSAT::TimeGate::TimeGate(union _LARGE_INTEGER *this, union _LARGE_INTEGER a2)
{
  HANDLE CurrentThread; // rax
  HANDLE v4; // rax

  this->QuadPart = 0;
  this[1] = a2;
  timeBeginPeriod(1u);
  CurrentThread = GetCurrentThread();
  this[2].LowPart = GetThreadPriority(CurrentThread);
  v4 = GetCurrentThread();
  SetThreadPriority(v4, 15);
  return this;
}

```

## disassembly

```asm
0x140060520  push    rbx
0x140060522  sub     rsp, 20h
0x140060526  mov     rbx, rcx
0x140060529  mov     qword ptr [rcx], 0
0x140060530  mov     [rcx+8], rdx
0x140060534  mov     ecx, 1; uPeriod
0x140060539  call    cs:__imp_timeBeginPeriod
0x14006053f  call    cs:__imp_GetCurrentThread
0x140060545  mov     rcx, rax; hThread
0x140060548  call    cs:__imp_GetThreadPriority
0x14006054e  mov     [rbx+10h], eax
0x140060551  call    cs:__imp_GetCurrentThread
0x140060557  mov     rcx, rax; hThread
0x14006055a  mov     edx, 0Fh; nPriority
0x14006055f  call    cs:__imp_SetThreadPriority
0x140060565  mov     rax, rbx
0x140060568  add     rsp, 20h
0x14006056c  pop     rbx
0x14006056d  retn
```
