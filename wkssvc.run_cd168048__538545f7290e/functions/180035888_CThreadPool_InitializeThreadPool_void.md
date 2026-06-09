# CThreadPool::InitializeThreadPool(void)

- ea: `0x180035888`
- end: `0x180035916`
- name: `?InitializeThreadPool@CThreadPool@@QEAAKXZ`
- size: `142`
- prototype: `unsigned int __fastcall(CThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ce14`

## callees

- `0x180035888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800358f9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800358dd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800358dd`

## pseudocode

```c
DWORD __fastcall CThreadPool::InitializeThreadPool(CThreadPool *this)
{
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  PTP_CLEANUP_GROUP v3; // rcx
  DWORD result; // eax

  *((_DWORD *)this + 2) = 3;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_DWORD *)this + 17) = 1;
  *((_DWORD *)this + 18) = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *(_QWORD *)this = ThreadpoolCleanupGroup;
  v3 = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
    return GetLastError();
  result = 0;
  *((_QWORD *)this + 3) = v3;
  *((_QWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180035888  push    rbx
0x18003588a  sub     rsp, 20h
0x18003588e  mov     rbx, rcx
0x180035891  mov     dword ptr [rcx+8], 3
0x180035898  mov     qword ptr [rcx+10h], 0
0x1800358a0  mov     qword ptr [rcx+18h], 0
0x1800358a8  mov     qword ptr [rcx+20h], 0
0x1800358b0  mov     qword ptr [rcx+28h], 0
0x1800358b8  mov     qword ptr [rcx+30h], 0
0x1800358c0  mov     qword ptr [rcx+38h], 0
0x1800358c8  mov     dword ptr [rcx+40h], 0
0x1800358cf  mov     dword ptr [rcx+44h], 1
0x1800358d6  mov     dword ptr [rcx+48h], 48h ; 'H'
0x1800358dd  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800358e4  nop     dword ptr [rax+rax+00h]
0x1800358e9  mov     [rbx], rax
0x1800358ec  mov     rcx, rax
0x1800358ef  test    rax, rax
0x1800358f2  jnz     short loc_180035905
0x1800358f4  add     rsp, 20h
0x1800358f8  pop     rbx
0x1800358f9  jmp     cs:__imp_GetLastError
0x180035905  xor     eax, eax
0x180035907  mov     [rbx+18h], rcx
0x18003590b  mov     [rbx+20h], rax
0x18003590f  add     rsp, 20h
0x180035913  pop     rbx
0x180035914  retn
```
