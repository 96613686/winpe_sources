# CReaderWriterLock2::_LockSpin(bool)

- ea: `0x18003792c`
- end: `0x180037a29`
- name: `?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z`
- size: `253`
- prototype: `void __fastcall(CReaderWriterLock2 *__hidden this, bool)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d89c`
- `0x18001fc70`
- `0x18002552c`
- `0x180036ce0`
- `0x180037044`

## callees

- `0x18003790c`
- `0x18003792c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037943`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037943`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800379e2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800379e2`

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
  v6 = (int)(*(double *)&qword_18003E360[GetCurrentThreadId() % 0xD] * 4000.0);
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
0x18003792c  push    rbx
0x18003792e  push    rbp
0x18003792f  push    rsi
0x180037930  push    rdi
0x180037931  push    r13
0x180037933  push    r14
0x180037935  push    r15
0x180037937  sub     rsp, 20h
0x18003793b  mov     r14b, dl
0x18003793e  mov     rdi, rcx
0x180037941  xor     ebp, ebp
0x180037943  call    cs:__imp_GetCurrentThreadId
0x18003794a  nop     dword ptr [rax+rax+00h]
0x18003794f  mov     r9d, eax
0x180037952  lea     rcx, qword_18003E360
0x180037959  mov     eax, 4EC4EC4Fh
0x18003795e  lea     r15d, [rbp+1]
0x180037962  mul     r9d
0x180037965  lea     r13d, [rbp+64h]
0x180037969  shr     edx, 2
0x18003796c  imul    r8d, edx, 0Dh
0x180037970  sub     r9d, r8d
0x180037973  xor     esi, esi
0x180037975  movsd   xmm0, qword ptr [rcx+r9*8]
0x18003797b  mulsd   xmm0, cs:__real@40af400000000000
0x180037983  cvttsd2si ebx, xmm0
0x180037987  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x18003798e  mov     r8d, ebx
0x180037991  cmovb   r8d, r15d
0x180037995  sub     r8d, r15d
0x180037998  js      short loc_1800379E0
0x18003799a  mov     edx, [rdi]
0x18003799c  test    r14b, r14b
0x18003799f  jz      short loc_1800379B0
0x1800379a1  test    dx, dx
0x1800379a4  jnz     short loc_1800379CA
0x1800379a6  mov     ecx, edx
0x1800379a8  or      ecx, 0FFFFh
0x1800379ae  jmp     short loc_1800379BB
0x1800379b0  test    edx, 0FFFF8000h
0x1800379b6  jnz     short loc_1800379CA
0x1800379b8  lea     ecx, [rdx+1]
0x1800379bb  mov     eax, edx
0x1800379bd  lock cmpxchg [rdi], ecx
0x1800379c1  cmp     edx, eax
0x1800379c3  jnz     short loc_1800379CA
0x1800379c5  mov     al, r15b
0x1800379c8  jmp     short loc_1800379CC
0x1800379ca  xor     al, al
0x1800379cc  test    al, al
0x1800379ce  jz      short loc_180037995
0x1800379d0  add     rsp, 20h
0x1800379d4  pop     r15
0x1800379d6  pop     r14
0x1800379d8  pop     r13
0x1800379da  pop     rdi
0x1800379db  pop     rsi
0x1800379dc  pop     rbp
0x1800379dd  pop     rbx
0x1800379de  retn
0x1800379e0  mov     ecx, ebp; dwMilliseconds
0x1800379e2  call    cs:__imp_Sleep
0x1800379e9  nop     dword ptr [rax+rax+00h]
0x1800379ee  mov     ecx, esi; unsigned int
0x1800379f0  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x1800379f5  movd    xmm0, ebx
0x1800379f9  mov     ebp, eax
0x1800379fb  cvtdq2pd xmm0, xmm0
0x1800379ff  mulsd   xmm0, cs:__real@3fe0000000000000
0x180037a07  cvttsd2si ebx, xmm0
0x180037a0b  cmp     ebx, 2710h
0x180037a11  jle     short loc_180037A1A
0x180037a13  mov     ebx, 2710h
0x180037a18  jmp     short loc_180037A21
0x180037a1a  cmp     ebx, r13d
0x180037a1d  cmovle  ebx, r13d
0x180037a21  add     esi, r15d
0x180037a24  jmp     loc_180037987
```
