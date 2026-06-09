# VsmmHvPrecommitGpas

- ea: `0x1400f2e74`
- end: `0x1400f2f47`
- name: `VsmmHvPrecommitGpas`
- size: `211`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007d04`
- `0x1400ab81c`
- `0x1400d150c`
- `0x1400f5dc8`

## callees

- `0x140021650`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x1400f2eb2`
- `HAL!KeQueryPerformanceCounter` at `0x1400f2eea`
- `HAL!KeQueryPerformanceCounter` at `0x1400f2eb2`
- `HAL!KeQueryPerformanceCounter` at `0x1400f2eea`
- `winhvr!WinHvPrecommitGpaPages` at `0x1400f2ed7`
- `winhvr!WinHvPrecommitGpaPages` at `0x1400f2ed7`

## pseudocode

```c
__int64 __fastcall VsmmHvPrecommitGpas(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // ebx
  LONGLONG v10; // rax
  __int128 v11; // rtt
  LARGE_INTEGER PerformanceCounter; // [rsp+30h] [rbp-48h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+40h] [rbp-38h] BYREF

  PerformanceFrequency.QuadPart = 0;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v9 = WinHvPrecommitGpaPages(*(_QWORD *)(a1 + 648), a2, a3, a4, a5);
  v11 = 1000000 * (*(_QWORD *)&KeQueryPerformanceCounter(&PerformanceFrequency) - PerformanceCounter.QuadPart);
  v10 = v11 / PerformanceFrequency.QuadPart;
  _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 1528) + 1208LL));
  _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(a1 + 1528) + 1216LL), v10);
  return v9;
}

```

## disassembly

```asm
0x1400f2e74  push    rbx
0x1400f2e76  push    rbp
0x1400f2e77  push    rsi
0x1400f2e78  push    rdi
0x1400f2e79  push    r14
0x1400f2e7b  sub     rsp, 50h
0x1400f2e7f  mov     rax, cs:__security_cookie
0x1400f2e86  xor     rax, rsp
0x1400f2e89  mov     [rsp+78h+var_30], rax
0x1400f2e8e  mov     rbx, [rsp+78h+arg_20]
0x1400f2e96  mov     r14, rcx
0x1400f2e99  xorps   xmm0, xmm0
0x1400f2e9c  xor     eax, eax
0x1400f2e9e  xor     ecx, ecx; PerformanceFrequency
0x1400f2ea0  mov     qword ptr [rsp+78h+PerformanceFrequency], rax
0x1400f2ea5  movups  [rsp+78h+var_48], xmm0
0x1400f2eaa  mov     rbp, r9
0x1400f2ead  mov     rsi, r8
0x1400f2eb0  mov     edi, edx
0x1400f2eb2  call    cs:__imp_KeQueryPerformanceCounter
0x1400f2eb9  nop     dword ptr [rax+rax+00h]
0x1400f2ebe  mov     rcx, [r14+288h]
0x1400f2ec5  mov     r9, rbp
0x1400f2ec8  mov     r8, rsi
0x1400f2ecb  mov     qword ptr [rsp+78h+var_48], rax
0x1400f2ed0  mov     edx, edi
0x1400f2ed2  mov     [rsp+78h+var_58], rbx
0x1400f2ed7  call    cs:__imp_WinHvPrecommitGpaPages
0x1400f2ede  nop     dword ptr [rax+rax+00h]
0x1400f2ee3  lea     rcx, [rsp+78h+PerformanceFrequency]; PerformanceFrequency
0x1400f2ee8  mov     ebx, eax
0x1400f2eea  call    cs:__imp_KeQueryPerformanceCounter
0x1400f2ef1  nop     dword ptr [rax+rax+00h]
0x1400f2ef6  mov     rcx, [r14+5F8h]
0x1400f2efd  mov     qword ptr [rsp+78h+var_48+8], rax
0x1400f2f02  sub     rax, qword ptr [rsp+78h+var_48]
0x1400f2f07  imul    rax, 0F4240h
0x1400f2f0e  cqo
0x1400f2f10  idiv    qword ptr [rsp+78h+PerformanceFrequency]
0x1400f2f15  lock inc qword ptr [rcx+4B8h]
0x1400f2f1d  mov     rcx, [r14+5F8h]
0x1400f2f24  lock add [rcx+4C0h], rax
0x1400f2f2c  mov     eax, ebx
0x1400f2f2e  mov     rcx, [rsp+78h+var_30]
0x1400f2f33  xor     rcx, rsp; StackCookie
0x1400f2f36  call    __security_check_cookie
0x1400f2f3b  add     rsp, 50h
0x1400f2f3f  pop     r14
0x1400f2f41  pop     rdi
0x1400f2f42  pop     rsi
0x1400f2f43  pop     rbp
0x1400f2f44  pop     rbx
0x1400f2f45  retn
```
