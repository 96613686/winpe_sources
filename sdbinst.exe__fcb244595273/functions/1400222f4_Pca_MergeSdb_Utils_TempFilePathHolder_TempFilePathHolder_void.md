# Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder(void)

- ea: `0x1400222f4`
- end: `0x140022325`
- name: `??1TempFilePathHolder@Utils@MergeSdb@Pca@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140024958`

## callees

- `0x1400222f4`
- `0x14002269c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14002230a`
- `KERNEL32!GetProcessHeap` at `0x14002230a`
- `KERNEL32!HeapFree` at `0x140022318`
- `KERNEL32!HeapFree` at `0x140022318`

## pseudocode

```c
void __fastcall Pca::MergeSdb::Utils::TempFilePathHolder::~TempFilePathHolder(LPCWSTR *this)
{
  WCHAR *v2; // rbx
  HANDLE ProcessHeap; // rax

  Pca::MergeSdb::Utils::TempFilePathHolder::Delete(this);
  v2 = (WCHAR *)*this;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
}

```

## disassembly

```asm
0x1400222f4  push    rbx
0x1400222f6  sub     rsp, 20h
0x1400222fa  mov     rbx, rcx
0x1400222fd  call    ?Delete@TempFilePathHolder@Utils@MergeSdb@Pca@@QEAAXXZ; Pca::MergeSdb::Utils::TempFilePathHolder::Delete(void)
0x140022302  mov     rbx, [rbx]
0x140022305  test    rbx, rbx
0x140022308  jz      short loc_14002231F
0x14002230a  call    cs:__imp_GetProcessHeap
0x140022310  mov     rcx, rax; hHeap
0x140022313  mov     r8, rbx; lpMem
0x140022316  xor     edx, edx; dwFlags
0x140022318  call    cs:__imp_HeapFree
0x14002231e  nop
0x14002231f  add     rsp, 20h
0x140022323  pop     rbx
0x140022324  retn
```
