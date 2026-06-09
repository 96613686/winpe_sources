# GetStartPageListBooklet(_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER * *,_PAGE_NUMBER * *)

- ea: `0x1800045d0`
- end: `0x1800047df`
- name: `?GetStartPageListBooklet@@YAHPEAU_EMF_ATTRIBUTE_INFO@@PEAPEAU_PAGE_NUMBER@@1@Z`
- size: `527`
- prototype: `__int64 __fastcall(struct _EMF_ATTRIBUTE_INFO *, struct _PAGE_NUMBER **, struct _PAGE_NUMBER **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002400`

## callees

- `0x180003860`
- `0x1800045d0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000468a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000468a`

## pseudocode

```c
__int64 __fastcall GetStartPageListBooklet(
        struct _EMF_ATTRIBUTE_INFO *a1,
        struct _PAGE_NUMBER **a2,
        struct _PAGE_NUMBER **a3)
{
  unsigned int v3; // eax
  unsigned int v6; // ebp
  int v7; // r14d
  int v8; // r15d
  __int64 v9; // rcx
  unsigned int v10; // esi
  struct _PAGE_NUMBER *v11; // rax
  struct _PAGE_NUMBER *v12; // r9
  unsigned int j; // r11d
  unsigned int i; // edx
  struct _PAGE_NUMBER *v15; // rcx
  struct _PAGE_NUMBER *v16; // rdx
  struct _PAGE_NUMBER *v17; // rax
  struct _PAGE_NUMBER *v18; // rdx
  struct _PAGE_NUMBER **v19; // rdx
  struct _PAGE_NUMBER *v20; // r8
  int v21; // ecx
  __int64 v22; // r8
  int v23; // ecx
  __int64 result; // rax
  unsigned int v25; // [rsp+50h] [rbp+8h] BYREF
  SIZE_T uBytes; // [rsp+68h] [rbp+20h] BYREF

  v3 = *((_DWORD *)a1 + 7);
  v25 = 4;
  LODWORD(uBytes) = 0;
  if ( v3 - 1 > 0xFFFFFFFD || !a2 || !a3 )
    return 0;
  v6 = *((_DWORD *)a1 + 16);
  v7 = *((_DWORD *)a1 + 18);
  v8 = *((_DWORD *)a1 + 13);
  *a2 = 0;
  *a3 = 0;
  v9 = (v3 >> 2) + 1;
  if ( (v3 & 0xFFFFFFFC) == v3 )
    v9 = v3 >> 2;
  if ( (int)ULongLongToULong(4 * v9, &v25) < 0
    || (v10 = v25, (int)ULongLongToULong(24LL * v25, (unsigned int *)&uBytes) < 0)
    || (v11 = (struct _PAGE_NUMBER *)LocalAlloc(0x40u, (unsigned int)uBytes), (v12 = v11) == 0) )
  {
    *a2 = 0;
    result = 0;
    *a3 = 0;
    return result;
  }
  *a3 = v11;
  *a2 = v11;
  if ( v6 <= 1 )
  {
    for ( i = 0; i < v10 >> 1; v12 = (struct _PAGE_NUMBER *)((char *)v12 + 48) )
    {
      *((_QWORD *)v12 + 4) = 0;
      *((_QWORD *)v12 + 3) = 0;
      *((_DWORD *)v12 + 4) = v10 - i;
      *(_QWORD *)v12 = (char *)v12 + 48;
      ++i;
      *((_QWORD *)v12 + 1) = (char *)v12 + 24;
      *((_DWORD *)v12 + 10) = i;
    }
    goto LABEL_16;
  }
  if ( v6 == 2 )
  {
    for ( j = 0; j < v10 >> 1; ++j )
    {
      *((_QWORD *)v12 + 4) = 0;
      *((_DWORD *)v12 + 4) = j + 1;
      *((_QWORD *)v12 + 1) = (char *)v12 + 24;
      *(_QWORD *)v12 = (char *)v12 + 48;
      *((_QWORD *)v12 + 3) = 0;
      *((_DWORD *)v12 + 10) = v10 - j;
      v12 = (struct _PAGE_NUMBER *)((char *)v12 + 48);
    }
LABEL_16:
    *((_QWORD *)v12 - 6) = 0;
  }
  if ( v7 )
  {
    v15 = *a3;
    v16 = 0;
    if ( *a3 )
    {
      do
      {
        v17 = *(struct _PAGE_NUMBER **)v15;
        *(_QWORD *)v15 = v16;
        v16 = v15;
        v15 = v17;
      }
      while ( v17 );
    }
    *a3 = v16;
  }
  if ( v8 == 2 )
  {
    v18 = *a3;
    if ( *a3 )
    {
      if ( v7 )
      {
        do
        {
          v22 = *((_QWORD *)v18 + 1);
          if ( v22 )
          {
            v23 = *((_DWORD *)v18 + 4);
            *((_DWORD *)v18 + 4) = *(_DWORD *)(v22 + 16);
            *(_DWORD *)(v22 + 16) = v23;
          }
          if ( *(_QWORD *)v18 )
            v18 = **(struct _PAGE_NUMBER ***)v18;
        }
        while ( v18 );
      }
      else
      {
        do
        {
          v19 = *(struct _PAGE_NUMBER ***)v18;
          if ( !v19 )
            break;
          v20 = v19[1];
          if ( v20 )
          {
            v21 = *((_DWORD *)v19 + 4);
            *((_DWORD *)v19 + 4) = *((_DWORD *)v20 + 4);
            *((_DWORD *)v20 + 4) = v21;
          }
          v18 = *v19;
        }
        while ( v18 );
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800045d0  push    rbx
0x1800045d2  push    rdi
0x1800045d3  push    r12
0x1800045d5  sub     rsp, 30h
0x1800045d9  mov     eax, [rcx+1Ch]
0x1800045dc  xor     r12d, r12d
0x1800045df  mov     rbx, r8
0x1800045e2  mov     [rsp+48h+arg_0], 4
0x1800045ea  mov     rdi, rdx
0x1800045ed  mov     dword ptr [rsp+48h+uBytes], r12d
0x1800045f2  lea     r9d, [rax-1]
0x1800045f6  cmp     r9d, 0FFFFFFFDh
0x1800045fa  ja      loc_1800047D4
0x180004600  test    rdx, rdx
0x180004603  jz      loc_1800047D4
0x180004609  test    rbx, rbx
0x18000460c  jz      loc_1800047D4
0x180004612  mov     [rsp+48h+arg_8], rbp
0x180004617  mov     ebp, [rcx+40h]
0x18000461a  mov     [rsp+48h+var_20], r14
0x18000461f  mov     r14d, [rcx+48h]
0x180004623  mov     [rsp+48h+var_28], r15
0x180004628  mov     r15d, [rcx+34h]
0x18000462c  mov     [rdx], r12
0x18000462f  mov     edx, eax
0x180004631  mov     [r8], r12
0x180004634  and     edx, 0FFFFFFFCh
0x180004637  mov     r8d, eax
0x18000463a  mov     [rsp+48h+arg_10], rsi
0x18000463f  shr     r8d, 2
0x180004643  cmp     edx, eax
0x180004645  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x18000464a  lea     ecx, [r8+1]
0x18000464e  cmovz   ecx, r8d
0x180004652  shl     rcx, 2; unsigned __int64
0x180004656  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000465b  test    eax, eax
0x18000465d  js      loc_1800047B5
0x180004663  mov     esi, [rsp+48h+arg_0]
0x180004667  lea     rdx, [rsp+48h+uBytes]; unsigned int *
0x18000466c  lea     rcx, [rsi+rsi*2]
0x180004670  shl     rcx, 3; unsigned __int64
0x180004674  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180004679  test    eax, eax
0x18000467b  js      loc_1800047B5
0x180004681  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x180004685  mov     ecx, 40h ; '@'; uFlags
0x18000468a  call    cs:__imp_LocalAlloc
0x180004690  mov     r9, rax
0x180004693  test    rax, rax
0x180004696  jz      loc_1800047B5
0x18000469c  mov     [rbx], rax
0x18000469f  mov     [rdi], rax
0x1800046a2  cmp     ebp, 1
0x1800046a5  jbe     short loc_1800046EB
0x1800046a7  cmp     ebp, 2
0x1800046aa  jnz     short loc_180004727
0x1800046ac  mov     r10d, esi
0x1800046af  mov     r11d, r12d
0x1800046b2  shr     r10d, 1
0x1800046b5  jz      short loc_180004723
0x1800046b7  lea     r8d, [r11+1]
0x1800046bb  mov     [r9+20h], r12
0x1800046bf  lea     rcx, [r9+18h]
0x1800046c3  mov     [r9+10h], r8d
0x1800046c7  lea     rdx, [r9+30h]
0x1800046cb  mov     [r9+8], rcx
0x1800046cf  mov     eax, esi
0x1800046d1  mov     [r9], rdx
0x1800046d4  sub     eax, r11d
0x1800046d7  mov     [rcx], r12
0x1800046da  mov     [r9+28h], eax
0x1800046de  mov     r9, rdx
0x1800046e1  mov     r11d, r8d
0x1800046e4  cmp     r8d, r10d
0x1800046e7  jb      short loc_1800046B7
0x1800046e9  jmp     short loc_180004723
0x1800046eb  mov     r8d, esi
0x1800046ee  mov     edx, r12d
0x1800046f1  shr     r8d, 1
0x1800046f4  jz      short loc_180004723
0x1800046f6  mov     eax, esi
0x1800046f8  mov     [r9+20h], r12
0x1800046fc  sub     eax, edx
0x1800046fe  mov     [r9+18h], r12
0x180004702  mov     [r9+10h], eax
0x180004706  lea     rcx, [r9+30h]
0x18000470a  lea     rax, [r9+18h]
0x18000470e  mov     [r9], rcx
0x180004711  inc     edx
0x180004713  mov     [r9+8], rax
0x180004717  mov     [r9+28h], edx
0x18000471b  mov     r9, rcx
0x18000471e  cmp     edx, r8d
0x180004721  jb      short loc_1800046F6
0x180004723  mov     [r9-30h], r12
0x180004727  test    r14d, r14d
0x18000472a  jz      short loc_18000474B
0x18000472c  mov     rcx, [rbx]
0x18000472f  mov     rdx, r12
0x180004732  test    rcx, rcx
0x180004735  jz      short loc_180004748
0x180004737  mov     rax, [rcx]
0x18000473a  mov     [rcx], rdx
0x18000473d  mov     rdx, rcx
0x180004740  mov     rcx, rax
0x180004743  test    rax, rax
0x180004746  jnz     short loc_180004737
0x180004748  mov     [rbx], rdx
0x18000474b  cmp     r15d, 2
0x18000474f  jnz     short loc_1800047AE
0x180004751  mov     rdx, [rbx]
0x180004754  test    rdx, rdx
0x180004757  jz      short loc_1800047AE
0x180004759  test    r14d, r14d
0x18000475c  jnz     short loc_180004787
0x18000475e  mov     rdx, [rdx]
0x180004761  test    rdx, rdx
0x180004764  jz      short loc_1800047AE
0x180004766  mov     r8, [rdx+8]
0x18000476a  test    r8, r8
0x18000476d  jz      short loc_18000477D
0x18000476f  mov     ecx, [rdx+10h]
0x180004772  mov     eax, [r8+10h]
0x180004776  mov     [rdx+10h], eax
0x180004779  mov     [r8+10h], ecx
0x18000477d  mov     rdx, [rdx]
0x180004780  test    rdx, rdx
0x180004783  jnz     short loc_18000475E
0x180004785  jmp     short loc_1800047AE
0x180004787  mov     r8, [rdx+8]
0x18000478b  test    r8, r8
0x18000478e  jz      short loc_18000479E
0x180004790  mov     ecx, [rdx+10h]
0x180004793  mov     eax, [r8+10h]
0x180004797  mov     [rdx+10h], eax
0x18000479a  mov     [r8+10h], ecx
0x18000479e  mov     rax, [rdx]
0x1800047a1  test    rax, rax
0x1800047a4  jz      short loc_1800047A9
0x1800047a6  mov     rdx, [rax]
0x1800047a9  test    rdx, rdx
0x1800047ac  jnz     short loc_180004787
0x1800047ae  mov     eax, 1
0x1800047b3  jmp     short loc_1800047BE
0x1800047b5  mov     [rdi], r12
0x1800047b8  mov     eax, r12d
0x1800047bb  mov     [rbx], r12
0x1800047be  mov     r15, [rsp+48h+var_28]
0x1800047c3  mov     r14, [rsp+48h+var_20]
0x1800047c8  mov     rsi, [rsp+48h+arg_10]
0x1800047cd  mov     rbp, [rsp+48h+arg_8]
0x1800047d2  jmp     short loc_1800047D6
0x1800047d4  xor     eax, eax
0x1800047d6  add     rsp, 30h
0x1800047da  pop     r12
0x1800047dc  pop     rdi
0x1800047dd  pop     rbx
0x1800047de  retn
```
