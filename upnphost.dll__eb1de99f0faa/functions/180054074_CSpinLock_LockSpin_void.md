# CSpinLock::_LockSpin(void)

- ea: `0x180054074`
- end: `0x180054167`
- name: `?_LockSpin@CSpinLock@@AEAAXXZ`
- size: `243`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180038394`
- `0x180038430`

## callees

- `0x180053e18`
- `0x180054074`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005408b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054133`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005408b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054133`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800540d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005411e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800540d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005411e`

## pseudocode

```c
void __fastcall CSpinLock::_LockSpin(CSpinLock *this)
{
  DWORD v2; // ebp
  unsigned int v3; // esi
  int v4; // ebx
  int v5; // edx

  v2 = 0;
  v3 = 0;
  v4 = (int)(*(double *)&qword_180069D50[GetCurrentThreadId() % 0xD] * 4000.0);
  while ( 1 )
  {
    if ( g_cProcessors <= 1 )
    {
      Sleep(v2);
      v2 = SleepTime(v3);
    }
    else
    {
      v5 = v4;
      while ( *(_DWORD *)this )
      {
        if ( --v5 < 0 )
        {
          Sleep(v2);
          v4 = (int)((double)v4 * 0.5);
          if ( v4 <= 10000 )
          {
            if ( v4 <= 100 )
              v4 = 100;
          }
          else
          {
            v4 = 10000;
          }
          v2 = SleepTime(v3);
        }
      }
    }
    if ( !*(_DWORD *)this
      && !_InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFF | 0x10000000, 0) )
    {
      break;
    }
    ++v3;
  }
}

```

## disassembly

```asm
0x180054074  mov     [rsp+arg_0], rbx
0x180054079  mov     [rsp+arg_10], rbp
0x18005407e  push    rsi
0x18005407f  push    rdi
0x180054080  push    r15
0x180054082  sub     rsp, 20h
0x180054086  mov     rdi, rcx
0x180054089  xor     ebp, ebp
0x18005408b  call    cs:__imp_GetCurrentThreadId
0x180054091  mov     r9d, eax
0x180054094  lea     rcx, qword_180069D50
0x18005409b  mov     eax, 4EC4EC4Fh
0x1800540a0  lea     r15d, [rbp+64h]
0x1800540a4  mul     r9d
0x1800540a7  shr     edx, 2
0x1800540aa  imul    r8d, edx, 0Dh
0x1800540ae  sub     r9d, r8d
0x1800540b1  xor     esi, esi
0x1800540b3  movsd   xmm0, qword ptr [rcx+r9*8]
0x1800540b9  mulsd   xmm0, cs:__real@40af400000000000
0x1800540c1  cvttsd2si ebx, xmm0
0x1800540c5  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x1800540cc  jbe     short loc_18005411C
0x1800540ce  mov     edx, ebx
0x1800540d0  jmp     short loc_180054114
0x1800540d2  sub     edx, 1
0x1800540d5  jns     short loc_180054114
0x1800540d7  mov     ecx, ebp; dwMilliseconds
0x1800540d9  call    cs:__imp_Sleep
0x1800540df  movd    xmm0, ebx
0x1800540e3  cvtdq2pd xmm0, xmm0
0x1800540e7  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800540ef  cvttsd2si ebx, xmm0
0x1800540f3  cmp     ebx, 2710h
0x1800540f9  jle     short loc_180054102
0x1800540fb  mov     ebx, 2710h
0x180054100  jmp     short loc_180054109
0x180054102  cmp     ebx, r15d
0x180054105  cmovle  ebx, r15d
0x180054109  mov     ecx, esi; unsigned int
0x18005410b  mov     edx, ebx
0x18005410d  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180054112  mov     ebp, eax
0x180054114  mov     eax, [rdi]
0x180054116  test    eax, eax
0x180054118  jnz     short loc_1800540D2
0x18005411a  jmp     short loc_18005412D
0x18005411c  mov     ecx, ebp; dwMilliseconds
0x18005411e  call    cs:__imp_Sleep
0x180054124  mov     ecx, esi; unsigned int
0x180054126  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18005412b  mov     ebp, eax
0x18005412d  mov     eax, [rdi]
0x18005412f  test    eax, eax
0x180054131  jnz     short loc_18005414D
0x180054133  call    cs:__imp_GetCurrentThreadId
0x180054139  mov     ecx, eax
0x18005413b  and     ecx, 0FFFFFFFh
0x180054141  bts     ecx, 1Ch
0x180054145  xor     eax, eax
0x180054147  lock cmpxchg [rdi], ecx
0x18005414b  jz      short loc_180054154
0x18005414d  inc     esi
0x18005414f  jmp     loc_1800540C5
0x180054154  mov     rbx, [rsp+38h+arg_0]
0x180054159  mov     rbp, [rsp+38h+arg_10]
0x18005415e  add     rsp, 20h
0x180054162  pop     r15
0x180054164  pop     rdi
0x180054165  pop     rsi
0x180054166  retn
```
