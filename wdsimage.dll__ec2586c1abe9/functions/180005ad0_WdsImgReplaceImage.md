# WdsImgReplaceImage

- ea: `0x180005ad0`
- end: `0x180005d17`
- name: `WdsImgReplaceImage`
- size: `583`
- prototype: `__int64 __fastcall(struct CImageGroup *, CImage *this, CImage *, unsigned int, unsigned int, __int64, unsigned int (*)(unsigned int, unsigned __int64, __int64, void *), void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003c68`
- `0x180003d64`
- `0x180005ad0`
- `0x1800096c0`
- `0x18000abe0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180005b79`
- `msvcrt!_wcsnicmp` at `0x180005b79`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005ce5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005ce5`
- `WdsCommonLib!GetFileNameFromPath` at `0x180005be7`
- `WdsCommonLib!GetFileNameFromPath` at `0x180005be7`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180005bfb`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180005bfb`

## pseudocode

```c
__int64 __fastcall WdsImgReplaceImage(
        struct CImageGroup *a1,
        CImage *this,
        CImage *a3,
        unsigned int a4,
        unsigned int a5,
        struct CImage **a6,
        unsigned int (*a7)(unsigned int, unsigned __int64, __int64, void *),
        void *a8)
{
  int v12; // r15d
  __int128 v13; // xmm6
  __int64 v14; // rbx
  const wchar_t *v15; // rcx
  size_t v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  const unsigned __int16 *FileNameFromPath; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  unsigned __int16 *v31; // [rsp+40h] [rbp-48h] BYREF
  struct CImage *v32; // [rsp+48h] [rbp-40h] BYREF

  v32 = 0;
  v31 = 0;
  v12 = 0;
  v13 = 0;
  if ( !a6 )
    goto LABEL_2;
  if ( (a4 & 0xFFFFFFFA) != 0 )
  {
    LODWORD(v14) = -1056833009;
    return (unsigned int)v14;
  }
  if ( !a1 )
    goto LABEL_2;
  if ( *((_DWORD *)a1 + 4) != 2 )
  {
LABEL_7:
    LODWORD(v14) = -1056833019;
    return (unsigned int)v14;
  }
  if ( !this )
    goto LABEL_2;
  if ( *((_DWORD *)this + 4) != 4 )
    goto LABEL_7;
  if ( !a3 )
  {
LABEL_2:
    LODWORD(v14) = -2147024809;
    return (unsigned int)v14;
  }
  if ( *((_DWORD *)a3 + 4) != 4 )
    goto LABEL_7;
  v15 = (const wchar_t *)*((_QWORD *)a1 + 4);
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  LODWORD(v14) = _wcsnicmp(v15, *((const wchar_t **)this + 11), v16) != 0 ? 0xC1020213 : 0;
  if ( (int)ElValidateHr_0((unsigned int)v14, v17, v18, 2134) >= 0 )
  {
    LODWORD(v14) = a5 == 256 || a5 == 257 || a5 - 258 < 2 ? 0 : -1056833008;
    if ( (int)ElValidateHr_0((unsigned int)v14, v19, v20, 2140) >= 0 )
    {
      FileNameFromPath = (const unsigned __int16 *)GetFileNameFromPath(*((_QWORD *)this + 11));
      v14 = DuplicateStringW(FileNameFromPath, &v31);
      if ( (unsigned int)ElValidateWin32(v14, v22, v23, 2147) )
      {
        if ( (int)v14 > 0 )
          LODWORD(v14) = (unsigned __int16)v14 | 0x80070000;
        goto LABEL_32;
      }
      if ( !*((_DWORD *)this + 12) )
      {
LABEL_27:
        LODWORD(v14) = CImage::Delete(this, 0);
        if ( (int)ElValidateHr_0((unsigned int)v14, v26, v27, 2166) >= 0 )
        {
          if ( v12 )
          {
            *((_DWORD *)a3 + 17) = 1;
            *(_OWORD *)((char *)a3 + 72) = v13;
          }
          LODWORD(v14) = CImage::Import(a3, a1, v31, a4, a5, a7, a8, &v32);
          if ( (int)ElValidateHr_0((unsigned int)v14, v28, v29, 2187) >= 0 )
            *a6 = v32;
        }
        goto LABEL_32;
      }
      v13 = *(_OWORD *)((char *)this + 52);
      LODWORD(v14) = 0;
      if ( (int)ElValidateHr_0(0, v24, v25, 2156) >= 0 )
      {
        v12 = 1;
        goto LABEL_27;
      }
    }
  }
LABEL_32:
  if ( v31 )
    operator delete(v31);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180005ad0  mov     r11, rsp
0x180005ad3  mov     [r11+8], rbx
0x180005ad7  mov     [r11+10h], rbp
0x180005adb  mov     [r11+18h], rsi
0x180005adf  push    rdi
0x180005ae0  push    r12
0x180005ae2  push    r13
0x180005ae4  push    r14
0x180005ae6  push    r15
0x180005ae8  sub     rsp, 60h
0x180005aec  mov     r12, [rsp+88h+arg_28]
0x180005af4  xor     eax, eax
0x180005af6  movaps  [rsp+88h+var_38], xmm6
0x180005afb  mov     r13d, r9d
0x180005afe  mov     [r11-40h], rax
0x180005b02  mov     rsi, r8
0x180005b05  mov     [r11-48h], rax
0x180005b09  mov     rdi, rdx
0x180005b0c  mov     rbp, rcx
0x180005b0f  mov     r15d, eax
0x180005b12  xorps   xmm6, xmm6
0x180005b15  test    r12, r12
0x180005b18  jnz     short loc_180005B24
0x180005b1a  mov     ebx, 80070057h
0x180005b1f  jmp     loc_180005CF1
0x180005b24  test    r13d, 0FFFFFFFAh
0x180005b2b  jz      short loc_180005B37
0x180005b2d  mov     ebx, 0C102020Fh
0x180005b32  jmp     loc_180005CF1
0x180005b37  test    rbp, rbp
0x180005b3a  jz      short loc_180005B1A
0x180005b3c  cmp     dword ptr [rcx+10h], 2
0x180005b40  jz      short loc_180005B4C
0x180005b42  mov     ebx, 0C1020205h
0x180005b47  jmp     loc_180005CF1
0x180005b4c  test    rdi, rdi
0x180005b4f  jz      short loc_180005B1A
0x180005b51  cmp     dword ptr [rdx+10h], 4
0x180005b55  jnz     short loc_180005B42
0x180005b57  test    rsi, rsi
0x180005b5a  jz      short loc_180005B1A
0x180005b5c  cmp     dword ptr [r8+10h], 4
0x180005b61  jnz     short loc_180005B42
0x180005b63  mov     rcx, [rcx+20h]; String1
0x180005b67  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005b6b  inc     r8; MaxCount
0x180005b6e  cmp     [rcx+r8*2], ax
0x180005b73  jnz     short loc_180005B6B
0x180005b75  mov     rdx, [rdx+58h]; String2
0x180005b79  call    cs:__imp__wcsnicmp
0x180005b80  nop     dword ptr [rax+rax+00h]
0x180005b85  neg     eax
0x180005b87  mov     r9d, 856h
0x180005b8d  sbb     ebx, ebx
0x180005b8f  and     ebx, 0C1020213h
0x180005b95  mov     ecx, ebx
0x180005b97  call    ElValidateHr_0
0x180005b9c  test    eax, eax
0x180005b9e  js      loc_180005CDB
0x180005ba4  mov     r14d, [rsp+88h+arg_20]
0x180005bac  mov     eax, r14d
0x180005baf  sub     eax, 100h
0x180005bb4  jz      short loc_180005BCC
0x180005bb6  sub     eax, 1
0x180005bb9  jz      short loc_180005BCC
0x180005bbb  sub     eax, 1
0x180005bbe  jz      short loc_180005BCC
0x180005bc0  cmp     eax, 1
0x180005bc3  jz      short loc_180005BCC
0x180005bc5  mov     ebx, 0C1020210h
0x180005bca  jmp     short loc_180005BCE
0x180005bcc  xor     ebx, ebx
0x180005bce  mov     r9d, 85Ch
0x180005bd4  mov     ecx, ebx
0x180005bd6  call    ElValidateHr_0
0x180005bdb  test    eax, eax
0x180005bdd  js      loc_180005CDB
0x180005be3  mov     rcx, [rdi+58h]
0x180005be7  call    cs:__imp_GetFileNameFromPath
0x180005bee  nop     dword ptr [rax+rax+00h]
0x180005bf3  mov     rcx, rax
0x180005bf6  lea     rdx, [rsp+88h+var_48]
0x180005bfb  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180005c02  nop     dword ptr [rax+rax+00h]
0x180005c07  mov     ecx, eax
0x180005c09  mov     r9d, 863h
0x180005c0f  mov     ebx, eax
0x180005c11  call    ElValidateWin32
0x180005c16  test    eax, eax
0x180005c18  jz      short loc_180005C30
0x180005c1a  test    ebx, ebx
0x180005c1c  jle     loc_180005CDB
0x180005c22  movzx   ebx, bx
0x180005c25  or      ebx, 80070000h
0x180005c2b  jmp     loc_180005CDB
0x180005c30  cmp     [rdi+30h], r15d
0x180005c34  jz      short loc_180005C55
0x180005c36  movups  xmm6, xmmword ptr [rdi+34h]
0x180005c3a  xor     ecx, ecx
0x180005c3c  mov     r9d, 86Ch
0x180005c42  xor     ebx, ebx
0x180005c44  call    ElValidateHr_0
0x180005c49  test    eax, eax
0x180005c4b  js      loc_180005CDB
0x180005c51  lea     r15d, [rbx+1]
0x180005c55  xor     edx, edx; int
0x180005c57  mov     rcx, rdi; this
0x180005c5a  call    ?Delete@CImage@@QEAAJH@Z; CImage::Delete(int)
0x180005c5f  mov     r9d, 876h
0x180005c65  mov     ecx, eax
0x180005c67  mov     ebx, eax
0x180005c69  call    ElValidateHr_0
0x180005c6e  test    eax, eax
0x180005c70  js      short loc_180005CDB
0x180005c72  test    r15d, r15d
0x180005c75  jz      short loc_180005C83
0x180005c77  mov     dword ptr [rsi+44h], 1
0x180005c7e  movdqu  xmmword ptr [rsi+48h], xmm6
0x180005c83  mov     r8, [rsp+88h+var_48]; unsigned __int16 *
0x180005c88  lea     rax, [rsp+88h+var_40]
0x180005c8d  mov     [rsp+88h+var_50], rax; struct CImage **
0x180005c92  mov     r9d, r13d; unsigned int
0x180005c95  mov     rax, [rsp+88h+arg_38]
0x180005c9d  mov     rdx, rbp; struct CImageGroup *
0x180005ca0  mov     [rsp+88h+var_58], rax; void *
0x180005ca5  mov     rcx, rsi; this
0x180005ca8  mov     rax, [rsp+88h+arg_30]
0x180005cb0  mov     [rsp+88h+var_60], rax; unsigned int (*)(unsigned int, unsigned __int64, __int64, void *)
0x180005cb5  mov     [rsp+88h+var_68], r14d; unsigned int
0x180005cba  call    ?Import@CImage@@QEAAJPEAVCImageGroup@@PEBGKKP6AKK_K_JPEAX@Z4PEAPEAV1@@Z; CImage::Import(CImageGroup *,ushort const *,ulong,ulong,ulong (*)(ulong,unsigned __int64,__int64,void *),void *,CImage * *)
0x180005cbf  mov     r9d, 88Bh
0x180005cc5  mov     ecx, eax
0x180005cc7  mov     ebx, eax
0x180005cc9  call    ElValidateHr_0
0x180005cce  test    eax, eax
0x180005cd0  js      short loc_180005CDB
0x180005cd2  mov     rax, [rsp+88h+var_40]
0x180005cd7  mov     [r12], rax
0x180005cdb  mov     rcx, [rsp+88h+var_48]
0x180005ce0  test    rcx, rcx
0x180005ce3  jz      short loc_180005CF1
0x180005ce5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005cec  nop     dword ptr [rax+rax+00h]
0x180005cf1  movaps  xmm6, [rsp+88h+var_38]
0x180005cf6  lea     r11, [rsp+88h+var_28]
0x180005cfb  mov     rbp, [r11+38h]
0x180005cff  mov     eax, ebx
0x180005d01  mov     rbx, [r11+30h]
0x180005d05  mov     rsi, [r11+40h]
0x180005d09  mov     rsp, r11
0x180005d0c  pop     r15
0x180005d0e  pop     r14
0x180005d10  pop     r13
0x180005d12  pop     r12
0x180005d14  pop     rdi
0x180005d15  retn
```
