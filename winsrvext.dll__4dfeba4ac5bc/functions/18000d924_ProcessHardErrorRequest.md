# ProcessHardErrorRequest

- ea: `0x18000d924`
- end: `0x18000da73`
- name: `ProcessHardErrorRequest`
- size: `335`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d6f0`
- `0x18000dda0`

## callees

- `0x18000d030`
- `0x18000d924`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000d968`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d99a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000da4f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d968`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d99a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000da4f`
- `ntdll!NtResumeThread` at `0x18000da1d`
- `ntdll!NtResumeThread` at `0x18000da1d`
- `ntdll!RtlCreateUserThread` at `0x18000d9ed`
- `ntdll!RtlCreateUserThread` at `0x18000d9ed`
- `ntdll!RtlEnterCriticalSection` at `0x18000d94f`
- `ntdll!RtlEnterCriticalSection` at `0x18000da2e`
- `ntdll!RtlEnterCriticalSection` at `0x18000d94f`
- `ntdll!RtlEnterCriticalSection` at `0x18000da2e`
- `CSRSRV!CsrAddStaticServerThread` at `0x18000da0a`
- `CSRSRV!CsrAddStaticServerThread` at `0x18000da0a`
- `USER32!PostThreadMessageW` at `0x18000d97e`
- `USER32!PostThreadMessageW` at `0x18000d97e`

## pseudocode

```c
NTSTATUS __fastcall ProcessHardErrorRequest(int a1)
{
  DWORD v2; // ebx
  PVOID v4; // r8
  __int128 Reserved8; // [rsp+50h] [rbp-18h] BYREF
  HANDLE ThreadHandle; // [rsp+78h] [rbp+10h] BYREF

  ThreadHandle = 0;
  Reserved8 = 0;
  RtlEnterCriticalSection(&gcsUserSrv);
  v2 = gdwHardErrorThreadId;
  if ( gdwHardErrorThreadId )
  {
    RtlLeaveCriticalSection(&gcsUserSrv);
    return PostThreadMessageW(v2, 0, 0, 0);
  }
  if ( a1 )
  {
    RtlLeaveCriticalSection(&gcsUserSrv);
    LOBYTE(v4) = 1;
    if ( RtlCreateUserThread(
           (PVOID)0xFFFFFFFFFFFFFFFFLL,
           0,
           v4,
           0,
           0,
           0,
           HardErrorWorkerThread,
           0,
           &ThreadHandle,
           &Reserved8) >= 0 )
    {
      CsrAddStaticServerThread(ThreadHandle, &Reserved8, 0);
      return NtResumeThread(ThreadHandle, 0);
    }
    RtlEnterCriticalSection(&gcsUserSrv);
  }
  gdwHardErrorThreadId = (DWORD)NtCurrentTeb()->ClientId.UniqueThread;
  RtlLeaveCriticalSection(&gcsUserSrv);
  return HardErrorHandler();
}

```

## disassembly

```asm
0x18000d924  mov     rax, rsp
0x18000d927  mov     [rax+8], rbx
0x18000d92b  mov     [rax+18h], rbp
0x18000d92f  push    rdi
0x18000d930  sub     rsp, 60h
0x18000d934  mov     edi, ecx
0x18000d936  mov     qword ptr [rax+10h], 0
0x18000d93e  xorps   xmm0, xmm0
0x18000d941  lea     rbp, gcsUserSrv
0x18000d948  mov     rcx, rbp; CriticalSection
0x18000d94b  movups  xmmword ptr [rax-18h], xmm0
0x18000d94f  call    cs:__imp_RtlEnterCriticalSection
0x18000d956  nop     dword ptr [rax+rax+00h]
0x18000d95b  mov     ebx, cs:gdwHardErrorThreadId
0x18000d961  test    ebx, ebx
0x18000d963  jz      short loc_18000D98F
0x18000d965  mov     rcx, rbp; CriticalSection
0x18000d968  call    cs:__imp_RtlLeaveCriticalSection
0x18000d96f  nop     dword ptr [rax+rax+00h]
0x18000d974  xor     r9d, r9d; lParam
0x18000d977  xor     r8d, r8d; wParam
0x18000d97a  xor     edx, edx; Msg
0x18000d97c  mov     ecx, ebx; idThread
0x18000d97e  call    cs:__imp_PostThreadMessageW
0x18000d985  nop     dword ptr [rax+rax+00h]
0x18000d98a  jmp     loc_18000DA60
0x18000d98f  test    edi, edi
0x18000d991  jz      loc_18000DA3A
0x18000d997  mov     rcx, rbp; CriticalSection
0x18000d99a  call    cs:__imp_RtlLeaveCriticalSection
0x18000d9a1  nop     dword ptr [rax+rax+00h]
0x18000d9a6  lea     rax, [rsp+68h+var_18]
0x18000d9ab  xor     r9d, r9d; Reserved2
0x18000d9ae  mov     [rsp+68h+Reserved8], rax; Reserved8
0x18000d9b3  mov     r8b, 1; Reserved1
0x18000d9b6  lea     rax, [rsp+68h+ThreadHandle]
0x18000d9bb  xor     edx, edx; OutThreadHandle
0x18000d9bd  mov     [rsp+68h+Reserved7], rax; Reserved7
0x18000d9c2  or      rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x18000d9c6  mov     [rsp+68h+Reserved6], 0; Reserved6
0x18000d9cf  lea     rax, HardErrorWorkerThread
0x18000d9d6  mov     [rsp+68h+Reserved5], rax; Reserved5
0x18000d9db  mov     [rsp+68h+Reserved4], 0; Reserved4
0x18000d9e4  mov     [rsp+68h+Reserved3], 0; Reserved3
0x18000d9ed  call    cs:__imp_RtlCreateUserThread
0x18000d9f4  nop     dword ptr [rax+rax+00h]
0x18000d9f9  test    eax, eax
0x18000d9fb  js      short loc_18000DA2B
0x18000d9fd  mov     rcx, [rsp+68h+ThreadHandle]
0x18000da02  lea     rdx, [rsp+68h+var_18]
0x18000da07  xor     r8d, r8d
0x18000da0a  call    cs:__imp_CsrAddStaticServerThread
0x18000da11  nop     dword ptr [rax+rax+00h]
0x18000da16  mov     rcx, [rsp+68h+ThreadHandle]; ThreadHandle
0x18000da1b  xor     edx, edx; SuspendCount
0x18000da1d  call    cs:__imp_NtResumeThread
0x18000da24  nop     dword ptr [rax+rax+00h]
0x18000da29  jmp     short loc_18000DA60
0x18000da2b  mov     rcx, rbp; CriticalSection
0x18000da2e  call    cs:__imp_RtlEnterCriticalSection
0x18000da35  nop     dword ptr [rax+rax+00h]
0x18000da3a  mov     rax, gs:30h
0x18000da43  mov     ecx, [rax+48h]
0x18000da46  mov     cs:gdwHardErrorThreadId, ecx
0x18000da4c  mov     rcx, rbp; CriticalSection
0x18000da4f  call    cs:__imp_RtlLeaveCriticalSection
0x18000da56  nop     dword ptr [rax+rax+00h]
0x18000da5b  call    HardErrorHandler
0x18000da60  lea     r11, [rsp+68h+var_8]
0x18000da65  mov     rbx, [r11+10h]
0x18000da69  mov     rbp, [r11+20h]
0x18000da6d  mov     rsp, r11
0x18000da70  pop     rdi
0x18000da71  retn
```
