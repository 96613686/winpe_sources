# AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::~THREAD_AFFINITY_CONTEXT(void)

- ea: `0x180002908`
- end: `0x18000294c`
- name: `??1THREAD_AFFINITY_CONTEXT@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a68`

## callees

- `0x180002908`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18000291d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18000291d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002926`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002926`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002934`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002934`

## pseudocode

```c
void __fastcall AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::~THREAD_AFFINITY_CONTEXT(
        struct _PROC_THREAD_ATTRIBUTE_LIST **this)
{
  struct _PROC_THREAD_ATTRIBUTE_LIST *v2; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v3; // rbx
  HANDLE ProcessHeap; // rax

  v2 = *this;
  if ( v2 )
  {
    DeleteProcThreadAttributeList(v2);
    v3 = *this;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180002908  mov     [rsp+arg_0], rbx
0x18000290d  push    rdi
0x18000290e  sub     rsp, 20h
0x180002912  mov     rdi, rcx
0x180002915  mov     rcx, [rcx]; lpAttributeList
0x180002918  test    rcx, rcx
0x18000291b  jz      short loc_180002941
0x18000291d  call    cs:__imp_DeleteProcThreadAttributeList
0x180002923  mov     rbx, [rdi]
0x180002926  call    cs:__imp_GetProcessHeap
0x18000292c  mov     r8, rbx; lpMem
0x18000292f  xor     edx, edx; dwFlags
0x180002931  mov     rcx, rax; hHeap
0x180002934  call    cs:__imp_HeapFree
0x18000293a  mov     qword ptr [rdi], 0
0x180002941  mov     rbx, [rsp+28h+arg_0]
0x180002946  add     rsp, 20h
0x18000294a  pop     rdi
0x18000294b  retn
```
