# CThreadPool::InitializeThreadPool(void)

- ea: `0x1800328d4`
- end: `0x180032956`
- name: `?InitializeThreadPool@CThreadPool@@QEAAKXZ`
- size: `130`
- prototype: `DWORD __fastcall(CThreadPool *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c308`

## callees

- `0x1800328d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003293f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180032929`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180032929`

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
0x1800328d4  push    rbx
0x1800328d6  sub     rsp, 20h
0x1800328da  mov     rbx, rcx
0x1800328dd  mov     dword ptr [rcx+8], 3
0x1800328e4  mov     qword ptr [rcx+10h], 0
0x1800328ec  mov     qword ptr [rcx+18h], 0
0x1800328f4  mov     qword ptr [rcx+20h], 0
0x1800328fc  mov     qword ptr [rcx+28h], 0
0x180032904  mov     qword ptr [rcx+30h], 0
0x18003290c  mov     qword ptr [rcx+38h], 0
0x180032914  mov     dword ptr [rcx+40h], 0
0x18003291b  mov     dword ptr [rcx+44h], 1
0x180032922  mov     dword ptr [rcx+48h], 48h ; 'H'
0x180032929  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18003292f  mov     [rbx], rax
0x180032932  mov     rcx, rax
0x180032935  test    rax, rax
0x180032938  jnz     short loc_180032946
0x18003293a  add     rsp, 20h
0x18003293e  pop     rbx
0x18003293f  jmp     cs:__imp_GetLastError
0x180032946  xor     eax, eax
0x180032948  mov     [rbx+18h], rcx
0x18003294c  mov     [rbx+20h], rax
0x180032950  add     rsp, 20h
0x180032954  pop     rbx
0x180032955  retn
```
