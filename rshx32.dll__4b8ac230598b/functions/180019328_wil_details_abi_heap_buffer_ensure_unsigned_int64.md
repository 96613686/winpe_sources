# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180019328`
- end: `0x1800193fb`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180018770`
- `0x180018da4`
- `0x18001b1b0`
- `0x18001b784`
- `0x18001c700`

## callees

- `0x180004fe8`
- `0x180019328`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800193aa`
- `msvcrt!memcpy_s` at `0x1800193aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800193bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800193bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800193cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800193cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001938d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800193e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001938d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800193e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019369`

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
0x180019328  push    rbx
0x18001932a  push    rbp
0x18001932b  push    rsi
0x18001932c  push    rdi
0x18001932d  push    r14
0x18001932f  push    r15
0x180019331  sub     rsp, 28h
0x180019335  mov     rdi, rcx
0x180019338  mov     rbx, rdx
0x18001933b  mov     rcx, [rcx+10h]
0x18001933f  mov     rax, [rdi+8]
0x180019343  sub     rax, [rdi]
0x180019346  sub     rcx, [rdi]
0x180019349  add     rax, rdx
0x18001934c  cmp     rax, rcx
0x18001934f  jb      loc_1800193EC
0x180019355  lea     rax, [rcx+rcx]
0x180019359  cmp     rdx, rax
0x18001935c  cmovb   rbx, rax
0x180019360  cmp     rcx, rbx
0x180019363  jnb     loc_1800193EC
0x180019369  call    cs:__imp_GetLastError
0x18001936f  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180019373  xor     ecx, ecx; dwFlags
0x180019375  mov     esi, eax
0x180019377  lea     r14, [rbx+40h]
0x18001937b  mov     rdx, r14; dwBytes
0x18001937e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180019383  mov     rbx, rax
0x180019386  test    rax, rax
0x180019389  jnz     short loc_180019397
0x18001938b  mov     ecx, esi; dwErrCode
0x18001938d  call    cs:__imp_SetLastError
0x180019393  xor     al, al
0x180019395  jmp     short loc_1800193EE
0x180019397  mov     r15, [rdi+8]
0x18001939b  mov     rdx, r14; DestinationSize
0x18001939e  sub     r15, [rdi]
0x1800193a1  mov     rcx, rbx; Destination
0x1800193a4  mov     r8, [rdi]; Source
0x1800193a7  mov     r9, r15; SourceSize
0x1800193aa  call    cs:__imp_memcpy_s
0x1800193b0  mov     rbp, [rdi+18h]
0x1800193b4  mov     [rdi+18h], rbx
0x1800193b8  test    rbp, rbp
0x1800193bb  jz      short loc_1800193D1
0x1800193bd  call    cs:__imp_GetProcessHeap
0x1800193c3  mov     r8, rbp; lpMem
0x1800193c6  xor     edx, edx; dwFlags
0x1800193c8  mov     rcx, rax; hHeap
0x1800193cb  call    cs:__imp_HeapFree
0x1800193d1  lea     rax, [r15+rbx]
0x1800193d5  mov     [rdi], rbx
0x1800193d8  mov     [rdi+8], rax
0x1800193dc  mov     ecx, esi; dwErrCode
0x1800193de  lea     rax, [r14+rbx]
0x1800193e2  mov     [rdi+10h], rax
0x1800193e6  call    cs:__imp_SetLastError
0x1800193ec  mov     al, 1
0x1800193ee  add     rsp, 28h
0x1800193f2  pop     r15
0x1800193f4  pop     r14
0x1800193f6  pop     rdi
0x1800193f7  pop     rsi
0x1800193f8  pop     rbp
0x1800193f9  pop     rbx
0x1800193fa  retn
```
