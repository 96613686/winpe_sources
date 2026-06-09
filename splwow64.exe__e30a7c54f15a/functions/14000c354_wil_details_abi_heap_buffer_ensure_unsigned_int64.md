# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000c354`
- end: `0x14000c426`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a158`
- `0x14000a2f8`
- `0x14000aad4`
- `0x14000b9b0`
- `0x14000bbb8`

## callees

- `0x14000542c`
- `0x140006388`
- `0x14000c354`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000c3f6`
- `KERNEL32!HeapFree` at `0x14000c3f6`
- `KERNEL32!SetLastError` at `0x14000c3b9`
- `KERNEL32!SetLastError` at `0x14000c411`
- `KERNEL32!SetLastError` at `0x14000c3b9`
- `KERNEL32!SetLastError` at `0x14000c411`
- `KERNEL32!GetLastError` at `0x14000c395`
- `KERNEL32!GetLastError` at `0x14000c395`
- `KERNEL32!GetProcessHeap` at `0x14000c3e8`
- `KERNEL32!GetProcessHeap` at `0x14000c3e8`

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
0x14000c354  push    rbx
0x14000c356  push    rbp
0x14000c357  push    rsi
0x14000c358  push    rdi
0x14000c359  push    r14
0x14000c35b  push    r15
0x14000c35d  sub     rsp, 28h
0x14000c361  mov     rdi, rcx
0x14000c364  mov     rbx, rdx
0x14000c367  mov     rcx, [rcx+10h]
0x14000c36b  mov     rax, [rdi+8]
0x14000c36f  sub     rax, [rdi]
0x14000c372  sub     rcx, [rdi]
0x14000c375  add     rax, rdx
0x14000c378  cmp     rax, rcx
0x14000c37b  jb      loc_14000C417
0x14000c381  lea     rax, [rcx+rcx]
0x14000c385  cmp     rdx, rax
0x14000c388  cmovb   rbx, rax
0x14000c38c  cmp     rcx, rbx
0x14000c38f  jnb     loc_14000C417
0x14000c395  call    cs:__imp_GetLastError
0x14000c39b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000c39f  xor     ecx, ecx; dwFlags
0x14000c3a1  mov     esi, eax
0x14000c3a3  lea     r14, [rbx+40h]
0x14000c3a7  mov     rdx, r14; dwBytes
0x14000c3aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c3af  mov     rbx, rax
0x14000c3b2  test    rax, rax
0x14000c3b5  jnz     short loc_14000C3C3
0x14000c3b7  mov     ecx, esi; dwErrCode
0x14000c3b9  call    cs:__imp_SetLastError
0x14000c3bf  xor     al, al
0x14000c3c1  jmp     short loc_14000C419
0x14000c3c3  mov     r15, [rdi+8]
0x14000c3c7  mov     rdx, r14; DestinationSize
0x14000c3ca  sub     r15, [rdi]
0x14000c3cd  mov     rcx, rbx; Destination
0x14000c3d0  mov     r8, [rdi]; Source
0x14000c3d3  mov     r9, r15; SourceSize
0x14000c3d6  call    memcpy_s
0x14000c3db  mov     rbp, [rdi+18h]
0x14000c3df  mov     [rdi+18h], rbx
0x14000c3e3  test    rbp, rbp
0x14000c3e6  jz      short loc_14000C3FC
0x14000c3e8  call    cs:__imp_GetProcessHeap
0x14000c3ee  mov     r8, rbp; lpMem
0x14000c3f1  xor     edx, edx; dwFlags
0x14000c3f3  mov     rcx, rax; hHeap
0x14000c3f6  call    cs:__imp_HeapFree
0x14000c3fc  lea     rax, [r15+rbx]
0x14000c400  mov     [rdi], rbx
0x14000c403  mov     [rdi+8], rax
0x14000c407  mov     ecx, esi; dwErrCode
0x14000c409  lea     rax, [r14+rbx]
0x14000c40d  mov     [rdi+10h], rax
0x14000c411  call    cs:__imp_SetLastError
0x14000c417  mov     al, 1
0x14000c419  add     rsp, 28h
0x14000c41d  pop     r15
0x14000c41f  pop     r14
0x14000c421  pop     rdi
0x14000c422  pop     rsi
0x14000c423  pop     rbp
0x14000c424  pop     rbx
0x14000c425  retn
```
