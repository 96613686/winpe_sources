# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180003830`
- end: `0x1800038f3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030e4`
- `0x180003900`

## callees

- `0x180003830`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003894`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003894`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003869`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003869`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000385b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000385b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038bf`

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
0x180003830  push    rbx
0x180003832  push    rbp
0x180003833  push    rsi
0x180003834  push    rdi
0x180003835  sub     rsp, 28h
0x180003839  mov     rbp, rdx
0x18000383c  mov     rdi, rcx
0x18000383f  test    rdx, rdx
0x180003842  jnz     short loc_180003885
0x180003844  mov     rcx, [rcx]
0x180003847  test    rcx, rcx
0x18000384a  jz      short loc_18000387E
0x18000384c  or      eax, 0FFFFFFFFh
0x18000384f  lock xadd [rcx], eax
0x180003853  cmp     eax, 1
0x180003856  jnz     short loc_18000386F
0x180003858  mov     rbx, [rdi]
0x18000385b  call    cs:__imp_GetProcessHeap
0x180003861  mov     r8, rbx; lpMem
0x180003864  xor     edx, edx; dwFlags
0x180003866  mov     rcx, rax; hHeap
0x180003869  call    cs:__imp_HeapFree
0x18000386f  mov     qword ptr [rdi], 0
0x180003876  mov     qword ptr [rdi+8], 0
0x18000387e  mov     eax, 1
0x180003883  jmp     short loc_1800038EA
0x180003885  call    cs:__imp_GetProcessHeap
0x18000388b  lea     r8, [rbp+4]; dwBytes
0x18000388f  xor     edx, edx; dwFlags
0x180003891  mov     rcx, rax; hHeap
0x180003894  call    cs:__imp_HeapAlloc
0x18000389a  mov     rsi, rax
0x18000389d  test    rax, rax
0x1800038a0  jz      short loc_1800038EA
0x1800038a2  mov     dword ptr [rax], 0
0x1800038a8  mov     rcx, [rdi]
0x1800038ab  test    rcx, rcx
0x1800038ae  jz      short loc_1800038DB
0x1800038b0  or      eax, 0FFFFFFFFh
0x1800038b3  lock xadd [rcx], eax
0x1800038b7  cmp     eax, 1
0x1800038ba  jnz     short loc_1800038D3
0x1800038bc  mov     rbx, [rdi]
0x1800038bf  call    cs:__imp_GetProcessHeap
0x1800038c5  mov     r8, rbx; lpMem
0x1800038c8  xor     edx, edx; dwFlags
0x1800038ca  mov     rcx, rax; hHeap
0x1800038cd  call    cs:__imp_HeapFree
0x1800038d3  mov     qword ptr [rdi+8], 0
0x1800038db  mov     [rdi], rsi
0x1800038de  mov     eax, 1
0x1800038e3  mov     [rdi+8], rbp
0x1800038e7  lock add [rsi], eax
0x1800038ea  add     rsp, 28h
0x1800038ee  pop     rdi
0x1800038ef  pop     rsi
0x1800038f0  pop     rbp
0x1800038f1  pop     rbx
0x1800038f2  retn
```
