# CReaderWriterLock2::_LockSpin(bool)

- ea: `0x180057794`
- end: `0x180057891`
- name: `?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z`
- size: `253`
- prototype: `void __fastcall(CReaderWriterLock2 *__hidden this, bool)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022778`
- `0x180022930`
- `0x180022e00`
- `0x180056d94`
- `0x1800570f8`

## callees

- `0x180057774`
- `0x180057794`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800577ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800577ab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005784a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005784a`

## pseudocode

```c
void __fastcall CReaderWriterLock2::_LockSpin(CReaderWriterLock2 *this, char a2)
{
  DWORD v4; // ebp
  unsigned int v5; // esi
  int v6; // ebx
  int v7; // r8d
  signed __int32 v8; // edx
  signed __int32 v9; // ecx
  char v10; // al

  v4 = 0;
  v5 = 0;
  v6 = (int)(*(double *)&qword_18006DD50[GetCurrentThreadId() % 0xD] * 4000.0);
LABEL_2:
  v7 = v6;
  if ( g_cProcessors < 2 )
    v7 = 1;
  do
  {
    if ( --v7 < 0 )
    {
      Sleep(v4);
      v4 = SleepTime(v5);
      v6 = (int)((double)v6 * 0.5);
      if ( v6 <= 10000 )
      {
        if ( v6 <= 100 )
          v6 = 100;
      }
      else
      {
        v6 = 10000;
      }
      ++v5;
      goto LABEL_2;
    }
    v8 = *(_DWORD *)this;
    if ( a2 )
    {
      if ( (_WORD)v8 )
        goto LABEL_12;
      v9 = v8 | 0xFFFF;
    }
    else
    {
      if ( (v8 & 0xFFFF8000) != 0 )
        goto LABEL_12;
      v9 = v8 + 1;
    }
    if ( v8 == _InterlockedCompareExchange((volatile signed __int32 *)this, v9, v8) )
    {
      v10 = 1;
      continue;
    }
LABEL_12:
    v10 = 0;
  }
  while ( !v10 );
}

```

## disassembly

```asm
0x180057794  push    rbx
0x180057796  push    rbp
0x180057797  push    rsi
0x180057798  push    rdi
0x180057799  push    r13
0x18005779b  push    r14
0x18005779d  push    r15
0x18005779f  sub     rsp, 20h
0x1800577a3  mov     r14b, dl
0x1800577a6  mov     rdi, rcx
0x1800577a9  xor     ebp, ebp
0x1800577ab  call    cs:__imp_GetCurrentThreadId
0x1800577b2  nop     dword ptr [rax+rax+00h]
0x1800577b7  mov     r9d, eax
0x1800577ba  lea     rcx, qword_18006DD50
0x1800577c1  mov     eax, 4EC4EC4Fh
0x1800577c6  lea     r15d, [rbp+1]
0x1800577ca  mul     r9d
0x1800577cd  lea     r13d, [rbp+64h]
0x1800577d1  shr     edx, 2
0x1800577d4  imul    r8d, edx, 0Dh
0x1800577d8  sub     r9d, r8d
0x1800577db  xor     esi, esi
0x1800577dd  movsd   xmm0, qword ptr [rcx+r9*8]
0x1800577e3  mulsd   xmm0, cs:__real@40af400000000000
0x1800577eb  cvttsd2si ebx, xmm0
0x1800577ef  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x1800577f6  mov     r8d, ebx
0x1800577f9  cmovb   r8d, r15d
0x1800577fd  sub     r8d, r15d
0x180057800  js      short loc_180057848
0x180057802  mov     edx, [rdi]
0x180057804  test    r14b, r14b
0x180057807  jz      short loc_180057818
0x180057809  test    dx, dx
0x18005780c  jnz     short loc_180057832
0x18005780e  mov     ecx, edx
0x180057810  or      ecx, 0FFFFh
0x180057816  jmp     short loc_180057823
0x180057818  test    edx, 0FFFF8000h
0x18005781e  jnz     short loc_180057832
0x180057820  lea     ecx, [rdx+1]
0x180057823  mov     eax, edx
0x180057825  lock cmpxchg [rdi], ecx
0x180057829  cmp     edx, eax
0x18005782b  jnz     short loc_180057832
0x18005782d  mov     al, r15b
0x180057830  jmp     short loc_180057834
0x180057832  xor     al, al
0x180057834  test    al, al
0x180057836  jz      short loc_1800577FD
0x180057838  add     rsp, 20h
0x18005783c  pop     r15
0x18005783e  pop     r14
0x180057840  pop     r13
0x180057842  pop     rdi
0x180057843  pop     rsi
0x180057844  pop     rbp
0x180057845  pop     rbx
0x180057846  retn
0x180057848  mov     ecx, ebp; dwMilliseconds
0x18005784a  call    cs:__imp_Sleep
0x180057851  nop     dword ptr [rax+rax+00h]
0x180057856  mov     ecx, esi; unsigned int
0x180057858  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18005785d  movd    xmm0, ebx
0x180057861  mov     ebp, eax
0x180057863  cvtdq2pd xmm0, xmm0
0x180057867  mulsd   xmm0, cs:__real@3fe0000000000000
0x18005786f  cvttsd2si ebx, xmm0
0x180057873  cmp     ebx, 2710h
0x180057879  jle     short loc_180057882
0x18005787b  mov     ebx, 2710h
0x180057880  jmp     short loc_180057889
0x180057882  cmp     ebx, r13d
0x180057885  cmovle  ebx, r13d
0x180057889  add     esi, r15d
0x18005788c  jmp     loc_1800577EF
```
