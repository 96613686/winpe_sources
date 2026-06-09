# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000c16c`
- end: `0x14000c23f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140008be0`
- `0x140008d70`
- `0x140009794`
- `0x14000ac68`
- `0x14000ae38`

## callees

- `0x140003eb8`
- `0x14000c16c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000c20f`
- `KERNEL32!HeapFree` at `0x14000c20f`
- `KERNEL32!GetLastError` at `0x14000c1ad`
- `KERNEL32!GetLastError` at `0x14000c1ad`
- `KERNEL32!SetLastError` at `0x14000c1d1`
- `KERNEL32!SetLastError` at `0x14000c22a`
- `KERNEL32!SetLastError` at `0x14000c1d1`
- `KERNEL32!SetLastError` at `0x14000c22a`
- `KERNEL32!GetProcessHeap` at `0x14000c201`
- `KERNEL32!GetProcessHeap` at `0x14000c201`
- `msvcrt!memcpy_s` at `0x14000c1ee`
- `msvcrt!memcpy_s` at `0x14000c1ee`

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
0x14000c16c  push    rbx
0x14000c16e  push    rbp
0x14000c16f  push    rsi
0x14000c170  push    rdi
0x14000c171  push    r14
0x14000c173  push    r15
0x14000c175  sub     rsp, 28h
0x14000c179  mov     rdi, rcx
0x14000c17c  mov     rbx, rdx
0x14000c17f  mov     rcx, [rcx+10h]
0x14000c183  mov     rax, [rdi+8]
0x14000c187  sub     rax, [rdi]
0x14000c18a  sub     rcx, [rdi]
0x14000c18d  add     rax, rdx
0x14000c190  cmp     rax, rcx
0x14000c193  jb      loc_14000C230
0x14000c199  lea     rax, [rcx+rcx]
0x14000c19d  cmp     rdx, rax
0x14000c1a0  cmovb   rbx, rax
0x14000c1a4  cmp     rcx, rbx
0x14000c1a7  jnb     loc_14000C230
0x14000c1ad  call    cs:__imp_GetLastError
0x14000c1b3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000c1b7  xor     ecx, ecx; dwFlags
0x14000c1b9  mov     esi, eax
0x14000c1bb  lea     r14, [rbx+40h]
0x14000c1bf  mov     rdx, r14; dwBytes
0x14000c1c2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c1c7  mov     rbx, rax
0x14000c1ca  test    rax, rax
0x14000c1cd  jnz     short loc_14000C1DB
0x14000c1cf  mov     ecx, esi; dwErrCode
0x14000c1d1  call    cs:__imp_SetLastError
0x14000c1d7  xor     al, al
0x14000c1d9  jmp     short loc_14000C232
0x14000c1db  mov     r15, [rdi+8]
0x14000c1df  mov     rdx, r14; DestinationSize
0x14000c1e2  sub     r15, [rdi]
0x14000c1e5  mov     rcx, rbx; Destination
0x14000c1e8  mov     r8, [rdi]; Source
0x14000c1eb  mov     r9, r15; SourceSize
0x14000c1ee  call    cs:__imp_memcpy_s
0x14000c1f4  mov     rbp, [rdi+18h]
0x14000c1f8  mov     [rdi+18h], rbx
0x14000c1fc  test    rbp, rbp
0x14000c1ff  jz      short loc_14000C215
0x14000c201  call    cs:__imp_GetProcessHeap
0x14000c207  mov     r8, rbp; lpMem
0x14000c20a  xor     edx, edx; dwFlags
0x14000c20c  mov     rcx, rax; hHeap
0x14000c20f  call    cs:__imp_HeapFree
0x14000c215  lea     rax, [r15+rbx]
0x14000c219  mov     [rdi], rbx
0x14000c21c  mov     [rdi+8], rax
0x14000c220  mov     ecx, esi; dwErrCode
0x14000c222  lea     rax, [r14+rbx]
0x14000c226  mov     [rdi+10h], rax
0x14000c22a  call    cs:__imp_SetLastError
0x14000c230  mov     al, 1
0x14000c232  add     rsp, 28h
0x14000c236  pop     r15
0x14000c238  pop     r14
0x14000c23a  pop     rdi
0x14000c23b  pop     rsi
0x14000c23c  pop     rbp
0x14000c23d  pop     rbx
0x14000c23e  retn
```
