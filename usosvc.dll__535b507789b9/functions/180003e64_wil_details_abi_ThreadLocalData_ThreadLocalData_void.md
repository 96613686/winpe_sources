# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003e64`
- end: `0x180003ee0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003cac`

## callees

- `0x180003e64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003eba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003eba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ec8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ec8`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180003e64  push    rbx
0x180003e66  push    rbp
0x180003e67  push    rsi
0x180003e68  push    rdi
0x180003e69  sub     rsp, 28h
0x180003e6d  movzx   eax, word ptr [rcx+20h]
0x180003e71  mov     rsi, rcx
0x180003e74  mov     rdi, [rcx+18h]
0x180003e78  lea     rbp, [rax+rax*4]
0x180003e7c  shl     rbp, 4
0x180003e80  add     rbp, rdi
0x180003e83  jmp     short loc_180003EB1
0x180003e85  mov     rbx, [rdi+40h]
0x180003e89  call    cs:__imp_GetProcessHeap
0x180003e8f  mov     r8, rbx; lpMem
0x180003e92  xor     edx, edx; dwFlags
0x180003e94  mov     rcx, rax; hHeap
0x180003e97  call    cs:__imp_HeapFree
0x180003e9d  mov     qword ptr [rdi+40h], 0
0x180003ea5  mov     qword ptr [rdi+48h], 0
0x180003ead  add     rdi, 50h ; 'P'
0x180003eb1  cmp     rdi, rbp
0x180003eb4  jnz     short loc_180003E85
0x180003eb6  mov     rbx, [rsi+18h]
0x180003eba  call    cs:__imp_GetProcessHeap
0x180003ec0  mov     r8, rbx; lpMem
0x180003ec3  xor     edx, edx; dwFlags
0x180003ec5  mov     rcx, rax; hHeap
0x180003ec8  call    cs:__imp_HeapFree
0x180003ece  xor     eax, eax
0x180003ed0  mov     [rsi+20h], eax
0x180003ed3  mov     [rsi+18h], rax
0x180003ed7  add     rsp, 28h
0x180003edb  pop     rdi
0x180003edc  pop     rsi
0x180003edd  pop     rbp
0x180003ede  pop     rbx
0x180003edf  retn
```
