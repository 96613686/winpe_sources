# GmoMigrationMemoryWalkerWorker::RunInitialize(void)

- ea: `0x14023c740`
- end: `0x14023c81d`
- name: `?RunInitialize@GmoMigrationMemoryWalkerWorker@@MEAAXXZ`
- size: `221`
- prototype: `void __fastcall(GmoMigrationMemoryWalkerWorker *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400364a0`
- `0x1400544a8`
- `0x140102580`
- `0x14011ea40`
- `0x14023c740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14023c7af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14023c7af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14023c775`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14023c775`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x14023c78c`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x14023c78c`

## pseudocode

```c
void __fastcall GmoMigrationMemoryWalkerWorker::RunInitialize(GmoMigrationMemoryWalkerWorker *this)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  GROUP_AFFINITY GroupAffinity; // [rsp+30h] [rbp-28h] BYREF

  GroupAffinity = *(GROUP_AFFINITY *)(*((_QWORD *)this + 35) + 160LL);
  if ( GroupAffinity.Mask )
  {
    CurrentThread = GetCurrentThread();
    if ( !SetThreadGroupAffinity(CurrentThread, &GroupAffinity, 0) )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
      {
        LastError = GetLastError();
        VmlDebugTraceWithError(16866, &off_1402E4B98, LastError);
      }
    }
  }
  else if ( (unsigned int)VmlIsDebugTraceEnabled(33250) )
  {
    VmlDebugTraceEx(33250, &off_1402E4B80);
  }
}

```

## disassembly

```asm
0x14023c740  push    rbx
0x14023c742  sub     rsp, 50h
0x14023c746  mov     rax, cs:__security_cookie
0x14023c74d  xor     rax, rsp
0x14023c750  mov     [rsp+58h+var_18], rax
0x14023c755  mov     rax, [rcx+118h]
0x14023c75c  mov     rbx, rcx
0x14023c75f  movups  xmm0, xmmword ptr [rax+0A0h]
0x14023c766  movq    rax, xmm0
0x14023c76b  movups  xmmword ptr [rsp+58h+GroupAffinity.Mask], xmm0
0x14023c770  test    rax, rax
0x14023c773  jz      short loc_14023C7DE
0x14023c775  call    cs:__imp_GetCurrentThread
0x14023c77c  nop     dword ptr [rax+rax+00h]
0x14023c781  xor     r8d, r8d; PreviousGroupAffinity
0x14023c784  lea     rdx, [rsp+58h+GroupAffinity]; GroupAffinity
0x14023c789  mov     rcx, rax; hThread
0x14023c78c  call    cs:__imp_SetThreadGroupAffinity
0x14023c793  nop     dword ptr [rax+rax+00h]
0x14023c798  test    eax, eax
0x14023c79a  jnz     short loc_14023C809
0x14023c79c  mov     ecx, 41E2h
0x14023c7a1  call    VmlIsDebugTraceEnabled
0x14023c7a6  test    eax, eax
0x14023c7a8  jz      short loc_14023C809
0x14023c7aa  movzx   ebx, [rsp+58h+GroupAffinity.Group]
0x14023c7af  call    cs:__imp_GetLastError
0x14023c7b6  nop     dword ptr [rax+rax+00h]
0x14023c7bb  mov     r9d, ebx
0x14023c7be  lea     rdx, off_1402E4B98; "Failed to set thread affinity group:0x'"...
0x14023c7c5  mov     r8d, eax
0x14023c7c8  mov     ecx, 41E2h
0x14023c7cd  mov     rax, [rsp+58h+GroupAffinity.Mask]
0x14023c7d2  mov     [rsp+58h+var_38], rax
0x14023c7d7  call    VmlDebugTraceWithError
0x14023c7dc  jmp     short loc_14023C809
0x14023c7de  mov     ecx, 81E2h
0x14023c7e3  call    VmlIsDebugTraceEnabled
0x14023c7e8  test    eax, eax
0x14023c7ea  jz      short loc_14023C809
0x14023c7ec  mov     rax, [rbx+118h]
0x14023c7f3  lea     rdx, off_1402E4B80; "Found CPU less NUMA node '%u'."
0x14023c7fa  mov     ecx, 81E2h
0x14023c7ff  movzx   r8d, byte ptr [rax+78h]
0x14023c804  call    VmlDebugTraceEx
0x14023c809  mov     rcx, [rsp+58h+var_18]
0x14023c80e  xor     rcx, rsp; StackCookie
0x14023c811  call    __security_check_cookie
0x14023c816  add     rsp, 50h
0x14023c81a  pop     rbx
0x14023c81b  retn
```
