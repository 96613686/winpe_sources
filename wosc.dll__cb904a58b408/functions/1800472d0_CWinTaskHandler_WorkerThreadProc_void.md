# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x1800472d0`
- end: `0x18004733b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800472d0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180047329`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180047329`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::WorkerThreadProc(_DWORD *Parameter)
{
  int v2; // ebp
  HMODULE v3; // rsi
  __int64 v4; // rdi

  v2 = Parameter[4];
  v3 = 0;
  v4 = (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 64LL))(Parameter);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)Parameter + 6) + 32LL))(*((_QWORD *)Parameter + 6), v4);
  if ( v2 )
  {
    v3 = (HMODULE)*((_QWORD *)Parameter + 3);
    *((_QWORD *)Parameter + 3) = 0;
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  if ( v2 )
    FreeLibraryAndExitThread(v3, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800472d0  push    rbx
0x1800472d2  push    rbp
0x1800472d3  push    rsi
0x1800472d4  push    rdi
0x1800472d5  sub     rsp, 28h
0x1800472d9  mov     rax, [rcx]
0x1800472dc  mov     rbx, rcx
0x1800472df  mov     ebp, [rcx+10h]
0x1800472e2  xor     esi, esi
0x1800472e4  mov     rax, [rax+40h]
0x1800472e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472ed  mov     rcx, [rbx+30h]
0x1800472f1  mov     edi, eax
0x1800472f3  mov     rdx, [rcx]
0x1800472f6  mov     rax, [rdx+20h]
0x1800472fa  mov     edx, edi
0x1800472fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047301  test    ebp, ebp
0x180047303  jz      short loc_180047311
0x180047305  mov     rsi, [rbx+18h]
0x180047309  mov     qword ptr [rbx+18h], 0
0x180047311  mov     rax, [rbx]
0x180047314  mov     rcx, rbx
0x180047317  mov     rax, [rax+10h]
0x18004731b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047320  test    ebp, ebp
0x180047322  jz      short loc_180047330
0x180047324  mov     edx, edi; dwExitCode
0x180047326  mov     rcx, rsi; hLibModule
0x180047329  call    cs:__imp_FreeLibraryAndExitThread
0x18004732f  int     3; Trap to Debugger
0x180047330  mov     eax, edi
0x180047332  add     rsp, 28h
0x180047336  pop     rdi
0x180047337  pop     rsi
0x180047338  pop     rbp
0x180047339  pop     rbx
0x18004733a  retn
```
