# NThreadingLibrary::TTpSetWorkEnv::~TTpSetWorkEnv(void)

- ea: `0x140013174`
- end: `0x1400131bb`
- name: `??1TTpSetWorkEnv@NThreadingLibrary@@UEAA@XZ`
- size: `71`
- prototype: `void __fastcall(NThreadingLibrary::TTpSetWorkEnv *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400131c4`
- `0x1400132a8`
- `0x140013340`

## callees

- `0x140013174`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400131a2`
- `KERNEL32!HeapFree` at `0x1400131a2`
- `KERNEL32!GetProcessHeap` at `0x140013194`
- `KERNEL32!GetProcessHeap` at `0x140013194`

## pseudocode

```c
void __fastcall NThreadingLibrary::TTpSetWorkEnv::~TTpSetWorkEnv(NThreadingLibrary::TTpSetWorkEnv *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax

  v1 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)this = &NThreadingLibrary::TTpSetWorkEnv::`vftable';
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x140013174  mov     [rsp+arg_0], rbx
0x140013179  push    rdi
0x14001317a  sub     rsp, 20h
0x14001317e  mov     rdi, [rcx+8]
0x140013182  lea     rax, ??_7TTpSetWorkEnv@NThreadingLibrary@@6B@; const NThreadingLibrary::TTpSetWorkEnv::`vftable'
0x140013189  mov     [rcx], rax
0x14001318c  mov     rbx, rcx
0x14001318f  test    rdi, rdi
0x140013192  jz      short loc_1400131B0
0x140013194  call    cs:__imp_GetProcessHeap
0x14001319a  mov     r8, rdi; lpMem
0x14001319d  xor     edx, edx; dwFlags
0x14001319f  mov     rcx, rax; hHeap
0x1400131a2  call    cs:__imp_HeapFree
0x1400131a8  mov     qword ptr [rbx+8], 0
0x1400131b0  mov     rbx, [rsp+28h+arg_0]
0x1400131b5  add     rsp, 20h
0x1400131b9  pop     rdi
0x1400131ba  retn
```
