# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180003b70`
- end: `0x180003bdb`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003b70`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180003bc9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180003bc9`

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
0x180003b70  push    rbx
0x180003b72  push    rbp
0x180003b73  push    rsi
0x180003b74  push    rdi
0x180003b75  sub     rsp, 28h
0x180003b79  mov     rax, [rcx]
0x180003b7c  mov     rbx, rcx
0x180003b7f  mov     ebp, [rcx+10h]
0x180003b82  xor     esi, esi
0x180003b84  mov     rax, [rax+40h]
0x180003b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8d  mov     rcx, [rbx+30h]
0x180003b91  mov     edi, eax
0x180003b93  mov     rdx, [rcx]
0x180003b96  mov     rax, [rdx+20h]
0x180003b9a  mov     edx, edi
0x180003b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba1  test    ebp, ebp
0x180003ba3  jz      short loc_180003BB1
0x180003ba5  mov     rsi, [rbx+18h]
0x180003ba9  mov     qword ptr [rbx+18h], 0
0x180003bb1  mov     rax, [rbx]
0x180003bb4  mov     rcx, rbx
0x180003bb7  mov     rax, [rax+10h]
0x180003bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc0  test    ebp, ebp
0x180003bc2  jz      short loc_180003BD0
0x180003bc4  mov     edx, edi; dwExitCode
0x180003bc6  mov     rcx, rsi; hLibModule
0x180003bc9  call    cs:__imp_FreeLibraryAndExitThread
0x180003bcf  int     3; Trap to Debugger
0x180003bd0  mov     eax, edi
0x180003bd2  add     rsp, 28h
0x180003bd6  pop     rdi
0x180003bd7  pop     rsi
0x180003bd8  pop     rbp
0x180003bd9  pop     rbx
0x180003bda  retn
```
