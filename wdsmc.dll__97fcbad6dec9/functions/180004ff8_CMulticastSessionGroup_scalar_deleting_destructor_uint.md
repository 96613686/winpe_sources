# CMulticastSessionGroup::`scalar deleting destructor'(uint)

- ea: `0x180004ff8`
- end: `0x18000508f`
- name: `??_GCMulticastSessionGroup@@QEAAPEAXI@Z`
- size: `151`
- prototype: `void *__fastcall(CMulticastSessionGroup *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000433c`
- `0x180004438`
- `0x180004c60`
- `0x180018488`

## callees

- `0x180004ff8`
- `0x1800193f8`
- `0x18001a83c`
- `0x18001a9a8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180005068`
- `KERNEL32!DeleteCriticalSection` at `0x180005068`

## pseudocode

```c
CMulticastSessionGroup *__fastcall CMulticastSessionGroup::`scalar deleting destructor'(CMulticastSessionGroup *this)
{
  __int64 v2; // rcx
  void *v3; // r14
  __int64 v4; // rdi
  CMulticastSession **v5; // rsi

  CMulticastSessionGroup::Shutdown(this);
  v2 = *((_QWORD *)this + 38);
  if ( v2 )
  {
    v3 = (void *)(v2 - 8);
    v4 = *(_QWORD *)(v2 - 8);
    v5 = (CMulticastSession **)(v2 + 24 * v4);
    while ( v4 )
    {
      v5 -= 3;
      --v4;
      if ( *v5 )
      {
        CMulticastSession::`scalar deleting destructor'(*v5);
        *v5 = 0;
      }
    }
    operator delete(v3);
    *((_QWORD *)this + 38) = 0;
  }
  *((_DWORD *)this + 78) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004ff8  mov     [rsp+arg_0], rbx
0x180004ffd  mov     [rsp+arg_8], rsi
0x180005002  mov     [rsp+arg_10], rdi
0x180005007  push    r14
0x180005009  sub     rsp, 20h
0x18000500d  mov     rbx, rcx
0x180005010  call    ?Shutdown@CMulticastSessionGroup@@QEAAKXZ; CMulticastSessionGroup::Shutdown(void)
0x180005015  mov     rcx, [rbx+130h]
0x18000501c  test    rcx, rcx
0x18000501f  jz      short loc_18000505E
0x180005021  lea     r14, [rcx-8]
0x180005025  mov     rdi, [r14]
0x180005028  lea     rax, [rdi+rdi*2]
0x18000502c  lea     rsi, [rcx+rax*8]
0x180005030  jmp     short loc_18000504A
0x180005032  lea     rsi, [rsi-18h]
0x180005036  dec     rdi
0x180005039  mov     rcx, [rsi]; this
0x18000503c  test    rcx, rcx
0x18000503f  jz      short loc_18000504A
0x180005041  call    ??_GCMulticastSession@@QEAAPEAXI@Z; CMulticastSession::`scalar deleting destructor'(uint)
0x180005046  and     qword ptr [rsi], 0
0x18000504a  test    rdi, rdi
0x18000504d  jnz     short loc_180005032
0x18000504f  mov     rcx, r14; void *
0x180005052  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005057  and     [rbx+130h], rdi
0x18000505e  and     dword ptr [rbx+138h], 0
0x180005065  mov     rcx, rbx; lpCriticalSection
0x180005068  call    cs:__imp_DeleteCriticalSection
0x18000506e  mov     rcx, rbx; void *
0x180005071  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005076  mov     rsi, [rsp+28h+arg_8]
0x18000507b  mov     rax, rbx
0x18000507e  mov     rbx, [rsp+28h+arg_0]
0x180005083  mov     rdi, [rsp+28h+arg_10]
0x180005088  add     rsp, 20h
0x18000508c  pop     r14
0x18000508e  retn
```
