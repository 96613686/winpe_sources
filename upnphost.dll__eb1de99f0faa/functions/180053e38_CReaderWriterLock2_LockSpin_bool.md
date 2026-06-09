# CReaderWriterLock2::_LockSpin(bool)

- ea: `0x180053e38`
- end: `0x180053f28`
- name: `?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z`
- size: `240`
- prototype: `void __fastcall(CReaderWriterLock2 *this, char)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021b80`
- `0x180021d38`
- `0x1800221cc`
- `0x180053444`
- `0x1800537a8`

## callees

- `0x180053e18`
- `0x180053e38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053e4f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180053ee7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180053ee7`

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
  v6 = (int)(*(double *)&qword_180069D50[GetCurrentThreadId() % 0xD] * 4000.0);
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
0x180053e38  push    rbx
0x180053e3a  push    rbp
0x180053e3b  push    rsi
0x180053e3c  push    rdi
0x180053e3d  push    r13
0x180053e3f  push    r14
0x180053e41  push    r15
0x180053e43  sub     rsp, 20h
0x180053e47  mov     r14b, dl
0x180053e4a  mov     rdi, rcx
0x180053e4d  xor     ebp, ebp
0x180053e4f  call    cs:__imp_GetCurrentThreadId
0x180053e55  mov     r9d, eax
0x180053e58  lea     rcx, qword_180069D50
0x180053e5f  mov     eax, 4EC4EC4Fh
0x180053e64  lea     r15d, [rbp+1]
0x180053e68  mul     r9d
0x180053e6b  lea     r13d, [rbp+64h]
0x180053e6f  shr     edx, 2
0x180053e72  imul    r8d, edx, 0Dh
0x180053e76  sub     r9d, r8d
0x180053e79  xor     esi, esi
0x180053e7b  movsd   xmm0, qword ptr [rcx+r9*8]
0x180053e81  mulsd   xmm0, cs:__real@40af400000000000
0x180053e89  cvttsd2si ebx, xmm0
0x180053e8d  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180053e94  mov     r8d, ebx
0x180053e97  cmovb   r8d, r15d
0x180053e9b  sub     r8d, r15d
0x180053e9e  js      short loc_180053EE5
0x180053ea0  mov     edx, [rdi]
0x180053ea2  test    r14b, r14b
0x180053ea5  jz      short loc_180053EB6
0x180053ea7  test    dx, dx
0x180053eaa  jnz     short loc_180053ED0
0x180053eac  mov     ecx, edx
0x180053eae  or      ecx, 0FFFFh
0x180053eb4  jmp     short loc_180053EC1
0x180053eb6  test    edx, 0FFFF8000h
0x180053ebc  jnz     short loc_180053ED0
0x180053ebe  lea     ecx, [rdx+1]
0x180053ec1  mov     eax, edx
0x180053ec3  lock cmpxchg [rdi], ecx
0x180053ec7  cmp     edx, eax
0x180053ec9  jnz     short loc_180053ED0
0x180053ecb  mov     al, r15b
0x180053ece  jmp     short loc_180053ED2
0x180053ed0  xor     al, al
0x180053ed2  test    al, al
0x180053ed4  jz      short loc_180053E9B
0x180053ed6  add     rsp, 20h
0x180053eda  pop     r15
0x180053edc  pop     r14
0x180053ede  pop     r13
0x180053ee0  pop     rdi
0x180053ee1  pop     rsi
0x180053ee2  pop     rbp
0x180053ee3  pop     rbx
0x180053ee4  retn
0x180053ee5  mov     ecx, ebp; dwMilliseconds
0x180053ee7  call    cs:__imp_Sleep
0x180053eed  mov     ecx, esi; unsigned int
0x180053eef  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180053ef4  movd    xmm0, ebx
0x180053ef8  mov     ebp, eax
0x180053efa  cvtdq2pd xmm0, xmm0
0x180053efe  mulsd   xmm0, cs:__real@3fe0000000000000
0x180053f06  cvttsd2si ebx, xmm0
0x180053f0a  cmp     ebx, 2710h
0x180053f10  jle     short loc_180053F19
0x180053f12  mov     ebx, 2710h
0x180053f17  jmp     short loc_180053F20
0x180053f19  cmp     ebx, r13d
0x180053f1c  cmovle  ebx, r13d
0x180053f20  add     esi, r15d
0x180053f23  jmp     loc_180053E8D
```
