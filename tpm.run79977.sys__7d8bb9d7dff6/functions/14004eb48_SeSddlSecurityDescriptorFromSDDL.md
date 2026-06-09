# SeSddlSecurityDescriptorFromSDDL

- ea: `0x14004eb48`
- end: `0x14004ec04`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400222b8`

## callees

- `0x140039840`
- `0x140039b40`
- `0x14004eb48`
- `0x14004f300`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004ebea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ebea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004eb8d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004eb8d`

## pseudocode

```c
__int64 __fastcall SeSddlSecurityDescriptorFromSDDL(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  unsigned __int64 v3; // rdx
  SIZE_T v6; // r9
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  PVOID PoolWithTag; // rax
  void *v11; // r14
  ULONG v12; // edx
  unsigned int v13; // ebx

  v3 = *a1;
  v6 = v3 + 2;
  if ( a1[1] == v3 + 2 )
  {
    v7 = *((_QWORD *)a1 + 1);
    v8 = v3 >> 1;
    if ( !*(_WORD *)(v7 + 2 * v8) )
      return SepSddlSecurityDescriptorFromSDDLString(v7, v8, a3);
  }
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, v6, 0x73546553u);
  v11 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, *a1 + 2LL);
    memmove(v11, *((const void **)a1 + 1), *a1);
    *((_WORD *)v11 + ((unsigned __int64)*a1 >> 1)) = 0;
    v13 = SepSddlSecurityDescriptorFromSDDLString((__int64)v11, v12, a3);
    ExFreePoolWithTag(v11, 0);
    return v13;
  }
  else
  {
    *a3 = 0;
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14004eb48  push    rbx
0x14004eb4a  push    rbp
0x14004eb4b  push    rsi
0x14004eb4c  push    rdi
0x14004eb4d  push    r14
0x14004eb4f  sub     rsp, 20h
0x14004eb53  movzx   edx, word ptr [rcx]
0x14004eb56  xor     ebp, ebp
0x14004eb58  movzx   eax, word ptr [rcx+2]
0x14004eb5c  mov     rsi, r8
0x14004eb5f  mov     rdi, rcx
0x14004eb62  lea     r9, [rdx+2]
0x14004eb66  cmp     rax, r9
0x14004eb69  jnz     short loc_14004EB7F
0x14004eb6b  mov     rcx, [rcx+8]
0x14004eb6f  shr     rdx, 1
0x14004eb72  cmp     [rcx+rdx*2], bp
0x14004eb76  jnz     short loc_14004EB7F
0x14004eb78  call    SepSddlSecurityDescriptorFromSDDLString
0x14004eb7d  jmp     short loc_14004EBF8
0x14004eb7f  mov     r8d, 73546553h; Tag
0x14004eb85  mov     rdx, r9; NumberOfBytes
0x14004eb88  mov     ecx, 1; PoolType
0x14004eb8d  call    cs:__imp_ExAllocatePoolWithTag
0x14004eb94  nop     dword ptr [rax+rax+00h]
0x14004eb99  mov     r14, rax
0x14004eb9c  test    rax, rax
0x14004eb9f  jnz     short loc_14004EBAB
0x14004eba1  mov     [rsi], rbp
0x14004eba4  mov     eax, 0C000009Ah
0x14004eba9  jmp     short loc_14004EBF8
0x14004ebab  movzx   r8d, word ptr [rdi]
0x14004ebaf  xor     edx, edx; Val
0x14004ebb1  add     r8, 2; Size
0x14004ebb5  mov     rcx, r14; void *
0x14004ebb8  call    memset
0x14004ebbd  movzx   r8d, word ptr [rdi]; Size
0x14004ebc1  mov     rcx, r14; void *
0x14004ebc4  mov     rdx, [rdi+8]; Src
0x14004ebc8  call    memmove
0x14004ebcd  movzx   ecx, word ptr [rdi]
0x14004ebd0  mov     r8, rsi
0x14004ebd3  shr     rcx, 1
0x14004ebd6  mov     [r14+rcx*2], bp
0x14004ebdb  mov     rcx, r14
0x14004ebde  call    SepSddlSecurityDescriptorFromSDDLString
0x14004ebe3  xor     edx, edx; Tag
0x14004ebe5  mov     rcx, r14; P
0x14004ebe8  mov     ebx, eax
0x14004ebea  call    cs:__imp_ExFreePoolWithTag
0x14004ebf1  nop     dword ptr [rax+rax+00h]
0x14004ebf6  mov     eax, ebx
0x14004ebf8  add     rsp, 20h
0x14004ebfc  pop     r14
0x14004ebfe  pop     rdi
0x14004ebff  pop     rsi
0x14004ec00  pop     rbp
0x14004ec01  pop     rbx
0x14004ec02  retn
```
