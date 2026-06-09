# CReaderWriterLock2::_LockSpin(bool)

- ea: `0x180034e1c`
- end: `0x180034f0c`
- name: `?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z`
- size: `240`
- prototype: `void __fastcall(CReaderWriterLock2 *this, char)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c440`
- `0x18001e724`
- `0x180023ae8`
- `0x1800341e0`
- `0x180034544`

## callees

- `0x180034dfc`
- `0x180034e1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034e33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034e33`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180034ecb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180034ecb`

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
  v6 = (int)(*(double *)&qword_18003B350[GetCurrentThreadId() % 0xD] * 4000.0);
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
0x180034e1c  push    rbx
0x180034e1e  push    rbp
0x180034e1f  push    rsi
0x180034e20  push    rdi
0x180034e21  push    r13
0x180034e23  push    r14
0x180034e25  push    r15
0x180034e27  sub     rsp, 20h
0x180034e2b  mov     r14b, dl
0x180034e2e  mov     rdi, rcx
0x180034e31  xor     ebp, ebp
0x180034e33  call    cs:__imp_GetCurrentThreadId
0x180034e39  mov     r9d, eax
0x180034e3c  lea     rcx, qword_18003B350
0x180034e43  mov     eax, 4EC4EC4Fh
0x180034e48  lea     r15d, [rbp+1]
0x180034e4c  mul     r9d
0x180034e4f  lea     r13d, [rbp+64h]
0x180034e53  shr     edx, 2
0x180034e56  imul    r8d, edx, 0Dh
0x180034e5a  sub     r9d, r8d
0x180034e5d  xor     esi, esi
0x180034e5f  movsd   xmm0, qword ptr [rcx+r9*8]
0x180034e65  mulsd   xmm0, cs:__real@40af400000000000
0x180034e6d  cvttsd2si ebx, xmm0
0x180034e71  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180034e78  mov     r8d, ebx
0x180034e7b  cmovb   r8d, r15d
0x180034e7f  sub     r8d, r15d
0x180034e82  js      short loc_180034EC9
0x180034e84  mov     edx, [rdi]
0x180034e86  test    r14b, r14b
0x180034e89  jz      short loc_180034E9A
0x180034e8b  test    dx, dx
0x180034e8e  jnz     short loc_180034EB4
0x180034e90  mov     ecx, edx
0x180034e92  or      ecx, 0FFFFh
0x180034e98  jmp     short loc_180034EA5
0x180034e9a  test    edx, 0FFFF8000h
0x180034ea0  jnz     short loc_180034EB4
0x180034ea2  lea     ecx, [rdx+1]
0x180034ea5  mov     eax, edx
0x180034ea7  lock cmpxchg [rdi], ecx
0x180034eab  cmp     edx, eax
0x180034ead  jnz     short loc_180034EB4
0x180034eaf  mov     al, r15b
0x180034eb2  jmp     short loc_180034EB6
0x180034eb4  xor     al, al
0x180034eb6  test    al, al
0x180034eb8  jz      short loc_180034E7F
0x180034eba  add     rsp, 20h
0x180034ebe  pop     r15
0x180034ec0  pop     r14
0x180034ec2  pop     r13
0x180034ec4  pop     rdi
0x180034ec5  pop     rsi
0x180034ec6  pop     rbp
0x180034ec7  pop     rbx
0x180034ec8  retn
0x180034ec9  mov     ecx, ebp; dwMilliseconds
0x180034ecb  call    cs:__imp_Sleep
0x180034ed1  mov     ecx, esi; unsigned int
0x180034ed3  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180034ed8  movd    xmm0, ebx
0x180034edc  mov     ebp, eax
0x180034ede  cvtdq2pd xmm0, xmm0
0x180034ee2  mulsd   xmm0, cs:__real@3fe0000000000000
0x180034eea  cvttsd2si ebx, xmm0
0x180034eee  cmp     ebx, 2710h
0x180034ef4  jle     short loc_180034EFD
0x180034ef6  mov     ebx, 2710h
0x180034efb  jmp     short loc_180034F04
0x180034efd  cmp     ebx, r13d
0x180034f00  cmovle  ebx, r13d
0x180034f04  add     esi, r15d
0x180034f07  jmp     loc_180034E71
```
