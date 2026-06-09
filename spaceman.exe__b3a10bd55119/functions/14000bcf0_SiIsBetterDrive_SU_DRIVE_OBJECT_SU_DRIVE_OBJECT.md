# SiIsBetterDrive(_SU_DRIVE_OBJECT *,_SU_DRIVE_OBJECT *)

- ea: `0x14000bcf0`
- end: `0x14000bee8`
- name: `?SiIsBetterDrive@@YAHPEAU_SU_DRIVE_OBJECT@@0@Z`
- size: `504`
- prototype: `_BOOL8 __fastcall(struct _SU_DRIVE_OBJECT *, struct _SU_DRIVE_OBJECT *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ce20`
- `0x14000ce68`

## callees

- `0x14000bcf0`

## pseudocode

```c
_BOOL8 __fastcall SiIsBetterDrive(struct _SU_DRIVE_OBJECT *a1, struct _SU_DRIVE_OBJECT *a2)
{
  int v4; // r11d
  int v5; // eax
  int v7; // edx
  unsigned int v8; // r8d
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  unsigned int v16; // r8d
  unsigned int v17; // edx
  unsigned int v18; // edx
  int v19; // r11d
  int v20; // r11d
  int v21; // r11d
  int v22; // r8d
  int v23; // eax
  unsigned int v24; // eax

  if ( *((_QWORD *)a1 + 7) == *((_QWORD *)a2 + 7) && *((_QWORD *)a1 + 8) == *((_QWORD *)a2 + 8) )
    return 0;
  v4 = *((_DWORD *)a1 + 714);
  v5 = *((_DWORD *)a2 + 714);
  if ( v4 == 5 )
  {
    if ( v5 != 5 )
      return 0;
  }
  else if ( v5 == 5 )
  {
    return 1;
  }
  if ( (*((_BYTE *)a1 + 20) & 1) != 0 )
  {
    if ( (*((_BYTE *)a2 + 20) & 1) == 0 )
      return 1;
  }
  else if ( (*((_BYTE *)a2 + 20) & 1) != 0 )
  {
    return 0;
  }
  v7 = *((_DWORD *)a1 + 677);
  v8 = 0;
  if ( v7 == 1 )
    goto LABEL_20;
  if ( v7 != 2 )
  {
    if ( v7 != 3 )
    {
      if ( v7 == 4 )
      {
LABEL_18:
        ++v8;
        goto LABEL_19;
      }
      if ( v7 != 5 )
        goto LABEL_21;
      v8 = 1;
    }
    ++v8;
    goto LABEL_18;
  }
LABEL_19:
  ++v8;
LABEL_20:
  ++v8;
LABEL_21:
  v9 = 0;
  if ( *((_DWORD *)a2 + 677) != 1 )
  {
    if ( *((_DWORD *)a2 + 677) == 2 )
    {
LABEL_29:
      ++v9;
      goto LABEL_30;
    }
    if ( *((_DWORD *)a2 + 677) != 3 )
    {
      if ( *((_DWORD *)a2 + 677) == 4 )
      {
LABEL_28:
        ++v9;
        goto LABEL_29;
      }
      if ( *((_DWORD *)a2 + 677) != 5 )
        goto LABEL_31;
      v9 = 1;
    }
    ++v9;
    goto LABEL_28;
  }
LABEL_30:
  ++v9;
LABEL_31:
  if ( v8 > v9 )
    return 1;
  v10 = 0;
  v11 = v7 - 1;
  if ( !v11 )
    goto LABEL_41;
  v12 = v11 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( !v14 )
      {
LABEL_39:
        ++v10;
        goto LABEL_40;
      }
      if ( v14 != 1 )
        goto LABEL_42;
      v10 = 1;
    }
    ++v10;
    goto LABEL_39;
  }
LABEL_40:
  ++v10;
LABEL_41:
  ++v10;
LABEL_42:
  v15 = 0;
  if ( *((_DWORD *)a2 + 677) == 1 )
    goto LABEL_51;
  if ( *((_DWORD *)a2 + 677) != 2 )
  {
    if ( *((_DWORD *)a2 + 677) != 3 )
    {
      if ( *((_DWORD *)a2 + 677) == 4 )
      {
LABEL_49:
        ++v15;
        goto LABEL_50;
      }
      if ( *((_DWORD *)a2 + 677) != 5 )
        goto LABEL_52;
      v15 = 1;
    }
    ++v15;
    goto LABEL_49;
  }
LABEL_50:
  ++v15;
LABEL_51:
  if ( v10 < v15 + 1 )
    return 0;
LABEL_52:
  v16 = 0;
  if ( v4 == 1 )
  {
LABEL_57:
    ++v16;
    goto LABEL_58;
  }
  if ( v4 == 2 )
  {
LABEL_58:
    ++v16;
    goto LABEL_59;
  }
  if ( v4 != 3 )
  {
    if ( v4 != 4 )
      goto LABEL_60;
    v16 = 1;
    goto LABEL_57;
  }
LABEL_59:
  ++v16;
LABEL_60:
  v17 = 0;
  if ( *((_DWORD *)a2 + 714) == 1 )
  {
LABEL_65:
    ++v17;
    goto LABEL_66;
  }
  if ( *((_DWORD *)a2 + 714) == 2 )
  {
LABEL_66:
    ++v17;
    goto LABEL_67;
  }
  if ( *((_DWORD *)a2 + 714) != 3 )
  {
    if ( *((_DWORD *)a2 + 714) != 4 )
      goto LABEL_68;
    v17 = 1;
    goto LABEL_65;
  }
LABEL_67:
  ++v17;
LABEL_68:
  if ( v16 > v17 )
    return 1;
  v18 = 0;
  v19 = v4 - 1;
  if ( !v19 )
  {
LABEL_74:
    ++v18;
    goto LABEL_75;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
LABEL_75:
    ++v18;
    goto LABEL_76;
  }
  v21 = v20 - 1;
  if ( v21 )
  {
    if ( v21 != 1 )
      goto LABEL_77;
    v18 = 1;
    goto LABEL_74;
  }
LABEL_76:
  ++v18;
LABEL_77:
  v22 = 0;
  switch ( *((_DWORD *)a2 + 714) )
  {
    case 1:
LABEL_82:
      ++v22;
      goto LABEL_83;
    case 2:
LABEL_83:
      ++v22;
LABEL_84:
      if ( v18 < v22 + 1 )
        return 0;
      break;
    case 3:
      goto LABEL_84;
    case 4:
      v22 = 1;
      goto LABEL_82;
  }
  if ( (*((_BYTE *)a1 + 20) & 2) != 0 )
  {
    if ( (*((_BYTE *)a2 + 20) & 2) == 0 )
      return 1;
  }
  else if ( (*((_BYTE *)a2 + 20) & 2) != 0 )
  {
    return 0;
  }
  v23 = *((_DWORD *)a2 + 715);
  if ( *((_DWORD *)a1 + 715) > v23 )
    return 1;
  if ( *((_DWORD *)a1 + 715) >= v23 )
  {
    v24 = *((_DWORD *)a1 + 4);
    if ( v24 > *((_DWORD *)a2 + 4) )
      return 1;
    if ( v24 >= *((_DWORD *)a2 + 4) )
      return a1 > a2;
  }
  return 0;
}

```

