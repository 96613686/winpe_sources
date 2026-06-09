# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1400070e8`
- end: `0x1400071ab`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006180`
- `0x1400074e0`

## callees

- `0x1400070e8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140007113`
- `KERNEL32!GetProcessHeap` at `0x14000713d`
- `KERNEL32!GetProcessHeap` at `0x140007177`
- `KERNEL32!GetProcessHeap` at `0x140007113`
- `KERNEL32!GetProcessHeap` at `0x14000713d`
- `KERNEL32!GetProcessHeap` at `0x140007177`
- `KERNEL32!HeapFree` at `0x140007121`
- `KERNEL32!HeapFree` at `0x140007185`
- `KERNEL32!HeapFree` at `0x140007121`
- `KERNEL32!HeapFree` at `0x140007185`
- `KERNEL32!HeapAlloc` at `0x14000714c`
- `KERNEL32!HeapAlloc` at `0x14000714c`

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
0x1400070e8  push    rbx
0x1400070ea  push    rbp
0x1400070eb  push    rsi
0x1400070ec  push    rdi
0x1400070ed  sub     rsp, 28h
0x1400070f1  mov     rbp, rdx
0x1400070f4  mov     rdi, rcx
0x1400070f7  test    rdx, rdx
0x1400070fa  jnz     short loc_14000713D
0x1400070fc  mov     rcx, [rcx]
0x1400070ff  test    rcx, rcx
0x140007102  jz      short loc_140007136
0x140007104  or      eax, 0FFFFFFFFh
0x140007107  lock xadd [rcx], eax
0x14000710b  cmp     eax, 1
0x14000710e  jnz     short loc_140007127
0x140007110  mov     rbx, [rdi]
0x140007113  call    cs:__imp_GetProcessHeap
0x140007119  mov     r8, rbx; lpMem
0x14000711c  xor     edx, edx; dwFlags
0x14000711e  mov     rcx, rax; hHeap
0x140007121  call    cs:__imp_HeapFree
0x140007127  mov     qword ptr [rdi], 0
0x14000712e  mov     qword ptr [rdi+8], 0
0x140007136  mov     eax, 1
0x14000713b  jmp     short loc_1400071A2
0x14000713d  call    cs:__imp_GetProcessHeap
0x140007143  lea     r8, [rbp+4]; dwBytes
0x140007147  xor     edx, edx; dwFlags
0x140007149  mov     rcx, rax; hHeap
0x14000714c  call    cs:__imp_HeapAlloc
0x140007152  mov     rsi, rax
0x140007155  test    rax, rax
0x140007158  jz      short loc_1400071A2
0x14000715a  mov     dword ptr [rax], 0
0x140007160  mov     rcx, [rdi]
0x140007163  test    rcx, rcx
0x140007166  jz      short loc_140007193
0x140007168  or      eax, 0FFFFFFFFh
0x14000716b  lock xadd [rcx], eax
0x14000716f  cmp     eax, 1
0x140007172  jnz     short loc_14000718B
0x140007174  mov     rbx, [rdi]
0x140007177  call    cs:__imp_GetProcessHeap
0x14000717d  mov     r8, rbx; lpMem
0x140007180  xor     edx, edx; dwFlags
0x140007182  mov     rcx, rax; hHeap
0x140007185  call    cs:__imp_HeapFree
0x14000718b  mov     qword ptr [rdi+8], 0
0x140007193  mov     [rdi], rsi
0x140007196  mov     eax, 1
0x14000719b  mov     [rdi+8], rbp
0x14000719f  lock add [rsi], eax
0x1400071a2  add     rsp, 28h
0x1400071a6  pop     rdi
0x1400071a7  pop     rsi
0x1400071a8  pop     rbp
0x1400071a9  pop     rbx
0x1400071aa  retn
```
