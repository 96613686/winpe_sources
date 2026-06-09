# CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)

- ea: `0x180057898`
- end: `0x1800579ee`
- name: `?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022e00`
- `0x180057b08`

## callees

- `0x180057774`
- `0x180057898`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800578b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005792b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057948`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800578b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005792b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057948`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800579a3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800579a3`

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
  v8 = (int)(*(double *)&qword_18006DD50[CurrentThreadId % 0xD] * 4000.0);
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
0x180057898  push    rbx
0x18005789a  push    rbp
0x18005789b  push    rsi
0x18005789c  push    rdi
0x18005789d  push    r12
0x18005789f  push    r14
0x1800578a1  push    r15
0x1800578a3  sub     rsp, 20h
0x1800578a7  mov     r15d, edx
0x1800578aa  mov     rbx, rcx
0x1800578ad  xor     r14d, r14d
0x1800578b0  call    cs:__imp_GetCurrentThreadId
0x1800578b7  nop     dword ptr [rax+rax+00h]
0x1800578bc  mov     r9d, eax
0x1800578bf  lea     rcx, qword_18006DD50
0x1800578c6  mov     eax, 4EC4EC4Fh
0x1800578cb  lea     r12d, [r14+1]
0x1800578cf  mul     r9d
0x1800578d2  shr     edx, 2
0x1800578d5  imul    r8d, edx, 0Dh
0x1800578d9  sub     r9d, r8d
0x1800578dc  xor     ebp, ebp
0x1800578de  movsd   xmm0, qword ptr [rcx+r9*8]
0x1800578e4  mulsd   xmm0, cs:__real@40af400000000000
0x1800578ec  cvttsd2si edi, xmm0
0x1800578f0  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x1800578f7  mov     esi, edi
0x1800578f9  cmovb   esi, r12d
0x1800578fd  sub     esi, r12d
0x180057900  js      loc_1800579A0
0x180057906  cmp     r15d, r12d
0x180057909  jnz     short loc_180057970
0x18005790b  mov     eax, [rbx+4]
0x18005790e  test    eax, eax
0x180057910  jnz     short loc_180057948
0x180057912  mov     edx, [rbx]
0x180057914  test    dx, dx
0x180057917  jnz     short loc_180057948
0x180057919  mov     ecx, edx
0x18005791b  mov     eax, edx
0x18005791d  or      ecx, 0FFFFh
0x180057923  lock cmpxchg [rbx], ecx
0x180057927  cmp     edx, eax
0x180057929  jnz     short loc_180057948
0x18005792b  call    cs:__imp_GetCurrentThreadId
0x180057932  nop     dword ptr [rax+rax+00h]
0x180057937  and     eax, 0FFFFFFFh
0x18005793c  bts     eax, 1Ch
0x180057940  xchg    eax, [rbx+4]
0x180057943  mov     cl, r12b
0x180057946  jmp     short loc_180057988
0x180057948  call    cs:__imp_GetCurrentThreadId
0x18005794f  nop     dword ptr [rax+rax+00h]
0x180057954  mov     ecx, [rbx+4]
0x180057957  and     eax, 0FFFFFFFh
0x18005795c  and     ecx, 0FFFFFFFh
0x180057962  cmp     ecx, eax
0x180057964  jnz     short loc_180057986
0x180057966  mov     eax, [rbx+4]
0x180057969  add     eax, 10000000h
0x18005796e  jmp     short loc_180057940
0x180057970  mov     edx, [rbx]
0x180057972  cmp     dx, 0FFFFh
0x180057977  jz      short loc_180057986
0x180057979  lea     ecx, [rdx+1]
0x18005797c  mov     eax, edx
0x18005797e  lock cmpxchg [rbx], ecx
0x180057982  cmp     edx, eax
0x180057984  jz      short loc_180057943
0x180057986  xor     cl, cl
0x180057988  test    cl, cl
0x18005798a  jz      loc_1800578FD
0x180057990  add     rsp, 20h
0x180057994  pop     r15
0x180057996  pop     r14
0x180057998  pop     r12
0x18005799a  pop     rdi
0x18005799b  pop     rsi
0x18005799c  pop     rbp
0x18005799d  pop     rbx
0x18005799e  retn
0x1800579a0  mov     ecx, r14d; dwMilliseconds
0x1800579a3  call    cs:__imp_Sleep
0x1800579aa  nop     dword ptr [rax+rax+00h]
0x1800579af  mov     ecx, ebp; unsigned int
0x1800579b1  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x1800579b6  movd    xmm0, edi
0x1800579ba  mov     r14d, eax
0x1800579bd  cvtdq2pd xmm0, xmm0
0x1800579c1  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800579c9  cvttsd2si edi, xmm0
0x1800579cd  cmp     edi, 2710h
0x1800579d3  jle     short loc_1800579DC
0x1800579d5  mov     edi, 2710h
0x1800579da  jmp     short loc_1800579E6
0x1800579dc  mov     eax, 64h ; 'd'
0x1800579e1  cmp     edi, eax
0x1800579e3  cmovle  edi, eax
0x1800579e6  add     ebp, r12d
0x1800579e9  jmp     loc_1800578F0
```
