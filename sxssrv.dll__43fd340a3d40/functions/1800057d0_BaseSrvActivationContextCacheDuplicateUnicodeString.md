# BaseSrvActivationContextCacheDuplicateUnicodeString

- ea: `0x1800057d0`
- end: `0x1800058a3`
- name: `BaseSrvActivationContextCacheDuplicateUnicodeString`
- size: `211`
- prototype: `__int64 __fastcall(__int64, const void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005170`
- `0x1800056a0`

## callees

- `0x1800057d0`
- `0x180006cc1`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005829`
- `ntdll!RtlAllocateHeap` at `0x180005829`

## pseudocode

```c
__int64 __fastcall BaseSrvActivationContextCacheDuplicateUnicodeString(__int64 a1, const void **a2)
{
  size_t v2; // rsi
  __int64 result; // rax
  PVOID Heap; // rax

  v2 = *(unsigned __int16 *)a2;
  if ( (_WORD)v2 )
  {
    if ( (unsigned __int16)(v2 + 2) < (unsigned __int16)v2 )
    {
      *(_WORD *)(a1 + 2) = -1;
      return 3221225621LL;
    }
    else
    {
      *(_WORD *)(a1 + 2) = v2 + 2;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(v2 + 2));
      *(_QWORD *)(a1 + 8) = Heap;
      if ( Heap )
      {
        memcpy_0(Heap, a2[1], v2);
        *(_WORD *)((v2 & 0xFFFFFFFFFFFFFFFEuLL) + *(_QWORD *)(a1 + 8)) = 0;
        result = 0;
        *(_WORD *)a1 = v2;
      }
      else
      {
        return 3221225495LL;
      }
    }
  }
  else
  {
    *(_DWORD *)a1 = 0;
    result = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800057d0  mov     [rsp+arg_8], rbx
0x1800057d5  mov     [rsp+arg_10], rsi
0x1800057da  push    r14
0x1800057dc  sub     rsp, 20h
0x1800057e0  movzx   esi, word ptr [rdx]
0x1800057e3  mov     r14, rdx
0x1800057e6  mov     rbx, rcx
0x1800057e9  test    si, si
0x1800057ec  jnz     short loc_18000580A
0x1800057ee  xor     ecx, ecx
0x1800057f0  mov     [rbx], ecx
0x1800057f2  xor     eax, eax
0x1800057f4  mov     [rbx+8], rcx
0x1800057f8  mov     rbx, [rsp+28h+arg_8]
0x1800057fd  mov     rsi, [rsp+28h+arg_10]
0x180005802  add     rsp, 20h
0x180005806  pop     r14
0x180005808  retn
0x18000580a  lea     eax, [rsi+2]
0x18000580d  cmp     ax, si
0x180005810  jb      short loc_180005886
0x180005812  mov     [rcx+2], ax
0x180005816  xor     edx, edx; Flags
0x180005818  mov     rcx, gs:60h
0x180005821  movzx   r8d, ax; Size
0x180005825  mov     rcx, [rcx+30h]; HeapHandle
0x180005829  call    cs:__imp_RtlAllocateHeap
0x180005830  nop     dword ptr [rax+rax+00h]
0x180005835  mov     [rbx+8], rax
0x180005839  test    rax, rax
0x18000583c  jnz     short loc_180005845
0x18000583e  mov     eax, 0C0000017h
0x180005843  jmp     short loc_180005891
0x180005845  mov     rdx, [r14+8]; Src
0x180005849  mov     r8, rsi; Size
0x18000584c  mov     [rsp+28h+arg_0], rdi
0x180005851  mov     rcx, rax; void *
0x180005854  mov     rdi, rsi
0x180005857  call    memcpy_0
0x18000585c  mov     rax, [rbx+8]
0x180005860  and     rdi, 0FFFFFFFFFFFFFFFEh
0x180005864  xor     ecx, ecx
0x180005866  mov     [rdi+rax], cx
0x18000586a  xor     eax, eax
0x18000586c  mov     rdi, [rsp+28h+arg_0]
0x180005871  mov     [rbx], si
0x180005874  mov     rbx, [rsp+28h+arg_8]
0x180005879  mov     rsi, [rsp+28h+arg_10]
0x18000587e  add     rsp, 20h
0x180005882  pop     r14
0x180005884  retn
0x180005886  mov     word ptr [rcx+2], 0FFFFh
0x18000588c  mov     eax, 0C0000095h
0x180005891  mov     rbx, [rsp+28h+arg_8]
0x180005896  mov     rsi, [rsp+28h+arg_10]
0x18000589b  add     rsp, 20h
0x18000589f  pop     r14
0x1800058a1  retn
```
