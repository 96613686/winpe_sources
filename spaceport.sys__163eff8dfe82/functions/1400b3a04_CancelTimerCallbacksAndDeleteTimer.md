# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1400b3a04`
- end: `0x1400b3aa5`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400b3c74`
- `0x1400b3fe0`

## callees

- `0x1400b3a04`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400b3a5a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b3a5a`
- `ntoskrnl!ExDeleteTimer` at `0x1400b3a87`
- `ntoskrnl!ExDeleteTimer` at `0x1400b3a87`

## pseudocode

```c
__int64 __fastcall CancelTimerCallbacksAndDeleteTimer(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 result; // rax
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+40h] [rbp-18h]

  if ( *(_QWORD *)(a1 + 360) )
  {
    v9 = 0;
    v8 = 0;
    v5 = 2;
    v4 = *(_QWORD *)(a1 + 264);
    LOWORD(v5) = *(_WORD *)(v4 + 56);
    *(_WORD *)(v4 + 56) = 2;
    if ( (_WORD)v5 == 1 )
      KeWaitForSingleObject((PVOID)(*(_QWORD *)(a1 + 264) + 32LL), Executive, 0, 0, 0);
    v6 = *(_QWORD *)(a1 + 360);
    LOBYTE(a3) = 1;
    LOBYTE(v5) = 1;
    v8 = 0;
    v9 = 0;
    result = ExDeleteTimer(v6, v5, a3, &v8);
    *(_QWORD *)(a1 + 360) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400b3a04  push    rbx
0x1400b3a06  sub     rsp, 50h
0x1400b3a0a  cmp     qword ptr [rcx+168h], 0
0x1400b3a12  mov     rbx, rcx
0x1400b3a15  jz      loc_1400B3A9E
0x1400b3a1b  xor     eax, eax
0x1400b3a1d  xorps   xmm0, xmm0
0x1400b3a20  mov     [rsp+58h+var_18], rax
0x1400b3a25  movups  [rsp+58h+var_28], xmm0
0x1400b3a2a  lea     edx, [rax+2]
0x1400b3a2d  mov     rax, [rcx+108h]
0x1400b3a34  xchg    dx, [rax+38h]
0x1400b3a38  cmp     dx, 1
0x1400b3a3c  jnz     short loc_1400B3A66
0x1400b3a3e  mov     rcx, [rcx+108h]
0x1400b3a45  xor     r9d, r9d; Alertable
0x1400b3a48  add     rcx, 20h ; ' '; Object
0x1400b3a4c  mov     [rsp+58h+Timeout], 0; Timeout
0x1400b3a55  xor     r8d, r8d; WaitMode
0x1400b3a58  xor     edx, edx; WaitReason
0x1400b3a5a  call    cs:__imp_KeWaitForSingleObject
0x1400b3a61  nop     dword ptr [rax+rax+00h]
0x1400b3a66  mov     rcx, [rbx+168h]
0x1400b3a6d  lea     r9, [rsp+58h+var_28]
0x1400b3a72  mov     r8b, 1
0x1400b3a75  xorps   xmm0, xmm0
0x1400b3a78  xor     eax, eax
0x1400b3a7a  mov     dl, r8b
0x1400b3a7d  movups  [rsp+58h+var_28], xmm0
0x1400b3a82  mov     [rsp+58h+var_18], rax
0x1400b3a87  call    cs:__imp_ExDeleteTimer
0x1400b3a8e  nop     dword ptr [rax+rax+00h]
0x1400b3a93  mov     qword ptr [rbx+168h], 0
0x1400b3a9e  add     rsp, 50h
0x1400b3aa2  pop     rbx
0x1400b3aa3  retn
```
