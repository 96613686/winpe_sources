# wil::details::shared_buffer::reset(void)

- ea: `0x180006f00`
- end: `0x180006f52`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800040e4`
- `0x180005fdc`
- `0x180006ddc`
- `0x180006f60`

## callees

- `0x180006f00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f32`

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
0x180006f00  mov     [rsp+arg_0], rbx
0x180006f05  push    rdi
0x180006f06  sub     rsp, 20h
0x180006f0a  mov     rdi, rcx
0x180006f0d  mov     rcx, [rcx]
0x180006f10  test    rcx, rcx
0x180006f13  jz      short loc_180006F47
0x180006f15  or      eax, 0FFFFFFFFh
0x180006f18  lock xadd [rcx], eax
0x180006f1c  cmp     eax, 1
0x180006f1f  jnz     short loc_180006F38
0x180006f21  mov     rbx, [rdi]
0x180006f24  call    cs:__imp_GetProcessHeap
0x180006f2a  mov     r8, rbx; lpMem
0x180006f2d  xor     edx, edx; dwFlags
0x180006f2f  mov     rcx, rax; hHeap
0x180006f32  call    cs:__imp_HeapFree
0x180006f38  mov     qword ptr [rdi], 0
0x180006f3f  mov     qword ptr [rdi+8], 0
0x180006f47  mov     rbx, [rsp+28h+arg_0]
0x180006f4c  add     rsp, 20h
0x180006f50  pop     rdi
0x180006f51  retn
```
