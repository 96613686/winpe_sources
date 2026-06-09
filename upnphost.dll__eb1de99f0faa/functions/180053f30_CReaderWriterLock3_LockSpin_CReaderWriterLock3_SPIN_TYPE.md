# CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)

- ea: `0x180053f30`
- end: `0x18005406d`
- name: `?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `317`
- prototype: `DWORD __fastcall(volatile signed __int32 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800221cc`
- `0x180054170`

## callees

- `0x180053e18`
- `0x180053f30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053f48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053fbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053fd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053f48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053fbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053fd4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180054028`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180054028`

## pseudocode

```c
DWORD __fastcall CReaderWriterLock3::_LockSpin(volatile signed __int32 *a1, int a2)
{
  DWORD v4; // r14d
  DWORD result; // eax
  DWORD CurrentThreadId; // kr00_4
  unsigned int v7; // ebp
  int v8; // edi
  int v9; // esi
  signed __int32 v10; // edx
  DWORD v11; // eax
  char v12; // cl
  signed __int32 v13; // edx

  v4 = 0;
  CurrentThreadId = GetCurrentThreadId();
  result = 1321528399 * CurrentThreadId;
  v7 = 0;
  v8 = (int)(*(double *)&qword_180069D50[CurrentThreadId % 0xD] * 4000.0);
LABEL_2:
  v9 = v8;
  if ( g_cProcessors < 2 )
    v9 = 1;
  do
  {
    if ( --v9 < 0 )
    {
      Sleep(v4);
      result = SleepTime(v7);
      v4 = result;
      v8 = (int)((double)v8 * 0.5);
      if ( v8 <= 10000 )
      {
        result = 100;
        if ( v8 <= 100 )
          v8 = 100;
      }
      else
      {
        v8 = 10000;
      }
      ++v7;
      goto LABEL_2;
    }
    if ( a2 == 1 )
    {
      if ( !*((_DWORD *)a1 + 1) && !(unsigned __int16)*a1 )
      {
        v10 = *a1;
        if ( v10 == _InterlockedCompareExchange(a1, v10 | 0xFFFF, v10) )
        {
          v11 = GetCurrentThreadId() & 0xFFFFFFF | 0x10000000;
LABEL_10:
          result = _InterlockedExchange(a1 + 1, v11);
LABEL_11:
          v12 = 1;
          continue;
        }
      }
      result = GetCurrentThreadId() & 0xFFFFFFF;
      if ( (a1[1] & 0xFFFFFFF) == result )
      {
        v11 = *((_DWORD *)a1 + 1) + 0x10000000;
        goto LABEL_10;
      }
    }
    else
    {
      v13 = *a1;
      if ( (unsigned __int16)*a1 != 0xFFFF )
      {
        result = _InterlockedCompareExchange(a1, v13 + 1, v13);
        if ( v13 == result )
          goto LABEL_11;
      }
    }
    v12 = 0;
  }
  while ( !v12 );
  return result;
}

```

## disassembly

```asm
0x180053f30  push    rbx
0x180053f32  push    rbp
0x180053f33  push    rsi
0x180053f34  push    rdi
0x180053f35  push    r12
0x180053f37  push    r14
0x180053f39  push    r15
0x180053f3b  sub     rsp, 20h
0x180053f3f  mov     r15d, edx
0x180053f42  mov     rbx, rcx
0x180053f45  xor     r14d, r14d
0x180053f48  call    cs:__imp_GetCurrentThreadId
0x180053f4e  mov     r9d, eax
0x180053f51  lea     rcx, qword_180069D50
0x180053f58  mov     eax, 4EC4EC4Fh
0x180053f5d  lea     r12d, [r14+1]
0x180053f61  mul     r9d
0x180053f64  shr     edx, 2
0x180053f67  imul    r8d, edx, 0Dh
0x180053f6b  sub     r9d, r8d
0x180053f6e  xor     ebp, ebp
0x180053f70  movsd   xmm0, qword ptr [rcx+r9*8]
0x180053f76  mulsd   xmm0, cs:__real@40af400000000000
0x180053f7e  cvttsd2si edi, xmm0
0x180053f82  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180053f89  mov     esi, edi
0x180053f8b  cmovb   esi, r12d
0x180053f8f  sub     esi, r12d
0x180053f92  js      loc_180054025
0x180053f98  cmp     r15d, r12d
0x180053f9b  jnz     short loc_180053FF6
0x180053f9d  mov     eax, [rbx+4]
0x180053fa0  test    eax, eax
0x180053fa2  jnz     short loc_180053FD4
0x180053fa4  mov     edx, [rbx]
0x180053fa6  test    dx, dx
0x180053fa9  jnz     short loc_180053FD4
0x180053fab  mov     ecx, edx
0x180053fad  mov     eax, edx
0x180053faf  or      ecx, 0FFFFh
0x180053fb5  lock cmpxchg [rbx], ecx
0x180053fb9  cmp     edx, eax
0x180053fbb  jnz     short loc_180053FD4
0x180053fbd  call    cs:__imp_GetCurrentThreadId
0x180053fc3  and     eax, 0FFFFFFFh
0x180053fc8  bts     eax, 1Ch
0x180053fcc  xchg    eax, [rbx+4]
0x180053fcf  mov     cl, r12b
0x180053fd2  jmp     short loc_18005400E
0x180053fd4  call    cs:__imp_GetCurrentThreadId
0x180053fda  mov     ecx, [rbx+4]
0x180053fdd  and     eax, 0FFFFFFFh
0x180053fe2  and     ecx, 0FFFFFFFh
0x180053fe8  cmp     ecx, eax
0x180053fea  jnz     short loc_18005400C
0x180053fec  mov     eax, [rbx+4]
0x180053fef  add     eax, 10000000h
0x180053ff4  jmp     short loc_180053FCC
0x180053ff6  mov     edx, [rbx]
0x180053ff8  cmp     dx, 0FFFFh
0x180053ffd  jz      short loc_18005400C
0x180053fff  lea     ecx, [rdx+1]
0x180054002  mov     eax, edx
0x180054004  lock cmpxchg [rbx], ecx
0x180054008  cmp     edx, eax
0x18005400a  jz      short loc_180053FCF
0x18005400c  xor     cl, cl
0x18005400e  test    cl, cl
0x180054010  jz      loc_180053F8F
0x180054016  add     rsp, 20h
0x18005401a  pop     r15
0x18005401c  pop     r14
0x18005401e  pop     r12
0x180054020  pop     rdi
0x180054021  pop     rsi
0x180054022  pop     rbp
0x180054023  pop     rbx
0x180054024  retn
0x180054025  mov     ecx, r14d; dwMilliseconds
0x180054028  call    cs:__imp_Sleep
0x18005402e  mov     ecx, ebp; unsigned int
0x180054030  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180054035  movd    xmm0, edi
0x180054039  mov     r14d, eax
0x18005403c  cvtdq2pd xmm0, xmm0
0x180054040  mulsd   xmm0, cs:__real@3fe0000000000000
0x180054048  cvttsd2si edi, xmm0
0x18005404c  cmp     edi, 2710h
0x180054052  jle     short loc_18005405B
0x180054054  mov     edi, 2710h
0x180054059  jmp     short loc_180054065
0x18005405b  mov     eax, 64h ; 'd'
0x180054060  cmp     edi, eax
0x180054062  cmovle  edi, eax
0x180054065  add     ebp, r12d
0x180054068  jmp     loc_180053F82
```
