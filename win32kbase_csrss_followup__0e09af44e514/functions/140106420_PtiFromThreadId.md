# PtiFromThreadId

- ea: `0x140106420`
- end: `0x140106549`
- name: `PtiFromThreadId`
- size: `297`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14018c3f0`
- `0x1401d7df0`
- `0x1401d8120`

## callees

- `0x140106420`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140106454`
- `ntoskrnl!PsGetCurrentProcess` at `0x140106454`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1401064ae`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1401064ae`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140106463`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140106463`
- `ntoskrnl!PsGetThreadSessionId` at `0x140106476`
- `ntoskrnl!PsGetThreadSessionId` at `0x140106476`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x140106442`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x140106442`
- `ntoskrnl!PsIsThreadTerminating` at `0x140106497`
- `ntoskrnl!PsIsThreadTerminating` at `0x140106497`
- `ntoskrnl!ObfDereferenceObject` at `0x140106514`
- `ntoskrnl!ObfDereferenceObject` at `0x140106539`
- `ntoskrnl!ObfDereferenceObject` at `0x140106514`
- `ntoskrnl!ObfDereferenceObject` at `0x140106539`
- `ntoskrnl!PsGetThreadId` at `0x1401064ca`
- `ntoskrnl!PsGetThreadId` at `0x1401064ca`

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
0x140106420  mov     rax, rsp
0x140106423  mov     [rax+8], rbx
0x140106427  mov     [rax+18h], rsi
0x14010642b  push    rdi
0x14010642c  sub     rsp, 30h
0x140106430  mov     qword ptr [rax+10h], 0
0x140106438  movsxd  rsi, ecx
0x14010643b  lea     rdx, [rax+10h]; Thread
0x14010643f  mov     rcx, rsi; ThreadId
0x140106442  call    cs:__imp_PsLookupThreadByThreadId
0x140106449  nop     dword ptr [rax+rax+00h]
0x14010644e  mov     edi, eax
0x140106450  test    eax, eax
0x140106452  js      short loc_14010648A
0x140106454  call    cs:__imp_PsGetCurrentProcess
0x14010645b  nop     dword ptr [rax+rax+00h]
0x140106460  mov     rcx, rax
0x140106463  call    cs:__imp_PsGetProcessSessionIdEx
0x14010646a  nop     dword ptr [rax+rax+00h]
0x14010646f  mov     ebx, eax
0x140106471  mov     rcx, [rsp+38h+Thread]
0x140106476  call    cs:__imp_PsGetThreadSessionId
0x14010647d  nop     dword ptr [rax+rax+00h]
0x140106482  cmp     eax, ebx
0x140106484  jnz     loc_140106534
0x14010648a  test    edi, edi
0x14010648c  js      loc_140106545
0x140106492  mov     rcx, [rsp+38h+Thread]; Thread
0x140106497  call    cs:__imp_PsIsThreadTerminating
0x14010649e  nop     dword ptr [rax+rax+00h]
0x1401064a3  xor     ebx, ebx
0x1401064a5  test    al, al
0x1401064a7  jnz     short loc_14010650F
0x1401064a9  mov     rcx, [rsp+38h+Thread]
0x1401064ae  call    cs:__imp_PsGetThreadWin32Thread
0x1401064b5  nop     dword ptr [rax+rax+00h]
0x1401064ba  test    rax, rax
0x1401064bd  jz      short loc_1401064C2
0x1401064bf  mov     rbx, [rax]
0x1401064c2  test    rbx, rbx
0x1401064c5  jz      short loc_14010650F
0x1401064c7  mov     rcx, [rbx]; Thread
0x1401064ca  call    cs:__imp_PsGetThreadId
0x1401064d1  nop     dword ptr [rax+rax+00h]
0x1401064d6  cmp     rax, rsi
0x1401064d9  jnz     short loc_1401064FF
0x1401064db  xor     ecx, ecx
0x1401064dd  xor     eax, eax
0x1401064df  lock cmpxchg [rbx+208h], ecx
0x1401064e7  bt      eax, 18h
0x1401064eb  jnb     short loc_1401064FF
0x1401064ed  xor     eax, eax
0x1401064ef  lock cmpxchg [rbx+208h], ecx
0x1401064f7  test    al, 1
0x1401064f9  cmovnz  rbx, rcx
0x1401064fd  jmp     short loc_140106501
0x1401064ff  xor     ebx, ebx
0x140106501  mov     [rsp+38h+var_18], rbx
0x140106506  jmp     short loc_14010650F
0x140106508  xor     ebx, ebx
0x14010650a  mov     [rsp+38h+var_18], rbx
0x14010650f  mov     rcx, [rsp+38h+Thread]; Object
0x140106514  call    cs:__imp_ObfDereferenceObject
0x14010651b  nop     dword ptr [rax+rax+00h]
0x140106520  mov     rax, rbx
0x140106523  mov     rbx, [rsp+38h+arg_0]
0x140106528  mov     rsi, [rsp+38h+arg_10]
0x14010652d  add     rsp, 30h
0x140106531  pop     rdi
0x140106532  retn
0x140106534  mov     rcx, [rsp+38h+Thread]; Object
0x140106539  call    cs:__imp_ObfDereferenceObject
0x140106540  nop     dword ptr [rax+rax+00h]
0x140106545  xor     eax, eax
0x140106547  jmp     short loc_140106523
0x140239276  push    rbp
0x140239278  sub     rsp, 20h
0x14023927c  mov     rbp, rdx
0x14023927f  mov     eax, 1
0x140239284  add     rsp, 20h
0x140239288  pop     rbp
0x140239289  retn
```
