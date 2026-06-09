# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180009ed8`
- end: `0x180009f9b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009070`
- `0x18000a2c0`

## callees

- `0x180009ed8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f75`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f3c`

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
0x180009ed8  push    rbx
0x180009eda  push    rbp
0x180009edb  push    rsi
0x180009edc  push    rdi
0x180009edd  sub     rsp, 28h
0x180009ee1  mov     rbp, rdx
0x180009ee4  mov     rdi, rcx
0x180009ee7  test    rdx, rdx
0x180009eea  jnz     short loc_180009F2D
0x180009eec  mov     rcx, [rcx]
0x180009eef  test    rcx, rcx
0x180009ef2  jz      short loc_180009F26
0x180009ef4  or      eax, 0FFFFFFFFh
0x180009ef7  lock xadd [rcx], eax
0x180009efb  cmp     eax, 1
0x180009efe  jnz     short loc_180009F17
0x180009f00  mov     rbx, [rdi]
0x180009f03  call    cs:__imp_GetProcessHeap
0x180009f09  mov     r8, rbx; lpMem
0x180009f0c  xor     edx, edx; dwFlags
0x180009f0e  mov     rcx, rax; hHeap
0x180009f11  call    cs:__imp_HeapFree
0x180009f17  mov     qword ptr [rdi], 0
0x180009f1e  mov     qword ptr [rdi+8], 0
0x180009f26  mov     eax, 1
0x180009f2b  jmp     short loc_180009F92
0x180009f2d  call    cs:__imp_GetProcessHeap
0x180009f33  lea     r8, [rbp+4]; dwBytes
0x180009f37  xor     edx, edx; dwFlags
0x180009f39  mov     rcx, rax; hHeap
0x180009f3c  call    cs:__imp_HeapAlloc
0x180009f42  mov     rsi, rax
0x180009f45  test    rax, rax
0x180009f48  jz      short loc_180009F92
0x180009f4a  mov     dword ptr [rax], 0
0x180009f50  mov     rcx, [rdi]
0x180009f53  test    rcx, rcx
0x180009f56  jz      short loc_180009F83
0x180009f58  or      eax, 0FFFFFFFFh
0x180009f5b  lock xadd [rcx], eax
0x180009f5f  cmp     eax, 1
0x180009f62  jnz     short loc_180009F7B
0x180009f64  mov     rbx, [rdi]
0x180009f67  call    cs:__imp_GetProcessHeap
0x180009f6d  mov     r8, rbx; lpMem
0x180009f70  xor     edx, edx; dwFlags
0x180009f72  mov     rcx, rax; hHeap
0x180009f75  call    cs:__imp_HeapFree
0x180009f7b  mov     qword ptr [rdi+8], 0
0x180009f83  mov     [rdi], rsi
0x180009f86  mov     eax, 1
0x180009f8b  mov     [rdi+8], rbp
0x180009f8f  lock add [rsi], eax
0x180009f92  add     rsp, 28h
0x180009f96  pop     rdi
0x180009f97  pop     rsi
0x180009f98  pop     rbp
0x180009f99  pop     rbx
0x180009f9a  retn
```
