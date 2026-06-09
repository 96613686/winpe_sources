# AcquireWriteAccessIfSomebodyDoesNotWaitOnSecondSpinlock(long volatile *,long volatile *,long &)

- ea: `0x18000fbdc`
- end: `0x18000fca3`
- name: `?AcquireWriteAccessIfSomebodyDoesNotWaitOnSecondSpinlock@@YAHPECJ0AEAJ@Z`
- size: `199`
- prototype: `__int64 __fastcall(volatile int *, volatile int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fb08`

## callees

- `0x18000fbdc`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall AcquireWriteAccessIfSomebodyDoesNotWaitOnSecondSpinlock(volatile int *a1, volatile int *a2, int *a3)
{
  unsigned int v6; // edi
  int v7; // ebp
  unsigned int v8; // ebx
  signed __int32 v9; // ecx
  signed __int32 v10; // edx

  v6 = 0;
  v7 = (*(__int64 (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32 + 344LL))(g_Kernel32);
  v8 = 1;
  while ( 1 )
  {
    v9 = *a3;
    if ( v9 == _InterlockedCompareExchange(a1, -1, *a3) )
      return v8;
    if ( v6 > 0x3E8 )
    {
      v6 = 0;
      if ( (*(unsigned int (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32 + 344LL))(g_Kernel32)
         - v7 > 0x3E8 )
      {
        while ( *(int *)a1 >= 0 )
        {
          v10 = *a1;
          if ( v10 == _InterlockedCompareExchange(a1, v10 | 0x80000000, v10) )
          {
            *a3 = 0x80000000;
            break;
          }
        }
      }
      (*(void (__fastcall **)(struct IKernel32Interface *, __int64))(*(_QWORD *)g_Kernel32 + 496LL))(g_Kernel32, 1);
    }
    if ( *(int *)a2 < -1 )
      return 0;
    ++v6;
  }
}

```

## disassembly

```asm
0x18000fbdc  push    rbx
0x18000fbde  push    rbp
0x18000fbdf  push    rsi
0x18000fbe0  push    rdi
0x18000fbe1  push    r13
0x18000fbe3  push    r14
0x18000fbe5  push    r15
0x18000fbe7  sub     rsp, 20h
0x18000fbeb  mov     rsi, rcx
0x18000fbee  mov     r14, r8
0x18000fbf1  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000fbf8  mov     r15, rdx
0x18000fbfb  mov     rax, [rcx]
0x18000fbfe  mov     rax, [rax+158h]
0x18000fc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc0a  xor     edi, edi
0x18000fc0c  mov     ebp, eax
0x18000fc0e  or      r13d, 0FFFFFFFFh
0x18000fc12  lea     ebx, [rdi+1]
0x18000fc15  mov     ecx, [r14]
0x18000fc18  mov     eax, ecx
0x18000fc1a  lock cmpxchg [rsi], r13d
0x18000fc1f  cmp     ecx, eax
0x18000fc21  jz      short loc_18000FC91
0x18000fc23  cmp     edi, 3E8h
0x18000fc29  jbe     short loc_18000FC83
0x18000fc2b  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000fc32  xor     edi, edi
0x18000fc34  mov     rax, [rcx]
0x18000fc37  mov     rax, [rax+158h]
0x18000fc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc43  sub     eax, ebp
0x18000fc45  cmp     eax, 3E8h
0x18000fc4a  jbe     short loc_18000FC6B
0x18000fc4c  mov     edx, [rsi]
0x18000fc4e  test    edx, edx
0x18000fc50  js      short loc_18000FC6B
0x18000fc52  mov     ecx, edx
0x18000fc54  mov     eax, edx
0x18000fc56  or      ecx, 80000000h
0x18000fc5c  lock cmpxchg [rsi], ecx
0x18000fc60  cmp     edx, eax
0x18000fc62  jnz     short loc_18000FC4C
0x18000fc64  mov     dword ptr [r14], 80000000h
0x18000fc6b  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000fc72  mov     edx, ebx
0x18000fc74  mov     rax, [rcx]
0x18000fc77  mov     rax, [rax+1F0h]
0x18000fc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc83  mov     eax, [r15]
0x18000fc86  cmp     eax, r13d
0x18000fc89  jl      short loc_18000FC8F
0x18000fc8b  add     edi, ebx
0x18000fc8d  jmp     short loc_18000FC15
0x18000fc8f  xor     ebx, ebx
0x18000fc91  mov     eax, ebx
0x18000fc93  add     rsp, 20h
0x18000fc97  pop     r15
0x18000fc99  pop     r14
0x18000fc9b  pop     r13
0x18000fc9d  pop     rdi
0x18000fc9e  pop     rsi
0x18000fc9f  pop     rbp
0x18000fca0  pop     rbx
0x18000fca1  retn
```
