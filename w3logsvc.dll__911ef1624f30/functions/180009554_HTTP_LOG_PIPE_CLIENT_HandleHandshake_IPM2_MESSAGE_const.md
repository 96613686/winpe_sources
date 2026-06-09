# HTTP_LOG_PIPE_CLIENT::HandleHandshake(IPM2_MESSAGE const *)

- ea: `0x180009554`
- end: `0x1800095fd`
- name: `?HandleHandshake@HTTP_LOG_PIPE_CLIENT@@QEAAXPEBVIPM2_MESSAGE@@@Z`
- size: `169`
- prototype: `void __fastcall(HTTP_LOG_PIPE_CLIENT *__hidden this, const struct IPM2_MESSAGE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800090c0`

## callees

- `0x180009554`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095ec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800095e2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800095e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800095d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800095d5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800095b6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800095b6`

## pseudocode

```c
void __fastcall HTTP_LOG_PIPE_CLIENT::HandleHandshake(HTTP_LOG_PIPE_CLIENT *this, const struct IPM2_MESSAGE *a2)
{
  __int64 v4; // rax
  DWORD v5; // r8d
  HANDLE v6; // rax

  if ( *((_DWORD *)this + 38) )
  {
    *((_DWORD *)this + 39) = 0;
  }
  else
  {
    *((_DWORD *)this + 38) = *(_DWORD *)(*(__int64 (__fastcall **)(const struct IPM2_MESSAGE *))(*(_QWORD *)a2 + 32LL))(a2);
    v4 = (*(__int64 (__fastcall **)(const struct IPM2_MESSAGE *))(*(_QWORD *)a2 + 32LL))(a2);
    v5 = *((_DWORD *)this + 38);
    *((_DWORD *)this + 40) = *(_DWORD *)(v4 + 4);
    v6 = OpenProcess(0x100000u, 0, v5);
    *((_QWORD *)this + 21) = v6;
    if ( !v6 || (SetThreadpoolWait(*((PTP_WAIT *)this + 22), v6, 0), !SetEvent(*((HANDLE *)this + 24))) )
      GetLastError();
  }
}

```

## disassembly

```asm
0x180009554  mov     [rsp+arg_0], rbx
0x180009559  push    rdi
0x18000955a  sub     rsp, 20h
0x18000955e  cmp     dword ptr [rcx+98h], 0
0x180009565  mov     rdi, rdx
0x180009568  mov     rbx, rcx
0x18000956b  jz      short loc_180009579
0x18000956d  mov     dword ptr [rcx+9Ch], 0
0x180009577  jmp     short loc_1800095F2
0x180009579  mov     rax, [rdx]
0x18000957c  mov     rcx, rdi
0x18000957f  mov     rax, [rax+20h]
0x180009583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009588  mov     ecx, [rax]
0x18000958a  mov     [rbx+98h], ecx
0x180009590  mov     rcx, rdi
0x180009593  mov     rax, [rdi]
0x180009596  mov     rax, [rax+20h]
0x18000959a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000959f  mov     r8d, [rbx+98h]; dwProcessId
0x1800095a6  xor     edx, edx; bInheritHandle
0x1800095a8  mov     ecx, [rax+4]
0x1800095ab  mov     [rbx+0A0h], ecx
0x1800095b1  mov     ecx, 100000h; dwDesiredAccess
0x1800095b6  call    cs:__imp_OpenProcess
0x1800095bc  mov     [rbx+0A8h], rax
0x1800095c3  test    rax, rax
0x1800095c6  jz      short loc_1800095EC
0x1800095c8  mov     rcx, [rbx+0B0h]; pwa
0x1800095cf  xor     r8d, r8d; pftTimeout
0x1800095d2  mov     rdx, rax; h
0x1800095d5  call    cs:__imp_SetThreadpoolWait
0x1800095db  mov     rcx, [rbx+0C0h]; hEvent
0x1800095e2  call    cs:__imp_SetEvent
0x1800095e8  test    eax, eax
0x1800095ea  jnz     short loc_1800095F2
0x1800095ec  call    cs:__imp_GetLastError
0x1800095f2  mov     rbx, [rsp+28h+arg_0]
0x1800095f7  add     rsp, 20h
0x1800095fb  pop     rdi
0x1800095fc  retn
```
