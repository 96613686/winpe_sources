# windiag::lua_exec_state_t::end_call(void)

- ea: `0x180075e14`
- end: `0x180075f97`
- name: `?end_call@lua_exec_state_t@windiag@@QEAA?AUcall_entry@12@XZ`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800763a0`

## callees

- `0x180075e14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075e66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075e66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180075e82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180075e82`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180075e4e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180075e4e`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180075e74`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180075e74`

## pseudocode

```c
__int64 __fastcall windiag::lua_exec_state_t::end_call(__int64 a1, __int64 a2)
{
  char v4; // bl
  signed __int64 v5; // rbp
  LARGE_INTEGER v6; // r14
  HANDLE CurrentThread; // rax
  DWORD CurrentThreadId; // eax
  _QWORD *v9; // r9
  LARGE_INTEGER *v10; // rdx
  LONGLONG QuadPart; // r8
  signed __int64 v12; // rcx
  DWORD LowPart; // r10d
  double v14; // xmm1_8
  __int64 v15; // r11
  __int64 v16; // rdx
  LARGE_INTEGER v19; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 CycleTime; // [rsp+50h] [rbp+18h] BYREF

  if ( *(_QWORD *)(a1 + 184) )
  {
    v4 = *(_BYTE *)(a1 + 144);
    v5 = 0;
    v19.QuadPart = 0;
    v6.QuadPart = 0;
    if ( QueryPerformanceCounter(&v19) )
      v6 = v19;
    if ( (v4 & 4) != 0 )
    {
      CycleTime = 0;
      CurrentThread = GetCurrentThread();
      if ( QueryThreadCycleTime(CurrentThread, &CycleTime) )
        v5 = CycleTime;
    }
    CurrentThreadId = GetCurrentThreadId();
    if ( *(__int64 *)(a1 + 96) <= 0
      || (v9 = (_QWORD *)(a1 + 176),
          v10 = *(LARGE_INTEGER **)(*(_QWORD *)(a1 + 160)
                                  + 8
                                  * ((*(_QWORD *)(a1 + 168) - 1LL)
                                   & (*(_QWORD *)(a1 + 184) - 1LL + *(_QWORD *)(a1 + 176)))),
          QuadPart = v10->QuadPart,
          v6.QuadPart <= v10->QuadPart)
      || QuadPart <= *(_QWORD *)(a1 + 88) )
    {
      LowPart = 0;
      v9 = (_QWORD *)(a1 + 176);
      v15 = 0;
      v12 = 0;
      v16 = 0;
    }
    else
    {
      v12 = 0;
      if ( CurrentThreadId == v10[3].HighPart && v5 > v10[1].QuadPart )
        v12 = v5 - v10[1].QuadPart;
      LowPart = v10[3].LowPart;
      v14 = 10000000.0 / (double)(int)*(_QWORD *)(a1 + 96);
      v15 = (unsigned int)(int)((double)(v6.LowPart - (int)QuadPart) * v14);
      v16 = (unsigned int)(int)((double)((int)QuadPart - *(_DWORD *)(a1 + 88)) * v14);
    }
    if ( (*(_QWORD *)(a1 + 184))-- == 1 )
      *v9 = 0;
    *(_QWORD *)a2 = v16;
    *(_QWORD *)(a2 + 8) = v12;
    *(_QWORD *)(a2 + 16) = v15;
    *(_DWORD *)(a2 + 24) = LowPart;
    *(_DWORD *)(a2 + 28) = 0;
  }
  else
  {
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180075e14  mov     rax, rsp
0x180075e17  mov     [rax+10h], rbx
0x180075e1b  mov     [rax+20h], rbp
0x180075e1f  push    rsi
0x180075e20  push    rdi
0x180075e21  push    r14
0x180075e23  sub     rsp, 20h
0x180075e27  cmp     qword ptr [rcx+0B8h], 0
0x180075e2f  mov     rdi, rdx
0x180075e32  mov     rsi, rcx
0x180075e35  jz      loc_180075F62
0x180075e3b  mov     bl, [rcx+90h]
0x180075e41  xor     ebp, ebp
0x180075e43  lea     rcx, [rax+8]; lpPerformanceCount
0x180075e47  mov     [rax+8], rbp
0x180075e4b  xor     r14d, r14d
0x180075e4e  call    cs:__imp_QueryPerformanceCounter
0x180075e54  test    eax, eax
0x180075e56  cmovnz  r14, [rsp+38h+arg_0]
0x180075e5c  test    bl, 4
0x180075e5f  jz      short loc_180075E82
0x180075e61  mov     [rsp+38h+CycleTime], rbp
0x180075e66  call    cs:__imp_GetCurrentThread
0x180075e6c  mov     rcx, rax; ThreadHandle
0x180075e6f  lea     rdx, [rsp+38h+CycleTime]; CycleTime
0x180075e74  call    cs:__imp_QueryThreadCycleTime
0x180075e7a  test    eax, eax
0x180075e7c  cmovnz  rbp, [rsp+38h+CycleTime]
0x180075e82  call    cs:__imp_GetCurrentThreadId
0x180075e88  cmp     qword ptr [rsi+60h], 0
0x180075e8d  jle     loc_180075F28
0x180075e93  mov     rdx, [rsi+0B8h]
0x180075e9a  lea     r9, [rsi+0B0h]
0x180075ea1  mov     r8, [r9]
0x180075ea4  dec     rdx
0x180075ea7  mov     rcx, [rsi+0A8h]
0x180075eae  add     r8, rdx
0x180075eb1  dec     rcx
0x180075eb4  and     r8, rcx
0x180075eb7  mov     rcx, [rsi+0A0h]
0x180075ebe  mov     rdx, [rcx+r8*8]
0x180075ec2  mov     r8, [rdx]
0x180075ec5  cmp     r14, r8
0x180075ec8  jle     short loc_180075F28
0x180075eca  cmp     r8, [rsi+58h]
0x180075ece  jle     short loc_180075F28
0x180075ed0  xor     ecx, ecx
0x180075ed2  cmp     eax, [rdx+1Ch]
0x180075ed5  jnz     short loc_180075EE4
0x180075ed7  cmp     rbp, [rdx+8]
0x180075edb  jle     short loc_180075EE4
0x180075edd  mov     rcx, rbp
0x180075ee0  sub     rcx, [rdx+8]
0x180075ee4  movsd   xmm1, cs:__real@416312d000000000
0x180075eec  xorps   xmm0, xmm0
0x180075eef  cvtsi2sd xmm0, qword ptr [rsi+60h]
0x180075ef5  mov     r10d, [rdx+18h]
0x180075ef9  sub     r14, r8
0x180075efc  sub     r8, [rsi+58h]
0x180075f00  divsd   xmm1, xmm0
0x180075f04  xorps   xmm0, xmm0
0x180075f07  cvtsi2sd xmm0, r14
0x180075f0c  mulsd   xmm0, xmm1
0x180075f10  cvttsd2si r11, xmm0
0x180075f15  xorps   xmm0, xmm0
0x180075f18  cvtsi2sd xmm0, r8
0x180075f1d  mulsd   xmm0, xmm1
0x180075f21  cvttsd2si rdx, xmm0
0x180075f26  jmp     short loc_180075F39
0x180075f28  xor     r10d, r10d
0x180075f2b  lea     r9, [rsi+0B0h]
0x180075f32  xor     r11d, r11d
0x180075f35  xor     ecx, ecx
0x180075f37  xor     edx, edx
0x180075f39  sub     qword ptr [rsi+0B8h], 1
0x180075f41  jnz     short loc_180075F4A
0x180075f43  mov     qword ptr [r9], 0
0x180075f4a  mov     [rdi], rdx
0x180075f4d  mov     [rdi+8], rcx
0x180075f51  mov     [rdi+10h], r11
0x180075f55  mov     [rdi+18h], r10d
0x180075f59  mov     dword ptr [rdi+1Ch], 0
0x180075f60  jmp     short loc_180075F81
0x180075f62  mov     qword ptr [rdx], 0
0x180075f69  mov     qword ptr [rdx+8], 0
0x180075f71  mov     qword ptr [rdx+10h], 0
0x180075f79  mov     qword ptr [rdx+18h], 0
0x180075f81  mov     rbx, [rsp+38h+arg_8]
0x180075f86  mov     rax, rdi
0x180075f89  mov     rbp, [rsp+38h+arg_18]
0x180075f8e  add     rsp, 20h
0x180075f92  pop     r14
0x180075f94  pop     rdi
0x180075f95  pop     rsi
0x180075f96  retn
```
