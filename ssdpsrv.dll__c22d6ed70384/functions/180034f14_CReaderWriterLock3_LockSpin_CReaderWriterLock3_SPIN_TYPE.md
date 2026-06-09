# CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)

- ea: `0x180034f14`
- end: `0x180035051`
- name: `?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `317`
- prototype: `DWORD __fastcall(volatile signed __int32 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c440`
- `0x180035154`

## callees

- `0x180034dfc`
- `0x180034f14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034f2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034fa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034fb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034f2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034fa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034fb8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003500c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003500c`

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
  v8 = (int)(*(double *)&qword_18003B350[CurrentThreadId % 0xD] * 4000.0);
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
0x180034f14  push    rbx
0x180034f16  push    rbp
0x180034f17  push    rsi
0x180034f18  push    rdi
0x180034f19  push    r12
0x180034f1b  push    r14
0x180034f1d  push    r15
0x180034f1f  sub     rsp, 20h
0x180034f23  mov     r15d, edx
0x180034f26  mov     rbx, rcx
0x180034f29  xor     r14d, r14d
0x180034f2c  call    cs:__imp_GetCurrentThreadId
0x180034f32  mov     r9d, eax
0x180034f35  lea     rcx, qword_18003B350
0x180034f3c  mov     eax, 4EC4EC4Fh
0x180034f41  lea     r12d, [r14+1]
0x180034f45  mul     r9d
0x180034f48  shr     edx, 2
0x180034f4b  imul    r8d, edx, 0Dh
0x180034f4f  sub     r9d, r8d
0x180034f52  xor     ebp, ebp
0x180034f54  movsd   xmm0, qword ptr [rcx+r9*8]
0x180034f5a  mulsd   xmm0, cs:__real@40af400000000000
0x180034f62  cvttsd2si edi, xmm0
0x180034f66  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180034f6d  mov     esi, edi
0x180034f6f  cmovb   esi, r12d
0x180034f73  sub     esi, r12d
0x180034f76  js      loc_180035009
0x180034f7c  cmp     r15d, r12d
0x180034f7f  jnz     short loc_180034FDA
0x180034f81  mov     eax, [rbx+4]
0x180034f84  test    eax, eax
0x180034f86  jnz     short loc_180034FB8
0x180034f88  mov     edx, [rbx]
0x180034f8a  test    dx, dx
0x180034f8d  jnz     short loc_180034FB8
0x180034f8f  mov     ecx, edx
0x180034f91  mov     eax, edx
0x180034f93  or      ecx, 0FFFFh
0x180034f99  lock cmpxchg [rbx], ecx
0x180034f9d  cmp     edx, eax
0x180034f9f  jnz     short loc_180034FB8
0x180034fa1  call    cs:__imp_GetCurrentThreadId
0x180034fa7  and     eax, 0FFFFFFFh
0x180034fac  bts     eax, 1Ch
0x180034fb0  xchg    eax, [rbx+4]
0x180034fb3  mov     cl, r12b
0x180034fb6  jmp     short loc_180034FF2
0x180034fb8  call    cs:__imp_GetCurrentThreadId
0x180034fbe  mov     ecx, [rbx+4]
0x180034fc1  and     eax, 0FFFFFFFh
0x180034fc6  and     ecx, 0FFFFFFFh
0x180034fcc  cmp     ecx, eax
0x180034fce  jnz     short loc_180034FF0
0x180034fd0  mov     eax, [rbx+4]
0x180034fd3  add     eax, 10000000h
0x180034fd8  jmp     short loc_180034FB0
0x180034fda  mov     edx, [rbx]
0x180034fdc  cmp     dx, 0FFFFh
0x180034fe1  jz      short loc_180034FF0
0x180034fe3  lea     ecx, [rdx+1]
0x180034fe6  mov     eax, edx
0x180034fe8  lock cmpxchg [rbx], ecx
0x180034fec  cmp     edx, eax
0x180034fee  jz      short loc_180034FB3
0x180034ff0  xor     cl, cl
0x180034ff2  test    cl, cl
0x180034ff4  jz      loc_180034F73
0x180034ffa  add     rsp, 20h
0x180034ffe  pop     r15
0x180035000  pop     r14
0x180035002  pop     r12
0x180035004  pop     rdi
0x180035005  pop     rsi
0x180035006  pop     rbp
0x180035007  pop     rbx
0x180035008  retn
0x180035009  mov     ecx, r14d; dwMilliseconds
0x18003500c  call    cs:__imp_Sleep
0x180035012  mov     ecx, ebp; unsigned int
0x180035014  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180035019  movd    xmm0, edi
0x18003501d  mov     r14d, eax
0x180035020  cvtdq2pd xmm0, xmm0
0x180035024  mulsd   xmm0, cs:__real@3fe0000000000000
0x18003502c  cvttsd2si edi, xmm0
0x180035030  cmp     edi, 2710h
0x180035036  jle     short loc_18003503F
0x180035038  mov     edi, 2710h
0x18003503d  jmp     short loc_180035049
0x18003503f  mov     eax, 64h ; 'd'
0x180035044  cmp     edi, eax
0x180035046  cmovle  edi, eax
0x180035049  add     ebp, r12d
0x18003504c  jmp     loc_180034F66
```
