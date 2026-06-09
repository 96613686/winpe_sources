# SkpgCreateSecureVaTranslationExtents

- ea: `0x1400a3b78`
- end: `0x1400a3ee9`
- name: `SkpgCreateSecureVaTranslationExtents`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1400a3798`

## callees

- `0x14004bbb4`
- `0x1400a3b78`
- `0x1400a4cac`
- `0x1400a5694`

## pseudocode

```c
__int64 __fastcall SkpgCreateSecureVaTranslationExtents(
        __int64 a1,
        _QWORD *a2,
        unsigned __int64 *a3,
        int *a4,
        _DWORD *a5)
{
  unsigned __int64 v8; // rdi
  int v9; // ebp
  int IsImagePatchingEnabled; // eax
  __int64 *v11; // rdx
  int v12; // r12d
  int v13; // r14d
  unsigned __int64 v14; // rax
  __int64 v15; // rbx

  v8 = *a3 + 144;
  if ( v8 <= *a3 )
    return 3221225621LL;
  v9 = *a4 + 3;
  IsImagePatchingEnabled = SkmmIsImagePatchingEnabled();
  v12 = IsImagePatchingEnabled;
  if ( (*a5 & 4) != 0 )
  {
    v13 = 1;
  }
  else
  {
    v13 = 0;
    if ( v8 + 48 < v8 )
      return 3221225621LL;
    v8 += 48LL;
    ++v9;
  }
  if ( (SkmiFlags & 0x1000) != 0 && !v13 )
  {
    if ( v8 + 240 < v8 )
      return 3221225621LL;
    v8 += 240LL;
    v9 += 5;
  }
  if ( IsImagePatchingEnabled )
  {
    v14 = v8 + 48;
    if ( v8 + 48 >= v8 )
    {
      ++v9;
      if ( !SkpgNtExtension )
      {
        v8 += 48LL;
        goto LABEL_16;
      }
      v8 += 96LL;
      if ( v14 + 48 >= v14 )
      {
        ++v9;
        goto LABEL_16;
      }
    }
    return 3221225621LL;
  }
LABEL_16:
  v15 = *v11;
  if ( a1 )
  {
    SkpgInitializeExtent(a1, v15, 4113, 0, 0);
    *(_WORD *)(v15 + 2) |= 4u;
    *(_BYTE *)(v15 + 3) = SkpgExtentCrc(a1, v15);
    SkpgInitializeExtent(a1, v15 + 48, 4107, 0, 0);
    *(_WORD *)(v15 + 50) |= 4u;
    *(_BYTE *)(v15 + 51) = SkpgExtentCrc(a1, v15 + 48);
    SkpgInitializeExtent(a1, v15 + 96, 4119, 0, 0);
    *(_WORD *)(v15 + 98) |= 4u;
    *(_BYTE *)(v15 + 99) = SkpgExtentCrc(a1, v15 + 96);
    v15 += 144;
    if ( !v13 )
    {
      SkpgInitializeExtent(a1, v15, 4121, 0, 0);
      *(_WORD *)(v15 + 2) |= 4u;
      *(_BYTE *)(v15 + 3) = SkpgExtentCrc(a1, v15);
      v15 += 48;
    }
    if ( (SkmiFlags & 0x1000) != 0 && !v13 )
    {
      SkpgInitializeExtent(a1, v15, 4110, 0, 0);
      *(_WORD *)(v15 + 2) |= 4u;
      *(_BYTE *)(v15 + 3) = SkpgExtentCrc(a1, v15);
      SkpgInitializeExtent(a1, v15 + 48, 4112, 0, 0);
      *(_WORD *)(v15 + 50) |= 4u;
      *(_BYTE *)(v15 + 51) = SkpgExtentCrc(a1, v15 + 48);
      SkpgInitializeExtent(a1, v15 + 96, 4111, 0, 0);
      *(_WORD *)(v15 + 98) |= 4u;
      *(_BYTE *)(v15 + 99) = SkpgExtentCrc(a1, v15 + 96);
      SkpgInitializeExtent(a1, v15 + 144, 4114, 0, 0);
      *(_WORD *)(v15 + 146) |= 4u;
      *(_BYTE *)(v15 + 147) = SkpgExtentCrc(a1, v15 + 144);
      SkpgInitializeExtent(a1, v15 + 192, 4122, 0, 0);
      *(_WORD *)(v15 + 194) |= 4u;
      *(_BYTE *)(v15 + 195) = SkpgExtentCrc(a1, v15 + 192);
      v15 += 240;
    }
    if ( v12 )
    {
      SkpgInitializeExtent(a1, v15, 4117, 0, 0);
      *(_DWORD *)(v15 + 32) |= 1u;
      *(_QWORD *)(v15 + 24) = &SkpgSecureExtension;
      *(_BYTE *)(v15 + 3) = SkpgExtentCrc(a1, v15);
      v15 += 48;
      if ( SkpgNtExtension )
      {
        SkpgInitializeExtent(a1, v15, 4117, 0, 0);
        *(_DWORD *)(v15 + 32) |= 1u;
        *(_QWORD *)(v15 + 24) = &SkpgNtExtension;
        *(_BYTE *)(v15 + 3) = SkpgExtentCrc(a1, v15);
        v15 += 48;
      }
    }
  }
  *a2 = v15;
  *a3 = v8;
  *a4 = v9;
  return 0;
}

