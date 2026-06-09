# AllocMem

- ea: `0x140007d00`
- end: `0x140007d52`
- name: `AllocMem`
- size: `82`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x140001174`
- `0x14000228c`
- `0x14000253c`
- `0x140002c90`
- `0x140005108`
- `0x14000745c`
- `0x140009e70`
- `0x14000bc28`
- `0x14000c39c`
- `0x14000cebc`
- `0x14000d0a4`
- `0x14000d3a0`
- `0x14000df0c`
- `0x14000e158`
- `0x14000ea3c`

## callees

- `0x140007d00`
- `0x14000f500`

## import_xrefs

- `NDIS!NdisAllocateMemoryWithTagPriority` at `0x140007d17`
- `NDIS!NdisAllocateMemoryWithTagPriority` at `0x140007d17`

## pseudocode

```c
__int64 __fastcall AllocMem(void *a1, UINT a2, __int64 a3, _QWORD *a4)
{
  PVOID MemoryWithTagPriority; // rax
  PVOID v7; // rbx
  unsigned int v8; // edi

  MemoryWithTagPriority = NdisAllocateMemoryWithTagPriority(a1, a2, 0x46465756u, LowPoolPriority);
  v7 = MemoryWithTagPriority;
  if ( MemoryWithTagPriority )
  {
    v8 = 0;
    memset(MemoryWithTagPriority, 0, a2);
  }
  else
  {
    v8 = -1073741670;
    v7 = 0;
  }
  *a4 = v7;
  return v8;
}

```

## disassembly

```asm
0x140007d00  push    rbx
0x140007d02  push    rbp
0x140007d03  push    rsi
0x140007d04  push    rdi
0x140007d05  sub     rsp, 28h
0x140007d09  mov     rsi, r9
0x140007d0c  mov     ebp, edx
0x140007d0e  xor     r9d, r9d; Priority
0x140007d11  mov     r8d, 46465756h; Tag
0x140007d17  call    cs:__imp_NdisAllocateMemoryWithTagPriority
0x140007d1e  nop     dword ptr [rax+rax+00h]
0x140007d23  mov     rbx, rax
0x140007d26  test    rax, rax
0x140007d29  jz      short loc_140007D49
0x140007d2b  xor     edi, edi
0x140007d2d  mov     r8d, ebp; Size
0x140007d30  xor     edx, edx; Val
0x140007d32  mov     rcx, rax; void *
0x140007d35  call    memset
0x140007d3a  mov     [rsi], rbx
0x140007d3d  mov     eax, edi
0x140007d3f  add     rsp, 28h
0x140007d43  pop     rdi
0x140007d44  pop     rsi
0x140007d45  pop     rbp
0x140007d46  pop     rbx
0x140007d47  retn
0x140007d49  mov     edi, 0C000009Ah
0x140007d4e  xor     ebx, ebx
0x140007d50  jmp     short loc_140007D3A
```
