# WinSAT::MemAssessment1::WaitForCompletion(ulong)

- ea: `0x14005fd40`
- end: `0x14005fdb8`
- name: `?WaitForCompletion@MemAssessment1@WinSAT@@UEAAKK@Z`
- size: `120`
- prototype: `unsigned int __fastcall(WinSAT::MemAssessment1 *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14005fd40`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x14005fd8b`
- `KERNEL32!GetCurrentThread` at `0x14005fd8b`
- `KERNEL32!WaitForSingleObject` at `0x14005fd61`
- `KERNEL32!WaitForSingleObject` at `0x14005fd61`
- `KERNEL32!SetThreadPriority` at `0x14005fd96`
- `KERNEL32!SetThreadPriority` at `0x14005fd96`
- `KERNEL32!GetCurrentProcess` at `0x14005fd7a`
- `KERNEL32!GetCurrentProcess` at `0x14005fd7a`
- `KERNEL32!SetPriorityClass` at `0x14005fd85`
- `KERNEL32!SetPriorityClass` at `0x14005fd85`
- `KERNEL32!SetLastError` at `0x14005fda5`
- `KERNEL32!SetLastError` at `0x14005fda5`

## pseudocode

```c
__int64 __fastcall WinSAT::MemAssessment1::WaitForCompletion(HANDLE *this, DWORD a2)
{
  DWORD v3; // edi
  DWORD v4; // ebx
  HANDLE CurrentProcess; // rax
  HANDLE CurrentThread; // rax

  if ( this[10] && *((_DWORD *)this + 14) == 4 )
  {
    v3 = WaitForSingleObject(this[81], a2);
    if ( v3 )
      *((_BYTE *)this + 738) = 1;
    v4 = *((_DWORD *)this + 181);
    CurrentProcess = GetCurrentProcess();
    SetPriorityClass(CurrentProcess, v4);
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 0);
    return v3;
  }
  else
  {
    SetLastError(0xFFFFFFFF);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x14005fd40  mov     [rsp+arg_0], rbx
0x14005fd45  push    rdi
0x14005fd46  sub     rsp, 20h
0x14005fd4a  cmp     qword ptr [rcx+50h], 0
0x14005fd4f  mov     rbx, rcx
0x14005fd52  jz      short loc_14005FDA0
0x14005fd54  cmp     dword ptr [rcx+38h], 4
0x14005fd58  jnz     short loc_14005FDA0
0x14005fd5a  mov     rcx, [rcx+288h]; hHandle
0x14005fd61  call    cs:__imp_WaitForSingleObject
0x14005fd67  mov     edi, eax
0x14005fd69  test    eax, eax
0x14005fd6b  jz      short loc_14005FD74
0x14005fd6d  mov     byte ptr [rbx+2E2h], 1
0x14005fd74  mov     ebx, [rbx+2D4h]
0x14005fd7a  call    cs:__imp_GetCurrentProcess
0x14005fd80  mov     rcx, rax; hProcess
0x14005fd83  mov     edx, ebx; dwPriorityClass
0x14005fd85  call    cs:__imp_SetPriorityClass
0x14005fd8b  call    cs:__imp_GetCurrentThread
0x14005fd91  mov     rcx, rax; hThread
0x14005fd94  xor     edx, edx; nPriority
0x14005fd96  call    cs:__imp_SetThreadPriority
0x14005fd9c  mov     eax, edi
0x14005fd9e  jmp     short loc_14005FDAD
0x14005fda0  or      ebx, 0FFFFFFFFh
0x14005fda3  mov     ecx, ebx; dwErrCode
0x14005fda5  call    cs:__imp_SetLastError
0x14005fdab  mov     eax, ebx
0x14005fdad  mov     rbx, [rsp+28h+arg_0]
0x14005fdb2  add     rsp, 20h
0x14005fdb6  pop     rdi
0x14005fdb7  retn
```
