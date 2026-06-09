# CSpinLock::_LockSpin(void)

- ea: `0x1800579f4`
- end: `0x180057b00`
- name: `?_LockSpin@CSpinLock@@AEAAXXZ`
- size: `268`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003a80c`
- `0x18003a8fc`

## callees

- `0x180057774`
- `0x1800579f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057a0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057ac5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057a0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057ac5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180057a5f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180057aaa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180057a5f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180057aaa`

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
  v4 = (int)(*(double *)&qword_18006DD50[GetCurrentThreadId() % 0xD] * 4000.0);
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
0x1800579f4  mov     [rsp+arg_0], rbx
0x1800579f9  mov     [rsp+arg_10], rbp
0x1800579fe  push    rsi
0x1800579ff  push    rdi
0x180057a00  push    r15
0x180057a02  sub     rsp, 20h
0x180057a06  mov     rdi, rcx
0x180057a09  xor     ebp, ebp
0x180057a0b  call    cs:__imp_GetCurrentThreadId
0x180057a12  nop     dword ptr [rax+rax+00h]
0x180057a17  mov     r9d, eax
0x180057a1a  lea     rcx, qword_18006DD50
0x180057a21  mov     eax, 4EC4EC4Fh
0x180057a26  lea     r15d, [rbp+64h]
0x180057a2a  mul     r9d
0x180057a2d  shr     edx, 2
0x180057a30  imul    r8d, edx, 0Dh
0x180057a34  sub     r9d, r8d
0x180057a37  xor     esi, esi
0x180057a39  movsd   xmm0, qword ptr [rcx+r9*8]
0x180057a3f  mulsd   xmm0, cs:__real@40af400000000000
0x180057a47  cvttsd2si ebx, xmm0
0x180057a4b  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x180057a52  jbe     short loc_180057AA8
0x180057a54  mov     edx, ebx
0x180057a56  jmp     short loc_180057AA0
0x180057a58  sub     edx, 1
0x180057a5b  jns     short loc_180057AA0
0x180057a5d  mov     ecx, ebp; dwMilliseconds
0x180057a5f  call    cs:__imp_Sleep
0x180057a66  nop     dword ptr [rax+rax+00h]
0x180057a6b  movd    xmm0, ebx
0x180057a6f  cvtdq2pd xmm0, xmm0
0x180057a73  mulsd   xmm0, cs:__real@3fe0000000000000
0x180057a7b  cvttsd2si ebx, xmm0
0x180057a7f  cmp     ebx, 2710h
0x180057a85  jle     short loc_180057A8E
0x180057a87  mov     ebx, 2710h
0x180057a8c  jmp     short loc_180057A95
0x180057a8e  cmp     ebx, r15d
0x180057a91  cmovle  ebx, r15d
0x180057a95  mov     ecx, esi; unsigned int
0x180057a97  mov     edx, ebx
0x180057a99  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180057a9e  mov     ebp, eax
0x180057aa0  mov     eax, [rdi]
0x180057aa2  test    eax, eax
0x180057aa4  jnz     short loc_180057A58
0x180057aa6  jmp     short loc_180057ABF
0x180057aa8  mov     ecx, ebp; dwMilliseconds
0x180057aaa  call    cs:__imp_Sleep
0x180057ab1  nop     dword ptr [rax+rax+00h]
0x180057ab6  mov     ecx, esi; unsigned int
0x180057ab8  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180057abd  mov     ebp, eax
0x180057abf  mov     eax, [rdi]
0x180057ac1  test    eax, eax
0x180057ac3  jnz     short loc_180057AE5
0x180057ac5  call    cs:__imp_GetCurrentThreadId
0x180057acc  nop     dword ptr [rax+rax+00h]
0x180057ad1  mov     ecx, eax
0x180057ad3  and     ecx, 0FFFFFFFh
0x180057ad9  bts     ecx, 1Ch
0x180057add  xor     eax, eax
0x180057adf  lock cmpxchg [rdi], ecx
0x180057ae3  jz      short loc_180057AEC
0x180057ae5  inc     esi
0x180057ae7  jmp     loc_180057A4B
0x180057aec  mov     rbx, [rsp+38h+arg_0]
0x180057af1  mov     rbp, [rsp+38h+arg_10]
0x180057af6  add     rsp, 20h
0x180057afa  pop     r15
0x180057afc  pop     rdi
0x180057afd  pop     rsi
0x180057afe  retn
```
