# USBD_ValidateExtendedConfigurationDescriptor

- ea: `0x14000f338`
- end: `0x14000f552`
- name: `USBD_ValidateExtendedConfigurationDescriptor`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140026294`

## callees

- `0x14000f338`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f531`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f531`
- `ntoskrnl!ExAllocatePool2` at `0x14000f391`
- `ntoskrnl!ExAllocatePool2` at `0x14000f391`

## pseudocode

```c
__int64 __fastcall USBD_ValidateExtendedConfigurationDescriptor(
        unsigned int *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int v7; // eax
  _BYTE *Pool2; // r11
  unsigned int v9; // ebx
  unsigned __int8 *v10; // rcx
  int v11; // r10d
  unsigned __int64 v12; // r8
  int v13; // ebx
  unsigned int v14; // edx
  unsigned int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // ebx
  __int16 v22; // r10
  unsigned __int8 *v23; // r8
  unsigned __int8 *v24; // rsi
  __int64 v25; // r14
  __int64 v26; // rax
  char v27; // r9
  __int64 i; // rdx
  unsigned __int8 v29; // cl
  unsigned __int8 v30; // cl
  char v31; // r9
  __int64 j; // rdx
  unsigned __int8 v33; // cl
  unsigned __int8 v34; // cl

  if ( a1 && a2 >= 0x10 && a3 && (v7 = *(unsigned __int16 *)(a3 + 2), v7 >= 9) && v7 <= a4 )
  {
    Pool2 = (_BYTE *)ExAllocatePool2(64, 256, 1130525525);
    if ( Pool2 )
    {
      v10 = (unsigned __int8 *)(a3 + 9);
      v11 = *(unsigned __int8 *)(a3 + 4);
      v12 = a3 + *(unsigned __int16 *)(a3 + 2);
      v13 = 0;
      while ( (unsigned __int64)v10 < v12 )
      {
        if ( (unsigned __int64)&v10[*v10] > v12 )
          goto LABEL_49;
        if ( v10[1] == 11 )
        {
          v14 = 1;
          Pool2[v10[2]] = 1;
          while ( 1 )
          {
            v15 = v10[3];
            if ( v14 >= v15 )
              break;
            v16 = v14 + v10[2];
            if ( (unsigned int)v16 >= 0x100 )
              goto LABEL_49;
            Pool2[v16] = 2;
            ++v14;
          }
          ++v13;
          v11 -= v15;
        }
        if ( v10[1] == 4 )
        {
          v17 = v10[2];
          if ( !Pool2[v17] )
            Pool2[v17] = 1;
        }
        v18 = *v10;
        if ( !(_BYTE)v18 )
          break;
        v10 += v18;
      }
      v19 = *a1;
      if ( (unsigned int)(v19 - 16) > 0x1800 )
        goto LABEL_49;
      if ( (unsigned int)v19 > a2 )
        goto LABEL_49;
      if ( *((_WORD *)a1 + 3) != 4 )
        goto LABEL_49;
      v20 = *((unsigned __int8 *)a1 + 8);
      v21 = v11 + v13;
      if ( v20 > v21 || (unsigned int)v19 < 24 * v20 + 16 )
        goto LABEL_49;
      v22 = 0;
      v23 = (unsigned __int8 *)(a1 + 4);
      v24 = (unsigned __int8 *)a1 + v19;
      v25 = 0x87FFFFFE03FFLL;
      while ( v23 < v24 )
      {
        v26 = *v23;
        if ( Pool2[v26] != 1 && v21 > 1 )
          goto LABEL_49;
        v27 = 0;
        Pool2[v26] = 3;
        for ( i = 0; (unsigned int)i < 8; i = (unsigned int)(i + 1) )
        {
          v29 = v23[i + 2];
          if ( v29 )
          {
            if ( v27 )
              goto LABEL_49;
            v30 = v29 - 48;
            if ( v30 > 0x2Fu || !_bittest64(&v25, v30) )
              goto LABEL_49;
          }
          else
          {
            v27 = 1;
          }
        }
        v31 = 0;
        for ( j = 0; (unsigned int)j < 8; j = (unsigned int)(j + 1) )
        {
          v33 = v23[j + 10];
          if ( v33 )
          {
            if ( v31 )
              goto LABEL_49;
            v34 = v33 - 48;
            if ( v34 > 0x2Fu || !_bittest64(&v25, v34) )
              goto LABEL_49;
          }
          else
          {
            v31 = 1;
          }
        }
        v23 += 24;
        ++v22;
      }
      v9 = 0;
      if ( v22 != *((unsigned __int8 *)a1 + 8) )
LABEL_49:
        v9 = -1073741811;
      ExFreePoolWithTag(Pool2, 0);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v9;
}

```

## disassembly

```asm
0x14000f338  push    rbx
0x14000f33a  push    rbp
0x14000f33b  push    rsi
0x14000f33c  push    rdi
0x14000f33d  push    r14
0x14000f33f  sub     rsp, 20h
0x14000f343  mov     rbx, r8
0x14000f346  mov     esi, edx
0x14000f348  mov     rdi, rcx
0x14000f34b  test    rcx, rcx
0x14000f34e  jz      loc_14000F53F
0x14000f354  cmp     edx, 10h
0x14000f357  jb      loc_14000F53F
0x14000f35d  test    rbx, rbx
0x14000f360  jz      loc_14000F53F
0x14000f366  movzx   eax, word ptr [r8+2]
0x14000f36b  cmp     eax, 9
0x14000f36e  jb      loc_14000F53F
0x14000f374  cmp     eax, r9d
0x14000f377  ja      loc_14000F53F
0x14000f37d  mov     r14d, 100h
0x14000f383  mov     r8d, 43627355h
0x14000f389  mov     edx, r14d
0x14000f38c  mov     ecx, 40h ; '@'
0x14000f391  call    cs:__imp_ExAllocatePool2
0x14000f398  nop     dword ptr [rax+rax+00h]
0x14000f39d  mov     r11, rax
0x14000f3a0  test    rax, rax
0x14000f3a3  jnz     short loc_14000F3AF
0x14000f3a5  mov     ebx, 0C000009Ah
0x14000f3aa  jmp     loc_14000F544
0x14000f3af  movzx   r8d, word ptr [rbx+2]
0x14000f3b4  lea     rcx, [rbx+9]
0x14000f3b8  movzx   r10d, byte ptr [rbx+4]
0x14000f3bd  add     r8, rbx
0x14000f3c0  xor     ebx, ebx
0x14000f3c2  lea     ebp, [rbx+1]
0x14000f3c5  cmp     rcx, r8
0x14000f3c8  jnb     short loc_14000F431
0x14000f3ca  movzx   eax, byte ptr [rcx]
0x14000f3cd  add     rax, rcx
0x14000f3d0  cmp     rax, r8
0x14000f3d3  ja      loc_14000F527
0x14000f3d9  cmp     byte ptr [rcx+1], 0Bh
0x14000f3dd  jnz     short loc_14000F410
0x14000f3df  movzx   eax, byte ptr [rcx+2]
0x14000f3e3  mov     edx, ebp
0x14000f3e5  mov     [rax+r11], bpl
0x14000f3e9  movzx   eax, byte ptr [rcx+3]
0x14000f3ed  cmp     edx, eax
0x14000f3ef  jnb     short loc_14000F40B
0x14000f3f1  movzx   r9d, byte ptr [rcx+2]
0x14000f3f6  add     r9d, edx
0x14000f3f9  cmp     r9d, r14d
0x14000f3fc  jnb     loc_14000F527
0x14000f402  mov     byte ptr [r9+r11], 2
0x14000f407  add     edx, ebp
0x14000f409  jmp     short loc_14000F3E9
0x14000f40b  add     ebx, ebp
0x14000f40d  sub     r10d, eax
0x14000f410  cmp     byte ptr [rcx+1], 4
0x14000f414  jnz     short loc_14000F425
0x14000f416  movzx   eax, byte ptr [rcx+2]
0x14000f41a  cmp     byte ptr [rax+r11], 0
0x14000f41f  jnz     short loc_14000F425
0x14000f421  mov     [rax+r11], bpl
0x14000f425  movzx   eax, byte ptr [rcx]
0x14000f428  test    al, al
0x14000f42a  jz      short loc_14000F431
0x14000f42c  add     rcx, rax
0x14000f42f  jmp     short loc_14000F3C5
0x14000f431  mov     ecx, [rdi]
0x14000f433  lea     eax, [rcx-10h]
0x14000f436  cmp     eax, 1800h
0x14000f43b  ja      loc_14000F527
0x14000f441  cmp     ecx, esi
0x14000f443  ja      loc_14000F527
0x14000f449  cmp     word ptr [rdi+6], 4
0x14000f44e  jnz     loc_14000F527
0x14000f454  movzx   eax, byte ptr [rdi+8]
0x14000f458  add     ebx, r10d
0x14000f45b  cmp     eax, ebx
0x14000f45d  ja      loc_14000F527
0x14000f463  lea     eax, [rax+rax*2]
0x14000f466  lea     eax, ds:10h[rax*8]
0x14000f46d  cmp     ecx, eax
0x14000f46f  jb      loc_14000F527
0x14000f475  xor     r10d, r10d
0x14000f478  lea     r8, [rdi+10h]
0x14000f47c  lea     rsi, [rdi+rcx]
0x14000f480  mov     r14, 87FFFFFE03FFh
0x14000f48a  cmp     r8, rsi
0x14000f48d  jnb     loc_14000F51B
0x14000f493  movzx   eax, byte ptr [r8]
0x14000f497  cmp     [rax+r11], bpl
0x14000f49b  jz      short loc_14000F4A5
0x14000f49d  cmp     ebx, ebp
0x14000f49f  ja      loc_14000F527
0x14000f4a5  xor     r9b, r9b
0x14000f4a8  mov     byte ptr [rax+r11], 3
0x14000f4ad  xor     edx, edx
0x14000f4af  cmp     edx, 8
0x14000f4b2  jnb     short loc_14000F4DC
0x14000f4b4  mov     cl, [rdx+r8+2]
0x14000f4b9  test    cl, cl
0x14000f4bb  jnz     short loc_14000F4C2
0x14000f4bd  mov     r9b, bpl
0x14000f4c0  jmp     short loc_14000F4D8
0x14000f4c2  test    r9b, r9b
0x14000f4c5  jnz     short loc_14000F527
0x14000f4c7  sub     cl, 30h ; '0'
0x14000f4ca  cmp     cl, 2Fh ; '/'
0x14000f4cd  ja      short loc_14000F527
0x14000f4cf  movzx   eax, cl
0x14000f4d2  bt      r14, rax
0x14000f4d6  jnb     short loc_14000F527
0x14000f4d8  add     edx, ebp
0x14000f4da  jmp     short loc_14000F4AF
0x14000f4dc  xor     r9b, r9b
0x14000f4df  xor     edx, edx
0x14000f4e1  cmp     edx, 8
0x14000f4e4  jnb     short loc_14000F50E
0x14000f4e6  mov     cl, [rdx+r8+0Ah]
0x14000f4eb  test    cl, cl
0x14000f4ed  jnz     short loc_14000F4F4
0x14000f4ef  mov     r9b, bpl
0x14000f4f2  jmp     short loc_14000F50A
0x14000f4f4  test    r9b, r9b
0x14000f4f7  jnz     short loc_14000F527
0x14000f4f9  sub     cl, 30h ; '0'
0x14000f4fc  cmp     cl, 2Fh ; '/'
0x14000f4ff  ja      short loc_14000F527
0x14000f501  movzx   eax, cl
0x14000f504  bt      r14, rax
0x14000f508  jnb     short loc_14000F527
0x14000f50a  add     edx, ebp
0x14000f50c  jmp     short loc_14000F4E1
0x14000f50e  add     r8, 18h
0x14000f512  add     r10w, bp
0x14000f516  jmp     loc_14000F48A
0x14000f51b  movzx   eax, byte ptr [rdi+8]
0x14000f51f  xor     ebx, ebx
0x14000f521  cmp     r10w, ax
0x14000f525  jz      short loc_14000F52C
0x14000f527  mov     ebx, 0C000000Dh
0x14000f52c  xor     edx, edx; Tag
0x14000f52e  mov     rcx, r11; P
0x14000f531  call    cs:__imp_ExFreePoolWithTag
0x14000f538  nop     dword ptr [rax+rax+00h]
0x14000f53d  jmp     short loc_14000F544
0x14000f53f  mov     ebx, 0C000000Dh
0x14000f544  mov     eax, ebx
0x14000f546  add     rsp, 20h
0x14000f54a  pop     r14
0x14000f54c  pop     rdi
0x14000f54d  pop     rsi
0x14000f54e  pop     rbp
0x14000f54f  pop     rbx
0x14000f550  retn
```
