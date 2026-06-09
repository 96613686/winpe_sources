# UpdateThreadIisData

- ea: `0x14000a5a0`
- end: `0x14000aa4c`
- name: `UpdateThreadIisData`
- size: `1196`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x140005acc`
- `0x140008588`
- `0x140008788`
- `0x140008b40`
- `0x140008c50`

## callees

- `0x14000a5a0`

## pseudocode

```c
void __fastcall UpdateThreadIisData(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  unsigned int v7; // r9d
  _DWORD *v8; // r8
  __int64 v9; // rbx
  char v10; // al
  char v11; // r11
  int v12; // ecx
  int v13; // r8d
  int v14; // edi
  unsigned int v15; // esi
  int v16; // ecx

  if ( a1 && a2 && a3 )
  {
    v7 = *(_DWORD *)(a1 + 276);
    v8 = (_DWORD *)(a2 + 8);
    v9 = 0;
    if ( v7 )
    {
      while ( *(_DWORD *)(a1 + 40 * v9 + 284) != *v8 )
      {
        v9 = (unsigned int)(v9 + 1);
        if ( (unsigned int)v9 >= v7 )
          goto LABEL_7;
      }
      if ( !a4 && (_DWORD)v9 != *(_DWORD *)(a1 + 280) )
      {
        *(_DWORD *)(a1 + 40 * v9 + 288) = dword_1400820F8 * *(_DWORD *)(a2 + 56);
        *(_DWORD *)(a1 + 40 * v9 + 292) = dword_1400820F8 * *(_DWORD *)(a2 + 60);
        *(_DWORD *)(a1 + 40 * v9 + 296) = *(_DWORD *)(a3 + 120);
        *(_DWORD *)(a1 + 40 * v9 + 300) = *(_DWORD *)(a3 + 124);
LABEL_74:
        *(_DWORD *)(a1 + 280) = v9;
        return;
      }
      v10 = 1;
    }
    else
    {
LABEL_7:
      if ( a4 )
        return;
      v10 = 0;
    }
    v11 = 0;
    if ( (unsigned int)v9 >= 0xA )
    {
      if ( !v10 )
        return;
    }
    else if ( !v10 )
    {
      *(_DWORD *)(a1 + 40 * v9 + 284) = *v8;
      v11 = 1;
      ++*(_DWORD *)(a1 + 276);
    }
    v12 = *(_DWORD *)(a2 + 56);
    v13 = dword_1400820F8;
    v14 = dword_1400820F8 * v12;
    if ( (unsigned int)(dword_1400820F8 * v12) >= *(_DWORD *)(a1 + 40 * v9 + 288) )
    {
      v14 = *(_DWORD *)(a1 + 40 * v9 + 288);
    }
    else
    {
      *(_DWORD *)(a1 + 40 * v9 + 288) = v14;
      v12 = *(_DWORD *)(a2 + 56);
      v13 = dword_1400820F8;
    }
    v15 = v13 * *(_DWORD *)(a2 + 60);
    if ( v15 >= *(_DWORD *)(a1 + 40 * v9 + 292) )
    {
      v15 = *(_DWORD *)(a1 + 40 * v9 + 292);
    }
    else
    {
      *(_DWORD *)(a1 + 40 * v9 + 292) = v15;
      v12 = *(_DWORD *)(a2 + 56);
      v13 = dword_1400820F8;
    }
    if ( !v11 )
    {
      *(_DWORD *)(a1 + 40 * v9 + 304) += *(_DWORD *)(a2 + 56) * v13 - v14;
      *(_DWORD *)(a1 + 40 * v9 + 308) += dword_1400820F8 * *(_DWORD *)(a2 + 60) - v15;
      *(_DWORD *)(a1 + 40 * v9 + 312) += *(_DWORD *)(a3 + 120) - *(_DWORD *)(a1 + 40 * v9 + 296);
      *(_DWORD *)(a1 + 40 * v9 + 316) += *(_DWORD *)(a3 + 124) - *(_DWORD *)(a1 + 40 * v9 + 300);
      v12 = *(_DWORD *)(a2 + 56);
      v13 = dword_1400820F8;
    }
    if ( *(_QWORD *)(a2 + 24) == 0x415B1D183C419E3DLL && *(_QWORD *)(a2 + 32) == 0x4BDE3889559B1AA9LL
      || *(_QWORD *)(a2 + 24) == 0x47A46398DD5EF90ALL && *(_QWORD *)(a2 + 32) == 0x5F79EFCDCE4D34ADLL )
    {
      if ( v11 )
        goto LABEL_73;
      *(_DWORD *)(a1 + 56) += v13 * v12 - v14;
      *(_DWORD *)(a1 + 56) += dword_1400820F8 * *(_DWORD *)(a2 + 60) - *(_DWORD *)(a1 + 40 * v9 + 292);
      goto LABEL_72;
    }
    if ( *(_QWORD *)(a2 + 24) == 0x473EDE92D42CF7EFLL && *(_QWORD *)(a2 + 32) == 0x3A1163A61E626C8BLL )
    {
      if ( *(_QWORD *)(a1 + 240) && !*(_QWORD *)(a1 + 248) )
      {
        if ( v11 )
          goto LABEL_73;
        *(_DWORD *)(a1 + 72) += *(_DWORD *)(a2 + 56) * v13 - *(_DWORD *)(a1 + 40 * v9 + 288);
LABEL_71:
        *(_DWORD *)(a1 + 72) += dword_1400820F8 * *(_DWORD *)(a2 + 60) - *(_DWORD *)(a1 + 40 * v9 + 292);
        goto LABEL_72;
      }
      if ( v11 )
        goto LABEL_73;
      v16 = v13 * v12 - *(_DWORD *)(a1 + 40 * v9 + 288);
      goto LABEL_39;
    }
    if ( *(_QWORD *)(a2 + 24) == 0x4BCF73EB00237F0DLL && *(_QWORD *)(a2 + 32) == 0x47585993661232A2LL )
    {
      if ( v11 )
        goto LABEL_73;
      v16 = v13 * v12 - *(_DWORD *)(a1 + 40 * v9 + 288);
      if ( *(_DWORD *)(a1 + 184) )
      {
        *(_DWORD *)(a1 + 64) += v16;
        *(_DWORD *)(a1 + 64) += dword_1400820F8 * *(_DWORD *)(a2 + 60) - *(_DWORD *)(a1 + 40 * v9 + 292);
        goto LABEL_72;
      }
LABEL_39:
      *(_DWORD *)(a1 + 60) += v16;
      *(_DWORD *)(a1 + 60) += dword_1400820F8 * *(_DWORD *)(a2 + 60) - *(_DWORD *)(a1 + 40 * v9 + 292);
LABEL_72:
      v13 = dword_1400820F8;
      goto LABEL_73;
    }
    if ( *(_QWORD *)(a2 + 24) == 0x46090D2EE2E55403LL && *(_QWORD *)(a2 + 32) == 0xC01340A00DBE70A4uLL
      || *(_QWORD *)(a2 + 24) == 0x42B03627E3642ACCLL && *(_QWORD *)(a2 + 32) == 0x73B03AA7B867283LL )
    {
      if ( !v11 && *(_BYTE *)(a2 + 45) != 19 )
      {
        *(_DWORD *)(a1 + 76) += v13 * v12 - *(_DWORD *)(a1 + 40 * v9 + 288);
        *(_DWORD *)(a1 + 76) += dword_1400820F8 * *(_DWORD *)(a2 + 60) - *(_DWORD *)(a1 + 40 * v9 + 292);
        goto LABEL_72;
      }
LABEL_73:
      *(_DWORD *)(a1 + 40 * v9 + 288) = *(_DWORD *)(a2 + 56) * v13;
      *(_DWORD *)(a1 + 40 * v9 + 292) = dword_1400820F8 * *(_DWORD *)(a2 + 60);
      *(_DWORD *)(a1 + 40 * v9 + 296) = *(_DWORD *)(a3 + 120);
      *(_DWORD *)(a1 + 40 * v9 + 300) = *(_DWORD *)(a3 + 124);
      if ( a4 )
        return;
      goto LABEL_74;
    }
    if ( *(_QWORD *)(a2 + 24) == 0x4B73EDA02E94E6C7LL && *(_QWORD *)(a2 + 32) == 0x271CCEED29251090LL )
    {
      if ( !*(_QWORD *)(a1 + 240) || *(_QWORD *)(a1 + 248) )
      {
        if ( v11 )
          goto LABEL_73;
        v16 = v13 * v12 - *(_DWORD *)(a1 + 40 * v9 + 288);
        goto LABEL_58;
      }
    }
    else
    {
      if ( (*(_QWORD *)(a2 + 24) != 0x4C373FC41FC299FALL || *(_QWORD *)(a2 + 32) != 0x70021D915BDE0D91LL)
        && (*(_QWORD *)(a2 + 24) != 0x459479D306A01367LL || *(_QWORD *)(a2 + 32) != 0x79463C6021C7B38ELL)
        && (*(_QWORD *)(a2 + 24) != 0x4EAE663C71BDA656LL || *(_QWORD *)(a2 + 32) != 0xCD0FFAF149A77A97uLL) )
      {
        goto LABEL_73;
      }
      if ( !*(_QWORD *)(a1 + 240) )
      {
        if ( v11 )
          goto LABEL_73;
        v16 = v13 * v12 - *(_DWORD *)(a1 + 40 * v9 + 288);
        if ( !*(_QWORD *)(a1 + 216) )
          goto LABEL_39;
LABEL_58:
        *(_DWORD *)(a1 + 68) += v16;
        *(_DWORD *)(a1 + 68) += dword_1400820F8 * *(_DWORD *)(a2 + 60) - *(_DWORD *)(a1 + 40 * v9 + 292);
        goto LABEL_72;
      }
    }
    if ( v11 )
      goto LABEL_73;
    *(_DWORD *)(a1 + 72) += v13 * v12 - *(_DWORD *)(a1 + 40 * v9 + 288);
    goto LABEL_71;
  }
}

