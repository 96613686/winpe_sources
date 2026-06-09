# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000a09c`
- end: `0x14000a16f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400077ec`
- `0x140007e00`
- `0x1400096b8`

## callees

- `0x140007748`
- `0x14000a09c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000a11e`
- `msvcrt!memcpy_s` at `0x14000a11e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a101`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a15a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a101`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a15a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a0dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a0dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a13f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a13f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a131`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a131`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r8
  char *v8; // rax
  char *v9; // rbx
  rsize_t v11; // r15
  void *v12; // rbp
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
      v8 = (char *)wil::details::ProcessHeapAlloc(0, v6, v7);
      v9 = v8;
      if ( !v8 )
      {
        SetLastError(LastError);
        return 0;
      }
      v11 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v8, v6, *(const void *const *)this, v11);
      v12 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v9;
      if ( v12 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
      }
      *(_QWORD *)this = v9;
      *((_QWORD *)this + 1) = &v9[v11];
      *((_QWORD *)this + 2) = &v9[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000a09c  push    rbx
0x14000a09e  push    rbp
0x14000a09f  push    rsi
0x14000a0a0  push    rdi
0x14000a0a1  push    r14
0x14000a0a3  push    r15
0x14000a0a5  sub     rsp, 28h
0x14000a0a9  mov     rdi, rcx
0x14000a0ac  mov     rbx, rdx
0x14000a0af  mov     rcx, [rcx+10h]
0x14000a0b3  mov     rax, [rdi+8]
0x14000a0b7  sub     rax, [rdi]
0x14000a0ba  sub     rcx, [rdi]
0x14000a0bd  add     rax, rdx
0x14000a0c0  cmp     rax, rcx
0x14000a0c3  jb      loc_14000A160
0x14000a0c9  lea     rax, [rcx+rcx]
0x14000a0cd  cmp     rdx, rax
0x14000a0d0  cmovb   rbx, rax
0x14000a0d4  cmp     rcx, rbx
0x14000a0d7  jnb     loc_14000A160
0x14000a0dd  call    cs:__imp_GetLastError
0x14000a0e3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000a0e7  xor     ecx, ecx; dwFlags
0x14000a0e9  mov     esi, eax
0x14000a0eb  lea     r14, [rbx+40h]
0x14000a0ef  mov     rdx, r14; dwBytes
0x14000a0f2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000a0f7  mov     rbx, rax
0x14000a0fa  test    rax, rax
0x14000a0fd  jnz     short loc_14000A10B
0x14000a0ff  mov     ecx, esi; dwErrCode
0x14000a101  call    cs:__imp_SetLastError
0x14000a107  xor     al, al
0x14000a109  jmp     short loc_14000A162
0x14000a10b  mov     r15, [rdi+8]
0x14000a10f  mov     rdx, r14; DestinationSize
0x14000a112  sub     r15, [rdi]
0x14000a115  mov     rcx, rbx; Destination
0x14000a118  mov     r8, [rdi]; Source
0x14000a11b  mov     r9, r15; SourceSize
0x14000a11e  call    cs:__imp_memcpy_s
0x14000a124  mov     rbp, [rdi+18h]
0x14000a128  mov     [rdi+18h], rbx
0x14000a12c  test    rbp, rbp
0x14000a12f  jz      short loc_14000A145
0x14000a131  call    cs:__imp_GetProcessHeap
0x14000a137  mov     r8, rbp; lpMem
0x14000a13a  xor     edx, edx; dwFlags
0x14000a13c  mov     rcx, rax; hHeap
0x14000a13f  call    cs:__imp_HeapFree
0x14000a145  lea     rax, [r15+rbx]
0x14000a149  mov     [rdi], rbx
0x14000a14c  mov     [rdi+8], rax
0x14000a150  mov     ecx, esi; dwErrCode
0x14000a152  lea     rax, [r14+rbx]
0x14000a156  mov     [rdi+10h], rax
0x14000a15a  call    cs:__imp_SetLastError
0x14000a160  mov     al, 1
0x14000a162  add     rsp, 28h
0x14000a166  pop     r15
0x14000a168  pop     r14
0x14000a16a  pop     rdi
0x14000a16b  pop     rsi
0x14000a16c  pop     rbp
0x14000a16d  pop     rbx
0x14000a16e  retn
```
