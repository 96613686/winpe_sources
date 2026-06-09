# VidVppInterceptThreadRoutine

- ea: `0x140024340`
- end: `0x140024445`
- name: `VidVppInterceptThreadRoutine`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001a20`
- `0x140021650`
- `0x140024340`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140024398`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140024398`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140024408`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140024408`
- `ntoskrnl!PsTerminateSystemThread` at `0x140024420`
- `ntoskrnl!PsTerminateSystemThread` at `0x140024420`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x1400243a4`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x1400243c3`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x1400243a4`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x1400243c3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400243e3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400243e3`

## pseudocode

```c
NTSTATUS __fastcall VidVppInterceptThreadRoutine(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  _GROUP_AFFINITY Affinity; // [rsp+30h] [rbp-28h] BYREF

  v1 = *(unsigned __int8 *)(a1 + 12);
  v2 = *(_QWORD *)a1;
  Affinity = 0;
  Affinity.Group = *(_WORD *)(v2 + 16 * v1 + 2184);
  Affinity.Mask = *(_QWORD *)(v2 + 16 * (v1 + 136));
  KeSetSystemGroupAffinityThread(&Affinity, 0);
  KeReenterRetpolinedCode();
  while ( 1 )
  {
    KeWaitForSingleObject((PVOID)(a1 + 352), Executive, 0, 0, 0);
    if ( *(_DWORD *)(a1 + 376) )
      break;
    VidInterceptProcess((__int64 *)a1, 1);
    KeReenterRetpolinedCode();
  }
  if ( *(_DWORD *)(a1 + 392) )
  {
    KeUnstackDetachProcess((PRKAPC_STATE)(a1 + 400));
    *(_DWORD *)(a1 + 392) = 0;
  }
  return PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140024340  mov     [rsp+arg_8], rbx
0x140024345  push    rdi
0x140024346  sub     rsp, 50h
0x14002434a  mov     rax, cs:__security_cookie
0x140024351  xor     rax, rsp
0x140024354  mov     [rsp+58h+var_18], rax
0x140024359  movzx   edx, byte ptr [rcx+0Ch]
0x14002435d  xorps   xmm0, xmm0
0x140024360  mov     r8, [rcx]
0x140024363  mov     eax, edx
0x140024365  add     rax, rax
0x140024368  mov     rbx, rcx
0x14002436b  movups  xmmword ptr [rsp+58h+Affinity.Mask], xmm0
0x140024370  lea     rcx, [rsp+58h+Affinity]; Affinity
0x140024375  movzx   eax, word ptr [r8+rax*8+888h]
0x14002437e  mov     [rsp+58h+Affinity.Group], ax
0x140024383  lea     rax, [rdx+88h]
0x14002438a  add     rax, rax
0x14002438d  xor     edx, edx; PreviousAffinity
0x14002438f  mov     rax, [r8+rax*8]
0x140024393  mov     [rsp+58h+Affinity.Mask], rax
0x140024398  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14002439f  nop     dword ptr [rax+rax+00h]
0x1400243a4  call    cs:__imp_KeReenterRetpolinedCode
0x1400243ab  nop     dword ptr [rax+rax+00h]
0x1400243b0  lea     rdi, [rbx+160h]
0x1400243b7  jmp     short loc_1400243CF
0x1400243b9  mov     dl, 1
0x1400243bb  mov     rcx, rbx
0x1400243be  call    VidInterceptProcess
0x1400243c3  call    cs:__imp_KeReenterRetpolinedCode
0x1400243ca  nop     dword ptr [rax+rax+00h]
0x1400243cf  xor     r9d, r9d; Alertable
0x1400243d2  mov     [rsp+58h+Timeout], 0; Timeout
0x1400243db  xor     r8d, r8d; WaitMode
0x1400243de  xor     edx, edx; WaitReason
0x1400243e0  mov     rcx, rdi; Object
0x1400243e3  call    cs:__imp_KeWaitForSingleObject
0x1400243ea  nop     dword ptr [rax+rax+00h]
0x1400243ef  cmp     dword ptr [rbx+178h], 0
0x1400243f6  jz      short loc_1400243B9
0x1400243f8  cmp     dword ptr [rbx+188h], 0
0x1400243ff  jz      short loc_14002441E
0x140024401  lea     rcx, [rbx+190h]; ApcState
0x140024408  call    cs:__imp_KeUnstackDetachProcess
0x14002440f  nop     dword ptr [rax+rax+00h]
0x140024414  mov     dword ptr [rbx+188h], 0
0x14002441e  xor     ecx, ecx; ExitStatus
0x140024420  call    cs:__imp_PsTerminateSystemThread
0x140024427  nop     dword ptr [rax+rax+00h]
0x14002442c  mov     rcx, [rsp+58h+var_18]
0x140024431  xor     rcx, rsp; StackCookie
0x140024434  call    __security_check_cookie
0x140024439  mov     rbx, [rsp+58h+arg_8]
0x14002443e  add     rsp, 50h
0x140024442  pop     rdi
0x140024443  retn
```
