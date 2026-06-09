# wil::details::shared_buffer::reset(void)

- ea: `0x180009de0`
- end: `0x180009e3f`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `95`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007704`
- `0x1800093b8`
- `0x180009ce0`
- `0x180009e50`

## callees

- `0x180009de0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e18`

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
0x180009de0  mov     [rsp+arg_0], rbx
0x180009de5  push    rdi
0x180009de6  sub     rsp, 20h
0x180009dea  mov     rdi, rcx
0x180009ded  mov     rcx, [rcx]
0x180009df0  test    rcx, rcx
0x180009df3  jz      short loc_180009E33
0x180009df5  or      eax, 0FFFFFFFFh
0x180009df8  lock xadd [rcx], eax
0x180009dfc  cmp     eax, 1
0x180009dff  jnz     short loc_180009E24
0x180009e01  mov     rbx, [rdi]
0x180009e04  call    cs:__imp_GetProcessHeap
0x180009e0b  nop     dword ptr [rax+rax+00h]
0x180009e10  mov     r8, rbx; lpMem
0x180009e13  xor     edx, edx; dwFlags
0x180009e15  mov     rcx, rax; hHeap
0x180009e18  call    cs:__imp_HeapFree
0x180009e1f  nop     dword ptr [rax+rax+00h]
0x180009e24  mov     qword ptr [rdi], 0
0x180009e2b  mov     qword ptr [rdi+8], 0
0x180009e33  mov     rbx, [rsp+28h+arg_0]
0x180009e38  add     rsp, 20h
0x180009e3c  pop     rdi
0x180009e3d  retn
```
