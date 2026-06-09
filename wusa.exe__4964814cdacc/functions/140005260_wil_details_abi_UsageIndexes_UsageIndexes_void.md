# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140005260`
- end: `0x1400052ed`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004f94`
- `0x140009700`
- `0x14000a0ac`

## callees

- `0x140005260`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140005292`
- `KERNEL32!HeapFree` at `0x1400052b7`
- `KERNEL32!HeapFree` at `0x1400052dc`
- `KERNEL32!HeapFree` at `0x140005292`
- `KERNEL32!HeapFree` at `0x1400052b7`
- `KERNEL32!HeapFree` at `0x1400052dc`
- `KERNEL32!GetProcessHeap` at `0x140005284`
- `KERNEL32!GetProcessHeap` at `0x1400052a9`
- `KERNEL32!GetProcessHeap` at `0x1400052ce`
- `KERNEL32!GetProcessHeap` at `0x140005284`
- `KERNEL32!GetProcessHeap` at `0x1400052a9`
- `KERNEL32!GetProcessHeap` at `0x1400052ce`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v1 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  v4 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
}

```

## disassembly

```asm
0x140005260  mov     [rsp+arg_0], rbx
0x140005265  push    rdi
0x140005266  sub     rsp, 20h
0x14000526a  mov     rdi, [rcx+0B0h]
0x140005271  mov     rbx, rcx
0x140005274  mov     qword ptr [rcx+0B0h], 0
0x14000527f  test    rdi, rdi
0x140005282  jz      short loc_140005298
0x140005284  call    cs:__imp_GetProcessHeap
0x14000528a  mov     r8, rdi; lpMem
0x14000528d  xor     edx, edx; dwFlags
0x14000528f  mov     rcx, rax; hHeap
0x140005292  call    cs:__imp_HeapFree
0x140005298  mov     rdi, [rbx+70h]
0x14000529c  mov     qword ptr [rbx+70h], 0
0x1400052a4  test    rdi, rdi
0x1400052a7  jz      short loc_1400052BD
0x1400052a9  call    cs:__imp_GetProcessHeap
0x1400052af  mov     r8, rdi; lpMem
0x1400052b2  xor     edx, edx; dwFlags
0x1400052b4  mov     rcx, rax; hHeap
0x1400052b7  call    cs:__imp_HeapFree
0x1400052bd  mov     rdi, [rbx+30h]
0x1400052c1  mov     qword ptr [rbx+30h], 0
0x1400052c9  test    rdi, rdi
0x1400052cc  jz      short loc_1400052E2
0x1400052ce  call    cs:__imp_GetProcessHeap
0x1400052d4  mov     r8, rdi; lpMem
0x1400052d7  xor     edx, edx; dwFlags
0x1400052d9  mov     rcx, rax; hHeap
0x1400052dc  call    cs:__imp_HeapFree
0x1400052e2  mov     rbx, [rsp+28h+arg_0]
0x1400052e7  add     rsp, 20h
0x1400052eb  pop     rdi
0x1400052ec  retn
```
