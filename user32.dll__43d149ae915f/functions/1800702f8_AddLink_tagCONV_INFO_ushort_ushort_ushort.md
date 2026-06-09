# AddLink(tagCONV_INFO *,ushort,ushort,ushort)

- ea: `0x1800702f8`
- end: `0x18007049d`
- name: `?AddLink@@YAHPEAUtagCONV_INFO@@GGG@Z`
- size: `421`
- prototype: `__int64 __fastcall(struct tagCONV_INFO *, unsigned __int16, unsigned __int16, unsigned __int16)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18008f390`
- `0x1800900d0`

## callees

- `0x180019b20`
- `0x18003ac24`
- `0x18004825c`
- `0x180048320`
- `0x1800702f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070366`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007041a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070366`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007041a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18007037d`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18007037d`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18007039f`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18007039f`

## pseudocode

```c
__int64 __fastcall AddLink(struct tagCONV_INFO *a1, unsigned __int16 a2, __int16 a3, __int16 a4)
{
  _WORD *v4; // rbx
  int v6; // ebp
  ATOM v10; // r14
  unsigned int v11; // esi
  void *v12; // rcx
  char *v13; // rax
  int v14; // ecx
  char *v15; // rbx
  __int64 v16; // rbp
  __int64 *i; // rcx
  _QWORD *v18; // rax

  v4 = (_WORD *)*((_QWORD *)a1 + 12);
  v6 = *((_DWORD *)a1 + 26);
  v10 = GlobalToLocalAtom(a2);
  v11 = 1;
  while ( v6 )
  {
    if ( v4[4] == v10 && v4[5] == a3 )
    {
      v4[6] = a4;
      v4[7] = 0;
LABEL_12:
      DeleteAtom(v10);
      return v11;
    }
    v4 += 8;
    --v6;
  }
  v12 = (void *)*((_QWORD *)a1 + 12);
  if ( v12 )
    v13 = (char *)LocalReAlloc(v12, 16LL * (unsigned int)(*((_DWORD *)a1 + 26) + 1), 0x42u);
  else
    v13 = (char *)LocalAlloc(0x40u, 0x10u);
  if ( !v13 )
  {
    SetLastDDEMLError(*((struct tagCL_INSTANCE_INFO **)a1 + 1), 0x4008u);
    v11 = 0;
    goto LABEL_12;
  }
  v14 = *((_DWORD *)a1 + 26);
  *((_QWORD *)a1 + 12) = v13;
  v15 = &v13[16 * v14];
  *((_DWORD *)a1 + 26) = v14 + 1;
  *((_WORD *)v15 + 7) = 0;
  *((_WORD *)v15 + 4) = v10;
  *((_WORD *)v15 + 5) = a3;
  *((_WORD *)v15 + 6) = a4;
  if ( (*((_BYTE *)a1 + 56) & 0x10) == 0 )
  {
    v16 = *((_QWORD *)a1 + 1);
    for ( i = *(__int64 **)(v16 + 112); ; i = (__int64 *)*i )
    {
      *(_QWORD *)v15 = i;
      if ( !i )
        break;
      if ( *((_WORD *)i + 4) == *((_WORD *)a1 + 17) && *((_WORD *)i + 5) == a2 && *((_WORD *)i + 7) == a3 )
      {
        ++*((_WORD *)i + 8);
        return v11;
      }
    }
    v18 = LocalAlloc(0x40u, 0x18u);
    *(_QWORD *)v15 = v18;
    if ( !v18 )
    {
      SetLastDDEMLError(*((struct tagCL_INSTANCE_INFO **)a1 + 1), 0x4008u);
      return 0;
    }
    *v18 = *(_QWORD *)(v16 + 112);
    *(_QWORD *)(v16 + 112) = *(_QWORD *)v15;
    *(_WORD *)(*(_QWORD *)v15 + 8LL) = IncLocalAtomCount(*((_WORD *)a1 + 17));
    *(_WORD *)(*(_QWORD *)v15 + 10LL) = IncGlobalAtomCount(a2);
    *(_WORD *)(*(_QWORD *)v15 + 12LL) = IncLocalAtomCount(v10);
    *(_WORD *)(*(_QWORD *)v15 + 14LL) = a3;
    *(_WORD *)(*(_QWORD *)v15 + 16LL) = 1;
  }
  return v11;
}

