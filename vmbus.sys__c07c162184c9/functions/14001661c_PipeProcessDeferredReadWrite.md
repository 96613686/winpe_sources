# PipeProcessDeferredReadWrite

- ea: `0x14001661c`
- end: `0x140016841`
- name: `PipeProcessDeferredReadWrite`
- size: `549`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140002b60`
- `0x140002d20`
- `0x140015f50`

## callees

- `0x1400026f0`
- `0x140015034`
- `0x1400150a0`
- `0x140015bf8`
- `0x14001617c`
- `0x14001661c`
- `0x140016ab0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400167b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400167b5`

## pseudocode

```c
char __fastcall PipeProcessDeferredReadWrite(__int64 a1, __int64 a2)
{
  char v2; // si
  int v5; // edi
  _QWORD **v6; // r14
  int v7; // r12d
  _QWORD *v8; // rdi
  unsigned int v9; // eax
  _QWORD *v10; // rax
  int v11; // eax
  int v12; // r12d
  _QWORD **v13; // r14
  _QWORD *v14; // rdi
  int v15; // eax
  unsigned int v16; // eax
  _QWORD *v17; // rax
  __int64 v18; // rax
  _QWORD *v19; // rcx
  char v20; // r11
  char v22; // [rsp+60h] [rbp+8h]
  int v23; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  if ( !*(_BYTE *)(a1 + 274) )
  {
    v5 = *(_DWORD *)(a1 + 132);
    v6 = (_QWORD **)(a1 + 16);
    v23 = v5;
    while ( 1 )
    {
      v7 = v5;
      while ( 1 )
      {
        v8 = *v6;
        if ( *v6 == v6 )
          break;
        v9 = PipeTryRead(a1, v8 - 17, &v23);
        if ( v9 == -1073741807 )
          break;
        if ( (unsigned __int8)PipeDequeueIrpForCompletion(v8 - 17, v9) )
        {
          v10 = *(_QWORD **)(a2 + 8);
          if ( *v10 != a2 )
LABEL_29:
            __fastfail(3u);
          *v8 = a2;
          v8[1] = v10;
          *v10 = v8;
          *(_QWORD *)(a2 + 8) = v8;
        }
      }
      v5 = v23;
      if ( v23 == v7 )
        break;
      v11 = PkCompleteRemoval(a1 + 64);
      if ( v11 == 532 )
      {
        v2 = 1;
      }
      else if ( v11 == 531 )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(a1 + 88) + 64LL) & 1) == 0 )
          v2 = 1;
        break;
      }
    }
  }
  v12 = *(_DWORD *)(a1 + 192);
  v13 = (_QWORD **)(a1 + 32);
  v23 = v12;
  v22 = 0;
  while ( 1 )
  {
    v14 = *v13;
    if ( *v13 == v13 )
      break;
    v15 = *((_DWORD *)v14 - 4);
    if ( v15 == 1 )
    {
      v22 = 1;
      v16 = PipeTryWriteIrp(a1, v14 - 17, &v23);
      if ( v16 == -2147483643 )
        break;
      if ( (unsigned __int8)PipeDequeueIrpForCompletion(v14 - 17, v16) )
      {
        v17 = *(_QWORD **)(a2 + 8);
        if ( *v17 != a2 )
          goto LABEL_29;
        *v14 = a2;
        v14[1] = v17;
        *v17 = v14;
        *(_QWORD *)(a2 + 8) = v14;
      }
    }
    else if ( (unsigned int)(v15 - 2) <= 1 )
    {
      if ( (unsigned int)PipeGpadTryWritePacket(a1, v14 - 2, &v23) == -2147483643 )
        break;
      v18 = *v14;
      if ( *(_QWORD **)(*v14 + 8LL) != v14 )
        goto LABEL_29;
      v19 = (_QWORD *)v14[1];
      if ( (_QWORD *)*v19 != v14 )
        goto LABEL_29;
      *v19 = v18;
      *(_QWORD *)(v18 + 8) = v19;
      if ( *((_DWORD *)v14 - 4) == 3 )
      {
        ExFreePoolWithTag(v14 - 2, 0x73756256u);
      }
      else
      {
        v14[1] = v14;
        *v14 = v14;
      }
    }
  }
  if ( v23 != v12 && ((unsigned int)PkCompleteInsertion(a1 + 64) == 532 || *(_BYTE *)(a1 + 444)) )
  {
    if ( v22 || *v13 != v13 )
    {
      v2 = v20;
      goto LABEL_37;
    }
    *(_BYTE *)(a1 + 444) = v20;
  }
  if ( v2 )
