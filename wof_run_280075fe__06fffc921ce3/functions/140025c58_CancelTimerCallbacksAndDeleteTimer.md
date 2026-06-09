# CancelTimerCallbacksAndDeleteTimer

- ea: `0x140025c58`
- end: `0x140025cf9`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140025ec8`
- `0x140026230`

## callees

- `0x140025c58`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x140025cdb`
- `ntoskrnl!ExDeleteTimer` at `0x140025cdb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140025cae`
- `ntoskrnl!KeWaitForSingleObject` at `0x140025cae`

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
0x140025c58  push    rbx
0x140025c5a  sub     rsp, 50h
0x140025c5e  cmp     qword ptr [rcx+168h], 0
0x140025c66  mov     rbx, rcx
0x140025c69  jz      loc_140025CF2
0x140025c6f  xor     eax, eax
0x140025c71  xorps   xmm0, xmm0
0x140025c74  mov     [rsp+58h+var_18], rax
0x140025c79  movups  [rsp+58h+var_28], xmm0
0x140025c7e  lea     edx, [rax+2]
0x140025c81  mov     rax, [rcx+108h]
0x140025c88  xchg    dx, [rax+38h]
0x140025c8c  cmp     dx, 1
0x140025c90  jnz     short loc_140025CBA
0x140025c92  mov     rcx, [rcx+108h]
0x140025c99  xor     r9d, r9d; Alertable
0x140025c9c  add     rcx, 20h ; ' '; Object
0x140025ca0  mov     [rsp+58h+Timeout], 0; Timeout
0x140025ca9  xor     r8d, r8d; WaitMode
0x140025cac  xor     edx, edx; WaitReason
0x140025cae  call    cs:__imp_KeWaitForSingleObject
0x140025cb5  nop     dword ptr [rax+rax+00h]
0x140025cba  mov     rcx, [rbx+168h]
0x140025cc1  lea     r9, [rsp+58h+var_28]
0x140025cc6  mov     r8b, 1
0x140025cc9  xorps   xmm0, xmm0
0x140025ccc  xor     eax, eax
0x140025cce  mov     dl, r8b
0x140025cd1  movups  [rsp+58h+var_28], xmm0
0x140025cd6  mov     [rsp+58h+var_18], rax
0x140025cdb  call    cs:__imp_ExDeleteTimer
0x140025ce2  nop     dword ptr [rax+rax+00h]
0x140025ce7  mov     qword ptr [rbx+168h], 0
0x140025cf2  add     rsp, 50h
0x140025cf6  pop     rbx
0x140025cf7  retn
```
