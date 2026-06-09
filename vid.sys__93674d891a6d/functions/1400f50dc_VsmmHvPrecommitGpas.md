# VsmmHvPrecommitGpas

- ea: `0x1400f50dc`
- end: `0x1400f51af`
- name: `VsmmHvPrecommitGpas`
- size: `211`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000743c`
- `0x1400ad5a4`
- `0x1400d3eac`
- `0x1400f8808`

## callees

- `0x140021c60`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x1400f511a`
- `HAL!KeQueryPerformanceCounter` at `0x1400f5152`
- `HAL!KeQueryPerformanceCounter` at `0x1400f511a`
- `HAL!KeQueryPerformanceCounter` at `0x1400f5152`
- `winhvr!WinHvPrecommitGpaPages` at `0x1400f513f`
- `winhvr!WinHvPrecommitGpaPages` at `0x1400f513f`

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
0x1400f50dc  push    rbx
0x1400f50de  push    rbp
0x1400f50df  push    rsi
0x1400f50e0  push    rdi
0x1400f50e1  push    r14
0x1400f50e3  sub     rsp, 50h
0x1400f50e7  mov     rax, cs:__security_cookie
0x1400f50ee  xor     rax, rsp
0x1400f50f1  mov     [rsp+78h+var_30], rax
0x1400f50f6  mov     rbx, [rsp+78h+arg_20]
0x1400f50fe  mov     r14, rcx
0x1400f5101  xorps   xmm0, xmm0
0x1400f5104  xor     eax, eax
0x1400f5106  xor     ecx, ecx; PerformanceFrequency
0x1400f5108  mov     qword ptr [rsp+78h+PerformanceFrequency], rax
0x1400f510d  movups  [rsp+78h+var_48], xmm0
0x1400f5112  mov     rbp, r9
0x1400f5115  mov     rsi, r8
0x1400f5118  mov     edi, edx
0x1400f511a  call    cs:__imp_KeQueryPerformanceCounter
0x1400f5121  nop     dword ptr [rax+rax+00h]
0x1400f5126  mov     rcx, [r14+288h]
0x1400f512d  mov     r9, rbp
0x1400f5130  mov     r8, rsi
0x1400f5133  mov     qword ptr [rsp+78h+var_48], rax
0x1400f5138  mov     edx, edi
0x1400f513a  mov     [rsp+78h+var_58], rbx
0x1400f513f  call    cs:__imp_WinHvPrecommitGpaPages
0x1400f5146  nop     dword ptr [rax+rax+00h]
0x1400f514b  lea     rcx, [rsp+78h+PerformanceFrequency]; PerformanceFrequency
0x1400f5150  mov     ebx, eax
0x1400f5152  call    cs:__imp_KeQueryPerformanceCounter
0x1400f5159  nop     dword ptr [rax+rax+00h]
0x1400f515e  mov     rcx, [r14+5F8h]
0x1400f5165  mov     qword ptr [rsp+78h+var_48+8], rax
0x1400f516a  sub     rax, qword ptr [rsp+78h+var_48]
0x1400f516f  imul    rax, 0F4240h
0x1400f5176  cqo
0x1400f5178  idiv    qword ptr [rsp+78h+PerformanceFrequency]
0x1400f517d  lock inc qword ptr [rcx+4B8h]
0x1400f5185  mov     rcx, [r14+5F8h]
0x1400f518c  lock add [rcx+4C0h], rax
0x1400f5194  mov     eax, ebx
0x1400f5196  mov     rcx, [rsp+78h+var_30]
0x1400f519b  xor     rcx, rsp; StackCookie
0x1400f519e  call    __security_check_cookie
0x1400f51a3  add     rsp, 50h
0x1400f51a7  pop     r14
0x1400f51a9  pop     rdi
0x1400f51aa  pop     rsi
0x1400f51ab  pop     rbp
0x1400f51ac  pop     rbx
0x1400f51ad  retn
```
