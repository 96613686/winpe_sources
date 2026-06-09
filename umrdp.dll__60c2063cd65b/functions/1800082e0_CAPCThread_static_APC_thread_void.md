# CAPCThread::static_APC_thread(void *)

- ea: `0x1800082e0`
- end: `0x18000832f`
- name: `?static_APC_thread@CAPCThread@@SAKPEAX@Z`
- size: `79`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800082e0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000831d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000831d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008310`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008310`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180008328`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180008328`

## pseudocode

```c
void __fastcall __noreturn CAPCThread::static_APC_thread(_QWORD *Parameter)
{
  void *v1; // rbx
  HMODULE v2; // rdi

  v1 = (void *)Parameter[8];
  v2 = (HMODULE)Parameter[9];
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Parameter[5] + 16LL))(Parameter[5]);
  while ( WaitForSingleObjectEx(v1, 0xFFFFFFFF, 1) )
    ;
  CloseHandle(v1);
  FreeLibraryAndExitThread(v2, 0);
}

```

## disassembly

```asm
0x1800082e0  mov     [rsp+arg_0], rbx
0x1800082e5  push    rdi
0x1800082e6  sub     rsp, 20h
0x1800082ea  mov     rbx, [rcx+40h]
0x1800082ee  mov     rdi, [rcx+48h]
0x1800082f2  mov     rcx, [rcx+28h]
0x1800082f6  mov     rax, [rcx]
0x1800082f9  mov     rax, [rax+10h]
0x1800082fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008302  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180008307  mov     r8d, 1; bAlertable
0x18000830d  mov     rcx, rbx; hHandle
0x180008310  call    cs:__imp_WaitForSingleObjectEx
0x180008316  test    eax, eax
0x180008318  jnz     short loc_180008302
0x18000831a  mov     rcx, rbx; hObject
0x18000831d  call    cs:__imp_CloseHandle
0x180008323  xor     edx, edx; dwExitCode
0x180008325  mov     rcx, rdi; hLibModule
0x180008328  call    cs:__imp_FreeLibraryAndExitThread
```
