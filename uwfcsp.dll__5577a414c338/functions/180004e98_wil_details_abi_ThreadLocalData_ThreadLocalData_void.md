# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004e98`
- end: `0x180004f14`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004dcc`

## callees

- `0x180004e98`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ebd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004eee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ebd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004eee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ecb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004efc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ecb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004efc`

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
0x180004e98  push    rbx
0x180004e9a  push    rbp
0x180004e9b  push    rsi
0x180004e9c  push    rdi
0x180004e9d  sub     rsp, 28h
0x180004ea1  movzx   eax, word ptr [rcx+20h]
0x180004ea5  mov     rsi, rcx
0x180004ea8  mov     rdi, [rcx+18h]
0x180004eac  lea     rbp, [rax+rax*4]
0x180004eb0  shl     rbp, 4
0x180004eb4  add     rbp, rdi
0x180004eb7  jmp     short loc_180004EE5
0x180004eb9  mov     rbx, [rdi+40h]
0x180004ebd  call    cs:__imp_GetProcessHeap
0x180004ec3  mov     r8, rbx; lpMem
0x180004ec6  xor     edx, edx; dwFlags
0x180004ec8  mov     rcx, rax; hHeap
0x180004ecb  call    cs:__imp_HeapFree
0x180004ed1  mov     qword ptr [rdi+40h], 0
0x180004ed9  mov     qword ptr [rdi+48h], 0
0x180004ee1  add     rdi, 50h ; 'P'
0x180004ee5  cmp     rdi, rbp
0x180004ee8  jnz     short loc_180004EB9
0x180004eea  mov     rbx, [rsi+18h]
0x180004eee  call    cs:__imp_GetProcessHeap
0x180004ef4  mov     r8, rbx; lpMem
0x180004ef7  xor     edx, edx; dwFlags
0x180004ef9  mov     rcx, rax; hHeap
0x180004efc  call    cs:__imp_HeapFree
0x180004f02  xor     eax, eax
0x180004f04  mov     [rsi+20h], eax
0x180004f07  mov     [rsi+18h], rax
0x180004f0b  add     rsp, 28h
0x180004f0f  pop     rdi
0x180004f10  pop     rsi
0x180004f11  pop     rbp
0x180004f12  pop     rbx
0x180004f13  retn
```