```

## disassembly

```asm
0x1400a3b78  mov     [rsp+arg_18], r9
0x1400a3b7d  push    rbx
0x1400a3b7e  push    rbp
0x1400a3b7f  push    rsi
0x1400a3b80  push    rdi
0x1400a3b81  push    r12
0x1400a3b83  push    r13
0x1400a3b85  push    r14
0x1400a3b87  push    r15
0x1400a3b89  sub     rsp, 38h
0x1400a3b8d  mov     rax, [r8]
0x1400a3b90  mov     r15, r8
0x1400a3b93  mov     r13, rdx
0x1400a3b96  mov     rsi, rcx
0x1400a3b99  lea     rdi, [rax+90h]
0x1400a3ba0  cmp     rdi, rax
0x1400a3ba3  jbe     loc_1400A3ED2
0x1400a3ba9  mov     ebp, [r9]
0x1400a3bac  add     ebp, 3
0x1400a3baf  call    SkmmIsImagePatchingEnabled
0x1400a3bb4  mov     r10, [rsp+78h+arg_20]
0x1400a3bbc  mov     r12d, eax
0x1400a3bbf  mov     r9d, [r10]
0x1400a3bc2  test    r9b, 4
0x1400a3bc6  jz      short loc_1400A3BD0
0x1400a3bc8  mov     r14d, 1
0x1400a3bce  jmp     short loc_1400A3BE5
0x1400a3bd0  xor     r14d, r14d
0x1400a3bd3  lea     rax, [rdi+30h]
0x1400a3bd7  cmp     rax, rdi
0x1400a3bda  jbe     loc_1400A3ED2
0x1400a3be0  mov     rdi, rax
0x1400a3be3  inc     ebp
0x1400a3be5  test    cs:SkmiFlags, 1000h
0x1400a3bef  jz      short loc_1400A3C0C
0x1400a3bf1  test    r14d, r14d
0x1400a3bf4  jnz     short loc_1400A3C0C
0x1400a3bf6  lea     rax, [rdi+0F0h]
0x1400a3bfd  cmp     rax, rdi
0x1400a3c00  jbe     loc_1400A3ED2
0x1400a3c06  mov     rdi, rax
0x1400a3c09  add     ebp, 5
0x1400a3c0c  test    r12d, r12d
0x1400a3c0f  jz      short loc_1400A3C3E
0x1400a3c11  lea     rax, [rdi+30h]
0x1400a3c15  cmp     rax, rdi
0x1400a3c18  jbe     loc_1400A3ED2
0x1400a3c1e  inc     ebp
0x1400a3c20  cmp     cs:SkpgNtExtension, 0
0x1400a3c28  jz      short loc_1400A3C3B
0x1400a3c2a  lea     rdi, [rax+30h]
0x1400a3c2e  cmp     rdi, rax
0x1400a3c31  jbe     loc_1400A3ED2
0x1400a3c37  inc     ebp
0x1400a3c39  jmp     short loc_1400A3C3E
0x1400a3c3b  mov     rdi, rax
0x1400a3c3e  mov     rbx, [rdx]
0x1400a3c41  test    rsi, rsi
0x1400a3c44  jz      loc_1400A3EBD
0x1400a3c4a  xor     r9d, r9d
0x1400a3c4d  mov     [rsp+78h+var_58], 0
0x1400a3c55  mov     r8d, 1011h
0x1400a3c5b  mov     rdx, rbx
0x1400a3c5e  mov     rcx, rsi
0x1400a3c61  call    SkpgInitializeExtent
0x1400a3c66  or      word ptr [rbx+2], 4
0x1400a3c6b  mov     rdx, rbx
0x1400a3c6e  mov     rcx, rsi
0x1400a3c71  call    SkpgExtentCrc
0x1400a3c76  xor     r9d, r9d
0x1400a3c79  mov     [rbx+3], al
0x1400a3c7c  mov     r8d, 100Bh
0x1400a3c82  mov     [rsp+78h+var_58], 0
0x1400a3c8a  lea     rdx, [rbx+30h]
0x1400a3c8e  mov     rcx, rsi
0x1400a3c91  call    SkpgInitializeExtent
0x1400a3c96  or      word ptr [rbx+32h], 4
0x1400a3c9b  lea     rdx, [rbx+30h]
0x1400a3c9f  mov     rcx, rsi
0x1400a3ca2  call    SkpgExtentCrc
0x1400a3ca7  xor     r9d, r9d
0x1400a3caa  mov     [rbx+33h], al
0x1400a3cad  mov     r8d, 1017h
0x1400a3cb3  mov     [rsp+78h+var_58], 0
0x1400a3cbb  lea     rdx, [rbx+60h]
0x1400a3cbf  mov     rcx, rsi
0x1400a3cc2  call    SkpgInitializeExtent
0x1400a3cc7  or      word ptr [rbx+62h], 4
0x1400a3ccc  lea     rdx, [rbx+60h]
0x1400a3cd0  mov     rcx, rsi
0x1400a3cd3  call    SkpgExtentCrc
0x1400a3cd8  mov     [rbx+63h], al
0x1400a3cdb  add     rbx, 90h
0x1400a3ce2  test    r14d, r14d
0x1400a3ce5  jnz     short loc_1400A3D17
0x1400a3ce7  xor     r9d, r9d
0x1400a3cea  mov     [rsp+78h+var_58], r14d
0x1400a3cef  mov     r8d, 1019h
0x1400a3cf5  mov     rdx, rbx
0x1400a3cf8  mov     rcx, rsi
0x1400a3cfb  call    SkpgInitializeExtent
0x1400a3d00  or      word ptr [rbx+2], 4
0x1400a3d05  mov     rdx, rbx
0x1400a3d08  mov     rcx, rsi
0x1400a3d0b  call    SkpgExtentCrc
0x1400a3d10  mov     [rbx+3], al
0x1400a3d13  add     rbx, 30h ; '0'
0x1400a3d17  test    cs:SkmiFlags, 1000h
0x1400a3d21  jz      loc_1400A3E38
0x1400a3d27  test    r14d, r14d
0x1400a3d2a  jnz     loc_1400A3E38
0x1400a3d30  xor     r14d, r14d
0x1400a3d33  xor     r9d, r9d
0x1400a3d36  mov     r8d, 100Eh
0x1400a3d3c  mov     [rsp+78h+var_58], r14d
0x1400a3d41  mov     rdx, rbx
0x1400a3d44  mov     rcx, rsi
0x1400a3d47  call    SkpgInitializeExtent
0x1400a3d4c  or      word ptr [rbx+2], 4
0x1400a3d51  mov     rdx, rbx
0x1400a3d54  mov     rcx, rsi
0x1400a3d57  call    SkpgExtentCrc
0x1400a3d5c  xor     r9d, r9d
0x1400a3d5f  mov     [rbx+3], al
0x1400a3d62  mov     r8d, 1010h
0x1400a3d68  mov     [rsp+78h+var_58], r14d
0x1400a3d6d  lea     rdx, [rbx+30h]
0x1400a3d71  mov     rcx, rsi
0x1400a3d74  call    SkpgInitializeExtent
0x1400a3d79  or      word ptr [rbx+32h], 4
0x1400a3d7e  lea     rdx, [rbx+30h]
0x1400a3d82  mov     rcx, rsi
0x1400a3d85  call    SkpgExtentCrc
0x1400a3d8a  xor     r9d, r9d
0x1400a3d8d  mov     [rbx+33h], al
0x1400a3d90  mov     r8d, 100Fh
0x1400a3d96  mov     [rsp+78h+var_58], r14d
0x1400a3d9b  lea     rdx, [rbx+60h]
0x1400a3d9f  mov     rcx, rsi
0x1400a3da2  call    SkpgInitializeExtent
0x1400a3da7  or      word ptr [rbx+62h], 4
0x1400a3dac  lea     rdx, [rbx+60h]
0x1400a3db0  mov     rcx, rsi
0x1400a3db3  call    SkpgExtentCrc
0x1400a3db8  xor     r9d, r9d
0x1400a3dbb  mov     [rbx+63h], al
0x1400a3dbe  mov     r8d, 1012h
0x1400a3dc4  mov     [rsp+78h+var_58], r14d
0x1400a3dc9  lea     rdx, [rbx+90h]
0x1400a3dd0  mov     rcx, rsi
0x1400a3dd3  call    SkpgInitializeExtent
0x1400a3dd8  or      word ptr [rbx+92h], 4
0x1400a3de0  lea     rdx, [rbx+90h]
0x1400a3de7  mov     rcx, rsi
0x1400a3dea  call    SkpgExtentCrc
0x1400a3def  xor     r9d, r9d
0x1400a3df2  mov     [rbx+93h], al
0x1400a3df8  mov     r8d, 101Ah
0x1400a3dfe  mov     [rsp+78h+var_58], r14d
0x1400a3e03  lea     rdx, [rbx+0C0h]
0x1400a3e0a  mov     rcx, rsi
0x1400a3e0d  call    SkpgInitializeExtent
0x1400a3e12  or      word ptr [rbx+0C2h], 4
0x1400a3e1a  lea     rdx, [rbx+0C0h]
0x1400a3e21  mov     rcx, rsi
0x1400a3e24  call    SkpgExtentCrc
0x1400a3e29  mov     [rbx+0C3h], al
0x1400a3e2f  add     rbx, 0F0h
0x1400a3e36  jmp     short loc_1400A3E3B
0x1400a3e38  xor     r14d, r14d
0x1400a3e3b  test    r12d, r12d
0x1400a3e3e  jz      short loc_1400A3EBD
0x1400a3e40  mov     r12d, 1015h
0x1400a3e46  mov     [rsp+78h+var_58], r14d
0x1400a3e4b  mov     r8d, r12d
0x1400a3e4e  xor     r9d, r9d
0x1400a3e51  mov     rdx, rbx
0x1400a3e54  mov     rcx, rsi
0x1400a3e57  call    SkpgInitializeExtent
0x1400a3e5c  or      dword ptr [rbx+20h], 1
0x1400a3e60  lea     rax, SkpgSecureExtension
0x1400a3e67  mov     rdx, rbx
0x1400a3e6a  mov     [rbx+18h], rax
0x1400a3e6e  mov     rcx, rsi
0x1400a3e71  call    SkpgExtentCrc
0x1400a3e76  mov     [rbx+3], al
0x1400a3e79  add     rbx, 30h ; '0'
0x1400a3e7d  cmp     cs:SkpgNtExtension, r14
0x1400a3e84  jz      short loc_1400A3EBD
0x1400a3e86  xor     r9d, r9d
0x1400a3e89  mov     [rsp+78h+var_58], r14d
0x1400a3e8e  mov     r8d, r12d
0x1400a3e91  mov     rdx, rbx
0x1400a3e94  mov     rcx, rsi
0x1400a3e97  call    SkpgInitializeExtent
0x1400a3e9c  or      dword ptr [rbx+20h], 1
0x1400a3ea0  lea     rax, SkpgNtExtension
0x1400a3ea7  mov     rdx, rbx
0x1400a3eaa  mov     [rbx+18h], rax
0x1400a3eae  mov     rcx, rsi
0x1400a3eb1  call    SkpgExtentCrc
0x1400a3eb6  mov     [rbx+3], al
0x1400a3eb9  add     rbx, 30h ; '0'
0x1400a3ebd  mov     rax, [rsp+78h+arg_18]
0x1400a3ec5  mov     [r13+0], rbx
0x1400a3ec9  mov     [r15], rdi
0x1400a3ecc  mov     [rax], ebp
0x1400a3ece  xor     eax, eax
0x1400a3ed0  jmp     short loc_1400A3ED7
0x1400a3ed2  mov     eax, 0C0000095h
0x1400a3ed7  add     rsp, 38h
0x1400a3edb  pop     r15
0x1400a3edd  pop     r14
0x1400a3edf  pop     r13
0x1400a3ee1  pop     r12
0x1400a3ee3  pop     rdi
0x1400a3ee4  pop     rsi
0x1400a3ee5  pop     rbp
0x1400a3ee6  pop     rbx
0x1400a3ee7  retn
```
