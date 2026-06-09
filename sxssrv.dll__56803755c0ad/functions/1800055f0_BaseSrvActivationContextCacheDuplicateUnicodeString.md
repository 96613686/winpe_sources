# BaseSrvActivationContextCacheDuplicateUnicodeString

- ea: `0x1800055f0`
- end: `0x1800056bf`
- name: `BaseSrvActivationContextCacheDuplicateUnicodeString`
- size: `207`
- prototype: `__int64 __fastcall(__int64, const void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004fa0`
- `0x1800054c0`

## callees

- `0x1800055f0`
- `0x180006c07`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005648`
- `ntdll!RtlAllocateHeap` at `0x180005648`

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
        result = 0;
        *(_WORD *)(*(_QWORD *)(a1 + 8) + 2 * (v2 >> 1)) = 0;
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
    result = 0;
    *(_DWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800055f0  mov     [rsp+arg_8], rsi
0x1800055f5  mov     [rsp+arg_10], rdi
0x1800055fa  push    r14
0x1800055fc  sub     rsp, 20h
0x180005600  movzx   esi, word ptr [rdx]
0x180005603  mov     r14, rdx
0x180005606  mov     rdi, rcx
0x180005609  test    si, si
0x18000560c  jnz     short loc_180005628
0x18000560e  xor     eax, eax
0x180005610  mov     [rcx], eax
0x180005612  mov     [rcx+8], rax
0x180005616  mov     rsi, [rsp+28h+arg_8]
0x18000561b  mov     rdi, [rsp+28h+arg_10]
0x180005620  add     rsp, 20h
0x180005624  pop     r14
0x180005626  retn
0x180005628  lea     eax, [rsi+2]
0x18000562b  cmp     ax, si
0x18000562e  jb      short loc_1800056A2
0x180005630  movzx   r8d, ax; Size
0x180005634  xor     edx, edx; Flags
0x180005636  mov     [rcx+2], r8w
0x18000563b  mov     rcx, gs:60h
0x180005644  mov     rcx, [rcx+30h]; HeapHandle
0x180005648  call    cs:__imp_RtlAllocateHeap
0x18000564f  nop     dword ptr [rax+rax+00h]
0x180005654  mov     [rdi+8], rax
0x180005658  test    rax, rax
0x18000565b  jnz     short loc_180005664
0x18000565d  mov     eax, 0C0000017h
0x180005662  jmp     short loc_1800056AD
0x180005664  mov     rdx, [r14+8]; Src
0x180005668  mov     r8, rsi; Size
0x18000566b  mov     [rsp+28h+arg_0], rbx
0x180005670  mov     rcx, rax; void *
0x180005673  mov     rbx, rsi
0x180005676  call    memcpy_0
0x18000567b  mov     rcx, [rdi+8]
0x18000567f  shr     rbx, 1
0x180005682  xor     eax, eax
0x180005684  mov     [rcx+rbx*2], ax
0x180005688  mov     rbx, [rsp+28h+arg_0]
0x18000568d  mov     [rdi], si
0x180005690  mov     rsi, [rsp+28h+arg_8]
0x180005695  mov     rdi, [rsp+28h+arg_10]
0x18000569a  add     rsp, 20h
0x18000569e  pop     r14
0x1800056a0  retn
0x1800056a2  mov     word ptr [rcx+2], 0FFFFh
0x1800056a8  mov     eax, 0C0000095h
0x1800056ad  mov     rsi, [rsp+28h+arg_8]
0x1800056b2  mov     rdi, [rsp+28h+arg_10]
0x1800056b7  add     rsp, 20h
0x1800056bb  pop     r14
0x1800056bd  retn
```
