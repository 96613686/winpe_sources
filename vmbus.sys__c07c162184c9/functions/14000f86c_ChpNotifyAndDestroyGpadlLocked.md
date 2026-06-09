# ChpNotifyAndDestroyGpadlLocked

- ea: `0x14000f86c`
- end: `0x14000f904`
- name: `ChpNotifyAndDestroyGpadlLocked`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000f6c4`
- `0x14001152c`

## callees

- `0x14000f5f0`
- `0x14000f7e4`
- `0x14000f86c`
- `0x140017190`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000f8c7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000f8c7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f8e1`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f8e1`
- `ntoskrnl!MmUnlockPages` at `0x14000f8ad`
- `ntoskrnl!MmUnlockPages` at `0x14000f8ad`

## pseudocode

```c
void __fastcall ChpNotifyAndDestroyGpadlLocked(__int64 a1, __int64 a2)
{
  void (__fastcall *v4)(__int64); // rbp
  int v5; // edx
  __int64 v6; // r14

  ChpMakeGpadlHostInvisible(a2);
  v4 = *(void (__fastcall **)(__int64))(a2 + 96);
  *(_DWORD *)(a2 + 16) = 6;
  if ( v4 )
  {
    v5 = *(_DWORD *)(a2 + 68);
    v6 = *(_QWORD *)(a2 + 104);
    *(_QWORD *)(a2 + 96) = 0;
    if ( (v5 & 2) != 0 )
    {
      MmUnlockPages(*(PMDL *)(a2 + 24));
      *(_DWORD *)(a2 + 68) &= ~2u;
    }
    ExReleaseFastMutex((PFAST_MUTEX)(a1 + 432));
    v4(v6);
    ExAcquireFastMutex((PFAST_MUTEX)(a1 + 432));
  }
  ChpDestroyGpadlLocked(a1, a2);
}

```

## disassembly

```asm
0x14000f86c  push    rbx
0x14000f86e  push    rbp
0x14000f86f  push    rsi
0x14000f870  push    rdi
0x14000f871  push    r14
0x14000f873  sub     rsp, 20h
0x14000f877  mov     rsi, rcx
0x14000f87a  mov     rdi, rdx
0x14000f87d  mov     rcx, rdx
0x14000f880  call    ChpMakeGpadlHostInvisible
0x14000f885  mov     rbp, [rdi+60h]
0x14000f889  mov     dword ptr [rdi+10h], 6
0x14000f890  test    rbp, rbp
0x14000f893  jz      short loc_14000F8ED
0x14000f895  mov     edx, [rdi+44h]
0x14000f898  mov     r14, [rdi+68h]
0x14000f89c  mov     qword ptr [rdi+60h], 0
0x14000f8a4  test    dl, 2
0x14000f8a7  jz      short loc_14000F8BD
0x14000f8a9  mov     rcx, [rdi+18h]; MemoryDescriptorList
0x14000f8ad  call    cs:__imp_MmUnlockPages
0x14000f8b4  nop     dword ptr [rax+rax+00h]
0x14000f8b9  and     dword ptr [rdi+44h], 0FFFFFFFDh
0x14000f8bd  lea     rbx, [rsi+1B0h]
0x14000f8c4  mov     rcx, rbx; FastMutex
0x14000f8c7  call    cs:__imp_ExReleaseFastMutex
0x14000f8ce  nop     dword ptr [rax+rax+00h]
0x14000f8d3  mov     rcx, r14
0x14000f8d6  mov     rax, rbp
0x14000f8d9  call    _guard_dispatch_icall
0x14000f8de  mov     rcx, rbx; FastMutex
0x14000f8e1  call    cs:__imp_ExAcquireFastMutex
0x14000f8e8  nop     dword ptr [rax+rax+00h]
0x14000f8ed  mov     rdx, rdi
0x14000f8f0  mov     rcx, rsi
0x14000f8f3  call    ChpDestroyGpadlLocked
0x14000f8f8  add     rsp, 20h
0x14000f8fc  pop     r14
0x14000f8fe  pop     rdi
0x14000f8ff  pop     rsi
0x14000f900  pop     rbp
0x14000f901  pop     rbx
0x14000f902  retn
```
