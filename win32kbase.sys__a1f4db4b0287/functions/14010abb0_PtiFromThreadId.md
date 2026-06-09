# PtiFromThreadId

- ea: `0x14010abb0`
- end: `0x14010acd9`
- name: `PtiFromThreadId`
- size: `297`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14018b400`
- `0x1401d8350`
- `0x1401d8680`

## callees

- `0x14010abb0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14010abe4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010abe4`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14010ac3e`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14010ac3e`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14010abf3`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14010abf3`
- `ntoskrnl!PsGetThreadSessionId` at `0x14010ac06`
- `ntoskrnl!PsGetThreadSessionId` at `0x14010ac06`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x14010abd2`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x14010abd2`
- `ntoskrnl!PsIsThreadTerminating` at `0x14010ac27`
- `ntoskrnl!PsIsThreadTerminating` at `0x14010ac27`
- `ntoskrnl!ObfDereferenceObject` at `0x14010aca4`
- `ntoskrnl!ObfDereferenceObject` at `0x14010acc9`
- `ntoskrnl!ObfDereferenceObject` at `0x14010aca4`
- `ntoskrnl!ObfDereferenceObject` at `0x14010acc9`
- `ntoskrnl!PsGetThreadId` at `0x14010ac5a`
- `ntoskrnl!PsGetThreadId` at `0x14010ac5a`

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
0x14010abb0  mov     rax, rsp
0x14010abb3  mov     [rax+8], rbx
0x14010abb7  mov     [rax+18h], rsi
0x14010abbb  push    rdi
0x14010abbc  sub     rsp, 30h
0x14010abc0  mov     qword ptr [rax+10h], 0
0x14010abc8  movsxd  rsi, ecx
0x14010abcb  lea     rdx, [rax+10h]; Thread
0x14010abcf  mov     rcx, rsi; ThreadId
0x14010abd2  call    cs:__imp_PsLookupThreadByThreadId
0x14010abd9  nop     dword ptr [rax+rax+00h]
0x14010abde  mov     edi, eax
0x14010abe0  test    eax, eax
0x14010abe2  js      short loc_14010AC1A
0x14010abe4  call    cs:__imp_PsGetCurrentProcess
0x14010abeb  nop     dword ptr [rax+rax+00h]
0x14010abf0  mov     rcx, rax
0x14010abf3  call    cs:__imp_PsGetProcessSessionIdEx
0x14010abfa  nop     dword ptr [rax+rax+00h]
0x14010abff  mov     ebx, eax
0x14010ac01  mov     rcx, [rsp+38h+Thread]
0x14010ac06  call    cs:__imp_PsGetThreadSessionId
0x14010ac0d  nop     dword ptr [rax+rax+00h]
0x14010ac12  cmp     eax, ebx
0x14010ac14  jnz     loc_14010ACC4
0x14010ac1a  test    edi, edi
0x14010ac1c  js      loc_14010ACD5
0x14010ac22  mov     rcx, [rsp+38h+Thread]; Thread
0x14010ac27  call    cs:__imp_PsIsThreadTerminating
0x14010ac2e  nop     dword ptr [rax+rax+00h]
0x14010ac33  xor     ebx, ebx
0x14010ac35  test    al, al
0x14010ac37  jnz     short loc_14010AC9F
0x14010ac39  mov     rcx, [rsp+38h+Thread]
0x14010ac3e  call    cs:__imp_PsGetThreadWin32Thread
0x14010ac45  nop     dword ptr [rax+rax+00h]
0x14010ac4a  test    rax, rax
0x14010ac4d  jz      short loc_14010AC52
0x14010ac4f  mov     rbx, [rax]
0x14010ac52  test    rbx, rbx
0x14010ac55  jz      short loc_14010AC9F
0x14010ac57  mov     rcx, [rbx]; Thread
0x14010ac5a  call    cs:__imp_PsGetThreadId
0x14010ac61  nop     dword ptr [rax+rax+00h]
0x14010ac66  cmp     rax, rsi
0x14010ac69  jnz     short loc_14010AC8F
0x14010ac6b  xor     ecx, ecx
0x14010ac6d  xor     eax, eax
0x14010ac6f  lock cmpxchg [rbx+208h], ecx
0x14010ac77  bt      eax, 18h
0x14010ac7b  jnb     short loc_14010AC8F
0x14010ac7d  xor     eax, eax
0x14010ac7f  lock cmpxchg [rbx+208h], ecx
0x14010ac87  test    al, 1
0x14010ac89  cmovnz  rbx, rcx
0x14010ac8d  jmp     short loc_14010AC91
0x14010ac8f  xor     ebx, ebx
0x14010ac91  mov     [rsp+38h+var_18], rbx
0x14010ac96  jmp     short loc_14010AC9F
0x14010ac98  xor     ebx, ebx
0x14010ac9a  mov     [rsp+38h+var_18], rbx
0x14010ac9f  mov     rcx, [rsp+38h+Thread]; Object
0x14010aca4  call    cs:__imp_ObfDereferenceObject
0x14010acab  nop     dword ptr [rax+rax+00h]
0x14010acb0  mov     rax, rbx
0x14010acb3  mov     rbx, [rsp+38h+arg_0]
0x14010acb8  mov     rsi, [rsp+38h+arg_10]
0x14010acbd  add     rsp, 30h
0x14010acc1  pop     rdi
0x14010acc2  retn
0x14010acc4  mov     rcx, [rsp+38h+Thread]; Object
0x14010acc9  call    cs:__imp_ObfDereferenceObject
0x14010acd0  nop     dword ptr [rax+rax+00h]
0x14010acd5  xor     eax, eax
0x14010acd7  jmp     short loc_14010ACB3
0x140239c1b  push    rbp
0x140239c1d  sub     rsp, 20h
0x140239c21  mov     rbp, rdx
0x140239c24  mov     eax, 1
0x140239c29  add     rsp, 20h
0x140239c2d  pop     rbp
0x140239c2e  retn
```
