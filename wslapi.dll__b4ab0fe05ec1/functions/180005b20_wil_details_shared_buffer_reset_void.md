# wil::details::shared_buffer::reset(void)

- ea: `0x180005b20`
- end: `0x180005b72`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000351c`
- `0x180005178`
- `0x180005a30`
- `0x180005b80`

## callees

- `0x180005b20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b44`

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
0x180005b20  mov     [rsp+arg_0], rbx
0x180005b25  push    rdi
0x180005b26  sub     rsp, 20h
0x180005b2a  mov     rdi, rcx
0x180005b2d  mov     rcx, [rcx]
0x180005b30  test    rcx, rcx
0x180005b33  jz      short loc_180005B67
0x180005b35  or      eax, 0FFFFFFFFh
0x180005b38  lock xadd [rcx], eax
0x180005b3c  cmp     eax, 1
0x180005b3f  jnz     short loc_180005B58
0x180005b41  mov     rbx, [rdi]
0x180005b44  call    cs:__imp_GetProcessHeap
0x180005b4a  mov     r8, rbx; lpMem
0x180005b4d  xor     edx, edx; dwFlags
0x180005b4f  mov     rcx, rax; hHeap
0x180005b52  call    cs:__imp_HeapFree
0x180005b58  mov     qword ptr [rdi], 0
0x180005b5f  mov     qword ptr [rdi+8], 0
0x180005b67  mov     rbx, [rsp+28h+arg_0]
0x180005b6c  add     rsp, 20h
0x180005b70  pop     rdi
0x180005b71  retn
```
