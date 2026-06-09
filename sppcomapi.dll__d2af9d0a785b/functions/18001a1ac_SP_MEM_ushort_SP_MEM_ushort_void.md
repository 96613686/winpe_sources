# SP_MEM<ushort *>::~SP_MEM<ushort *>(void)

- ea: `0x18001a1ac`
- end: `0x18001a1f4`
- name: `??1?$SP_MEM@PEAG@@QEAA@XZ`
- size: `72`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`

## callees

- `0x18001a1ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a1c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a1c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a1d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a1d5`

## pseudocode

```c
void __fastcall SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(void **a1)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18001a1ac  mov     [rsp+arg_0], rbx
0x18001a1b1  push    rdi
0x18001a1b2  sub     rsp, 20h
0x18001a1b6  mov     rdi, [rcx]
0x18001a1b9  mov     rbx, rcx
0x18001a1bc  test    rdi, rdi
0x18001a1bf  jz      short loc_18001A1E8
0x18001a1c1  call    cs:__imp_GetProcessHeap
0x18001a1c8  nop     dword ptr [rax+rax+00h]
0x18001a1cd  mov     r8, rdi; lpMem
0x18001a1d0  xor     edx, edx; dwFlags
0x18001a1d2  mov     rcx, rax; hHeap
0x18001a1d5  call    cs:__imp_HeapFree
0x18001a1dc  nop     dword ptr [rax+rax+00h]
0x18001a1e1  mov     qword ptr [rbx], 0
0x18001a1e8  mov     rbx, [rsp+28h+arg_0]
0x18001a1ed  add     rsp, 20h
0x18001a1f1  pop     rdi
0x18001a1f2  retn
```
