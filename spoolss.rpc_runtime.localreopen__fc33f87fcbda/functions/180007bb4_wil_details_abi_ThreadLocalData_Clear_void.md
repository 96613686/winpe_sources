# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x180007bb4`
- end: `0x180007c49`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007584`

## callees

- `0x180007bb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c16`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::Clear(wil::details_abi::ThreadLocalData *this)
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
0x180007bb4  push    rbx
0x180007bb6  push    rbp
0x180007bb7  push    rsi
0x180007bb8  push    rdi
0x180007bb9  sub     rsp, 28h
0x180007bbd  movzx   eax, word ptr [rcx+20h]
0x180007bc1  mov     rsi, rcx
0x180007bc4  mov     rdi, [rcx+18h]
0x180007bc8  lea     rbp, [rax+rax*4]
0x180007bcc  shl     rbp, 4
0x180007bd0  add     rbp, rdi
0x180007bd3  jmp     short loc_180007C0D
0x180007bd5  mov     rbx, [rdi+40h]
0x180007bd9  call    cs:__imp_GetProcessHeap
0x180007be0  nop     dword ptr [rax+rax+00h]
0x180007be5  mov     r8, rbx; lpMem
0x180007be8  xor     edx, edx; dwFlags
0x180007bea  mov     rcx, rax; hHeap
0x180007bed  call    cs:__imp_HeapFree
0x180007bf4  nop     dword ptr [rax+rax+00h]
0x180007bf9  mov     qword ptr [rdi+40h], 0
0x180007c01  mov     qword ptr [rdi+48h], 0
0x180007c09  add     rdi, 50h ; 'P'
0x180007c0d  cmp     rdi, rbp
0x180007c10  jnz     short loc_180007BD5
0x180007c12  mov     rbx, [rsi+18h]
0x180007c16  call    cs:__imp_GetProcessHeap
0x180007c1d  nop     dword ptr [rax+rax+00h]
0x180007c22  mov     r8, rbx; lpMem
0x180007c25  xor     edx, edx; dwFlags
0x180007c27  mov     rcx, rax; hHeap
0x180007c2a  call    cs:__imp_HeapFree
0x180007c31  nop     dword ptr [rax+rax+00h]
0x180007c36  xor     eax, eax
0x180007c38  mov     [rsi+20h], eax
0x180007c3b  mov     [rsi+18h], rax
0x180007c3f  add     rsp, 28h
0x180007c43  pop     rdi
0x180007c44  pop     rsi
0x180007c45  pop     rbp
0x180007c46  pop     rbx
0x180007c47  retn
```
