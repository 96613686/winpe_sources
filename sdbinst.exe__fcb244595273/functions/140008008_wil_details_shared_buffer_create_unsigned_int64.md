# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140008008`
- end: `0x1400080cb`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400068d0`
- `0x1400083f0`

## callees

- `0x140008008`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000806c`
- `KERNEL32!HeapAlloc` at `0x14000806c`
- `KERNEL32!GetProcessHeap` at `0x140008033`
- `KERNEL32!GetProcessHeap` at `0x14000805d`
- `KERNEL32!GetProcessHeap` at `0x140008097`
- `KERNEL32!GetProcessHeap` at `0x140008033`
- `KERNEL32!GetProcessHeap` at `0x14000805d`
- `KERNEL32!GetProcessHeap` at `0x140008097`
- `KERNEL32!HeapFree` at `0x140008041`
- `KERNEL32!HeapFree` at `0x1400080a5`
- `KERNEL32!HeapFree` at `0x140008041`
- `KERNEL32!HeapFree` at `0x1400080a5`

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
0x140008008  push    rbx
0x14000800a  push    rbp
0x14000800b  push    rsi
0x14000800c  push    rdi
0x14000800d  sub     rsp, 28h
0x140008011  mov     rbp, rdx
0x140008014  mov     rdi, rcx
0x140008017  test    rdx, rdx
0x14000801a  jnz     short loc_14000805D
0x14000801c  mov     rcx, [rcx]
0x14000801f  test    rcx, rcx
0x140008022  jz      short loc_140008056
0x140008024  or      eax, 0FFFFFFFFh
0x140008027  lock xadd [rcx], eax
0x14000802b  cmp     eax, 1
0x14000802e  jnz     short loc_140008047
0x140008030  mov     rbx, [rdi]
0x140008033  call    cs:__imp_GetProcessHeap
0x140008039  mov     r8, rbx; lpMem
0x14000803c  xor     edx, edx; dwFlags
0x14000803e  mov     rcx, rax; hHeap
0x140008041  call    cs:__imp_HeapFree
0x140008047  mov     qword ptr [rdi], 0
0x14000804e  mov     qword ptr [rdi+8], 0
0x140008056  mov     eax, 1
0x14000805b  jmp     short loc_1400080C2
0x14000805d  call    cs:__imp_GetProcessHeap
0x140008063  lea     r8, [rbp+4]; dwBytes
0x140008067  xor     edx, edx; dwFlags
0x140008069  mov     rcx, rax; hHeap
0x14000806c  call    cs:__imp_HeapAlloc
0x140008072  mov     rsi, rax
0x140008075  test    rax, rax
0x140008078  jz      short loc_1400080C2
0x14000807a  mov     dword ptr [rax], 0
0x140008080  mov     rcx, [rdi]
0x140008083  test    rcx, rcx
0x140008086  jz      short loc_1400080B3
0x140008088  or      eax, 0FFFFFFFFh
0x14000808b  lock xadd [rcx], eax
0x14000808f  cmp     eax, 1
0x140008092  jnz     short loc_1400080AB
0x140008094  mov     rbx, [rdi]
0x140008097  call    cs:__imp_GetProcessHeap
0x14000809d  mov     r8, rbx; lpMem
0x1400080a0  xor     edx, edx; dwFlags
0x1400080a2  mov     rcx, rax; hHeap
0x1400080a5  call    cs:__imp_HeapFree
0x1400080ab  mov     qword ptr [rdi+8], 0
0x1400080b3  mov     [rdi], rsi
0x1400080b6  mov     eax, 1
0x1400080bb  mov     [rdi+8], rbp
0x1400080bf  lock add [rsi], eax
0x1400080c2  add     rsp, 28h
0x1400080c6  pop     rdi
0x1400080c7  pop     rsi
0x1400080c8  pop     rbp
0x1400080c9  pop     rbx
0x1400080ca  retn
```
