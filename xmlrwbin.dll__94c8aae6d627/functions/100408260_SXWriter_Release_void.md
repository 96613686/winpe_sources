# SXWriter::Release(void)

- ea: `0x100408260`
- end: `0x1004082c0`
- name: `?Release@SXWriter@@UEAAKXZ`
- size: `96`
- prototype: `unsigned int __fastcall(SXWriter *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x100407bf0`
- `0x100407c00`
- `0x100407c50`
- `0x100407c60`
- `0x100407c90`
- `0x100407ca0`
- `0x100407cf0`

## callees

- `0x100408260`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXWriter::Release(SXWriter *this)
{
  unsigned __int32 v1; // ebx
  __int64 v2; // rdi
  char *v3; // rcx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 59);
  if ( v1 )
    return v1;
  v2 = *((_QWORD *)this - 1);
  v3 = (char *)this - 16;
  if ( v3 )
    (**(void (__fastcall ***)(char *, __int64))v3)(v3, 1);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x100408260  push    rbx
0x100408262  sub     rsp, 20h
0x100408266  mov     ebx, 0FFFFFFFFh
0x10040826b  lock xadd [rcx+0ECh], ebx
0x100408273  sub     ebx, 1
0x100408276  jnz     short loc_1004082B8
0x100408278  mov     [rsp+28h+arg_0], rdi
0x10040827d  mov     rdi, [rcx-8]
0x100408281  add     rcx, 0FFFFFFFFFFFFFFF0h
0x100408285  jz      short loc_100408296
0x100408287  mov     rax, [rcx]
0x10040828a  lea     edx, [rbx+1]
0x10040828d  mov     rax, [rax]
0x100408290  call    cs:__guard_dispatch_icall_fptr
0x100408296  test    rdi, rdi
0x100408299  jz      short loc_1004082AB
0x10040829b  mov     rdx, [rdi]
0x10040829e  mov     rcx, rdi
0x1004082a1  mov     rax, [rdx+10h]
0x1004082a5  call    cs:__guard_dispatch_icall_fptr
0x1004082ab  mov     rdi, [rsp+28h+arg_0]
0x1004082b0  mov     eax, ebx
0x1004082b2  add     rsp, 20h
0x1004082b6  pop     rbx
0x1004082b7  retn
0x1004082b8  mov     eax, ebx
0x1004082ba  add     rsp, 20h
0x1004082be  pop     rbx
0x1004082bf  retn
```
