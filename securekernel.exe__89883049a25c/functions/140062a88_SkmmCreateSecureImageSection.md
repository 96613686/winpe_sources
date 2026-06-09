# SkmmCreateSecureImageSection

- ea: `0x140062a88`
- end: `0x1400631c5`
- name: `SkmmCreateSecureImageSection`
- size: `1853`
- prototype: `__int64 __fastcall(__int64, ULONG_PTR, char, unsigned int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task`

## callers

- `0x140014dd0`

## callees

- `0x140002ef0`
- `0x14000f0f0`
- `0x140012750`
- `0x140037e68`
- `0x140050634`
- `0x14006177c`
- `0x140062a88`
- `0x14007148c`
- `0x140087d14`
- `0x140087d88`
- `0x1400a0df8`
- `0x1400a18a0`
- `0x1400d64dc`
- `0x1400d7280`
- `0x1400f9780`
- `0x1400f9a80`

## import_xrefs

- `skci!SkciCreateSecureImage` at `0x140062c23`
- `skci!SkciCreateSecureImage` at `0x140062c23`
- `skci!SkciFreeImageContext` at `0x140063160`
- `skci!SkciFreeImageContext` at `0x140063160`

## pseudocode

```c
__int64 __fastcall SkmmCreateSecureImageSection(__int64 a1, ULONG_PTR a2, char a3, unsigned int a4, int a5, _QWORD *a6)
{
  unsigned int *v8; // rbx
  unsigned int v9; // esi
  __int64 result; // rax
  ULONG_PTR v11; // rdi
  size_t v12; // r14
  void *Pool; // rax
  void *v14; // r15
  int Handle; // edi
  __int64 v16; // rdx
  unsigned __int64 j; // r8
  __int64 v18; // rsi
  __int64 v19; // rcx
  __int16 v20; // ax
  size_t v21; // rax
  unsigned int v22; // ecx
  int v23; // eax
  unsigned int v24; // edx
  int v25; // r8d
  unsigned int *v26; // rdx
  int v27; // r12d
  unsigned int v28; // r13d
  void *v29; // rax
  __int64 v30; // r9
  unsigned int v31; // ecx
  __int64 i; // r14
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // ecx
  int v36; // eax
  int v37; // eax
  unsigned int v38; // eax
  unsigned int *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  _OWORD *v44; // rax
  unsigned __int64 v45; // r10
  unsigned __int64 v46; // r11
  unsigned int v47; // eax
  void *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdx
  unsigned int v51; // [rsp+34h] [rbp-55h] BYREF
  ULONG_PTR v52; // [rsp+38h] [rbp-51h] BYREF
  __int64 v53; // [rsp+40h] [rbp-49h] BYREF
  void *v54; // [rsp+48h] [rbp-41h] BYREF
  __int64 v55; // [rsp+50h] [rbp-39h] BYREF
  ULONG_PTR v56; // [rsp+58h] [rbp-31h]
  __int64 v57; // [rsp+60h] [rbp-29h] BYREF
  int v58; // [rsp+68h] [rbp-21h]
  int v59; // [rsp+6Ch] [rbp-1Dh]
  int v60; // [rsp+70h] [rbp-19h]
  __int128 v61; // [rsp+74h] [rbp-15h]
  int v62; // [rsp+84h] [rbp-5h]

  v57 = 0;
  v55 = 0;
  v8 = 0;
  v54 = 0;
  v51 = 0;
  v61 = 0;
  v9 = 0;
  v52 = 0;
  v53 = 0;
  result = SkmmMapDataTransfer(a1, a2, 1u, &v52, 0);
  if ( (int)result < 0 )
    return result;
  v11 = v52;
  v56 = v52;
  v12 = *(unsigned int *)(v52 + 40);
  Pool = (void *)SkAllocatePool(1, v12, 1348955465);
  v14 = Pool;
  if ( Pool )
  {
    memmove(Pool, *(const void **)(v11 + 24), v12);
    SkmmUnmapDataTransfer(v11);
    v56 = 0;
    Handle = RtlImageNtHeaderEx(0, v14, v12, &v55);
    if ( Handle < 0 )
      goto LABEL_89;
    v18 = v55;
    Handle = -1073741701;
    if ( v55 - (__int64)v14 + 136 > v12 )
    {
      v19 = 7;
LABEL_87:
      SKMI_BAD_IMAGE(v19, v16, j);
      goto LABEL_88;
    }
    v20 = *(_WORD *)(v55 + 24);
    if ( v20 == 523 )
    {
      if ( *(_WORD *)(v55 + 4) == 0x8664 )
      {
        LODWORD(v52) = 0;
        goto LABEL_13;
      }
    }
    else if ( v20 == 267 && *(_WORD *)(v55 + 4) == 332 )
    {
      LODWORD(v52) = 1;
LABEL_13:
      if ( v55 + 8 * (unsigned __int64)*(unsigned int *)(v55 + 132) + 136 - (unsigned __int64)v14 > v12 )
      {
        v19 = 8;
        goto LABEL_87;
      }
      v21 = *(unsigned int *)(v55 + 84);
      if ( !(_DWORD)v21 || v21 > v12 )
      {
        v19 = 9;
        goto LABEL_87;
      }
      v22 = *(_DWORD *)(v55 + 56);
      if ( v22 < 0x1000 || ((v22 - 1) & v22) != 0 )
      {
        v19 = 10;
        goto LABEL_87;
      }
      LOBYTE(j) = a3;
      Handle = SkciCreateSecureImage(v14, v12, j, a4, a5, &v53);
      if ( Handle < 0 )
      {
LABEL_88:
        v9 = 0;
        goto LABEL_89;
      }
      Handle = SkmmAllocateSparseTableEntry(&SkmiImageTable, &v51);
      if ( Handle < 0
        || (v23 = SkobCreateObjectEx(0, &SkmiImageType, 0, &v54), v8 = (unsigned int *)v54, Handle = v23, v23 < 0) )
      {
        v9 = v51;
        goto LABEL_89;
      }
      memset_0(v54, 0, 0xF8u);
      v24 = v51;
      v25 = v52;
      *(_QWORD *)(SkmiImageTable + 8LL * v51) = v8;
      v8[18] = v24;
      v26 = 0;
      *((_QWORD *)v8 + 14) = 0;
      v8[30] = 0;
      v8[31] = -1;
      *v8 = (v25 << 14) | *v8 & 0xFFFFBFFF | 1;
      if ( v25 )
      {
        v27 = 4;
        v28 = *(_DWORD *)(v18 + 116);
        *((_QWORD *)v8 + 6) = *(unsigned int *)(v18 + 52);
        v8[45] = *(_DWORD *)(v18 + 88);
        if ( v28 > 0xC )
          v26 = (unsigned int *)(v18 + 216);
      }
      else
      {
        v27 = 8;
        v28 = *(_DWORD *)(v18 + 132);
        *((_QWORD *)v8 + 6) = *(_QWORD *)(v18 + 48);
        v8[45] = *(_DWORD *)(v18 + 88);
        if ( v28 > 0xC )
          v26 = (unsigned int *)(v18 + 232);
      }
      if ( *((_QWORD *)v8 + 6) >= 0xFFFF800000000000uLL )
        *v8 |= 0x100u;
      *((_QWORD *)v8 + 5) = *((_QWORD *)v8 + 6);
      *((_QWORD *)v8 + 7) = *((_QWORD *)v8 + 6) + *(unsigned int *)(v18 + 40);
      v8[1] = (*(_DWORD *)(v18 + 80) >> 12) + ((*(_DWORD *)(v18 + 80) & 0xFFF) != 0);
      *((_QWORD *)v8 + 18) = v53;
      v53 = 0;
      if ( v26 )
      {
        v8[32] = *v26;
        v8[33] = v26[1];
      }
      if ( _bittest16((const signed __int16 *)(v18 + 22), 0xDu) )
        *v8 |= 0x40000u;
      v8[46] = *(_DWORD *)(v18 + 8);
      v8[55] = *(_DWORD *)(v18 + 80);
      v8[56] = *(_DWORD *)(v18 + 84);
      v29 = (void *)SkAllocatePool(512, 8LL * v8[1], 1951624525);
      *((_QWORD *)v8 + 1) = v29;
      if ( !v29 )
      {
LABEL_34:
        Handle = -1073741670;
        goto LABEL_88;
      }
      memset_0(v29, 0, 8LL * v8[1]);
      v60 = *(_DWORD *)(v18 + 84);
      v58 = v60;
      v59 = 0;
      v62 = 0x40000000;
      Handle = SkmiPopulateImagePrototypes(v8, &v57);
      if ( Handle < 0 )
        goto LABEL_88;
      v31 = 0;
      j = 4095;
      v16 = (*(_DWORD *)(v18 + 84) >> 12) + (unsigned int)((*(_DWORD *)(v18 + 84) & 0xFFF) != 0);
      for ( i = v18 + *(unsigned __int16 *)(v18 + 20) + 24LL; ; i += 40 )
      {
        v33 = *(unsigned __int16 *)(v18 + 6);
        v51 = v31;
        if ( v31 >= v33 )
          break;
        Handle = -1073741701;
        if ( i - (__int64)v14 + 40 > (unsigned __int64)*(unsigned int *)(v18 + 84) )
        {
          v19 = 11;
          goto LABEL_87;
        }
        v34 = *(_DWORD *)(i + 12);
        if ( (v34 & 0xFFF) != 0 )
        {
          v19 = 43;
          goto LABEL_87;
        }
        if ( v34 >> 12 < (unsigned int)v16 )
        {
          v19 = 44;
          goto LABEL_87;
        }
        Handle = SkmiPopulateImagePrototypes(v8, i);
        if ( Handle < 0 )
          goto LABEL_88;
        v35 = *(_DWORD *)(i + 8);
        j = 4095;
        v36 = *(_DWORD *)(i + 12) >> 12;
        v16 = (v35 >> 12) + v36 + ((v35 & 0xFFF) != 0);
        v31 = v51 + 1;
      }
      if ( (*(_BYTE *)(v18 + 22) & 1) != 0 )
      {
        *((_QWORD *)v8 + 11) = 0;
        v8[24] = 1;
      }
      else
      {
        if ( v28 <= 5 )
        {
LABEL_48:
          Handle = -1073741701;
          goto LABEL_88;
        }
        v8[56] = *(_DWORD *)(v18 + 84);
        v37 = v18 - (_DWORD)v14;
        if ( (_DWORD)v52 )
        {
          v38 = v37 + 52;
          v39 = (unsigned int *)(v18 + 160);
        }
        else
        {
          v38 = v37 + 48;
          v39 = (unsigned int *)(v18 + 176);
        }
        v8[38] = v38;
        if ( v27 + (v38 & 0xFFF) > 0x1000 )
        {
          v40 = 13;
LABEL_54:
          SKMI_BAD_IMAGE(v40, v16, j);
          goto LABEL_48;
        }
        v41 = *v39;
        if ( (_DWORD)v41 && v39[1] )
        {
          *((_QWORD *)v8 + 11) = v41;
          v42 = v39[1];
          v8[24] = v42;
          v16 = *((_QWORD *)v8 + 11);
          if ( v16 < 0 || v16 + v42 > (unsigned __int64)*(unsigned int *)(v18 + 80) )
          {
            *((_QWORD *)v8 + 11) = 0;
            v40 = 12;
            goto LABEL_54;
          }
          v43 = 16LL * ((unsigned int)*(unsigned __int16 *)(v18 + 6) + 1);
          v8[25] = *(unsigned __int16 *)(v18 + 6) + 1;
          v44 = (_OWORD *)SkAllocatePool(1, v43, 1934847309);
          *((_QWORD *)v8 + 13) = v44;
          if ( !v44 )
            goto LABEL_34;
          v30 = 0;
          *v44 = 0;
          v16 = v18 + *(unsigned __int16 *)(v18 + 20) + 24LL;
          for ( j = *((_QWORD *)v8 + 13) + 16LL;
                (unsigned int)v30 < *(unsigned __int16 *)(v18 + 6);
                v30 = (unsigned int)(v30 + 1) )
          {
            *(_DWORD *)j = *(_DWORD *)(v16 + 12) >> 12;
            *(_DWORD *)(j + 4) = (*(_DWORD *)(v16 + 16) >> 12) + ((*(_DWORD *)(v16 + 16) & 0xFFF) != 0);
            *(_QWORD *)(j + 8) = *(unsigned int *)(v16 + 20);
            v45 = *(unsigned int *)(v16 + 12);
            v46 = *((_QWORD *)v8 + 11);
            if ( v46 >= v45 && v46 + v8[24] <= (unsigned int)(v45 + *(_DWORD *)(v16 + 16)) )
              *((_QWORD *)v8 + 8) = *(_DWORD *)(v16 + 20) + (v46 & 0xFFFFF000) - (unsigned int)v45;
            v16 += 40;
            j += 16LL;
          }
          if ( !*((_QWORD *)v8 + 8) )
          {
            v40 = 14;
            goto LABEL_54;
          }
        }
        else
        {
          *((_QWORD *)v8 + 11) = 1;
          v8[24] = 0;
        }
      }
      if ( *(_WORD *)(v18 + 24) == 523 && *(_DWORD *)(v18 + 132) >= 0xAu )
      {
        v47 = *(_DWORD *)(v18 + 220);
        v8[54] = v47;
        if ( v47 )
          *((_QWORD *)v8 + 26) = *(unsigned int *)(v18 + 216);
        v16 = *((_QWORD *)v8 + 26);
        j = v16 + v8[54];
        if ( j < v16 || j > v8[55] )
        {
          Handle = -1073741701;
          v19 = 52;
          goto LABEL_87;
        }
        v48 = (void *)SkAllocatePool(512, 128, 1147628873);
        *((_QWORD *)v8 + 29) = v48;
        if ( !v48 )
          goto LABEL_34;
        memset_0(v48, 0, 0x80u);
      }
      v49 = RtlLookupImageSectionByName(v18, "KSCP", j, v30);
      if ( v49 )
        v8[44] = *(_DWORD *)(v49 + 12);
      LOBYTE(v50) = 1;
      Handle = SkobCreateHandle(v8, v50, 0, a6);
      if ( Handle >= 0 )
        *((_QWORD *)v8 + 30) = *a6;
      goto LABEL_88;
    }
    v19 = 5;
    goto LABEL_87;
  }
  Handle = -1073741670;
LABEL_89:
  if ( v53 )
    SkciFreeImageContext();
  if ( v8 )
    SkobDereferenceObject(v8);
  if ( v9 )
    SkmmFreeSparseTableEntry(&SkmiImageTable, v9);
  if ( v14 )
    SkFreePool(1, v14);
  if ( v56 )
    SkmmUnmapDataTransfer(v56);
  return (unsigned int)Handle;
}

```

