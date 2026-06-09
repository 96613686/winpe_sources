# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000d6a0`
- end: `0x18000d763`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bb58`
- `0x18000ddf0`

## callees

- `0x18000d6a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d6d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d73d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d6d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d73d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d72f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d72f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d704`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d704`

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
0x18000d6a0  push    rbx
0x18000d6a2  push    rbp
0x18000d6a3  push    rsi
0x18000d6a4  push    rdi
0x18000d6a5  sub     rsp, 28h
0x18000d6a9  mov     rbp, rdx
0x18000d6ac  mov     rdi, rcx
0x18000d6af  test    rdx, rdx
0x18000d6b2  jnz     short loc_18000D6F5
0x18000d6b4  mov     rcx, [rcx]
0x18000d6b7  test    rcx, rcx
0x18000d6ba  jz      short loc_18000D6EE
0x18000d6bc  or      eax, 0FFFFFFFFh
0x18000d6bf  lock xadd [rcx], eax
0x18000d6c3  cmp     eax, 1
0x18000d6c6  jnz     short loc_18000D6DF
0x18000d6c8  mov     rbx, [rdi]
0x18000d6cb  call    cs:__imp_GetProcessHeap
0x18000d6d1  mov     r8, rbx; lpMem
0x18000d6d4  xor     edx, edx; dwFlags
0x18000d6d6  mov     rcx, rax; hHeap
0x18000d6d9  call    cs:__imp_HeapFree
0x18000d6df  mov     qword ptr [rdi], 0
0x18000d6e6  mov     qword ptr [rdi+8], 0
0x18000d6ee  mov     eax, 1
0x18000d6f3  jmp     short loc_18000D75A
0x18000d6f5  call    cs:__imp_GetProcessHeap
0x18000d6fb  lea     r8, [rbp+4]; dwBytes
0x18000d6ff  xor     edx, edx; dwFlags
0x18000d701  mov     rcx, rax; hHeap
0x18000d704  call    cs:__imp_HeapAlloc
0x18000d70a  mov     rsi, rax
0x18000d70d  test    rax, rax
0x18000d710  jz      short loc_18000D75A
0x18000d712  mov     dword ptr [rax], 0
0x18000d718  mov     rcx, [rdi]
0x18000d71b  test    rcx, rcx
0x18000d71e  jz      short loc_18000D74B
0x18000d720  or      eax, 0FFFFFFFFh
0x18000d723  lock xadd [rcx], eax
0x18000d727  cmp     eax, 1
0x18000d72a  jnz     short loc_18000D743
0x18000d72c  mov     rbx, [rdi]
0x18000d72f  call    cs:__imp_GetProcessHeap
0x18000d735  mov     r8, rbx; lpMem
0x18000d738  xor     edx, edx; dwFlags
0x18000d73a  mov     rcx, rax; hHeap
0x18000d73d  call    cs:__imp_HeapFree
0x18000d743  mov     qword ptr [rdi+8], 0
0x18000d74b  mov     [rdi], rsi
0x18000d74e  mov     eax, 1
0x18000d753  mov     [rdi+8], rbp
0x18000d757  lock add [rsi], eax
0x18000d75a  add     rsp, 28h
0x18000d75e  pop     rdi
0x18000d75f  pop     rsi
0x18000d760  pop     rbp
0x18000d761  pop     rbx
0x18000d762  retn
```
