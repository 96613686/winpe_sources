# putend

- ea: `0x1800a03c8`
- end: `0x1800a08c7`
- name: `putend`
- size: `1279`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18009f200`
- `0x1800a3378`

## callees

- `0x18009d5e4`
- `0x1800a03c8`
- `0x1800a3608`
- `0x1800c97c2`

## import_xrefs

- `msvcrt!free` at `0x1800a0532`
- `msvcrt!free` at `0x1800a0640`
- `msvcrt!free` at `0x1800a07ed`
- `msvcrt!free` at `0x1800a0532`
- `msvcrt!free` at `0x1800a0640`
- `msvcrt!free` at `0x1800a07ed`
- `msvcrt!malloc` at `0x1800a04c1`
- `msvcrt!malloc` at `0x1800a05a1`
- `msvcrt!malloc` at `0x1800a068c`
- `msvcrt!malloc` at `0x1800a0800`
- `msvcrt!malloc` at `0x1800a04c1`
- `msvcrt!malloc` at `0x1800a05a1`
- `msvcrt!malloc` at `0x1800a068c`
- `msvcrt!malloc` at `0x1800a0800`
- `KERNEL32!WriteFile` at `0x1800a0624`
- `KERNEL32!WriteFile` at `0x1800a07d2`
- `KERNEL32!WriteFile` at `0x1800a0624`
- `KERNEL32!WriteFile` at `0x1800a07d2`

## pseudocode

```c
__int64 __fastcall putend(__int64 a1, __int64 a2, __int64 a3, size_t a4, void *Src, HANDLE *a6, __int64 a7)
{
  int v8; // ebp
  int v13; // r15d
  char *v15; // rax
  _DWORD *v16; // rbx
  __int64 v17; // rcx
  HANDLE v18; // rcx
  char *v19; // rax
  __int64 v20; // rcx
  signed int v21; // ebp
  _DWORD *v22; // rax
  BOOL v23; // eax
  char *v24; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-68h] BYREF
  int v26; // [rsp+34h] [rbp-64h]
  __int64 v27; // [rsp+38h] [rbp-60h]
  __int64 v28; // [rsp+40h] [rbp-58h]
  int v29; // [rsp+D0h] [rbp+38h]
  int v30; // [rsp+D0h] [rbp+38h]

  v8 = 0;
  NumberOfBytesWritten = 0;
  v13 = 0;
  if ( !*(_DWORD *)(a7 + 624) || a1 <= 65534 && a2 <= 4294967294LL && a3 <= 4294967294LL )
    goto LABEL_24;
  v13 = 1;
  if ( *(_QWORD *)(a7 + 216) != -1 )
  {
    v28 = DZSetFilePointer(*a6, 0, 1);
    if ( *(__int16 *)(a7 + 3740) >= 0 )
    {
      v26 = 0;
      v27 = a1;
      v30 = 0;
    }
    else
    {
      v8 = *(_DWORD *)(a7 + 3744);
      v30 = *(_DWORD *)(a7 + 3748);
      v26 = v8 + 1;
      v27 = *(unsigned int *)(a7 + 3760);
    }
    v19 = (char *)malloc(0x4Du);
    v16 = v19;
    if ( !v19 )
      return 4;
    v20 = v27;
    *(_DWORD *)v19 = 101075792;
    *(_QWORD *)(v19 + 4) = 44;
    *((_DWORD *)v19 + 3) = 2949165;
    *((_DWORD *)v19 + 4) = v8;
    *((_DWORD *)v19 + 5) = v30;
    *((_QWORD *)v19 + 3) = v20;
    *((_QWORD *)v19 + 4) = a1;
    *((_QWORD *)v19 + 5) = a2;
    *((_QWORD *)v19 + 6) = a3;
    *((_DWORD *)v19 + 15) = v30;
    *((_QWORD *)v19 + 8) = v28;
    *((_DWORD *)v19 + 18) = v26;
    v18 = *a6;
LABEL_21:
    v16[14] = 117853008;
    if ( !WriteFile(v18, v16, 0x4Cu, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 76 )
      goto LABEL_15;
    free(v16);
LABEL_24:
    v21 = a4 + 22;
    if ( *(_QWORD *)(a7 + 216) == -1 )
    {
      if ( (unsigned int)PromptForNewDisk(0, a6, a4 + 22, a7) )
        return *(_DWORD *)(a7 + 208) != 0 ? 9 : 19;
      v22 = malloc(v21 + 1LL);
      v16 = v22;
      if ( v22 )
      {
        *v22 = 101010256;
        if ( *(__int16 *)(a7 + 3740) >= 0 )
        {
          v22[1] = 0;
          if ( v13 )
          {
            if ( a1 > 65534 )
            {
LABEL_37:
              *((_WORD *)v22 + 4) = -1;
              goto LABEL_43;
            }
            *((_WORD *)v22 + 4) = a1;
LABEL_43:
            if ( a1 <= 65534 )
              *((_WORD *)v22 + 5) = a1;
            else
              *((_WORD *)v22 + 5) = -1;
            if ( a2 <= 4294967294LL )
              v22[3] = a2;
            else
              v22[3] = -1;
            if ( a3 > 4294967294LL )
            {
              v22[4] = -1;
LABEL_54:
              *((_WORD *)v22 + 10) = a4;
              if ( a4 )
                memcpy_0((char *)v22 + 22, Src, a4);
              v23 = WriteFile(*a6, v16, v21, &NumberOfBytesWritten, 0);
              goto LABEL_57;
            }
LABEL_53:
            v22[4] = a3;
            goto LABEL_54;
          }
          *((_WORD *)v22 + 4) = a1;
        }
        else
        {
          if ( v13 )
          {
            if ( *(_DWORD *)(a7 + 3744) <= 0xFFFEu )
              *((_WORD *)v22 + 2) = *(_WORD *)(a7 + 3744);
            else
              *((_WORD *)v22 + 2) = -1;
            if ( *(_DWORD *)(a7 + 3748) <= 0xFFFEu )
              *((_WORD *)v22 + 3) = *(_WORD *)(a7 + 3748);
            else
              *((_WORD *)v22 + 3) = -1;
            if ( *(_DWORD *)(a7 + 3760) > 0xFFFEu )
              goto LABEL_37;
            *((_WORD *)v22 + 4) = *(_WORD *)(a7 + 3760);
            goto LABEL_43;
          }
          *((_WORD *)v22 + 2) = *(_WORD *)(a7 + 3744);
          *((_WORD *)v22 + 3) = *(_WORD *)(a7 + 3748);
          *((_WORD *)v22 + 4) = *(_WORD *)(a7 + 3760);
        }
        *((_WORD *)v22 + 5) = a1;
        v22[3] = a2;
        goto LABEL_53;
      }
      return 4;
    }
    v24 = (char *)malloc(v21 + 1LL);
    v16 = v24;
    if ( !v24 )
      return 4;
    *(_DWORD *)v24 = 101010256;
    if ( *(__int16 *)(a7 + 3740) >= 0 )
    {
      *((_DWORD *)v24 + 1) = 0;
      if ( v13 )
        goto LABEL_66;
      *((_WORD *)v24 + 4) = a1;
    }
    else
    {
      if ( v13 )
      {
        *((_DWORD *)v24 + 1) = -1;
LABEL_66:
        *((_WORD *)v24 + 4) = -1;
        *(_QWORD *)(v24 + 10) = -1;
        *((_WORD *)v24 + 9) = -1;
LABEL_69:
        *((_WORD *)v24 + 10) = a4;
        if ( a4 )
          memcpy_0(v24 + 22, Src, a4);
        v23 = WriteFile(*(HANDLE *)(a7 + 216), v16, v21, &NumberOfBytesWritten, 0);
LABEL_57:
        if ( v23 && NumberOfBytesWritten == v21 )
        {
          free(v16);
          return 0;
        }
LABEL_15:
        free(v16);
        return 10;
      }
      *((_WORD *)v24 + 2) = *(_WORD *)(a7 + 3744);
      *((_WORD *)v24 + 3) = *(_WORD *)(a7 + 3748);
      *((_WORD *)v24 + 4) = *(_WORD *)(a7 + 3760);
    }
    *((_WORD *)v24 + 5) = a1;
    *((_DWORD *)v24 + 3) = a2;
    *((_DWORD *)v24 + 4) = a3;
    goto LABEL_69;
  }
  if ( !(unsigned int)PromptForNewDisk(0, a6, 76, a7) )
  {
    v28 = DZSetFilePointer(*a6, 0, 1);
    if ( *(__int16 *)(a7 + 3740) >= 0 )
    {
      v26 = 0;
      v27 = a1;
      v29 = 0;
    }
    else
    {
      v8 = *(_DWORD *)(a7 + 3744);
      v29 = *(_DWORD *)(a7 + 3748);
      v26 = v8 + 1;
      v27 = *(unsigned int *)(a7 + 3760);
    }
    v15 = (char *)malloc(0x4Du);
    v16 = v15;
    if ( !v15 )
      return 4;
    v17 = v27;
    *(_DWORD *)v15 = 101075792;
    *(_QWORD *)(v15 + 4) = 44;
    *((_DWORD *)v15 + 3) = 2949165;
    *((_DWORD *)v15 + 4) = v8;
    *((_DWORD *)v15 + 5) = v29;
    *((_QWORD *)v15 + 3) = v17;
    *((_QWORD *)v15 + 4) = a1;
    *((_QWORD *)v15 + 5) = a2;
    *((_QWORD *)v15 + 6) = a3;
    v18 = *a6;
    *((_DWORD *)v15 + 15) = v29;
    *((_QWORD *)v15 + 8) = v28;
    *((_DWORD *)v15 + 18) = v26;
    goto LABEL_21;
  }
  if ( *(_DWORD *)(a7 + 208) )
    return 9;
  else
    return 19;
}

