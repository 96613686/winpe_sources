# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003b4c`
- end: `0x180003bc8`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a80`

## callees

- `0x180003b4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ba2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ba2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003bb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003bb0`

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
0x180003b4c  push    rbx
0x180003b4e  push    rbp
0x180003b4f  push    rsi
0x180003b50  push    rdi
0x180003b51  sub     rsp, 28h
0x180003b55  movzx   eax, word ptr [rcx+20h]
0x180003b59  mov     rsi, rcx
0x180003b5c  mov     rdi, [rcx+18h]
0x180003b60  lea     rbp, [rax+rax*4]
0x180003b64  shl     rbp, 4
0x180003b68  add     rbp, rdi
0x180003b6b  jmp     short loc_180003B99
0x180003b6d  mov     rbx, [rdi+40h]
0x180003b71  call    cs:__imp_GetProcessHeap
0x180003b77  mov     r8, rbx; lpMem
0x180003b7a  xor     edx, edx; dwFlags
0x180003b7c  mov     rcx, rax; hHeap
0x180003b7f  call    cs:__imp_HeapFree
0x180003b85  mov     qword ptr [rdi+40h], 0
0x180003b8d  mov     qword ptr [rdi+48h], 0
0x180003b95  add     rdi, 50h ; 'P'
0x180003b99  cmp     rdi, rbp
0x180003b9c  jnz     short loc_180003B6D
0x180003b9e  mov     rbx, [rsi+18h]
0x180003ba2  call    cs:__imp_GetProcessHeap
0x180003ba8  mov     r8, rbx; lpMem
0x180003bab  xor     edx, edx; dwFlags
0x180003bad  mov     rcx, rax; hHeap
0x180003bb0  call    cs:__imp_HeapFree
0x180003bb6  xor     eax, eax
0x180003bb8  mov     [rsi+20h], eax
0x180003bbb  mov     [rsi+18h], rax
0x180003bbf  add     rsp, 28h
0x180003bc3  pop     rdi
0x180003bc4  pop     rsi
0x180003bc5  pop     rbp
0x180003bc6  pop     rbx
0x180003bc7  retn
```
