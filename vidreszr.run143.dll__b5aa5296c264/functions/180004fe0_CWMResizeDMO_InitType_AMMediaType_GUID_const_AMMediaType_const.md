# CWMResizeDMO::InitType(_AMMediaType *,_GUID const *,_AMMediaType const *)

- ea: `0x180004fe0`
- end: `0x1800054d5`
- name: `?InitType@CWMResizeDMO@@AEAAJPEAU_AMMediaType@@PEBU_GUID@@PEBU2@@Z`
- size: `1269`
- prototype: `HRESULT __fastcall(CWMResizeDMO *this, struct _AMMediaType *, const struct _GUID *, const struct _AMMediaType *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800047b0`
- `0x180004bd0`

## callees

- `0x180001968`
- `0x1800019b4`
- `0x180002fe0`
- `0x180003950`
- `0x180003c80`
- `0x180004fe0`
- `0x180008f40`

## import_xrefs

- `msdmo!MoInitMediaType` at `0x180005098`
- `msdmo!MoInitMediaType` at `0x180005196`
- `msdmo!MoInitMediaType` at `0x180005244`
- `msdmo!MoInitMediaType` at `0x180005484`
- `msdmo!MoInitMediaType` at `0x180005098`
- `msdmo!MoInitMediaType` at `0x180005196`
- `msdmo!MoInitMediaType` at `0x180005244`
- `msdmo!MoInitMediaType` at `0x180005484`

## pseudocode

