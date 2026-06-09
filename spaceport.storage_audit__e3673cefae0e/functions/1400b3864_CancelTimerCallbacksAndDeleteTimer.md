# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1400b3864`
- end: `0x1400b3905`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400b3ad4`
- `0x1400b3e40`

## callees

- `0x1400b3864`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400b38ba`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b38ba`
- `ntoskrnl!ExDeleteTimer` at `0x1400b38e7`
- `ntoskrnl!ExDeleteTimer` at `0x1400b38e7`

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
0x1400b3864  push    rbx
0x1400b3866  sub     rsp, 50h
0x1400b386a  cmp     qword ptr [rcx+168h], 0
0x1400b3872  mov     rbx, rcx
0x1400b3875  jz      loc_1400B38FE
0x1400b387b  xor     eax, eax
0x1400b387d  xorps   xmm0, xmm0
0x1400b3880  mov     [rsp+58h+var_18], rax
0x1400b3885  movups  [rsp+58h+var_28], xmm0
0x1400b388a  lea     edx, [rax+2]
0x1400b388d  mov     rax, [rcx+108h]
0x1400b3894  xchg    dx, [rax+38h]
0x1400b3898  cmp     dx, 1
0x1400b389c  jnz     short loc_1400B38C6
0x1400b389e  mov     rcx, [rcx+108h]
0x1400b38a5  xor     r9d, r9d; Alertable
0x1400b38a8  add     rcx, 20h ; ' '; Object
0x1400b38ac  mov     [rsp+58h+Timeout], 0; Timeout
0x1400b38b5  xor     r8d, r8d; WaitMode
0x1400b38b8  xor     edx, edx; WaitReason
0x1400b38ba  call    cs:__imp_KeWaitForSingleObject
0x1400b38c1  nop     dword ptr [rax+rax+00h]
0x1400b38c6  mov     rcx, [rbx+168h]
0x1400b38cd  lea     r9, [rsp+58h+var_28]
0x1400b38d2  mov     r8b, 1
0x1400b38d5  xorps   xmm0, xmm0
0x1400b38d8  xor     eax, eax
0x1400b38da  mov     dl, r8b
0x1400b38dd  movups  [rsp+58h+var_28], xmm0
0x1400b38e2  mov     [rsp+58h+var_18], rax
0x1400b38e7  call    cs:__imp_ExDeleteTimer
0x1400b38ee  nop     dword ptr [rax+rax+00h]
0x1400b38f3  mov     qword ptr [rbx+168h], 0
0x1400b38fe  add     rsp, 50h
0x1400b3902  pop     rbx
0x1400b3903  retn
```
