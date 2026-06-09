# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180002200`
- end: `0x1800022da`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `218`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000280c`
- `0x180002d90`

## callees

- `0x180002200`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000226f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000226f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002244`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800022a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002244`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800022a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002236`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002260`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000229a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002236`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002260`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000229a`

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
0x180002200  mov     [rsp+arg_0], rbx
0x180002205  mov     [rsp+arg_8], rbp
0x18000220a  mov     [rsp+arg_10], rsi
0x18000220f  push    rdi
0x180002210  sub     rsp, 20h
0x180002214  mov     rbp, rdx
0x180002217  mov     rdi, rcx
0x18000221a  test    rdx, rdx
0x18000221d  jnz     short loc_180002260
0x18000221f  mov     rcx, [rcx]
0x180002222  test    rcx, rcx
0x180002225  jz      short loc_180002259
0x180002227  or      eax, 0FFFFFFFFh
0x18000222a  lock xadd [rcx], eax
0x18000222e  cmp     eax, 1
0x180002231  jnz     short loc_18000224A
0x180002233  mov     rbx, [rdi]
0x180002236  call    cs:__imp_GetProcessHeap
0x18000223c  mov     r8, rbx; lpMem
0x18000223f  xor     edx, edx; dwFlags
0x180002241  mov     rcx, rax; hHeap
0x180002244  call    cs:__imp_HeapFree
0x18000224a  mov     qword ptr [rdi], 0
0x180002251  mov     qword ptr [rdi+8], 0
0x180002259  mov     eax, 1
0x18000225e  jmp     short loc_1800022C5
0x180002260  call    cs:__imp_GetProcessHeap
0x180002266  lea     r8, [rbp+4]; dwBytes
0x18000226a  xor     edx, edx; dwFlags
0x18000226c  mov     rcx, rax; hHeap
0x18000226f  call    cs:__imp_HeapAlloc
0x180002275  mov     rsi, rax
0x180002278  test    rax, rax
0x18000227b  jz      short loc_1800022C5
0x18000227d  mov     dword ptr [rax], 0
0x180002283  mov     rcx, [rdi]
0x180002286  test    rcx, rcx
0x180002289  jz      short loc_1800022B6
0x18000228b  or      eax, 0FFFFFFFFh
0x18000228e  lock xadd [rcx], eax
0x180002292  cmp     eax, 1
0x180002295  jnz     short loc_1800022AE
0x180002297  mov     rbx, [rdi]
0x18000229a  call    cs:__imp_GetProcessHeap
0x1800022a0  mov     r8, rbx; lpMem
0x1800022a3  xor     edx, edx; dwFlags
0x1800022a5  mov     rcx, rax; hHeap
0x1800022a8  call    cs:__imp_HeapFree
0x1800022ae  mov     qword ptr [rdi+8], 0
0x1800022b6  mov     [rdi], rsi
0x1800022b9  mov     eax, 1
0x1800022be  mov     [rdi+8], rbp
0x1800022c2  lock add [rsi], eax
0x1800022c5  mov     rbx, [rsp+28h+arg_0]
0x1800022ca  mov     rbp, [rsp+28h+arg_8]
0x1800022cf  mov     rsi, [rsp+28h+arg_10]
0x1800022d4  add     rsp, 20h
0x1800022d8  pop     rdi
0x1800022d9  retn
```
