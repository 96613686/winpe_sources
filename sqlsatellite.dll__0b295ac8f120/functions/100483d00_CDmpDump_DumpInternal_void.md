# CDmpDump::DumpInternal(void)

- ea: `0x100483d00`
- end: `0x100483ed8`
- name: `?DumpInternal@CDmpDump@@AEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(CDmpDump *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100483b90`
- `0x100483c00`

## callees

- `0x1004823d0`
- `0x1004838e0`
- `0x100483d00`

## import_xrefs

- `KERNEL32!GetThreadPriority` at `0x100483d1f`
- `KERNEL32!GetThreadPriority` at `0x100483d1f`
- `KERNEL32!SetThreadPriority` at `0x100483d3f`
- `KERNEL32!SetThreadPriority` at `0x100483eb1`
- `KERNEL32!SetThreadPriority` at `0x100483d3f`
- `KERNEL32!SetThreadPriority` at `0x100483eb1`
- `KERNEL32!GetCurrentThreadId` at `0x100483d49`
- `KERNEL32!GetCurrentThreadId` at `0x100483d49`
- `KERNEL32!GetCurrentThread` at `0x100483d16`
- `KERNEL32!GetCurrentThread` at `0x100483d33`
- `KERNEL32!GetCurrentThread` at `0x100483ea5`
- `KERNEL32!GetCurrentThread` at `0x100483d16`
- `KERNEL32!GetCurrentThread` at `0x100483d33`
- `KERNEL32!GetCurrentThread` at `0x100483ea5`
- `KERNEL32!GetCurrentProcessId` at `0x100483e3e`
- `KERNEL32!GetCurrentProcessId` at `0x100483e3e`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x100483e81`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x100483e81`

## pseudocode

