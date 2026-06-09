# RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(void)

- ea: `0x180010a40`
- end: `0x180010a7d`
- name: `?Release@?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEAAXXZ`
- size: `61`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d674`
- `0x18000d68c`
- `0x18000dd50`
- `0x18000dd90`
- `0x18000ed8c`
- `0x18001200c`
- `0x1800123a0`

## callees

- `0x180010a40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a64`

## pseudocode

```c
void __fastcall RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(__int64 a1)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *(void **)(a1 + 8);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180010a40  mov     [rsp+arg_8], rbx
0x180010a45  push    rdi
0x180010a46  sub     rsp, 20h
0x180010a4a  mov     rdi, [rcx+8]
0x180010a4e  mov     rbx, rcx
0x180010a51  test    rdi, rdi
0x180010a54  jz      short loc_180010A72
0x180010a56  call    cs:__imp_GetProcessHeap
0x180010a5c  mov     r8, rdi; lpMem
0x180010a5f  xor     edx, edx; dwFlags
0x180010a61  mov     rcx, rax; hHeap
0x180010a64  call    cs:__imp_HeapFree
0x180010a6a  mov     qword ptr [rbx+8], 0
0x180010a72  mov     rbx, [rsp+28h+arg_8]
0x180010a77  add     rsp, 20h
0x180010a7b  pop     rdi
0x180010a7c  retn
```
