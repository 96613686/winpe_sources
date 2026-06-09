# SrvCreateSystemThreads

- ea: `0x180004120`
- end: `0x180004156`
- name: `SrvCreateSystemThreads`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004120`

## import_xrefs

- `CSRSRV!CsrExecServerThread` at `0x18000412f`
- `CSRSRV!CsrExecServerThread` at `0x18000412f`
- `win32u!NtUserHandleSystemThreadCreationFailure` at `0x180004141`
- `win32u!NtUserHandleSystemThreadCreationFailure` at `0x180004141`

## pseudocode

```c
__int64 SrvCreateSystemThreads()
{
  int v0; // ebx

  v0 = CsrExecServerThread(StartCreateSystemThreads, 0);
  if ( v0 < 0 )
    NtUserHandleSystemThreadCreationFailure();
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180004120  push    rbx
0x180004122  sub     rsp, 20h
0x180004126  xor     edx, edx
0x180004128  lea     rcx, StartCreateSystemThreads
0x18000412f  call    cs:__imp_CsrExecServerThread
0x180004136  nop     dword ptr [rax+rax+00h]
0x18000413b  mov     ebx, eax
0x18000413d  test    eax, eax
0x18000413f  jns     short loc_18000414D
0x180004141  call    cs:__imp_NtUserHandleSystemThreadCreationFailure
0x180004148  nop     dword ptr [rax+rax+00h]
0x18000414d  mov     eax, ebx
0x18000414f  add     rsp, 20h
0x180004153  pop     rbx
0x180004154  retn
```