## disassembly

```asm
0x140062a88  push    rbp
0x140062a8a  push    rbx
0x140062a8b  push    rsi
0x140062a8c  push    rdi
0x140062a8d  push    r12
0x140062a8f  push    r13
0x140062a91  push    r14
0x140062a93  push    r15
0x140062a95  lea     rbp, [rsp-0Fh]
0x140062a9a  sub     rsp, 98h
0x140062aa1  xor     edi, edi
0x140062aa3  mov     r12d, r9d
0x140062aa6  mov     r13b, r8b
0x140062aa9  mov     [rbp+47h+var_70], rdi
0x140062aad  xorps   xmm0, xmm0
0x140062ab0  mov     [rbp+47h+var_80], rdi
0x140062ab4  mov     ebx, edi
0x140062ab6  mov     [rbp+47h+var_A0], edi
0x140062ab9  lea     r8d, [rdi+1]
0x140062abd  mov     [rbp+47h+var_88], rbx
0x140062ac1  lea     r9, [rbp+47h+var_98]
0x140062ac5  mov     [rbp+47h+var_9C], edi
0x140062ac8  movdqu  [rbp+47h+var_5C], xmm0
0x140062acd  mov     esi, edi
0x140062acf  mov     [rbp+47h+var_98], rdi
0x140062ad3  mov     [rbp+47h+var_90], rdi
0x140062ad7  mov     [rsp+0D0h+var_B0], rdi
0x140062adc  call    SkmmMapDataTransfer
0x140062ae1  test    eax, eax
0x140062ae3  js      loc_1400631B0
0x140062ae9  mov     rdi, [rbp+47h+var_98]
0x140062aed  lea     ecx, [rbx+1]
0x140062af0  mov     r8d, 50676D49h
0x140062af6  mov     [rbp+47h+var_78], rdi
0x140062afa  mov     r14d, [rdi+28h]
0x140062afe  mov     edx, r14d
0x140062b01  call    SkAllocatePool
0x140062b06  mov     r15, rax
0x140062b09  test    rax, rax
0x140062b0c  jnz     short loc_140062B18
0x140062b0e  mov     edi, 0C000009Ah
0x140062b13  jmp     loc_140063157
0x140062b18  mov     rdx, [rdi+18h]; Src
0x140062b1c  mov     r8, r14; Size
0x140062b1f  mov     rcx, r15; void *
0x140062b22  call    memmove
0x140062b27  mov     rcx, rdi
0x140062b2a  call    SkmmUnmapDataTransfer
0x140062b2f  lea     r9, [rbp+47h+var_80]
0x140062b33  mov     [rbp+47h+var_78], rbx
0x140062b37  mov     r8, r14
0x140062b3a  mov     rdx, r15
0x140062b3d  xor     ecx, ecx
0x140062b3f  call    RtlImageNtHeaderEx
0x140062b44  mov     edi, eax
0x140062b46  test    eax, eax
0x140062b48  js      loc_140063157
0x140062b4e  mov     rsi, [rbp+47h+var_80]
0x140062b52  mov     edi, 0C000007Bh
0x140062b57  mov     rax, rsi
0x140062b5a  sub     rax, r15
0x140062b5d  add     rax, 88h
0x140062b63  cmp     rax, r14
0x140062b66  jbe     short loc_140062B72
0x140062b68  mov     ecx, 7
0x140062b6d  jmp     loc_14006314F
0x140062b72  movzx   eax, word ptr [rsi+18h]
0x140062b76  mov     ecx, 20Bh
0x140062b7b  cmp     ax, cx
0x140062b7e  jnz     short loc_140062B94
0x140062b80  mov     eax, 8664h
0x140062b85  cmp     [rsi+4], ax
0x140062b89  jnz     loc_14006314A
0x140062b8f  mov     dword ptr [rbp+47h+var_98], ebx
0x140062b92  jmp     short loc_140062BB6
0x140062b94  mov     ecx, 10Bh
0x140062b99  cmp     ax, cx
0x140062b9c  jnz     loc_14006314A
0x140062ba2  lea     eax, [rcx+41h]
0x140062ba5  cmp     [rsi+4], ax
0x140062ba9  jnz     loc_14006314A
0x140062baf  mov     dword ptr [rbp+47h+var_98], 1
0x140062bb6  mov     eax, [rsi+84h]
0x140062bbc  lea     rax, ds:88h[rax*8]
0x140062bc4  sub     rax, r15
0x140062bc7  add     rax, rsi
0x140062bca  cmp     rax, r14
0x140062bcd  jbe     short loc_140062BD9
0x140062bcf  mov     ecx, 8
0x140062bd4  jmp     loc_14006314F
0x140062bd9  mov     eax, [rsi+54h]
0x140062bdc  test    eax, eax
0x140062bde  jz      loc_140063143
0x140062be4  cmp     rax, r14
0x140062be7  ja      loc_140063143
0x140062bed  mov     ecx, [rsi+38h]
0x140062bf0  cmp     ecx, 1000h
0x140062bf6  jb      loc_14006313C
0x140062bfc  lea     eax, [rcx-1]
0x140062bff  test    ecx, eax
0x140062c01  jnz     loc_14006313C
0x140062c07  lea     rax, [rbp+47h+var_90]
0x140062c0b  mov     r9d, r12d
0x140062c0e  mov     [rsp+0D0h+var_A8], rax
0x140062c13  mov     r8b, r13b
0x140062c16  mov     eax, [rbp+47h+arg_20]
0x140062c19  mov     rdx, r14
0x140062c1c  mov     rcx, r15
0x140062c1f  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140062c23  call    cs:__imp_SkciCreateSecureImage
0x140062c2a  nop     dword ptr [rax+rax+00h]
0x140062c2f  mov     edi, eax
0x140062c31  test    eax, eax
0x140062c33  js      loc_140063154
0x140062c39  lea     rdx, [rbp+47h+var_9C]
0x140062c3d  lea     rcx, SkmiImageTable
0x140062c44  call    SkmmAllocateSparseTableEntry
0x140062c49  mov     edi, eax
0x140062c4b  test    eax, eax
0x140062c4d  js      loc_140063137
0x140062c53  lea     r9, [rbp+47h+var_88]
0x140062c57  xor     r8d, r8d
0x140062c5a  lea     rdx, SkmiImageType
0x140062c61  xor     ecx, ecx
0x140062c63  call    SkobCreateObjectEx
0x140062c68  mov     rbx, [rbp+47h+var_88]
0x140062c6c  mov     edi, eax
0x140062c6e  test    eax, eax
0x140062c70  js      loc_140063137
0x140062c76  xor     edx, edx; Val
0x140062c78  mov     r8d, 0F8h; Size
0x140062c7e  mov     rcx, rbx; void *
0x140062c81  call    memset_0
0x140062c86  mov     rax, cs:SkmiImageTable
0x140062c8d  xor     edi, edi
0x140062c8f  mov     edx, [rbp+47h+var_9C]
0x140062c92  mov     r8d, dword ptr [rbp+47h+var_98]
0x140062c96  mov     [rbp+47h+var_A0], edi
0x140062c99  mov     [rax+rdx*8], rbx
0x140062c9d  mov     eax, r8d
0x140062ca0  mov     [rbx+48h], edx
0x140062ca3  mov     edx, edi
0x140062ca5  mov     [rbx+70h], rdi
0x140062ca9  mov     [rbx+78h], edi
0x140062cac  mov     dword ptr [rbx+7Ch], 0FFFFFFFFh
0x140062cb3  mov     ecx, [rbx]
0x140062cb5  btr     ecx, 0Eh
0x140062cb9  shl     eax, 0Eh
0x140062cbc  or      ecx, eax
0x140062cbe  or      ecx, 1
0x140062cc1  mov     [rbx], ecx
0x140062cc3  test    r8d, r8d
0x140062cc6  jz      short loc_140062CEF
0x140062cc8  mov     eax, [rsi+34h]
0x140062ccb  lea     r12d, [rdi+4]
0x140062ccf  mov     r13d, [rsi+74h]
0x140062cd3  mov     [rbx+30h], rax
0x140062cd7  mov     eax, [rsi+58h]
0x140062cda  mov     [rbx+0B4h], eax
0x140062ce0  cmp     r13d, 0Ch
0x140062ce4  jbe     short loc_140062D1A
0x140062ce6  lea     rdx, [rsi+0D8h]
0x140062ced  jmp     short loc_140062D1A
0x140062cef  mov     rax, [rsi+30h]
0x140062cf3  mov     r12d, 8
0x140062cf9  mov     r13d, [rsi+84h]
0x140062d00  mov     [rbx+30h], rax
0x140062d04  mov     eax, [rsi+58h]
0x140062d07  mov     [rbx+0B4h], eax
0x140062d0d  cmp     r13d, 0Ch
0x140062d11  jbe     short loc_140062D1A
0x140062d13  lea     rdx, [rsi+0E8h]
0x140062d1a  mov     rax, 0FFFF800000000000h
0x140062d24  cmp     [rbx+30h], rax
0x140062d28  jb      short loc_140062D2E
0x140062d2a  bts     dword ptr [rbx], 8
0x140062d2e  mov     rax, [rbx+30h]
0x140062d32  mov     r14d, 0FFFh
0x140062d38  mov     [rbx+28h], rax
0x140062d3c  mov     eax, [rsi+28h]
0x140062d3f  add     rax, [rbx+30h]
0x140062d43  mov     [rbx+38h], rax
0x140062d47  mov     eax, edi
0x140062d49  mov     ecx, [rsi+50h]
0x140062d4c  test    r14d, ecx
0x140062d4f  setnz   al
0x140062d52  shr     ecx, 0Ch
0x140062d55  add     eax, ecx
0x140062d57  mov     [rbx+4], eax
0x140062d5a  mov     rax, [rbp+47h+var_90]
0x140062d5e  mov     [rbx+90h], rax
0x140062d65  mov     [rbp+47h+var_90], rdi
0x140062d69  test    rdx, rdx
0x140062d6c  jz      short loc_140062D7F
0x140062d6e  mov     eax, [rdx]
0x140062d70  mov     [rbx+80h], eax
0x140062d76  mov     eax, [rdx+4]
0x140062d79  mov     [rbx+84h], eax
0x140062d7f  bt      word ptr [rsi+16h], 0Dh
0x140062d85  jnb     short loc_140062D8B
0x140062d87  bts     dword ptr [rbx], 12h
0x140062d8b  mov     eax, [rsi+8]
0x140062d8e  mov     ecx, 200h
0x140062d93  mov     [rbx+0B8h], eax
0x140062d99  mov     r8d, 74536D4Dh
0x140062d9f  mov     eax, [rsi+50h]
0x140062da2  mov     [rbx+0DCh], eax
0x140062da8  mov     eax, [rsi+54h]
0x140062dab  mov     [rbx+0E0h], eax
0x140062db1  mov     edx, [rbx+4]
0x140062db4  shl     rdx, 3
0x140062db8  call    SkAllocatePool
0x140062dbd  mov     [rbx+8], rax
0x140062dc1  test    rax, rax
0x140062dc4  jnz     short loc_140062DD0
0x140062dc6  mov     edi, 0C000009Ah
0x140062dcb  jmp     loc_140063154
0x140062dd0  mov     r8d, [rbx+4]
0x140062dd4  xor     edx, edx; Val
0x140062dd6  shl     r8, 3; Size
0x140062dda  mov     rcx, rax; void *
0x140062ddd  call    memset_0
0x140062de2  mov     eax, [rsi+54h]
0x140062de5  lea     rdx, [rbp+47h+var_70]
0x140062de9  mov     rcx, rbx
0x140062dec  mov     [rbp+47h+var_60], eax
0x140062def  mov     [rbp+47h+var_68], eax
0x140062df2  mov     [rbp+47h+var_64], edi
0x140062df5  mov     [rbp+47h+var_4C], 40000000h
0x140062dfc  call    SkmiPopulateImagePrototypes
0x140062e01  mov     edi, eax
0x140062e03  test    eax, eax
0x140062e05  js      loc_140063154
0x140062e0b  mov     eax, [rsi+54h]
0x140062e0e  mov     edi, 0
0x140062e13  test    r14d, eax
0x140062e16  mov     edx, edi
0x140062e18  movzx   r14d, word ptr [rsi+14h]
0x140062e1d  mov     ecx, edi
0x140062e1f  setnz   dl
0x140062e22  mov     r8d, 0FFFh
0x140062e28  shr     eax, 0Ch
0x140062e2b  add     r14, 18h
0x140062e2f  add     edx, eax
0x140062e31  add     r14, rsi
0x140062e34  movzx   eax, word ptr [rsi+6]
0x140062e38  mov     [rbp+47h+var_9C], ecx
0x140062e3b  cmp     ecx, eax
0x140062e3d  jnb     loc_140062ECD
0x140062e43  mov     eax, [rsi+54h]
0x140062e46  mov     rcx, r14
0x140062e49  sub     rcx, r15
0x140062e4c  mov     edi, 0C000007Bh
0x140062e51  add     rcx, 28h ; '('
0x140062e55  cmp     rcx, rax
0x140062e58  ja      short loc_140062EC3
0x140062e5a  mov     eax, [r14+0Ch]
0x140062e5e  test    r8d, eax
0x140062e61  jnz     short loc_140062EB9
0x140062e63  shr     eax, 0Ch
0x140062e66  cmp     eax, edx
0x140062e68  jb      short loc_140062EAF
0x140062e6a  mov     rdx, r14
0x140062e6d  mov     rcx, rbx
0x140062e70  call    SkmiPopulateImagePrototypes
0x140062e75  mov     edi, eax
0x140062e77  test    eax, eax
0x140062e79  js      loc_140063154
0x140062e7f  mov     ecx, [r14+8]
0x140062e83  mov     r8d, 0FFFh
0x140062e89  mov     eax, [r14+0Ch]
0x140062e8d  test    r8d, ecx
0x140062e90  mov     edi, 0
0x140062e95  mov     edx, edi
0x140062e97  setnz   dl
0x140062e9a  shr     ecx, 0Ch
0x140062e9d  shr     eax, 0Ch
0x140062ea0  add     r14, 28h ; '('
0x140062ea4  add     edx, eax
0x140062ea6  add     edx, ecx
0x140062ea8  mov     ecx, [rbp+47h+var_9C]
0x140062eab  inc     ecx
0x140062ead  jmp     short loc_140062E34
0x140062eaf  mov     ecx, 2Ch ; ','
0x140062eb4  jmp     loc_14006314F
0x140062eb9  mov     ecx, 2Bh ; '+'
0x140062ebe  jmp     loc_14006314F
0x140062ec3  mov     ecx, 0Bh
0x140062ec8  jmp     loc_14006314F
0x140062ecd  test    byte ptr [rsi+16h], 1
0x140062ed1  jnz     loc_14006304D
0x140062ed7  cmp     r13d, 5
0x140062edb  ja      short loc_140062EE7
0x140062edd  mov     edi, 0C000007Bh
0x140062ee2  jmp     loc_140063154
0x140062ee7  mov     eax, [rsi+54h]
0x140062eea  mov     [rbx+0E0h], eax
0x140062ef0  mov     eax, esi
0x140062ef2  sub     eax, r15d
0x140062ef5  cmp     dword ptr [rbp+47h+var_98], edi
  ... truncated ...
```
