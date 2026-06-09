# CTaskNameHolder::~CTaskNameHolder(void)

- ea: `0x180019dc4`
- end: `0x180019e39`
- name: `??1CTaskNameHolder@@QEAA@XZ`
- size: `117`
- prototype: `void __fastcall(CTaskNameHolder *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180019d70`
- `0x180019e90`

## callees

- `0x180019dc4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019df7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019df7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019de3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019de3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e0c`

## pseudocode

```c
void __fastcall CTaskNameHolder::~CTaskNameHolder(CTaskNameHolder *this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rbx
  HANDLE v5; // rax

  v2 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
}

```

## disassembly

```asm
0x180019dc4  push    rdi
0x180019dc6  sub     rsp, 30h
0x180019dca  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180019dd3  mov     [rsp+38h+arg_0], rbx
0x180019dd8  mov     rbx, rcx
0x180019ddb  mov     rdi, [rcx]
0x180019dde  test    rdi, rdi
0x180019de1  jz      short loc_180019E03
0x180019de3  call    cs:__imp_GetProcessHeap
0x180019dea  nop     dword ptr [rax+rax+00h]
0x180019def  mov     r8, rdi; lpMem
0x180019df2  xor     edx, edx; dwFlags
0x180019df4  mov     rcx, rax; hHeap
0x180019df7  call    cs:__imp_HeapFree
0x180019dfe  nop     dword ptr [rax+rax+00h]
0x180019e03  mov     rbx, [rbx+8]
0x180019e07  test    rbx, rbx
0x180019e0a  jz      short loc_180019E2D
0x180019e0c  call    cs:__imp_GetProcessHeap
0x180019e13  nop     dword ptr [rax+rax+00h]
0x180019e18  mov     r8, rbx; lpMem
0x180019e1b  xor     edx, edx; dwFlags
0x180019e1d  mov     rcx, rax; hHeap
0x180019e20  call    cs:__imp_HeapFree
0x180019e27  nop     dword ptr [rax+rax+00h]
0x180019e2c  nop
0x180019e2d  mov     rbx, [rsp+38h+arg_0]
0x180019e32  add     rsp, 30h
0x180019e36  pop     rdi
0x180019e37  retn
```