```

## disassembly

```asm
0x14000a5a0  test    rcx, rcx
0x14000a5a3  jz      locret_14000AA4B
0x14000a5a9  push    rbx
0x14000a5aa  push    rbp
0x14000a5ab  push    rsi
0x14000a5ac  push    rdi
0x14000a5ad  push    r14
0x14000a5af  push    r15
0x14000a5b1  mov     r15b, r9b
0x14000a5b4  mov     rbp, r8
0x14000a5b7  mov     r10, rcx
0x14000a5ba  test    rdx, rdx
0x14000a5bd  jz      loc_14000AA43
0x14000a5c3  test    r8, r8
0x14000a5c6  jz      loc_14000AA43
0x14000a5cc  mov     r9d, [rcx+114h]
0x14000a5d3  lea     r8, [rdx+8]
0x14000a5d7  xor     ebx, ebx
0x14000a5d9  test    r9d, r9d
0x14000a5dc  jz      short loc_14000A5F6
0x14000a5de  mov     r11d, [r8]
0x14000a5e1  lea     rcx, [rbx+rbx*4]
0x14000a5e5  cmp     [r10+rcx*8+11Ch], r11d
0x14000a5ed  jz      short loc_14000A628
0x14000a5ef  inc     ebx
0x14000a5f1  cmp     ebx, r9d
0x14000a5f4  jb      short loc_14000A5E1
0x14000a5f6  test    r15b, r15b
0x14000a5f9  jnz     loc_14000AA43
0x14000a5ff  xor     al, al
0x14000a601  xor     r11b, r11b
0x14000a604  cmp     ebx, 0Ah
0x14000a607  jnb     short loc_14000A679
0x14000a609  test    al, al
0x14000a60b  jnz     short loc_14000A681
0x14000a60d  mov     eax, [r8]
0x14000a610  lea     rcx, [rbx+rbx*4]
0x14000a614  mov     [r10+rcx*8+11Ch], eax
0x14000a61c  mov     r11b, 1
0x14000a61f  inc     dword ptr [r10+114h]
0x14000a626  jmp     short loc_14000A681
0x14000a628  test    r15b, r15b
0x14000a62b  jnz     short loc_14000A675
0x14000a62d  cmp     ebx, [r10+118h]
0x14000a634  jz      short loc_14000A675
0x14000a636  mov     eax, [rdx+38h]
0x14000a639  imul    eax, cs:dword_1400820F8
0x14000a640  mov     [r10+rcx*8+120h], eax
0x14000a648  mov     eax, [rdx+3Ch]
0x14000a64b  imul    eax, cs:dword_1400820F8
0x14000a652  mov     [r10+rcx*8+124h], eax
0x14000a65a  mov     eax, [rbp+78h]
0x14000a65d  mov     [r10+rcx*8+128h], eax
0x14000a665  mov     eax, [rbp+7Ch]
0x14000a668  mov     [r10+rcx*8+12Ch], eax
0x14000a670  jmp     loc_14000AA3C
0x14000a675  mov     al, 1
0x14000a677  jmp     short loc_14000A601
0x14000a679  test    al, al
0x14000a67b  jz      loc_14000AA43
0x14000a681  mov     ecx, [rdx+38h]
0x14000a684  lea     r9, [rbx+rbx*4]
0x14000a688  mov     r8d, cs:dword_1400820F8
0x14000a68f  mov     edi, ecx
0x14000a691  mov     eax, [r10+r9*8+120h]
0x14000a699  imul    edi, r8d
0x14000a69d  cmp     edi, eax
0x14000a69f  jnb     short loc_14000A6B5
0x14000a6a1  mov     [r10+r9*8+120h], edi
0x14000a6a9  mov     ecx, [rdx+38h]
0x14000a6ac  mov     r8d, cs:dword_1400820F8
0x14000a6b3  jmp     short loc_14000A6B7
0x14000a6b5  mov     edi, eax
0x14000a6b7  mov     esi, [rdx+3Ch]
0x14000a6ba  mov     eax, [r10+r9*8+124h]
0x14000a6c2  imul    esi, r8d
0x14000a6c6  cmp     esi, eax
0x14000a6c8  jnb     short loc_14000A6DE
0x14000a6ca  mov     [r10+r9*8+124h], esi
0x14000a6d2  mov     ecx, [rdx+38h]
0x14000a6d5  mov     r8d, cs:dword_1400820F8
0x14000a6dc  jmp     short loc_14000A6E0
0x14000a6de  mov     esi, eax
0x14000a6e0  test    r11b, r11b
0x14000a6e3  jnz     short loc_14000A739
0x14000a6e5  imul    r8d, [rdx+38h]
0x14000a6ea  sub     r8d, edi
0x14000a6ed  add     [r10+r9*8+130h], r8d
0x14000a6f5  mov     eax, [rdx+3Ch]
0x14000a6f8  imul    eax, cs:dword_1400820F8
0x14000a6ff  sub     eax, esi
0x14000a701  add     [r10+r9*8+134h], eax
0x14000a709  mov     eax, [rbp+78h]
0x14000a70c  sub     eax, [r10+r9*8+128h]
0x14000a714  add     [r10+r9*8+138h], eax
0x14000a71c  mov     eax, [rbp+7Ch]
0x14000a71f  sub     eax, [r10+r9*8+12Ch]
0x14000a727  add     [r10+r9*8+13Ch], eax
0x14000a72f  mov     ecx, [rdx+38h]
0x14000a732  mov     r8d, cs:dword_1400820F8
0x14000a739  mov     rax, [rdx+18h]
0x14000a73d  cmp     rax, cs:qword_140043AF8
0x14000a744  jnz     short loc_14000A753
0x14000a746  mov     rax, [rdx+20h]
0x14000a74a  cmp     rax, cs:qword_140043B00
0x14000a751  jz      short loc_14000A76D
0x14000a753  mov     rax, [rdx+18h]
0x14000a757  cmp     rax, cs:qword_140043AE8
0x14000a75e  jnz     short loc_14000A79B
0x14000a760  mov     rax, [rdx+20h]
0x14000a764  cmp     rax, cs:qword_140043AF0
0x14000a76b  jnz     short loc_14000A79B
0x14000a76d  test    r11b, r11b
0x14000a770  jnz     loc_14000A9FA
0x14000a776  imul    ecx, r8d
0x14000a77a  sub     ecx, edi
0x14000a77c  add     [r10+38h], ecx
0x14000a780  mov     eax, [rdx+3Ch]
0x14000a783  imul    eax, cs:dword_1400820F8
0x14000a78a  sub     eax, [r10+r9*8+124h]
0x14000a792  add     [r10+38h], eax
0x14000a796  jmp     loc_14000A9F3
0x14000a79b  mov     rax, [rdx+18h]
0x14000a79f  cmp     rax, cs:qword_140043AD8
0x14000a7a6  jnz     short loc_14000A81C
0x14000a7a8  mov     rax, [rdx+20h]
0x14000a7ac  cmp     rax, cs:qword_140043AE0
0x14000a7b3  jnz     short loc_14000A81C
0x14000a7b5  cmp     qword ptr [r10+0F0h], 0
0x14000a7bd  jz      short loc_14000A7E8
0x14000a7bf  cmp     qword ptr [r10+0F8h], 0
0x14000a7c7  jnz     short loc_14000A7E8
0x14000a7c9  test    r11b, r11b
0x14000a7cc  jnz     loc_14000A9FA
0x14000a7d2  imul    r8d, [rdx+38h]
0x14000a7d7  sub     r8d, [r10+r9*8+120h]
0x14000a7df  add     [r10+48h], r8d
0x14000a7e3  jmp     loc_14000A9DD
0x14000a7e8  test    r11b, r11b
0x14000a7eb  jnz     loc_14000A9FA
0x14000a7f1  imul    ecx, r8d
0x14000a7f5  sub     ecx, [r10+r9*8+120h]
0x14000a7fd  add     [r10+3Ch], ecx
0x14000a801  mov     eax, [rdx+3Ch]
0x14000a804  imul    eax, cs:dword_1400820F8
0x14000a80b  sub     eax, [r10+r9*8+124h]
0x14000a813  add     [r10+3Ch], eax
0x14000a817  jmp     loc_14000A9F3
0x14000a81c  mov     rax, [rdx+18h]
0x14000a820  cmp     rax, cs:qword_140043AC8
0x14000a827  jnz     short loc_14000A874
0x14000a829  mov     rax, [rdx+20h]
0x14000a82d  cmp     rax, cs:qword_140043AD0
0x14000a834  jnz     short loc_14000A874
0x14000a836  test    r11b, r11b
0x14000a839  jnz     loc_14000A9FA
0x14000a83f  imul    ecx, r8d
0x14000a843  sub     ecx, [r10+r9*8+120h]
0x14000a84b  cmp     dword ptr [r10+0B8h], 0
0x14000a853  jbe     short loc_14000A7FD
0x14000a855  add     [r10+40h], ecx
0x14000a859  mov     eax, [rdx+3Ch]
0x14000a85c  imul    eax, cs:dword_1400820F8
0x14000a863  sub     eax, [r10+r9*8+124h]
0x14000a86b  add     [r10+40h], eax
0x14000a86f  jmp     loc_14000A9F3
0x14000a874  mov     rax, [rdx+18h]
0x14000a878  cmp     rax, cs:qword_140043AB8
0x14000a87f  jnz     short loc_14000A88E
0x14000a881  mov     rax, [rdx+20h]
0x14000a885  cmp     rax, cs:qword_140043AC0
0x14000a88c  jz      short loc_14000A8A8
0x14000a88e  mov     rax, [rdx+18h]
0x14000a892  cmp     rax, cs:qword_140043AA8
0x14000a899  jnz     short loc_14000A8E6
0x14000a89b  mov     rax, [rdx+20h]
0x14000a89f  cmp     rax, cs:qword_140043AB0
0x14000a8a6  jnz     short loc_14000A8E6
0x14000a8a8  test    r11b, r11b
0x14000a8ab  jnz     loc_14000A9FA
0x14000a8b1  cmp     byte ptr [rdx+2Dh], 13h
0x14000a8b5  jz      loc_14000A9FA
0x14000a8bb  imul    ecx, r8d
0x14000a8bf  sub     ecx, [r10+r9*8+120h]
0x14000a8c7  add     [r10+4Ch], ecx
0x14000a8cb  mov     eax, [rdx+3Ch]
0x14000a8ce  imul    eax, cs:dword_1400820F8
0x14000a8d5  sub     eax, [r10+r9*8+124h]
0x14000a8dd  add     [r10+4Ch], eax
0x14000a8e1  jmp     loc_14000A9F3
0x14000a8e6  mov     rax, [rdx+18h]
0x14000a8ea  cmp     rax, cs:qword_140043A98
0x14000a8f1  jnz     short loc_14000A94C
0x14000a8f3  mov     rax, [rdx+20h]
0x14000a8f7  cmp     rax, cs:qword_140043AA0
0x14000a8fe  jnz     short loc_14000A94C
0x14000a900  cmp     qword ptr [r10+0F0h], 0
0x14000a908  jz      short loc_14000A918
0x14000a90a  cmp     qword ptr [r10+0F8h], 0
0x14000a912  jz      loc_14000A9C8
0x14000a918  test    r11b, r11b
0x14000a91b  jnz     loc_14000A9FA
0x14000a921  imul    ecx, r8d
0x14000a925  sub     ecx, [r10+r9*8+120h]
0x14000a92d  add     [r10+44h], ecx
0x14000a931  mov     eax, [rdx+3Ch]
0x14000a934  imul    eax, cs:dword_1400820F8
0x14000a93b  sub     eax, [r10+r9*8+124h]
0x14000a943  add     [r10+44h], eax
0x14000a947  jmp     loc_14000A9F3
0x14000a94c  mov     rax, [rdx+18h]
0x14000a950  cmp     rax, cs:qword_140043A68
0x14000a957  jnz     short loc_14000A966
0x14000a959  mov     rax, [rdx+20h]
0x14000a95d  cmp     rax, cs:qword_140043A70
0x14000a964  jz      short loc_14000A99A
0x14000a966  mov     rax, [rdx+18h]
0x14000a96a  cmp     rax, cs:qword_140043A58
0x14000a971  jnz     short loc_14000A980
0x14000a973  mov     rax, [rdx+20h]
0x14000a977  cmp     rax, cs:qword_140043A60
0x14000a97e  jz      short loc_14000A99A
0x14000a980  mov     rax, [rdx+18h]
0x14000a984  cmp     rax, cs:qword_140043A48
0x14000a98b  jnz     short loc_14000A9FA
0x14000a98d  mov     rax, [rdx+20h]
0x14000a991  cmp     rax, cs:qword_140043A50
0x14000a998  jnz     short loc_14000A9FA
0x14000a99a  cmp     qword ptr [r10+0F0h], 0
0x14000a9a2  jnz     short loc_14000A9C8
0x14000a9a4  test    r11b, r11b
0x14000a9a7  jnz     short loc_14000A9FA
0x14000a9a9  imul    ecx, r8d
0x14000a9ad  sub     ecx, [r10+r9*8+120h]
0x14000a9b5  cmp     qword ptr [r10+0D8h], 0
0x14000a9bd  jnz     loc_14000A92D
0x14000a9c3  jmp     loc_14000A7FD
0x14000a9c8  test    r11b, r11b
0x14000a9cb  jnz     short loc_14000A9FA
0x14000a9cd  imul    ecx, r8d
0x14000a9d1  sub     ecx, [r10+r9*8+120h]
0x14000a9d9  add     [r10+48h], ecx
0x14000a9dd  mov     eax, [rdx+3Ch]
0x14000a9e0  imul    eax, cs:dword_1400820F8
0x14000a9e7  sub     eax, [r10+r9*8+124h]
0x14000a9ef  add     [r10+48h], eax
0x14000a9f3  mov     r8d, cs:dword_1400820F8
0x14000a9fa  imul    r8d, [rdx+38h]
0x14000a9ff  lea     rcx, [rbx+rbx*4]
0x14000aa03  mov     [r10+r9*8+120h], r8d
0x14000aa0b  mov     eax, [rdx+3Ch]
0x14000aa0e  imul    eax, cs:dword_1400820F8
0x14000aa15  mov     [r10+r9*8+124h], eax
0x14000aa1d  mov     eax, [rbp+78h]
0x14000aa20  mov     [r10+rcx*8+128h], eax
0x14000aa28  lea     rcx, [rbx+rbx*4]
0x14000aa2c  mov     eax, [rbp+7Ch]
0x14000aa2f  mov     [r10+rcx*8+12Ch], eax
0x14000aa37  test    r15b, r15b
0x14000aa3a  jnz     short loc_14000AA43
0x14000aa3c  mov     [r10+118h], ebx
0x14000aa43  pop     r15
0x14000aa45  pop     r14
0x14000aa47  pop     rdi
0x14000aa48  pop     rsi
0x14000aa49  pop     rbp
0x14000aa4a  pop     rbx
0x14000aa4b  retn
```
