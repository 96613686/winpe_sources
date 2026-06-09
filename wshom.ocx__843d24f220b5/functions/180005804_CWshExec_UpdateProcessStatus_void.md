# CWshExec::UpdateProcessStatus(void)

- ea: `0x180005804`
- end: `0x180005847`
- name: `?UpdateProcessStatus@CWshExec@@AEAAXXZ`
- size: `67`
- prototype: `void __fastcall(CWshExec *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800057c0`
- `0x180006f00`
- `0x180006fd0`

## callees

- `0x180005804`

## import_xrefs

- `KERNEL32!GetExitCodeProcess` at `0x180005825`
- `KERNEL32!GetExitCodeProcess` at `0x180005825`

## pseudocode

```c
void __fastcall CWshExec::UpdateProcessStatus(CWshExec *this)
{
  void *v2; // rcx
  DWORD ExitCode; // [rsp+30h] [rbp+8h] BYREF

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 29, 0, 0) )
  {
    v2 = (void *)*((_QWORD *)this + 13);
    ExitCode = 0;
    GetExitCodeProcess(v2, &ExitCode);
    if ( ExitCode != 259 )
    {
      _InterlockedExchange((volatile __int32 *)this + 29, 0);
      _InterlockedExchange((volatile __int32 *)this + 28, ExitCode);
    }
  }
}

```

## disassembly

```asm
0x180005804  push    rbx
0x180005806  sub     rsp, 20h
0x18000580a  xor     edx, edx
0x18000580c  mov     rbx, rcx
0x18000580f  xor     eax, eax
0x180005811  lock cmpxchg [rcx+74h], edx
0x180005816  jz      short loc_180005841
0x180005818  mov     rcx, [rcx+68h]; hProcess
0x18000581c  mov     [rsp+28h+ExitCode], edx
0x180005820  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x180005825  call    cs:__imp_GetExitCodeProcess
0x18000582b  cmp     [rsp+28h+ExitCode], 103h
0x180005833  jz      short loc_180005841
0x180005835  xor     eax, eax
0x180005837  xchg    eax, [rbx+74h]
0x18000583a  mov     eax, [rsp+28h+ExitCode]
0x18000583e  xchg    eax, [rbx+70h]
0x180005841  add     rsp, 20h
0x180005845  pop     rbx
0x180005846  retn
```
