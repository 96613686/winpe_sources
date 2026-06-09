# TmpDereferencePropagateRequest

- ea: `0x14000cfa8`
- end: `0x14000d079`
- name: `TmpDereferencePropagateRequest`
- size: `209`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140018720`
- `0x1400187b0`
- `0x140018810`
- `0x140018f20`
- `0x14001953c`
- `0x14001976c`
- `0x140019810`

## callees

- `0x14000cfa8`
- `0x14000d080`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000cfeb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000cfeb`
- `ntoskrnl!KeReleaseMutex` at `0x14000d046`
- `ntoskrnl!KeReleaseMutex` at `0x14000d046`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d024`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d055`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d024`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d055`
- `ntoskrnl!ObfReferenceObject` at `0x14000cfca`
- `ntoskrnl!ObfReferenceObject` at `0x14000cfca`

## pseudocode

```c
void __fastcall TmpDereferencePropagateRequest(char *P)
{
  __int64 v1; // rdi
  char **v3; // rcx
  PVOID *v4; // rdx

  v1 = *((_QWORD *)P + 7);
  if ( v1 )
  {
    ObfReferenceObject(*((PVOID *)P + 7));
    KeWaitForSingleObject((PVOID)(v1 + 40), Executive, 0, 0, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 2, 0xFFFFFFFF) == 1 )
    {
      v3 = (char **)*((_QWORD *)P + 2);
      if ( v3[1] != P + 16 || (v4 = (PVOID *)*((_QWORD *)P + 3), *v4 != P + 16) )
        __fastfail(3u);
      *v4 = v3;
      v3[1] = (char *)v4;
      ObfDereferenceObject((PVOID)v1);
      *((_QWORD *)P + 7) = 0;
      TmpDeletePropagateRequest(P);
    }
    KeReleaseMutex((PRKMUTEX)(v1 + 40), 0);
    ObfDereferenceObject((PVOID)v1);
  }
}

```

## disassembly

```asm
0x14000cfa8  mov     [rsp+arg_0], rbx
0x14000cfad  mov     [rsp+arg_8], rsi
0x14000cfb2  push    rdi
0x14000cfb3  sub     rsp, 30h
0x14000cfb7  mov     rdi, [rcx+38h]
0x14000cfbb  mov     rbx, rcx
0x14000cfbe  test    rdi, rdi
0x14000cfc1  jz      loc_14000D061
0x14000cfc7  mov     rcx, rdi; Object
0x14000cfca  call    cs:__imp_ObfReferenceObject
0x14000cfd1  nop     dword ptr [rax+rax+00h]
0x14000cfd6  xor     r9d, r9d; Alertable
0x14000cfd9  mov     [rsp+38h+Timeout], 0; Timeout
0x14000cfe2  xor     r8d, r8d; WaitMode
0x14000cfe5  lea     rcx, [rdi+28h]; Object
0x14000cfe9  xor     edx, edx; WaitReason
0x14000cfeb  call    cs:__imp_KeWaitForSingleObject
0x14000cff2  nop     dword ptr [rax+rax+00h]
0x14000cff7  or      eax, 0FFFFFFFFh
0x14000cffa  lock xadd [rbx+8], eax
0x14000cfff  cmp     eax, 1
0x14000d002  jnz     short loc_14000D040
0x14000d004  lea     rax, [rbx+10h]
0x14000d008  mov     rcx, [rax]
0x14000d00b  cmp     [rcx+8], rax
0x14000d00f  jnz     short loc_14000D072
0x14000d011  mov     rdx, [rax+8]
0x14000d015  cmp     [rdx], rax
0x14000d018  jnz     short loc_14000D072
0x14000d01a  mov     [rdx], rcx
0x14000d01d  mov     [rcx+8], rdx
0x14000d021  mov     rcx, rdi; Object
0x14000d024  call    cs:__imp_ObfDereferenceObject
0x14000d02b  nop     dword ptr [rax+rax+00h]
0x14000d030  mov     rcx, rbx; P
0x14000d033  mov     qword ptr [rbx+38h], 0
0x14000d03b  call    TmpDeletePropagateRequest
0x14000d040  xor     edx, edx; Wait
0x14000d042  lea     rcx, [rdi+28h]; Mutex
0x14000d046  call    cs:__imp_KeReleaseMutex
0x14000d04d  nop     dword ptr [rax+rax+00h]
0x14000d052  mov     rcx, rdi; Object
0x14000d055  call    cs:__imp_ObfDereferenceObject
0x14000d05c  nop     dword ptr [rax+rax+00h]
0x14000d061  mov     rbx, [rsp+38h+arg_0]
0x14000d066  mov     rsi, [rsp+38h+arg_8]
0x14000d06b  add     rsp, 30h
0x14000d06f  pop     rdi
0x14000d070  retn
0x14000d072  mov     ecx, 3
0x14000d077  int     29h; Win8: RtlFailFast(ecx)
```
