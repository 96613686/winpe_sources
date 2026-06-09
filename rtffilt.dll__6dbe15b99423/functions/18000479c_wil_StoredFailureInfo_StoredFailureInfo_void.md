# wil::StoredFailureInfo::~StoredFailureInfo(void)

- ea: `0x18000479c`
- end: `0x1800047fd`
- name: `??1StoredFailureInfo@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004718`
- `0x18000de78`
- `0x1800101ec`
- `0x180014590`
- `0x180017af0`

## callees

- `0x18000479c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047d6`

## pseudocode

```c
void __fastcall wil::StoredFailureInfo::~StoredFailureInfo(wil::StoredFailureInfo *this)
{
  volatile signed __int32 *v2; // rcx
  void *v3; // rbx
  HANDLE ProcessHeap; // rax

  v2 = (volatile signed __int32 *)*((_QWORD *)this + 19);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = (void *)*((_QWORD *)this + 19);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
  }
}

```

## disassembly

```asm
0x18000479c  mov     [rsp+arg_0], rbx
0x1800047a1  push    rdi
0x1800047a2  sub     rsp, 20h
0x1800047a6  mov     rdi, rcx
0x1800047a9  mov     rcx, [rcx+98h]
0x1800047b0  test    rcx, rcx
0x1800047b3  jz      short loc_1800047F2
0x1800047b5  or      eax, 0FFFFFFFFh
0x1800047b8  lock xadd [rcx], eax
0x1800047bc  cmp     eax, 1
0x1800047bf  jnz     short loc_1800047DC
0x1800047c1  mov     rbx, [rdi+98h]
0x1800047c8  call    cs:__imp_GetProcessHeap
0x1800047ce  mov     r8, rbx; lpMem
0x1800047d1  xor     edx, edx; dwFlags
0x1800047d3  mov     rcx, rax; hHeap
0x1800047d6  call    cs:__imp_HeapFree
0x1800047dc  mov     qword ptr [rdi+98h], 0
0x1800047e7  mov     qword ptr [rdi+0A0h], 0
0x1800047f2  mov     rbx, [rsp+28h+arg_0]
0x1800047f7  add     rsp, 20h
0x1800047fb  pop     rdi
0x1800047fc  retn
```
