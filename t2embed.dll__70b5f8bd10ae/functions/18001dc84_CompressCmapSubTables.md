# CompressCmapSubTables

- ea: `0x18001dc84`
- end: `0x18001df8d`
- name: `CompressCmapSubTables`
- size: `777`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d5f8`

## callees

- `0x180010618`
- `0x180011640`
- `0x180013230`
- `0x1800134a0`
- `0x1800164a0`
- `0x18001ce6c`
- `0x18001dc84`
- `0x18002738c`
- `0x180027504`

## pseudocode

```c
__int64 __fastcall CompressCmapSubTables(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned __int16 v7; // r14
  __int64 v9; // rdi
  unsigned __int16 updated; // bx
  unsigned int v12; // r13d
  unsigned __int16 i; // dx
  unsigned __int16 j; // r8
  unsigned __int16 v15; // r9
  int v17; // edx
  __int64 v18; // rcx
  unsigned __int16 v19; // r15
  int v20; // r8d
  __int64 v21; // rbp
  unsigned int v22; // ecx
  unsigned int v23; // esi
  __int64 v24; // r9
  int v25; // eax
  __int64 v26; // rbp
  unsigned __int16 v27; // r12
  unsigned __int16 v28; // bp
  unsigned int v29; // r13d
  unsigned __int16 v30; // ax
  unsigned __int16 v31; // bp
  unsigned __int16 k; // dx
  __int64 v33; // rax
  unsigned int v34; // esi
  _WORD v35[2]; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 v36; // [rsp+34h] [rbp-64h]
  unsigned int v37; // [rsp+38h] [rbp-60h]
  int v38; // [rsp+3Ch] [rbp-5Ch]
  int v39; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v40; // [rsp+44h] [rbp-54h]

  v7 = a3;
  LOWORD(v40) = 0;
  v39 = 0;
  v35[0] = 0;
  v9 = Mem_Alloc(8LL * a3);
  if ( !v9 )
    return 1005;
  updated = 0;
  v12 = 0;
  for ( i = 0; i < v7; ++i )
  {
    for ( j = 0; j < i; ++j )
    {
      if ( *(_DWORD *)(a2 + 8LL * i + 4) < *(_DWORD *)(a2 + 8LL * *(unsigned __int16 *)(v9 + 8LL * j) + 4) )
      {
        v15 = i;
        do
        {
          *(_WORD *)(v9 + 8LL * v15) = *(_WORD *)(v9 + 8LL * v15 - 8);
          --v15;
        }
        while ( v15 > j );
        break;
      }
    }
    *(_WORD *)(v9 + 8LL * j) = i;
  }
  v17 = 0;
  v18 = a2;
  v19 = 0;
  v20 = a4;
  while ( v19 < v7 )
  {
    v21 = 8LL * *(unsigned __int16 *)(v9 + 8LL * v19);
    if ( v19 && *(_DWORD *)(v18 + v21 + 4) == v17 )
    {
      *(_DWORD *)(v9 + 8LL * v19 + 4) = *(_DWORD *)(v9 + 8LL * v19 - 4);
    }
    else
    {
      updated = ReadCmapLength(a1, &v39, (unsigned int)(*(_DWORD *)(v18 + v21 + 4) + v20), v35);
      if ( updated )
        goto LABEL_31;
      v22 = a5;
      v23 = (a5 + 1) & 0xFFFFFFFE;
      v37 = v22;
      v36 = v23 - v22;
      if ( v12 + v40 + (unsigned __int16)(v23 - v22) > a6 )
      {
        updated = 1007;
        goto LABEL_31;
      }
      v24 = v40;
      *(_DWORD *)(v9 + 8LL * v19 + 4) = v23 - a4;
      v25 = *(_DWORD *)(a2 + v21 + 4);
      v26 = a1;
      v38 = v25;
      updated = CopyBlock(a1, v23, (unsigned int)(v25 + a4), v24);
      if ( updated )
        goto LABEL_32;
      v27 = v36;
      v28 = 0;
      v29 = v37;
      do
      {
        if ( v28 >= v27 )
          break;
        v30 = WriteByte(a1, 0, v29 + v28++);
        updated = v30;
      }
      while ( !v30 );
      a5 = v40 + v23;
      v20 = a4;
      v7 = a3;
      v12 = a5 - a4;
      v18 = a2;
      v17 = v38;
    }
    ++v19;
  }
  v31 = 0;
  if ( !updated )
  {
    for ( k = 0; k < v7; *(_DWORD *)(a2 + 8LL * *(unsigned __int16 *)(v9 + 8 * v33) + 4) = *(_DWORD *)(v9 + 8 * v33 + 4) )
      v33 = k++;
    v34 = a4 + (unsigned __int16)GetGenericSize(CMAP_HEADER_CONTROL);
    if ( v7 )
    {
      do
      {
        updated = WriteGeneric(a1, a2 + 8LL * v31, 8u, (unsigned __int8 *)CMAP_TABLELOC_CONTROL, v34, v35);
        if ( updated )
          break;
        ++v31;
        v34 += v35[0];
      }
      while ( v31 < v7 );
    }
  }
LABEL_31:
  v26 = a1;
LABEL_32:
  Mem_Free(v9);
  if ( !updated )
    updated = UpdateDirEntry(v26, "cmap", v12);
  *a7 = v12;
  return updated;
}