```c
HRESULT __fastcall CWMResizeDMO::InitType(
        CWMResizeDMO *this,
        struct _AMMediaType *a2,
        const struct _GUID *a3,
        const struct _AMMediaType *a4)
{
  __int64 v5; // rax
  int v9; // r15d
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  struct tagVIDEOINFOHEADER *v12; // rbx
  unsigned __int64 v13; // rdx
  HRESULT inited; // r15d
  HRESULT result; // eax
  BYTE *pbFormat; // rcx
  BYTE *v17; // rax
  BYTE *v18; // rdx
  BYTE *v19; // rcx
  BYTE *v20; // rax
  BYTE *v21; // rcx
  BYTE *v22; // rax
  __int64 v23; // rcx
  DWORD v24; // eax
  DWORD v25; // r9d
  int v26; // ecx
  int v27; // eax
  int biWidth; // r10d
  int biHeight; // r8d
  int v30; // ecx
  unsigned __int64 v31; // rdx
  ULONG v32; // eax
  int v33; // eax

  v5 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 )
    v5 = *(_QWORD *)a3->Data4 - *(_QWORD *)MEDIASUBTYPE_RGB565.Data4;
  v9 = v5 == 0 ? 0xC : 0;
  v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 )
    v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)MEDIASUBTYPE_RGB8.Data4;
  if ( !v10 )
    v9 = 1024;
  if ( a4 )
  {
    v12 = (struct tagVIDEOINFOHEADER *)operator new[](0x458u);
    if ( v12 )
    {
      if ( *(_QWORD *)&FORMAT_MFVideoFormat.Data1 == *(_QWORD *)&a4->formattype.Data1
        && *(_QWORD *)FORMAT_MFVideoFormat.Data4 == *(_QWORD *)a4->formattype.Data4 )
      {
        inited = MoInitMediaType(a2, v9 + 176);
        if ( inited < 0 )
        {
LABEL_12:
          operator delete(v12, v13);
          return inited;
        }
        pbFormat = a2->pbFormat;
        a2->subtype = *a3;
        a2->majortype = MEDIATYPE_Video;
        *(_QWORD *)&a2->bFixedSizeSamples = 1;
        a2->lSampleSize = 0;
        a2->formattype = GUID_00000000_0000_0000_0000_000000000000;
        v17 = a4->pbFormat;
        *(_OWORD *)pbFormat = *(_OWORD *)v17;
        *((_OWORD *)pbFormat + 1) = *((_OWORD *)v17 + 1);
        *((_OWORD *)pbFormat + 2) = *((_OWORD *)v17 + 2);
        *((_OWORD *)pbFormat + 3) = *((_OWORD *)v17 + 3);
        *((_OWORD *)pbFormat + 4) = *((_OWORD *)v17 + 4);
        *((_OWORD *)pbFormat + 5) = *((_OWORD *)v17 + 5);
        *((_OWORD *)pbFormat + 6) = *((_OWORD *)v17 + 6);
        *((_OWORD *)pbFormat + 7) = *((_OWORD *)v17 + 7);
        *((_OWORD *)pbFormat + 8) = *((_OWORD *)v17 + 8);
        *((_OWORD *)pbFormat + 9) = *((_OWORD *)v17 + 9);
        *((_OWORD *)pbFormat + 10) = *((_OWORD *)v17 + 10);
        v18 = a2->pbFormat;
        a2->formattype = FORMAT_MFVideoFormat;
        ConvertMFVideoFormatToVIH3(v12, (struct _MFVIDEOFORMAT *)v18);
        goto LABEL_22;
      }
      if ( *(_QWORD *)&FORMAT_VideoInfo.Data1 == *(_QWORD *)&a4->formattype.Data1
        && *(_QWORD *)FORMAT_VideoInfo.Data4 == *(_QWORD *)a4->formattype.Data4 )
      {
        inited = MoInitMediaType(a2, v9 + 88);
        if ( inited < 0 )
          goto LABEL_12;
        v19 = a2->pbFormat;
        a2->subtype = *a3;
        a2->majortype = MEDIATYPE_Video;
        *(_QWORD *)&a2->bFixedSizeSamples = 1;
        a2->lSampleSize = 0;
        a2->formattype = GUID_00000000_0000_0000_0000_000000000000;
        v20 = a4->pbFormat;
        *(_OWORD *)v19 = *(_OWORD *)v20;
        *((_OWORD *)v19 + 1) = *((_OWORD *)v20 + 1);
        *((_OWORD *)v19 + 2) = *((_OWORD *)v20 + 2);
        *((_OWORD *)v19 + 3) = *((_OWORD *)v20 + 3);
        *((_OWORD *)v19 + 4) = *((_OWORD *)v20 + 4);
        *((_QWORD *)v19 + 10) = *((_QWORD *)v20 + 10);
        a2->formattype = FORMAT_VideoInfo;
        goto LABEL_22;
      }
      if ( *(_QWORD *)&FORMAT_VideoInfo2.Data1 == *(_QWORD *)&a4->formattype.Data1
        && *(_QWORD *)FORMAT_VideoInfo2.Data4 == *(_QWORD *)a4->formattype.Data4 )
      {
        inited = MoInitMediaType(a2, v9 + 112);
        if ( inited < 0 )
          goto LABEL_12;
        v21 = a2->pbFormat;
        a2->subtype = *a3;
        a2->majortype = MEDIATYPE_Video;
        *(_QWORD *)&a2->bFixedSizeSamples = 1;
        a2->lSampleSize = 0;
        a2->formattype = GUID_00000000_0000_0000_0000_000000000000;
        v22 = a4->pbFormat;
        *(_OWORD *)v21 = *(_OWORD *)v22;
        *((_OWORD *)v21 + 1) = *((_OWORD *)v22 + 1);
        *((_OWORD *)v21 + 2) = *((_OWORD *)v22 + 2);
        *((_OWORD *)v21 + 3) = *((_OWORD *)v22 + 3);
        *((_OWORD *)v21 + 4) = *((_OWORD *)v22 + 4);
        *((_OWORD *)v21 + 5) = *((_OWORD *)v22 + 5);
        *((_OWORD *)v21 + 6) = *((_OWORD *)v22 + 6);
        a2->formattype = FORMAT_VideoInfo2;
LABEL_22:
        v12->dwBitRate = 0;
        v12->bmiHeader.biSize = 40;
        v12->bmiHeader.biBitCount = BitCountFromSubtype(a3);
        v24 = biCompressionFromSubtype(v23);
        v12->bmiHeader.biCompression = v24;
        v25 = v24;
        v26 = *((_DWORD *)this + 132);
        if ( v26 < 0 || *((int *)this + 133) < 0 || (v27 = *((_DWORD *)this + 134), v27 < 0) || *((int *)this + 135) < 0 )
        {
          if ( *((int *)this + 128) < 0
            || *((int *)this + 129) < 0
            || (biWidth = *((_DWORD *)this + 130), biWidth < 0)
            || *((int *)this + 131) < 0 )
          {
            biHeight = v12->bmiHeader.biHeight;
            biWidth = v12->bmiHeader.biWidth;
          }
          else
          {
            v12->bmiHeader.biWidth = biWidth;
            biHeight = -*((_DWORD *)this + 131);
            if ( v12->bmiHeader.biHeight >= 0 )
              biHeight = *((_DWORD *)this + 131);
            v12->bmiHeader.biHeight = biHeight;
          }
        }
        else
        {
          biWidth = v27 + v26;
          v12->bmiHeader.biWidth = v27 + v26;
          biHeight = -(*((_DWORD *)this + 133) + *((_DWORD *)this + 135));
          if ( v12->bmiHeader.biHeight >= 0 )
            biHeight = *((_DWORD *)this + 133) + *((_DWORD *)this + 135);
          v12->bmiHeader.biHeight = biHeight;
        }
        if ( v25 == 961893977
          || v25 == 842094169
          || v25 == 842094158
          || v25 == 825316942
          || v25 == 808596553
          || v25 == 1448433993 )
        {
          v33 = -biHeight;
          if ( biHeight > 0 )
            v33 = biHeight;
          v31 = ((biWidth * v12->bmiHeader.biBitCount * v33) >> 31) & 7;
          v32 = biWidth * v12->bmiHeader.biBitCount * v33 / 8;
        }
        else
        {
          v30 = -biHeight;
          if ( biHeight > 0 )
            v30 = biHeight;
          v31 = ((biWidth * v12->bmiHeader.biBitCount / 8 + 3) >> 31) & 3;
          v32 = 4 * v30 * ((biWidth * v12->bmiHeader.biBitCount / 8 + 3) / 4);
        }
        v12->bmiHeader.biSizeImage = v32;
        a2->lSampleSize = v32;
        v12->bmiHeader.biClrUsed = 0;
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1
          && *(_QWORD *)a3->Data4 == *(_QWORD *)MEDIASUBTYPE_RGB565.Data4 )
        {
          v12[1].rcSource.left = 63488;
          v12[1].rcSource.top = 2016;
          v12[1].rcSource.right = 31;
        }
        if ( *(_QWORD *)&a2->formattype.Data1 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1
          && *(_QWORD *)a2->formattype.Data4 == *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
        {
          ConvertVIHToMFVideoFormat2((struct _MFVIDEOFORMAT *)a2->pbFormat, v12);
        }
        operator delete(v12, v31);
        return 0;
      }
      operator delete(v12, v11);
    }
    return -2147467259;
  }
  result = MoInitMediaType(a2, 0);
  if ( result < 0 )
    return result;
  a2->subtype = *a3;
  a2->majortype = MEDIATYPE_Video;
  *(_QWORD *)&a2->bFixedSizeSamples = 1;
  a2->lSampleSize = 0;
  a2->formattype = GUID_00000000_0000_0000_0000_000000000000;
  return 0;
}

```

