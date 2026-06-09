# CIndexCache::Find(ushort const *,ulong)

- ea: `0x18000f6ec`
- end: `0x18000f767`
- name: `?Find@CIndexCache@@QEAAHPEBGK@Z`
- size: `123`
- prototype: `__int64 __fastcall(CIndexCache *this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800101d4`
- `0x1800118ec`

## callees

- `0x18000f6ec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f73a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f73a`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000f715`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000f715`

## pseudocode

```c
__int64 __fastcall CIndexCache::Find(CIndexCache *this, const unsigned __int16 *a2, int a3)
{
  int v3; // edi
  CFlexArray *v4; // r14
  int v5; // ebp
  int i; // ebx
  PCNZWCH *v9; // rsi

  v3 = 0;
  v4 = (CIndexCache *)((char *)this + 8);
  v5 = *((_DWORD *)this + 2);
  for ( i = 0; i < v5; ++i )
  {
    v9 = (PCNZWCH *)CFlexArray::GetAt(v4, i);
    if ( CompareStringW(0x7Fu, 1u, v9[2], -1, a2, -1) == 2 )
    {
      if ( v3 == a3 )
        return *((unsigned int *)v9 + 2);
      ++v3;
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000f6ec  push    rbx
0x18000f6ee  push    rbp
0x18000f6ef  push    rsi
0x18000f6f0  push    rdi
0x18000f6f1  push    r12
0x18000f6f3  push    r14
0x18000f6f5  push    r15
0x18000f6f7  sub     rsp, 30h
0x18000f6fb  xor     edi, edi
0x18000f6fd  lea     r14, [rcx+8]
0x18000f701  mov     ebp, [r14]
0x18000f704  xor     ebx, ebx
0x18000f706  mov     r15d, r8d
0x18000f709  mov     r12, rdx
0x18000f70c  cmp     ebx, ebp
0x18000f70e  jge     short loc_18000F755
0x18000f710  mov     edx, ebx
0x18000f712  mov     rcx, r14
0x18000f715  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000f71b  or      r9d, 0FFFFFFFFh; cchCount1
0x18000f71f  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000f727  mov     rsi, rax
0x18000f72a  mov     [rsp+68h+lpString2], r12; lpString2
0x18000f72f  mov     r8, [rax+10h]; lpString1
0x18000f733  lea     edx, [r9+2]; dwCmpFlags
0x18000f737  lea     ecx, [rdx+7Eh]; Locale
0x18000f73a  call    cs:__imp_CompareStringW
0x18000f740  cmp     eax, 2
0x18000f743  jnz     short loc_18000F74C
0x18000f745  cmp     edi, r15d
0x18000f748  jz      short loc_18000F750
0x18000f74a  inc     edi
0x18000f74c  inc     ebx
0x18000f74e  jmp     short loc_18000F70C
0x18000f750  mov     eax, [rsi+8]
0x18000f753  jmp     short loc_18000F758
0x18000f755  or      eax, 0FFFFFFFFh
0x18000f758  add     rsp, 30h
0x18000f75c  pop     r15
0x18000f75e  pop     r14
0x18000f760  pop     r12
0x18000f762  pop     rdi
0x18000f763  pop     rsi
0x18000f764  pop     rbp
0x18000f765  pop     rbx
0x18000f766  retn
```