```

## disassembly

```asm
0x18001dc84  mov     rax, rsp
0x18001dc87  mov     [rax+20h], r9d
0x18001dc8b  mov     [rax+18h], r8w
0x18001dc90  mov     [rax+10h], rdx
0x18001dc94  mov     [rax+8], rcx
0x18001dc98  push    rbx
0x18001dc99  push    rbp
0x18001dc9a  push    rsi
0x18001dc9b  push    rdi
0x18001dc9c  push    r12
0x18001dc9e  push    r13
0x18001dca0  push    r14
0x18001dca2  push    r15
0x18001dca4  sub     rsp, 58h
0x18001dca8  xor     eax, eax
0x18001dcaa  movzx   r14d, r8w
0x18001dcae  mov     [rsp+98h+var_56], eax
0x18001dcb2  mov     ecx, r14d
0x18001dcb5  xor     ebp, ebp
0x18001dcb7  shl     rcx, 3; Size
0x18001dcbb  mov     r12, rdx
0x18001dcbe  mov     [rsp+40h], eax
0x18001dcc2  mov     [rsp+98h+var_68], bp
0x18001dcc7  call    Mem_Alloc
0x18001dccc  mov     rdi, rax
0x18001dccf  test    rax, rax
0x18001dcd2  jnz     short loc_18001DCDE
0x18001dcd4  mov     eax, 3EDh
0x18001dcd9  jmp     loc_18001DF7C
0x18001dcde  mov     ebx, ebp
0x18001dce0  mov     r13d, ebp
0x18001dce3  mov     edx, ebp
0x18001dce5  cmp     bp, r14w
0x18001dce9  jnb     short loc_18001DD43
0x18001dceb  mov     r8d, ebp
0x18001dcee  movzx   r9d, dx
0x18001dcf2  cmp     r8w, dx
0x18001dcf6  jnb     short loc_18001DD32
0x18001dcf8  movzx   eax, r8w
0x18001dcfc  movzx   ecx, word ptr [rdi+rax*8]
0x18001dd00  mov     eax, [r12+rcx*8+4]
0x18001dd05  cmp     [r12+r9*8+4], eax
0x18001dd0a  jb      short loc_18001DD12
0x18001dd0c  inc     r8w
0x18001dd10  jmp     short loc_18001DCF2
0x18001dd12  movzx   r9d, dx
0x18001dd16  movzx   ecx, r9w
0x18001dd1a  movzx   eax, word ptr [rdi+rcx*8-8]
0x18001dd1f  mov     [rdi+rcx*8], ax
0x18001dd23  mov     eax, 0FFFFh
0x18001dd28  add     r9w, ax
0x18001dd2c  cmp     r9w, r8w
0x18001dd30  ja      short loc_18001DD16
0x18001dd32  movzx   eax, r8w
0x18001dd36  mov     [rdi+rax*8], dx
0x18001dd3a  inc     dx
0x18001dd3d  cmp     dx, r14w
0x18001dd41  jb      short loc_18001DCEB
0x18001dd43  mov     esi, [rsp+98h+arg_20]
0x18001dd4a  mov     edx, ebp
0x18001dd4c  mov     rcx, [rsp+98h+arg_8]
0x18001dd54  mov     r15d, ebp
0x18001dd57  mov     r8d, [rsp+98h+arg_18]
0x18001dd5f  xor     r9d, r9d
0x18001dd62  cmp     r15w, r14w
0x18001dd66  jnb     loc_18001DEAA
0x18001dd6c  movzx   r12d, r15w
0x18001dd70  movzx   eax, word ptr [rdi+r12*8]
0x18001dd75  lea     rbp, ds:0[rax*8]
0x18001dd7d  test    r15w, r15w
0x18001dd81  jz      short loc_18001DD98
0x18001dd83  cmp     [rcx+rbp+4], edx
0x18001dd87  jnz     short loc_18001DD98
0x18001dd89  mov     eax, [rdi+r12*8-4]
0x18001dd8e  mov     [rdi+r12*8+4], eax
0x18001dd93  jmp     loc_18001DE97
0x18001dd98  add     r8d, [rcx+rbp+4]
0x18001dd9d  lea     r9, [rsp+98h+var_68]
0x18001dda2  mov     rcx, [rsp+98h+arg_0]
0x18001ddaa  lea     rdx, [rsp+98h+var_58]
0x18001ddaf  call    ReadCmapLength
0x18001ddb4  movzx   ebx, ax
0x18001ddb7  test    ax, ax
0x18001ddba  jnz     loc_18001DF44
0x18001ddc0  mov     ecx, esi
0x18001ddc2  inc     esi
0x18001ddc4  and     esi, 0FFFFFFFEh
0x18001ddc7  mov     [rsp+98h+var_60], ecx
0x18001ddcb  movzx   eax, si
0x18001ddce  sub     ax, cx
0x18001ddd1  mov     [rsp+98h+var_64], ax
0x18001ddd6  movzx   eax, ax
0x18001ddd9  add     eax, [rsp+98h+var_56+2]
0x18001dddd  add     eax, r13d
0x18001dde0  cmp     eax, [rsp+98h+arg_28]
0x18001dde7  ja      loc_18001DEA0
0x18001dded  mov     ecx, [rsp+98h+arg_18]
0x18001ddf4  mov     eax, esi
0x18001ddf6  mov     r9d, [rsp+98h+var_56+2]
0x18001ddfb  sub     eax, ecx
0x18001ddfd  mov     [rdi+r12*8+4], eax
0x18001de02  mov     edx, esi
0x18001de04  mov     rax, [rsp+98h+arg_8]
0x18001de0c  mov     eax, [rax+rbp+4]
0x18001de10  mov     rbp, [rsp+98h+arg_0]
0x18001de18  mov     [rsp+98h+var_5C], eax
0x18001de1c  lea     r8d, [rax+rcx]
0x18001de20  mov     rcx, rbp
0x18001de23  call    CopyBlock
0x18001de28  movzx   ebx, ax
0x18001de2b  xor     eax, eax
0x18001de2d  test    bx, bx
0x18001de30  jnz     loc_18001DF4C
0x18001de36  movzx   r12d, [rsp+98h+var_64]
0x18001de3c  mov     ebp, eax
0x18001de3e  mov     r13d, [rsp+98h+var_60]
0x18001de43  mov     r14, [rsp+98h+arg_0]
0x18001de4b  cmp     bp, r12w
0x18001de4f  jnb     short loc_18001DE6D
0x18001de51  movzx   r8d, bp
0x18001de55  xor     edx, edx
0x18001de57  add     r8d, r13d
0x18001de5a  mov     rcx, r14
0x18001de5d  call    WriteByte
0x18001de62  inc     bp
0x18001de65  movzx   ebx, ax
0x18001de68  test    ax, ax
0x18001de6b  jz      short loc_18001DE4B
0x18001de6d  add     esi, [rsp+98h+var_56+2]
0x18001de71  mov     r8d, [rsp+98h+arg_18]
0x18001de79  mov     r13d, esi
0x18001de7c  movzx   r14d, [rsp+98h+arg_10]
0x18001de85  sub     r13d, r8d
0x18001de88  mov     rcx, [rsp+98h+arg_8]
0x18001de90  xor     r9d, r9d
0x18001de93  mov     edx, [rsp+98h+var_5C]
0x18001de97  inc     r15w
0x18001de9b  jmp     loc_18001DD62
0x18001dea0  mov     ebx, 3EFh
0x18001dea5  jmp     loc_18001DF44
0x18001deaa  xor     ebp, ebp
0x18001deac  test    bx, bx
0x18001deaf  jnz     loc_18001DF44
0x18001deb5  mov     r12, [rsp+98h+arg_8]
0x18001debd  mov     edx, ebp
0x18001debf  cmp     bp, r14w
0x18001dec3  jnb     short loc_18001DEDE
0x18001dec5  movzx   eax, dx
0x18001dec8  inc     dx
0x18001decb  movzx   ecx, word ptr [rdi+rax*8]
0x18001decf  mov     eax, [rdi+rax*8+4]
0x18001ded3  mov     [r12+rcx*8+4], eax
0x18001ded8  cmp     dx, r14w
0x18001dedc  jb      short loc_18001DEC5
0x18001dede  lea     rcx, CMAP_HEADER_CONTROL
0x18001dee5  call    GetGenericSize
0x18001deea  movzx   esi, ax
0x18001deed  xor     r15d, r15d
0x18001def0  add     esi, [rsp+98h+arg_18]
0x18001def7  cmp     r15w, r14w
0x18001defb  jnb     short loc_18001DF44
0x18001defd  mov     rcx, [rsp+98h+arg_0]
0x18001df05  lea     r9, CMAP_TABLELOC_CONTROL
0x18001df0c  movzx   eax, bp
0x18001df0f  mov     r8d, 8
0x18001df15  lea     rdx, [r12+rax*8]
0x18001df19  lea     rax, [rsp+98h+var_68]
0x18001df1e  mov     [rsp+98h+var_70], rax
0x18001df23  mov     [rsp+98h+var_78], esi
0x18001df27  call    WriteGeneric
0x18001df2c  movzx   ebx, ax
0x18001df2f  test    ax, ax
0x18001df32  jnz     short loc_18001DF44
0x18001df34  movzx   eax, [rsp+98h+var_68]
0x18001df39  inc     bp
0x18001df3c  add     esi, eax
0x18001df3e  cmp     bp, r14w
0x18001df42  jb      short loc_18001DEFD
0x18001df44  mov     rbp, [rsp+98h+arg_0]
0x18001df4c  mov     rcx, rdi
0x18001df4f  call    Mem_Free
0x18001df54  test    bx, bx
0x18001df57  jnz     short loc_18001DF6E
0x18001df59  mov     r8d, r13d
0x18001df5c  lea     rdx, aCmap; "cmap"
0x18001df63  mov     rcx, rbp
0x18001df66  call    UpdateDirEntry
0x18001df6b  movzx   ebx, ax
0x18001df6e  mov     rax, [rsp+98h+arg_30]
0x18001df76  mov     [rax], r13d
0x18001df79  movzx   eax, bx
0x18001df7c  add     rsp, 58h
0x18001df80  pop     r15
0x18001df82  pop     r14
0x18001df84  pop     r13
0x18001df86  pop     r12
0x18001df88  pop     rdi
0x18001df89  pop     rsi
0x18001df8a  pop     rbp
0x18001df8b  pop     rbx
0x18001df8c  retn
```
