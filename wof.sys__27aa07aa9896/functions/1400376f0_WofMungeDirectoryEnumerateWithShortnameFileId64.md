# WofMungeDirectoryEnumerateWithShortnameFileId64

- ea: `0x1400376f0`
- end: `0x140037d0d`
- name: `WofMungeDirectoryEnumerateWithShortnameFileId64`
- size: `1565`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140036e70`

## callees

- `0x140011590`
- `0x1400115b0`
- `0x140022fcc`
- `0x1400230a8`
- `0x140023108`
- `0x140023150`
- `0x140023198`
- `0x140035ed0`
- `0x1400376f0`

## pseudocode

```c
__int64 __fastcall WofMungeDirectoryEnumerateWithShortnameFileId64(
        int a1,
        unsigned __int8 *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        char a6,
        unsigned int *a7)
{
  unsigned __int8 *v7; // rdi
  unsigned __int64 v8; // r15
  unsigned int v9; // esi
  unsigned int v10; // r12d
  unsigned __int8 *v11; // r13
  unsigned int v12; // edx
  unsigned int v13; // r14d
  unsigned int *v14; // r15
  void *v15; // rcx
  __int64 v16; // r8
  size_t v17; // r8
  void *v18; // rdx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  unsigned int v22; // eax
  unsigned int *v23; // rcx
  unsigned int *v24; // rcx
  unsigned int v25; // eax
  unsigned __int8 v26; // al
  unsigned __int8 *v27; // rcx
  size_t v28; // r8
  void *v29; // rdx
  void *v30; // rcx
  unsigned int v31; // eax
  unsigned int *v32; // rcx
  void *v33; // rdx
  unsigned int v34; // eax
  _DWORD *v35; // rcx
  unsigned int v36; // r14d
  unsigned int v37; // r8d
  size_t v38; // r8
  void *v39; // rcx
  void *v40; // rcx
  unsigned int v41; // eax
  unsigned int *v42; // rcx
  unsigned int *v43; // rcx
  unsigned int v44; // eax
  _QWORD *v45; // rcx
  unsigned __int8 v46; // al
  unsigned __int8 *v47; // rcx
  size_t v48; // r8
  void *v49; // rdx
  void *v50; // rcx
  unsigned int v51; // eax
  unsigned int *v52; // rcx
  unsigned int *v53; // rcx
  unsigned int v54; // ecx
  unsigned int *v55; // rcx
  unsigned int v56; // ecx
  unsigned int v57; // eax
  unsigned int *v58; // rcx
  int v60; // [rsp+90h] [rbp+8h]
  unsigned __int64 v61; // [rsp+98h] [rbp+10h]
  __int64 v62; // [rsp+A8h] [rbp+20h]

  v62 = a4;
  v60 = a1;
  v7 = a2;
  v8 = (unsigned __int64)&a2[a3];
  v61 = v8;
  v9 = 0;
  v10 = 0;
  v11 = a2;
  v12 = a5;
  while ( 1 )
  {
    v13 = *((_DWORD *)v11 + 15);
    if ( v13 >= a3 - 106 )
      v13 = a3 - 106;
    switch ( a1 )
    {
      case 3:
        v14 = (unsigned int *)(a4 + v9);
        v10 = v13 + 94;
        if ( a6 )
          RtlCopyToUser(v14, v7, 0x38u);
        else
          RtlCopyVolatileMemory(v14, v7, 0x38u);
        v21 = (char *)v14 + 69;
        if ( a6 )
          RtlSetUserMemory(v21);
        else
          RtlSetVolatileMemory(v21, 0, 0x19u);
        v22 = *((_DWORD *)v11 + 14);
        if ( *((_DWORD *)v11 + 17) == FileTag )
        {
          if ( byte_140018454 )
            v22 &= ~0x400u;
          if ( byte_140018455 )
            v22 &= ~0x200u;
          if ( !v22 )
            v22 = 128;
          v53 = v14 + 14;
          if ( a6 )
            RtlWriteULongToUser(v53, v22);
          else
            *v53 = v22;
          v54 = byte_140018454 ? *((_DWORD *)v7 + 16) : *((_DWORD *)v11 + 17);
          if ( a6 )
            RtlWriteULongToUser(v14 + 16, v54);
          else
            v14[16] = v54;
        }
        else
        {
          v23 = v14 + 14;
          if ( a6 )
            RtlWriteULongToUser(v23, v22);
          else
            *v23 = v22;
          v24 = v14 + 16;
          v25 = (*((_DWORD *)v11 + 14) & 0x400) != 0 ? *((_DWORD *)v11 + 17) : *((_DWORD *)v11 + 16);
          if ( a6 )
            RtlWriteULongToUser(v24, v25);
          else
            *v24 = v25;
        }
        v26 = v7[80];
        v27 = (unsigned __int8 *)(v14 + 17);
        if ( a6 )
          RtlWriteUCharToUser(v27, v26);
        else
          *v27 = v26;
        v28 = (char)v7[80];
        v29 = v7 + 82;
        v30 = (char *)v14 + 70;
        if ( a6 )
          RtlCopyToUser(v30, v29, v28);
        else
          RtlCopyVolatileMemory(v30, v29, v28);
        v31 = *((_DWORD *)v11 + 15);
        v32 = v14 + 15;
        if ( a6 )
          RtlWriteULongToUser(v32, v31);
        else
          *v32 = v31;
        v20 = (char *)v14 + 94;
        break;
      case 37:
        v14 = (unsigned int *)(a4 + v9);
        v10 = v13 + 104;
        if ( a6 )
          RtlCopyToUser(v14, v7, 0x38u);
        else
          RtlCopyVolatileMemory(v14, v7, 0x38u);
        v40 = (char *)v14 + 69;
        if ( a6 )
          RtlSetUserMemory(v40);
        else
          RtlSetVolatileMemory(v40, 0, 0x1Bu);
        v41 = *((_DWORD *)v7 + 14);
        if ( *((_DWORD *)v7 + 17) == FileTag )
        {
          if ( byte_140018454 )
            v41 &= ~0x400u;
          if ( byte_140018455 )
            v41 &= ~0x200u;
          if ( !v41 )
            v41 = 128;
          v55 = v14 + 14;
          if ( a6 )
            RtlWriteULongToUser(v55, v41);
          else
            *v55 = v41;
          v56 = byte_140018454 ? *((_DWORD *)v7 + 16) : *((_DWORD *)v7 + 17);
          if ( a6 )
            RtlWriteULongToUser(v14 + 16, v56);
          else
            v14[16] = v56;
        }
        else
        {
          v42 = v14 + 14;
          if ( a6 )
            RtlWriteULongToUser(v42, v41);
          else
            *v42 = v41;
          v43 = v14 + 16;
          v44 = (*((_DWORD *)v7 + 14) & 0x400) != 0 ? *((_DWORD *)v7 + 17) : *((_DWORD *)v7 + 16);
          if ( a6 )
            RtlWriteULongToUser(v43, v44);
          else
            *v43 = v44;
        }
        v45 = v14 + 24;
        if ( a6 )
          RtlWriteULong64ToUser(v45, *((_QWORD *)v7 + 9));
        else
          *v45 = *((_QWORD *)v7 + 9);
        v46 = v7[80];
        v47 = (unsigned __int8 *)(v14 + 17);
        if ( a6 )
          RtlWriteUCharToUser(v47, v46);
        else
          *v47 = v46;
        v48 = (char)v7[80];
        v49 = v7 + 82;
        v50 = (char *)v14 + 70;
        if ( a6 )
          RtlCopyToUser(v50, v49, v48);
        else
          RtlCopyVolatileMemory(v50, v49, v48);
        v51 = *((_DWORD *)v11 + 15);
        v52 = v14 + 15;
        if ( a6 )
          RtlWriteULongToUser(v52, v51);
        else
          *v52 = v51;
        v20 = v14 + 26;
        break;
      case 79:
        v14 = (unsigned int *)(a4 + v9);
        v10 = v13 + 106;
        if ( a6 )
          RtlCopyToUser(v14, v7, 0x52u);
        else
          RtlCopyVolatileMemory(v14, v7, 0x52u);
        v15 = (char *)v14 + 81;
        if ( a6 )
          RtlSetUserMemory(v15);
        else
          RtlSetVolatileMemory(v15, 0, 0x19u);
        if ( *((_DWORD *)v7 + 17) == FileTag )
        {
          v57 = WofSanitizeAttributes(*((unsigned int *)v7 + 14), 0, v16);
          v58 = v14 + 14;
          if ( a6 )
            RtlWriteULongToUser(v58, v57);
          else
            *v58 = v57;
          if ( byte_140018454 )
          {
            if ( a6 )
              RtlWriteULongToUser(v14 + 17, 0);
            else
              v14[17] = 0;
          }
        }
        v17 = (char)v7[80];
        v18 = v7 + 82;
        v19 = (char *)v14 + 82;
        if ( a6 )
          RtlCopyToUser(v19, v18, v17);
        else
          RtlCopyVolatileMemory(v19, v18, v17);
        v20 = (char *)v14 + 106;
        break;
      default:
        goto LABEL_38;
    }
    v33 = v7 + 106;
    if ( a6 )
      RtlCopyToUser(v20, v33, v13);
    else
      RtlCopyVolatileMemory(v20, v33, v13);
    v34 = (v10 + 7) & 0xFFFFFFF8;
    if ( a6 )
      RtlWriteULongToUser(v14, v34);
    else
      *v14 = v34;
    v8 = v61;
    a4 = v62;
    v12 = a5;
LABEL_38:
    if ( !*(_DWORD *)v7 )
      break;
    v36 = (v10 + 7) & 0xFFFFFFF8;
    v37 = v36;
    if ( v36 >= v12 - v9 )
      v37 = v12 - v9;
    v38 = v37 - v10;
    v39 = (void *)(a4 + v10 + v9);
    if ( a6 )
      RtlSetUserMemory(v39);
    else
      RtlSetVolatileMemory(v39, 0, v38);
    v9 += v36;
    v7 += *(unsigned int *)v7;
    v11 = v7;
    if ( (unsigned __int64)v7 >= v8 )
      goto LABEL_130;
    v12 = a5;
    if ( v9 >= a5 )
      goto LABEL_130;
    a3 = v8 - (_DWORD)v7;
    a1 = v60;
    a4 = v62;
  }
  v35 = (_DWORD *)(a4 + v9);
  if ( a6 )
    RtlWriteULongToUser(v35, 0);
  else
    *v35 = 0;
  v9 += v10;
LABEL_130:
  *a7 = v9;
  return 0;
}

