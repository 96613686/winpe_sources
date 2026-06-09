# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000c494`
- end: `0x18000c587`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `243`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b9a8`
- `0x18000c610`

## callees

- `0x18000c494`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000c4de`
- `KERNEL32!HeapFree` at `0x18000c551`
- `KERNEL32!HeapFree` at `0x18000c4de`
- `KERNEL32!HeapFree` at `0x18000c551`
- `KERNEL32!GetProcessHeap` at `0x18000c4ca`
- `KERNEL32!GetProcessHeap` at `0x18000c4fa`
- `KERNEL32!GetProcessHeap` at `0x18000c53d`
- `KERNEL32!GetProcessHeap` at `0x18000c4ca`
- `KERNEL32!GetProcessHeap` at `0x18000c4fa`
- `KERNEL32!GetProcessHeap` at `0x18000c53d`
- `KERNEL32!HeapAlloc` at `0x18000c50f`
- `KERNEL32!HeapAlloc` at `0x18000c50f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
      this[1] = a2;
      result = 1;
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
0x18000c494  mov     [rsp+arg_0], rbx
0x18000c499  mov     [rsp+arg_8], rbp
0x18000c49e  mov     [rsp+arg_10], rsi
0x18000c4a3  push    rdi
0x18000c4a4  sub     rsp, 20h
0x18000c4a8  mov     rbp, rdx
0x18000c4ab  mov     rdi, rcx
0x18000c4ae  test    rdx, rdx
0x18000c4b1  jnz     short loc_18000C4FA
0x18000c4b3  mov     rcx, [rcx]
0x18000c4b6  test    rcx, rcx
0x18000c4b9  jz      short loc_18000C4F3
0x18000c4bb  or      eax, 0FFFFFFFFh
0x18000c4be  lock xadd [rcx], eax
0x18000c4c2  cmp     eax, 1
0x18000c4c5  jnz     short loc_18000C4EA
0x18000c4c7  mov     rbx, [rdi]
0x18000c4ca  call    cs:__imp_GetProcessHeap
0x18000c4d1  nop     dword ptr [rax+rax+00h]
0x18000c4d6  mov     r8, rbx; lpMem
0x18000c4d9  xor     edx, edx; dwFlags
0x18000c4db  mov     rcx, rax; hHeap
0x18000c4de  call    cs:__imp_HeapFree
0x18000c4e5  nop     dword ptr [rax+rax+00h]
0x18000c4ea  and     qword ptr [rdi], 0
0x18000c4ee  and     qword ptr [rdi+8], 0
0x18000c4f3  mov     eax, 1
0x18000c4f8  jmp     short loc_18000C571
0x18000c4fa  call    cs:__imp_GetProcessHeap
0x18000c501  nop     dword ptr [rax+rax+00h]
0x18000c506  mov     rcx, rax; hHeap
0x18000c509  lea     r8, [rbp+4]; dwBytes
0x18000c50d  xor     edx, edx; dwFlags
0x18000c50f  call    cs:__imp_HeapAlloc
0x18000c516  nop     dword ptr [rax+rax+00h]
0x18000c51b  mov     rsi, rax
0x18000c51e  test    rax, rax
0x18000c521  jz      short loc_18000C571
0x18000c523  and     dword ptr [rax], 0
0x18000c526  mov     rcx, [rdi]
0x18000c529  test    rcx, rcx
0x18000c52c  jz      short loc_18000C562
0x18000c52e  or      eax, 0FFFFFFFFh
0x18000c531  lock xadd [rcx], eax
0x18000c535  cmp     eax, 1
0x18000c538  jnz     short loc_18000C55D
0x18000c53a  mov     rbx, [rdi]
0x18000c53d  call    cs:__imp_GetProcessHeap
0x18000c544  nop     dword ptr [rax+rax+00h]
0x18000c549  mov     r8, rbx; lpMem
0x18000c54c  xor     edx, edx; dwFlags
0x18000c54e  mov     rcx, rax; hHeap
0x18000c551  call    cs:__imp_HeapFree
0x18000c558  nop     dword ptr [rax+rax+00h]
0x18000c55d  and     qword ptr [rdi+8], 0
0x18000c562  mov     [rdi], rsi
0x18000c565  mov     [rdi+8], rbp
0x18000c569  mov     eax, 1
0x18000c56e  lock add [rsi], eax
0x18000c571  mov     rbx, [rsp+28h+arg_0]
0x18000c576  mov     rbp, [rsp+28h+arg_8]
0x18000c57b  mov     rsi, [rsp+28h+arg_10]
0x18000c580  add     rsp, 20h
0x18000c584  pop     rdi
0x18000c585  retn
```
