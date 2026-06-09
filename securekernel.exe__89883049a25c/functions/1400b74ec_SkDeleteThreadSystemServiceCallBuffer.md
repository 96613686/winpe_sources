# SkDeleteThreadSystemServiceCallBuffer

- ea: `0x1400b74ec`
- end: `0x1400b766c`
- name: `SkDeleteThreadSystemServiceCallBuffer`
- size: `384`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140033b58`
- `0x1400ae98c`

## callees

- `0x140002900`
- `0x14000b084`
- `0x140037e68`
- `0x140095cd8`
- `0x1400b74ec`
- `0x1400ef680`

## pseudocode

```c
__int64 __fastcall SkDeleteThreadSystemServiceCallBuffer(_QWORD *a1)
{
  __int64 result; // rax
  _QWORD *StackBase; // rsi
  __int64 *v3; // rbx
  __int64 v4; // rdi
  __int128 v5; // rax
  __int128 v6; // rtt
  __int64 v7; // rdx
  __int64 v8; // r14
  __int64 *v9; // rax
  __int64 **v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  ULONG_PTR RegionSize; // [rsp+60h] [rbp+8h] BYREF
  PVOID BaseAddress; // [rsp+68h] [rbp+10h] BYREF

  result = a1[3];
  if ( result )
  {
    StackBase = KeGetPcr()->NtTib.StackBase;
    v3 = (__int64 *)a1[38];
    v4 = a1[9];
    v5 = (__int64)((result & 0xFFFFFFFFFFFFF000uLL) - v3[2]);
    a1[3] = 0;
    v6 = v5;
    a1[38] = 0;
    v7 = StackBase[18];
    v8 = v6 / 4096;
    if ( v7 )
      --*(_WORD *)(v7 + *((_QWORD *)&xmmword_140167150 + 1));
    SkAcquirePushLockExclusive(v4 + 312);
    _InterlockedAnd16((volatile signed __int16 *)v3 + 12, ~(1 << v8));
    if ( *((_WORD *)v3 + 12) )
    {
      if ( !*(_QWORD *)(v4 + 304) )
        *(_QWORD *)(v4 + 304) = v3;
      v3 = 0;
    }
    else
    {
      v9 = (__int64 *)*v3;
      if ( *(__int64 **)(*v3 + 8) != v3 || (v10 = (__int64 **)v3[1], *v10 != v3) )
        __fastfail(3u);
      *v10 = v9;
      v9[1] = (__int64)v10;
      if ( *(__int64 **)(v4 + 304) == v3 )
        *(_QWORD *)(v4 + 304) = 0;
    }
    result = RtlReleaseSRWLockExclusive(v4 + 312);
    v13 = StackBase[18];
    if ( v13 )
    {
      result = *((_QWORD *)&xmmword_140167150 + 1);
      if ( (*(_WORD *)(v13 + *((_QWORD *)&xmmword_140167150 + 1)))++ == 0xFFFF )
      {
        result = xmmword_140167160 + StackBase[17];
        if ( *(_QWORD *)(v13 + xmmword_140167160) != result )
          result = SkiCheckForKernelApcDelivery(xmmword_140167160, v13, v11, v12);
      }
    }
    if ( v3 )
    {
      BaseAddress = (PVOID)v3[2];
      RegionSize = 0;
      ZwFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, &RegionSize, 0x8000u);
      return SkFreePool(512, v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400b74ec  mov     [rsp+arg_10], rbx
0x1400b74f1  push    rbp
0x1400b74f2  push    rsi
0x1400b74f3  push    rdi
0x1400b74f4  push    r12
0x1400b74f6  push    r13
0x1400b74f8  push    r14
0x1400b74fa  push    r15
0x1400b74fc  sub     rsp, 20h
0x1400b7500  mov     rax, [rcx+18h]
0x1400b7504  xor     r15d, r15d
0x1400b7507  test    rax, rax
0x1400b750a  jz      loc_1400B764F
0x1400b7510  mov     rsi, gs:8
0x1400b7519  and     rax, 0FFFFFFFFFFFFF000h
0x1400b751f  mov     rbx, [rcx+130h]
0x1400b7526  mov     r8d, 1000h
0x1400b752c  mov     rdi, [rcx+48h]
0x1400b7530  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400b7534  sub     rax, [rbx+10h]
0x1400b7538  cqo
0x1400b753a  mov     [rcx+18h], r15
0x1400b753e  idiv    r8
0x1400b7541  mov     [rcx+130h], r15
0x1400b7548  mov     rdx, [rsi+90h]
0x1400b754f  mov     r14, rax
0x1400b7552  test    rdx, rdx
0x1400b7555  jz      short loc_1400B7564
0x1400b7557  mov     rcx, qword ptr cs:xmmword_140167150+8
0x1400b755e  add     [rdx+rcx], r13w
0x1400b7563  nop
0x1400b7564  lea     rbp, [rdi+138h]
0x1400b756b  mov     rcx, rbp
0x1400b756e  call    SkAcquirePushLockExclusive
0x1400b7573  mov     r12d, 1
0x1400b7579  mov     ecx, r14d
0x1400b757c  mov     eax, r12d
0x1400b757f  shl     ax, cl
0x1400b7582  not     ax
0x1400b7585  lock and [rbx+18h], ax
0x1400b758a  cmp     [rbx+18h], r15w
0x1400b758f  jz      short loc_1400B75A6
0x1400b7591  cmp     [rdi+130h], r15
0x1400b7598  jnz     short loc_1400B75A1
0x1400b759a  mov     [rdi+130h], rbx
0x1400b75a1  mov     rbx, r15
0x1400b75a4  jmp     short loc_1400B75D7
0x1400b75a6  mov     rax, [rbx]
0x1400b75a9  cmp     [rax+8], rbx
0x1400b75ad  jnz     loc_1400B7665
0x1400b75b3  mov     rdx, [rbx+8]
0x1400b75b7  cmp     [rdx], rbx
0x1400b75ba  jnz     loc_1400B7665
0x1400b75c0  mov     [rdx], rax
0x1400b75c3  mov     [rax+8], rdx
0x1400b75c7  cmp     [rdi+130h], rbx
0x1400b75ce  jnz     short loc_1400B75D7
0x1400b75d0  mov     [rdi+130h], r15
0x1400b75d7  mov     rcx, rbp
0x1400b75da  call    RtlReleaseSRWLockExclusive
0x1400b75df  mov     rdx, [rsi+90h]
0x1400b75e6  test    rdx, rdx
0x1400b75e9  jz      short loc_1400B7617
0x1400b75eb  nop
0x1400b75ec  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400b75f3  add     [rdx+rax], r12w
0x1400b75f8  jnz     short loc_1400B7617
0x1400b75fa  mov     rax, [rsi+88h]
0x1400b7601  nop
0x1400b7602  mov     rcx, qword ptr cs:xmmword_140167160
0x1400b7609  add     rax, rcx
0x1400b760c  cmp     [rdx+rcx], rax
0x1400b7610  jz      short loc_1400B7617
0x1400b7612  call    SkiCheckForKernelApcDelivery
0x1400b7617  test    rbx, rbx
0x1400b761a  jz      short loc_1400B764F
0x1400b761c  mov     rax, [rbx+10h]
0x1400b7620  lea     r8, [rsp+58h+RegionSize]; RegionSize
0x1400b7625  mov     r9d, 8000h; FreeType
0x1400b762b  mov     [rsp+58h+BaseAddress], rax
0x1400b7630  lea     rdx, [rsp+58h+BaseAddress]; BaseAddress
0x1400b7635  mov     [rsp+58h+RegionSize], r15
0x1400b763a  mov     rcx, r13; ProcessHandle
0x1400b763d  call    ZwFreeVirtualMemory
0x1400b7642  mov     rdx, rbx
0x1400b7645  mov     ecx, 200h
0x1400b764a  call    SkFreePool
0x1400b764f  mov     rbx, [rsp+58h+arg_10]
0x1400b7654  add     rsp, 20h
0x1400b7658  pop     r15
0x1400b765a  pop     r14
0x1400b765c  pop     r13
0x1400b765e  pop     r12
0x1400b7660  pop     rdi
0x1400b7661  pop     rsi
0x1400b7662  pop     rbp
0x1400b7663  retn
0x1400b7665  mov     ecx, 3
0x1400b766a  int     29h; Win8: RtlFailFast(ecx)
```
