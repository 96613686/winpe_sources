# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1400922cc`
- end: `0x14009236d`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400924ac`
- `0x140092d54`

## callees

- `0x1400922cc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140092322`
- `ntoskrnl!KeWaitForSingleObject` at `0x140092322`
- `ntoskrnl!ExDeleteTimer` at `0x14009234f`
- `ntoskrnl!ExDeleteTimer` at `0x14009234f`

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
0x1400922cc  push    rbx
0x1400922ce  sub     rsp, 50h
0x1400922d2  cmp     qword ptr [rcx+168h], 0
0x1400922da  mov     rbx, rcx
0x1400922dd  jz      loc_140092366
0x1400922e3  xor     eax, eax
0x1400922e5  xorps   xmm0, xmm0
0x1400922e8  mov     [rsp+58h+var_18], rax
0x1400922ed  movups  [rsp+58h+var_28], xmm0
0x1400922f2  lea     edx, [rax+2]
0x1400922f5  mov     rax, [rcx+108h]
0x1400922fc  xchg    dx, [rax+38h]
0x140092300  cmp     dx, 1
0x140092304  jnz     short loc_14009232E
0x140092306  mov     rcx, [rcx+108h]
0x14009230d  xor     r9d, r9d; Alertable
0x140092310  add     rcx, 20h ; ' '; Object
0x140092314  mov     [rsp+58h+Timeout], 0; Timeout
0x14009231d  xor     r8d, r8d; WaitMode
0x140092320  xor     edx, edx; WaitReason
0x140092322  call    cs:__imp_KeWaitForSingleObject
0x140092329  nop     dword ptr [rax+rax+00h]
0x14009232e  mov     rcx, [rbx+168h]
0x140092335  lea     r9, [rsp+58h+var_28]
0x14009233a  mov     r8b, 1
0x14009233d  xorps   xmm0, xmm0
0x140092340  xor     eax, eax
0x140092342  mov     dl, r8b
0x140092345  movups  [rsp+58h+var_28], xmm0
0x14009234a  mov     [rsp+58h+var_18], rax
0x14009234f  call    cs:__imp_ExDeleteTimer
0x140092356  nop     dword ptr [rax+rax+00h]
0x14009235b  mov     qword ptr [rbx+168h], 0
0x140092366  add     rsp, 50h
0x14009236a  pop     rbx
0x14009236b  retn
```
