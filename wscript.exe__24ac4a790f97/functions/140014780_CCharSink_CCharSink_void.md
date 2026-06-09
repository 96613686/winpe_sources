# CCharSink::~CCharSink(void)

- ea: `0x140014780`
- end: `0x1400147a8`
- name: `??1CCharSink@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(CCharSink *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400057f0`
- `0x14000cfbc`
- `0x14000f540`
- `0x140011e90`

## callees

- `0x140014780`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001479c`
- `KERNEL32!HeapFree` at `0x14001479c`
- `KERNEL32!GetProcessHeap` at `0x14001478e`
- `KERNEL32!GetProcessHeap` at `0x14001478e`

## pseudocode

```c
void __fastcall CCharSink::~CCharSink(void **this)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *this;
  if ( *this )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x140014780  push    rbx
0x140014782  sub     rsp, 20h
0x140014786  mov     rbx, [rcx]
0x140014789  test    rbx, rbx
0x14001478c  jz      short loc_1400147A2
0x14001478e  call    cs:__imp_GetProcessHeap
0x140014794  mov     r8, rbx; lpMem
0x140014797  xor     edx, edx; dwFlags
0x140014799  mov     rcx, rax; hHeap
0x14001479c  call    cs:__imp_HeapFree
0x1400147a2  add     rsp, 20h
0x1400147a6  pop     rbx
0x1400147a7  retn
```
