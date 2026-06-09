# SAXWriter::Release(void)

- ea: `0x10041d020`
- end: `0x10041d07d`
- name: `?Release@SAXWriter@@UEAAKXZ`
- size: `93`
- prototype: `unsigned int __fastcall(SAXWriter *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1004202c0`
- `0x1004202f0`
- `0x100420320`
- `0x100420330`
- `0x100420360`

## callees

- `0x10041d020`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::Release(SAXWriter *this)
{
  unsigned __int32 v1; // ebx
  __int64 v2; // rdi
  char *v3; // rcx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 12);
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
0x10041d020  push    rbx
0x10041d022  sub     rsp, 20h
0x10041d026  mov     ebx, 0FFFFFFFFh
0x10041d02b  lock xadd [rcx+30h], ebx
0x10041d030  sub     ebx, 1
0x10041d033  jnz     short loc_10041D075
0x10041d035  mov     [rsp+28h+arg_0], rdi
0x10041d03a  mov     rdi, [rcx-8]
0x10041d03e  add     rcx, 0FFFFFFFFFFFFFFF0h
0x10041d042  jz      short loc_10041D053
0x10041d044  mov     rax, [rcx]
0x10041d047  lea     edx, [rbx+1]
0x10041d04a  mov     rax, [rax]
0x10041d04d  call    cs:__guard_dispatch_icall_fptr
0x10041d053  test    rdi, rdi
0x10041d056  jz      short loc_10041D068
0x10041d058  mov     rdx, [rdi]
0x10041d05b  mov     rcx, rdi
0x10041d05e  mov     rax, [rdx+10h]
0x10041d062  call    cs:__guard_dispatch_icall_fptr
0x10041d068  mov     rdi, [rsp+28h+arg_0]
0x10041d06d  mov     eax, ebx
0x10041d06f  add     rsp, 20h
0x10041d073  pop     rbx
0x10041d074  retn
0x10041d075  mov     eax, ebx
0x10041d077  add     rsp, 20h
0x10041d07b  pop     rbx
0x10041d07c  retn
```
