# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140010568`
- end: `0x1400105f5`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14001008c`
- `0x140012700`
- `0x140013248`
- `0x14001cd49`

## callees

- `0x140010568`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001058c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400105b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400105d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001058c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400105b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400105d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001059a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400105bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400105e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001059a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400105bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400105e4`

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
0x140010568  mov     [rsp+arg_0], rbx
0x14001056d  push    rdi
0x14001056e  sub     rsp, 20h
0x140010572  mov     rdi, [rcx+0B0h]
0x140010579  mov     rbx, rcx
0x14001057c  mov     qword ptr [rcx+0B0h], 0
0x140010587  test    rdi, rdi
0x14001058a  jz      short loc_1400105A0
0x14001058c  call    cs:__imp_GetProcessHeap
0x140010592  mov     r8, rdi; lpMem
0x140010595  xor     edx, edx; dwFlags
0x140010597  mov     rcx, rax; hHeap
0x14001059a  call    cs:__imp_HeapFree
0x1400105a0  mov     rdi, [rbx+70h]
0x1400105a4  mov     qword ptr [rbx+70h], 0
0x1400105ac  test    rdi, rdi
0x1400105af  jz      short loc_1400105C5
0x1400105b1  call    cs:__imp_GetProcessHeap
0x1400105b7  mov     r8, rdi; lpMem
0x1400105ba  xor     edx, edx; dwFlags
0x1400105bc  mov     rcx, rax; hHeap
0x1400105bf  call    cs:__imp_HeapFree
0x1400105c5  mov     rdi, [rbx+30h]
0x1400105c9  mov     qword ptr [rbx+30h], 0
0x1400105d1  test    rdi, rdi
0x1400105d4  jz      short loc_1400105EA
0x1400105d6  call    cs:__imp_GetProcessHeap
0x1400105dc  mov     r8, rdi; lpMem
0x1400105df  xor     edx, edx; dwFlags
0x1400105e1  mov     rcx, rax; hHeap
0x1400105e4  call    cs:__imp_HeapFree
0x1400105ea  mov     rbx, [rsp+28h+arg_0]
0x1400105ef  add     rsp, 20h
0x1400105f3  pop     rdi
0x1400105f4  retn
```
