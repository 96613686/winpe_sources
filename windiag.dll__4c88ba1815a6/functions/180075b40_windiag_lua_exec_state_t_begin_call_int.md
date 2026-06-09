# windiag::lua_exec_state_t::begin_call(int)

- ea: `0x180075b40`
- end: `0x180075c42`
- name: `?begin_call@lua_exec_state_t@windiag@@QEAAXH@Z`
- size: `258`
- prototype: `void __fastcall(windiag::lua_exec_state_t *this, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800763a0`

## callees

- `0x18000491c`
- `0x1800660b0`
- `0x180075b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180075ba3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180075ba3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180075b6f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180075b6f`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180075b95`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180075b95`

## pseudocode

```c
void __fastcall windiag::lua_exec_state_t::begin_call(windiag::lua_exec_state_t *this, DWORD a2)
{
  char v2; // bl
  unsigned __int64 v4; // rdi
  LARGE_INTEGER v6; // rbp
  HANDLE CurrentThread; // rax
  DWORD CurrentThreadId; // r15d
  __int64 v9; // rdx
  __int64 v10; // r14
  LARGE_INTEGER *v11; // rdx
  LARGE_INTEGER v12; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 CycleTime; // [rsp+60h] [rbp+18h] BYREF

  v2 = *((_BYTE *)this + 144);
  v4 = 0;
  v12.QuadPart = 0;
  v6.QuadPart = 0;
  if ( QueryPerformanceCounter(&v12) )
    v6 = v12;
  if ( (v2 & 4) != 0 )
  {
    CycleTime = 0;
    CurrentThread = GetCurrentThread();
    if ( QueryThreadCycleTime(CurrentThread, &CycleTime) )
      v4 = CycleTime;
  }
  CurrentThreadId = GetCurrentThreadId();
  if ( *((_QWORD *)this + 21) <= (unsigned __int64)(*((_QWORD *)this + 23) + 1LL) )
    std::deque<windiag::lua_exec_state_t::call_entry>::_Growmap((char *)this + 152);
  v9 = *((_QWORD *)this + 21) - 1LL;
  *((_QWORD *)this + 22) &= v9;
  v10 = *((_QWORD *)this + 23) + *((_QWORD *)this + 22);
  if ( !*(_QWORD *)(*((_QWORD *)this + 20) + 8 * (v9 & v10)) )
    *(_QWORD *)(*((_QWORD *)this + 20) + 8 * (v9 & v10)) = operator new(0x20u);
  v11 = *(LARGE_INTEGER **)(*((_QWORD *)this + 20) + 8 * (v10 & (*((_QWORD *)this + 21) - 1LL)));
  *v11 = v6;
  v11[1].QuadPart = v4;
  v11[2].QuadPart = 0;
  v11[3].LowPart = a2;
  v11[3].HighPart = CurrentThreadId;
  ++*((_QWORD *)this + 23);
}

```

## disassembly

```asm
0x180075b40  mov     rax, rsp
0x180075b43  mov     [rax+10h], rbx
0x180075b47  mov     [rax+20h], rbp
0x180075b4b  push    rsi
0x180075b4c  push    rdi
0x180075b4d  push    r12
0x180075b4f  push    r14
0x180075b51  push    r15
0x180075b53  sub     rsp, 20h
0x180075b57  mov     bl, [rcx+90h]
0x180075b5d  mov     rsi, rcx
0x180075b60  xor     edi, edi
0x180075b62  lea     rcx, [rax+8]; lpPerformanceCount
0x180075b66  mov     [rax+8], rdi
0x180075b6a  mov     r12d, edx
0x180075b6d  xor     ebp, ebp
0x180075b6f  call    cs:__imp_QueryPerformanceCounter
0x180075b75  test    eax, eax
0x180075b77  cmovnz  rbp, [rsp+48h+arg_0]
0x180075b7d  test    bl, 4
0x180075b80  jz      short loc_180075BA3
0x180075b82  mov     [rsp+48h+CycleTime], rdi
0x180075b87  call    cs:__imp_GetCurrentThread
0x180075b8d  mov     rcx, rax; ThreadHandle
0x180075b90  lea     rdx, [rsp+48h+CycleTime]; CycleTime
0x180075b95  call    cs:__imp_QueryThreadCycleTime
0x180075b9b  test    eax, eax
0x180075b9d  cmovnz  rdi, [rsp+48h+CycleTime]
0x180075ba3  call    cs:__imp_GetCurrentThreadId
0x180075ba9  lea     rbx, [rsi+98h]
0x180075bb0  mov     r15d, eax
0x180075bb3  mov     rcx, [rbx+20h]
0x180075bb7  inc     rcx
0x180075bba  cmp     [rbx+10h], rcx
0x180075bbe  ja      short loc_180075BC8
0x180075bc0  mov     rcx, rbx
0x180075bc3  call    ?_Growmap@?$deque@Ucall_entry@lua_exec_state_t@windiag@@V?$allocator@Ucall_entry@lua_exec_state_t@windiag@@@std@@@std@@AEAAX_K@Z; std::deque<windiag::lua_exec_state_t::call_entry>::_Growmap(unsigned __int64)
0x180075bc8  mov     rdx, [rbx+10h]
0x180075bcc  dec     rdx
0x180075bcf  and     [rbx+18h], rdx
0x180075bd3  mov     r14, [rbx+18h]
0x180075bd7  add     r14, [rbx+20h]
0x180075bdb  mov     rax, [rbx+8]
0x180075bdf  mov     rsi, r14
0x180075be2  and     rsi, rdx
0x180075be5  cmp     qword ptr [rax+rsi*8], 0
0x180075bea  jnz     short loc_180075BFE
0x180075bec  mov     ecx, 20h ; ' '; Size
0x180075bf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180075bf6  mov     rcx, [rbx+8]
0x180075bfa  mov     [rcx+rsi*8], rax
0x180075bfe  mov     rcx, [rbx+10h]
0x180075c02  mov     rax, [rbx+8]
0x180075c06  dec     rcx
0x180075c09  and     rcx, r14
0x180075c0c  mov     rdx, [rax+rcx*8]
0x180075c10  mov     [rdx], rbp
0x180075c13  mov     rbp, [rsp+48h+arg_18]
0x180075c18  mov     [rdx+8], rdi
0x180075c1c  mov     qword ptr [rdx+10h], 0
0x180075c24  mov     [rdx+18h], r12d
0x180075c28  mov     [rdx+1Ch], r15d
0x180075c2c  inc     qword ptr [rbx+20h]
0x180075c30  mov     rbx, [rsp+48h+arg_8]
0x180075c35  add     rsp, 20h
0x180075c39  pop     r15
0x180075c3b  pop     r14
0x180075c3d  pop     r12
0x180075c3f  pop     rdi
0x180075c40  pop     rsi
0x180075c41  retn
```
