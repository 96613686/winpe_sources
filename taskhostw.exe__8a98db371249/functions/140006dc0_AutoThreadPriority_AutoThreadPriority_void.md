# AutoThreadPriority::~AutoThreadPriority(void)

- ea: `0x140006dc0`
- end: `0x140006ded`
- name: `??1AutoThreadPriority@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(AutoThreadPriority *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ad10`
- `0x14000ad90`

## callees

- `0x140006dc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140006dd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140006dd0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140006de0`

## pseudocode

```c
void __fastcall AutoThreadPriority::~AutoThreadPriority(AutoThreadPriority *this)
{
  int v1; // ebx
  HANDLE CurrentThread; // rax

  v1 = *(_DWORD *)this;
  if ( *(_DWORD *)this != 0x7FFFFFFF )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, v1);
  }
}

```

## disassembly

```asm
0x140006dc0  push    rbx
0x140006dc2  sub     rsp, 20h
0x140006dc6  mov     ebx, [rcx]
0x140006dc8  cmp     ebx, 7FFFFFFFh
0x140006dce  jz      short loc_140006DE7
0x140006dd0  call    cs:__imp_GetCurrentThread
0x140006dd6  mov     rcx, rax
0x140006dd9  mov     edx, ebx
0x140006ddb  add     rsp, 20h
0x140006ddf  pop     rbx
0x140006de0  jmp     cs:__imp_SetThreadPriority
0x140006de7  add     rsp, 20h
0x140006deb  pop     rbx
0x140006dec  retn
```
