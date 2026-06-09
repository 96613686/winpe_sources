# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180004a0c`
- end: `0x180004ae6`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `218`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004fdc`
- `0x180005560`

## callees

- `0x180004a0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004aa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004aa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ab4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ab4`

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
0x180004a0c  mov     [rsp+arg_0], rbx
0x180004a11  mov     [rsp+arg_8], rbp
0x180004a16  mov     [rsp+arg_10], rsi
0x180004a1b  push    rdi
0x180004a1c  sub     rsp, 20h
0x180004a20  mov     rbp, rdx
0x180004a23  mov     rdi, rcx
0x180004a26  test    rdx, rdx
0x180004a29  jnz     short loc_180004A6C
0x180004a2b  mov     rcx, [rcx]
0x180004a2e  test    rcx, rcx
0x180004a31  jz      short loc_180004A65
0x180004a33  or      eax, 0FFFFFFFFh
0x180004a36  lock xadd [rcx], eax
0x180004a3a  cmp     eax, 1
0x180004a3d  jnz     short loc_180004A56
0x180004a3f  mov     rbx, [rdi]
0x180004a42  call    cs:__imp_GetProcessHeap
0x180004a48  mov     r8, rbx; lpMem
0x180004a4b  xor     edx, edx; dwFlags
0x180004a4d  mov     rcx, rax; hHeap
0x180004a50  call    cs:__imp_HeapFree
0x180004a56  mov     qword ptr [rdi], 0
0x180004a5d  mov     qword ptr [rdi+8], 0
0x180004a65  mov     eax, 1
0x180004a6a  jmp     short loc_180004AD1
0x180004a6c  call    cs:__imp_GetProcessHeap
0x180004a72  lea     r8, [rbp+4]; dwBytes
0x180004a76  xor     edx, edx; dwFlags
0x180004a78  mov     rcx, rax; hHeap
0x180004a7b  call    cs:__imp_HeapAlloc
0x180004a81  mov     rsi, rax
0x180004a84  test    rax, rax
0x180004a87  jz      short loc_180004AD1
0x180004a89  mov     dword ptr [rax], 0
0x180004a8f  mov     rcx, [rdi]
0x180004a92  test    rcx, rcx
0x180004a95  jz      short loc_180004AC2
0x180004a97  or      eax, 0FFFFFFFFh
0x180004a9a  lock xadd [rcx], eax
0x180004a9e  cmp     eax, 1
0x180004aa1  jnz     short loc_180004ABA
0x180004aa3  mov     rbx, [rdi]
0x180004aa6  call    cs:__imp_GetProcessHeap
0x180004aac  mov     r8, rbx; lpMem
0x180004aaf  xor     edx, edx; dwFlags
0x180004ab1  mov     rcx, rax; hHeap
0x180004ab4  call    cs:__imp_HeapFree
0x180004aba  mov     qword ptr [rdi+8], 0
0x180004ac2  mov     [rdi], rsi
0x180004ac5  mov     eax, 1
0x180004aca  mov     [rdi+8], rbp
0x180004ace  lock add [rsi], eax
0x180004ad1  mov     rbx, [rsp+28h+arg_0]
0x180004ad6  mov     rbp, [rsp+28h+arg_8]
0x180004adb  mov     rsi, [rsp+28h+arg_10]
0x180004ae0  add     rsp, 20h
0x180004ae4  pop     rdi
0x180004ae5  retn
```
