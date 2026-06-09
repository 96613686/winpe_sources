# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1400228d8`
- end: `0x140022979`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140022b48`
- `0x140022eb0`

## callees

- `0x1400228d8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002292e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002292e`
- `ntoskrnl!ExDeleteTimer` at `0x14002295b`
- `ntoskrnl!ExDeleteTimer` at `0x14002295b`

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
0x1400228d8  push    rbx
0x1400228da  sub     rsp, 50h
0x1400228de  cmp     qword ptr [rcx+168h], 0
0x1400228e6  mov     rbx, rcx
0x1400228e9  jz      loc_140022972
0x1400228ef  xor     eax, eax
0x1400228f1  xorps   xmm0, xmm0
0x1400228f4  mov     [rsp+58h+var_18], rax
0x1400228f9  movups  [rsp+58h+var_28], xmm0
0x1400228fe  lea     edx, [rax+2]
0x140022901  mov     rax, [rcx+108h]
0x140022908  xchg    dx, [rax+38h]
0x14002290c  cmp     dx, 1
0x140022910  jnz     short loc_14002293A
0x140022912  mov     rcx, [rcx+108h]
0x140022919  xor     r9d, r9d; Alertable
0x14002291c  add     rcx, 20h ; ' '; Object
0x140022920  mov     [rsp+58h+Timeout], 0; Timeout
0x140022929  xor     r8d, r8d; WaitMode
0x14002292c  xor     edx, edx; WaitReason
0x14002292e  call    cs:__imp_KeWaitForSingleObject
0x140022935  nop     dword ptr [rax+rax+00h]
0x14002293a  mov     rcx, [rbx+168h]
0x140022941  lea     r9, [rsp+58h+var_28]
0x140022946  mov     r8b, 1
0x140022949  xorps   xmm0, xmm0
0x14002294c  xor     eax, eax
0x14002294e  mov     dl, r8b
0x140022951  movups  [rsp+58h+var_28], xmm0
0x140022956  mov     [rsp+58h+var_18], rax
0x14002295b  call    cs:__imp_ExDeleteTimer
0x140022962  nop     dword ptr [rax+rax+00h]
0x140022967  mov     qword ptr [rbx+168h], 0
0x140022972  add     rsp, 50h
0x140022976  pop     rbx
0x140022977  retn
```
