# CTSReaderWriterLock::_LockSpin(CTSReaderWriterLock::SPIN_TYPE)

- ea: `0x18001b848`
- end: `0x18001b947`
- name: `?_LockSpin@CTSReaderWriterLock@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `255`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b70c`
- `0x18001ba38`

## callees

- `0x18001b2e4`
- `0x18001b580`
- `0x18001b848`
- `0x18001b950`
- `0x18001b984`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001b91c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001b91c`
- `KERNEL32!SwitchToThread` at `0x18001b910`
- `KERNEL32!SwitchToThread` at `0x18001b910`

## pseudocode

```c
__int64 __fastcall CTSReaderWriterLock::_LockSpin(CTSReaderWriterLock *a1, int a2)
{
  DWORD v3; // ebp
  double v5; // xmm0_8
  int v6; // ebx
  int v7; // edi
  __int64 result; // rax
  int v9; // eax
  int v10; // r8d
  unsigned int v11; // [rsp+68h] [rbp+10h] BYREF

  v3 = 0;
  v11 = 0;
  PAL_System_ThreadGetId(&v11);
  v5 = *(double *)&`CTSReaderWriterLock::_RandomBackoffFactor'::`2'::s_aFactors[v11 % 0xD] * 4000.0;
LABEL_2:
  v6 = (int)v5;
  if ( (int)v5 <= 10000 )
  {
    if ( v6 <= 100 )
      v6 = 100;
  }
  else
  {
    v6 = 10000;
  }
  v7 = 1;
  if ( *((_DWORD *)a1 + 3) )
    v7 = v6;
  while ( 1 )
  {
    if ( a2 == 1 )
    {
      result = CTSReaderWriterLock::_TryWriteLock(a1, 0);
    }
    else if ( a2 == 2 )
    {
      result = CTSReaderWriterLock::_TryReadLock(a1);
    }
    else
    {
      result = 0;
      if ( (unsigned __int16)*(_DWORD *)a1 != 0xFFFF )
      {
        v9 = PAL_System_AtomicCompareAndExchange(a1, (unsigned int)(*(_DWORD *)a1 + 1));
        if ( v10 == v9 )
          result = 1;
      }
    }
    if ( (_DWORD)result )
      return result;
    if ( !--v7 )
    {
      if ( !SwitchToThread() )
        Sleep(v3);
      v3 ^= 1u;
      v5 = (double)v6 * 0.5;
      goto LABEL_2;
    }
  }
}

```

## disassembly

```asm
0x18001b848  push    rbx
0x18001b84a  push    rbp
0x18001b84b  push    rsi
0x18001b84c  push    rdi
0x18001b84d  push    r13
0x18001b84f  push    r14
0x18001b851  sub     rsp, 28h
0x18001b855  mov     rsi, rcx
0x18001b858  xor     ebp, ebp
0x18001b85a  lea     rcx, [rsp+58h+arg_8]
0x18001b85f  mov     [rsp+58h+arg_8], ebp
0x18001b863  mov     r14d, edx
0x18001b866  call    PAL_System_ThreadGetId
0x18001b86b  mov     r8d, [rsp+58h+arg_8]
0x18001b870  lea     rcx, ?s_aFactors@?1??_RandomBackoffFactor@CTSReaderWriterLock@@AEAANXZ@4QBNB; double const near * const `CTSReaderWriterLock::_RandomBackoffFactor(void)'::`2'::s_aFactors
0x18001b877  mov     eax, 4EC4EC4Fh
0x18001b87c  lea     r13d, [rbp+64h]
0x18001b880  mul     r8d
0x18001b883  shr     edx, 2
0x18001b886  imul    eax, edx, 0Dh
0x18001b889  sub     r8d, eax
0x18001b88c  movsd   xmm0, qword ptr [rcx+r8*8]
0x18001b892  mulsd   xmm0, cs:__real@40af400000000000
0x18001b89a  cvttsd2si ebx, xmm0
0x18001b89e  cmp     ebx, 2710h
0x18001b8a4  jle     short loc_18001B8AD
0x18001b8a6  mov     ebx, 2710h
0x18001b8ab  jmp     short loc_18001B8B4
0x18001b8ad  cmp     ebx, r13d
0x18001b8b0  cmovle  ebx, r13d
0x18001b8b4  cmp     dword ptr [rsi+0Ch], 0
0x18001b8b8  mov     edi, 1
0x18001b8bd  cmovnz  edi, ebx
0x18001b8c0  cmp     r14d, 1
0x18001b8c4  jnz     short loc_18001B8D2
0x18001b8c6  xor     edx, edx; int
0x18001b8c8  mov     rcx, rsi; this
0x18001b8cb  call    ?_TryWriteLock@CTSReaderWriterLock@@AEAAHJ@Z; CTSReaderWriterLock::_TryWriteLock(long)
0x18001b8d0  jmp     short loc_18001B907
0x18001b8d2  cmp     r14d, 2
0x18001b8d6  jnz     short loc_18001B8E2
0x18001b8d8  mov     rcx, rsi; this
0x18001b8db  call    ?_TryReadLock@CTSReaderWriterLock@@AEAAHXZ; CTSReaderWriterLock::_TryReadLock(void)
0x18001b8e0  jmp     short loc_18001B907
0x18001b8e2  mov     r8d, [rsi]
0x18001b8e5  cmp     r8w, 0FFFFh
0x18001b8eb  jz      short loc_18001B905
0x18001b8ed  lea     edx, [r8+1]
0x18001b8f1  mov     rcx, rsi
0x18001b8f4  call    PAL_System_AtomicCompareAndExchange
0x18001b8f9  cmp     r8d, eax
0x18001b8fc  jnz     short loc_18001B905
0x18001b8fe  mov     eax, 1
0x18001b903  jmp     short loc_18001B907
0x18001b905  xor     eax, eax
0x18001b907  test    eax, eax
0x18001b909  jnz     short loc_18001B93A
0x18001b90b  sub     edi, 1
0x18001b90e  jnz     short loc_18001B8C0
0x18001b910  call    cs:__imp_SwitchToThread
0x18001b916  test    eax, eax
0x18001b918  jnz     short loc_18001B922
0x18001b91a  mov     ecx, ebp; dwMilliseconds
0x18001b91c  call    cs:__imp_Sleep
0x18001b922  movd    xmm0, ebx
0x18001b926  xor     ebp, 1
0x18001b929  cvtdq2pd xmm0, xmm0
0x18001b92d  mulsd   xmm0, cs:__real@3fe0000000000000
0x18001b935  jmp     loc_18001B89A
0x18001b93a  add     rsp, 28h
0x18001b93e  pop     r14
0x18001b940  pop     r13
0x18001b942  pop     rdi
0x18001b943  pop     rsi
0x18001b944  pop     rbp
0x18001b945  pop     rbx
0x18001b946  retn
```
