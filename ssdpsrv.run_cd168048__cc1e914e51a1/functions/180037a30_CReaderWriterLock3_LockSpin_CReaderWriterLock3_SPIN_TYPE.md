# CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)

- ea: `0x180037a30`
- end: `0x180037b86`
- name: `?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d89c`
- `0x180037ca0`

## callees

- `0x18003790c`
- `0x180037a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037a48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037ac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037ae0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037a48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037ac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037ae0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180037b3b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180037b3b`

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
  v8 = (int)(*(double *)&qword_18003E360[CurrentThreadId % 0xD] * 4000.0);
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
0x180037a30  push    rbx
0x180037a32  push    rbp
0x180037a33  push    rsi
0x180037a34  push    rdi
0x180037a35  push    r12
0x180037a37  push    r14
0x180037a39  push    r15
0x180037a3b  sub     rsp, 20h
0x180037a3f  mov     r15d, edx
0x180037a42  mov     rbx, rcx
0x180037a45  xor     r14d, r14d
0x180037a48  call    cs:__imp_GetCurrentThreadId
0x180037a4f  nop     dword ptr [rax+rax+00h]
0x180037a54  mov     r9d, eax
0x180037a57  lea     rcx, qword_18003E360
0x180037a5e  mov     eax, 4EC4EC4Fh
0x180037a63  lea     r12d, [r14+1]
0x180037a67  mul     r9d
0x180037a6a  shr     edx, 2
0x180037a6d  imul    r8d, edx, 0Dh
0x180037a71  sub     r9d, r8d
0x180037a74  xor     ebp, ebp
0x180037a76  movsd   xmm0, qword ptr [rcx+r9*8]
0x180037a7c  mulsd   xmm0, cs:__real@40af400000000000
0x180037a84  cvttsd2si edi, xmm0
0x180037a88  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180037a8f  mov     esi, edi
0x180037a91  cmovb   esi, r12d
0x180037a95  sub     esi, r12d
0x180037a98  js      loc_180037B38
0x180037a9e  cmp     r15d, r12d
0x180037aa1  jnz     short loc_180037B08
0x180037aa3  mov     eax, [rbx+4]
0x180037aa6  test    eax, eax
0x180037aa8  jnz     short loc_180037AE0
0x180037aaa  mov     edx, [rbx]
0x180037aac  test    dx, dx
0x180037aaf  jnz     short loc_180037AE0
0x180037ab1  mov     ecx, edx
0x180037ab3  mov     eax, edx
0x180037ab5  or      ecx, 0FFFFh
0x180037abb  lock cmpxchg [rbx], ecx
0x180037abf  cmp     edx, eax
0x180037ac1  jnz     short loc_180037AE0
0x180037ac3  call    cs:__imp_GetCurrentThreadId
0x180037aca  nop     dword ptr [rax+rax+00h]
0x180037acf  and     eax, 0FFFFFFFh
0x180037ad4  bts     eax, 1Ch
0x180037ad8  xchg    eax, [rbx+4]
0x180037adb  mov     cl, r12b
0x180037ade  jmp     short loc_180037B20
0x180037ae0  call    cs:__imp_GetCurrentThreadId
0x180037ae7  nop     dword ptr [rax+rax+00h]
0x180037aec  mov     ecx, [rbx+4]
0x180037aef  and     eax, 0FFFFFFFh
0x180037af4  and     ecx, 0FFFFFFFh
0x180037afa  cmp     ecx, eax
0x180037afc  jnz     short loc_180037B1E
0x180037afe  mov     eax, [rbx+4]
0x180037b01  add     eax, 10000000h
0x180037b06  jmp     short loc_180037AD8
0x180037b08  mov     edx, [rbx]
0x180037b0a  cmp     dx, 0FFFFh
0x180037b0f  jz      short loc_180037B1E
0x180037b11  lea     ecx, [rdx+1]
0x180037b14  mov     eax, edx
0x180037b16  lock cmpxchg [rbx], ecx
0x180037b1a  cmp     edx, eax
0x180037b1c  jz      short loc_180037ADB
0x180037b1e  xor     cl, cl
0x180037b20  test    cl, cl
0x180037b22  jz      loc_180037A95
0x180037b28  add     rsp, 20h
0x180037b2c  pop     r15
0x180037b2e  pop     r14
0x180037b30  pop     r12
0x180037b32  pop     rdi
0x180037b33  pop     rsi
0x180037b34  pop     rbp
0x180037b35  pop     rbx
0x180037b36  retn
0x180037b38  mov     ecx, r14d; dwMilliseconds
0x180037b3b  call    cs:__imp_Sleep
0x180037b42  nop     dword ptr [rax+rax+00h]
0x180037b47  mov     ecx, ebp; unsigned int
0x180037b49  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180037b4e  movd    xmm0, edi
0x180037b52  mov     r14d, eax
0x180037b55  cvtdq2pd xmm0, xmm0
0x180037b59  mulsd   xmm0, cs:__real@3fe0000000000000
0x180037b61  cvttsd2si edi, xmm0
0x180037b65  cmp     edi, 2710h
0x180037b6b  jle     short loc_180037B74
0x180037b6d  mov     edi, 2710h
0x180037b72  jmp     short loc_180037B7E
0x180037b74  mov     eax, 64h ; 'd'
0x180037b79  cmp     edi, eax
0x180037b7b  cmovle  edi, eax
0x180037b7e  add     ebp, r12d
0x180037b81  jmp     loc_180037A88
```