## disassembly

```asm
0x14000bcf0  push    rbx
0x14000bcf2  push    rsi
0x14000bcf3  push    rdi
0x14000bcf4  mov     rax, [rcx+38h]
0x14000bcf8  mov     rbx, rdx
0x14000bcfb  mov     rdi, rcx
0x14000bcfe  cmp     rax, [rdx+38h]
0x14000bd02  jnz     short loc_14000BD12
0x14000bd04  mov     rax, [rcx+40h]
0x14000bd08  cmp     rax, [rdx+40h]
0x14000bd0c  jz      loc_14000BEE2
0x14000bd12  mov     r11d, [rcx+0B28h]
0x14000bd19  mov     esi, 1
0x14000bd1e  mov     eax, [rdx+0B28h]
0x14000bd24  cmp     r11d, 5
0x14000bd28  jz      short loc_14000BD36
0x14000bd2a  cmp     eax, 5
0x14000bd2d  jnz     short loc_14000BD3F
0x14000bd2f  mov     eax, esi
0x14000bd31  jmp     loc_14000BEE4
0x14000bd36  cmp     eax, 5
0x14000bd39  jnz     loc_14000BEE2
0x14000bd3f  test    [rcx+14h], sil
0x14000bd43  jz      short loc_14000BD4D
0x14000bd45  test    [rdx+14h], sil
0x14000bd49  jz      short loc_14000BD2F
0x14000bd4b  jmp     short loc_14000BD57
0x14000bd4d  test    [rdx+14h], sil
0x14000bd51  jnz     loc_14000BEE2
0x14000bd57  mov     edx, [rcx+0A94h]
0x14000bd5d  xor     r8d, r8d
0x14000bd60  mov     ecx, edx
0x14000bd62  sub     ecx, esi
0x14000bd64  jz      short loc_14000BD82
0x14000bd66  sub     ecx, esi
0x14000bd68  jz      short loc_14000BD7F
0x14000bd6a  sub     ecx, esi
0x14000bd6c  jz      short loc_14000BD79
0x14000bd6e  sub     ecx, esi
0x14000bd70  jz      short loc_14000BD7C
0x14000bd72  cmp     ecx, esi
0x14000bd74  jnz     short loc_14000BD85
0x14000bd76  mov     r8d, esi
0x14000bd79  add     r8d, esi
0x14000bd7c  add     r8d, esi
0x14000bd7f  add     r8d, esi
0x14000bd82  add     r8d, esi
0x14000bd85  mov     r9d, [rbx+0A94h]
0x14000bd8c  xor     ecx, ecx
0x14000bd8e  mov     r10d, r9d
0x14000bd91  sub     r10d, esi
0x14000bd94  jz      short loc_14000BDB2
0x14000bd96  sub     r10d, esi
0x14000bd99  jz      short loc_14000BDB0
0x14000bd9b  sub     r10d, esi
0x14000bd9e  jz      short loc_14000BDAC
0x14000bda0  sub     r10d, esi
0x14000bda3  jz      short loc_14000BDAE
0x14000bda5  cmp     r10d, esi
0x14000bda8  jnz     short loc_14000BDB4
0x14000bdaa  mov     ecx, esi
0x14000bdac  add     ecx, esi
0x14000bdae  add     ecx, esi
0x14000bdb0  add     ecx, esi
0x14000bdb2  add     ecx, esi
0x14000bdb4  cmp     r8d, ecx
0x14000bdb7  ja      loc_14000BD2F
0x14000bdbd  xor     ecx, ecx
0x14000bdbf  sub     edx, esi
0x14000bdc1  jz      short loc_14000BDDB
0x14000bdc3  sub     edx, esi
0x14000bdc5  jz      short loc_14000BDD9
0x14000bdc7  sub     edx, esi
0x14000bdc9  jz      short loc_14000BDD5
0x14000bdcb  sub     edx, esi
0x14000bdcd  jz      short loc_14000BDD7
0x14000bdcf  cmp     edx, esi
0x14000bdd1  jnz     short loc_14000BDDD
0x14000bdd3  mov     ecx, esi
0x14000bdd5  add     ecx, esi
0x14000bdd7  add     ecx, esi
0x14000bdd9  add     ecx, esi
0x14000bddb  add     ecx, esi
0x14000bddd  xor     edx, edx
0x14000bddf  sub     r9d, esi
0x14000bde2  jz      short loc_14000BE00
0x14000bde4  sub     r9d, esi
0x14000bde7  jz      short loc_14000BDFE
0x14000bde9  sub     r9d, esi
0x14000bdec  jz      short loc_14000BDFA
0x14000bdee  sub     r9d, esi
0x14000bdf1  jz      short loc_14000BDFC
0x14000bdf3  cmp     r9d, esi
0x14000bdf6  jnz     short loc_14000BE0B
0x14000bdf8  mov     edx, esi
0x14000bdfa  add     edx, esi
0x14000bdfc  add     edx, esi
0x14000bdfe  add     edx, esi
0x14000be00  lea     eax, [rdx+1]
0x14000be03  cmp     ecx, eax
0x14000be05  jb      loc_14000BEE2
0x14000be0b  xor     r8d, r8d
0x14000be0e  mov     ecx, r11d
0x14000be11  sub     ecx, esi
0x14000be13  jz      short loc_14000BE24
0x14000be15  sub     ecx, esi
0x14000be17  jz      short loc_14000BE27
0x14000be19  sub     ecx, esi
0x14000be1b  jz      short loc_14000BE2A
0x14000be1d  cmp     ecx, esi
0x14000be1f  jnz     short loc_14000BE2D
0x14000be21  mov     r8d, esi
0x14000be24  add     r8d, esi
0x14000be27  add     r8d, esi
0x14000be2a  add     r8d, esi
0x14000be2d  mov     ecx, [rbx+0B28h]
0x14000be33  xor     edx, edx
0x14000be35  mov     r9d, ecx
0x14000be38  sub     r9d, esi
0x14000be3b  jz      short loc_14000BE4E
0x14000be3d  sub     r9d, esi
0x14000be40  jz      short loc_14000BE50
0x14000be42  sub     r9d, esi
0x14000be45  jz      short loc_14000BE52
0x14000be47  cmp     r9d, esi
0x14000be4a  jnz     short loc_14000BE54
0x14000be4c  mov     edx, esi
0x14000be4e  add     edx, esi
0x14000be50  add     edx, esi
0x14000be52  add     edx, esi
0x14000be54  cmp     r8d, edx
0x14000be57  ja      loc_14000BD2F
0x14000be5d  xor     edx, edx
0x14000be5f  sub     r11d, esi
0x14000be62  jz      short loc_14000BE75
0x14000be64  sub     r11d, esi
0x14000be67  jz      short loc_14000BE77
0x14000be69  sub     r11d, esi
0x14000be6c  jz      short loc_14000BE79
0x14000be6e  cmp     r11d, esi
0x14000be71  jnz     short loc_14000BE7B
0x14000be73  mov     edx, esi
0x14000be75  add     edx, esi
0x14000be77  add     edx, esi
0x14000be79  add     edx, esi
0x14000be7b  xor     r8d, r8d
0x14000be7e  sub     ecx, esi
0x14000be80  jz      short loc_14000BE91
0x14000be82  sub     ecx, esi
0x14000be84  jz      short loc_14000BE94
0x14000be86  sub     ecx, esi
0x14000be88  jz      short loc_14000BE97
0x14000be8a  cmp     ecx, esi
0x14000be8c  jnz     short loc_14000BE9F
0x14000be8e  mov     r8d, esi
0x14000be91  add     r8d, esi
0x14000be94  add     r8d, esi
0x14000be97  lea     eax, [r8+1]
0x14000be9b  cmp     edx, eax
0x14000be9d  jb      short loc_14000BEE2
0x14000be9f  mov     al, 2
0x14000bea1  test    [rdi+14h], al
0x14000bea4  jz      short loc_14000BEB1
0x14000bea6  test    [rbx+14h], al
0x14000bea9  jz      loc_14000BD2F
0x14000beaf  jmp     short loc_14000BEB6
0x14000beb1  test    [rbx+14h], al
0x14000beb4  jnz     short loc_14000BEE2
0x14000beb6  mov     eax, [rbx+0B2Ch]
0x14000bebc  cmp     [rdi+0B2Ch], eax
0x14000bec2  jg      loc_14000BD2F
0x14000bec8  jl      short loc_14000BEE2
0x14000beca  mov     eax, [rdi+10h]
0x14000becd  cmp     eax, [rbx+10h]
0x14000bed0  ja      loc_14000BD2F
0x14000bed6  jb      short loc_14000BEE2
0x14000bed8  xor     eax, eax
0x14000beda  cmp     rdi, rbx
0x14000bedd  setnbe  al
0x14000bee0  jmp     short loc_14000BEE4
0x14000bee2  xor     eax, eax
0x14000bee4  pop     rdi
0x14000bee5  pop     rsi
0x14000bee6  pop     rbx
0x14000bee7  retn
```
