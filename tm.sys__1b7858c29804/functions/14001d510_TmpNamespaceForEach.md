# TmpNamespaceForEach

- ea: `0x14001d510`
- end: `0x14001d601`
- name: `TmpNamespaceForEach`
- size: `241`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140001860`
- `0x14000c7e8`
- `0x14000d330`
- `0x140010e70`
- `0x140012a30`
- `0x14001a630`
- `0x14001e810`

## callees

- `0x1400025c0`
- `0x14001d510`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001d53d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d53d`
- `ntoskrnl!KeReleaseMutex` at `0x14001d58a`
- `ntoskrnl!KeReleaseMutex` at `0x14001d58a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d5dc`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d5dc`
- `ntoskrnl!ObfReferenceObject` at `0x14001d5b8`
- `ntoskrnl!ObfReferenceObject` at `0x14001d5b8`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14001d54e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14001d56e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14001d54e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14001d56e`

## pseudocode

```c
__int64 __fastcall TmpNamespaceForEach(
        PRTL_AVL_TABLE Table,
        unsigned __int8 (__fastcall *a2)(_BYTE *, __int64),
        __int64 (__fastcall *a3)(_BYTE *, __int64),
        __int64 a4)
{
  unsigned int v8; // esi
  _BYTE *i; // rax
  _BYTE *v11; // rbp

  v8 = 0;
  KeWaitForSingleObject(&Table[1], Executive, 0, 0, 0);
  for ( i = RtlEnumerateGenericTableAvl(Table, 1u); i; i = RtlEnumerateGenericTableAvl(Table, 0) )
  {
    if ( !*i )
    {
      v11 = &i[-LOWORD(Table[1].RestartKey) - 32];
      ObfReferenceObject(v11);
      if ( !a2 || a2(v11, a4) )
        v8 = a3(v11, a4);
      ObfDereferenceObject(v11);
    }
  }
  KeReleaseMutex((PRKMUTEX)&Table[1], 0);
  return v8;
}

```

## disassembly

```asm
0x14001d510  push    rbx
0x14001d512  push    rsi
0x14001d513  push    rdi
0x14001d514  push    r12
0x14001d516  push    r14
0x14001d518  push    r15
0x14001d51a  sub     rsp, 38h
0x14001d51e  mov     r15, r9
0x14001d521  mov     r12, r8
0x14001d524  mov     r14, rdx
0x14001d527  mov     rbx, rcx
0x14001d52a  xor     esi, esi
0x14001d52c  xor     r9d, r9d; Alertable
0x14001d52f  xor     r8d, r8d; WaitMode
0x14001d532  mov     [rsp+68h+Timeout], rsi; Timeout
0x14001d537  xor     edx, edx; WaitReason
0x14001d539  add     rcx, 68h ; 'h'; Object
0x14001d53d  call    cs:__imp_KeWaitForSingleObject
0x14001d544  nop     dword ptr [rax+rax+00h]
0x14001d549  mov     dl, 1; Restart
0x14001d54b  mov     rcx, rbx; Table
0x14001d54e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14001d555  nop     dword ptr [rax+rax+00h]
0x14001d55a  test    rax, rax
0x14001d55d  jz      short loc_14001D584
0x14001d55f  mov     [rsp+68h+arg_0], rbp
0x14001d564  cmp     byte ptr [rax], 0
0x14001d567  jz      short loc_14001D5A7
0x14001d569  xor     edx, edx; Restart
0x14001d56b  mov     rcx, rbx; Table
0x14001d56e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14001d575  nop     dword ptr [rax+rax+00h]
0x14001d57a  test    rax, rax
0x14001d57d  jnz     short loc_14001D564
0x14001d57f  mov     rbp, [rsp+68h+arg_0]
0x14001d584  xor     edx, edx; Wait
0x14001d586  lea     rcx, [rbx+68h]; Mutex
0x14001d58a  call    cs:__imp_KeReleaseMutex
0x14001d591  nop     dword ptr [rax+rax+00h]
0x14001d596  mov     eax, esi
0x14001d598  add     rsp, 38h
0x14001d59c  pop     r15
0x14001d59e  pop     r14
0x14001d5a0  pop     r12
0x14001d5a2  pop     rdi
0x14001d5a3  pop     rsi
0x14001d5a4  pop     rbx
0x14001d5a5  retn
0x14001d5a7  movzx   ecx, word ptr [rbx+0A0h]
0x14001d5ae  sub     rax, rcx
0x14001d5b1  lea     rbp, [rax-20h]
0x14001d5b5  mov     rcx, rbp; Object
0x14001d5b8  call    cs:__imp_ObfReferenceObject
0x14001d5bf  nop     dword ptr [rax+rax+00h]
0x14001d5c4  test    r14, r14
0x14001d5c7  jnz     short loc_14001D5ED
0x14001d5c9  mov     rdx, r15
0x14001d5cc  mov     rcx, rbp
0x14001d5cf  mov     rax, r12
0x14001d5d2  call    _guard_dispatch_icall
0x14001d5d7  mov     esi, eax
0x14001d5d9  mov     rcx, rbp; Object
0x14001d5dc  call    cs:__imp_ObfDereferenceObject
0x14001d5e3  nop     dword ptr [rax+rax+00h]
0x14001d5e8  jmp     loc_14001D569
0x14001d5ed  mov     rdx, r15
0x14001d5f0  mov     rcx, rbp
0x14001d5f3  mov     rax, r14
0x14001d5f6  call    _guard_dispatch_icall
0x14001d5fb  test    al, al
0x14001d5fd  jz      short loc_14001D5D9
0x14001d5ff  jmp     short loc_14001D5C9
```
