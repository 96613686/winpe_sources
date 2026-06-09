# SpConvertStreamFormatEnum(SPSTREAMFORMAT,_GUID *,tWAVEFORMATEX * *,int *)

- ea: `0x18009c3c0`
- end: `0x18009c7b7`
- name: `?SpConvertStreamFormatEnum@@YAJW4SPSTREAMFORMAT@@PEAU_GUID@@PEAPEAUtWAVEFORMATEX@@PEAH@Z`
- size: `1015`
- prototype: `__int64 __fastcall(enum SPSTREAMFORMAT, struct _GUID *, struct tWAVEFORMATEX **, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180089ce4`
- `0x1800bf7f0`
- `0x1800c59c0`

## callees

- `0x18009c3c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c40c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c49b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c503`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c57a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c5b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c68f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c6ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c40c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c49b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c503`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c57a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c5b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c68f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c6ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c733`

## pseudocode

```c
__int64 __fastcall SpConvertStreamFormatEnum(
        enum SPSTREAMFORMAT a1,
        struct _GUID *a2,
        struct tWAVEFORMATEX **a3,
        int *a4)
{
  unsigned int v7; // ebx
  unsigned int v8; // esi
  struct _GUID *v9; // rdi
  struct tWAVEFORMATEX *v10; // rax
  struct tWAVEFORMATEX *v11; // rcx
  char v12; // r9
  unsigned int v13; // eax
  WORD v14; // si
  __int64 v15; // rax
  int v16; // r9d
  __int64 *v17; // rdx
  DWORD v18; // r8d
  struct tWAVEFORMATEX *v19; // rax
  unsigned int v20; // esi
  char *v21; // rax
  char *v22; // r8
  int *v23; // rcx
  __int64 v24; // rax
  unsigned __int16 v25; // si
  int v26; // ecx
  char *v27; // rax
  __int64 v28; // rsi
  struct tWAVEFORMATEX *v29; // rax
  struct tWAVEFORMATEX *v30; // r8
  WORD v31; // r10
  __int64 v32; // r9
  int *v33; // rax
  __int64 *v34; // rcx
  WORD v35; // cx
  __int64 (**v36)[4]; // rax
  __int64 *v37; // rax
  __int64 v38; // rsi
  char *v39; // rax
  char *v40; // rax
  char *v41; // rax
  __int64 result; // rax

  if ( a2 && a3 )
  {
    v7 = 0;
    if ( a4 )
      *a4 = 0;
    v8 = a1 - 4;
    v9 = &GUID_NULL;
    if ( (unsigned int)(a1 - 4) <= 0x23 )
    {
      v10 = (struct tWAVEFORMATEX *)CoTaskMemAlloc(0x12u);
      *a3 = v10;
      v11 = v10;
      if ( v10 )
      {
        v12 = v8;
        v13 = v8 >> 2;
        v11->wFormatTag = 1;
        v14 = (v8 & 1) + 1;
        v15 = v13 & 0xF;
        v16 = v12 & 2;
        v11->nBlockAlign = v14;
        v11->nChannels = v14;
        v17 = `SpConvertStreamFormatEnum'::`14'::adwKHZ;
        if ( (unsigned int)v15 < 9 )
          v17 = (__int64 *)((char *)`SpConvertStreamFormatEnum'::`14'::adwKHZ + 4 * v15);
        v18 = *(_DWORD *)v17;
        v11->nSamplesPerSec = *(_DWORD *)v17;
        v11->wBitsPerSample = 8;
        if ( v16 )
        {
          v14 *= 2;
          v11->wBitsPerSample = 16;
          v11->nBlockAlign = v14;
        }
        v11->nAvgBytesPerSec = v18 * v14;
        v11->cbSize = 0;
        goto LABEL_12;
      }
      goto LABEL_44;
    }
    if ( a1 == SPSF_TrueSpeech_8kHz1BitMono )
    {
      v19 = (struct tWAVEFORMATEX *)CoTaskMemAlloc(0x32u);
      *a3 = v19;
      if ( !v19 )
        goto LABEL_44;
      *(_OWORD *)&v19->wFormatTag = 0;
      *(_OWORD *)&v19->cbSize = 0;
      *(_OWORD *)&v19[1].wBitsPerSample = 0;
      v19[2].nBlockAlign = 0;
      v19->cbSize = 32;
      LOBYTE(v19[1].wFormatTag) = 1;
      *(_DWORD *)&v19->wFormatTag = 65570;
      v19->nSamplesPerSec = 8000;
      v19->nAvgBytesPerSec = 1067;
      *(_DWORD *)&v19->nBlockAlign = 65568;
      LOBYTE(v19[1].nChannels) = -16;
      goto LABEL_12;
    }
    v20 = a1 - 41;
    if ( (unsigned int)(a1 - 41) > 7 )
    {
      v20 = a1 - 49;
      if ( (unsigned int)(a1 - 49) > 7 )
      {
        v28 = (unsigned int)(a1 - 57);
        if ( (unsigned int)v28 <= 7 )
        {
          v29 = (struct tWAVEFORMATEX *)CoTaskMemAlloc(0x32u);
          *a3 = v29;
          v30 = v29;
          if ( v29 )
          {
            *(_OWORD *)&v29->wFormatTag = 0;
            *(_OWORD *)&v29->cbSize = 0;
            *(_OWORD *)&v29[1].wBitsPerSample = 0;
            v29[2].nBlockAlign = 0;
            v31 = (v28 & 1) + 1;
            v29->wFormatTag = 2;
            v32 = (unsigned int)v28 >> 1;
            v33 = `SpConvertStreamFormatEnum'::`62'::adwKHZ;
            v30->nChannels = v31;
            if ( (unsigned int)v32 < 4 )
              v33 = &`SpConvertStreamFormatEnum'::`62'::adwKHZ[v32];
            v30->nSamplesPerSec = *v33;
            v34 = `SpConvertStreamFormatEnum'::`53'::BlockAlign;
            v30->nAvgBytesPerSec = `SpConvertStreamFormatEnum'::`53'::BytesPerSec[v28];
            if ( (unsigned int)v32 < 4 )
              v34 = (__int64 *)((char *)`SpConvertStreamFormatEnum'::`53'::BlockAlign + 4 * v32);
            v35 = v31 * *(_WORD *)v34;
            v36 = `SpConvertStreamFormatEnum'::`53'::Extra;
            *(_DWORD *)&v30->wBitsPerSample = 2097156;
            v30->nBlockAlign = v35;
            if ( (unsigned int)v32 < 4 )
              v36 = &`SpConvertStreamFormatEnum'::`53'::Extra[v32];
            v37 = (__int64 *)*v36;
            *(_OWORD *)&v30[1].wFormatTag = *(_OWORD *)v37;
            *(_OWORD *)&v30[1].cbSize = *((_OWORD *)v37 + 1);
            goto LABEL_12;
          }
          goto LABEL_44;
        }
        v38 = (unsigned int)(a1 - 65);
        if ( (unsigned int)v38 > 3 )
        {
          if ( a1 != SPSF_NUM_FORMATS )
          {
            if ( a1 == (SPSF_GSM610_44kHzMono|SPSF_NonStandardFormat) )
            {
              v41 = (char *)CoTaskMemAlloc(0x12u);
              *a3 = (struct tWAVEFORMATEX *)v41;
              if ( !v41 )
                goto LABEL_44;
              *(_WORD *)v41 = 3;
              v9 = (struct _GUID *)&SPDFID_WaveFormatEx;
              *((_DWORD *)v41 + 3) = 0x200000;
              *((_WORD *)v41 + 1) = 0;
              *(_QWORD *)(v41 + 4) = 16000;
              *((_WORD *)v41 + 8) = 0;
              if ( a4 )
              {
                *a4 = 1;
                goto LABEL_49;
              }
            }
            else
            {
              *a3 = 0;
              if ( a1 == SPSF_NoAssignedFormat )
                goto LABEL_49;
              if ( a1 == SPSF_Text )
              {
                v9 = (struct _GUID *)&SPDFID_Text;
                goto LABEL_49;
              }
            }
            v7 = -2147024809;
            goto LABEL_49;
          }
          v40 = (char *)CoTaskMemAlloc(0x14u);
          *a3 = (struct tWAVEFORMATEX *)v40;
          if ( !v40 )
          {
LABEL_44:
            v7 = -2147024882;
            goto LABEL_49;
          }
          *(_DWORD *)v40 = 66190;
          *((_DWORD *)v40 + 1) = 16000;
          *((_DWORD *)v40 + 2) = 2000;
          *((_WORD *)v40 + 6) = 40;
          *(_DWORD *)(v40 + 14) = 0x20000;
          *((_WORD *)v40 + 9) = 320;
        }
        else
        {
          v39 = (char *)CoTaskMemAlloc(0x14u);
          *a3 = (struct tWAVEFORMATEX *)v39;
          if ( !v39 )
            goto LABEL_44;
          *(_QWORD *)(v39 + 4) = 0;
          *(_QWORD *)(v39 + 12) = 0;
          *(_DWORD *)v39 = 65585;
          *((_DWORD *)v39 + 1) = `SpConvertStreamFormatEnum'::`62'::adwKHZ[v38];
          *((_DWORD *)v39 + 2) = `SpConvertStreamFormatEnum'::`62'::BytesPerSec[v38];
          *((_WORD *)v39 + 6) = 65;
          *((_DWORD *)v39 + 4) = 20971522;
        }
LABEL_12:
        v9 = (struct _GUID *)&SPDFID_WaveFormatEx;
LABEL_49:
        result = v7;
        *a2 = *v9;
        return result;
      }
      v27 = (char *)CoTaskMemAlloc(0x12u);
      *a3 = (struct tWAVEFORMATEX *)v27;
      v22 = v27;
      if ( !v27 )
        goto LABEL_44;
      *(_QWORD *)(v27 + 4) = 0;
      v23 = `SpConvertStreamFormatEnum'::`62'::adwKHZ;
      *(_DWORD *)(v27 + 14) = 0;
      *(_WORD *)v27 = 7;
    }
    else
    {
      v21 = (char *)CoTaskMemAlloc(0x12u);
      *a3 = (struct tWAVEFORMATEX *)v21;
      v22 = v21;
      if ( !v21 )
        goto LABEL_44;
      *(_QWORD *)(v21 + 4) = 0;
      v23 = `SpConvertStreamFormatEnum'::`62'::adwKHZ;
      *(_DWORD *)(v21 + 14) = 0;
      *(_WORD *)v21 = 6;
    }
    v24 = v20 >> 1;
    v25 = (v20 & 1) + 1;
    *((_WORD *)v22 + 1) = v25;
    *((_WORD *)v22 + 6) = v25;
    if ( (unsigned int)v24 < 4 )
      v23 = &`SpConvertStreamFormatEnum'::`62'::adwKHZ[v24];
    v26 = *v23;
    *((_DWORD *)v22 + 1) = v26;
    *((_WORD *)v22 + 7) = 8;
    *((_DWORD *)v22 + 2) = v26 * v25;
    goto LABEL_12;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18009c3c0  push    rbx
0x18009c3c2  push    rbp
0x18009c3c3  push    rsi
0x18009c3c4  push    rdi
0x18009c3c5  push    r13
0x18009c3c7  push    r14
0x18009c3c9  push    r15
0x18009c3cb  sub     rsp, 20h
0x18009c3cf  mov     r15, r9
0x18009c3d2  mov     r14, r8
0x18009c3d5  mov     rbp, rdx
0x18009c3d8  test    rdx, rdx
0x18009c3db  jz      loc_18009C7A3
0x18009c3e1  test    r8, r8
0x18009c3e4  jz      loc_18009C7A3
0x18009c3ea  xor     ebx, ebx
0x18009c3ec  test    r9, r9
0x18009c3ef  jz      short loc_18009C3F4
0x18009c3f1  mov     [r9], ebx
0x18009c3f4  lea     esi, [rcx-4]
0x18009c3f7  lea     rdi, GUID_NULL
0x18009c3fe  cmp     esi, 23h ; '#'
0x18009c401  ja      loc_18009C491
0x18009c407  mov     ecx, 12h; cb
0x18009c40c  call    cs:__imp_CoTaskMemAlloc
0x18009c412  mov     [r14], rax
0x18009c415  mov     rcx, rax
0x18009c418  test    rax, rax
0x18009c41b  jz      loc_18009C776
0x18009c421  mov     edx, 1
0x18009c426  mov     eax, esi
0x18009c428  mov     r9d, esi
0x18009c42b  shr     eax, 2
0x18009c42e  and     si, dx
0x18009c431  mov     [rcx], dx
0x18009c434  add     si, dx
0x18009c437  and     eax, 0Fh
0x18009c43a  and     r9d, 2
0x18009c43e  mov     [rcx+0Ch], si
0x18009c442  mov     [rcx+2], si
0x18009c446  lea     rdx, ?adwKHZ@?O@??SpConvertStreamFormatEnum@@YAJW4SPSTREAMFORMAT@@PEAU_GUID@@PEAPEAUtWAVEFORMATEX@@PEAH@Z@4QBKB; ulong const near * const `SpConvertStreamFormatEnum(SPSTREAMFORMAT,_GUID *,tWAVEFORMATEX * *,int *)'::`14'::adwKHZ
0x18009c44d  cmp     eax, 9
0x18009c450  jnb     short loc_18009C456
0x18009c452  lea     rdx, [rdx+rax*4]
0x18009c456  mov     r8d, [rdx]
0x18009c459  mov     [rcx+4], r8d
0x18009c45d  mov     word ptr [rcx+0Eh], 8
0x18009c463  test    r9d, r9d
0x18009c466  jz      short loc_18009C475
0x18009c468  add     si, si
0x18009c46b  mov     word ptr [rcx+0Eh], 10h
0x18009c471  mov     [rcx+0Ch], si
0x18009c475  movzx   eax, si
0x18009c478  imul    eax, r8d
0x18009c47c  mov     [rcx+8], eax
0x18009c47f  xor     eax, eax
0x18009c481  mov     [rcx+10h], ax
0x18009c485  lea     rdi, SPDFID_WaveFormatEx
0x18009c48c  jmp     loc_18009C797
0x18009c491  cmp     ecx, 28h ; '('
0x18009c494  jnz     short loc_18009C4F1
0x18009c496  mov     ecx, 32h ; '2'; cb
0x18009c49b  call    cs:__imp_CoTaskMemAlloc
0x18009c4a1  mov     [r14], rax
0x18009c4a4  test    rax, rax
0x18009c4a7  jz      loc_18009C776
0x18009c4ad  xor     ecx, ecx
0x18009c4af  xorps   xmm0, xmm0
0x18009c4b2  movups  xmmword ptr [rax], xmm0
0x18009c4b5  movups  xmmword ptr [rax+10h], xmm0
0x18009c4b9  lea     edx, [rcx+1]
0x18009c4bc  movups  xmmword ptr [rax+20h], xmm0
0x18009c4c0  mov     [rax+30h], cx
0x18009c4c4  lea     r10d, [rcx+20h]
0x18009c4c8  mov     [rax+10h], r10w
0x18009c4cd  mov     [rax+12h], dl
0x18009c4d0  mov     dword ptr [rax], 10022h
0x18009c4d6  mov     dword ptr [rax+4], 1F40h
0x18009c4dd  mov     dword ptr [rax+8], 42Bh
0x18009c4e4  mov     dword ptr [rax+0Ch], 10020h
0x18009c4eb  mov     byte ptr [rax+14h], 0F0h
0x18009c4ef  jmp     short loc_18009C485
0x18009c4f1  lea     esi, [rcx-29h]
0x18009c4f4  mov     r13d, 7
0x18009c4fa  cmp     esi, r13d
0x18009c4fd  ja      short loc_18009C56D
0x18009c4ff  lea     ecx, [r13+0Bh]; cb
0x18009c503  call    cs:__imp_CoTaskMemAlloc
0x18009c509  mov     [r14], rax
0x18009c50c  mov     r8, rax
0x18009c50f  test    rax, rax
0x18009c512  jz      loc_18009C776
0x18009c518  mov     [rax+4], rbx
0x18009c51c  lea     rcx, ?adwKHZ@?DO@??SpConvertStreamFormatEnum@@YAJW4SPSTREAMFORMAT@@PEAU_GUID@@PEAPEAUtWAVEFORMATEX@@PEAH@Z@4QBKB; ulong const near * const `SpConvertStreamFormatEnum(SPSTREAMFORMAT,_GUID *,tWAVEFORMATEX * *,int *)'::`62'::adwKHZ
0x18009c523  mov     [rax+0Eh], ebx
0x18009c526  mov     word ptr [rax], 6
0x18009c52b  mov     edx, 1
0x18009c530  mov     eax, esi
0x18009c532  and     si, dx
0x18009c535  shr     eax, 1
0x18009c537  add     si, dx
0x18009c53a  mov     edx, 4
0x18009c53f  mov     [r8+2], si
0x18009c544  mov     [r8+0Ch], si
0x18009c549  cmp     eax, edx
0x18009c54b  jnb     short loc_18009C551
0x18009c54d  lea     rcx, [rcx+rax*4]
0x18009c551  mov     ecx, [rcx]
0x18009c553  mov     [r8+4], ecx
0x18009c557  movzx   eax, si
0x18009c55a  imul    eax, ecx
0x18009c55d  mov     word ptr [r8+0Eh], 8
0x18009c564  mov     [r8+8], eax
0x18009c568  jmp     loc_18009C485
0x18009c56d  lea     esi, [rcx-31h]
0x18009c570  cmp     esi, r13d
0x18009c573  ja      short loc_18009C5A3
0x18009c575  mov     ecx, 12h; cb
0x18009c57a  call    cs:__imp_CoTaskMemAlloc
0x18009c580  mov     [r14], rax
0x18009c583  mov     r8, rax
0x18009c586  test    rax, rax
0x18009c589  jz      loc_18009C776
0x18009c58f  mov     [rax+4], rbx
0x18009c593  lea     rcx, ?adwKHZ@?DO@??SpConvertStreamFormatEnum@@YAJW4SPSTREAMFORMAT@@PEAU_GUID@@PEAPEAUtWAVEFORMATEX@@PEAH@Z@4QBKB; ulong const near * const `SpConvertStreamFormatEnum(SPSTREAMFORMAT,_GUID *,tWAVEFORMATEX * *,int *)'::`62'::adwKHZ
0x18009c59a  mov     [rax+0Eh], ebx
0x18009c59d  mov     [rax], r13w
0x18009c5a1  jmp     short loc_18009C52B
0x18009c5a3  lea     esi, [rcx-39h]
0x18009c5a6  cmp     esi, r13d
0x18009c5a9  ja      loc_18009C67D
0x18009c5af  mov     ecx, 32h ; '2'; cb
0x18009c5b4  call    cs:__imp_CoTaskMemAlloc
0x18009c5ba  mov     [r14], rax
0x18009c5bd  mov     r8, rax
0x18009c5c0  test    rax, rax
0x18009c5c3  jz      loc_18009C776
0x18009c5c9  xor     eax, eax
0x18009c5cb  xorps   xmm0, xmm0
0x18009c5ce  movups  xmmword ptr [r8], xmm0
0x18009c5d2  mov     edx, 1
0x18009c5d7  mov     r10d, esi
0x18009c5da  movups  xmmword ptr [r8+10h], xmm0
0x18009c5df  and     r10w, dx
0x18009c5e3  movups  xmmword ptr [r8+20h], xmm0
0x18009c5e8  mov     [r8+30h], ax
0x18009c5ed  add     r10w, dx
0x18009c5f1  mov     eax, esi
0x18009c5f3  mov     word ptr [r8], 2
0x18009c5f9  shr     eax, 1
0x18009c5fb  mov     edx, 4
0x18009c600  mov     r9d, eax
0x18009c603  cmp     eax, edx
0x18009c605  lea     rax, ?adwKHZ@?DO@??SpConvertStreamFormatEnum@@YAJW4SPSTREAMFORMAT@@PEAU_GUID@@PEAPEAUtWAVEFORMATEX@@PEAH@Z@4QBKB; ulong const near * const `SpConvertStreamFormatEnum(SPSTREAMFORMAT,_GUID *,tWAVEFORMATEX * *,int *)'::`62'::adwKHZ
0x18009c60c  mov     [r8+2], r10w
0x18009c611  jnb     short loc_18009C617
0x18009c613  lea     rax, [rax+r9*4]
0x18009c617  mov     eax, [rax]
0x18009c619  lea     r11, __ImageBase
0x18009c620  mov     [r8+4], eax
0x18009c624  lea     rcx, ?BlockAlign@?DF@??SpConvertStreamFormatEnum@@YAJW4SPSTREAMFORMAT@@PEAU_GUID@@PEAPEAUtWAVEFORMATEX@@PEAH@Z@4QBKB; ulong const near * const `SpConvertStreamFormatEnum(SPSTREAMFORMAT,_GUID *,tWAVEFORMATEX * *,int *)'::`53'::BlockAlign
0x18009c62b  mov     eax, ds:rva ?BytesPerSec@?DF@??SpConvertStreamFormatEnum@@YAJW4SPSTREAMFORMAT@@PEAU_GUID@@PEAPEAUtWAVEFORMATEX@@PEAH@Z@4QBKB[r11+rsi*4]; ulong const near * const `SpConvertStreamFormatEnum(SPSTREAMFORMAT,_GUID *,tWAVEFORMATEX * *,int *)'::`53'::BytesPerSec ...
0x18009c633  mov     [r8+8], eax
0x18009c637  jnb     short loc_18009C63D
0x18009c639  lea     rcx, [rcx+r9*4]
0x18009c63d  movzx   ecx, word ptr [rcx]
0x18009c640  movzx   eax, r10w
0x18009c644  imul    ecx, eax
0x18009c647  lea     rax, ?Extra@?DF@??SpConvertStreamFormatEnum@@YAJW4SPSTREAMFORMAT@@PEAU_GUID@@PEAPEAUtWAVEFORMATEX@@PEAH@Z@4PAPEBEA; uchar const * near * `SpConvertStreamFormatEnum(SPSTREAMFORMAT,_GUID *,tWAVEFORMATEX * *,int *)'::`53'::Extra
0x18009c64e  mov     dword ptr [r8+0Eh], 200004h
0x18009c656  mov     [r8+0Ch], cx
0x18009c65b  cmp     r9d, edx
0x18009c65e  jnb     short loc_18009C664
0x18009c660  lea     rax, [rax+r9*8]
0x18009c664  mov     rax, [rax]
0x18009c667  movups  xmm0, xmmword ptr [rax]
0x18009c66a  movups  xmmword ptr [r8+12h], xmm0
0x18009c66f  movups  xmm1, xmmword ptr [rax+10h]
0x18009c673  movups  xmmword ptr [r8+22h], xmm1
0x18009c678  jmp     loc_18009C485
0x18009c67d  lea     esi, [rcx-41h]
0x18009c680  mov     r13d, 3
0x18009c686  cmp     esi, r13d
0x18009c689  ja      short loc_18009C6E5
0x18009c68b  lea     ecx, [r13+11h]; cb
0x18009c68f  call    cs:__imp_CoTaskMemAlloc
0x18009c695  mov     [r14], rax
0x18009c698  mov     r8, rax
0x18009c69b  test    rax, rax
0x18009c69e  jz      loc_18009C776
0x18009c6a4  mov     [rax+4], rbx
0x18009c6a8  lea     r11, __ImageBase
0x18009c6af  mov     [rax+0Ch], rbx
0x18009c6b3  mov     dword ptr [rax], 10031h
0x18009c6b9  mov     eax, ds:rva ?adwKHZ@?DO@??SpConvertStreamFormatEnum@@YAJW4SPSTREAMFORMAT@@PEAU_GUID@@PEAPEAUtWAVEFORMATEX@@PEAH@Z@4QBKB[r11+rsi*4]; ulong const near * const `SpConvertStreamFormatEnum(SPSTREAMFORMAT,_GUID *,tWAVEFORMATEX * *,int *)'::`62'::adwKHZ ...
0x18009c6c1  mov     [r8+4], eax
0x18009c6c5  mov     eax, ds:rva ?BytesPerSec@?DO@??SpConvertStreamFormatEnum@@YAJW4SPSTREAMFORMAT@@PEAU_GUID@@PEAPEAUtWAVEFORMATEX@@PEAH@Z@4QBKB[r11+rsi*4]; ulong const near * const `SpConvertStreamFormatEnum(SPSTREAMFORMAT,_GUID *,tWAVEFORMATEX * *,int *)'::`62'::BytesPerSec ...
0x18009c6cd  mov     [r8+8], eax
0x18009c6d1  mov     word ptr [r8+0Ch], 41h ; 'A'
0x18009c6d8  mov     dword ptr [r8+10h], 1400002h
0x18009c6e0  jmp     loc_18009C485
0x18009c6e5  cmp     ecx, 45h ; 'E'
0x18009c6e8  jnz     short loc_18009C729
0x18009c6ea  mov     ecx, 14h; cb
0x18009c6ef  call    cs:__imp_CoTaskMemAlloc
0x18009c6f5  mov     [r14], rax
0x18009c6f8  test    rax, rax
0x18009c6fb  jz      short loc_18009C776
0x18009c6fd  mov     dword ptr [rax], 1028Eh
0x18009c703  mov     dword ptr [rax+4], 3E80h
0x18009c70a  mov     dword ptr [rax+8], 7D0h
0x18009c711  mov     word ptr [rax+0Ch], 28h ; '('
0x18009c717  mov     dword ptr [rax+0Eh], 20000h
0x18009c71e  mov     word ptr [rax+12h], 140h
0x18009c724  jmp     loc_18009C485
0x18009c729  cmp     ecx, 46h ; 'F'
0x18009c72c  jnz     short loc_18009C77D
0x18009c72e  mov     ecx, 12h; cb
0x18009c733  call    cs:__imp_CoTaskMemAlloc
0x18009c739  mov     [r14], rax
0x18009c73c  mov     rcx, rax
0x18009c73f  test    rax, rax
0x18009c742  jz      short loc_18009C776
0x18009c744  mov     [rax], r13w
0x18009c748  lea     rdi, SPDFID_WaveFormatEx
0x18009c74f  xor     eax, eax
0x18009c751  mov     dword ptr [rcx+0Ch], 200000h
0x18009c758  mov     [rcx+2], ax
0x18009c75c  mov     qword ptr [rcx+4], 3E80h
0x18009c764  mov     [rcx+10h], ax
0x18009c768  test    r15, r15
0x18009c76b  jz      short loc_18009C789
0x18009c76d  mov     dword ptr [r15], 1
0x18009c774  jmp     short loc_18009C797
0x18009c776  mov     ebx, 8007000Eh
0x18009c77b  jmp     short loc_18009C797
0x18009c77d  mov     [r8], rbx
0x18009c780  test    ecx, ecx
0x18009c782  jz      short loc_18009C797
0x18009c784  cmp     ecx, 1
0x18009c787  jz      short loc_18009C790
0x18009c789  mov     ebx, 80070057h
0x18009c78e  jmp     short loc_18009C797
0x18009c790  lea     rdi, SPDFID_Text
0x18009c797  movups  xmm0, xmmword ptr [rdi]
0x18009c79a  mov     eax, ebx
0x18009c79c  movdqu  xmmword ptr [rbp+0], xmm0
0x18009c7a1  jmp     short loc_18009C7A8
0x18009c7a3  mov     eax, 80070057h
0x18009c7a8  add     rsp, 20h
0x18009c7ac  pop     r15
0x18009c7ae  pop     r14
0x18009c7b0  pop     r13
0x18009c7b2  pop     rdi
0x18009c7b3  pop     rsi
0x18009c7b4  pop     rbp
0x18009c7b5  pop     rbx
0x18009c7b6  retn
```
