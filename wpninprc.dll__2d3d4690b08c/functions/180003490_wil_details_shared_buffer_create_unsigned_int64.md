# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180003490`
- end: `0x180003553`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d40`
- `0x180003560`

## callees

- `0x180003490`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000351f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000351f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800034f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800034f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000352d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000352d`

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
0x180003490  push    rbx
0x180003492  push    rbp
0x180003493  push    rsi
0x180003494  push    rdi
0x180003495  sub     rsp, 28h
0x180003499  mov     rbp, rdx
0x18000349c  mov     rdi, rcx
0x18000349f  test    rdx, rdx
0x1800034a2  jnz     short loc_1800034E5
0x1800034a4  mov     rcx, [rcx]
0x1800034a7  test    rcx, rcx
0x1800034aa  jz      short loc_1800034DE
0x1800034ac  or      eax, 0FFFFFFFFh
0x1800034af  lock xadd [rcx], eax
0x1800034b3  cmp     eax, 1
0x1800034b6  jnz     short loc_1800034CF
0x1800034b8  mov     rbx, [rdi]
0x1800034bb  call    cs:__imp_GetProcessHeap
0x1800034c1  mov     r8, rbx; lpMem
0x1800034c4  xor     edx, edx; dwFlags
0x1800034c6  mov     rcx, rax; hHeap
0x1800034c9  call    cs:__imp_HeapFree
0x1800034cf  mov     qword ptr [rdi], 0
0x1800034d6  mov     qword ptr [rdi+8], 0
0x1800034de  mov     eax, 1
0x1800034e3  jmp     short loc_18000354A
0x1800034e5  call    cs:__imp_GetProcessHeap
0x1800034eb  lea     r8, [rbp+4]; dwBytes
0x1800034ef  xor     edx, edx; dwFlags
0x1800034f1  mov     rcx, rax; hHeap
0x1800034f4  call    cs:__imp_HeapAlloc
0x1800034fa  mov     rsi, rax
0x1800034fd  test    rax, rax
0x180003500  jz      short loc_18000354A
0x180003502  mov     dword ptr [rax], 0
0x180003508  mov     rcx, [rdi]
0x18000350b  test    rcx, rcx
0x18000350e  jz      short loc_18000353B
0x180003510  or      eax, 0FFFFFFFFh
0x180003513  lock xadd [rcx], eax
0x180003517  cmp     eax, 1
0x18000351a  jnz     short loc_180003533
0x18000351c  mov     rbx, [rdi]
0x18000351f  call    cs:__imp_GetProcessHeap
0x180003525  mov     r8, rbx; lpMem
0x180003528  xor     edx, edx; dwFlags
0x18000352a  mov     rcx, rax; hHeap
0x18000352d  call    cs:__imp_HeapFree
0x180003533  mov     qword ptr [rdi+8], 0
0x18000353b  mov     [rdi], rsi
0x18000353e  mov     eax, 1
0x180003543  mov     [rdi+8], rbp
0x180003547  lock add [rsi], eax
0x18000354a  add     rsp, 28h
0x18000354e  pop     rdi
0x18000354f  pop     rsi
0x180003550  pop     rbp
0x180003551  pop     rbx
0x180003552  retn
```
