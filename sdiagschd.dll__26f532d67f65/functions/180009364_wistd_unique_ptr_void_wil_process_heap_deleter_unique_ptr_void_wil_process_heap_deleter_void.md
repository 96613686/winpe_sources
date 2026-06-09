# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180009364`
- end: `0x18000939e`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cd4a`

## callees

- `0x180009364`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000938a`
- `KERNEL32!HeapFree` at `0x18000938a`
- `KERNEL32!GetProcessHeap` at `0x180009376`
- `KERNEL32!GetProcessHeap` at `0x180009376`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
        void **a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x180009364  push    rbx
0x180009366  sub     rsp, 20h
0x18000936a  mov     rbx, [rcx]
0x18000936d  and     qword ptr [rcx], 0
0x180009371  test    rbx, rbx
0x180009374  jz      short loc_180009397
0x180009376  call    cs:__imp_GetProcessHeap
0x18000937d  nop     dword ptr [rax+rax+00h]
0x180009382  mov     rcx, rax; hHeap
0x180009385  mov     r8, rbx; lpMem
0x180009388  xor     edx, edx; dwFlags
0x18000938a  call    cs:__imp_HeapFree
0x180009391  nop     dword ptr [rax+rax+00h]
0x180009396  nop
0x180009397  add     rsp, 20h
0x18000939b  pop     rbx
0x18000939c  retn
```
