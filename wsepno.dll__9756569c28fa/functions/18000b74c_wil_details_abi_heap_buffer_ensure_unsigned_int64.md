# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000b74c`
- end: `0x18000b81e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180008aac`
- `0x180008c50`
- `0x180009488`
- `0x18000a780`
- `0x18000a988`

## callees

- `0x180003a28`
- `0x1800083d0`
- `0x18000b74c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b7b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b809`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b7b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b78d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b78d`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  char *v7; // rax
  char *v8; // rbx
  rsize_t v10; // r15
  void *v11; // rbp
  HANDLE ProcessHeap; // rax

  v3 = a2;
  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this >= v4 )
  {
    if ( a2 < 2 * v4 )
      v3 = 2 * v4;
    if ( v4 < v3 )
    {
      LastError = GetLastError();
      v6 = (v3 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v7 = (char *)wil::details::ProcessHeapAlloc(0, v6);
      v8 = v7;
      if ( !v7 )
      {
        SetLastError(LastError);
        return 0;
      }
      v10 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v7, v6, *(const void *const *)this, v10);
      v11 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v8;
      if ( v11 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v11);
      }
      *(_QWORD *)this = v8;
      *((_QWORD *)this + 1) = &v8[v10];
      *((_QWORD *)this + 2) = &v8[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000b74c  push    rbx
0x18000b74e  push    rbp
0x18000b74f  push    rsi
0x18000b750  push    rdi
0x18000b751  push    r14
0x18000b753  push    r15
0x18000b755  sub     rsp, 28h
0x18000b759  mov     rdi, rcx
0x18000b75c  mov     rbx, rdx
0x18000b75f  mov     rcx, [rcx+10h]
0x18000b763  mov     rax, [rdi+8]
0x18000b767  sub     rax, [rdi]
0x18000b76a  sub     rcx, [rdi]
0x18000b76d  add     rax, rdx
0x18000b770  cmp     rax, rcx
0x18000b773  jb      loc_18000B80F
0x18000b779  lea     rax, [rcx+rcx]
0x18000b77d  cmp     rdx, rax
0x18000b780  cmovb   rbx, rax
0x18000b784  cmp     rcx, rbx
0x18000b787  jnb     loc_18000B80F
0x18000b78d  call    cs:__imp_GetLastError
0x18000b793  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000b797  xor     ecx, ecx; dwFlags
0x18000b799  mov     esi, eax
0x18000b79b  lea     r14, [rbx+40h]
0x18000b79f  mov     rdx, r14; dwBytes
0x18000b7a2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b7a7  mov     rbx, rax
0x18000b7aa  test    rax, rax
0x18000b7ad  jnz     short loc_18000B7BB
0x18000b7af  mov     ecx, esi; dwErrCode
0x18000b7b1  call    cs:__imp_SetLastError
0x18000b7b7  xor     al, al
0x18000b7b9  jmp     short loc_18000B811
0x18000b7bb  mov     r15, [rdi+8]
0x18000b7bf  mov     rdx, r14; DestinationSize
0x18000b7c2  sub     r15, [rdi]
0x18000b7c5  mov     rcx, rbx; Destination
0x18000b7c8  mov     r8, [rdi]; Source
0x18000b7cb  mov     r9, r15; SourceSize
0x18000b7ce  call    memcpy_s
0x18000b7d3  mov     rbp, [rdi+18h]
0x18000b7d7  mov     [rdi+18h], rbx
0x18000b7db  test    rbp, rbp
0x18000b7de  jz      short loc_18000B7F4
0x18000b7e0  call    cs:__imp_GetProcessHeap
0x18000b7e6  mov     r8, rbp; lpMem
0x18000b7e9  xor     edx, edx; dwFlags
0x18000b7eb  mov     rcx, rax; hHeap
0x18000b7ee  call    cs:__imp_HeapFree
0x18000b7f4  lea     rax, [r15+rbx]
0x18000b7f8  mov     [rdi], rbx
0x18000b7fb  mov     [rdi+8], rax
0x18000b7ff  mov     ecx, esi; dwErrCode
0x18000b801  lea     rax, [r14+rbx]
0x18000b805  mov     [rdi+10h], rax
0x18000b809  call    cs:__imp_SetLastError
0x18000b80f  mov     al, 1
0x18000b811  add     rsp, 28h
0x18000b815  pop     r15
0x18000b817  pop     r14
0x18000b819  pop     rdi
0x18000b81a  pop     rsi
0x18000b81b  pop     rbp
0x18000b81c  pop     rbx
0x18000b81d  retn
```
