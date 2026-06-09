# wil::details::shared_buffer::reset(void)

- ea: `0x180009bf4`
- end: `0x180009c46`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007734`
- `0x180009238`
- `0x180009b04`
- `0x180009c50`

## callees

- `0x180009bf4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c26`

## pseudocode

```c
void __fastcall wil::details::shared_buffer::reset(volatile signed __int32 **this)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rbx
  HANDLE ProcessHeap; // rax

  v2 = *this;
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *this;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v3);
    }
    *this = 0;
    this[1] = 0;
  }
}

```

## disassembly

```asm
0x180009bf4  mov     [rsp+arg_0], rbx
0x180009bf9  push    rdi
0x180009bfa  sub     rsp, 20h
0x180009bfe  mov     rdi, rcx
0x180009c01  mov     rcx, [rcx]
0x180009c04  test    rcx, rcx
0x180009c07  jz      short loc_180009C3B
0x180009c09  or      eax, 0FFFFFFFFh
0x180009c0c  lock xadd [rcx], eax
0x180009c10  cmp     eax, 1
0x180009c13  jnz     short loc_180009C2C
0x180009c15  mov     rbx, [rdi]
0x180009c18  call    cs:__imp_GetProcessHeap
0x180009c1e  mov     r8, rbx; lpMem
0x180009c21  xor     edx, edx; dwFlags
0x180009c23  mov     rcx, rax; hHeap
0x180009c26  call    cs:__imp_HeapFree
0x180009c2c  mov     qword ptr [rdi], 0
0x180009c33  mov     qword ptr [rdi+8], 0
0x180009c3b  mov     rbx, [rsp+28h+arg_0]
0x180009c40  add     rsp, 20h
0x180009c44  pop     rdi
0x180009c45  retn
```
