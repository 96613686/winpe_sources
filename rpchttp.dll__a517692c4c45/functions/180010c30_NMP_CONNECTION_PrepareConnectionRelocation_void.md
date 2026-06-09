# NMP_CONNECTION::PrepareConnectionRelocation(void)

- ea: `0x180010c30`
- end: `0x180010cc6`
- name: `?PrepareConnectionRelocation@NMP_CONNECTION@@UEAAXXZ`
- size: `150`
- prototype: `void __fastcall(NMP_CONNECTION *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010c30`
- `0x18001ef00`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180010c4b`
- `KERNEL32!GetCurrentThreadId` at `0x180010c66`
- `KERNEL32!GetCurrentThreadId` at `0x180010c4b`
- `KERNEL32!GetCurrentThreadId` at `0x180010c66`

## pseudocode

```c
void __fastcall NMP_CONNECTION::PrepareConnectionRelocation(NMP_CONNECTION *this)
{
  __int64 v1; // rbx
  NMP_CONNECTION **v3; // rdx
  NMP_CONNECTION **v4; // rcx

  v1 = *((_QWORD *)this + 17);
  if ( *(_DWORD *)(v1 + 120)
    || _InterlockedCompareExchange(
         (volatile signed __int32 *)(v1 + 120),
         GetCurrentThreadId() & 0xFFFFFFF | 0x10000000,
         0) )
  {
    if ( (*(_DWORD *)(v1 + 120) & 0xFFFFFFF) == (GetCurrentThreadId() & 0xFFFFFFF) )
      _InterlockedExchange((volatile __int32 *)(v1 + 120), *(_DWORD *)(v1 + 120) + 0x10000000);
    else
      CSpinLock::_LockSpin((CSpinLock *)(v1 + 120));
  }
  v3 = (NMP_CONNECTION **)*((_QWORD *)this + 20);
  if ( v3[1] != (NMP_CONNECTION *)((char *)this + 160)
    || (v4 = (NMP_CONNECTION **)*((_QWORD *)this + 21), *v4 != (NMP_CONNECTION *)((char *)this + 160)) )
  {
    __fastfail(3u);
  }
  *v4 = (NMP_CONNECTION *)v3;
  v3[1] = (NMP_CONNECTION *)v4;
}

```

## disassembly

```asm
0x180010c30  mov     [rsp+arg_0], rbx
0x180010c35  push    rdi
0x180010c36  sub     rsp, 20h
0x180010c3a  mov     rbx, [rcx+88h]
0x180010c41  mov     rdi, rcx
0x180010c44  mov     eax, [rbx+78h]
0x180010c47  test    eax, eax
0x180010c49  jnz     short loc_180010C66
0x180010c4b  call    cs:__imp_GetCurrentThreadId
0x180010c51  mov     edx, eax
0x180010c53  and     edx, 0FFFFFFFh
0x180010c59  bts     edx, 1Ch
0x180010c5d  xor     eax, eax
0x180010c5f  lock cmpxchg [rbx+78h], edx
0x180010c64  jz      short loc_180010C94
0x180010c66  call    cs:__imp_GetCurrentThreadId
0x180010c6c  mov     ecx, [rbx+78h]
0x180010c6f  and     eax, 0FFFFFFFh
0x180010c74  and     ecx, 0FFFFFFFh
0x180010c7a  cmp     ecx, eax
0x180010c7c  jnz     short loc_180010C8B
0x180010c7e  mov     eax, [rbx+78h]
0x180010c81  add     eax, 10000000h
0x180010c86  xchg    eax, [rbx+78h]
0x180010c89  jmp     short loc_180010C94
0x180010c8b  lea     rcx, [rbx+78h]; this
0x180010c8f  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x180010c94  lea     rax, [rdi+0A0h]
0x180010c9b  mov     rdx, [rax]
0x180010c9e  cmp     [rdx+8], rax
0x180010ca2  jnz     short loc_180010CBF
0x180010ca4  mov     rcx, [rax+8]
0x180010ca8  cmp     [rcx], rax
0x180010cab  jnz     short loc_180010CBF
0x180010cad  mov     rbx, [rsp+28h+arg_0]
0x180010cb2  mov     [rcx], rdx
0x180010cb5  mov     [rdx+8], rcx
0x180010cb9  add     rsp, 20h
0x180010cbd  pop     rdi
0x180010cbe  retn
0x180010cbf  mov     ecx, 3
0x180010cc4  int     29h; Win8: RtlFailFast(ecx)
```
