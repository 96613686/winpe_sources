# SXReader::Release(void)

- ea: `0x100404880`
- end: `0x1004048da`
- name: `?Release@SXReader@@UEAAKXZ`
- size: `90`
- prototype: `unsigned int __fastcall(SXReader *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x100406410`
- `0x100406450`

## callees

- `0x100404880`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXReader::Release(SXReader *this)
{
  unsigned __int32 v1; // ebx
  __int64 v2; // rdi

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 368);
  if ( v1 )
    return v1;
  v2 = *((_QWORD *)this + 1);
  (**(void (__fastcall ***)(SXReader *, __int64))this)(this, 1);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x100404880  push    rbx
0x100404882  sub     rsp, 20h
0x100404886  mov     ebx, 0FFFFFFFFh
0x10040488b  lock xadd [rcx+5C0h], ebx
0x100404893  sub     ebx, 1
0x100404896  jnz     short loc_1004048D2
0x100404898  mov     rax, [rcx]
0x10040489b  lea     edx, [rbx+1]
0x10040489e  mov     [rsp+28h+arg_0], rdi
0x1004048a3  mov     rdi, [rcx+8]
0x1004048a7  mov     rax, [rax]
0x1004048aa  call    cs:__guard_dispatch_icall_fptr
0x1004048b0  test    rdi, rdi
0x1004048b3  jz      short loc_1004048C5
0x1004048b5  mov     rdx, [rdi]
0x1004048b8  mov     rcx, rdi
0x1004048bb  mov     rax, [rdx+10h]
0x1004048bf  call    cs:__guard_dispatch_icall_fptr
0x1004048c5  mov     rdi, [rsp+28h+arg_0]
0x1004048ca  mov     eax, ebx
0x1004048cc  add     rsp, 20h
0x1004048d0  pop     rbx
0x1004048d1  retn
0x1004048d2  mov     eax, ebx
0x1004048d4  add     rsp, 20h
0x1004048d8  pop     rbx
0x1004048d9  retn
```
