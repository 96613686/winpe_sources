# SmbCompressionMdlCompress

- ea: `0x140020d44`
- end: `0x140020e6a`
- name: `SmbCompressionMdlCompress`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140053a6c`

## callees

- `0x140020658`
- `0x140020d44`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140020db2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140020db2`

## pseudocode

```c
__int64 __fastcall SmbCompressionMdlCompress(unsigned int a1, __int64 *a2, unsigned int a3, _DWORD *a4, _DWORD *a5)
{
  _DWORD *v5; // r14
  unsigned int v6; // r10d
  int v7; // r13d
  __int64 *v9; // rbx
  unsigned int v10; // ebp
  _DWORD *v11; // rdi
  PVOID v12; // r15
  unsigned int v13; // eax
  __int64 v14; // rsi
  int v15; // eax
  unsigned int v16; // ecx
  unsigned int v19; // [rsp+80h] [rbp+18h] BYREF

  v5 = a5;
  v6 = 0;
  v7 = (int)a4;
  v9 = a2;
  v10 = a3;
  v11 = a4;
  for ( *a5 = 0; v9; v11 = (_DWORD *)((char *)v11 + v16) )
  {
    if ( !v10 )
      break;
    v12 = (*((_BYTE *)v9 + 10) & 5) != 0
        ? (PVOID)v9[3]
        : MmMapLockedPagesSpecifyCache((PMDL)v9, 0, MmCached, 0, 0, 0x40000010u);
    v13 = *((_DWORD *)v9 + 10);
    v14 = v10;
    if ( v10 >= v13 )
      v14 = v13;
    v19 = a3 + v7 - (_DWORD)v11;
    v15 = SmbCompressionCompress(a1, v12, (unsigned int)v14, v11, &v19);
    v6 = v15;
    if ( v15 == -1073741789 )
    {
      if ( v14 + 8 >= (unsigned __int64)(a3 - *v5) )
        return v6;
      v11[1] = v14;
      *v11 = 0;
      memmove(v11 + 2, v12, (unsigned int)v14);
      v16 = v14 + 8;
      v6 = 0;
    }
    else
    {
      if ( v15 < 0 )
        return v6;
      v16 = v19;
    }
    *v5 += v16;
    v10 -= v14;
    v9 = (__int64 *)*v9;
  }
  return v6;
}

```

## disassembly

```asm
0x140020d44  mov     [rsp+arg_8], rbx
0x140020d49  mov     [rsp+arg_0], ecx
0x140020d4d  push    rbp
0x140020d4e  push    rsi
0x140020d4f  push    rdi
0x140020d50  push    r12
0x140020d52  push    r13
0x140020d54  push    r14
0x140020d56  push    r15
0x140020d58  sub     rsp, 30h
0x140020d5c  mov     r14, [rsp+68h+arg_20]
0x140020d64  xor     r10d, r10d
0x140020d67  mov     r13, r9
0x140020d6a  mov     r12d, r8d
0x140020d6d  mov     rbx, rdx
0x140020d70  mov     ebp, r8d
0x140020d73  mov     rdi, r9
0x140020d76  mov     [r14], r10d
0x140020d79  test    rdx, rdx
0x140020d7c  jz      loc_140020E51
0x140020d82  test    ebp, ebp
0x140020d84  jz      loc_140020E51
0x140020d8a  test    byte ptr [rbx+0Ah], 5
0x140020d8e  jz      short loc_140020D96
0x140020d90  mov     r15, [rbx+18h]
0x140020d94  jmp     short loc_140020DC1
0x140020d96  xor     r9d, r9d; RequestedAddress
0x140020d99  mov     [rsp+68h+Priority], 40000010h; Priority
0x140020da1  xor     edx, edx; AccessMode
0x140020da3  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140020dab  mov     rcx, rbx; MemoryDescriptorList
0x140020dae  lea     r8d, [r9+1]; CacheType
0x140020db2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140020db9  nop     dword ptr [rax+rax+00h]
0x140020dbe  mov     r15, rax
0x140020dc1  mov     eax, [rbx+28h]
0x140020dc4  mov     esi, ebp
0x140020dc6  mov     ecx, [rsp+68h+arg_0]
0x140020dca  cmp     ebp, eax
0x140020dcc  mov     r9, rdi
0x140020dcf  mov     rdx, r15
0x140020dd2  cmovnb  esi, eax
0x140020dd5  mov     eax, r13d
0x140020dd8  sub     eax, edi
0x140020dda  mov     r8d, esi
0x140020ddd  add     eax, r12d
0x140020de0  mov     [rsp+68h+arg_10], eax
0x140020de7  lea     rax, [rsp+68h+arg_10]
0x140020def  mov     qword ptr [rsp+68h+BugCheckOnFailure], rax
0x140020df4  call    SmbCompressionCompress
0x140020df9  mov     r10d, eax
0x140020dfc  cmp     eax, 0C0000023h
0x140020e01  jnz     short loc_140020E30
0x140020e03  mov     edx, r12d
0x140020e06  mov     r8d, esi; Size
0x140020e09  sub     edx, [r14]
0x140020e0c  lea     rcx, [rsi+8]
0x140020e10  cmp     rcx, rdx
0x140020e13  jnb     short loc_140020E51
0x140020e15  xor     eax, eax
0x140020e17  mov     [rdi+4], esi
0x140020e1a  lea     rcx, [rdi+8]; void *
0x140020e1e  mov     [rdi], eax
0x140020e20  mov     rdx, r15; Src
0x140020e23  call    memmove
0x140020e28  lea     ecx, [rsi+8]
0x140020e2b  xor     r10d, r10d
0x140020e2e  jmp     short loc_140020E3B
0x140020e30  test    eax, eax
0x140020e32  js      short loc_140020E51
0x140020e34  mov     ecx, [rsp+68h+arg_10]
0x140020e3b  add     [r14], ecx
0x140020e3e  sub     ebp, esi
0x140020e40  mov     rbx, [rbx]
0x140020e43  mov     eax, ecx
0x140020e45  add     rdi, rax
0x140020e48  test    rbx, rbx
0x140020e4b  jnz     loc_140020D82
0x140020e51  mov     rbx, [rsp+68h+arg_8]
0x140020e56  mov     eax, r10d
0x140020e59  add     rsp, 30h
0x140020e5d  pop     r15
0x140020e5f  pop     r14
0x140020e61  pop     r13
0x140020e63  pop     r12
0x140020e65  pop     rdi
0x140020e66  pop     rsi
0x140020e67  pop     rbp
0x140020e68  retn
```
