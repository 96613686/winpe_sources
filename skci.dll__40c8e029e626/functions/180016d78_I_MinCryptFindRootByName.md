# I_MinCryptFindRootByName

- ea: `0x180016d78`
- end: `0x180016e40`
- name: `I_MinCryptFindRootByName`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016f2c`

## callees

- `0x180016d78`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x180016dc2`
- `securekernel!RtlCompareMemory` at `0x180016e16`
- `securekernel!RtlCompareMemory` at `0x180016dc2`
- `securekernel!RtlCompareMemory` at `0x180016e16`

## pseudocode

```c
__int64 *__fastcall I_MinCryptFindRootByName(const void **a1, __int64 a2)
{
  __int64 i; // rdi
  __int64 j; // rdi

  for ( i = 0; (unsigned int)i < 0x13; i = (unsigned int)(i + 1) )
  {
    if ( *(_DWORD *)a1 == LODWORD(RootTable[5 * i])
      && RtlCompareMemory(a1[1], (&off_1800529F8)[5 * i], *(unsigned int *)a1) == (unsigned int)a1 )
    {
      return &RootTable[5 * i];
    }
  }
  if ( a2 && (*(_DWORD *)(a2 + 4) & 0x80u) != 0 )
  {
    for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
    {
      if ( *(_DWORD *)a1 == LODWORD(AltRootTable[5 * j])
        && RtlCompareMemory(a1[1], *(&off_180052438 + 5 * j), *(unsigned int *)a1) == (unsigned int)a1 )
      {
        return &AltRootTable[5 * j];
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016d78  push    rbx
0x180016d7a  push    rbp
0x180016d7b  push    rsi
0x180016d7c  push    rdi
0x180016d7d  push    r14
0x180016d7f  push    r15
0x180016d81  sub     rsp, 28h
0x180016d85  mov     rsi, rdx
0x180016d88  lea     r15, cs:180000000h
0x180016d8f  mov     r14, rcx
0x180016d92  xor     edi, edi
0x180016d94  cmp     edi, 13h
0x180016d97  jnb     short loc_180016DDC
0x180016d99  mov     ecx, [r14]
0x180016d9c  lea     rdx, [rdi+rdi*4]
0x180016da0  lea     rbp, rva RootTable[r15]
0x180016da7  lea     rbp, [rbp+rdx*8+0]
0x180016dac  cmp     ecx, [rbp+0]
0x180016daf  jnz     short loc_180016DD3
0x180016db1  mov     rdx, ds:rva off_1800529F8[r15+rdx*8]; Source2
0x180016db9  mov     ebx, ecx
0x180016dbb  mov     r8d, ecx; Length
0x180016dbe  mov     rcx, [r14+8]; Source1
0x180016dc2  call    cs:__imp_RtlCompareMemory
0x180016dc9  nop     dword ptr [rax+rax+00h]
0x180016dce  cmp     rax, rbx
0x180016dd1  jz      short loc_180016DD7
0x180016dd3  inc     edi
0x180016dd5  jmp     short loc_180016D94
0x180016dd7  mov     rax, rbp
0x180016dda  jmp     short loc_180016E32
0x180016ddc  test    rsi, rsi
0x180016ddf  jz      short loc_180016E30
0x180016de1  mov     eax, [rsi+4]
0x180016de4  test    al, al
0x180016de6  jns     short loc_180016E30
0x180016de8  xor     edi, edi
0x180016dea  cmp     edi, 2
0x180016ded  jnb     short loc_180016E30
0x180016def  mov     ecx, [r14]
0x180016df2  lea     rdx, [rdi+rdi*4]
0x180016df6  lea     rsi, rva AltRootTable[r15]
0x180016dfd  lea     rsi, [rsi+rdx*8]
0x180016e01  cmp     ecx, [rsi]
0x180016e03  jnz     short loc_180016E27
0x180016e05  mov     rdx, ds:rva off_180052438[r15+rdx*8]; Source2
0x180016e0d  mov     ebx, ecx
0x180016e0f  mov     r8d, ecx; Length
0x180016e12  mov     rcx, [r14+8]; Source1
0x180016e16  call    cs:__imp_RtlCompareMemory
0x180016e1d  nop     dword ptr [rax+rax+00h]
0x180016e22  cmp     rax, rbx
0x180016e25  jz      short loc_180016E2B
0x180016e27  inc     edi
0x180016e29  jmp     short loc_180016DEA
0x180016e2b  mov     rax, rsi
0x180016e2e  jmp     short loc_180016E32
0x180016e30  xor     eax, eax
0x180016e32  add     rsp, 28h
0x180016e36  pop     r15
0x180016e38  pop     r14
0x180016e3a  pop     rdi
0x180016e3b  pop     rsi
0x180016e3c  pop     rbp
0x180016e3d  pop     rbx
0x180016e3e  retn
```
