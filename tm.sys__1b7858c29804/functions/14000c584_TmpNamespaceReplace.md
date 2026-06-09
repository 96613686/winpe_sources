# TmpNamespaceReplace

- ea: `0x14000c584`
- end: `0x14000c65c`
- name: `TmpNamespaceReplace`
- size: `216`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, PVOID Object)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015648`

## callees

- `0x14000c584`
- `0x14000c664`
- `0x14001b444`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000c5db`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c5db`
- `ntoskrnl!KeReleaseMutex` at `0x14000c62a`
- `ntoskrnl!KeReleaseMutex` at `0x14000c62a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c63e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c63e`
- `ntoskrnl!ObfReferenceObject` at `0x14000c5b7`
- `ntoskrnl!ObfReferenceObject` at `0x14000c5b7`

## pseudocode

```c
__int64 __fastcall TmpNamespaceReplace(PRTL_AVL_TABLE Table, PVOID Object, __int64 a3, __int64 a4)
{
  __int64 v4; // r15
  __int64 RestartKey_low; // r12
  unsigned int v10; // eax
  struct _KMUTANT *v11; // rcx
  unsigned int v12; // edi

  v4 = WORD1(Table[1].RestartKey);
  RestartKey_low = LOWORD(Table[1].RestartKey);
  if ( Object )
    ObfReferenceObject(Object);
  KeWaitForSingleObject(&Table[1], Executive, 0, 0, 0);
  TmpNamespaceRemove(Table, Object, a3);
  if ( *(_QWORD *)(RestartKey_low + a4) )
    TmpNamespaceRemove(Table, Object, a4);
  *(_OWORD *)(v4 + a4) = *(_OWORD *)(v4 + a3);
  v10 = TmpNamespaceInsert(Table, Object);
  v11 = (struct _KMUTANT *)&Table[1];
  v12 = v10;
  KeReleaseMutex(v11, 0);
  if ( Object )
    ObfDereferenceObject(Object);
  return v12;
}

```

## disassembly

```asm
0x14000c584  push    rbx
0x14000c586  push    rbp
0x14000c587  push    rsi
0x14000c588  push    rdi
0x14000c589  push    r12
0x14000c58b  push    r14
0x14000c58d  push    r15
0x14000c58f  sub     rsp, 30h
0x14000c593  movzx   r15d, word ptr [rcx+0A2h]
0x14000c59b  mov     rsi, r9
0x14000c59e  movzx   r12d, word ptr [rcx+0A0h]
0x14000c5a6  mov     rbp, r8
0x14000c5a9  mov     rbx, rdx
0x14000c5ac  mov     rdi, rcx
0x14000c5af  test    rdx, rdx
0x14000c5b2  jz      short loc_14000C5C3
0x14000c5b4  mov     rcx, rdx; Object
0x14000c5b7  call    cs:__imp_ObfReferenceObject
0x14000c5be  nop     dword ptr [rax+rax+00h]
0x14000c5c3  lea     r14, [rdi+68h]
0x14000c5c7  mov     [rsp+68h+Timeout], 0; Timeout
0x14000c5d0  mov     rcx, r14; Object
0x14000c5d3  xor     r9d, r9d; Alertable
0x14000c5d6  xor     r8d, r8d; WaitMode
0x14000c5d9  xor     edx, edx; WaitReason
0x14000c5db  call    cs:__imp_KeWaitForSingleObject
0x14000c5e2  nop     dword ptr [rax+rax+00h]
0x14000c5e7  mov     r8, rbp
0x14000c5ea  mov     rdx, rbx; Object
0x14000c5ed  mov     rcx, rdi; Table
0x14000c5f0  call    TmpNamespaceRemove
0x14000c5f5  cmp     qword ptr [r12+rsi], 0
0x14000c5fa  jz      short loc_14000C60A
0x14000c5fc  mov     r8, rsi
0x14000c5ff  mov     rdx, rbx; Object
0x14000c602  mov     rcx, rdi; Table
0x14000c605  call    TmpNamespaceRemove
0x14000c60a  movups  xmm0, xmmword ptr [r15+rbp]
0x14000c60f  mov     r8, rsi
0x14000c612  mov     rdx, rbx; Object
0x14000c615  mov     rcx, rdi; Table
0x14000c618  movdqu  xmmword ptr [r15+rsi], xmm0
0x14000c61e  call    TmpNamespaceInsert
0x14000c623  xor     edx, edx; Wait
0x14000c625  mov     rcx, r14; Mutex
0x14000c628  mov     edi, eax
0x14000c62a  call    cs:__imp_KeReleaseMutex
0x14000c631  nop     dword ptr [rax+rax+00h]
0x14000c636  test    rbx, rbx
0x14000c639  jz      short loc_14000C64A
0x14000c63b  mov     rcx, rbx; Object
0x14000c63e  call    cs:__imp_ObfDereferenceObject
0x14000c645  nop     dword ptr [rax+rax+00h]
0x14000c64a  mov     eax, edi
0x14000c64c  add     rsp, 30h
0x14000c650  pop     r15
0x14000c652  pop     r14
0x14000c654  pop     r12
0x14000c656  pop     rdi
0x14000c657  pop     rsi
0x14000c658  pop     rbp
0x14000c659  pop     rbx
0x14000c65a  retn
```
