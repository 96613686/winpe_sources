# ChpGpadlCreatedLocked

- ea: `0x14000f6c4`
- end: `0x14000f78b`
- name: `ChpGpadlCreatedLocked`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000eec8`

## callees

- `0x14000f5f0`
- `0x14000f6c4`
- `0x14000f7e4`
- `0x14000f86c`
- `0x14000fc04`
- `0x140017190`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000f70c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000f70c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f72b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f72b`

## pseudocode

```c
void __fastcall ChpGpadlCreatedLocked(__int64 a1, __int64 a2, int a3)
{
  void (__fastcall *v4)(_QWORD, _QWORD, __int64); // r15
  __int64 v7; // rbx
  struct _FAST_MUTEX *v8; // rdi

  v4 = *(void (__fastcall **)(_QWORD, _QWORD, __int64))(a2 + 80);
  *(_DWORD *)(a2 + 16) = *(_DWORD *)(a2 + 16) != 0 ? 4 : 1;
  if ( v4 )
  {
    v7 = *(_QWORD *)(a2 + 88);
    v8 = (struct _FAST_MUTEX *)(a1 + 432);
    *(_QWORD *)(a2 + 80) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a1 + 432));
    v4((unsigned int)a3, *(unsigned int *)(a2 + 64), v7);
    ExAcquireFastMutex(v8);
  }
  if ( *(_DWORD *)(a2 + 16) == 1 )
  {
    *(_DWORD *)(a2 + 16) = 2;
    if ( a3 < 0 )
    {
      ChpMakeGpadlHostInvisible(a2);
      ChpDestroyGpadlLocked(a1, a2);
    }
  }
  else
  {
    *(_DWORD *)(a2 + 16) = 5;
    if ( a3 < 0 )
      ChpNotifyAndDestroyGpadlLocked(a1, a2);
    else
      ChpSendTeardownGpadlPacket(a2);
  }
}

```

## disassembly

```asm
0x14000f6c4  push    rbx
0x14000f6c6  push    rbp
0x14000f6c7  push    rsi
0x14000f6c8  push    rdi
0x14000f6c9  push    r14
0x14000f6cb  push    r15
0x14000f6cd  sub     rsp, 28h
0x14000f6d1  mov     eax, [rdx+10h]
0x14000f6d4  mov     ebp, r8d
0x14000f6d7  mov     r15, [rdx+50h]
0x14000f6db  neg     eax
0x14000f6dd  mov     rsi, rdx
0x14000f6e0  mov     r14, rcx
0x14000f6e3  sbb     r9d, r9d
0x14000f6e6  and     r9d, 3
0x14000f6ea  inc     r9d
0x14000f6ed  mov     [rdx+10h], r9d
0x14000f6f1  test    r15, r15
0x14000f6f4  jz      short loc_14000F737
0x14000f6f6  mov     rbx, [rdx+58h]
0x14000f6fa  lea     rdi, [rcx+1B0h]
0x14000f701  mov     rcx, rdi; FastMutex
0x14000f704  mov     qword ptr [rdx+50h], 0
0x14000f70c  call    cs:__imp_ExReleaseFastMutex
0x14000f713  nop     dword ptr [rax+rax+00h]
0x14000f718  mov     edx, [rsi+40h]
0x14000f71b  mov     r8, rbx
0x14000f71e  mov     ecx, ebp
0x14000f720  mov     rax, r15
0x14000f723  call    _guard_dispatch_icall
0x14000f728  mov     rcx, rdi; FastMutex
0x14000f72b  call    cs:__imp_ExAcquireFastMutex
0x14000f732  nop     dword ptr [rax+rax+00h]
0x14000f737  cmp     dword ptr [rsi+10h], 1
0x14000f73b  jnz     short loc_14000F75D
0x14000f73d  mov     dword ptr [rsi+10h], 2
0x14000f744  test    ebp, ebp
0x14000f746  jns     short loc_14000F77D
0x14000f748  mov     rcx, rsi
0x14000f74b  call    ChpMakeGpadlHostInvisible
0x14000f750  mov     rdx, rsi
0x14000f753  mov     rcx, r14
0x14000f756  call    ChpDestroyGpadlLocked
0x14000f75b  jmp     short loc_14000F77D
0x14000f75d  mov     dword ptr [rsi+10h], 5
0x14000f764  test    ebp, ebp
0x14000f766  js      short loc_14000F772
0x14000f768  mov     rcx, rsi
0x14000f76b  call    ChpSendTeardownGpadlPacket
0x14000f770  jmp     short loc_14000F77D
0x14000f772  mov     rdx, rsi
0x14000f775  mov     rcx, r14
0x14000f778  call    ChpNotifyAndDestroyGpadlLocked
0x14000f77d  add     rsp, 28h
0x14000f781  pop     r15
0x14000f783  pop     r14
0x14000f785  pop     rdi
0x14000f786  pop     rsi
0x14000f787  pop     rbp
0x14000f788  pop     rbx
0x14000f789  retn
```