```c
__int64 __fastcall CDmpDump::DumpInternal(CDmpDump *this)
{
  int v2; // ebx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r14d
  HANDLE v5; // rax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  HANDLE v18; // rax
  __int64 result; // rax

  v2 = 0;
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( ThreadPriority != 0x7FFFFFFF )
  {
    v5 = GetCurrentThread();
    SetThreadPriority(v5, 1);
  }
  if ( *((_DWORD *)this + 41) != GetCurrentThreadId() || **((_DWORD **)this + 6) != -1073741571 )
  {
    LOBYTE(v2) = (*((_DWORD *)this + 42) & 0x9000) != 0;
    v2 = CDmpClient::ExecuteAllCallbacks(*((CDmpClient **)this + 2), this, v2);
  }
  v6 = (*(__int64 (__fastcall **)(CDmpDump *, CDmpDump *, __int64))(*(_QWORD *)this + 96LL))(this, this, 5800);
  if ( v2 >= 0 )
    v2 = v6;
  v7 = *((_QWORD *)this + 10);
  v8 = -1;
  if ( v7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(v7 + 2 * v9) );
    v10 = (*(__int64 (__fastcall **)(CDmpDump *, __int64, __int64))(*(_QWORD *)this + 96LL))(this, v7, 2 * v9);
    if ( v2 >= 0 )
      v2 = v10;
  }
  v11 = *((_QWORD *)this + 9);
  if ( v11 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v11 + 2 * v12) );
    v13 = (*(__int64 (__fastcall **)(CDmpDump *, __int64, __int64))(*(_QWORD *)this + 96LL))(this, v11, 2 * v12);
    if ( v2 >= 0 )
      v2 = v13;
  }
  v14 = *((_QWORD *)this + 623);
  if ( v14 )
  {
    do
      ++v8;
    while ( *(_WORD *)(v14 + 2 * v8) );
    v15 = (*(__int64 (__fastcall **)(CDmpDump *, __int64, __int64))(*(_QWORD *)this + 96LL))(this, v14, 2 * v8);
    if ( v2 >= 0 )
      v2 = v15;
  }
  *((_DWORD *)this + 30) = GetCurrentProcessId();
  v16 = CDmpDump::ComputeChecksums(this);
  if ( v2 >= 0 )
    v2 = v16;
  v17 = (*(__int64 (__fastcall **)(CDmpDump *, _QWORD))(*(_QWORD *)this + 32LL))(this, 0);
  if ( v2 >= 0 )
    v2 = v17;
  if ( ThreadPriority != 0x7FFFFFFF )
  {
    v18 = GetCurrentThread();
    SetThreadPriority(v18, ThreadPriority);
  }
  result = (unsigned int)v2;
  if ( v2 >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x100483d00  mov     [rsp+arg_0], rbx
0x100483d05  push    rsi
0x100483d06  push    rdi
0x100483d07  push    r14
0x100483d09  sub     rsp, 40h
0x100483d0d  mov     rsi, rcx
0x100483d10  xor     ebx, ebx
0x100483d12  mov     [rsp+58h+var_38], ebx
0x100483d16  call    cs:__imp_GetCurrentThread
0x100483d1c  mov     rcx, rax; hThread
0x100483d1f  call    cs:__imp_GetThreadPriority
0x100483d25  mov     r14d, eax
0x100483d28  mov     [rsp+58h+arg_18], eax
0x100483d2c  cmp     eax, 7FFFFFFFh
0x100483d31  jz      short loc_100483D45
0x100483d33  call    cs:__imp_GetCurrentThread
0x100483d39  mov     rcx, rax; hThread
0x100483d3c  lea     edx, [rbx+1]; nPriority
0x100483d3f  call    cs:__imp_SetThreadPriority
0x100483d45  mov     [rsp+58h+arg_8], ebx
0x100483d49  call    cs:__imp_GetCurrentThreadId
0x100483d4f  cmp     [rsi+0A4h], eax
0x100483d55  jnz     short loc_100483D63
0x100483d57  mov     rax, [rsi+30h]
0x100483d5b  cmp     dword ptr [rax], 0C00000FDh
0x100483d61  jz      short loc_100483D85
0x100483d63  test    dword ptr [rsi+0A8h], 9000h
0x100483d6d  setnz   bl
0x100483d70  mov     r8d, ebx; int
0x100483d73  mov     rdx, rsi; struct CDmpDump *
0x100483d76  mov     rcx, [rsi+10h]; this
0x100483d7a  call    ?ExecuteAllCallbacks@CDmpClient@@QEAAJPEAVCDmpDump@@H@Z; CDmpClient::ExecuteAllCallbacks(CDmpDump *,int)
0x100483d7f  mov     ebx, eax
0x100483d81  mov     [rsp+58h+var_38], eax
0x100483d85  mov     r9, [rsi]
0x100483d88  mov     r8d, 16A8h
0x100483d8e  mov     rdx, rsi
0x100483d91  mov     rcx, rsi
0x100483d94  call    qword ptr [r9+60h]
0x100483d98  test    ebx, ebx
0x100483d9a  cmovns  ebx, eax
0x100483d9d  mov     [rsp+58h+var_38], ebx
0x100483da1  mov     rdx, [rsi+50h]
0x100483da5  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x100483dac  test    rdx, rdx
0x100483daf  jz      short loc_100483DDD
0x100483db1  mov     rax, [rsi]
0x100483db4  mov     r8, rdi
0x100483db7  nop     word ptr [rax+rax+00000000h]
0x100483dc0  inc     r8
0x100483dc3  cmp     word ptr [rdx+r8*2], 0
0x100483dc9  jnz     short loc_100483DC0
0x100483dcb  add     r8, r8
0x100483dce  mov     rcx, rsi
0x100483dd1  call    qword ptr [rax+60h]
0x100483dd4  test    ebx, ebx
0x100483dd6  cmovns  ebx, eax
0x100483dd9  mov     [rsp+58h+var_38], ebx
0x100483ddd  mov     rdx, [rsi+48h]
0x100483de1  test    rdx, rdx
0x100483de4  jz      short loc_100483E0D
0x100483de6  mov     rax, [rsi]
0x100483de9  mov     r8, rdi
0x100483dec  nop     dword ptr [rax+00h]
0x100483df0  inc     r8
0x100483df3  cmp     word ptr [rdx+r8*2], 0
0x100483df9  jnz     short loc_100483DF0
0x100483dfb  add     r8, r8
0x100483dfe  mov     rcx, rsi
0x100483e01  call    qword ptr [rax+60h]
0x100483e04  test    ebx, ebx
0x100483e06  cmovns  ebx, eax
0x100483e09  mov     [rsp+58h+var_38], ebx
0x100483e0d  mov     rdx, [rsi+1378h]
0x100483e14  test    rdx, rdx
0x100483e17  jz      short loc_100483E3E
0x100483e19  mov     rax, [rsi]
0x100483e1c  nop     dword ptr [rax+00h]
0x100483e20  lea     rdi, [rdi+1]
0x100483e24  cmp     word ptr [rdx+rdi*2], 0
0x100483e29  jnz     short loc_100483E20
0x100483e2b  lea     r8, [rdi+rdi]
0x100483e2f  mov     rcx, rsi
0x100483e32  call    qword ptr [rax+60h]
0x100483e35  test    ebx, ebx
0x100483e37  cmovns  ebx, eax
0x100483e3a  mov     [rsp+58h+var_38], ebx
0x100483e3e  call    cs:__imp_GetCurrentProcessId
0x100483e44  mov     [rsi+78h], eax
0x100483e47  mov     rcx, rsi; this
0x100483e4a  call    ?ComputeChecksums@CDmpDump@@AEAAJXZ; CDmpDump::ComputeChecksums(void)
0x100483e4f  test    ebx, ebx
0x100483e51  cmovns  ebx, eax
0x100483e54  mov     [rsp+58h+var_38], ebx
0x100483e58  mov     rax, [rsi]
0x100483e5b  xor     edx, edx
0x100483e5d  mov     rcx, rsi
0x100483e60  call    qword ptr [rax+20h]
0x100483e63  mov     [rsp+58h+arg_10], eax
0x100483e67  test    ebx, ebx
0x100483e69  cmovns  ebx, eax
0x100483e6c  mov     [rsp+58h+var_38], ebx
0x100483e70  jmp     short loc_100483E9C
0x100483e72  mov     [rsp+58h+arg_8], eax
0x100483e76  mov     eax, [rsp+58h+arg_8]
0x100483e7a  cmp     eax, 0C00000FDh
0x100483e7f  jnz     short loc_100483E87
0x100483e81  call    cs:__imp__resetstkoflw
0x100483e87  mov     eax, [rsp+58h+arg_8]
0x100483e8b  test    eax, eax
0x100483e8d  js      short loc_100483E97
0x100483e8f  mov     [rsp+58h+arg_8], 80004005h
0x100483e97  mov     r14d, [rsp+58h+arg_18]
0x100483e9c  cmp     r14d, 7FFFFFFFh
0x100483ea3  jz      short loc_100483EB7
0x100483ea5  call    cs:__imp_GetCurrentThread
0x100483eab  mov     rcx, rax; hThread
0x100483eae  mov     edx, r14d; nPriority
0x100483eb1  call    cs:__imp_SetThreadPriority
0x100483eb7  mov     eax, [rsp+58h+arg_8]
0x100483ebb  mov     [rsp+58h+arg_10], eax
0x100483ebf  mov     eax, [rsp+58h+var_38]
0x100483ec3  test    eax, eax
0x100483ec5  cmovns  eax, [rsp+58h+arg_10]
0x100483eca  mov     rbx, [rsp+58h+arg_0]
0x100483ecf  add     rsp, 40h
0x100483ed3  pop     r14
0x100483ed5  pop     rdi
0x100483ed6  pop     rsi
0x100483ed7  retn
0x10048dcb0  push    rbp
0x10048dcb2  sub     rsp, 20h
0x10048dcb6  mov     rbp, rdx
0x10048dcb9  mov     [rbp+28h], rcx
0x10048dcbd  mov     [rbp+30h], rcx
0x10048dcc1  mov     eax, 1
0x10048dcc6  add     rsp, 20h
0x10048dcca  pop     rbp
0x10048dccb  retn
```
