# CDmpDump::DumpInternal(void)

- ea: `0x100443a60`
- end: `0x100443c38`
- name: `?DumpInternal@CDmpDump@@AEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(CDmpDump *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1004438f0`
- `0x100443960`

## callees

- `0x100442120`
- `0x100443640`
- `0x100443a60`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x100443a9f`
- `KERNEL32!SetThreadPriority` at `0x100443c11`
- `KERNEL32!SetThreadPriority` at `0x100443a9f`
- `KERNEL32!SetThreadPriority` at `0x100443c11`
- `KERNEL32!GetCurrentThread` at `0x100443a76`
- `KERNEL32!GetCurrentThread` at `0x100443a93`
- `KERNEL32!GetCurrentThread` at `0x100443c05`
- `KERNEL32!GetCurrentThread` at `0x100443a76`
- `KERNEL32!GetCurrentThread` at `0x100443a93`
- `KERNEL32!GetCurrentThread` at `0x100443c05`
- `KERNEL32!GetCurrentThreadId` at `0x100443aa9`
- `KERNEL32!GetCurrentThreadId` at `0x100443aa9`
- `KERNEL32!GetCurrentProcessId` at `0x100443b9e`
- `KERNEL32!GetCurrentProcessId` at `0x100443b9e`
- `KERNEL32!GetThreadPriority` at `0x100443a7f`
- `KERNEL32!GetThreadPriority` at `0x100443a7f`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x100443be1`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x100443be1`

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
0x100443a60  mov     [rsp+arg_0], rbx
0x100443a65  push    rsi
0x100443a66  push    rdi
0x100443a67  push    r14
0x100443a69  sub     rsp, 40h
0x100443a6d  mov     rsi, rcx
0x100443a70  xor     ebx, ebx
0x100443a72  mov     [rsp+58h+var_38], ebx
0x100443a76  call    cs:__imp_GetCurrentThread
0x100443a7c  mov     rcx, rax; hThread
0x100443a7f  call    cs:__imp_GetThreadPriority
0x100443a85  mov     r14d, eax
0x100443a88  mov     [rsp+58h+arg_18], eax
0x100443a8c  cmp     eax, 7FFFFFFFh
0x100443a91  jz      short loc_100443AA5
0x100443a93  call    cs:__imp_GetCurrentThread
0x100443a99  mov     rcx, rax; hThread
0x100443a9c  lea     edx, [rbx+1]; nPriority
0x100443a9f  call    cs:__imp_SetThreadPriority
0x100443aa5  mov     [rsp+58h+arg_8], ebx
0x100443aa9  call    cs:__imp_GetCurrentThreadId
0x100443aaf  cmp     [rsi+0A4h], eax
0x100443ab5  jnz     short loc_100443AC3
0x100443ab7  mov     rax, [rsi+30h]
0x100443abb  cmp     dword ptr [rax], 0C00000FDh
0x100443ac1  jz      short loc_100443AE5
0x100443ac3  test    dword ptr [rsi+0A8h], 9000h
0x100443acd  setnz   bl
0x100443ad0  mov     r8d, ebx; int
0x100443ad3  mov     rdx, rsi; struct CDmpDump *
0x100443ad6  mov     rcx, [rsi+10h]; this
0x100443ada  call    ?ExecuteAllCallbacks@CDmpClient@@QEAAJPEAVCDmpDump@@H@Z; CDmpClient::ExecuteAllCallbacks(CDmpDump *,int)
0x100443adf  mov     ebx, eax
0x100443ae1  mov     [rsp+58h+var_38], eax
0x100443ae5  mov     r9, [rsi]
0x100443ae8  mov     r8d, 16A8h
0x100443aee  mov     rdx, rsi
0x100443af1  mov     rcx, rsi
0x100443af4  call    qword ptr [r9+60h]
0x100443af8  test    ebx, ebx
0x100443afa  cmovns  ebx, eax
0x100443afd  mov     [rsp+58h+var_38], ebx
0x100443b01  mov     rdx, [rsi+50h]
0x100443b05  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x100443b0c  test    rdx, rdx
0x100443b0f  jz      short loc_100443B3D
0x100443b11  mov     rax, [rsi]
0x100443b14  mov     r8, rdi
0x100443b17  nop     word ptr [rax+rax+00000000h]
0x100443b20  inc     r8
0x100443b23  cmp     word ptr [rdx+r8*2], 0
0x100443b29  jnz     short loc_100443B20
0x100443b2b  add     r8, r8
0x100443b2e  mov     rcx, rsi
0x100443b31  call    qword ptr [rax+60h]
0x100443b34  test    ebx, ebx
0x100443b36  cmovns  ebx, eax
0x100443b39  mov     [rsp+58h+var_38], ebx
0x100443b3d  mov     rdx, [rsi+48h]
0x100443b41  test    rdx, rdx
0x100443b44  jz      short loc_100443B6D
0x100443b46  mov     rax, [rsi]
0x100443b49  mov     r8, rdi
0x100443b4c  nop     dword ptr [rax+00h]
0x100443b50  inc     r8
0x100443b53  cmp     word ptr [rdx+r8*2], 0
0x100443b59  jnz     short loc_100443B50
0x100443b5b  add     r8, r8
0x100443b5e  mov     rcx, rsi
0x100443b61  call    qword ptr [rax+60h]
0x100443b64  test    ebx, ebx
0x100443b66  cmovns  ebx, eax
0x100443b69  mov     [rsp+58h+var_38], ebx
0x100443b6d  mov     rdx, [rsi+1378h]
0x100443b74  test    rdx, rdx
0x100443b77  jz      short loc_100443B9E
0x100443b79  mov     rax, [rsi]
0x100443b7c  nop     dword ptr [rax+00h]
0x100443b80  lea     rdi, [rdi+1]
0x100443b84  cmp     word ptr [rdx+rdi*2], 0
0x100443b89  jnz     short loc_100443B80
0x100443b8b  lea     r8, [rdi+rdi]
0x100443b8f  mov     rcx, rsi
0x100443b92  call    qword ptr [rax+60h]
0x100443b95  test    ebx, ebx
0x100443b97  cmovns  ebx, eax
0x100443b9a  mov     [rsp+58h+var_38], ebx
0x100443b9e  call    cs:__imp_GetCurrentProcessId
0x100443ba4  mov     [rsi+78h], eax
0x100443ba7  mov     rcx, rsi; this
0x100443baa  call    ?ComputeChecksums@CDmpDump@@AEAAJXZ; CDmpDump::ComputeChecksums(void)
0x100443baf  test    ebx, ebx
0x100443bb1  cmovns  ebx, eax
0x100443bb4  mov     [rsp+58h+var_38], ebx
0x100443bb8  mov     rax, [rsi]
0x100443bbb  xor     edx, edx
0x100443bbd  mov     rcx, rsi
0x100443bc0  call    qword ptr [rax+20h]
0x100443bc3  mov     [rsp+58h+arg_10], eax
0x100443bc7  test    ebx, ebx
0x100443bc9  cmovns  ebx, eax
0x100443bcc  mov     [rsp+58h+var_38], ebx
0x100443bd0  jmp     short loc_100443BFC
0x100443bd2  mov     [rsp+58h+arg_8], eax
0x100443bd6  mov     eax, [rsp+58h+arg_8]
0x100443bda  cmp     eax, 0C00000FDh
0x100443bdf  jnz     short loc_100443BE7
0x100443be1  call    cs:__imp__resetstkoflw
0x100443be7  mov     eax, [rsp+58h+arg_8]
0x100443beb  test    eax, eax
0x100443bed  js      short loc_100443BF7
0x100443bef  mov     [rsp+58h+arg_8], 80004005h
0x100443bf7  mov     r14d, [rsp+58h+arg_18]
0x100443bfc  cmp     r14d, 7FFFFFFFh
0x100443c03  jz      short loc_100443C17
0x100443c05  call    cs:__imp_GetCurrentThread
0x100443c0b  mov     rcx, rax; hThread
0x100443c0e  mov     edx, r14d; nPriority
0x100443c11  call    cs:__imp_SetThreadPriority
0x100443c17  mov     eax, [rsp+58h+arg_8]
0x100443c1b  mov     [rsp+58h+arg_10], eax
0x100443c1f  mov     eax, [rsp+58h+var_38]
0x100443c23  test    eax, eax
0x100443c25  cmovns  eax, [rsp+58h+arg_10]
0x100443c2a  mov     rbx, [rsp+58h+arg_0]
0x100443c2f  add     rsp, 40h
0x100443c33  pop     r14
0x100443c35  pop     rdi
0x100443c36  pop     rsi
0x100443c37  retn
0x100456430  push    rbp
0x100456432  sub     rsp, 20h
0x100456436  mov     rbp, rdx
0x100456439  mov     [rbp+28h], rcx
0x10045643d  mov     [rbp+30h], rcx
0x100456441  mov     eax, 1
0x100456446  add     rsp, 20h
0x10045644a  pop     rbp
0x10045644b  retn
```
