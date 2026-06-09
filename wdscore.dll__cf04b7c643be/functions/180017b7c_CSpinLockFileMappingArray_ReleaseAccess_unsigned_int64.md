# CSpinLockFileMappingArray::ReleaseAccess(unsigned __int64)

- ea: `0x180017b7c`
- end: `0x180017bcf`
- name: `?ReleaseAccess@CSpinLockFileMappingArray@@QEAAX_K@Z`
- size: `83`
- prototype: `void __fastcall(CSpinLockFileMappingArray *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f798`
- `0x18000fa70`
- `0x180011aa0`
- `0x180017acc`

## callees

- `0x180017ab4`
- `0x18002a010`

## pseudocode

```c
void __fastcall CSpinLockFileMappingArray::ReleaseAccess(CSpinLockFileMappingArray *this, __int64 a2)
{
  volatile int *v3; // rax
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  v3 = (volatile int *)(*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64 *))(**(_QWORD **)this + 16LL))(
                         *(_QWORD *)this,
                         8 * a2,
                         8,
                         &v4);
  ReleaseAccess(v3);
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)this + 24LL))(*(_QWORD *)this, v4);
}

```

## disassembly

```asm
0x180017b7c  push    rbx
0x180017b7e  sub     rsp, 30h
0x180017b82  mov     rbx, rcx
0x180017b85  mov     [rsp+38h+arg_0], 0
0x180017b8e  mov     rcx, [rcx]
0x180017b91  lea     r9, [rsp+38h+arg_0]
0x180017b96  shl     rdx, 3
0x180017b9a  mov     r8d, 8
0x180017ba0  mov     rax, [rcx]
0x180017ba3  mov     rax, [rax+10h]
0x180017ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bac  mov     rcx, rax; volatile int *
0x180017baf  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180017bb4  mov     rcx, [rbx]
0x180017bb7  mov     rdx, [rsp+38h+arg_0]
0x180017bbc  mov     rax, [rcx]
0x180017bbf  mov     rax, [rax+18h]
0x180017bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bc8  add     rsp, 30h
0x180017bcc  pop     rbx
0x180017bcd  retn
```
