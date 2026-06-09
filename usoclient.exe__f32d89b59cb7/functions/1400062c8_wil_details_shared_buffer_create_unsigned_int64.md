# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1400062c8`
- end: `0x14000638b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005700`
- `0x1400063a0`

## callees

- `0x1400062c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000632c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000632c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000631d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006357`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000631d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006357`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006301`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006365`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006301`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006365`

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
0x1400062c8  push    rbx
0x1400062ca  push    rbp
0x1400062cb  push    rsi
0x1400062cc  push    rdi
0x1400062cd  sub     rsp, 28h
0x1400062d1  mov     rbp, rdx
0x1400062d4  mov     rdi, rcx
0x1400062d7  test    rdx, rdx
0x1400062da  jnz     short loc_14000631D
0x1400062dc  mov     rcx, [rcx]
0x1400062df  test    rcx, rcx
0x1400062e2  jz      short loc_140006316
0x1400062e4  or      eax, 0FFFFFFFFh
0x1400062e7  lock xadd [rcx], eax
0x1400062eb  cmp     eax, 1
0x1400062ee  jnz     short loc_140006307
0x1400062f0  mov     rbx, [rdi]
0x1400062f3  call    cs:__imp_GetProcessHeap
0x1400062f9  mov     r8, rbx; lpMem
0x1400062fc  xor     edx, edx; dwFlags
0x1400062fe  mov     rcx, rax; hHeap
0x140006301  call    cs:__imp_HeapFree
0x140006307  mov     qword ptr [rdi], 0
0x14000630e  mov     qword ptr [rdi+8], 0
0x140006316  mov     eax, 1
0x14000631b  jmp     short loc_140006382
0x14000631d  call    cs:__imp_GetProcessHeap
0x140006323  lea     r8, [rbp+4]; dwBytes
0x140006327  xor     edx, edx; dwFlags
0x140006329  mov     rcx, rax; hHeap
0x14000632c  call    cs:__imp_HeapAlloc
0x140006332  mov     rsi, rax
0x140006335  test    rax, rax
0x140006338  jz      short loc_140006382
0x14000633a  mov     dword ptr [rax], 0
0x140006340  mov     rcx, [rdi]
0x140006343  test    rcx, rcx
0x140006346  jz      short loc_140006373
0x140006348  or      eax, 0FFFFFFFFh
0x14000634b  lock xadd [rcx], eax
0x14000634f  cmp     eax, 1
0x140006352  jnz     short loc_14000636B
0x140006354  mov     rbx, [rdi]
0x140006357  call    cs:__imp_GetProcessHeap
0x14000635d  mov     r8, rbx; lpMem
0x140006360  xor     edx, edx; dwFlags
0x140006362  mov     rcx, rax; hHeap
0x140006365  call    cs:__imp_HeapFree
0x14000636b  mov     qword ptr [rdi+8], 0
0x140006373  mov     [rdi], rsi
0x140006376  mov     eax, 1
0x14000637b  mov     [rdi+8], rbp
0x14000637f  lock add [rsi], eax
0x140006382  add     rsp, 28h
0x140006386  pop     rdi
0x140006387  pop     rsi
0x140006388  pop     rbp
0x140006389  pop     rbx
0x14000638a  retn
```
