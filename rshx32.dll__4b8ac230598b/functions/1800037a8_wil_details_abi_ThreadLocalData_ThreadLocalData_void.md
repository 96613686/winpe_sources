# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800037a8`
- end: `0x180003824`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036dc`

## callees

- `0x1800037a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000380c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000380c`

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
0x1800037a8  push    rbx
0x1800037aa  push    rbp
0x1800037ab  push    rsi
0x1800037ac  push    rdi
0x1800037ad  sub     rsp, 28h
0x1800037b1  movzx   eax, word ptr [rcx+20h]
0x1800037b5  mov     rsi, rcx
0x1800037b8  mov     rdi, [rcx+18h]
0x1800037bc  lea     rbp, [rax+rax*4]
0x1800037c0  shl     rbp, 4
0x1800037c4  add     rbp, rdi
0x1800037c7  jmp     short loc_1800037F5
0x1800037c9  mov     rbx, [rdi+40h]
0x1800037cd  call    cs:__imp_GetProcessHeap
0x1800037d3  mov     r8, rbx; lpMem
0x1800037d6  xor     edx, edx; dwFlags
0x1800037d8  mov     rcx, rax; hHeap
0x1800037db  call    cs:__imp_HeapFree
0x1800037e1  mov     qword ptr [rdi+40h], 0
0x1800037e9  mov     qword ptr [rdi+48h], 0
0x1800037f1  add     rdi, 50h ; 'P'
0x1800037f5  cmp     rdi, rbp
0x1800037f8  jnz     short loc_1800037C9
0x1800037fa  mov     rbx, [rsi+18h]
0x1800037fe  call    cs:__imp_GetProcessHeap
0x180003804  mov     r8, rbx; lpMem
0x180003807  xor     edx, edx; dwFlags
0x180003809  mov     rcx, rax; hHeap
0x18000380c  call    cs:__imp_HeapFree
0x180003812  xor     eax, eax
0x180003814  mov     [rsi+20h], eax
0x180003817  mov     [rsi+18h], rax
0x18000381b  add     rsp, 28h
0x18000381f  pop     rdi
0x180003820  pop     rsi
0x180003821  pop     rbp
0x180003822  pop     rbx
0x180003823  retn
```
