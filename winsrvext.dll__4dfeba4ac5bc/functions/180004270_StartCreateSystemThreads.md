# StartCreateSystemThreads

- ea: `0x180004270`
- end: `0x1800042e9`
- name: `StartCreateSystemThreads`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004270`

## import_xrefs

- `ntdll!RtlExitUserThread` at `0x1800042d5`
- `ntdll!RtlExitUserThread` at `0x1800042d5`
- `ntdll!NtSetInformationThread` at `0x180004294`
- `ntdll!NtSetInformationThread` at `0x180004294`
- `CSRSRV!CsrDereferenceThread` at `0x1800042c7`
- `CSRSRV!CsrDereferenceThread` at `0x1800042c7`
- `CSRSRV!CsrConnectToUser` at `0x1800042a4`
- `CSRSRV!CsrConnectToUser` at `0x1800042a4`
- `win32u!NtUserCreateSystemThreads` at `0x1800042b3`
- `win32u!NtUserCreateSystemThreads` at `0x1800042b3`

## pseudocode

```c
void StartCreateSystemThreads()
{
  __int64 v0; // rbx
  int ThreadInformation; // [rsp+38h] [rbp+10h] BYREF

  ThreadInformation = 1;
  if ( NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadLastSystemCall|0x20, &ThreadInformation, 4u) >= 0 )
  {
    v0 = CsrConnectToUser();
    NtUserCreateSystemThreads();
    if ( v0 )
      CsrDereferenceThread(v0);
    RtlExitUserThread(0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180004270  push    rbx
0x180004272  sub     rsp, 20h
0x180004276  mov     r9d, 4; ThreadInformationLength
0x18000427c  mov     [rsp+28h+ThreadInformation], 1
0x180004284  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x180004289  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180004290  lea     edx, [r9+31h]; ThreadInformationClass
0x180004294  call    cs:__imp_NtSetInformationThread
0x18000429b  nop     dword ptr [rax+rax+00h]
0x1800042a0  test    eax, eax
0x1800042a2  js      short loc_1800042E2
0x1800042a4  call    cs:__imp_CsrConnectToUser
0x1800042ab  nop     dword ptr [rax+rax+00h]
0x1800042b0  mov     rbx, rax
0x1800042b3  call    cs:__imp_NtUserCreateSystemThreads
0x1800042ba  nop     dword ptr [rax+rax+00h]
0x1800042bf  test    rbx, rbx
0x1800042c2  jz      short loc_1800042D3
0x1800042c4  mov     rcx, rbx
0x1800042c7  call    cs:__imp_CsrDereferenceThread
0x1800042ce  nop     dword ptr [rax+rax+00h]
0x1800042d3  xor     ecx, ecx; Status
0x1800042d5  call    cs:__imp_RtlExitUserThread
0x1800042dc  nop     dword ptr [rax+rax+00h]
0x1800042e1  int     3; Trap to Debugger
0x1800042e2  add     rsp, 20h
0x1800042e6  pop     rbx
0x1800042e7  retn
```
