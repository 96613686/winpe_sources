# PtiFromThreadId

- ea: `0x14010d570`
- end: `0x14010d699`
- name: `PtiFromThreadId`
- size: `297`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14018dcc0`
- `0x1401d88d0`
- `0x1401d8c00`

## callees

- `0x14010d570`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14010d5a4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010d5a4`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14010d5fe`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14010d5fe`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14010d5b3`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14010d5b3`
- `ntoskrnl!PsGetThreadSessionId` at `0x14010d5c6`
- `ntoskrnl!PsGetThreadSessionId` at `0x14010d5c6`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x14010d592`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x14010d592`
- `ntoskrnl!PsIsThreadTerminating` at `0x14010d5e7`
- `ntoskrnl!PsIsThreadTerminating` at `0x14010d5e7`
- `ntoskrnl!ObfDereferenceObject` at `0x14010d664`
- `ntoskrnl!ObfDereferenceObject` at `0x14010d689`
- `ntoskrnl!ObfDereferenceObject` at `0x14010d664`
- `ntoskrnl!ObfDereferenceObject` at `0x14010d689`
- `ntoskrnl!PsGetThreadId` at `0x14010d61a`
- `ntoskrnl!PsGetThreadId` at `0x14010d61a`

## pseudocode

```c
__int64 __fastcall PtiFromThreadId(int a1)
{
  HANDLE v1; // rsi
  __int64 v2; // rdx
  __int64 v3; // rcx
  NTSTATUS v4; // edi
  __int64 v5; // r8
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // ebx
  __int64 v8; // rbx
  __int64 *ThreadWin32Thread; // rax
  PETHREAD Thread; // [rsp+48h] [rbp+10h] BYREF

  Thread = 0;
  v1 = (HANDLE)a1;
  v4 = PsLookupThreadByThreadId((HANDLE)a1, &Thread);
  if ( v4 >= 0 )
  {
    CurrentProcess = PsGetCurrentProcess(v3, v2, v5);
    ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess);
    if ( (unsigned int)PsGetThreadSessionId(Thread) != ProcessSessionId )
    {
      ObfDereferenceObject(Thread);
      return 0;
    }
  }
  if ( v4 < 0 )
    return 0;
  v8 = 0;
  if ( !PsIsThreadTerminating(Thread) )
  {
    ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(Thread);
    if ( ThreadWin32Thread )
      v8 = *ThreadWin32Thread;
    if ( v8 )
    {
      if ( PsGetThreadId(*(PETHREAD *)v8) == v1
        && (_InterlockedCompareExchange((volatile signed __int32 *)(v8 + 520), 0, 0) & 0x1000000) != 0 )
      {
        if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v8 + 520), 0, 0) & 1) != 0 )
          v8 = 0;
      }
      else
      {
        v8 = 0;
      }
    }
  }
  ObfDereferenceObject(Thread);
  return v8;
}

```

## disassembly

```asm
0x14010d570  mov     rax, rsp
0x14010d573  mov     [rax+8], rbx
0x14010d577  mov     [rax+18h], rsi
0x14010d57b  push    rdi
0x14010d57c  sub     rsp, 30h
0x14010d580  mov     qword ptr [rax+10h], 0
0x14010d588  movsxd  rsi, ecx
0x14010d58b  lea     rdx, [rax+10h]; Thread
0x14010d58f  mov     rcx, rsi; ThreadId
0x14010d592  call    cs:__imp_PsLookupThreadByThreadId
0x14010d599  nop     dword ptr [rax+rax+00h]
0x14010d59e  mov     edi, eax
0x14010d5a0  test    eax, eax
0x14010d5a2  js      short loc_14010D5DA
0x14010d5a4  call    cs:__imp_PsGetCurrentProcess
0x14010d5ab  nop     dword ptr [rax+rax+00h]
0x14010d5b0  mov     rcx, rax
0x14010d5b3  call    cs:__imp_PsGetProcessSessionIdEx
0x14010d5ba  nop     dword ptr [rax+rax+00h]
0x14010d5bf  mov     ebx, eax
0x14010d5c1  mov     rcx, [rsp+38h+Thread]
0x14010d5c6  call    cs:__imp_PsGetThreadSessionId
0x14010d5cd  nop     dword ptr [rax+rax+00h]
0x14010d5d2  cmp     eax, ebx
0x14010d5d4  jnz     loc_14010D684
0x14010d5da  test    edi, edi
0x14010d5dc  js      loc_14010D695
0x14010d5e2  mov     rcx, [rsp+38h+Thread]; Thread
0x14010d5e7  call    cs:__imp_PsIsThreadTerminating
0x14010d5ee  nop     dword ptr [rax+rax+00h]
0x14010d5f3  xor     ebx, ebx
0x14010d5f5  test    al, al
0x14010d5f7  jnz     short loc_14010D65F
0x14010d5f9  mov     rcx, [rsp+38h+Thread]
0x14010d5fe  call    cs:__imp_PsGetThreadWin32Thread
0x14010d605  nop     dword ptr [rax+rax+00h]
0x14010d60a  test    rax, rax
0x14010d60d  jz      short loc_14010D612
0x14010d60f  mov     rbx, [rax]
0x14010d612  test    rbx, rbx
0x14010d615  jz      short loc_14010D65F
0x14010d617  mov     rcx, [rbx]; Thread
0x14010d61a  call    cs:__imp_PsGetThreadId
0x14010d621  nop     dword ptr [rax+rax+00h]
0x14010d626  cmp     rax, rsi
0x14010d629  jnz     short loc_14010D64F
0x14010d62b  xor     ecx, ecx
0x14010d62d  xor     eax, eax
0x14010d62f  lock cmpxchg [rbx+208h], ecx
0x14010d637  bt      eax, 18h
0x14010d63b  jnb     short loc_14010D64F
0x14010d63d  xor     eax, eax
0x14010d63f  lock cmpxchg [rbx+208h], ecx
0x14010d647  test    al, 1
0x14010d649  cmovnz  rbx, rcx
0x14010d64d  jmp     short loc_14010D651
0x14010d64f  xor     ebx, ebx
0x14010d651  mov     [rsp+38h+var_18], rbx
0x14010d656  jmp     short loc_14010D65F
0x14010d658  xor     ebx, ebx
0x14010d65a  mov     [rsp+38h+var_18], rbx
0x14010d65f  mov     rcx, [rsp+38h+Thread]; Object
0x14010d664  call    cs:__imp_ObfDereferenceObject
0x14010d66b  nop     dword ptr [rax+rax+00h]
0x14010d670  mov     rax, rbx
0x14010d673  mov     rbx, [rsp+38h+arg_0]
0x14010d678  mov     rsi, [rsp+38h+arg_10]
0x14010d67d  add     rsp, 30h
0x14010d681  pop     rdi
0x14010d682  retn
0x14010d684  mov     rcx, [rsp+38h+Thread]; Object
0x14010d689  call    cs:__imp_ObfDereferenceObject
0x14010d690  nop     dword ptr [rax+rax+00h]
0x14010d695  xor     eax, eax
0x14010d697  jmp     short loc_14010D673
0x1402399fe  push    rbp
0x140239a00  sub     rsp, 20h
0x140239a04  mov     rbp, rdx
0x140239a07  mov     eax, 1
0x140239a0c  add     rsp, 20h
0x140239a10  pop     rbp
0x140239a11  retn
```
