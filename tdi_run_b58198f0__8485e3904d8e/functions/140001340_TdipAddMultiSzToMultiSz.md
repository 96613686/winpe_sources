# TdipAddMultiSzToMultiSz

- ea: `0x140001340`
- end: `0x140001538`
- name: `TdipAddMultiSzToMultiSz`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140001df0`

## callees

- `0x140001340`
- `0x140001c10`
- `0x140001c60`
- `0x140001cb0`
- `0x140001d30`
- `0x140005600`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400013ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400013ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001448`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001448`

## pseudocode

```c
__int64 __fastcall TdipAddMultiSzToMultiSz(unsigned __int16 *a1, wchar_t *a2, _QWORD *a3)
{
  unsigned __int64 v4; // r9
  __int64 v7; // r13
  unsigned __int64 v8; // rdi
  __int64 v9; // rsi
  unsigned int v10; // edi
  size_t v11; // r15
  size_t v12; // r12
  void *Pool2; // rsi
  unsigned __int64 i; // rbp
  unsigned __int64 v16; // rax
  size_t v17; // rdx
  wchar_t *v18; // r10
  size_t v19; // rdx
  size_t pcchLength; // [rsp+60h] [rbp+8h] BYREF
  size_t v21; // [rsp+70h] [rbp+18h]

  v4 = a1[1] - (unsigned __int64)*a1;
  pcchLength = 0;
  *a3 = 0;
  if ( v4 < 2 )
    return 3221225485LL;
  v7 = *((_QWORD *)a1 + 1);
  v8 = 0;
  v9 = 0;
  while ( v8 < (unsigned __int64)*a1 >> 1 )
  {
    if ( !(2 * v8 + v7) )
      return 3221225485LL;
    v17 = *a1 - 2 * v8 + 1;
    if ( v17 > 0x7FFFFFFF || StringLengthWorkerW((STRSAFE_PCNZWCH)(2 * v8 + v7), v17, &pcchLength) )
      return 3221225485LL;
    if ( !(unsigned __int8)TdipIsSzInMultiSzSafe(v18, a2) )
      v9 += 2 * pcchLength + 2;
    v8 += pcchLength + 1;
  }
  v10 = 0;
  if ( v9 )
  {
    v11 = (unsigned int)TdipCbOfMultiSzSafe(a2);
    v12 = v11 + v9;
    Pool2 = (void *)ExAllocatePool2(64, v11 + v9 + 2, 1783186516);
    if ( Pool2 )
    {
      v21 = v11 >> 1;
      memmove(Pool2, a2, v11);
      for ( i = 0; ; i += pcchLength + 1 )
      {
        v16 = (unsigned __int64)*a1 >> 1;
        if ( i >= v16 )
          break;
        if ( !(v7 + 2 * i)
          || (v19 = v16 - i + 1, v19 > 0x7FFFFFFF)
          || StringLengthWorkerW((STRSAFE_PCNZWCH)(v7 + 2 * i), v19, &pcchLength) )
        {
LABEL_13:
          ExFreePoolWithTag(Pool2, 0x6A494454u);
          return 3221225485LL;
        }
        if ( !(unsigned __int8)TdipIsSzInMultiSzSafe((wchar_t *)(v7 + 2 * i), (wchar_t *)Pool2) )
        {
          if ( StringCchCatW((STRSAFE_LPWSTR)Pool2 + v21, ((v12 + 2) >> 1) - v21, (STRSAFE_LPCWSTR)(v7 + 2 * i)) )
            goto LABEL_13;
          v21 += pcchLength + 1;
        }
      }
      *a3 = Pool2;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x140001340  push    rbx
0x140001342  push    rbp
0x140001343  push    rsi
0x140001344  push    rdi
0x140001345  push    r13
0x140001347  push    r14
0x140001349  sub     rsp, 28h
0x14000134d  movzx   r9d, word ptr [rcx+2]
0x140001352  mov     rbp, rdx
0x140001355  movzx   eax, word ptr [rcx]
0x140001358  xor     edx, edx
0x14000135a  sub     r9, rax
0x14000135d  mov     [rsp+58h+pcchLength], rdx
0x140001362  mov     [r8], rdx
0x140001365  mov     r14, r8
0x140001368  mov     rbx, rcx
0x14000136b  cmp     r9, 2
0x14000136f  jb      loc_1400013FA
0x140001375  mov     r13, [rcx+8]
0x140001379  mov     edi, edx
0x14000137b  mov     esi, edx
0x14000137d  movzx   eax, word ptr [rbx]
0x140001380  mov     ecx, eax
0x140001382  shr     rcx, 1
0x140001385  cmp     rdi, rcx
0x140001388  jb      short loc_1400013ED
0x14000138a  xor     edi, edi
0x14000138c  mov     [rsp+58h+arg_8], r12
0x140001391  mov     [rsp+58h+var_38], r15
0x140001396  test    rsi, rsi
0x140001399  jz      short loc_1400013D3
0x14000139b  mov     rcx, rbp
0x14000139e  call    TdipCbOfMultiSzSafe
0x1400013a3  mov     r15d, eax
0x1400013a6  mov     r8d, 6A494454h
0x1400013ac  mov     ecx, 40h ; '@'
0x1400013b1  lea     r12, [r15+rsi]
0x1400013b5  lea     rdx, [r12+2]
0x1400013ba  call    cs:__imp_ExAllocatePool2
0x1400013c1  nop     dword ptr [rax+rax+00h]
0x1400013c6  mov     rsi, rax
0x1400013c9  test    rax, rax
0x1400013cc  jnz     short loc_14000140D
0x1400013ce  mov     edi, 0C000009Ah
0x1400013d3  mov     eax, edi
0x1400013d5  mov     r12, [rsp+58h+arg_8]
0x1400013da  mov     r15, [rsp+58h+var_38]
0x1400013df  add     rsp, 28h
0x1400013e3  pop     r14
0x1400013e5  pop     r13
0x1400013e7  pop     rdi
0x1400013e8  pop     rsi
0x1400013e9  pop     rbp
0x1400013ea  pop     rbx
0x1400013eb  retn
0x1400013ed  lea     rcx, [rdi+rdi]
0x1400013f1  lea     r10, [rcx+r13]
0x1400013f5  test    r10, r10
0x1400013f8  jnz     short loc_140001466
0x1400013fa  mov     eax, 0C000000Dh
0x1400013ff  add     rsp, 28h
0x140001403  pop     r14
0x140001405  pop     r13
0x140001407  pop     rdi
0x140001408  pop     rsi
0x140001409  pop     rbp
0x14000140a  pop     rbx
0x14000140b  retn
0x14000140d  mov     rax, r15
0x140001410  mov     r8, r15; Size
0x140001413  shr     rax, 1
0x140001416  mov     rdx, rbp; Src
0x140001419  mov     rcx, rsi; void *
0x14000141c  mov     [rsp+58h+arg_10], rax
0x140001421  call    memmove
0x140001426  xor     ebp, ebp
0x140001428  movzx   eax, word ptr [rbx]
0x14000142b  shr     rax, 1
0x14000142e  cmp     rbp, rax
0x140001431  jnb     short loc_14000145E
0x140001433  lea     r15, ds:0[rbp*2]
0x14000143b  add     r15, r13
0x14000143e  jnz     short loc_1400014B8
0x140001440  mov     edx, 6A494454h; Tag
0x140001445  mov     rcx, rsi; P
0x140001448  call    cs:__imp_ExFreePoolWithTag
0x14000144f  nop     dword ptr [rax+rax+00h]
0x140001454  mov     eax, 0C000000Dh
0x140001459  jmp     loc_1400013D5
0x14000145e  mov     [r14], rsi
0x140001461  jmp     loc_1400013D3
0x140001466  sub     rax, rcx
0x140001469  lea     rdx, [rax+1]; cchMax
0x14000146d  cmp     rdx, 7FFFFFFFh
0x140001474  ja      short loc_1400013FA
0x140001476  lea     r8, [rsp+58h+pcchLength]; pcchLength
0x14000147b  mov     rcx, r10; psz
0x14000147e  call    StringLengthWorkerW
0x140001483  test    eax, eax
0x140001485  js      loc_1400013FA
0x14000148b  jnz     loc_1400013FA
0x140001491  mov     rdx, rbp; Str1
0x140001494  mov     rcx, r10; Str2
0x140001497  call    TdipIsSzInMultiSzSafe
0x14000149c  mov     rcx, [rsp+58h+pcchLength]
0x1400014a1  test    al, al
0x1400014a3  jnz     short loc_1400014AD
0x1400014a5  lea     rsi, [rsi+rcx*2]
0x1400014a9  add     rsi, 2
0x1400014ad  inc     rdi
0x1400014b0  add     rdi, rcx
0x1400014b3  jmp     loc_14000137D
0x1400014b8  sub     rax, rbp
0x1400014bb  lea     rdx, [rax+1]; cchMax
0x1400014bf  cmp     rdx, 7FFFFFFFh
0x1400014c6  ja      loc_140001440
0x1400014cc  lea     r8, [rsp+58h+pcchLength]; pcchLength
0x1400014d1  mov     rcx, r15; psz
0x1400014d4  call    StringLengthWorkerW
0x1400014d9  test    eax, eax
0x1400014db  jnz     loc_140001440
0x1400014e1  mov     rdx, rsi; Str1
0x1400014e4  mov     rcx, r15; Str2
0x1400014e7  call    TdipIsSzInMultiSzSafe
0x1400014ec  test    al, al
0x1400014ee  jz      short loc_140001500
0x1400014f0  mov     rax, [rsp+58h+pcchLength]
0x1400014f5  inc     rax
0x1400014f8  add     rbp, rax
0x1400014fb  jmp     loc_140001428
0x140001500  mov     rax, [rsp+58h+arg_10]
0x140001505  lea     rdx, [r12+2]
0x14000150a  shr     rdx, 1
0x14000150d  mov     r8, r15; pszSrc
0x140001510  sub     rdx, rax; cchDest
0x140001513  lea     rcx, [rsi+rax*2]; pszDest
0x140001517  call    StringCchCatW
0x14000151c  test    eax, eax
0x14000151e  jnz     loc_140001440
0x140001524  mov     rax, [rsp+58h+arg_10]
0x140001529  inc     rax
0x14000152c  add     rax, [rsp+58h+pcchLength]
0x140001531  mov     [rsp+58h+arg_10], rax
0x140001536  jmp     short loc_1400014F0
```
