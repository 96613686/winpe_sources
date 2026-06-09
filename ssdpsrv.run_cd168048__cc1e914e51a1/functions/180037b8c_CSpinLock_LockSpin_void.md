# CSpinLock::_LockSpin(void)

- ea: `0x180037b8c`
- end: `0x180037c98`
- name: `?_LockSpin@CSpinLock@@AEAAXXZ`
- size: `268`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800253a8`
- `0x180036918`

## callees

- `0x18003790c`
- `0x180037b8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037ba3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037c5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037ba3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037c5d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180037bf7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180037c42`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180037bf7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180037c42`

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
  v4 = (int)(*(double *)&qword_18003E360[GetCurrentThreadId() % 0xD] * 4000.0);
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
0x180037b8c  mov     [rsp+arg_0], rbx
0x180037b91  mov     [rsp+arg_10], rbp
0x180037b96  push    rsi
0x180037b97  push    rdi
0x180037b98  push    r15
0x180037b9a  sub     rsp, 20h
0x180037b9e  mov     rdi, rcx
0x180037ba1  xor     ebp, ebp
0x180037ba3  call    cs:__imp_GetCurrentThreadId
0x180037baa  nop     dword ptr [rax+rax+00h]
0x180037baf  mov     r9d, eax
0x180037bb2  lea     rcx, qword_18003E360
0x180037bb9  mov     eax, 4EC4EC4Fh
0x180037bbe  lea     r15d, [rbp+64h]
0x180037bc2  mul     r9d
0x180037bc5  shr     edx, 2
0x180037bc8  imul    r8d, edx, 0Dh
0x180037bcc  sub     r9d, r8d
0x180037bcf  xor     esi, esi
0x180037bd1  movsd   xmm0, qword ptr [rcx+r9*8]
0x180037bd7  mulsd   xmm0, cs:__real@40af400000000000
0x180037bdf  cvttsd2si ebx, xmm0
0x180037be3  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x180037bea  jbe     short loc_180037C40
0x180037bec  mov     edx, ebx
0x180037bee  jmp     short loc_180037C38
0x180037bf0  sub     edx, 1
0x180037bf3  jns     short loc_180037C38
0x180037bf5  mov     ecx, ebp; dwMilliseconds
0x180037bf7  call    cs:__imp_Sleep
0x180037bfe  nop     dword ptr [rax+rax+00h]
0x180037c03  movd    xmm0, ebx
0x180037c07  cvtdq2pd xmm0, xmm0
0x180037c0b  mulsd   xmm0, cs:__real@3fe0000000000000
0x180037c13  cvttsd2si ebx, xmm0
0x180037c17  cmp     ebx, 2710h
0x180037c1d  jle     short loc_180037C26
0x180037c1f  mov     ebx, 2710h
0x180037c24  jmp     short loc_180037C2D
0x180037c26  cmp     ebx, r15d
0x180037c29  cmovle  ebx, r15d
0x180037c2d  mov     ecx, esi; unsigned int
0x180037c2f  mov     edx, ebx
0x180037c31  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180037c36  mov     ebp, eax
0x180037c38  mov     eax, [rdi]
0x180037c3a  test    eax, eax
0x180037c3c  jnz     short loc_180037BF0
0x180037c3e  jmp     short loc_180037C57
0x180037c40  mov     ecx, ebp; dwMilliseconds
0x180037c42  call    cs:__imp_Sleep
0x180037c49  nop     dword ptr [rax+rax+00h]
0x180037c4e  mov     ecx, esi; unsigned int
0x180037c50  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180037c55  mov     ebp, eax
0x180037c57  mov     eax, [rdi]
0x180037c59  test    eax, eax
0x180037c5b  jnz     short loc_180037C7D
0x180037c5d  call    cs:__imp_GetCurrentThreadId
0x180037c64  nop     dword ptr [rax+rax+00h]
0x180037c69  mov     ecx, eax
0x180037c6b  and     ecx, 0FFFFFFFh
0x180037c71  bts     ecx, 1Ch
0x180037c75  xor     eax, eax
0x180037c77  lock cmpxchg [rdi], ecx
0x180037c7b  jz      short loc_180037C84
0x180037c7d  inc     esi
0x180037c7f  jmp     loc_180037BE3
0x180037c84  mov     rbx, [rsp+38h+arg_0]
0x180037c89  mov     rbp, [rsp+38h+arg_10]
0x180037c8e  add     rsp, 20h
0x180037c92  pop     r15
0x180037c94  pop     rdi
0x180037c95  pop     rsi
0x180037c96  retn
```
