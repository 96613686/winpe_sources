# HTTP2Channel::AsyncCompleteHelper(long)

- ea: `0x180005320`
- end: `0x180005398`
- name: `?AsyncCompleteHelper@HTTP2Channel@@UEAAJJ@Z`
- size: `120`
- prototype: `__int64 __fastcall(HTTP2Channel *__hidden this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005320`
- `0x18000f3fc`
- `0x180016df8`
- `0x18001ac60`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2Channel::AsyncCompleteHelper(HTTP2Channel *this, unsigned int a2)
{
  unsigned int v2; // ebx
  struct HTTP2VirtualConnection *v4; // rax

  v2 = a2;
  if ( a2 == -1073606614 )
  {
    v4 = HTTP2Channel::LockParentPointer(this);
    if ( v4 )
    {
      v2 = (*(__int64 (__fastcall **)(struct HTTP2VirtualConnection *, __int64))(*(_QWORD *)v4 + 128LL))(v4, 1);
      HTTP2Channel::UnlockParentPointer(this);
    }
    else
    {
      v2 = 0;
    }
  }
  else if ( a2 && a2 != -1073606615 )
  {
    (*(void (__fastcall **)(HTTP2Channel *))(*(_QWORD *)this + 136LL))(this);
  }
  HTTP2Channel::RemoveReference(this);
  return v2;
}

```

## disassembly

```asm
0x180005320  mov     [rsp+arg_0], rbx
0x180005325  push    rdi
0x180005326  sub     rsp, 20h
0x18000532a  mov     ebx, edx
0x18000532c  mov     rdi, rcx
0x18000532f  cmp     edx, 0C002102Ah
0x180005335  jnz     short loc_180005368
0x180005337  call    ?LockParentPointer@HTTP2Channel@@QEAAPEAVHTTP2VirtualConnection@@XZ; HTTP2Channel::LockParentPointer(void)
0x18000533c  mov     rcx, rax
0x18000533f  test    rax, rax
0x180005342  jz      short loc_180005364
0x180005344  mov     rdx, [rax]
0x180005347  mov     rax, [rdx+80h]
0x18000534e  mov     edx, 1
0x180005353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005358  mov     rcx, rdi; this
0x18000535b  mov     ebx, eax
0x18000535d  call    ?UnlockParentPointer@HTTP2Channel@@QEAAXXZ; HTTP2Channel::UnlockParentPointer(void)
0x180005362  jmp     short loc_180005383
0x180005364  xor     ebx, ebx
0x180005366  jmp     short loc_180005383
0x180005368  test    edx, edx
0x18000536a  jz      short loc_180005383
0x18000536c  cmp     edx, 0C0021029h
0x180005372  jz      short loc_180005383
0x180005374  mov     rax, [rcx]
0x180005377  mov     rax, [rax+88h]
0x18000537e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005383  mov     rcx, rdi; this
0x180005386  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x18000538b  mov     eax, ebx
0x18000538d  mov     rbx, [rsp+28h+arg_0]
0x180005392  add     rsp, 20h
0x180005396  pop     rdi
0x180005397  retn
```
