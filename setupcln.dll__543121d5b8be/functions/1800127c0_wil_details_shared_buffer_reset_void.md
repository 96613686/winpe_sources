# wil::details::shared_buffer::reset(void)

- ea: `0x1800127c0`
- end: `0x180012812`
- name: `?reset@shared_buffer@details@wil@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dae4`
- `0x180010fac`
- `0x180011e98`
- `0x180012820`

## callees

- `0x1800127c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800127e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800127e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800127f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800127f2`

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
0x1800127c0  mov     [rsp+arg_0], rbx
0x1800127c5  push    rdi
0x1800127c6  sub     rsp, 20h
0x1800127ca  mov     rdi, rcx
0x1800127cd  mov     rcx, [rcx]
0x1800127d0  test    rcx, rcx
0x1800127d3  jz      short loc_180012807
0x1800127d5  or      eax, 0FFFFFFFFh
0x1800127d8  lock xadd [rcx], eax
0x1800127dc  cmp     eax, 1
0x1800127df  jnz     short loc_1800127F8
0x1800127e1  mov     rbx, [rdi]
0x1800127e4  call    cs:__imp_GetProcessHeap
0x1800127ea  mov     r8, rbx; lpMem
0x1800127ed  xor     edx, edx; dwFlags
0x1800127ef  mov     rcx, rax; hHeap
0x1800127f2  call    cs:__imp_HeapFree
0x1800127f8  mov     qword ptr [rdi], 0
0x1800127ff  mov     qword ptr [rdi+8], 0
0x180012807  mov     rbx, [rsp+28h+arg_0]
0x18001280c  add     rsp, 20h
0x180012810  pop     rdi
0x180012811  retn
```
