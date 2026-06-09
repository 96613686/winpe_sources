# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180029100`
- end: `0x1800291e8`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800273a4`
- `0x180029670`

## callees

- `0x180029100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002913f`
- `KERNEL32!HeapFree` at `0x1800291bb`
- `KERNEL32!HeapFree` at `0x18002913f`
- `KERNEL32!HeapFree` at `0x1800291bb`
- `KERNEL32!HeapAlloc` at `0x180029176`
- `KERNEL32!HeapAlloc` at `0x180029176`
- `KERNEL32!GetProcessHeap` at `0x18002912b`
- `KERNEL32!GetProcessHeap` at `0x180029161`
- `KERNEL32!GetProcessHeap` at `0x1800291a7`
- `KERNEL32!GetProcessHeap` at `0x18002912b`
- `KERNEL32!GetProcessHeap` at `0x180029161`
- `KERNEL32!GetProcessHeap` at `0x1800291a7`

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
0x180029100  push    rbx
0x180029102  push    rbp
0x180029103  push    rsi
0x180029104  push    rdi
0x180029105  sub     rsp, 28h
0x180029109  mov     rbp, rdx
0x18002910c  mov     rdi, rcx
0x18002910f  test    rdx, rdx
0x180029112  jnz     short loc_180029161
0x180029114  mov     rcx, [rcx]
0x180029117  test    rcx, rcx
0x18002911a  jz      short loc_18002915A
0x18002911c  or      eax, 0FFFFFFFFh
0x18002911f  lock xadd [rcx], eax
0x180029123  cmp     eax, 1
0x180029126  jnz     short loc_18002914B
0x180029128  mov     rbx, [rdi]
0x18002912b  call    cs:__imp_GetProcessHeap
0x180029132  nop     dword ptr [rax+rax+00h]
0x180029137  mov     r8, rbx; lpMem
0x18002913a  xor     edx, edx; dwFlags
0x18002913c  mov     rcx, rax; hHeap
0x18002913f  call    cs:__imp_HeapFree
0x180029146  nop     dword ptr [rax+rax+00h]
0x18002914b  mov     qword ptr [rdi], 0
0x180029152  mov     qword ptr [rdi+8], 0
0x18002915a  mov     eax, 1
0x18002915f  jmp     short loc_1800291DE
0x180029161  call    cs:__imp_GetProcessHeap
0x180029168  nop     dword ptr [rax+rax+00h]
0x18002916d  lea     r8, [rbp+4]; dwBytes
0x180029171  xor     edx, edx; dwFlags
0x180029173  mov     rcx, rax; hHeap
0x180029176  call    cs:__imp_HeapAlloc
0x18002917d  nop     dword ptr [rax+rax+00h]
0x180029182  mov     rsi, rax
0x180029185  test    rax, rax
0x180029188  jz      short loc_1800291DE
0x18002918a  mov     dword ptr [rax], 0
0x180029190  mov     rcx, [rdi]
0x180029193  test    rcx, rcx
0x180029196  jz      short loc_1800291CF
0x180029198  or      eax, 0FFFFFFFFh
0x18002919b  lock xadd [rcx], eax
0x18002919f  cmp     eax, 1
0x1800291a2  jnz     short loc_1800291C7
0x1800291a4  mov     rbx, [rdi]
0x1800291a7  call    cs:__imp_GetProcessHeap
0x1800291ae  nop     dword ptr [rax+rax+00h]
0x1800291b3  mov     r8, rbx; lpMem
0x1800291b6  xor     edx, edx; dwFlags
0x1800291b8  mov     rcx, rax; hHeap
0x1800291bb  call    cs:__imp_HeapFree
0x1800291c2  nop     dword ptr [rax+rax+00h]
0x1800291c7  mov     qword ptr [rdi+8], 0
0x1800291cf  mov     [rdi], rsi
0x1800291d2  mov     eax, 1
0x1800291d7  mov     [rdi+8], rbp
0x1800291db  lock add [rsi], eax
0x1800291de  add     rsp, 28h
0x1800291e2  pop     rdi
0x1800291e3  pop     rsi
0x1800291e4  pop     rbp
0x1800291e5  pop     rbx
0x1800291e6  retn
```