LABEL_37:
    *(_BYTE *)(a1 + 444) = 0;
  return v2;
}

```

## disassembly

```asm
0x14001661c  mov     [rsp+arg_8], rbx
0x140016621  push    rbp
0x140016622  push    rsi
0x140016623  push    rdi
0x140016624  push    r12
0x140016626  push    r13
0x140016628  push    r14
0x14001662a  push    r15
0x14001662c  sub     rsp, 20h
0x140016630  xor     sil, sil
0x140016633  mov     rbp, rdx
0x140016636  mov     rbx, rcx
0x140016639  mov     r11d, 1
0x14001663f  cmp     [rcx+112h], sil
0x140016646  jnz     loc_1400166F3
0x14001664c  mov     edi, [rcx+84h]
0x140016652  lea     r14, [rcx+10h]
0x140016656  mov     [rsp+58h+arg_10], edi
0x14001665a  mov     r12d, edi
0x14001665d  mov     rdi, [r14]
0x140016660  cmp     rdi, r14
0x140016663  jz      short loc_1400166AE
0x140016665  lea     r15, [rdi-88h]
0x14001666c  mov     rcx, rbx
0x14001666f  mov     rdx, r15
0x140016672  lea     r8, [rsp+58h+arg_10]
0x140016677  call    PipeTryRead
0x14001667c  cmp     eax, 0C0000011h
0x140016681  jz      short loc_1400166AE
0x140016683  mov     edx, eax
0x140016685  mov     rcx, r15
0x140016688  call    PipeDequeueIrpForCompletion
0x14001668d  test    al, al
0x14001668f  jz      short loc_14001665D
0x140016691  mov     rax, [rbp+8]
0x140016695  cmp     [rax], rbp
0x140016698  jnz     loc_1400167D5
0x14001669e  mov     [rdi], rbp
0x1400166a1  mov     [rdi+8], rax
0x1400166a5  mov     [rax], rdi
0x1400166a8  mov     [rbp+8], rdi
0x1400166ac  jmp     short loc_14001665D
0x1400166ae  mov     edi, [rsp+58h+arg_10]
0x1400166b2  cmp     edi, r12d
0x1400166b5  jz      short loc_1400166ED
0x1400166b7  lea     rcx, [rbx+40h]
0x1400166bb  mov     edx, edi
0x1400166bd  call    PkCompleteRemoval
0x1400166c2  cmp     eax, 214h
0x1400166c7  jnz     short loc_1400166CE
0x1400166c9  mov     sil, 1
0x1400166cc  jmp     short loc_14001665A
0x1400166ce  cmp     eax, 213h
0x1400166d3  jnz     short loc_14001665A
0x1400166d5  mov     rax, [rbx+58h]
0x1400166d9  mov     r11d, 1
0x1400166df  movzx   esi, sil
0x1400166e3  test    [rax+40h], r11b
0x1400166e7  cmovz   esi, r11d
0x1400166eb  jmp     short loc_1400166F3
0x1400166ed  mov     r11d, 1
0x1400166f3  mov     r12d, [rbx+0C0h]
0x1400166fa  lea     r14, [rbx+20h]
0x1400166fe  mov     [rsp+58h+arg_10], r12d
0x140016703  mov     [rsp+58h+arg_0], 0
0x140016708  mov     rdi, [r14]
0x14001670b  cmp     rdi, r14
0x14001670e  jz      loc_1400167E2
0x140016714  lea     r15, [rdi-10h]
0x140016718  mov     eax, [r15]
0x14001671b  cmp     eax, r11d
0x14001671e  jnz     short loc_14001676F
0x140016720  lea     r8, [rsp+58h+arg_10]
0x140016725  mov     [rsp+58h+arg_0], r11b
0x14001672a  lea     rdx, [r15-78h]
0x14001672e  mov     rcx, rbx
0x140016731  call    PipeTryWriteIrp
0x140016736  cmp     eax, 80000005h
0x14001673b  jz      loc_1400167DC
0x140016741  mov     edx, eax
0x140016743  lea     rcx, [r15-78h]
0x140016747  call    PipeDequeueIrpForCompletion
0x14001674c  mov     r11d, 1
0x140016752  test    al, al
0x140016754  jz      short loc_140016708
0x140016756  mov     rax, [rbp+8]
0x14001675a  cmp     [rax], rbp
0x14001675d  jnz     short loc_1400167D5
0x14001675f  mov     [rdi], rbp
0x140016762  mov     [rdi+8], rax
0x140016766  mov     [rax], rdi
0x140016769  mov     [rbp+8], rdi
0x14001676d  jmp     short loc_140016708
0x14001676f  add     eax, 0FFFFFFFEh
0x140016772  cmp     eax, r11d
0x140016775  ja      short loc_140016708
0x140016777  lea     r8, [rsp+58h+arg_10]
0x14001677c  mov     rdx, r15
0x14001677f  mov     rcx, rbx
0x140016782  call    PipeGpadTryWritePacket
0x140016787  cmp     eax, 80000005h
0x14001678c  jz      short loc_1400167DC
0x14001678e  mov     rax, [rdi]
0x140016791  cmp     [rax+8], rdi
0x140016795  jnz     short loc_1400167D5
0x140016797  mov     rcx, [rdi+8]
0x14001679b  cmp     [rcx], rdi
0x14001679e  jnz     short loc_1400167D5
0x1400167a0  mov     [rcx], rax
0x1400167a3  mov     [rax+8], rcx
0x1400167a7  cmp     dword ptr [r15], 3
0x1400167ab  jnz     short loc_1400167C3
0x1400167ad  mov     edx, 73756256h; Tag
0x1400167b2  mov     rcx, r15; P
0x1400167b5  call    cs:__imp_ExFreePoolWithTag
0x1400167bc  nop     dword ptr [rax+rax+00h]
0x1400167c1  jmp     short loc_1400167CA
0x1400167c3  mov     [rdi+8], rdi
0x1400167c7  mov     [rdi], rdi
0x1400167ca  mov     r11d, 1
0x1400167d0  jmp     loc_140016708
0x1400167d5  mov     ecx, 3
0x1400167da  int     29h; Win8: RtlFailFast(ecx)
0x1400167dc  mov     r11d, 1
0x1400167e2  mov     edx, [rsp+58h+arg_10]
0x1400167e6  cmp     edx, r12d
0x1400167e9  jz      short loc_140016817
0x1400167eb  lea     rcx, [rbx+40h]
0x1400167ef  call    PkCompleteInsertion
0x1400167f4  cmp     eax, 214h
0x1400167f9  jz      short loc_140016804
0x1400167fb  cmp     byte ptr [rbx+1BCh], 0
0x140016802  jz      short loc_140016817
0x140016804  cmp     [rsp+58h+arg_0], 0
0x140016809  jnz     short loc_14001683C
0x14001680b  cmp     [r14], r14
0x14001680e  jnz     short loc_14001683C
0x140016810  mov     [rbx+1BCh], r11b
0x140016817  test    sil, sil
0x14001681a  jz      short loc_140016823
0x14001681c  mov     byte ptr [rbx+1BCh], 0
0x140016823  mov     rbx, [rsp+58h+arg_8]
0x140016828  mov     al, sil
0x14001682b  add     rsp, 20h
0x14001682f  pop     r15
0x140016831  pop     r14
0x140016833  pop     r13
0x140016835  pop     r12
0x140016837  pop     rdi
0x140016838  pop     rsi
0x140016839  pop     rbp
0x14001683a  retn
0x14001683c  mov     sil, r11b
0x14001683f  jmp     short loc_14001681C
```
