# CancelTimerCallbacksAndDeleteTimer

- ea: `0x140022928`
- end: `0x1400229c9`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140022b98`
- `0x140022f00`

## callees

- `0x140022928`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002297e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002297e`
- `ntoskrnl!ExDeleteTimer` at `0x1400229ab`
- `ntoskrnl!ExDeleteTimer` at `0x1400229ab`

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
0x140022928  push    rbx
0x14002292a  sub     rsp, 50h
0x14002292e  cmp     qword ptr [rcx+168h], 0
0x140022936  mov     rbx, rcx
0x140022939  jz      loc_1400229C2
0x14002293f  xor     eax, eax
0x140022941  xorps   xmm0, xmm0
0x140022944  mov     [rsp+58h+var_18], rax
0x140022949  movups  [rsp+58h+var_28], xmm0
0x14002294e  lea     edx, [rax+2]
0x140022951  mov     rax, [rcx+108h]
0x140022958  xchg    dx, [rax+38h]
0x14002295c  cmp     dx, 1
0x140022960  jnz     short loc_14002298A
0x140022962  mov     rcx, [rcx+108h]
0x140022969  xor     r9d, r9d; Alertable
0x14002296c  add     rcx, 20h ; ' '; Object
0x140022970  mov     [rsp+58h+Timeout], 0; Timeout
0x140022979  xor     r8d, r8d; WaitMode
0x14002297c  xor     edx, edx; WaitReason
0x14002297e  call    cs:__imp_KeWaitForSingleObject
0x140022985  nop     dword ptr [rax+rax+00h]
0x14002298a  mov     rcx, [rbx+168h]
0x140022991  lea     r9, [rsp+58h+var_28]
0x140022996  mov     r8b, 1
0x140022999  xorps   xmm0, xmm0
0x14002299c  xor     eax, eax
0x14002299e  mov     dl, r8b
0x1400229a1  movups  [rsp+58h+var_28], xmm0
0x1400229a6  mov     [rsp+58h+var_18], rax
0x1400229ab  call    cs:__imp_ExDeleteTimer
0x1400229b2  nop     dword ptr [rax+rax+00h]
0x1400229b7  mov     qword ptr [rbx+168h], 0
0x1400229c2  add     rsp, 50h
0x1400229c6  pop     rbx
0x1400229c7  retn
```
