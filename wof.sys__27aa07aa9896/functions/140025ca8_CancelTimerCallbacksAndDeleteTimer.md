# CancelTimerCallbacksAndDeleteTimer

- ea: `0x140025ca8`
- end: `0x140025d49`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140025f18`
- `0x140026280`

## callees

- `0x140025ca8`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x140025d2b`
- `ntoskrnl!ExDeleteTimer` at `0x140025d2b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140025cfe`
- `ntoskrnl!KeWaitForSingleObject` at `0x140025cfe`

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
0x140025ca8  push    rbx
0x140025caa  sub     rsp, 50h
0x140025cae  cmp     qword ptr [rcx+168h], 0
0x140025cb6  mov     rbx, rcx
0x140025cb9  jz      loc_140025D42
0x140025cbf  xor     eax, eax
0x140025cc1  xorps   xmm0, xmm0
0x140025cc4  mov     [rsp+58h+var_18], rax
0x140025cc9  movups  [rsp+58h+var_28], xmm0
0x140025cce  lea     edx, [rax+2]
0x140025cd1  mov     rax, [rcx+108h]
0x140025cd8  xchg    dx, [rax+38h]
0x140025cdc  cmp     dx, 1
0x140025ce0  jnz     short loc_140025D0A
0x140025ce2  mov     rcx, [rcx+108h]
0x140025ce9  xor     r9d, r9d; Alertable
0x140025cec  add     rcx, 20h ; ' '; Object
0x140025cf0  mov     [rsp+58h+Timeout], 0; Timeout
0x140025cf9  xor     r8d, r8d; WaitMode
0x140025cfc  xor     edx, edx; WaitReason
0x140025cfe  call    cs:__imp_KeWaitForSingleObject
0x140025d05  nop     dword ptr [rax+rax+00h]
0x140025d0a  mov     rcx, [rbx+168h]
0x140025d11  lea     r9, [rsp+58h+var_28]
0x140025d16  mov     r8b, 1
0x140025d19  xorps   xmm0, xmm0
0x140025d1c  xor     eax, eax
0x140025d1e  mov     dl, r8b
0x140025d21  movups  [rsp+58h+var_28], xmm0
0x140025d26  mov     [rsp+58h+var_18], rax
0x140025d2b  call    cs:__imp_ExDeleteTimer
0x140025d32  nop     dword ptr [rax+rax+00h]
0x140025d37  mov     qword ptr [rbx+168h], 0
0x140025d42  add     rsp, 50h
0x140025d46  pop     rbx
0x140025d47  retn
```
