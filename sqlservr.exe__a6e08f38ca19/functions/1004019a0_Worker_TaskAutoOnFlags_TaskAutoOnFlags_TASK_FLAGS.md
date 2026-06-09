# Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)

- ea: `0x1004019a0`
- end: `0x100401a15`
- name: `??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z`
- size: `117`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x100401350`
- `0x10040d5d0`
- `0x1004119c0`
- `0x1004219e0`
- `0x100421c40`
- `0x10043a840`
- `0x10043b680`

## callees

- `0x1004019a0`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100409bf8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100409bf8`
- `sqldk!SystemThread_TlsOffset` at `0x1004019cb`
- `sqldk!SystemThread_TlsIndex` at `0x1004019c1`

## pseudocode

```c
int *__fastcall Worker::TaskAutoOnFlags::TaskAutoOnFlags(int *a1, int a2)
{
  int v4; // ecx
  __int64 v5; // rdi
  __int64 v6; // r8
  int *result; // rax

  v4 = 0;
  *a1 = 0;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v6 = *(_QWORD *)(v5 + 256);
  if ( !v6 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v6 = *(_QWORD *)(v5 + 256);
    v4 = *a1;
  }
  *((_QWORD *)a1 + 1) = v6;
  *a1 = v4 | a2 & ~*(_DWORD *)(v6 + 616);
  result = a1;
  *(_DWORD *)(v6 + 616) |= a2;
  return result;
}

```

## disassembly

```asm
0x1004019a0  mov     [rsp+arg_0], rbx
0x1004019a5  mov     [rsp+arg_8], rsi
0x1004019aa  push    rdi
0x1004019ab  sub     rsp, 20h
0x1004019af  mov     rbx, rcx
0x1004019b2  mov     esi, edx
0x1004019b4  xor     ecx, ecx
0x1004019b6  mov     [rbx], ecx
0x1004019b8  mov     r9, gs:58h
0x1004019c1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004019c8  mov     r8d, [rax]
0x1004019cb  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004019d2  mov     edi, [rax]
0x1004019d4  add     rdi, [r9+r8*8]
0x1004019d8  mov     r8, [rdi+100h]
0x1004019df  test    r8, r8
0x1004019e2  jz      loc_100409BF8
0x1004019e8  mov     [rbx+8], r8
0x1004019ec  mov     eax, [r8+268h]
0x1004019f3  not     eax
0x1004019f5  and     eax, esi
0x1004019f7  or      eax, ecx
0x1004019f9  mov     [rbx], eax
0x1004019fb  mov     rax, rbx
0x1004019fe  or      [r8+268h], esi
0x100401a05  mov     rbx, [rsp+28h+arg_0]
0x100401a0a  mov     rsi, [rsp+28h+arg_8]
0x100401a0f  add     rsp, 20h
0x100401a13  pop     rdi
0x100401a14  retn
0x100409bf8  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100409bfe  mov     r8, [rdi+100h]
0x100409c05  mov     ecx, [rbx]
0x100409c07  jmp     loc_1004019E8
```
