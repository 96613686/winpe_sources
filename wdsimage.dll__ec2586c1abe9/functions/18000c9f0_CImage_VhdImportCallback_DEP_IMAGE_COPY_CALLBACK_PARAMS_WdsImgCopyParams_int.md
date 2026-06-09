# CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)

- ea: `0x18000c9f0`
- end: `0x18000cdf7`
- name: `?VhdImportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z`
- size: `1031`
- prototype: `__int64 __fastcall(CImage *__hidden this, struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *, struct WdsImgCopyParams *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000d1f0`

## callees

- `0x18000c9f0`
- `0x18000d5b0`
- `0x18000d6b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cce8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd03`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cce8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd03`
- `KERNEL32!GetFileAttributesW` at `0x18000cccf`
- `KERNEL32!GetFileAttributesW` at `0x18000cccf`
- `WdsCommonLib!WdsAppendSuffixToFileName` at `0x18000cc78`
- `WdsCommonLib!WdsAppendSuffixToFileName` at `0x18000cc78`
- `WdsCommonLib!ConcatenatePaths` at `0x18000cca9`
- `WdsCommonLib!ConcatenatePaths` at `0x18000cca9`
- `WdsCommonLib!WdsIdnCompareFilePaths` at `0x18000cb5c`
- `WdsCommonLib!WdsIdnCompareFilePaths` at `0x18000cb5c`
- `WdsCommonLib!GetFileNameFromPath` at `0x18000cb44`
- `WdsCommonLib!GetFileNameFromPath` at `0x18000cbc6`
- `WdsCommonLib!GetFileNameFromPath` at `0x18000cb44`
- `WdsCommonLib!GetFileNameFromPath` at `0x18000cbc6`

## pseudocode

```c
__int64 __fastcall CImage::VhdImportCallback(
        CImage *this,
        struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *a2,
        struct WdsImgCopyParams *a3,
        int *a4)
{
  int v4; // r12d
  __int64 v9; // rbx
  const wchar_t *v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rdx
  _WORD *v13; // r8
  __int64 v14; // r9
  __int16 v15; // ax
  _WORD *v16; // rax
  __int64 v17; // rax
  unsigned int v18; // esi
  __int64 v19; // rbp
  __int64 FileNameFromPath; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rdx
  _WORD *v27; // r9
  __int64 v28; // r10
  __int16 v29; // ax
  _WORD *v30; // rax
  void **v31; // rsi
  __int64 v32; // rdx
  __int64 v33; // r8
  LPCWSTR *v34; // r15
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rdx
  _WORD *v40; // r8
  signed __int64 v41; // r9
  __int16 v42; // ax
  _WORD *v43; // rax
  int v45; // [rsp+60h] [rbp+18h] BYREF

  v4 = 0;
  LODWORD(v9) = 0;
  v10 = 0;
  if ( *((_DWORD *)a3 + 8) )
  {
    LODWORD(v9) = -2147023673;
    if ( (int)ElValidateHr_5(2147943623LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2528) < 0 )
      return (unsigned int)v9;
  }
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v10 = L"Base.VHD";
  }
  else if ( *((_DWORD *)this + 7) == 3 )
  {
    v10 = L"Base.VHDX";
  }
  else
  {
    LODWORD(v9) = -2147024883;
    if ( (int)ElValidateHr_5(2147942413LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2547) < 0 )
      return (unsigned int)v9;
  }
  *a4 = 0;
  if ( (*(_BYTE *)a2 & 1) != 0 )
  {
    v11 = *((_QWORD *)a2 + 5);
    v12 = 2147483646;
    v13 = (_WORD *)*((_QWORD *)a2 + 4);
    if ( (unsigned __int64)(v11 - 1) > 0x7FFFFFFE )
    {
      LODWORD(v9) = -2147024809;
      if ( v11 )
        *v13 = 0;
    }
    else
    {
      v12 = 2147483646 - v11;
      v14 = *((_QWORD *)a3 + 2) - (_QWORD)v13;
      do
      {
        if ( !(v12 + v11) )
          break;
        v15 = *(_WORD *)((char *)v13 + v14);
        if ( !v15 )
          break;
        *v13++ = v15;
        --v11;
      }
      while ( v11 );
      v16 = v13 - 1;
      if ( v11 )
        v16 = v13;
      LODWORD(v9) = v11 == 0 ? 0x8007007A : 0;
      *v16 = 0;
    }
    ElValidateHr_5((unsigned int)v9, v12, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2567);
    return (unsigned int)v9;
  }
  if ( *(_DWORD *)a2 )
    return (unsigned int)v9;
  v17 = *((_QWORD *)a3 + 8);
  v18 = 0;
  if ( *(_DWORD *)(v17 + 12) )
  {
    while ( 1 )
    {
      v45 = 0;
      v19 = 0;
      if ( v18 < *(_DWORD *)(v17 + 12) )
        v19 = *(_QWORD *)(*(_QWORD *)v17 + 8LL * v18);
      FileNameFromPath = GetFileNameFromPath(*(_QWORD *)(v19 + 16));
      v9 = (unsigned int)WdsIdnCompareFilePaths(FileNameFromPath, *((_QWORD *)a2 + 2), &v45);
      if ( (unsigned int)ElValidateWin32_4(v9, v21, v22, 2583) )
        break;
      if ( !v45 )
        goto LABEL_28;
      v17 = *((_QWORD *)a3 + 8);
      if ( ++v18 >= *(_DWORD *)(v17 + 12) )
        goto LABEL_27;
    }
  }
  else
  {
LABEL_27:
    LODWORD(v9) = -2147024894;
    v19 = 0;
    if ( (int)ElValidateHr_5(2147942402LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2597) < 0 )
      return (unsigned int)v9;
LABEL_28:
    v23 = *(_QWORD *)(v19 + 24);
    if ( v23 )
    {
      v24 = GetFileNameFromPath(*(_QWORD *)(v23 + 88));
      v25 = *((_QWORD *)a2 + 5);
      v26 = 2147483646;
      v27 = (_WORD *)*((_QWORD *)a2 + 4);
      if ( (unsigned __int64)(v25 - 1) > 0x7FFFFFFE )
      {
        LODWORD(v9) = -2147024809;
        if ( v25 )
          *v27 = 0;
      }
      else
      {
        v26 = 2147483646 - v25;
        v28 = v24 - (_QWORD)v27;
        do
        {
          if ( !(v26 + v25) )
            break;
          v29 = *(_WORD *)((char *)v27 + v28);
          if ( !v29 )
            break;
          *v27++ = v29;
          --v25;
        }
        while ( v25 );
        v30 = v27 - 1;
        if ( v25 )
          v30 = v27;
        LODWORD(v9) = v25 == 0 ? 0x8007007A : 0;
        *v30 = 0;
      }
      if ( (int)ElValidateHr_5((unsigned int)v9, v26, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2619) >= 0 )
        *a4 = 1;
      return (unsigned int)v9;
    }
    v31 = (void **)(v19 + 32);
    while ( 1 )
    {
      LODWORD(v9) = WdsAppendSuffixToFileName(v10, (unsigned int)++*((_DWORD *)a3 + 15), v19 + 32);
      if ( (unsigned int)ElValidateWin32_4((unsigned int)v9, v32, v33, 2634) )
        break;
      v34 = (LPCWSTR *)(v19 + 40);
      v9 = (unsigned int)ConcatenatePaths(*((_QWORD *)a3 + 1), *v31, v19 + 40);
      if ( (unsigned int)ElValidateWin32_4(v9, v35, v36, 2640) )
        break;
      if ( GetFileAttributesW(*v34) == -1 )
        goto LABEL_51;
      if ( *v34 )
      {
        operator delete((void *)*v34);
        *v34 = 0;
      }
      if ( *v31 )
      {
        operator delete(*v31);
        *v31 = 0;
      }
      if ( (unsigned int)++v4 >= 0xFF )
      {
        LODWORD(v9) = -2147024865;
        if ( (int)ElValidateHr_5(2147942431LL, v37, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2659) < 0 )
          return (unsigned int)v9;
LABEL_51:
        v38 = *((_QWORD *)a2 + 5);
        v39 = 2147483646;
        v40 = (_WORD *)*((_QWORD *)a2 + 4);
        if ( (unsigned __int64)(v38 - 1) > 0x7FFFFFFE )
        {
          LODWORD(v9) = -2147024809;
          if ( v38 )
            *v40 = 0;
        }
        else
        {
          v39 = 2147483646 - v38;
          v41 = (_BYTE *)*v31 - (_BYTE *)v40;
          do
          {
            if ( !(v39 + v38) )
              break;
            v42 = *(_WORD *)((char *)v40 + v41);
            if ( !v42 )
              break;
            *v40++ = v42;
            --v38;
          }
          while ( v38 );
          v43 = v40 - 1;
          if ( v38 )
            v43 = v40;
          LODWORD(v9) = v38 == 0 ? 0x8007007A : 0;
          *v43 = 0;
        }
        ElValidateHr_5((unsigned int)v9, v39, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2669);
        return (unsigned int)v9;
      }
    }
  }
  if ( (int)v9 > 0 )
    LODWORD(v9) = (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c9f0  mov     [rsp+arg_0], rbx
0x18000c9f5  mov     [rsp+arg_8], rbp
0x18000c9fa  mov     [rsp+arg_18], rsi
0x18000c9ff  push    rdi
0x18000ca00  push    r12
0x18000ca02  push    r13
0x18000ca04  push    r14
0x18000ca06  push    r15
0x18000ca08  sub     rsp, 20h
0x18000ca0c  xor     r12d, r12d
0x18000ca0f  lea     rbp, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000ca16  mov     r15, r9
0x18000ca19  mov     r14, r8
0x18000ca1c  mov     rdi, rdx
0x18000ca1f  mov     rsi, rcx
0x18000ca22  mov     ebx, r12d
0x18000ca25  mov     r13d, r12d
0x18000ca28  cmp     [r8+20h], r12d
0x18000ca2c  jz      short loc_18000CA4B
0x18000ca2e  mov     ebx, 800704C7h
0x18000ca33  mov     r9d, 9E0h
0x18000ca39  mov     ecx, ebx
0x18000ca3b  mov     r8, rbp
0x18000ca3e  call    ElValidateHr_5
0x18000ca43  test    eax, eax
0x18000ca45  js      loc_18000CDD7
0x18000ca4b  cmp     dword ptr [rsi+1Ch], 1
0x18000ca4f  jnz     short loc_18000CA5A
0x18000ca51  lea     r13, aBaseVhd; "Base.VHD"
0x18000ca58  jmp     short loc_18000CA86
0x18000ca5a  cmp     dword ptr [rsi+1Ch], 3
0x18000ca5e  jnz     short loc_18000CA69
0x18000ca60  lea     r13, aBaseVhdx; "Base.VHDX"
0x18000ca67  jmp     short loc_18000CA86
0x18000ca69  mov     ebx, 8007000Dh
0x18000ca6e  mov     r9d, 9F3h
0x18000ca74  mov     ecx, ebx
0x18000ca76  mov     r8, rbp
0x18000ca79  call    ElValidateHr_5
0x18000ca7e  test    eax, eax
0x18000ca80  js      loc_18000CDD7
0x18000ca86  mov     [r15], r12d
0x18000ca89  test    byte ptr [rdi], 1
0x18000ca8c  jz      loc_18000CB14
0x18000ca92  mov     rcx, [rdi+28h]
0x18000ca96  mov     edx, 7FFFFFFEh
0x18000ca9b  mov     r9, [r14+10h]
0x18000ca9f  mov     r8, [rdi+20h]
0x18000caa3  lea     rax, [rcx-1]
0x18000caa7  cmp     rax, rdx
0x18000caaa  ja      short loc_18000CAF1
0x18000caac  sub     rdx, rcx
0x18000caaf  sub     r9, r8
0x18000cab2  lea     rax, [rdx+rcx]
0x18000cab6  test    rax, rax
0x18000cab9  jz      short loc_18000CAD3
0x18000cabb  movzx   eax, word ptr [r9+r8]
0x18000cac0  test    ax, ax
0x18000cac3  jz      short loc_18000CAD3
0x18000cac5  mov     [r8], ax
0x18000cac9  add     r8, 2
0x18000cacd  sub     rcx, 1
0x18000cad1  jnz     short loc_18000CAB2
0x18000cad3  test    rcx, rcx
0x18000cad6  lea     rax, [r8-2]
0x18000cada  cmovnz  rax, r8
0x18000cade  neg     rcx
0x18000cae1  sbb     ebx, ebx
0x18000cae3  not     ebx
0x18000cae5  and     ebx, 8007007Ah
0x18000caeb  mov     [rax], r12w
0x18000caef  jmp     short loc_18000CAFF
0x18000caf1  mov     ebx, 80070057h
0x18000caf6  test    rcx, rcx
0x18000caf9  jz      short loc_18000CAFF
0x18000cafb  mov     [r8], r12w
0x18000caff  mov     r9d, 0A07h
0x18000cb05  mov     r8, rbp
0x18000cb08  mov     ecx, ebx
0x18000cb0a  call    ElValidateHr_5
0x18000cb0f  jmp     loc_18000CDD7
0x18000cb14  cmp     [rdi], r12d
0x18000cb17  jnz     loc_18000CDD7
0x18000cb1d  mov     rax, [r14+40h]
0x18000cb21  mov     esi, r12d
0x18000cb24  cmp     [rax+0Ch], r12d
0x18000cb28  jbe     short loc_18000CB91
0x18000cb2a  mov     [rsp+48h+arg_10], r12d
0x18000cb2f  mov     rbp, r12
0x18000cb32  cmp     esi, [rax+0Ch]
0x18000cb35  jnb     short loc_18000CB40
0x18000cb37  mov     rax, [rax]
0x18000cb3a  mov     ecx, esi
0x18000cb3c  mov     rbp, [rax+rcx*8]
0x18000cb40  mov     rcx, [rbp+10h]
0x18000cb44  call    cs:__imp_GetFileNameFromPath
0x18000cb4b  nop     dword ptr [rax+rax+00h]
0x18000cb50  mov     rdx, [rdi+10h]
0x18000cb54  lea     r8, [rsp+48h+arg_10]
0x18000cb59  mov     rcx, rax
0x18000cb5c  call    cs:__imp_WdsIdnCompareFilePaths
0x18000cb63  nop     dword ptr [rax+rax+00h]
0x18000cb68  mov     ecx, eax
0x18000cb6a  mov     r9d, 0A17h
0x18000cb70  mov     ebx, eax
0x18000cb72  call    ElValidateWin32_4
0x18000cb77  test    eax, eax
0x18000cb79  jnz     loc_18000CDCA
0x18000cb7f  cmp     [rsp+48h+arg_10], r12d
0x18000cb84  jz      short loc_18000CBB5
0x18000cb86  mov     rax, [r14+40h]
0x18000cb8a  inc     esi
0x18000cb8c  cmp     esi, [rax+0Ch]
0x18000cb8f  jb      short loc_18000CB2A
0x18000cb91  mov     ebx, 80070002h
0x18000cb96  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000cb9d  mov     ecx, ebx
0x18000cb9f  mov     r9d, 0A25h
0x18000cba5  mov     rbp, r12
0x18000cba8  call    ElValidateHr_5
0x18000cbad  test    eax, eax
0x18000cbaf  js      loc_18000CDD7
0x18000cbb5  mov     rcx, [rbp+18h]
0x18000cbb9  test    rcx, rcx
0x18000cbbc  jz      loc_18000CC66
0x18000cbc2  mov     rcx, [rcx+58h]
0x18000cbc6  call    cs:__imp_GetFileNameFromPath
0x18000cbcd  nop     dword ptr [rax+rax+00h]
0x18000cbd2  mov     r8, [rdi+28h]
0x18000cbd6  mov     edx, 7FFFFFFEh
0x18000cbdb  mov     r9, [rdi+20h]
0x18000cbdf  mov     r10, rax
0x18000cbe2  lea     rcx, [r8-1]
0x18000cbe6  cmp     rcx, rdx
0x18000cbe9  ja      short loc_18000CC30
0x18000cbeb  sub     rdx, r8
0x18000cbee  sub     r10, r9
0x18000cbf1  lea     rax, [rdx+r8]
0x18000cbf5  test    rax, rax
0x18000cbf8  jz      short loc_18000CC12
0x18000cbfa  movzx   eax, word ptr [r10+r9]
0x18000cbff  test    ax, ax
0x18000cc02  jz      short loc_18000CC12
0x18000cc04  mov     [r9], ax
0x18000cc08  add     r9, 2
0x18000cc0c  sub     r8, 1
0x18000cc10  jnz     short loc_18000CBF1
0x18000cc12  test    r8, r8
0x18000cc15  lea     rax, [r9-2]
0x18000cc19  cmovnz  rax, r9
0x18000cc1d  neg     r8
0x18000cc20  sbb     ebx, ebx
0x18000cc22  not     ebx
0x18000cc24  and     ebx, 8007007Ah
0x18000cc2a  mov     [rax], r12w
0x18000cc2e  jmp     short loc_18000CC3E
0x18000cc30  mov     ebx, 80070057h
0x18000cc35  test    r8, r8
0x18000cc38  jz      short loc_18000CC3E
0x18000cc3a  mov     [r9], r12w
0x18000cc3e  mov     r9d, 0A3Bh
0x18000cc44  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000cc4b  mov     ecx, ebx
0x18000cc4d  call    ElValidateHr_5
0x18000cc52  test    eax, eax
0x18000cc54  js      loc_18000CDD7
0x18000cc5a  mov     dword ptr [r15], 1
0x18000cc61  jmp     loc_18000CDD7
0x18000cc66  lea     rsi, [rbp+20h]
0x18000cc6a  inc     dword ptr [r14+3Ch]
0x18000cc6e  mov     r8, rsi
0x18000cc71  mov     edx, [r14+3Ch]
0x18000cc75  mov     rcx, r13
0x18000cc78  call    cs:__imp_WdsAppendSuffixToFileName
0x18000cc7f  nop     dword ptr [rax+rax+00h]
0x18000cc84  mov     ecx, eax
0x18000cc86  mov     r9d, 0A4Ah
0x18000cc8c  mov     ebx, eax
0x18000cc8e  call    ElValidateWin32_4
0x18000cc93  test    eax, eax
0x18000cc95  jnz     loc_18000CDCA
0x18000cc9b  mov     rdx, [rsi]
0x18000cc9e  lea     r15, [rbp+28h]
0x18000cca2  mov     rcx, [r14+8]
0x18000cca6  mov     r8, r15
0x18000cca9  call    cs:__imp_ConcatenatePaths
0x18000ccb0  nop     dword ptr [rax+rax+00h]
0x18000ccb5  mov     ecx, eax
0x18000ccb7  mov     r9d, 0A50h
0x18000ccbd  mov     ebx, eax
0x18000ccbf  call    ElValidateWin32_4
0x18000ccc4  test    eax, eax
0x18000ccc6  jnz     loc_18000CDCA
0x18000cccc  mov     rcx, [r15]; lpFileName
0x18000cccf  call    cs:__imp_GetFileAttributesW
0x18000ccd6  nop     dword ptr [rax+rax+00h]
0x18000ccdb  cmp     eax, 0FFFFFFFFh
0x18000ccde  jz      short loc_18000CD45
0x18000cce0  mov     rcx, [r15]
0x18000cce3  test    rcx, rcx
0x18000cce6  jz      short loc_18000CCF8
0x18000cce8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ccef  nop     dword ptr [rax+rax+00h]
0x18000ccf4  and     qword ptr [r15], 0
0x18000ccf8  mov     rcx, [rsi]
0x18000ccfb  xor     r15d, r15d
0x18000ccfe  test    rcx, rcx
0x18000cd01  jz      short loc_18000CD12
0x18000cd03  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cd0a  nop     dword ptr [rax+rax+00h]
0x18000cd0f  mov     [rsi], r15
0x18000cd12  inc     r12d
0x18000cd15  cmp     r12d, 0FFh
0x18000cd1c  jb      loc_18000CC6A
0x18000cd22  mov     ebx, 8007001Fh
0x18000cd27  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000cd2e  mov     ecx, ebx
0x18000cd30  mov     r9d, 0A63h
0x18000cd36  call    ElValidateHr_5
0x18000cd3b  test    eax, eax
0x18000cd3d  js      loc_18000CDD7
0x18000cd43  jmp     short loc_18000CD48
0x18000cd45  xor     r15d, r15d
0x18000cd48  mov     rcx, [rdi+28h]
0x18000cd4c  mov     edx, 7FFFFFFEh
0x18000cd51  mov     r9, [rsi]
0x18000cd54  mov     r8, [rdi+20h]
0x18000cd58  lea     rax, [rcx-1]
0x18000cd5c  cmp     rax, rdx
0x18000cd5f  ja      short loc_18000CDA6
0x18000cd61  sub     rdx, rcx
0x18000cd64  sub     r9, r8
0x18000cd67  lea     rax, [rdx+rcx]
0x18000cd6b  test    rax, rax
0x18000cd6e  jz      short loc_18000CD88
0x18000cd70  movzx   eax, word ptr [r9+r8]
0x18000cd75  test    ax, ax
0x18000cd78  jz      short loc_18000CD88
0x18000cd7a  mov     [r8], ax
0x18000cd7e  add     r8, 2
0x18000cd82  sub     rcx, 1
0x18000cd86  jnz     short loc_18000CD67
0x18000cd88  test    rcx, rcx
0x18000cd8b  lea     rax, [r8-2]
0x18000cd8f  cmovnz  rax, r8
0x18000cd93  neg     rcx
0x18000cd96  sbb     ebx, ebx
0x18000cd98  not     ebx
0x18000cd9a  and     ebx, 8007007Ah
0x18000cda0  mov     [rax], r15w
0x18000cda4  jmp     short loc_18000CDB4
0x18000cda6  mov     ebx, 80070057h
0x18000cdab  test    rcx, rcx
0x18000cdae  jz      short loc_18000CDB4
0x18000cdb0  mov     [r8], r15w
0x18000cdb4  mov     r9d, 0A6Dh
0x18000cdba  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000cdc1  mov     ecx, ebx
0x18000cdc3  call    ElValidateHr_5
0x18000cdc8  jmp     short loc_18000CDD7
0x18000cdca  test    ebx, ebx
0x18000cdcc  jle     short loc_18000CDD7
0x18000cdce  movzx   ebx, bx
0x18000cdd1  or      ebx, 80070000h
0x18000cdd7  mov     rbp, [rsp+48h+arg_8]
0x18000cddc  mov     eax, ebx
0x18000cdde  mov     rbx, [rsp+48h+arg_0]
0x18000cde3  mov     rsi, [rsp+48h+arg_18]
0x18000cde8  add     rsp, 20h
0x18000cdec  pop     r15
0x18000cdee  pop     r14
0x18000cdf0  pop     r13
0x18000cdf2  pop     r12
0x18000cdf4  pop     rdi
0x18000cdf5  retn
```
