# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180006358`
- end: `0x18000641b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b84`
- `0x180006700`

## callees

- `0x180006358`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800063bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800063bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006391`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006391`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006383`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006383`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063e7`

## pseudocode

```c
__int64 __fastcall wil::details::shared_buffer::create(volatile signed __int32 **this, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rbx
  HANDLE v6; // rax
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // rsi
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    result = (__int64)HeapAlloc(ProcessHeap, 0, (SIZE_T)(a2 + 1));
    v9 = (volatile signed __int32 *)result;
    if ( result )
    {
      *(_DWORD *)result = 0;
      if ( *this )
      {
        if ( _InterlockedExchangeAdd(*this, 0xFFFFFFFF) == 1 )
        {
          v10 = *this;
          v11 = GetProcessHeap();
          HeapFree(v11, 0, (LPVOID)v10);
        }
        this[1] = 0;
      }
      *this = v9;
      result = 1;
      this[1] = a2;
      _InterlockedAdd(v9, 1u);
    }
  }
  else
  {
    v4 = *this;
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 )
      {
        v5 = *this;
        v6 = GetProcessHeap();
        HeapFree(v6, 0, (LPVOID)v5);
      }
      *this = 0;
      this[1] = 0;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180006358  push    rbx
0x18000635a  push    rbp
0x18000635b  push    rsi
0x18000635c  push    rdi
0x18000635d  sub     rsp, 28h
0x180006361  mov     rbp, rdx
0x180006364  mov     rdi, rcx
0x180006367  test    rdx, rdx
0x18000636a  jnz     short loc_1800063AD
0x18000636c  mov     rcx, [rcx]
0x18000636f  test    rcx, rcx
0x180006372  jz      short loc_1800063A6
0x180006374  or      eax, 0FFFFFFFFh
0x180006377  lock xadd [rcx], eax
0x18000637b  cmp     eax, 1
0x18000637e  jnz     short loc_180006397
0x180006380  mov     rbx, [rdi]
0x180006383  call    cs:__imp_GetProcessHeap
0x180006389  mov     r8, rbx; lpMem
0x18000638c  xor     edx, edx; dwFlags
0x18000638e  mov     rcx, rax; hHeap
0x180006391  call    cs:__imp_HeapFree
0x180006397  mov     qword ptr [rdi], 0
0x18000639e  mov     qword ptr [rdi+8], 0
0x1800063a6  mov     eax, 1
0x1800063ab  jmp     short loc_180006412
0x1800063ad  call    cs:__imp_GetProcessHeap
0x1800063b3  lea     r8, [rbp+4]; dwBytes
0x1800063b7  xor     edx, edx; dwFlags
0x1800063b9  mov     rcx, rax; hHeap
0x1800063bc  call    cs:__imp_HeapAlloc
0x1800063c2  mov     rsi, rax
0x1800063c5  test    rax, rax
0x1800063c8  jz      short loc_180006412
0x1800063ca  mov     dword ptr [rax], 0
0x1800063d0  mov     rcx, [rdi]
0x1800063d3  test    rcx, rcx
0x1800063d6  jz      short loc_180006403
0x1800063d8  or      eax, 0FFFFFFFFh
0x1800063db  lock xadd [rcx], eax
0x1800063df  cmp     eax, 1
0x1800063e2  jnz     short loc_1800063FB
0x1800063e4  mov     rbx, [rdi]
0x1800063e7  call    cs:__imp_GetProcessHeap
0x1800063ed  mov     r8, rbx; lpMem
0x1800063f0  xor     edx, edx; dwFlags
0x1800063f2  mov     rcx, rax; hHeap
0x1800063f5  call    cs:__imp_HeapFree
0x1800063fb  mov     qword ptr [rdi+8], 0
0x180006403  mov     [rdi], rsi
0x180006406  mov     eax, 1
0x18000640b  mov     [rdi+8], rbp
0x18000640f  lock add [rsi], eax
0x180006412  add     rsp, 28h
0x180006416  pop     rdi
0x180006417  pop     rsi
0x180006418  pop     rbp
0x180006419  pop     rbx
0x18000641a  retn
```