```

## disassembly

```asm
0x1400376f0  mov     [rsp+arg_18], r9
0x1400376f5  mov     [rsp+arg_0], ecx
0x1400376f9  push    rbx
0x1400376fa  push    rsi
0x1400376fb  push    rdi
0x1400376fc  push    r12
0x1400376fe  push    r13
0x140037700  push    r14
0x140037702  push    r15
0x140037704  sub     rsp, 50h
0x140037708  mov     rdi, rdx
0x14003770b  mov     [rsp+88h+var_68], 0
0x140037710  mov     [rsp+88h+arg_10], 0
0x14003771b  mov     r15d, r8d
0x14003771e  add     r15, rdx
0x140037721  mov     [rsp+88h+arg_8], r15
0x140037729  xor     esi, esi
0x14003772b  xor     r12d, r12d
0x14003772e  mov     r13, rdx
0x140037731  movzx   ebx, [rsp+88h+arg_28]
0x140037739  mov     edx, [rsp+88h+arg_20]
0x140037740  mov     r14d, [r13+3Ch]
0x140037744  lea     eax, [r8-6Ah]
0x140037748  cmp     r14d, eax
0x14003774b  cmovnb  r14d, eax
0x14003774f  cmp     ecx, 3
0x140037752  jz      loc_1400377E2
0x140037758  cmp     ecx, 25h ; '%'
0x14003775b  jz      loc_1400379B5
0x140037761  cmp     ecx, 4Fh ; 'O'
0x140037764  jnz     loc_14003790B
0x14003776a  mov     r15d, esi
0x14003776d  add     r15, r9
0x140037770  lea     r12d, [r14+6Ah]
0x140037774  mov     [rsp+88h+var_50], r12d
0x140037779  mov     [rsp+88h+var_68], 1
0x14003777e  mov     r8d, 52h ; 'R'; Size
0x140037784  mov     rdx, rdi; Src
0x140037787  mov     rcx, r15; void *
0x14003778a  test    bl, bl
0x14003778c  jz      loc_140037C7B
0x140037792  call    RtlCopyToUser
0x140037797  lea     rcx, [r15+51h]; void *
0x14003779b  xor     edx, edx; Val
0x14003779d  mov     r8d, 19h; Size
0x1400377a3  test    bl, bl
0x1400377a5  jz      loc_140037C8F
0x1400377ab  call    RtlSetUserMemory
0x1400377b0  mov     eax, cs:FileTag
0x1400377b6  cmp     [rdi+44h], eax
0x1400377b9  jz      loc_140037C99
0x1400377bf  movsx   r8, byte ptr [rdi+50h]; Size
0x1400377c4  lea     rdx, [rdi+52h]; Src
0x1400377c8  lea     rcx, [r15+52h]; void *
0x1400377cc  test    bl, bl
0x1400377ce  jz      loc_140037C85
0x1400377d4  call    RtlCopyToUser
0x1400377d9  lea     rcx, [r15+6Ah]
0x1400377dd  jmp     loc_1400378C1
0x1400377e2  mov     r15d, esi
0x1400377e5  add     r15, r9
0x1400377e8  lea     r12d, [r14+5Eh]
0x1400377ec  mov     [rsp+88h+var_50], r12d
0x1400377f1  mov     [rsp+88h+var_68], 1
0x1400377f6  mov     r8d, 38h ; '8'; Size
0x1400377fc  mov     rdx, rdi; Src
0x1400377ff  mov     rcx, r15; void *
0x140037802  test    bl, bl
0x140037804  jz      loc_140037C15
0x14003780a  call    RtlCopyToUser
0x14003780f  lea     rcx, [r15+45h]; void *
0x140037813  xor     edx, edx; Val
0x140037815  mov     r8d, 19h; Size
0x14003781b  test    bl, bl
0x14003781d  jz      loc_140037C47
0x140037823  call    RtlSetUserMemory
0x140037828  mov     eax, cs:FileTag
0x14003782e  cmp     [r13+44h], eax
0x140037832  mov     eax, [r13+38h]
0x140037836  jz      loc_140037AAD
0x14003783c  lea     rcx, [r15+38h]
0x140037840  test    bl, bl
0x140037842  jz      loc_140037BEC
0x140037848  mov     edx, eax
0x14003784a  call    RtlWriteULongToUser
0x14003784f  lea     rcx, [r15+40h]
0x140037853  test    dword ptr [r13+38h], 400h
0x14003785b  jnz     loc_140037BAD
0x140037861  mov     eax, [r13+40h]
0x140037865  test    bl, bl
0x140037867  jz      loc_140037BF3
0x14003786d  mov     edx, eax
0x14003786f  call    RtlWriteULongToUser
0x140037874  movzx   eax, byte ptr [rdi+50h]
0x140037878  lea     rcx, [r15+44h]
0x14003787c  test    bl, bl
0x14003787e  jz      loc_140037BBE
0x140037884  movzx   edx, al
0x140037887  call    RtlWriteUCharToUser
0x14003788c  movsx   r8, byte ptr [rdi+50h]; Size
0x140037891  lea     rdx, [rdi+52h]; Src
0x140037895  lea     rcx, [r15+46h]; void *
0x140037899  test    bl, bl
0x14003789b  jz      loc_140037C1F
0x1400378a1  call    RtlCopyToUser
0x1400378a6  mov     eax, [r13+3Ch]
0x1400378aa  lea     rcx, [r15+3Ch]
0x1400378ae  test    bl, bl
0x1400378b0  jz      loc_140037BD2
0x1400378b6  mov     edx, eax
0x1400378b8  call    RtlWriteULongToUser
0x1400378bd  lea     rcx, [r15+5Eh]; void *
0x1400378c1  lea     rdx, [rdi+6Ah]; Src
0x1400378c5  mov     r8d, r14d; Size
0x1400378c8  test    bl, bl
0x1400378ca  jz      loc_140037BA3
0x1400378d0  call    RtlCopyToUser
0x1400378d5  lea     eax, [r12+7]
0x1400378da  and     eax, 0FFFFFFF8h
0x1400378dd  test    bl, bl
0x1400378df  jz      loc_140037B2B
0x1400378e5  mov     edx, eax
0x1400378e7  mov     rcx, r15
0x1400378ea  call    RtlWriteULongToUser
0x1400378ef  mov     [rsp+88h+var_68], 0
0x1400378f4  mov     r15, [rsp+88h+arg_8]
0x1400378fc  mov     r9, [rsp+88h+arg_18]
0x140037904  mov     edx, [rsp+88h+arg_20]
0x14003790b  mov     [rsp+88h+var_68], 1
0x140037910  cmp     dword ptr [rdi], 0
0x140037913  jnz     short loc_14003793A
0x140037915  mov     ecx, esi
0x140037917  add     rcx, r9
0x14003791a  test    bl, bl
0x14003791c  jz      loc_140037B18
0x140037922  xor     edx, edx
0x140037924  call    RtlWriteULongToUser
0x140037929  mov     [rsp+88h+var_68], 0
0x14003792e  add     esi, r12d
0x140037931  mov     [rsp+88h+var_4C], esi
0x140037935  jmp     loc_140037CE4
0x14003793a  mov     ecx, edx
0x14003793c  sub     ecx, esi
0x14003793e  lea     r14d, [r12+7]
0x140037943  and     r14d, 0FFFFFFF8h
0x140037947  mov     r8d, r14d
0x14003794a  cmp     r14d, ecx
0x14003794d  cmovnb  r8d, ecx
0x140037951  sub     r8d, r12d; Size
0x140037954  lea     ecx, [r12+rsi]
0x140037958  add     rcx, r9; void *
0x14003795b  xor     edx, edx; Val
0x14003795d  test    bl, bl
0x14003795f  jz      loc_140037C29
0x140037965  call    RtlSetUserMemory
0x14003796a  mov     [rsp+88h+var_68], 0
0x14003796f  add     esi, r14d
0x140037972  mov     [rsp+88h+var_4C], esi
0x140037976  mov     eax, [rdi]
0x140037978  add     rdi, rax
0x14003797b  mov     [rsp+88h+var_48], rdi
0x140037980  mov     r13, rdi
0x140037983  cmp     rdi, r15
0x140037986  jnb     loc_140037CE4
0x14003798c  mov     edx, [rsp+88h+arg_20]
0x140037993  cmp     esi, edx
0x140037995  jnb     loc_140037CE4
0x14003799b  mov     r8d, r15d
0x14003799e  sub     r8d, edi
0x1400379a1  mov     ecx, [rsp+88h+arg_0]
0x1400379a8  mov     r9, [rsp+88h+arg_18]
0x1400379b0  jmp     loc_140037740
0x1400379b5  mov     r15d, esi
0x1400379b8  add     r15, r9
0x1400379bb  lea     r12d, [r14+68h]
0x1400379bf  mov     [rsp+88h+var_50], r12d
0x1400379c4  mov     [rsp+88h+var_68], 1
0x1400379c9  mov     r8d, 38h ; '8'; Size
0x1400379cf  mov     rdx, rdi; Src
0x1400379d2  mov     rcx, r15; void *
0x1400379d5  test    bl, bl
0x1400379d7  jz      loc_140037C33
0x1400379dd  call    RtlCopyToUser
0x1400379e2  lea     rcx, [r15+45h]; void *
0x1400379e6  xor     edx, edx; Val
0x1400379e8  mov     r8d, 1Bh; Size
0x1400379ee  test    bl, bl
0x1400379f0  jz      loc_140037C51
0x1400379f6  call    RtlSetUserMemory
0x1400379fb  mov     eax, cs:FileTag
0x140037a01  cmp     [rdi+44h], eax
0x140037a04  mov     eax, [rdi+38h]
0x140037a07  jz      loc_140037B33
0x140037a0d  lea     rcx, [r15+38h]
0x140037a11  test    bl, bl
0x140037a13  jz      loc_140037C07
0x140037a19  mov     edx, eax
0x140037a1b  call    RtlWriteULongToUser
0x140037a20  lea     rcx, [r15+40h]
0x140037a24  test    dword ptr [rdi+38h], 400h
0x140037a2b  jnz     loc_140037BB6
0x140037a31  mov     eax, [rdi+40h]
0x140037a34  test    bl, bl
0x140037a36  jz      loc_140037C0E
0x140037a3c  mov     edx, eax
0x140037a3e  call    RtlWriteULongToUser
0x140037a43  mov     rax, [rdi+48h]
0x140037a47  lea     rcx, [r15+60h]
0x140037a4b  test    bl, bl
0x140037a4d  jz      loc_140037B23
0x140037a53  mov     rdx, rax
0x140037a56  call    RtlWriteULong64ToUser
0x140037a5b  movzx   eax, byte ptr [rdi+50h]
0x140037a5f  lea     rcx, [r15+44h]
0x140037a63  test    bl, bl
0x140037a65  jz      loc_140037BD9
0x140037a6b  movzx   edx, al
0x140037a6e  call    RtlWriteUCharToUser
0x140037a73  movsx   r8, byte ptr [rdi+50h]; Size
0x140037a78  lea     rdx, [rdi+52h]; Src
0x140037a7c  lea     rcx, [r15+46h]; void *
0x140037a80  test    bl, bl
0x140037a82  jz      loc_140037C3D
0x140037a88  call    RtlCopyToUser
0x140037a8d  mov     eax, [r13+3Ch]
0x140037a91  lea     rcx, [r15+3Ch]
0x140037a95  test    bl, bl
0x140037a97  jz      loc_140037BE0
0x140037a9d  mov     edx, eax
0x140037a9f  call    RtlWriteULongToUser
0x140037aa4  lea     rcx, [r15+68h]
0x140037aa8  jmp     loc_1400378C1
0x140037aad  mov     [rsp+88h+var_58], eax
0x140037ab1  cmp     cs:byte_140018454, 0
0x140037ab8  jz      short loc_140037AC2
0x140037aba  btr     eax, 0Ah
0x140037abe  mov     [rsp+88h+var_58], eax
0x140037ac2  cmp     cs:byte_140018455, 0
0x140037ac9  jnz     loc_140037BC5
0x140037acf  test    eax, eax
0x140037ad1  mov     ecx, 80h
0x140037ad6  cmovz   eax, ecx
0x140037ad9  mov     [rsp+88h+var_58], eax
0x140037add  lea     rcx, [r15+38h]
0x140037ae1  test    bl, bl
0x140037ae3  jz      loc_140037C5B
0x140037ae9  mov     edx, eax
0x140037aeb  call    RtlWriteULongToUser
0x140037af0  cmp     cs:byte_140018454, 0
0x140037af7  jz      loc_140037B9A
0x140037afd  mov     ecx, [rdi+40h]
0x140037b00  test    bl, bl
0x140037b02  jz      loc_140037C62
0x140037b08  mov     edx, ecx
0x140037b0a  lea     rcx, [r15+40h]
0x140037b0e  call    RtlWriteULongToUser
0x140037b13  jmp     loc_140037874
0x140037b18  mov     dword ptr [rcx], 0
0x140037b1e  jmp     loc_140037929
0x140037b23  mov     [rcx], rax
0x140037b26  jmp     loc_140037A5B
0x140037b2b  mov     [r15], eax
0x140037b2e  jmp     loc_1400378EF
0x140037b33  mov     [rsp+88h+var_60], eax
0x140037b37  cmp     cs:byte_140018454, 0
0x140037b3e  jz      short loc_140037B48
0x140037b40  btr     eax, 0Ah
0x140037b44  mov     [rsp+88h+var_60], eax
0x140037b48  cmp     cs:byte_140018455, 0
0x140037b4f  jnz     loc_140037BFA
0x140037b55  test    eax, eax
0x140037b57  mov     ecx, 80h
0x140037b5c  cmovz   eax, ecx
0x140037b5f  mov     [rsp+88h+var_60], eax
0x140037b63  lea     rcx, [r15+38h]
0x140037b67  test    bl, bl
0x140037b69  jz      loc_140037C6B
0x140037b6f  mov     edx, eax
0x140037b71  call    RtlWriteULongToUser
0x140037b76  cmp     cs:byte_140018454, 0
0x140037b7d  jnz     short loc_140037BE7
0x140037b7f  mov     ecx, [rdi+44h]
0x140037b82  test    bl, bl
0x140037b84  jz      loc_140037C72
0x140037b8a  mov     edx, ecx
0x140037b8c  lea     rcx, [r15+40h]
0x140037b90  call    RtlWriteULongToUser
0x140037b95  jmp     loc_140037A43
0x140037b9a  mov     ecx, [r13+44h]
0x140037b9e  jmp     loc_140037B00
0x140037ba3  call    RtlCopyVolatileMemory
0x140037ba8  jmp     loc_1400378D5
0x140037bad  mov     eax, [r13+44h]
0x140037bb1  jmp     loc_140037865
0x140037bb6  mov     eax, [rdi+44h]
0x140037bb9  jmp     loc_140037A34
0x140037bbe  mov     [rcx], al
0x140037bc0  jmp     loc_14003788C
0x140037bc5  btr     eax, 9
0x140037bc9  mov     [rsp+88h+var_58], eax
  ... truncated ...
```
