# I_MinCryptFindRootByKey

- ea: `0x180016d0c`
- end: `0x180016d6f`
- name: `I_MinCryptFindRootByKey`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016f2c`

## callees

- `0x180016d0c`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x180016d45`
- `securekernel!RtlCompareMemory` at `0x180016d45`

## pseudocode

```c
__int64 *__fastcall I_MinCryptFindRootByKey(const void **a1)
{
  __int64 i; // rdi

  for ( i = 0; (unsigned int)i < 0x13; i = (unsigned int)(i + 1) )
  {
    if ( *(_DWORD *)a1 == LODWORD(RootTable[5 * i + 2])
      && RtlCompareMemory(a1[1], (const void *)RootTable[5 * i + 3], *(unsigned int *)a1) == (unsigned int)a1 )
    {
      return &RootTable[5 * i];
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016d0c  push    rbx
0x180016d0e  push    rsi
0x180016d0f  push    rdi
0x180016d10  push    r14
0x180016d12  push    r15
0x180016d14  sub     rsp, 20h
0x180016d18  mov     r14, rcx
0x180016d1b  lea     r15, RootTable
0x180016d22  xor     edi, edi
0x180016d24  cmp     edi, 13h
0x180016d27  jnb     short loc_180016D60
0x180016d29  mov     ecx, [r14]
0x180016d2c  lea     rsi, [rdi+rdi*4]
0x180016d30  cmp     ecx, [r15+rsi*8+10h]
0x180016d35  jnz     short loc_180016D56
0x180016d37  mov     rdx, [r15+rsi*8+18h]; Source2
0x180016d3c  mov     ebx, ecx
0x180016d3e  mov     r8d, ecx; Length
0x180016d41  mov     rcx, [r14+8]; Source1
0x180016d45  call    cs:__imp_RtlCompareMemory
0x180016d4c  nop     dword ptr [rax+rax+00h]
0x180016d51  cmp     rax, rbx
0x180016d54  jz      short loc_180016D5A
0x180016d56  inc     edi
0x180016d58  jmp     short loc_180016D24
0x180016d5a  lea     rax, [r15+rsi*8]
0x180016d5e  jmp     short loc_180016D62
0x180016d60  xor     eax, eax
0x180016d62  add     rsp, 20h
0x180016d66  pop     r15
0x180016d68  pop     r14
0x180016d6a  pop     rdi
0x180016d6b  pop     rsi
0x180016d6c  pop     rbx
0x180016d6d  retn
```
