# AcquireReadAccess(long volatile *)

- ea: `0x18000f73c`
- end: `0x18000f792`
- name: `?AcquireReadAccess@@YAXPECJ@Z`
- size: `86`
- prototype: `void __fastcall(volatile int *)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f798`
- `0x18000f924`
- `0x18000fa70`
- `0x180011aa0`
- `0x1800123a0`
- `0x1800179a4`
- `0x180018ac0`
- `0x180018dc0`
- `0x180018ee0`
- `0x180019180`
- `0x1800192f0`
- `0x1800194f0`
- `0x180019680`
- `0x1800197c0`
- `0x1800198d0`
- `0x1800199e0`
- `0x180019be0`

## callees

- `0x18000f73c`
- `0x18002a010`

## pseudocode

```c
void __fastcall AcquireReadAccess(volatile int *a1)
{
  unsigned int v2; // ebx
  signed __int32 v3; // edx

  v2 = 0;
  do
  {
    if ( v2 > 0x3E8 )
    {
      v2 = 0;
      (*(void (__fastcall **)(struct IKernel32Interface *, __int64))(*(_QWORD *)g_Kernel32 + 496LL))(g_Kernel32, 1);
    }
    v3 = 0;
    ++v2;
    if ( *(int *)a1 >= 0 )
      v3 = *a1;
  }
  while ( v3 != _InterlockedCompareExchange(a1, v3 + 1, v3) );
}

```

## disassembly

```asm
0x18000f73c  mov     [rsp+arg_0], rbx
0x18000f741  push    rdi
0x18000f742  sub     rsp, 20h
0x18000f746  mov     rdi, rcx
0x18000f749  xor     ebx, ebx
0x18000f74b  cmp     ebx, 3E8h
0x18000f751  jbe     short loc_18000F76E
0x18000f753  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f75a  xor     ebx, ebx
0x18000f75c  mov     rax, [rcx]
0x18000f75f  lea     edx, [rbx+1]
0x18000f762  mov     rax, [rax+1F0h]
0x18000f769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f76e  mov     eax, [rdi]
0x18000f770  xor     edx, edx
0x18000f772  inc     ebx
0x18000f774  test    eax, eax
0x18000f776  cmovns  edx, eax
0x18000f779  mov     eax, edx
0x18000f77b  lea     ecx, [rdx+1]
0x18000f77e  lock cmpxchg [rdi], ecx
0x18000f782  cmp     edx, eax
0x18000f784  jnz     short loc_18000F74B
0x18000f786  mov     rbx, [rsp+28h+arg_0]
0x18000f78b  add     rsp, 20h
0x18000f78f  pop     rdi
0x18000f790  retn
```