```

## disassembly

```asm
0x1800702f8  push    rbx
0x1800702fa  push    rbp
0x1800702fb  push    rsi
0x1800702fc  push    rdi
0x1800702fd  push    r12
0x1800702ff  push    r13
0x180070301  push    r14
0x180070303  push    r15
0x180070305  sub     rsp, 28h
0x180070309  mov     rbx, [rcx+60h]
0x18007030d  mov     rdi, rcx
0x180070310  mov     ebp, [rcx+68h]
0x180070313  movzx   r12d, r9w
0x180070317  movzx   ecx, dx; unsigned __int16
0x18007031a  movzx   r15d, r8w
0x18007031e  movzx   r13d, dx
0x180070322  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180070327  movzx   r14d, ax
0x18007032b  mov     esi, 1
0x180070330  test    ebp, ebp
0x180070332  jz      short loc_180070357
0x180070334  cmp     [rbx+8], r14w
0x180070339  jnz     short loc_180070342
0x18007033b  cmp     [rbx+0Ah], r15w
0x180070340  jz      short loc_18007034A
0x180070342  add     rbx, 10h
0x180070346  sub     ebp, esi
0x180070348  jmp     short loc_180070330
0x18007034a  xor     eax, eax
0x18007034c  mov     [rbx+0Ch], r12w
0x180070351  mov     [rbx+0Eh], ax
0x180070355  jmp     short loc_18007039B
0x180070357  mov     rcx, [rdi+60h]; hMem
0x18007035b  test    rcx, rcx
0x18007035e  jnz     short loc_18007036E
0x180070360  lea     edx, [rcx+10h]; uBytes
0x180070363  lea     ecx, [rdx+30h]; uFlags
0x180070366  call    cs:__imp_LocalAlloc
0x18007036c  jmp     short loc_180070383
0x18007036e  mov     edx, [rdi+68h]
0x180070371  mov     r8d, 42h ; 'B'; uFlags
0x180070377  add     edx, esi
0x180070379  shl     rdx, 4; uBytes
0x18007037d  call    cs:__imp_LocalReAlloc
0x180070383  mov     rbx, rax
0x180070386  test    rax, rax
0x180070389  jnz     short loc_1800703AA
0x18007038b  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x18007038f  mov     edx, 4008h; unsigned int
0x180070394  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x180070399  xor     esi, esi
0x18007039b  movzx   ecx, r14w; nAtom
0x18007039f  call    cs:__imp_DeleteAtom
0x1800703a5  jmp     loc_18007048A
0x1800703aa  mov     ecx, [rdi+68h]
0x1800703ad  mov     [rdi+60h], rbx
0x1800703b1  mov     eax, ecx
0x1800703b3  shl     rax, 4
0x1800703b7  add     rbx, rax
0x1800703ba  lea     eax, [rcx+1]
0x1800703bd  mov     [rdi+68h], eax
0x1800703c0  xor     eax, eax
0x1800703c2  mov     [rbx+0Eh], ax
0x1800703c6  mov     [rbx+8], r14w
0x1800703cb  mov     [rbx+0Ah], r15w
0x1800703d0  mov     [rbx+0Ch], r12w
0x1800703d5  test    byte ptr [rdi+38h], 10h
0x1800703d9  jnz     loc_18007048A
0x1800703df  mov     rbp, [rdi+8]
0x1800703e3  mov     rcx, [rbp+70h]
0x1800703e7  mov     [rbx], rcx
0x1800703ea  test    rcx, rcx
0x1800703ed  jz      short loc_180070412
0x1800703ef  movzx   eax, word ptr [rdi+22h]
0x1800703f3  cmp     [rcx+8], ax
0x1800703f7  jnz     short loc_180070407
0x1800703f9  cmp     [rcx+0Ah], r13w
0x1800703fe  jnz     short loc_180070407
0x180070400  cmp     [rcx+0Eh], r15w
0x180070405  jz      short loc_18007040C
0x180070407  mov     rcx, [rcx]
0x18007040a  jmp     short loc_1800703E7
0x18007040c  add     [rcx+10h], si
0x180070410  jmp     short loc_18007048A
0x180070412  mov     edx, 18h; uBytes
0x180070417  lea     ecx, [rdx+28h]; uFlags
0x18007041a  call    cs:__imp_LocalAlloc
0x180070420  mov     [rbx], rax
0x180070423  mov     rcx, rax
0x180070426  test    rax, rax
0x180070429  jnz     short loc_18007043D
0x18007042b  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x18007042f  mov     edx, 4008h; unsigned int
0x180070434  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x180070439  xor     eax, eax
0x18007043b  jmp     short loc_18007048C
0x18007043d  mov     rax, [rbp+70h]
0x180070441  mov     [rcx], rax
0x180070444  mov     rax, [rbx]
0x180070447  mov     [rbp+70h], rax
0x18007044b  movzx   ecx, word ptr [rdi+22h]; unsigned __int16
0x18007044f  call    ?IncLocalAtomCount@@YAGG@Z; IncLocalAtomCount(ushort)
0x180070454  mov     rcx, [rbx]
0x180070457  mov     [rcx+8], ax
0x18007045b  movzx   ecx, r13w; unsigned __int16
0x18007045f  call    ?IncGlobalAtomCount@@YAGG@Z; IncGlobalAtomCount(ushort)
0x180070464  mov     rcx, [rbx]
0x180070467  mov     [rcx+0Ah], ax
0x18007046b  movzx   ecx, r14w; unsigned __int16
0x18007046f  call    ?IncLocalAtomCount@@YAGG@Z; IncLocalAtomCount(ushort)
0x180070474  mov     rcx, [rbx]
0x180070477  mov     [rcx+0Ch], ax
0x18007047b  mov     rax, [rbx]
0x18007047e  mov     [rax+0Eh], r15w
0x180070483  mov     rax, [rbx]
0x180070486  mov     [rax+10h], si
0x18007048a  mov     eax, esi
0x18007048c  add     rsp, 28h
0x180070490  pop     r15
0x180070492  pop     r14
0x180070494  pop     r13
0x180070496  pop     r12
0x180070498  pop     rdi
0x180070499  pop     rsi
0x18007049a  pop     rbp
0x18007049b  pop     rbx
0x18007049c  retn
```
