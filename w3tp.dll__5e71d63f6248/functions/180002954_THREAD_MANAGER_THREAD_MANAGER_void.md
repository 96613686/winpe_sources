# THREAD_MANAGER::~THREAD_MANAGER(void)

- ea: `0x180002954`
- end: `0x180002a1f`
- name: `??1THREAD_MANAGER@@AEAA@XZ`
- size: `203`
- prototype: `void __fastcall(THREAD_MANAGER *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001870`
- `0x180002a90`

## callees

- `0x180002954`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800029de`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800029de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800029b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002a03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800029b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002a03`

## pseudocode

```c
void __fastcall THREAD_MANAGER::~THREAD_MANAGER(THREAD_MANAGER *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v5; // rcx
  void *v6; // rbx
  HANDLE v7; // rax

  *(_DWORD *)this = 2017545556;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 17);
  if ( v2 )
  {
    (**v2)(v2, 1);
    *((_QWORD *)this + 17) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 19);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *((_QWORD *)this + 19) = 0;
  }
  v5 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)*((_QWORD *)this + 21);
  if ( v5 )
  {
    if ( *((_DWORD *)this + 46) )
    {
      DeleteProcThreadAttributeList(v5);
      *((_DWORD *)this + 46) = 0;
    }
    v6 = (void *)*((_QWORD *)this + 21);
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
    *((_QWORD *)this + 21) = 0;
  }
}

```

## disassembly

```asm
0x180002954  mov     [rsp+arg_0], rbx
0x180002959  push    rdi
0x18000295a  sub     rsp, 20h
0x18000295e  mov     rdi, rcx
0x180002961  mov     dword ptr [rcx], 78414D54h
0x180002967  mov     qword ptr [rcx+68h], 0
0x18000296f  mov     qword ptr [rcx+70h], 0
0x180002977  mov     rcx, [rcx+88h]
0x18000297e  test    rcx, rcx
0x180002981  jz      short loc_18000299E
0x180002983  mov     rax, [rcx]
0x180002986  mov     edx, 1
0x18000298b  mov     rax, [rax]
0x18000298e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002993  mov     qword ptr [rdi+88h], 0
0x18000299e  mov     rbx, [rdi+98h]
0x1800029a5  test    rbx, rbx
0x1800029a8  jz      short loc_1800029C9
0x1800029aa  call    cs:__imp_GetProcessHeap
0x1800029b0  mov     r8, rbx; lpMem
0x1800029b3  xor     edx, edx; dwFlags
0x1800029b5  mov     rcx, rax; hHeap
0x1800029b8  call    cs:__imp_HeapFree
0x1800029be  mov     qword ptr [rdi+98h], 0
0x1800029c9  mov     rcx, [rdi+0A8h]; lpAttributeList
0x1800029d0  test    rcx, rcx
0x1800029d3  jz      short loc_180002A14
0x1800029d5  cmp     dword ptr [rdi+0B8h], 0
0x1800029dc  jz      short loc_1800029EE
0x1800029de  call    cs:__imp_DeleteProcThreadAttributeList
0x1800029e4  mov     dword ptr [rdi+0B8h], 0
0x1800029ee  mov     rbx, [rdi+0A8h]
0x1800029f5  call    cs:__imp_GetProcessHeap
0x1800029fb  mov     r8, rbx; lpMem
0x1800029fe  xor     edx, edx; dwFlags
0x180002a00  mov     rcx, rax; hHeap
0x180002a03  call    cs:__imp_HeapFree
0x180002a09  mov     qword ptr [rdi+0A8h], 0
0x180002a14  mov     rbx, [rsp+28h+arg_0]
0x180002a19  add     rsp, 20h
0x180002a1d  pop     rdi
0x180002a1e  retn
```
