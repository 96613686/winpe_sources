# CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::Add(CCabDecompressor * const &,ulong *)

- ea: `0x14001a620`
- end: `0x14001a6d8`
- name: `?Add@?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@UEAAJAEBQEAVCCabDecompressor@@PEAK@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000d454`
- `0x14000d480`
- `0x14001a620`

## pseudocode

```c
__int64 __fastcall CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::Add(
        __int64 a1,
        _QWORD *a2,
        _DWORD *a3)
{
  void **v3; // rsi
  unsigned int v4; // eax
  unsigned int v5; // ebp
  unsigned int v6; // ebx
  unsigned int v10; // eax
  SIZE_T v11; // rdx
  void *v12; // rax
  __int64 v13; // r8
  _QWORD *v14; // rdx

  v3 = (void **)(a1 + 8);
  v4 = *(_DWORD *)(a1 + 16);
  v5 = *(_DWORD *)(a1 + 20) + 1;
  v6 = 0;
  if ( v4 < v5 || !*v3 )
  {
    if ( v5 < 8 )
      v5 = 8;
    v10 = 2 * v4;
    if ( v10 >= v5 )
      v5 = v10;
    v11 = 8 * v5;
    if ( *v3 )
      v12 = SusReAlloc(*v3, v11);
    else
      v12 = SusAlloc((unsigned int)v11);
    if ( !v12 )
      return (unsigned int)-2147024882;
    *v3 = v12;
    v3 = (void **)(a1 + 8);
    *(_DWORD *)(a1 + 16) = v5;
  }
  if ( a3 )
    *a3 = *(_DWORD *)(a1 + 20);
  v13 = *(unsigned int *)(a1 + 20);
  v14 = *v3;
  *(_DWORD *)(a1 + 20) = v13 + 1;
  v14[v13] = *a2;
  return v6;
}

```

## disassembly

```asm
0x14001a620  mov     [rsp+arg_0], rbx
0x14001a625  mov     [rsp+arg_8], rbp
0x14001a62a  mov     [rsp+arg_10], rsi
0x14001a62f  push    rdi
0x14001a630  push    r14
0x14001a632  push    r15
0x14001a634  sub     rsp, 20h
0x14001a638  mov     ebp, [rcx+14h]
0x14001a63b  lea     rsi, [rcx+8]
0x14001a63f  mov     eax, [rcx+10h]
0x14001a642  inc     ebp
0x14001a644  xor     ebx, ebx
0x14001a646  mov     r14, r8
0x14001a649  mov     r15, rdx
0x14001a64c  mov     rdi, rcx
0x14001a64f  cmp     eax, ebp
0x14001a651  jb      short loc_14001A658
0x14001a653  cmp     [rsi], rbx
0x14001a656  jnz     short loc_14001A69C
0x14001a658  mov     ecx, 8
0x14001a65d  cmp     ebp, ecx
0x14001a65f  cmovb   ebp, ecx
0x14001a662  add     eax, eax
0x14001a664  cmp     eax, ebp
0x14001a666  cmovnb  ebp, eax
0x14001a669  lea     edx, ds:0[rbp*8]; dwBytes
0x14001a670  cmp     [rsi], rbx
0x14001a673  jnz     short loc_14001A67E
0x14001a675  mov     ecx, edx; unsigned __int64
0x14001a677  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x14001a67c  jmp     short loc_14001A686
0x14001a67e  mov     rcx, [rsi]; lpMem
0x14001a681  call    ?SusReAlloc@@YAPEAXPEAX_K@Z; SusReAlloc(void *,unsigned __int64)
0x14001a686  test    rax, rax
0x14001a689  jnz     short loc_14001A692
0x14001a68b  mov     ebx, 8007000Eh
0x14001a690  jmp     short loc_14001A6BD
0x14001a692  mov     [rsi], rax
0x14001a695  lea     rsi, [rdi+8]
0x14001a699  mov     [rdi+10h], ebp
0x14001a69c  test    r14, r14
0x14001a69f  jz      short loc_14001A6A7
0x14001a6a1  mov     ecx, [rdi+14h]
0x14001a6a4  mov     [r14], ecx
0x14001a6a7  mov     edx, [rdi+14h]
0x14001a6aa  mov     r8d, edx
0x14001a6ad  lea     ecx, [rdx+1]
0x14001a6b0  mov     rdx, [rsi]
0x14001a6b3  mov     [rdi+14h], ecx
0x14001a6b6  mov     rcx, [r15]
0x14001a6b9  mov     [rdx+r8*8], rcx
0x14001a6bd  mov     rbp, [rsp+38h+arg_8]
0x14001a6c2  mov     eax, ebx
0x14001a6c4  mov     rbx, [rsp+38h+arg_0]
0x14001a6c9  mov     rsi, [rsp+38h+arg_10]
0x14001a6ce  add     rsp, 20h
0x14001a6d2  pop     r15
0x14001a6d4  pop     r14
0x14001a6d6  pop     rdi
0x14001a6d7  retn
```
