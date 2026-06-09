# ComTaskMgrWnd::CreateShutdownTasksThread(void)

- ea: `0x1400096c4`
- end: `0x14000971b`
- name: `?CreateShutdownTasksThread@ComTaskMgrWnd@@AEAAJXZ`
- size: `87`
- prototype: `__int64 __fastcall(ComTaskMgrWnd *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003880`

## callees

- `0x1400096c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400096ea`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400096ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400096f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400096f9`

## pseudocode

```c
__int64 __fastcall ComTaskMgrWnd::CreateShutdownTasksThread(ComTaskMgrWnd *this)
{
  unsigned int v1; // edi
  HANDLE Thread; // rax
  signed int LastError; // eax

  v1 = 0;
  Thread = CreateThread(0, 0, ComTaskMgrWnd::ShutdownTasksThreadProc, 0, 0, 0);
  *((_QWORD *)this + 8) = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x1400096c4  mov     [rsp+arg_0], rbx
0x1400096c9  push    rdi
0x1400096ca  sub     rsp, 30h
0x1400096ce  xor     edi, edi
0x1400096d0  lea     r8, ?ShutdownTasksThreadProc@ComTaskMgrWnd@@CAKPEAX@Z; lpStartAddress
0x1400096d7  mov     rbx, rcx
0x1400096da  mov     [rsp+38h+lpThreadId], rdi; lpThreadId
0x1400096df  xor     r9d, r9d; lpParameter
0x1400096e2  mov     [rsp+38h+dwCreationFlags], edi; dwCreationFlags
0x1400096e6  xor     edx, edx; dwStackSize
0x1400096e8  xor     ecx, ecx; lpThreadAttributes
0x1400096ea  call    cs:__imp_CreateThread
0x1400096f0  mov     [rbx+40h], rax
0x1400096f4  test    rax, rax
0x1400096f7  jnz     short loc_14000970E
0x1400096f9  call    cs:__imp_GetLastError
0x1400096ff  mov     edi, eax
0x140009701  test    eax, eax
0x140009703  jle     short loc_14000970E
0x140009705  movzx   edi, ax
0x140009708  or      edi, 80070000h
0x14000970e  mov     rbx, [rsp+38h+arg_0]
0x140009713  mov     eax, edi
0x140009715  add     rsp, 30h
0x140009719  pop     rdi
0x14000971a  retn
```
