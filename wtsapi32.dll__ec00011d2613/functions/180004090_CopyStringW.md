# _CopyStringW

- ea: `0x180004090`
- end: `0x18000413c`
- name: `_CopyStringW`
- size: `172`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d20`
- `0x180005c60`

## callees

- `0x180004090`
- `0x180015582`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800040dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800040dc`

## pseudocode

```c
__int64 __fastcall CopyStringW(_WORD *Src, void **a2, unsigned int *a3)
{
  __int64 v6; // rax
  unsigned int v8; // edi
  __int64 result; // rax

  if ( Src )
  {
    v6 = -1;
    while ( Src[++v6] != 0 )
      ;
    v8 = 2 * v6 + 2;
    result = (__int64)LocalAlloc(0x40u, v8);
    *a2 = (void *)result;
    if ( result )
    {
      if ( a3 )
        *a3 = v8;
      memcpy_0(*a2, Src, v8);
      return 1;
    }
  }
  else
  {
    *a2 = 0;
    result = 1;
    if ( a3 )
      *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004090  mov     [rsp+arg_10], rbx
0x180004095  mov     [rsp+arg_18], r14
0x18000409a  push    r15
0x18000409c  sub     rsp, 20h
0x1800040a0  mov     r15, r8
0x1800040a3  mov     r14, rdx
0x1800040a6  mov     rbx, rcx
0x1800040a9  test    rcx, rcx
0x1800040ac  jz      short loc_180004122
0x1800040ae  mov     [rsp+28h+arg_0], rsi
0x1800040b3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800040ba  mov     [rsp+28h+arg_8], rdi
0x1800040bf  nop
0x1800040c0  cmp     word ptr [rcx+rax*2+2], 0
0x1800040c6  lea     rax, [rax+1]
0x1800040ca  jnz     short loc_1800040C0
0x1800040cc  lea     edi, ds:2[rax*2]
0x1800040d3  mov     ecx, 40h ; '@'; uFlags
0x1800040d8  mov     edx, edi; uBytes
0x1800040da  mov     esi, edi
0x1800040dc  call    cs:__imp_LocalAlloc
0x1800040e2  mov     [r14], rax
0x1800040e5  test    rax, rax
0x1800040e8  jnz     short loc_180004105
0x1800040ea  mov     rsi, [rsp+28h+arg_0]
0x1800040ef  mov     rdi, [rsp+28h+arg_8]
0x1800040f4  mov     rbx, [rsp+28h+arg_10]
0x1800040f9  mov     r14, [rsp+28h+arg_18]
0x1800040fe  add     rsp, 20h
0x180004102  pop     r15
0x180004104  retn
0x180004105  test    r15, r15
0x180004108  jz      short loc_18000410D
0x18000410a  mov     [r15], edi
0x18000410d  mov     rcx, [r14]; void *
0x180004110  mov     r8, rsi; Size
0x180004113  mov     rdx, rbx; Src
0x180004116  call    memcpy_0
0x18000411b  mov     eax, 1
0x180004120  jmp     short loc_1800040EA
0x180004122  mov     qword ptr [rdx], 0
0x180004129  mov     eax, 1
0x18000412e  test    r15, r15
0x180004131  jz      short loc_1800040F4
0x180004133  mov     dword ptr [r8], 0
0x18000413a  jmp     short loc_1800040F4
```
