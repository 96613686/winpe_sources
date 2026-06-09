# CWinSATTaskMangerTask::TNThreadProcS(void *)

- ea: `0x1800211b0`
- end: `0x1800211f0`
- name: `?TNThreadProcS@CWinSATTaskMangerTask@@CAKPEAX@Z`
- size: `64`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180020dcc`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800211e9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800211e9`

## pseudocode

```c
void __fastcall __noreturn CWinSATTaskMangerTask::TNThreadProcS(CWinSATTaskMangerTask *Parameter)
{
  DWORD v2; // eax
  __int64 v3; // rdx
  DWORD v4; // edi
  HMODULE v5; // rbx

  v2 = CWinSATTaskMangerTask::TNThreadProc(Parameter);
  v3 = *(_QWORD *)Parameter;
  v4 = v2;
  v5 = (HMODULE)*((_QWORD *)Parameter + 12);
  *((_QWORD *)Parameter + 12) = 0;
  (*(void (__fastcall **)(CWinSATTaskMangerTask *))(v3 + 16))(Parameter);
  FreeLibraryAndExitThread(v5, v4);
}

```

## disassembly

```asm
0x1800211b0  mov     [rsp+arg_0], rbx
0x1800211b5  mov     [rsp+arg_8], rsi
0x1800211ba  push    rdi
0x1800211bb  sub     rsp, 20h
0x1800211bf  mov     rsi, rcx
0x1800211c2  call    ?TNThreadProc@CWinSATTaskMangerTask@@AEAAKXZ; CWinSATTaskMangerTask::TNThreadProc(void)
0x1800211c7  mov     rdx, [rsi]
0x1800211ca  mov     edi, eax
0x1800211cc  mov     rbx, [rsi+60h]
0x1800211d0  mov     rcx, rsi
0x1800211d3  mov     qword ptr [rsi+60h], 0
0x1800211db  mov     rax, [rdx+10h]
0x1800211df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211e4  mov     edx, edi; dwExitCode
0x1800211e6  mov     rcx, rbx; hLibModule
0x1800211e9  call    cs:__imp_FreeLibraryAndExitThread
```
