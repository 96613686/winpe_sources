# CFciPropertiesShellExt::EndBackgroundThread(ulong,bool)

- ea: `0x180007cc0`
- end: `0x180007d3e`
- name: `?EndBackgroundThread@CFciPropertiesShellExt@@AEAA_NK_N@Z`
- size: `126`
- prototype: `char __fastcall(CFciPropertiesShellExt *this, DWORD, char)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005fa0`

## callees

- `0x180007cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007cf8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007cf8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007ce9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007ce9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180007d0e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180007d0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d20`

## pseudocode

```c
char __fastcall CFciPropertiesShellExt::EndBackgroundThread(CFciPropertiesShellExt *this, DWORD a2, char a3)
{
  void *v6; // rcx

  if ( !*((_QWORD *)this + 17) )
    return 0;
  if ( a3 )
    SetEvent(*((HANDLE *)this + 19));
  if ( WaitForSingleObject(*((HANDLE *)this + 17), a2) )
    TerminateThread(*((HANDLE *)this + 17), 0x80004005);
  v6 = (void *)*((_QWORD *)this + 17);
  if ( v6 )
    CloseHandle(v6);
  *((_QWORD *)this + 17) = 0;
  return 1;
}

```

## disassembly

```asm
0x180007cc0  mov     [rsp+arg_0], rbx
0x180007cc5  push    rdi
0x180007cc6  sub     rsp, 20h
0x180007cca  cmp     qword ptr [rcx+88h], 0
0x180007cd2  mov     edi, edx
0x180007cd4  mov     rbx, rcx
0x180007cd7  jnz     short loc_180007CDD
0x180007cd9  xor     al, al
0x180007cdb  jmp     short loc_180007D33
0x180007cdd  test    r8b, r8b
0x180007ce0  jz      short loc_180007CEF
0x180007ce2  mov     rcx, [rcx+98h]; hEvent
0x180007ce9  call    cs:__imp_SetEvent
0x180007cef  mov     rcx, [rbx+88h]; hHandle
0x180007cf6  mov     edx, edi; dwMilliseconds
0x180007cf8  call    cs:__imp_WaitForSingleObject
0x180007cfe  test    eax, eax
0x180007d00  jz      short loc_180007D14
0x180007d02  mov     rcx, [rbx+88h]; hThread
0x180007d09  mov     edx, 80004005h; dwExitCode
0x180007d0e  call    cs:__imp_TerminateThread
0x180007d14  mov     rcx, [rbx+88h]; hObject
0x180007d1b  test    rcx, rcx
0x180007d1e  jz      short loc_180007D26
0x180007d20  call    cs:__imp_CloseHandle
0x180007d26  mov     qword ptr [rbx+88h], 0
0x180007d31  mov     al, 1
0x180007d33  mov     rbx, [rsp+28h+arg_0]
0x180007d38  add     rsp, 20h
0x180007d3c  pop     rdi
0x180007d3d  retn
```
