# CSpinLockFileMappingArray::AcquireReadAccess(unsigned __int64,uint *)

- ea: `0x18000f830`
- end: `0x18000f91e`
- name: `?AcquireReadAccess@CSpinLockFileMappingArray@@QEAAX_KPEAI@Z`
- size: `238`
- prototype: `void __fastcall(CSpinLockFileMappingArray *__hidden this, unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f798`

## callees

- `0x18000f830`
- `0x18002a010`

## pseudocode

```c
void __fastcall CSpinLockFileMappingArray::AcquireReadAccess(
        CSpinLockFileMappingArray *this,
        __int64 a2,
        unsigned int *a3)
{
  __int64 v4; // r15
  __int64 v6; // rcx
  __int64 v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rbp
  signed __int32 v10; // edx
  int v11; // ebx
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v4 = 8 * a2;
  while ( 1 )
  {
    do
    {
      v6 = *(_QWORD *)this;
      v12 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v6 + 16LL))(v6, v4, 8, &v12);
    }
    while ( !v7 );
    v8 = 0;
    v9 = *(_QWORD *)(*(_QWORD *)this + 8LL);
    while ( 1 )
    {
      if ( v8 > 0x3E8 )
      {
        v8 = 0;
        (*(void (__fastcall **)(struct IKernel32Interface *, __int64))(*(_QWORD *)g_Kernel32 + 496LL))(g_Kernel32, 1);
      }
      if ( *(int *)(v9 + 8) < -1 )
      {
        v11 = 0;
        goto LABEL_14;
      }
      v10 = 0;
      if ( *(int *)v7 >= 0 )
        v10 = *(_DWORD *)v7;
      if ( v10 == _InterlockedCompareExchange((volatile signed __int32 *)v7, v10 + 1, v10) )
        break;
      ++v8;
    }
    v11 = 1;
    if ( a3 )
      *a3 = *(_DWORD *)(v7 + 4);
LABEL_14:
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)this + 24LL))(*(_QWORD *)this, v12);
    if ( v11 )
      break;
    (*(void (__fastcall **)(struct IKernel32Interface *, __int64))(*(_QWORD *)g_Kernel32 + 496LL))(g_Kernel32, 1);
  }
}

```

## disassembly

```asm
0x18000f830  push    rbx
0x18000f832  push    rbp
0x18000f833  push    rsi
0x18000f834  push    rdi
0x18000f835  push    r14
0x18000f837  push    r15
0x18000f839  sub     rsp, 38h
0x18000f83d  mov     rsi, r8
0x18000f840  lea     r15, ds:0[rdx*8]
0x18000f848  mov     r14, rcx
0x18000f84b  mov     rcx, [r14]
0x18000f84e  lea     r9, [rsp+68h+arg_0]
0x18000f853  mov     [rsp+68h+arg_0], 0
0x18000f85c  mov     r8d, 8
0x18000f862  mov     rdx, r15
0x18000f865  mov     rax, [rcx]
0x18000f868  mov     rax, [rax+10h]
0x18000f86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f871  mov     rdi, rax
0x18000f874  test    rax, rax
0x18000f877  jz      short loc_18000F84B
0x18000f879  mov     rcx, [r14]
0x18000f87c  xor     ebx, ebx
0x18000f87e  mov     rbp, [rcx+8]
0x18000f882  cmp     ebx, 3E8h
0x18000f888  jbe     short loc_18000F8A5
0x18000f88a  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f891  xor     ebx, ebx
0x18000f893  mov     rax, [rcx]
0x18000f896  lea     edx, [rbx+1]
0x18000f899  mov     rax, [rax+1F0h]
0x18000f8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8a5  mov     eax, [rbp+8]
0x18000f8a8  cmp     eax, 0FFFFFFFFh
0x18000f8ab  jl      short loc_18000F8D8
0x18000f8ad  mov     eax, [rdi]
0x18000f8af  xor     edx, edx
0x18000f8b1  test    eax, eax
0x18000f8b3  cmovns  edx, eax
0x18000f8b6  mov     eax, edx
0x18000f8b8  lea     ecx, [rdx+1]
0x18000f8bb  lock cmpxchg [rdi], ecx
0x18000f8bf  cmp     edx, eax
0x18000f8c1  jz      short loc_18000F8C7
0x18000f8c3  inc     ebx
0x18000f8c5  jmp     short loc_18000F882
0x18000f8c7  mov     ebx, 1
0x18000f8cc  test    rsi, rsi
0x18000f8cf  jz      short loc_18000F8DA
0x18000f8d1  mov     eax, [rdi+4]
0x18000f8d4  mov     [rsi], eax
0x18000f8d6  jmp     short loc_18000F8DA
0x18000f8d8  xor     ebx, ebx
0x18000f8da  mov     rcx, [r14]
0x18000f8dd  mov     rdx, [rsp+68h+arg_0]
0x18000f8e2  mov     rax, [rcx]
0x18000f8e5  mov     rax, [rax+18h]
0x18000f8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ee  test    ebx, ebx
0x18000f8f0  jnz     short loc_18000F910
0x18000f8f2  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f8f9  lea     edx, [rbx+1]
0x18000f8fc  mov     rax, [rcx]
0x18000f8ff  mov     rax, [rax+1F0h]
0x18000f906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f90b  jmp     loc_18000F84B
0x18000f910  add     rsp, 38h
0x18000f914  pop     r15
0x18000f916  pop     r14
0x18000f918  pop     rdi
0x18000f919  pop     rsi
0x18000f91a  pop     rbp
0x18000f91b  pop     rbx
0x18000f91c  retn
```
