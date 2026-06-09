# WinHvpThrottleVpDispatchThreadNoCheck

- ea: `0x140004118`
- end: `0x1400041f2`
- name: `WinHvpThrottleVpDispatchThreadNoCheck`
- size: `218`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000b380`

## callees

- `0x140004118`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004181`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004181`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004137`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004137`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400041db`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400041db`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x14000414b`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x14000414b`
- `ntoskrnl!ExSetTimer` at `0x1400041c6`
- `ntoskrnl!ExSetTimer` at `0x1400041c6`

## pseudocode

```c
void __fastcall WinHvpThrottleVpDispatchThreadNoCheck(_QWORD *a1)
{
  KIRQL v2; // si
  unsigned __int64 v3; // r10
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v2 = KeAcquireSpinLockRaiseToDpc(a1 + 11);
  v3 = KeQueryInterruptTimePrecise(&v4);
  a1[10] = a1[8] + dword_140016188;
  if ( a1[10] > v3 )
  {
    if ( _InterlockedIncrement64(a1 - 1) <= 1 )
      __fastfail(0xEu);
    ExSetTimer(a1[6], v3 - a1[10], 0, 0);
    KeSetActualBasePriorityThread(a1[5], 1);
  }
  else
  {
    a1[10] = -1;
  }
  KeReleaseSpinLock(a1 + 11, v2);
}

```

## disassembly

```asm
0x140004118  mov     [rsp+arg_8], rbx
0x14000411d  mov     [rsp+arg_10], rsi
0x140004122  push    rdi
0x140004123  sub     rsp, 20h
0x140004127  mov     rbx, rcx
0x14000412a  mov     [rsp+28h+arg_0], 0
0x140004133  add     rcx, 58h ; 'X'; SpinLock
0x140004137  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000413e  nop     dword ptr [rax+rax+00h]
0x140004143  lea     rcx, [rsp+28h+arg_0]
0x140004148  mov     sil, al
0x14000414b  call    cs:__imp_KeQueryInterruptTimePrecise
0x140004152  nop     dword ptr [rax+rax+00h]
0x140004157  movsxd  rdx, cs:dword_140016188
0x14000415e  mov     r10, rax
0x140004161  add     rdx, [rbx+40h]
0x140004165  mov     [rbx+50h], rdx
0x140004169  mov     rdx, [rbx+50h]
0x14000416d  cmp     rdx, rax
0x140004170  ja      short loc_14000419E
0x140004172  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x14000417a  mov     dl, sil; NewIrql
0x14000417d  lea     rcx, [rbx+58h]; SpinLock
0x140004181  call    cs:__imp_KeReleaseSpinLock
0x140004188  nop     dword ptr [rax+rax+00h]
0x14000418d  mov     rbx, [rsp+28h+arg_8]
0x140004192  mov     rsi, [rsp+28h+arg_10]
0x140004197  add     rsp, 20h
0x14000419b  pop     rdi
0x14000419c  retn
0x14000419e  mov     eax, 1
0x1400041a3  lock xadd [rbx-8], rax
0x1400041a9  inc     rax
0x1400041ac  cmp     rax, 1
0x1400041b0  jle     short loc_1400041E9
0x1400041b2  mov     rax, [rbx+50h]
0x1400041b6  xor     r9d, r9d
0x1400041b9  mov     rcx, [rbx+30h]
0x1400041bd  sub     r10, rax
0x1400041c0  mov     rdx, r10
0x1400041c3  xor     r8d, r8d
0x1400041c6  call    cs:__imp_ExSetTimer
0x1400041cd  nop     dword ptr [rax+rax+00h]
0x1400041d2  mov     rcx, [rbx+28h]
0x1400041d6  mov     edx, 1
0x1400041db  call    cs:__imp_KeSetActualBasePriorityThread
0x1400041e2  nop     dword ptr [rax+rax+00h]
0x1400041e7  jmp     short loc_14000417A
0x1400041e9  mov     ecx, 0Eh
0x1400041ee  int     29h; Win8: RtlFailFast(ecx)
0x1400041f0  jmp     short loc_1400041B2
```
