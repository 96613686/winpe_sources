# CSpinLock::_LockSpin(void)

- ea: `0x180035058`
- end: `0x18003514b`
- name: `?_LockSpin@CSpinLock@@AEAAXXZ`
- size: `243`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180023984`
- `0x180033e50`

## callees

- `0x180034dfc`
- `0x180035058`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003506f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035117`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003506f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035117`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800350bd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180035102`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800350bd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180035102`

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
  v4 = (int)(*(double *)&qword_18003B350[GetCurrentThreadId() % 0xD] * 4000.0);
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
0x180035058  mov     [rsp+arg_0], rbx
0x18003505d  mov     [rsp+arg_10], rbp
0x180035062  push    rsi
0x180035063  push    rdi
0x180035064  push    r15
0x180035066  sub     rsp, 20h
0x18003506a  mov     rdi, rcx
0x18003506d  xor     ebp, ebp
0x18003506f  call    cs:__imp_GetCurrentThreadId
0x180035075  mov     r9d, eax
0x180035078  lea     rcx, qword_18003B350
0x18003507f  mov     eax, 4EC4EC4Fh
0x180035084  lea     r15d, [rbp+64h]
0x180035088  mul     r9d
0x18003508b  shr     edx, 2
0x18003508e  imul    r8d, edx, 0Dh
0x180035092  sub     r9d, r8d
0x180035095  xor     esi, esi
0x180035097  movsd   xmm0, qword ptr [rcx+r9*8]
0x18003509d  mulsd   xmm0, cs:__real@40af400000000000
0x1800350a5  cvttsd2si ebx, xmm0
0x1800350a9  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x1800350b0  jbe     short loc_180035100
0x1800350b2  mov     edx, ebx
0x1800350b4  jmp     short loc_1800350F8
0x1800350b6  sub     edx, 1
0x1800350b9  jns     short loc_1800350F8
0x1800350bb  mov     ecx, ebp; dwMilliseconds
0x1800350bd  call    cs:__imp_Sleep
0x1800350c3  movd    xmm0, ebx
0x1800350c7  cvtdq2pd xmm0, xmm0
0x1800350cb  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800350d3  cvttsd2si ebx, xmm0
0x1800350d7  cmp     ebx, 2710h
0x1800350dd  jle     short loc_1800350E6
0x1800350df  mov     ebx, 2710h
0x1800350e4  jmp     short loc_1800350ED
0x1800350e6  cmp     ebx, r15d
0x1800350e9  cmovle  ebx, r15d
0x1800350ed  mov     ecx, esi; unsigned int
0x1800350ef  mov     edx, ebx
0x1800350f1  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x1800350f6  mov     ebp, eax
0x1800350f8  mov     eax, [rdi]
0x1800350fa  test    eax, eax
0x1800350fc  jnz     short loc_1800350B6
0x1800350fe  jmp     short loc_180035111
0x180035100  mov     ecx, ebp; dwMilliseconds
0x180035102  call    cs:__imp_Sleep
0x180035108  mov     ecx, esi; unsigned int
0x18003510a  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18003510f  mov     ebp, eax
0x180035111  mov     eax, [rdi]
0x180035113  test    eax, eax
0x180035115  jnz     short loc_180035131
0x180035117  call    cs:__imp_GetCurrentThreadId
0x18003511d  mov     ecx, eax
0x18003511f  and     ecx, 0FFFFFFFh
0x180035125  bts     ecx, 1Ch
0x180035129  xor     eax, eax
0x18003512b  lock cmpxchg [rdi], ecx
0x18003512f  jz      short loc_180035138
0x180035131  inc     esi
0x180035133  jmp     loc_1800350A9
0x180035138  mov     rbx, [rsp+38h+arg_0]
0x18003513d  mov     rbp, [rsp+38h+arg_10]
0x180035142  add     rsp, 20h
0x180035146  pop     r15
0x180035148  pop     rdi
0x180035149  pop     rsi
0x18003514a  retn
```
