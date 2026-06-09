# wil::details::shared_buffer::reset(void)

- ea: `0x18000da3c`
- end: `0x18000da8e`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b8a8`
- `0x18000cff8`
- `0x18000d8cc`
- `0x18000daa0`

## callees

- `0x18000da3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000da6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000da6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000da60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000da60`

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
0x18000da3c  mov     [rsp+arg_0], rbx
0x18000da41  push    rdi
0x18000da42  sub     rsp, 20h
0x18000da46  mov     rdi, rcx
0x18000da49  mov     rcx, [rcx]
0x18000da4c  test    rcx, rcx
0x18000da4f  jz      short loc_18000DA83
0x18000da51  or      eax, 0FFFFFFFFh
0x18000da54  lock xadd [rcx], eax
0x18000da58  cmp     eax, 1
0x18000da5b  jnz     short loc_18000DA74
0x18000da5d  mov     rbx, [rdi]
0x18000da60  call    cs:__imp_GetProcessHeap
0x18000da66  mov     r8, rbx; lpMem
0x18000da69  xor     edx, edx; dwFlags
0x18000da6b  mov     rcx, rax; hHeap
0x18000da6e  call    cs:__imp_HeapFree
0x18000da74  mov     qword ptr [rdi], 0
0x18000da7b  mov     qword ptr [rdi+8], 0
0x18000da83  mov     rbx, [rsp+28h+arg_0]
0x18000da88  add     rsp, 20h
0x18000da8c  pop     rdi
0x18000da8d  retn
```
