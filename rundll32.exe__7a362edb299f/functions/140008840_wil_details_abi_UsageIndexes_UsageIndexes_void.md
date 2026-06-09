# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140008840`
- end: `0x1400088cd`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140008574`
- `0x1400097cc`
- `0x14000a168`

## callees

- `0x140008840`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008872`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008897`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400088bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008872`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008897`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400088bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008864`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008889`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400088ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008864`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008889`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400088ae`

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
0x140008840  mov     [rsp+arg_0], rbx
0x140008845  push    rdi
0x140008846  sub     rsp, 20h
0x14000884a  mov     rdi, [rcx+0B0h]
0x140008851  mov     rbx, rcx
0x140008854  mov     qword ptr [rcx+0B0h], 0
0x14000885f  test    rdi, rdi
0x140008862  jz      short loc_140008878
0x140008864  call    cs:__imp_GetProcessHeap
0x14000886a  mov     r8, rdi; lpMem
0x14000886d  xor     edx, edx; dwFlags
0x14000886f  mov     rcx, rax; hHeap
0x140008872  call    cs:__imp_HeapFree
0x140008878  mov     rdi, [rbx+70h]
0x14000887c  mov     qword ptr [rbx+70h], 0
0x140008884  test    rdi, rdi
0x140008887  jz      short loc_14000889D
0x140008889  call    cs:__imp_GetProcessHeap
0x14000888f  mov     r8, rdi; lpMem
0x140008892  xor     edx, edx; dwFlags
0x140008894  mov     rcx, rax; hHeap
0x140008897  call    cs:__imp_HeapFree
0x14000889d  mov     rdi, [rbx+30h]
0x1400088a1  mov     qword ptr [rbx+30h], 0
0x1400088a9  test    rdi, rdi
0x1400088ac  jz      short loc_1400088C2
0x1400088ae  call    cs:__imp_GetProcessHeap
0x1400088b4  mov     r8, rdi; lpMem
0x1400088b7  xor     edx, edx; dwFlags
0x1400088b9  mov     rcx, rax; hHeap
0x1400088bc  call    cs:__imp_HeapFree
0x1400088c2  mov     rbx, [rsp+28h+arg_0]
0x1400088c7  add     rsp, 20h
0x1400088cb  pop     rdi
0x1400088cc  retn
```
