# WofMungeDirectoryEnumerateWithShortnameFileId64

- ea: `0x1400376a0`
- end: `0x140037cbd`
- name: `WofMungeDirectoryEnumerateWithShortnameFileId64`
- size: `1565`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140036e20`

## callees

- `0x140011590`
- `0x1400115b0`
- `0x140022fcc`
- `0x1400230a8`
- `0x140023108`
- `0x140023150`
- `0x140023198`
- `0x140035e80`
- `0x1400376a0`

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
0x1400376a0  mov     [rsp+arg_18], r9
0x1400376a5  mov     [rsp+arg_0], ecx
0x1400376a9  push    rbx
0x1400376aa  push    rsi
0x1400376ab  push    rdi
0x1400376ac  push    r12
0x1400376ae  push    r13
0x1400376b0  push    r14
0x1400376b2  push    r15
0x1400376b4  sub     rsp, 50h
0x1400376b8  mov     rdi, rdx
0x1400376bb  mov     [rsp+88h+var_68], 0
0x1400376c0  mov     [rsp+88h+arg_10], 0
0x1400376cb  mov     r15d, r8d
0x1400376ce  add     r15, rdx
0x1400376d1  mov     [rsp+88h+arg_8], r15
0x1400376d9  xor     esi, esi
0x1400376db  xor     r12d, r12d
0x1400376de  mov     r13, rdx
0x1400376e1  movzx   ebx, [rsp+88h+arg_28]
0x1400376e9  mov     edx, [rsp+88h+arg_20]
0x1400376f0  mov     r14d, [r13+3Ch]
0x1400376f4  lea     eax, [r8-6Ah]
0x1400376f8  cmp     r14d, eax
0x1400376fb  cmovnb  r14d, eax
0x1400376ff  cmp     ecx, 3
0x140037702  jz      loc_140037792
0x140037708  cmp     ecx, 25h ; '%'
0x14003770b  jz      loc_140037965
0x140037711  cmp     ecx, 4Fh ; 'O'
0x140037714  jnz     loc_1400378BB
0x14003771a  mov     r15d, esi
0x14003771d  add     r15, r9
0x140037720  lea     r12d, [r14+6Ah]
0x140037724  mov     [rsp+88h+var_50], r12d
0x140037729  mov     [rsp+88h+var_68], 1
0x14003772e  mov     r8d, 52h ; 'R'; Size
0x140037734  mov     rdx, rdi; Src
0x140037737  mov     rcx, r15; void *
0x14003773a  test    bl, bl
0x14003773c  jz      loc_140037C2B
0x140037742  call    RtlCopyToUser
0x140037747  lea     rcx, [r15+51h]; void *
0x14003774b  xor     edx, edx; Val
0x14003774d  mov     r8d, 19h; Size
0x140037753  test    bl, bl
0x140037755  jz      loc_140037C3F
0x14003775b  call    RtlSetUserMemory
0x140037760  mov     eax, cs:FileTag
0x140037766  cmp     [rdi+44h], eax
0x140037769  jz      loc_140037C49
0x14003776f  movsx   r8, byte ptr [rdi+50h]; Size
0x140037774  lea     rdx, [rdi+52h]; Src
0x140037778  lea     rcx, [r15+52h]; void *
0x14003777c  test    bl, bl
0x14003777e  jz      loc_140037C35
0x140037784  call    RtlCopyToUser
0x140037789  lea     rcx, [r15+6Ah]
0x14003778d  jmp     loc_140037871
0x140037792  mov     r15d, esi
0x140037795  add     r15, r9
0x140037798  lea     r12d, [r14+5Eh]
0x14003779c  mov     [rsp+88h+var_50], r12d
0x1400377a1  mov     [rsp+88h+var_68], 1
0x1400377a6  mov     r8d, 38h ; '8'; Size
0x1400377ac  mov     rdx, rdi; Src
0x1400377af  mov     rcx, r15; void *
0x1400377b2  test    bl, bl
0x1400377b4  jz      loc_140037BC5
0x1400377ba  call    RtlCopyToUser
0x1400377bf  lea     rcx, [r15+45h]; void *
0x1400377c3  xor     edx, edx; Val
0x1400377c5  mov     r8d, 19h; Size
0x1400377cb  test    bl, bl
0x1400377cd  jz      loc_140037BF7
0x1400377d3  call    RtlSetUserMemory
0x1400377d8  mov     eax, cs:FileTag
0x1400377de  cmp     [r13+44h], eax
0x1400377e2  mov     eax, [r13+38h]
0x1400377e6  jz      loc_140037A5D
0x1400377ec  lea     rcx, [r15+38h]
0x1400377f0  test    bl, bl
0x1400377f2  jz      loc_140037B9C
0x1400377f8  mov     edx, eax
0x1400377fa  call    RtlWriteULongToUser
0x1400377ff  lea     rcx, [r15+40h]
0x140037803  test    dword ptr [r13+38h], 400h
0x14003780b  jnz     loc_140037B5D
0x140037811  mov     eax, [r13+40h]
0x140037815  test    bl, bl
0x140037817  jz      loc_140037BA3
0x14003781d  mov     edx, eax
0x14003781f  call    RtlWriteULongToUser
0x140037824  movzx   eax, byte ptr [rdi+50h]
0x140037828  lea     rcx, [r15+44h]
0x14003782c  test    bl, bl
0x14003782e  jz      loc_140037B6E
0x140037834  movzx   edx, al
0x140037837  call    RtlWriteUCharToUser
0x14003783c  movsx   r8, byte ptr [rdi+50h]; Size
0x140037841  lea     rdx, [rdi+52h]; Src
0x140037845  lea     rcx, [r15+46h]; void *
0x140037849  test    bl, bl
0x14003784b  jz      loc_140037BCF
0x140037851  call    RtlCopyToUser
0x140037856  mov     eax, [r13+3Ch]
0x14003785a  lea     rcx, [r15+3Ch]
0x14003785e  test    bl, bl
0x140037860  jz      loc_140037B82
0x140037866  mov     edx, eax
0x140037868  call    RtlWriteULongToUser
0x14003786d  lea     rcx, [r15+5Eh]; void *
0x140037871  lea     rdx, [rdi+6Ah]; Src
0x140037875  mov     r8d, r14d; Size
0x140037878  test    bl, bl
0x14003787a  jz      loc_140037B53
0x140037880  call    RtlCopyToUser
0x140037885  lea     eax, [r12+7]
0x14003788a  and     eax, 0FFFFFFF8h
0x14003788d  test    bl, bl
0x14003788f  jz      loc_140037ADB
0x140037895  mov     edx, eax
0x140037897  mov     rcx, r15
0x14003789a  call    RtlWriteULongToUser
0x14003789f  mov     [rsp+88h+var_68], 0
0x1400378a4  mov     r15, [rsp+88h+arg_8]
0x1400378ac  mov     r9, [rsp+88h+arg_18]
0x1400378b4  mov     edx, [rsp+88h+arg_20]
0x1400378bb  mov     [rsp+88h+var_68], 1
0x1400378c0  cmp     dword ptr [rdi], 0
0x1400378c3  jnz     short loc_1400378EA
0x1400378c5  mov     ecx, esi
0x1400378c7  add     rcx, r9
0x1400378ca  test    bl, bl
0x1400378cc  jz      loc_140037AC8
0x1400378d2  xor     edx, edx
0x1400378d4  call    RtlWriteULongToUser
0x1400378d9  mov     [rsp+88h+var_68], 0
0x1400378de  add     esi, r12d
0x1400378e1  mov     [rsp+88h+var_4C], esi
0x1400378e5  jmp     loc_140037C94
0x1400378ea  mov     ecx, edx
0x1400378ec  sub     ecx, esi
0x1400378ee  lea     r14d, [r12+7]
0x1400378f3  and     r14d, 0FFFFFFF8h
0x1400378f7  mov     r8d, r14d
0x1400378fa  cmp     r14d, ecx
0x1400378fd  cmovnb  r8d, ecx
0x140037901  sub     r8d, r12d; Size
0x140037904  lea     ecx, [r12+rsi]
0x140037908  add     rcx, r9; void *
0x14003790b  xor     edx, edx; Val
0x14003790d  test    bl, bl
0x14003790f  jz      loc_140037BD9
0x140037915  call    RtlSetUserMemory
0x14003791a  mov     [rsp+88h+var_68], 0
0x14003791f  add     esi, r14d
0x140037922  mov     [rsp+88h+var_4C], esi
0x140037926  mov     eax, [rdi]
0x140037928  add     rdi, rax
0x14003792b  mov     [rsp+88h+var_48], rdi
0x140037930  mov     r13, rdi
0x140037933  cmp     rdi, r15
0x140037936  jnb     loc_140037C94
0x14003793c  mov     edx, [rsp+88h+arg_20]
0x140037943  cmp     esi, edx
0x140037945  jnb     loc_140037C94
0x14003794b  mov     r8d, r15d
0x14003794e  sub     r8d, edi
0x140037951  mov     ecx, [rsp+88h+arg_0]
0x140037958  mov     r9, [rsp+88h+arg_18]
0x140037960  jmp     loc_1400376F0
0x140037965  mov     r15d, esi
0x140037968  add     r15, r9
0x14003796b  lea     r12d, [r14+68h]
0x14003796f  mov     [rsp+88h+var_50], r12d
0x140037974  mov     [rsp+88h+var_68], 1
0x140037979  mov     r8d, 38h ; '8'; Size
0x14003797f  mov     rdx, rdi; Src
0x140037982  mov     rcx, r15; void *
0x140037985  test    bl, bl
0x140037987  jz      loc_140037BE3
0x14003798d  call    RtlCopyToUser
0x140037992  lea     rcx, [r15+45h]; void *
0x140037996  xor     edx, edx; Val
0x140037998  mov     r8d, 1Bh; Size
0x14003799e  test    bl, bl
0x1400379a0  jz      loc_140037C01
0x1400379a6  call    RtlSetUserMemory
0x1400379ab  mov     eax, cs:FileTag
0x1400379b1  cmp     [rdi+44h], eax
0x1400379b4  mov     eax, [rdi+38h]
0x1400379b7  jz      loc_140037AE3
0x1400379bd  lea     rcx, [r15+38h]
0x1400379c1  test    bl, bl
0x1400379c3  jz      loc_140037BB7
0x1400379c9  mov     edx, eax
0x1400379cb  call    RtlWriteULongToUser
0x1400379d0  lea     rcx, [r15+40h]
0x1400379d4  test    dword ptr [rdi+38h], 400h
0x1400379db  jnz     loc_140037B66
0x1400379e1  mov     eax, [rdi+40h]
0x1400379e4  test    bl, bl
0x1400379e6  jz      loc_140037BBE
0x1400379ec  mov     edx, eax
0x1400379ee  call    RtlWriteULongToUser
0x1400379f3  mov     rax, [rdi+48h]
0x1400379f7  lea     rcx, [r15+60h]
0x1400379fb  test    bl, bl
0x1400379fd  jz      loc_140037AD3
0x140037a03  mov     rdx, rax
0x140037a06  call    RtlWriteULong64ToUser
0x140037a0b  movzx   eax, byte ptr [rdi+50h]
0x140037a0f  lea     rcx, [r15+44h]
0x140037a13  test    bl, bl
0x140037a15  jz      loc_140037B89
0x140037a1b  movzx   edx, al
0x140037a1e  call    RtlWriteUCharToUser
0x140037a23  movsx   r8, byte ptr [rdi+50h]; Size
0x140037a28  lea     rdx, [rdi+52h]; Src
0x140037a2c  lea     rcx, [r15+46h]; void *
0x140037a30  test    bl, bl
0x140037a32  jz      loc_140037BED
0x140037a38  call    RtlCopyToUser
0x140037a3d  mov     eax, [r13+3Ch]
0x140037a41  lea     rcx, [r15+3Ch]
0x140037a45  test    bl, bl
0x140037a47  jz      loc_140037B90
0x140037a4d  mov     edx, eax
0x140037a4f  call    RtlWriteULongToUser
0x140037a54  lea     rcx, [r15+68h]
0x140037a58  jmp     loc_140037871
0x140037a5d  mov     [rsp+88h+var_58], eax
0x140037a61  cmp     cs:byte_140018454, 0
0x140037a68  jz      short loc_140037A72
0x140037a6a  btr     eax, 0Ah
0x140037a6e  mov     [rsp+88h+var_58], eax
0x140037a72  cmp     cs:byte_140018455, 0
0x140037a79  jnz     loc_140037B75
0x140037a7f  test    eax, eax
0x140037a81  mov     ecx, 80h
0x140037a86  cmovz   eax, ecx
0x140037a89  mov     [rsp+88h+var_58], eax
0x140037a8d  lea     rcx, [r15+38h]
0x140037a91  test    bl, bl
0x140037a93  jz      loc_140037C0B
0x140037a99  mov     edx, eax
0x140037a9b  call    RtlWriteULongToUser
0x140037aa0  cmp     cs:byte_140018454, 0
0x140037aa7  jz      loc_140037B4A
0x140037aad  mov     ecx, [rdi+40h]
0x140037ab0  test    bl, bl
0x140037ab2  jz      loc_140037C12
0x140037ab8  mov     edx, ecx
0x140037aba  lea     rcx, [r15+40h]
0x140037abe  call    RtlWriteULongToUser
0x140037ac3  jmp     loc_140037824
0x140037ac8  mov     dword ptr [rcx], 0
0x140037ace  jmp     loc_1400378D9
0x140037ad3  mov     [rcx], rax
0x140037ad6  jmp     loc_140037A0B
0x140037adb  mov     [r15], eax
0x140037ade  jmp     loc_14003789F
0x140037ae3  mov     [rsp+88h+var_60], eax
0x140037ae7  cmp     cs:byte_140018454, 0
0x140037aee  jz      short loc_140037AF8
0x140037af0  btr     eax, 0Ah
0x140037af4  mov     [rsp+88h+var_60], eax
0x140037af8  cmp     cs:byte_140018455, 0
0x140037aff  jnz     loc_140037BAA
0x140037b05  test    eax, eax
0x140037b07  mov     ecx, 80h
0x140037b0c  cmovz   eax, ecx
0x140037b0f  mov     [rsp+88h+var_60], eax
0x140037b13  lea     rcx, [r15+38h]
0x140037b17  test    bl, bl
0x140037b19  jz      loc_140037C1B
0x140037b1f  mov     edx, eax
0x140037b21  call    RtlWriteULongToUser
0x140037b26  cmp     cs:byte_140018454, 0
0x140037b2d  jnz     short loc_140037B97
0x140037b2f  mov     ecx, [rdi+44h]
0x140037b32  test    bl, bl
0x140037b34  jz      loc_140037C22
0x140037b3a  mov     edx, ecx
0x140037b3c  lea     rcx, [r15+40h]
0x140037b40  call    RtlWriteULongToUser
0x140037b45  jmp     loc_1400379F3
0x140037b4a  mov     ecx, [r13+44h]
0x140037b4e  jmp     loc_140037AB0
0x140037b53  call    RtlCopyVolatileMemory
0x140037b58  jmp     loc_140037885
0x140037b5d  mov     eax, [r13+44h]
0x140037b61  jmp     loc_140037815
0x140037b66  mov     eax, [rdi+44h]
0x140037b69  jmp     loc_1400379E4
0x140037b6e  mov     [rcx], al
0x140037b70  jmp     loc_14003783C
0x140037b75  btr     eax, 9
0x140037b79  mov     [rsp+88h+var_58], eax
  ... truncated ...
```
