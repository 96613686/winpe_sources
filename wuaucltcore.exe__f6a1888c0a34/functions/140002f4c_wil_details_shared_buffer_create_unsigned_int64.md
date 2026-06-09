# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140002f4c`
- end: `0x140003026`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `218`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400032e4`
- `0x140003860`

## callees

- `0x140002f4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140002fbb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140002fbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002ff4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002ff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002fe6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002fe6`

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
0x140002f4c  mov     [rsp+arg_0], rbx
0x140002f51  mov     [rsp+arg_8], rbp
0x140002f56  mov     [rsp+arg_10], rsi
0x140002f5b  push    rdi
0x140002f5c  sub     rsp, 20h
0x140002f60  mov     rbp, rdx
0x140002f63  mov     rdi, rcx
0x140002f66  test    rdx, rdx
0x140002f69  jnz     short loc_140002FAC
0x140002f6b  mov     rcx, [rcx]
0x140002f6e  test    rcx, rcx
0x140002f71  jz      short loc_140002FA5
0x140002f73  or      eax, 0FFFFFFFFh
0x140002f76  lock xadd [rcx], eax
0x140002f7a  cmp     eax, 1
0x140002f7d  jnz     short loc_140002F96
0x140002f7f  mov     rbx, [rdi]
0x140002f82  call    cs:__imp_GetProcessHeap
0x140002f88  mov     r8, rbx; lpMem
0x140002f8b  xor     edx, edx; dwFlags
0x140002f8d  mov     rcx, rax; hHeap
0x140002f90  call    cs:__imp_HeapFree
0x140002f96  mov     qword ptr [rdi], 0
0x140002f9d  mov     qword ptr [rdi+8], 0
0x140002fa5  mov     eax, 1
0x140002faa  jmp     short loc_140003011
0x140002fac  call    cs:__imp_GetProcessHeap
0x140002fb2  lea     r8, [rbp+4]; dwBytes
0x140002fb6  xor     edx, edx; dwFlags
0x140002fb8  mov     rcx, rax; hHeap
0x140002fbb  call    cs:__imp_HeapAlloc
0x140002fc1  mov     rsi, rax
0x140002fc4  test    rax, rax
0x140002fc7  jz      short loc_140003011
0x140002fc9  mov     dword ptr [rax], 0
0x140002fcf  mov     rcx, [rdi]
0x140002fd2  test    rcx, rcx
0x140002fd5  jz      short loc_140003002
0x140002fd7  or      eax, 0FFFFFFFFh
0x140002fda  lock xadd [rcx], eax
0x140002fde  cmp     eax, 1
0x140002fe1  jnz     short loc_140002FFA
0x140002fe3  mov     rbx, [rdi]
0x140002fe6  call    cs:__imp_GetProcessHeap
0x140002fec  mov     r8, rbx; lpMem
0x140002fef  xor     edx, edx; dwFlags
0x140002ff1  mov     rcx, rax; hHeap
0x140002ff4  call    cs:__imp_HeapFree
0x140002ffa  mov     qword ptr [rdi+8], 0
0x140003002  mov     [rdi], rsi
0x140003005  mov     eax, 1
0x14000300a  mov     [rdi+8], rbp
0x14000300e  lock add [rsi], eax
0x140003011  mov     rbx, [rsp+28h+arg_0]
0x140003016  mov     rbp, [rsp+28h+arg_8]
0x14000301b  mov     rsi, [rsp+28h+arg_10]
0x140003020  add     rsp, 20h
0x140003024  pop     rdi
0x140003025  retn
```
