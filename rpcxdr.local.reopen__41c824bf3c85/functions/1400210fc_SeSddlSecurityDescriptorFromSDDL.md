# SeSddlSecurityDescriptorFromSDDL

- ea: `0x1400210fc`
- end: `0x1400211b8`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020e70`

## callees

- `0x140015840`
- `0x140015b40`
- `0x1400210fc`
- `0x1400218d4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140021141`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140021141`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002119e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002119e`

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
      return SepSddlSecurityDescriptorFromSDDLString(v7, v8, (__int64)a3);
  }
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, v6, 0x73546553u);
  v11 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, *a1 + 2LL);
    memmove(v11, *((const void **)a1 + 1), *a1);
    *((_WORD *)v11 + ((unsigned __int64)*a1 >> 1)) = 0;
    v13 = SepSddlSecurityDescriptorFromSDDLString((__int64)v11, v12, (__int64)a3);
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
0x1400210fc  push    rbx
0x1400210fe  push    rbp
0x1400210ff  push    rsi
0x140021100  push    rdi
0x140021101  push    r14
0x140021103  sub     rsp, 20h
0x140021107  movzx   edx, word ptr [rcx]
0x14002110a  xor     ebp, ebp
0x14002110c  movzx   eax, word ptr [rcx+2]
0x140021110  mov     rsi, r8
0x140021113  mov     rdi, rcx
0x140021116  lea     r9, [rdx+2]
0x14002111a  cmp     rax, r9
0x14002111d  jnz     short loc_140021133
0x14002111f  mov     rcx, [rcx+8]
0x140021123  shr     rdx, 1
0x140021126  cmp     [rcx+rdx*2], bp
0x14002112a  jnz     short loc_140021133
0x14002112c  call    SepSddlSecurityDescriptorFromSDDLString
0x140021131  jmp     short loc_1400211AC
0x140021133  mov     r8d, 73546553h; Tag
0x140021139  mov     rdx, r9; NumberOfBytes
0x14002113c  mov     ecx, 1; PoolType
0x140021141  call    cs:__imp_ExAllocatePoolWithTag
0x140021148  nop     dword ptr [rax+rax+00h]
0x14002114d  mov     r14, rax
0x140021150  test    rax, rax
0x140021153  jnz     short loc_14002115F
0x140021155  mov     [rsi], rbp
0x140021158  mov     eax, 0C000009Ah
0x14002115d  jmp     short loc_1400211AC
0x14002115f  movzx   r8d, word ptr [rdi]
0x140021163  xor     edx, edx; Val
0x140021165  add     r8, 2; Size
0x140021169  mov     rcx, r14; void *
0x14002116c  call    memset
0x140021171  movzx   r8d, word ptr [rdi]; Size
0x140021175  mov     rcx, r14; void *
0x140021178  mov     rdx, [rdi+8]; Src
0x14002117c  call    memmove
0x140021181  movzx   ecx, word ptr [rdi]
0x140021184  mov     r8, rsi
0x140021187  shr     rcx, 1
0x14002118a  mov     [r14+rcx*2], bp
0x14002118f  mov     rcx, r14
0x140021192  call    SepSddlSecurityDescriptorFromSDDLString
0x140021197  xor     edx, edx; Tag
0x140021199  mov     rcx, r14; P
0x14002119c  mov     ebx, eax
0x14002119e  call    cs:__imp_ExFreePoolWithTag
0x1400211a5  nop     dword ptr [rax+rax+00h]
0x1400211aa  mov     eax, ebx
0x1400211ac  add     rsp, 20h
0x1400211b0  pop     r14
0x1400211b2  pop     rdi
0x1400211b3  pop     rsi
0x1400211b4  pop     rbp
0x1400211b5  pop     rbx
0x1400211b6  retn
```