## disassembly

```asm
0x180004fe0  mov     [rsp+arg_8], rbp
0x180004fe5  mov     [rsp+arg_10], rsi
0x180004fea  push    rdi
0x180004feb  push    r14
0x180004fed  push    r15
0x180004fef  sub     rsp, 20h
0x180004ff3  mov     rax, [r8]
0x180004ff6  mov     rbp, r9
0x180004ff9  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data1
0x180005000  mov     r14, r8
0x180005003  mov     rdi, rdx
0x180005006  mov     rsi, rcx
0x180005009  jnz     short loc_180005016
0x18000500b  mov     rax, [r8+8]
0x18000500f  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data4
0x180005016  test    rax, rax
0x180005019  setz    al
0x18000501c  neg     al
0x18000501e  mov     rax, [r8]
0x180005021  sbb     r15d, r15d
0x180005024  and     r15d, 0Ch
0x180005028  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data1
0x18000502f  jnz     short loc_18000503C
0x180005031  mov     rax, [r8+8]
0x180005035  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data4
0x18000503c  test    rax, rax
0x18000503f  mov     [rsp+38h+arg_0], rbx
0x180005044  mov     ecx, 400h
0x180005049  cmovz   r15d, ecx
0x18000504d  test    rbp, rbp
0x180005050  jz      loc_18000547F
0x180005056  mov     ecx, 458h; unsigned __int64
0x18000505b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005060  mov     rbx, rax
0x180005063  test    rax, rax
0x180005066  jz      loc_180005478
0x18000506c  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180005073  cmp     rax, [rbp+2Ch]
0x180005077  jnz     loc_18000516D
0x18000507d  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180005084  cmp     rax, [rbp+34h]
0x180005088  jnz     loc_18000516D
0x18000508e  lea     edx, [r15+0B0h]; cbFormat
0x180005095  mov     rcx, rdi; pmt
0x180005098  call    cs:__imp_MoInitMediaType
0x18000509e  mov     r15d, eax
0x1800050a1  test    eax, eax
0x1800050a3  jns     short loc_1800050B5
0x1800050a5  mov     rcx, rbx; void *
0x1800050a8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800050ad  mov     eax, r15d
0x1800050b0  jmp     loc_1800054BC
0x1800050b5  movups  xmm0, xmmword ptr [r14]
0x1800050b9  mov     rcx, [rdi+50h]
0x1800050bd  xor     r15d, r15d
0x1800050c0  movups  xmmword ptr [rdi+10h], xmm0
0x1800050c4  movups  xmm1, xmmword ptr cs:MEDIATYPE_Video.Data1
0x1800050cb  movups  xmmword ptr [rdi], xmm1
0x1800050ce  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800050d5  mov     qword ptr [rdi+20h], 1
0x1800050dd  mov     [rdi+28h], r15d
0x1800050e1  movups  xmmword ptr [rdi+2Ch], xmm0
0x1800050e5  mov     rax, [rbp+50h]
0x1800050e9  movups  xmm0, xmmword ptr [rax]
0x1800050ec  movups  xmmword ptr [rcx], xmm0
0x1800050ef  movups  xmm1, xmmword ptr [rax+10h]
0x1800050f3  movups  xmmword ptr [rcx+10h], xmm1
0x1800050f7  movups  xmm0, xmmword ptr [rax+20h]
0x1800050fb  movups  xmmword ptr [rcx+20h], xmm0
0x1800050ff  movups  xmm1, xmmword ptr [rax+30h]
0x180005103  movups  xmmword ptr [rcx+30h], xmm1
0x180005107  movups  xmm0, xmmword ptr [rax+40h]
0x18000510b  movups  xmmword ptr [rcx+40h], xmm0
0x18000510f  movups  xmm1, xmmword ptr [rax+50h]
0x180005113  movups  xmmword ptr [rcx+50h], xmm1
0x180005117  movups  xmm0, xmmword ptr [rax+60h]
0x18000511b  movups  xmmword ptr [rcx+60h], xmm0
0x18000511f  movups  xmm1, xmmword ptr [rax+70h]
0x180005123  movups  xmmword ptr [rcx+70h], xmm1
0x180005127  movups  xmm0, xmmword ptr [rax+80h]
0x18000512e  movups  xmmword ptr [rcx+80h], xmm0
0x180005135  movups  xmm1, xmmword ptr [rax+90h]
0x18000513c  movups  xmmword ptr [rcx+90h], xmm1
0x180005143  movups  xmm0, xmmword ptr [rax+0A0h]
0x18000514a  movups  xmmword ptr [rcx+0A0h], xmm0
0x180005151  mov     rdx, [rdi+50h]; struct _MFVIDEOFORMAT *
0x180005155  mov     rcx, rbx; struct tagVIDEOINFOHEADER *
0x180005158  movups  xmm1, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000515f  movups  xmmword ptr [rdi+2Ch], xmm1
0x180005163  call    ?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)
0x180005168  jmp     loc_1800052CA
0x18000516d  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180005174  cmp     rax, [rbp+2Ch]
0x180005178  jnz     loc_18000521B
0x18000517e  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180005185  cmp     rax, [rbp+34h]
0x180005189  jnz     loc_18000521B
0x18000518f  lea     edx, [r15+58h]; cbFormat
0x180005193  mov     rcx, rdi; pmt
0x180005196  call    cs:__imp_MoInitMediaType
0x18000519c  mov     r15d, eax
0x18000519f  test    eax, eax
0x1800051a1  js      loc_1800050A5
0x1800051a7  movups  xmm0, xmmword ptr [r14]
0x1800051ab  mov     rcx, [rdi+50h]
0x1800051af  xor     r15d, r15d
0x1800051b2  movups  xmmword ptr [rdi+10h], xmm0
0x1800051b6  movups  xmm1, xmmword ptr cs:MEDIATYPE_Video.Data1
0x1800051bd  movups  xmmword ptr [rdi], xmm1
0x1800051c0  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800051c7  mov     qword ptr [rdi+20h], 1
0x1800051cf  mov     [rdi+28h], r15d
0x1800051d3  movups  xmmword ptr [rdi+2Ch], xmm0
0x1800051d7  mov     rax, [rbp+50h]
0x1800051db  movups  xmm0, xmmword ptr [rax]
0x1800051de  movups  xmmword ptr [rcx], xmm0
0x1800051e1  movups  xmm1, xmmword ptr [rax+10h]
0x1800051e5  movups  xmmword ptr [rcx+10h], xmm1
0x1800051e9  movups  xmm0, xmmword ptr [rax+20h]
0x1800051ed  movups  xmmword ptr [rcx+20h], xmm0
0x1800051f1  movups  xmm1, xmmword ptr [rax+30h]
0x1800051f5  movups  xmmword ptr [rcx+30h], xmm1
0x1800051f9  movups  xmm0, xmmword ptr [rax+40h]
0x1800051fd  movups  xmmword ptr [rcx+40h], xmm0
0x180005201  movsd   xmm1, qword ptr [rax+50h]
0x180005206  movsd   qword ptr [rcx+50h], xmm1
0x18000520b  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180005212  movups  xmmword ptr [rdi+2Ch], xmm0
0x180005216  jmp     loc_1800052CA
0x18000521b  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180005222  cmp     rax, [rbp+2Ch]
0x180005226  jnz     loc_180005470
0x18000522c  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180005233  cmp     rax, [rbp+34h]
0x180005237  jnz     loc_180005470
0x18000523d  lea     edx, [r15+70h]; cbFormat
0x180005241  mov     rcx, rdi; pmt
0x180005244  call    cs:__imp_MoInitMediaType
0x18000524a  mov     r15d, eax
0x18000524d  test    eax, eax
0x18000524f  js      loc_1800050A5
0x180005255  movups  xmm0, xmmword ptr [r14]
0x180005259  mov     rcx, [rdi+50h]
0x18000525d  xor     r15d, r15d
0x180005260  movups  xmmword ptr [rdi+10h], xmm0
0x180005264  movups  xmm1, xmmword ptr cs:MEDIATYPE_Video.Data1
0x18000526b  movups  xmmword ptr [rdi], xmm1
0x18000526e  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180005275  mov     qword ptr [rdi+20h], 1
0x18000527d  mov     [rdi+28h], r15d
0x180005281  movups  xmmword ptr [rdi+2Ch], xmm0
0x180005285  mov     rax, [rbp+50h]
0x180005289  movups  xmm0, xmmword ptr [rax]
0x18000528c  movups  xmmword ptr [rcx], xmm0
0x18000528f  movups  xmm1, xmmword ptr [rax+10h]
0x180005293  movups  xmmword ptr [rcx+10h], xmm1
0x180005297  movups  xmm0, xmmword ptr [rax+20h]
0x18000529b  movups  xmmword ptr [rcx+20h], xmm0
0x18000529f  movups  xmm1, xmmword ptr [rax+30h]
0x1800052a3  movups  xmmword ptr [rcx+30h], xmm1
0x1800052a7  movups  xmm0, xmmword ptr [rax+40h]
0x1800052ab  movups  xmmword ptr [rcx+40h], xmm0
0x1800052af  movups  xmm1, xmmword ptr [rax+50h]
0x1800052b3  movups  xmmword ptr [rcx+50h], xmm1
0x1800052b7  movups  xmm0, xmmword ptr [rax+60h]
0x1800052bb  movups  xmmword ptr [rcx+60h], xmm0
0x1800052bf  movups  xmm1, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x1800052c6  movups  xmmword ptr [rdi+2Ch], xmm1
0x1800052ca  mov     rcx, r14
0x1800052cd  mov     [rbx+20h], r15d
0x1800052d1  mov     dword ptr [rbx+30h], 28h ; '('
0x1800052d8  call    BitCountFromSubtype
0x1800052dd  mov     [rbx+3Eh], ax
0x1800052e1  call    biCompressionFromSubtype
0x1800052e6  mov     [rbx+40h], eax
0x1800052e9  mov     r9d, eax
0x1800052ec  mov     ecx, [rsi+210h]
0x1800052f2  test    ecx, ecx
0x1800052f4  js      short loc_18000533A
0x1800052f6  cmp     dword ptr [rsi+214h], 0
0x1800052fd  jl      short loc_18000533A
0x1800052ff  mov     eax, [rsi+218h]
0x180005305  test    eax, eax
0x180005307  js      short loc_18000533A
0x180005309  cmp     dword ptr [rsi+21Ch], 0
0x180005310  jl      short loc_18000533A
0x180005312  lea     r10d, [rax+rcx]
0x180005316  mov     [rbx+34h], r10d
0x18000531a  mov     edx, [rsi+21Ch]
0x180005320  add     edx, [rsi+214h]
0x180005326  mov     r8d, edx
0x180005329  neg     r8d
0x18000532c  cmp     dword ptr [rbx+38h], 0
0x180005330  cmovge  r8d, edx
0x180005334  mov     [rbx+38h], r8d
0x180005338  jmp     short loc_180005387
0x18000533a  cmp     dword ptr [rsi+200h], 0
0x180005341  jl      short loc_18000537F
0x180005343  cmp     dword ptr [rsi+204h], 0
0x18000534a  jl      short loc_18000537F
0x18000534c  mov     r10d, [rsi+208h]
0x180005353  test    r10d, r10d
0x180005356  js      short loc_18000537F
0x180005358  cmp     dword ptr [rsi+20Ch], 0
0x18000535f  jl      short loc_18000537F
0x180005361  mov     [rbx+34h], r10d
0x180005365  mov     eax, [rsi+20Ch]
0x18000536b  mov     r8d, eax
0x18000536e  neg     r8d
0x180005371  cmp     dword ptr [rbx+38h], 0
0x180005375  cmovge  r8d, eax
0x180005379  mov     [rbx+38h], r8d
0x18000537d  jmp     short loc_180005387
0x18000537f  mov     r8d, [rbx+38h]
0x180005383  mov     r10d, [rbx+34h]
0x180005387  cmp     r9d, 39555659h
0x18000538e  jz      short loc_1800053EB
0x180005390  cmp     r9d, 32315659h
0x180005397  jz      short loc_1800053EB
0x180005399  cmp     r9d, 3231564Eh
0x1800053a0  jz      short loc_1800053EB
0x1800053a2  cmp     r9d, 3131564Eh
0x1800053a9  jz      short loc_1800053EB
0x1800053ab  cmp     r9d, 30323449h
0x1800053b2  jz      short loc_1800053EB
0x1800053b4  cmp     r9d, 56555949h
0x1800053bb  jz      short loc_1800053EB
0x1800053bd  movzx   eax, word ptr [rbx+3Eh]
0x1800053c1  mov     ecx, r8d
0x1800053c4  neg     ecx
0x1800053c6  cmovs   ecx, r8d
0x1800053ca  imul    eax, r10d
0x1800053ce  cdq
0x1800053cf  and     edx, 7
0x1800053d2  add     eax, edx
0x1800053d4  sar     eax, 3
0x1800053d7  add     eax, 3
0x1800053da  cdq
0x1800053db  and     edx, 3
0x1800053de  add     eax, edx
0x1800053e0  sar     eax, 2
0x1800053e3  imul    eax, ecx
0x1800053e6  shl     eax, 2
0x1800053e9  jmp     short loc_180005408
0x1800053eb  movzx   ecx, word ptr [rbx+3Eh]
0x1800053ef  mov     eax, r8d
0x1800053f2  neg     eax
0x1800053f4  cmovs   eax, r8d
0x1800053f8  imul    eax, ecx
0x1800053fb  imul    eax, r10d
0x1800053ff  cdq
0x180005400  and     edx, 7
0x180005403  add     eax, edx
0x180005405  sar     eax, 3
0x180005408  mov     [rbx+44h], eax
0x18000540b  mov     [rdi+28h], eax
0x18000540e  mov     [rbx+50h], r15d
0x180005412  mov     rax, [r14]
0x180005415  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data1
0x18000541c  jnz     short loc_180005440
0x18000541e  mov     rax, [r14+8]
0x180005422  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data4
0x180005429  jnz     short loc_180005440
0x18000542b  mov     dword ptr [rbx+58h], 0F800h
0x180005432  mov     dword ptr [rbx+5Ch], 7E0h
0x180005439  mov     dword ptr [rbx+60h], 1Fh
0x180005440  mov     rax, [rdi+2Ch]
0x180005444  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000544b  jnz     short loc_180005466
0x18000544d  mov     rax, [rdi+34h]
0x180005451  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180005458  jnz     short loc_180005466
0x18000545a  mov     rcx, [rdi+50h]; struct _MFVIDEOFORMAT *
0x18000545e  mov     rdx, rbx; struct tagVIDEOINFOHEADER *
0x180005461  call    ?ConvertVIHToMFVideoFormat2@@YAJPEAU_MFVIDEOFORMAT@@PEAUtagVIDEOINFOHEADER@@@Z; ConvertVIHToMFVideoFormat2(_MFVIDEOFORMAT *,tagVIDEOINFOHEADER *)
0x180005466  mov     rcx, rbx; void *
0x180005469  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000546e  jmp     short loc_1800054BA
0x180005470  mov     rcx, rbx; void *
0x180005473  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005478  mov     eax, 80004005h
0x18000547d  jmp     short loc_1800054BC
0x18000547f  xor     edx, edx; cbFormat
0x180005481  mov     rcx, rdi; pmt
0x180005484  call    cs:__imp_MoInitMediaType
0x18000548a  test    eax, eax
0x18000548c  js      short loc_1800054BC
0x18000548e  movups  xmm0, xmmword ptr [r14]
0x180005492  xor     r15d, r15d
0x180005495  movups  xmmword ptr [rdi+10h], xmm0
0x180005499  movups  xmm1, xmmword ptr cs:MEDIATYPE_Video.Data1
0x1800054a0  movups  xmmword ptr [rdi], xmm1
0x1800054a3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800054aa  mov     qword ptr [rdi+20h], 1
0x1800054b2  mov     [rdi+28h], r15d
0x1800054b6  movups  xmmword ptr [rdi+2Ch], xmm0
0x1800054ba  xor     eax, eax
0x1800054bc  mov     rbx, [rsp+38h+arg_0]
0x1800054c1  mov     rbp, [rsp+38h+arg_8]
0x1800054c6  mov     rsi, [rsp+38h+arg_10]
  ... truncated ...
```
