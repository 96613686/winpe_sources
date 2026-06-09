# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1400062a8`
- end: `0x14000636b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400056e0`
- `0x140006380`

## callees

- `0x1400062a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000630c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000630c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006337`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006337`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006345`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006345`

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
0x1400062a8  push    rbx
0x1400062aa  push    rbp
0x1400062ab  push    rsi
0x1400062ac  push    rdi
0x1400062ad  sub     rsp, 28h
0x1400062b1  mov     rbp, rdx
0x1400062b4  mov     rdi, rcx
0x1400062b7  test    rdx, rdx
0x1400062ba  jnz     short loc_1400062FD
0x1400062bc  mov     rcx, [rcx]
0x1400062bf  test    rcx, rcx
0x1400062c2  jz      short loc_1400062F6
0x1400062c4  or      eax, 0FFFFFFFFh
0x1400062c7  lock xadd [rcx], eax
0x1400062cb  cmp     eax, 1
0x1400062ce  jnz     short loc_1400062E7
0x1400062d0  mov     rbx, [rdi]
0x1400062d3  call    cs:__imp_GetProcessHeap
0x1400062d9  mov     r8, rbx; lpMem
0x1400062dc  xor     edx, edx; dwFlags
0x1400062de  mov     rcx, rax; hHeap
0x1400062e1  call    cs:__imp_HeapFree
0x1400062e7  mov     qword ptr [rdi], 0
0x1400062ee  mov     qword ptr [rdi+8], 0
0x1400062f6  mov     eax, 1
0x1400062fb  jmp     short loc_140006362
0x1400062fd  call    cs:__imp_GetProcessHeap
0x140006303  lea     r8, [rbp+4]; dwBytes
0x140006307  xor     edx, edx; dwFlags
0x140006309  mov     rcx, rax; hHeap
0x14000630c  call    cs:__imp_HeapAlloc
0x140006312  mov     rsi, rax
0x140006315  test    rax, rax
0x140006318  jz      short loc_140006362
0x14000631a  mov     dword ptr [rax], 0
0x140006320  mov     rcx, [rdi]
0x140006323  test    rcx, rcx
0x140006326  jz      short loc_140006353
0x140006328  or      eax, 0FFFFFFFFh
0x14000632b  lock xadd [rcx], eax
0x14000632f  cmp     eax, 1
0x140006332  jnz     short loc_14000634B
0x140006334  mov     rbx, [rdi]
0x140006337  call    cs:__imp_GetProcessHeap
0x14000633d  mov     r8, rbx; lpMem
0x140006340  xor     edx, edx; dwFlags
0x140006342  mov     rcx, rax; hHeap
0x140006345  call    cs:__imp_HeapFree
0x14000634b  mov     qword ptr [rdi+8], 0
0x140006353  mov     [rdi], rsi
0x140006356  mov     eax, 1
0x14000635b  mov     [rdi+8], rbp
0x14000635f  lock add [rsi], eax
0x140006362  add     rsp, 28h
0x140006366  pop     rdi
0x140006367  pop     rsi
0x140006368  pop     rbp
0x140006369  pop     rbx
0x14000636a  retn
```