```

## disassembly

```asm
0x1800a03c8  push    rbx
0x1800a03ca  push    rbp
0x1800a03cb  push    rsi
0x1800a03cc  push    rdi
0x1800a03cd  push    r12
0x1800a03cf  push    r13
0x1800a03d1  push    r14
0x1800a03d3  push    r15
0x1800a03d5  sub     rsp, 58h
0x1800a03d9  mov     rdi, [rsp+98h+arg_30]
0x1800a03e1  xor     ebp, ebp
0x1800a03e3  mov     r14, r9
0x1800a03e6  mov     [rsp+98h+NumberOfBytesWritten], ebp
0x1800a03ea  mov     r12, r8
0x1800a03ed  mov     r13, rdx
0x1800a03f0  mov     rsi, rcx
0x1800a03f3  mov     r15d, ebp
0x1800a03f6  mov     eax, 0FFFFFFFEh
0x1800a03fb  cmp     [rdi+270h], ebp
0x1800a0401  jz      loc_1800A0646
0x1800a0407  cmp     rcx, 0FFFEh
0x1800a040e  jg      short loc_1800A041E
0x1800a0410  cmp     rdx, rax
0x1800a0413  jg      short loc_1800A041E
0x1800a0415  cmp     r8, rax
0x1800a0418  jle     loc_1800A0646
0x1800a041e  cmp     qword ptr [rdi+0D8h], 0FFFFFFFFFFFFFFFFh
0x1800a0426  mov     r15d, 1
0x1800a042c  jnz     loc_1800A0542
0x1800a0432  mov     rbx, [rsp+98h+arg_28]
0x1800a043a  lea     r8d, [r15+4Bh]
0x1800a043e  mov     rdx, rbx
0x1800a0441  mov     r9, rdi
0x1800a0444  xor     ecx, ecx
0x1800a0446  call    PromptForNewDisk
0x1800a044b  test    eax, eax
0x1800a044d  jz      short loc_1800A046A
0x1800a044f  cmp     [rdi+0D0h], ebp
0x1800a0455  jnz     short loc_1800A0460
0x1800a0457  lea     eax, [r15+12h]
0x1800a045b  jmp     loc_1800A08B6
0x1800a0460  mov     eax, 9
0x1800a0465  jmp     loc_1800A08B6
0x1800a046a  mov     rcx, [rbx]
0x1800a046d  xor     edx, edx
0x1800a046f  mov     r8d, r15d
0x1800a0472  call    DZSetFilePointer
0x1800a0477  mov     [rsp+98h+var_58], rax
0x1800a047c  cmp     [rdi+0E9Ch], bp
0x1800a0483  jge     short loc_1800A04AC
0x1800a0485  mov     ebp, [rdi+0EA0h]
0x1800a048b  mov     ecx, [rdi+0EA4h]
0x1800a0491  mov     dword ptr [rsp+98h+arg_30], ecx
0x1800a0498  lea     eax, [rbp+1]
0x1800a049b  mov     [rsp+98h+var_64], eax
0x1800a049f  mov     eax, [rdi+0EB0h]
0x1800a04a5  mov     [rsp+98h+var_60], rax
0x1800a04aa  jmp     short loc_1800A04BC
0x1800a04ac  mov     [rsp+98h+var_64], ebp
0x1800a04b0  mov     [rsp+98h+var_60], rsi
0x1800a04b5  mov     dword ptr [rsp+98h+arg_30], ebp
0x1800a04bc  mov     ecx, 4Dh ; 'M'; Size
0x1800a04c1  call    cs:__imp_malloc
0x1800a04c7  xor     edx, edx
0x1800a04c9  mov     rbx, rax
0x1800a04cc  test    rax, rax
0x1800a04cf  jz      loc_1800A08B1
0x1800a04d5  mov     rcx, [rsp+98h+var_60]
0x1800a04da  mov     dword ptr [rax], 6064B50h
0x1800a04e0  mov     qword ptr [rax+4], 2Ch ; ','
0x1800a04e8  mov     dword ptr [rax+0Ch], 2D002Dh
0x1800a04ef  mov     [rax+10h], ebp
0x1800a04f2  mov     eax, dword ptr [rsp+98h+arg_30]
0x1800a04f9  mov     [rbx+14h], eax
0x1800a04fc  mov     [rbx+18h], rcx
0x1800a0500  mov     rcx, [rsp+98h+arg_28]
0x1800a0508  mov     [rbx+20h], rsi
0x1800a050c  mov     [rbx+28h], r13
0x1800a0510  mov     [rbx+30h], r12
0x1800a0514  mov     rcx, [rcx]
0x1800a0517  mov     [rbx+3Ch], eax
0x1800a051a  mov     rax, [rsp+98h+var_58]
0x1800a051f  mov     [rbx+40h], rax
0x1800a0523  mov     eax, [rsp+98h+var_64]
0x1800a0527  mov     [rbx+48h], eax
0x1800a052a  jmp     loc_1800A060A
0x1800a052f  mov     rcx, rbx; Block
0x1800a0532  call    cs:__imp_free
0x1800a0538  mov     eax, 0Ah
0x1800a053d  jmp     loc_1800A08B6
0x1800a0542  mov     rcx, [rsp+98h+arg_28]
0x1800a054a  xor     edx, edx
0x1800a054c  mov     r8d, r15d
0x1800a054f  mov     rcx, [rcx]
0x1800a0552  call    DZSetFilePointer
0x1800a0557  mov     [rsp+98h+var_58], rax
0x1800a055c  cmp     [rdi+0E9Ch], bp
0x1800a0563  jge     short loc_1800A058C
0x1800a0565  mov     ebp, [rdi+0EA0h]
0x1800a056b  mov     ecx, [rdi+0EA4h]
0x1800a0571  mov     dword ptr [rsp+98h+arg_30], ecx
0x1800a0578  lea     eax, [rbp+1]
0x1800a057b  mov     [rsp+98h+var_64], eax
0x1800a057f  mov     eax, [rdi+0EB0h]
0x1800a0585  mov     [rsp+98h+var_60], rax
0x1800a058a  jmp     short loc_1800A059C
0x1800a058c  mov     [rsp+98h+var_64], ebp
0x1800a0590  mov     [rsp+98h+var_60], rsi
0x1800a0595  mov     dword ptr [rsp+98h+arg_30], ebp
0x1800a059c  mov     ecx, 4Dh ; 'M'; Size
0x1800a05a1  call    cs:__imp_malloc
0x1800a05a7  xor     edx, edx
0x1800a05a9  mov     rbx, rax
0x1800a05ac  test    rax, rax
0x1800a05af  jz      loc_1800A08B1
0x1800a05b5  mov     rcx, [rsp+98h+var_60]
0x1800a05ba  mov     dword ptr [rax], 6064B50h
0x1800a05c0  mov     qword ptr [rax+4], 2Ch ; ','
0x1800a05c8  mov     dword ptr [rax+0Ch], 2D002Dh
0x1800a05cf  mov     [rax+10h], ebp
0x1800a05d2  mov     eax, dword ptr [rsp+98h+arg_30]
0x1800a05d9  mov     [rbx+14h], eax
0x1800a05dc  mov     [rbx+18h], rcx
0x1800a05e0  mov     [rbx+20h], rsi
0x1800a05e4  mov     [rbx+28h], r13
0x1800a05e8  mov     [rbx+30h], r12
0x1800a05ec  mov     [rbx+3Ch], eax
0x1800a05ef  mov     rax, [rsp+98h+var_58]
0x1800a05f4  mov     [rbx+40h], rax
0x1800a05f8  mov     eax, [rsp+98h+var_64]
0x1800a05fc  mov     [rbx+48h], eax
0x1800a05ff  mov     rax, [rsp+98h+arg_28]
0x1800a0607  mov     rcx, [rax]; hFile
0x1800a060a  mov     [rsp+98h+lpOverlapped], rdx; lpOverlapped
0x1800a060f  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a0614  mov     rdx, rbx; lpBuffer
0x1800a0617  mov     dword ptr [rbx+38h], 7064B50h
0x1800a061e  mov     r8d, 4Ch ; 'L'; nNumberOfBytesToWrite
0x1800a0624  call    cs:__imp_WriteFile
0x1800a062a  test    eax, eax
0x1800a062c  jz      loc_1800A052F
0x1800a0632  cmp     [rsp+98h+NumberOfBytesWritten], 4Ch ; 'L'
0x1800a0637  jnz     loc_1800A052F
0x1800a063d  mov     rcx, rbx; Block
0x1800a0640  call    cs:__imp_free
0x1800a0646  cmp     qword ptr [rdi+0D8h], 0FFFFFFFFFFFFFFFFh
0x1800a064e  lea     rbp, [r14+16h]
0x1800a0652  jnz     loc_1800A07FA
0x1800a0658  mov     rdx, [rsp+98h+arg_28]
0x1800a0660  mov     r9, rdi
0x1800a0663  mov     r8, rbp
0x1800a0666  xor     ecx, ecx
0x1800a0668  call    PromptForNewDisk
0x1800a066d  test    eax, eax
0x1800a066f  jz      short loc_1800A0686
0x1800a0671  mov     eax, [rdi+0D0h]
0x1800a0677  neg     eax
0x1800a0679  sbb     eax, eax
0x1800a067b  and     eax, 0FFFFFFF6h
0x1800a067e  add     eax, 13h
0x1800a0681  jmp     loc_1800A08B6
0x1800a0686  movsxd  rcx, ebp
0x1800a0689  inc     rcx; Size
0x1800a068c  call    cs:__imp_malloc
0x1800a0692  xor     ecx, ecx
0x1800a0694  mov     rbx, rax
0x1800a0697  test    rax, rax
0x1800a069a  jz      loc_1800A08B1
0x1800a06a0  mov     dword ptr [rax], 6054B50h
0x1800a06a6  cmp     [rdi+0E9Ch], cx
0x1800a06ad  jge     loc_1800A0739
0x1800a06b3  test    r15d, r15d
0x1800a06b6  jz      short loc_1800A0716
0x1800a06b8  mov     edx, 0FFFEh
0x1800a06bd  cmp     [rdi+0EA0h], edx
0x1800a06c3  jbe     short loc_1800A06CF
0x1800a06c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a06c9  mov     [rbx+4], ax
0x1800a06cd  jmp     short loc_1800A06DE
0x1800a06cf  movzx   eax, word ptr [rdi+0EA0h]
0x1800a06d6  mov     [rbx+4], ax
0x1800a06da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a06de  cmp     [rdi+0EA4h], edx
0x1800a06e4  jbe     short loc_1800A06EC
0x1800a06e6  mov     [rbx+6], ax
0x1800a06ea  jmp     short loc_1800A06FB
0x1800a06ec  movzx   eax, word ptr [rdi+0EA4h]
0x1800a06f3  mov     [rbx+6], ax
0x1800a06f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a06fb  cmp     [rdi+0EB0h], edx
0x1800a0701  jbe     short loc_1800A0709
0x1800a0703  mov     [rbx+8], ax
0x1800a0707  jmp     short loc_1800A075B
0x1800a0709  movzx   eax, word ptr [rdi+0EB0h]
0x1800a0710  mov     [rbx+8], ax
0x1800a0714  jmp     short loc_1800A0757
0x1800a0716  movzx   eax, word ptr [rdi+0EA0h]
0x1800a071d  mov     [rbx+4], ax
0x1800a0721  movzx   eax, word ptr [rdi+0EA4h]
0x1800a0728  mov     [rbx+6], ax
0x1800a072c  movzx   eax, word ptr [rdi+0EB0h]
0x1800a0733  mov     [rbx+8], ax
0x1800a0737  jmp     short loc_1800A078B
0x1800a0739  xor     eax, eax
0x1800a073b  mov     [rbx+4], eax
0x1800a073e  test    r15d, r15d
0x1800a0741  jz      short loc_1800A0787
0x1800a0743  mov     edx, 0FFFEh
0x1800a0748  cmp     rsi, rdx
0x1800a074b  jle     short loc_1800A0753
0x1800a074d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a0751  jmp     short loc_1800A0703
0x1800a0753  mov     [rbx+8], si
0x1800a0757  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a075b  cmp     rsi, rdx
0x1800a075e  jle     short loc_1800A0766
0x1800a0760  mov     [rbx+0Ah], ax
0x1800a0764  jmp     short loc_1800A076A
0x1800a0766  mov     [rbx+0Ah], si
0x1800a076a  mov     edx, 0FFFFFFFEh
0x1800a076f  cmp     r13, rdx
0x1800a0772  jle     short loc_1800A0779
0x1800a0774  mov     [rbx+0Ch], eax
0x1800a0777  jmp     short loc_1800A077D
0x1800a0779  mov     [rbx+0Ch], r13d
0x1800a077d  cmp     r12, rdx
0x1800a0780  jle     short loc_1800A0793
0x1800a0782  mov     [rbx+10h], eax
0x1800a0785  jmp     short loc_1800A0797
0x1800a0787  mov     [rbx+8], si
0x1800a078b  mov     [rbx+0Ah], si
0x1800a078f  mov     [rbx+0Ch], r13d
0x1800a0793  mov     [rbx+10h], r12d
0x1800a0797  mov     [rbx+14h], r14w
0x1800a079c  test    r14, r14
0x1800a079f  jz      short loc_1800A07B7
0x1800a07a1  mov     rdx, [rsp+98h+Src]; Src
0x1800a07a9  lea     rcx, [rbx+16h]; void *
0x1800a07ad  mov     r8, r14; Size
0x1800a07b0  call    memcpy_0
0x1800a07b5  xor     ecx, ecx
0x1800a07b7  mov     rax, [rsp+98h+arg_28]
0x1800a07bf  mov     [rsp+98h+lpOverlapped], rcx; lpOverlapped
0x1800a07c4  mov     rcx, [rax]; hFile
0x1800a07c7  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a07cc  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800a07cf  mov     rdx, rbx; lpBuffer
0x1800a07d2  call    cs:__imp_WriteFile
0x1800a07d8  test    eax, eax
0x1800a07da  jz      loc_1800A052F
0x1800a07e0  cmp     [rsp+98h+NumberOfBytesWritten], ebp
0x1800a07e4  jnz     loc_1800A052F
0x1800a07ea  mov     rcx, rbx; Block
0x1800a07ed  call    cs:__imp_free
0x1800a07f3  xor     eax, eax
0x1800a07f5  jmp     loc_1800A08B6
0x1800a07fa  movsxd  rcx, ebp
0x1800a07fd  inc     rcx; Size
0x1800a0800  call    cs:__imp_malloc
0x1800a0806  xor     ecx, ecx
0x1800a0808  mov     rbx, rax
0x1800a080b  test    rax, rax
0x1800a080e  jz      loc_1800A08B1
0x1800a0814  mov     dword ptr [rax], 6054B50h
0x1800a081a  cmp     [rdi+0E9Ch], cx
0x1800a0821  jge     short loc_1800A0854
0x1800a0823  test    r15d, r15d
0x1800a0826  jz      short loc_1800A0831
0x1800a0828  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a082c  mov     [rbx+4], eax
0x1800a082f  jmp     short loc_1800A0862
0x1800a0831  movzx   eax, word ptr [rdi+0EA0h]
0x1800a0838  mov     [rbx+4], ax
0x1800a083c  movzx   eax, word ptr [rdi+0EA4h]
0x1800a0843  mov     [rbx+6], ax
0x1800a0847  movzx   eax, word ptr [rdi+0EB0h]
0x1800a084e  mov     [rbx+8], ax
0x1800a0852  jmp     short loc_1800A0874
0x1800a0854  xor     eax, eax
0x1800a0856  mov     [rbx+4], eax
0x1800a0859  test    r15d, r15d
0x1800a085c  jz      short loc_1800A0870
0x1800a085e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a0862  mov     [rbx+8], ax
0x1800a0866  mov     [rbx+0Ah], rax
0x1800a086a  mov     [rbx+12h], ax
0x1800a086e  jmp     short loc_1800A0880
0x1800a0870  mov     [rbx+8], si
0x1800a0874  mov     [rbx+0Ah], si
0x1800a0878  mov     [rbx+0Ch], r13d
0x1800a087c  mov     [rbx+10h], r12d
0x1800a0880  mov     [rbx+14h], r14w
0x1800a0885  test    r14, r14
0x1800a0888  jz      short loc_1800A08A0
0x1800a088a  mov     rdx, [rsp+98h+Src]; Src
0x1800a0892  lea     rcx, [rbx+16h]; void *
0x1800a0896  mov     r8, r14; Size
0x1800a0899  call    memcpy_0
0x1800a089e  xor     ecx, ecx
0x1800a08a0  mov     [rsp+98h+lpOverlapped], rcx
  ... truncated ...
```
