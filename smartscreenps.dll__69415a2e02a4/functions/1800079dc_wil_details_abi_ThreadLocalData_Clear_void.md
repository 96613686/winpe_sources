# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x1800079dc`
- end: `0x180007a71`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007658`

## callees

- `0x1800079dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a52`

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
0x1800079dc  push    rbx
0x1800079de  push    rbp
0x1800079df  push    rsi
0x1800079e0  push    rdi
0x1800079e1  sub     rsp, 28h
0x1800079e5  movzx   eax, word ptr [rcx+20h]
0x1800079e9  mov     rsi, rcx
0x1800079ec  mov     rdi, [rcx+18h]
0x1800079f0  lea     rbp, [rax+rax*4]
0x1800079f4  shl     rbp, 4
0x1800079f8  add     rbp, rdi
0x1800079fb  jmp     short loc_180007A35
0x1800079fd  mov     rbx, [rdi+40h]
0x180007a01  call    cs:__imp_GetProcessHeap
0x180007a08  nop     dword ptr [rax+rax+00h]
0x180007a0d  mov     r8, rbx; lpMem
0x180007a10  xor     edx, edx; dwFlags
0x180007a12  mov     rcx, rax; hHeap
0x180007a15  call    cs:__imp_HeapFree
0x180007a1c  nop     dword ptr [rax+rax+00h]
0x180007a21  mov     qword ptr [rdi+40h], 0
0x180007a29  mov     qword ptr [rdi+48h], 0
0x180007a31  add     rdi, 50h ; 'P'
0x180007a35  cmp     rdi, rbp
0x180007a38  jnz     short loc_1800079FD
0x180007a3a  mov     rbx, [rsi+18h]
0x180007a3e  call    cs:__imp_GetProcessHeap
0x180007a45  nop     dword ptr [rax+rax+00h]
0x180007a4a  mov     r8, rbx; lpMem
0x180007a4d  xor     edx, edx; dwFlags
0x180007a4f  mov     rcx, rax; hHeap
0x180007a52  call    cs:__imp_HeapFree
0x180007a59  nop     dword ptr [rax+rax+00h]
0x180007a5e  xor     eax, eax
0x180007a60  mov     [rsi+20h], eax
0x180007a63  mov     [rsi+18h], rax
0x180007a67  add     rsp, 28h
0x180007a6b  pop     rdi
0x180007a6c  pop     rsi
0x180007a6d  pop     rbp
0x180007a6e  pop     rbx
0x180007a6f  retn
```
