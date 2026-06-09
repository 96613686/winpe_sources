# CWMResizeDMO::SetOutputType(ulong,_AMMediaType const *,ulong)

- ea: `0x1800089b0`
- end: `0x180008e84`
- name: `?SetOutputType@CWMResizeDMO@@MEAAJKPEBU_AMMediaType@@K@Z`
- size: `1236`
- prototype: `__int64 __fastcall(CWMResizeDMO *this, int, const struct _AMMediaType *, char)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001968`
- `0x1800019b4`
- `0x180003570`
- `0x180005610`
- `0x1800089b0`
- `0x180008ed0`
- `0x180008f40`
- `0x180009170`
- `0x180011ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008aa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008bb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008aa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008bb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800089f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800089f1`
- `msdmo!MoCopyMediaType` at `0x180008b9f`
- `msdmo!MoCopyMediaType` at `0x180008b9f`
- `msdmo!MoFreeMediaType` at `0x180008a16`
- `msdmo!MoFreeMediaType` at `0x180008b1d`
- `msdmo!MoFreeMediaType` at `0x180008a16`
- `msdmo!MoFreeMediaType` at `0x180008b1d`

## pseudocode

```c
__int64 __fastcall CWMResizeDMO::SetOutputType(CWMResizeDMO *this, int a2, const struct _AMMediaType *a3, char a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  const struct _GUID *const *v9; // rdx
  unsigned int v10; // r8d
  CWMResizeDMO *v11; // rcx
  int VIH; // ebp
  __int64 v13; // r14
  int v14; // eax
  unsigned int v15; // r10d
  unsigned int v16; // edx
  WMSDKRESIZER *v17; // rcx
  WMSDKRESIZER *v18; // rcx
  int v19; // ecx
  _DWORD *v20; // rdx
  HRESULT v21; // r15d
  int v22; // ecx
  _OWORD *v23; // r9
  int v24; // ecx
  _OWORD *v25; // r8
  int v26; // ecx
  int v27; // ecx
  int v28; // eax
  _QWORD *v29; // rcx
  void *v30; // rcx
  int v31; // ecx
  void *v32; // rax
  int v33; // ecx

  if ( a2 )
    return 2147746305LL;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 392);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  if ( (a4 & 2) != 0 )
  {
    if ( !*((_DWORD *)this + 3) )
    {
      LeaveCriticalSection(v8);
      return 1;
    }
    if ( (a4 & 1) == 0 )
    {
      *((_DWORD *)this + 3) = 0;
      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
      LeaveCriticalSection(v8);
      return 0;
    }
LABEL_55:
    LeaveCriticalSection(v8);
    return 0;
  }
  if ( !a3 )
  {
    LeaveCriticalSection(v8);
    return 2147500035LL;
  }
  VIH = CheckType(a3, v9, v10);
  if ( VIH < 0
    || (VIH = CWMResizeDMO::getVIH(
                v11,
                a3,
                *((struct tagVIDEOINFOHEADER **)this + 147),
                (struct tagVIDEOINFOHEADER **)this + 146),
        VIH < 0) )
  {
    LeaveCriticalSection(v8);
    return (unsigned int)VIH;
  }
  v13 = *((_QWORD *)this + 146);
  if ( !(unsigned int)IsValidBitmapInfoHeader((const struct tagBITMAPINFOHEADER *)(v13 + 48)) )
  {
    LeaveCriticalSection(v8);
    return 2147942487LL;
  }
  v14 = biCompressionFromSubtype(&a3->subtype);
  if ( v14 == v15
    && (unsigned int)ValidImageSize(v15, *(_DWORD *)(v13 + 52), *(_DWORD *)(v13 + 56))
    && (!*((_DWORD *)this + 2)
     || *(_QWORD *)&a3->subtype.Data1 == *((_QWORD *)this + 4) && *(_QWORD *)a3->subtype.Data4 == *((_QWORD *)this + 5)) )
  {
    *((_DWORD *)this + 115) = 1;
    if ( *((_DWORD *)this + 3) )
    {
      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
      *((_DWORD *)this + 3) = 0;
    }
    v17 = (WMSDKRESIZER *)*((_QWORD *)this + 54);
    if ( v17 )
    {
      WMSDKRESIZER::`scalar deleting destructor'(v17, v16);
      *((_QWORD *)this + 54) = 0;
    }
    v18 = (WMSDKRESIZER *)*((_QWORD *)this + 56);
    if ( v18 )
    {
      WMSDKRESIZER::`scalar deleting destructor'(v18, v16);
      *((_QWORD *)this + 56) = 0;
    }
    *((_DWORD *)this + 146) = (int)((*(_DWORD *)(v13 + 52) * *(unsigned __int16 *)(v13 + 62) + 31) & 0xFFFFFFE0) / 8;
    v19 = *(_DWORD *)(v13 + 56);
    if ( v19 <= 0 )
      *((_DWORD *)this + 143) = (v19 >= 0) - 1;
    else
      *((_DWORD *)this + 143) = 1;
    v21 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 104), a3);
    if ( v21 < 0 )
    {
      *((_QWORD *)this + 146) = 0;
      LeaveCriticalSection(v8);
      return (unsigned int)v21;
    }
    *((_DWORD *)this + 3) = 1;
    if ( (*(_QWORD *)&a3->formattype.Data1 != *(_QWORD *)&FORMAT_VideoInfo.Data1
       || *(_QWORD *)a3->formattype.Data4 != *(_QWORD *)FORMAT_VideoInfo.Data4)
      && *(_QWORD *)&a3->formattype.Data1 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1
      && *(_QWORD *)a3->formattype.Data4 == *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
    {
      v20 = (_DWORD *)((char *)this + 1468);
      if ( *((int *)this + 129) >= 4 )
      {
        *((_DWORD *)this + 319) = *((_DWORD *)this + 125);
        v22 = *((_DWORD *)this + 126);
        *((_WORD *)this + 641) = HIWORD(v22);
        *((_DWORD *)this + 321) = *((_DWORD *)this + 127);
        *((_DWORD *)this + 322) = *((_DWORD *)this + 128);
        *((_WORD *)this + 640) = v22;
        *(_OWORD *)((char *)this + 244) = *(_OWORD *)((char *)this + 1276);
        *v20 = 1;
      }
      v23 = (_OWORD *)((char *)this + 260);
      if ( *((int *)this + 134) >= 4 )
      {
        *((_DWORD *)this + 323) = *((_DWORD *)this + 130);
        v24 = *((_DWORD *)this + 131);
        *((_WORD *)this + 649) = HIWORD(v24);
        *((_DWORD *)this + 325) = *((_DWORD *)this + 132);
        *((_DWORD *)this + 326) = *((_DWORD *)this + 133);
        *((_WORD *)this + 648) = v24;
        *v23 = *(_OWORD *)((char *)this + 1292);
        *v20 = 1;
      }
      v25 = (_OWORD *)((char *)this + 276);
      if ( *((int *)this + 139) >= 4 )
      {
        *((_DWORD *)this + 327) = *((_DWORD *)this + 135);
        v26 = *((_DWORD *)this + 136);
        *((_WORD *)this + 657) = HIWORD(v26);
        *((_DWORD *)this + 329) = *((_DWORD *)this + 137);
        *((_DWORD *)this + 330) = *((_DWORD *)this + 138);
        *((_WORD *)this + 656) = v26;
        *v25 = *(_OWORD *)((char *)this + 1308);
        *v20 = 1;
      }
      if ( *((int *)this + 141) <= 0 )
      {
        v29 = (_QWORD *)((char *)this + 200);
      }
      else
      {
        v27 = *((_DWORD *)this + 140);
        *((_DWORD *)this + 308) = HIWORD(v27);
        v28 = (unsigned __int16)v27;
        v29 = (_QWORD *)((char *)this + 200);
        *((_DWORD *)this + 309) = v28;
        *((_QWORD *)this + 25) = *((_QWORD *)this + 154);
        *v20 = 1;
      }
      *((_QWORD *)this + 175) = *v29;
      *((_DWORD *)this + 352) = *((_DWORD *)this + 53);
      *(_OWORD *)((char *)this + 1412) = *v25;
      *(_OWORD *)((char *)this + 1428) = *v23;
      *((_QWORD *)this + 181) = *((_QWORD *)this + 37);
      *((_DWORD *)this + 364) = *((_DWORD *)this + 87);
    }
    v30 = (void *)*((_QWORD *)this + 76);
    if ( v30 )
      operator delete(v30, (unsigned __int64)v20);
    v31 = -(*(_DWORD *)(v13 + 52) * *(_DWORD *)(v13 + 56));
    if ( *(_DWORD *)(v13 + 52) * *(_DWORD *)(v13 + 56) > 0 )
      v31 = *(_DWORD *)(v13 + 52) * *(_DWORD *)(v13 + 56);
    v32 = operator new[](4 * v31);
    *((_QWORD *)this + 76) = v32;
    if ( !v32 )
    {
      LeaveCriticalSection(v8);
      return 2147500037LL;
    }
    if ( (*((_BYTE *)this + 496) & 2) == 0 )
    {
      *((_QWORD *)this + 60) = 0;
      *((_DWORD *)this + 122) = *(_DWORD *)(v13 + 52);
      v33 = -*(_DWORD *)(v13 + 56);
      if ( *(int *)(v13 + 56) > 0 )
        v33 = *(_DWORD *)(v13 + 56);
      *((_DWORD *)this + 123) = v33;
    }
    goto LABEL_55;
  }
  LeaveCriticalSection(v8);
  return 2147746309LL;
}

```

## disassembly

```asm
0x1800089b0  push    rbx
0x1800089b2  push    rbp
0x1800089b3  push    rsi
0x1800089b4  sub     rsp, 20h
0x1800089b8  mov     ebp, r9d
0x1800089bb  mov     rsi, r8
0x1800089be  mov     rbx, rcx
0x1800089c1  cmp     edx, 1
0x1800089c4  jb      short loc_1800089D3
0x1800089c6  mov     eax, 80040201h
0x1800089cb  add     rsp, 20h
0x1800089cf  pop     rsi
0x1800089d0  pop     rbp
0x1800089d1  pop     rbx
0x1800089d2  retn
0x1800089d3  mov     [rsp+38h+arg_0], rdi
0x1800089d8  lea     rdi, [rcx+188h]
0x1800089df  mov     [rsp+38h+arg_8], r12
0x1800089e4  mov     rcx, rdi; lpCriticalSection
0x1800089e7  mov     [rsp+38h+arg_10], r14
0x1800089ec  mov     [rsp+38h+arg_18], r15
0x1800089f1  call    cs:__imp_EnterCriticalSection
0x1800089f7  test    bpl, 2
0x1800089fb  jz      short loc_180008A3F
0x1800089fd  cmp     dword ptr [rbx+0Ch], 0
0x180008a01  jz      short loc_180008A2C
0x180008a03  test    bpl, 1
0x180008a07  jnz     loc_180008E4D
0x180008a0d  xor     ebp, ebp
0x180008a0f  lea     rcx, [rbx+68h]; pmt
0x180008a13  mov     [rbx+0Ch], ebp
0x180008a16  call    cs:__imp_MoFreeMediaType
0x180008a1c  mov     rcx, rdi; lpCriticalSection
0x180008a1f  call    cs:__imp_LeaveCriticalSection
0x180008a25  xor     eax, eax
0x180008a27  jmp     loc_180008E68
0x180008a2c  mov     rcx, rdi; lpCriticalSection
0x180008a2f  call    cs:__imp_LeaveCriticalSection
0x180008a35  mov     eax, 1
0x180008a3a  jmp     loc_180008E68
0x180008a3f  test    rsi, rsi
0x180008a42  jnz     short loc_180008A57
0x180008a44  mov     rcx, rdi; lpCriticalSection
0x180008a47  call    cs:__imp_LeaveCriticalSection
0x180008a4d  mov     eax, 80004003h
0x180008a52  jmp     loc_180008E68
0x180008a57  mov     rcx, rsi; struct _AMMediaType *
0x180008a5a  call    ?CheckType@@YAJPEBU_AMMediaType@@PEBQEBU_GUID@@I@Z; CheckType(_AMMediaType const *,_GUID const * const *,uint)
0x180008a5f  mov     ebp, eax
0x180008a61  test    eax, eax
0x180008a63  js      short loc_180008A81
0x180008a65  mov     r8, [rbx+498h]; struct tagVIDEOINFOHEADER *
0x180008a6c  lea     r9, [rbx+490h]; struct tagVIDEOINFOHEADER **
0x180008a73  mov     rdx, rsi; struct _AMMediaType *
0x180008a76  call    ?getVIH@CWMResizeDMO@@AEAAJPEBU_AMMediaType@@PEAUtagVIDEOINFOHEADER@@PEAPEAU3@@Z; CWMResizeDMO::getVIH(_AMMediaType const *,tagVIDEOINFOHEADER *,tagVIDEOINFOHEADER * *)
0x180008a7b  mov     ebp, eax
0x180008a7d  test    eax, eax
0x180008a7f  jns     short loc_180008A91
0x180008a81  mov     rcx, rdi; lpCriticalSection
0x180008a84  call    cs:__imp_LeaveCriticalSection
0x180008a8a  mov     eax, ebp
0x180008a8c  jmp     loc_180008E68
0x180008a91  mov     r14, [rbx+490h]
0x180008a98  lea     rcx, [r14+30h]; struct tagBITMAPINFOHEADER *
0x180008a9c  call    ?IsValidBitmapInfoHeader@@YAHPEBUtagBITMAPINFOHEADER@@@Z; IsValidBitmapInfoHeader(tagBITMAPINFOHEADER const *)
0x180008aa1  test    eax, eax
0x180008aa3  jnz     short loc_180008AB8
0x180008aa5  mov     rcx, rdi; lpCriticalSection
0x180008aa8  call    cs:__imp_LeaveCriticalSection
0x180008aae  mov     eax, 80070057h
0x180008ab3  jmp     loc_180008E68
0x180008ab8  mov     r10d, [r14+40h]
0x180008abc  lea     rcx, [rsi+10h]
0x180008ac0  call    biCompressionFromSubtype
0x180008ac5  cmp     eax, r10d
0x180008ac8  jnz     loc_180008E5A
0x180008ace  mov     edx, [r14+34h]; int
0x180008ad2  mov     ecx, r10d; unsigned int
0x180008ad5  mov     r8d, [r14+38h]; int
0x180008ad9  call    ?ValidImageSize@@YAHKJJ@Z; ValidImageSize(ulong,long,long)
0x180008ade  test    eax, eax
0x180008ae0  jz      loc_180008E5A
0x180008ae6  cmp     dword ptr [rbx+8], 0
0x180008aea  jz      short loc_180008B08
0x180008aec  mov     rax, [rsi+10h]
0x180008af0  cmp     rax, [rbx+20h]
0x180008af4  jnz     loc_180008E5A
0x180008afa  mov     rax, [rsi+18h]
0x180008afe  cmp     rax, [rbx+28h]
0x180008b02  jnz     loc_180008E5A
0x180008b08  xor     ebp, ebp
0x180008b0a  mov     dword ptr [rbx+1CCh], 1
0x180008b14  cmp     [rbx+0Ch], ebp
0x180008b17  jz      short loc_180008B26
0x180008b19  lea     rcx, [rbx+68h]; pmt
0x180008b1d  call    cs:__imp_MoFreeMediaType
0x180008b23  mov     [rbx+0Ch], ebp
0x180008b26  mov     rcx, [rbx+1B0h]; this
0x180008b2d  test    rcx, rcx
0x180008b30  jz      short loc_180008B3E
0x180008b32  call    ??_GWMSDKRESIZER@@QEAAPEAXI@Z; WMSDKRESIZER::`scalar deleting destructor'(uint)
0x180008b37  mov     [rbx+1B0h], rbp
0x180008b3e  mov     rcx, [rbx+1C0h]; this
0x180008b45  test    rcx, rcx
0x180008b48  jz      short loc_180008B56
0x180008b4a  call    ??_GWMSDKRESIZER@@QEAAPEAXI@Z; WMSDKRESIZER::`scalar deleting destructor'(uint)
0x180008b4f  mov     [rbx+1C0h], rbp
0x180008b56  movzx   eax, word ptr [r14+3Eh]
0x180008b5b  imul    eax, [r14+34h]
0x180008b60  add     eax, 1Fh
0x180008b63  and     eax, 0FFFFFFE0h
0x180008b66  cdq
0x180008b67  and     edx, 7
0x180008b6a  add     eax, edx
0x180008b6c  sar     eax, 3
0x180008b6f  mov     [rbx+248h], eax
0x180008b75  mov     ecx, [r14+38h]
0x180008b79  test    ecx, ecx
0x180008b7b  jle     short loc_180008B89
0x180008b7d  mov     dword ptr [rbx+23Ch], 1
0x180008b87  jmp     short loc_180008B98
0x180008b89  test    ecx, ecx
0x180008b8b  mov     eax, ebp
0x180008b8d  setns   al
0x180008b90  dec     eax
0x180008b92  mov     [rbx+23Ch], eax
0x180008b98  lea     rcx, [rbx+68h]; pmtDest
0x180008b9c  mov     rdx, rsi; pmtSrc
0x180008b9f  call    cs:__imp_MoCopyMediaType
0x180008ba5  mov     r15d, eax
0x180008ba8  test    eax, eax
0x180008baa  jns     short loc_180008BC4
0x180008bac  mov     rcx, rdi; lpCriticalSection
0x180008baf  mov     [rbx+490h], rbp
0x180008bb6  call    cs:__imp_LeaveCriticalSection
0x180008bbc  mov     eax, r15d
0x180008bbf  jmp     loc_180008E68
0x180008bc4  mov     dword ptr [rbx+0Ch], 1
0x180008bcb  mov     rax, [rsi+2Ch]
0x180008bcf  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180008bd6  jnz     short loc_180008BE9
0x180008bd8  mov     rax, [rsi+34h]
0x180008bdc  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180008be3  jz      loc_180008DDA
0x180008be9  mov     rax, [rsi+2Ch]
0x180008bed  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180008bf4  jnz     loc_180008DDA
0x180008bfa  mov     rax, [rsi+34h]
0x180008bfe  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180008c05  jnz     loc_180008DDA
0x180008c0b  cmp     dword ptr [rbx+204h], 4
0x180008c12  lea     rdx, [rbx+5BCh]; unsigned __int64
0x180008c19  jl      short loc_180008C79
0x180008c1b  mov     ecx, [rbx+1F4h]
0x180008c21  mov     eax, ecx
0x180008c23  sar     eax, 10h
0x180008c26  mov     [rbx+4FEh], ax
0x180008c2d  mov     [rbx+4FCh], cx
0x180008c34  mov     ecx, [rbx+1F8h]
0x180008c3a  mov     eax, ecx
0x180008c3c  sar     eax, 10h
0x180008c3f  mov     [rbx+502h], ax
0x180008c46  mov     eax, [rbx+1FCh]
0x180008c4c  mov     [rbx+504h], eax
0x180008c52  mov     eax, [rbx+200h]
0x180008c58  mov     [rbx+508h], eax
0x180008c5e  mov     [rbx+500h], cx
0x180008c65  movups  xmm0, xmmword ptr [rbx+4FCh]
0x180008c6c  movups  xmmword ptr [rbx+0F4h], xmm0
0x180008c73  mov     dword ptr [rdx], 1
0x180008c79  cmp     dword ptr [rbx+218h], 4
0x180008c80  lea     r9, [rbx+104h]
0x180008c87  jl      short loc_180008CE4
0x180008c89  mov     ecx, [rbx+208h]
0x180008c8f  mov     eax, ecx
0x180008c91  sar     eax, 10h
0x180008c94  mov     [rbx+50Eh], ax
0x180008c9b  mov     [rbx+50Ch], cx
0x180008ca2  mov     ecx, [rbx+20Ch]
0x180008ca8  mov     eax, ecx
0x180008caa  sar     eax, 10h
0x180008cad  mov     [rbx+512h], ax
0x180008cb4  mov     eax, [rbx+210h]
0x180008cba  mov     [rbx+514h], eax
0x180008cc0  mov     eax, [rbx+214h]
0x180008cc6  mov     [rbx+518h], eax
0x180008ccc  mov     [rbx+510h], cx
0x180008cd3  movups  xmm0, xmmword ptr [rbx+50Ch]
0x180008cda  movups  xmmword ptr [r9], xmm0
0x180008cde  mov     dword ptr [rdx], 1
0x180008ce4  cmp     dword ptr [rbx+22Ch], 4
0x180008ceb  lea     r8, [rbx+114h]
0x180008cf2  jl      short loc_180008D4F
0x180008cf4  mov     ecx, [rbx+21Ch]
0x180008cfa  mov     eax, ecx
0x180008cfc  sar     eax, 10h
0x180008cff  mov     [rbx+51Eh], ax
0x180008d06  mov     [rbx+51Ch], cx
0x180008d0d  mov     ecx, [rbx+220h]
0x180008d13  mov     eax, ecx
0x180008d15  sar     eax, 10h
0x180008d18  mov     [rbx+522h], ax
0x180008d1f  mov     eax, [rbx+224h]
0x180008d25  mov     [rbx+524h], eax
0x180008d2b  mov     eax, [rbx+228h]
0x180008d31  mov     [rbx+528h], eax
0x180008d37  mov     [rbx+520h], cx
0x180008d3e  movups  xmm0, xmmword ptr [rbx+51Ch]
0x180008d45  movups  xmmword ptr [r8], xmm0
0x180008d49  mov     dword ptr [rdx], 1
0x180008d4f  cmp     [rbx+234h], ebp
0x180008d55  jle     short loc_180008D8D
0x180008d57  mov     ecx, [rbx+230h]
0x180008d5d  mov     eax, ecx
0x180008d5f  sar     eax, 10h
0x180008d62  movzx   eax, ax
0x180008d65  mov     [rbx+4D0h], eax
0x180008d6b  movzx   eax, cx
0x180008d6e  lea     rcx, [rbx+0C8h]
0x180008d75  mov     [rbx+4D4h], eax
0x180008d7b  mov     rax, [rbx+4D0h]
0x180008d82  mov     [rcx], rax
0x180008d85  mov     dword ptr [rdx], 1
0x180008d8b  jmp     short loc_180008D94
0x180008d8d  lea     rcx, [rbx+0C8h]
0x180008d94  mov     rax, [rcx]
0x180008d97  mov     [rbx+578h], rax
0x180008d9e  mov     eax, [rbx+0D4h]
0x180008da4  mov     [rbx+580h], eax
0x180008daa  movups  xmm0, xmmword ptr [r8]
0x180008dae  movups  xmmword ptr [rbx+584h], xmm0
0x180008db5  movups  xmm0, xmmword ptr [r9]
0x180008db9  movups  xmmword ptr [rbx+594h], xmm0
0x180008dc0  mov     rax, [rbx+128h]
0x180008dc7  mov     [rbx+5A8h], rax
0x180008dce  mov     eax, [rbx+15Ch]
0x180008dd4  mov     [rbx+5B0h], eax
0x180008dda  mov     rcx, [rbx+260h]; void *
0x180008de1  test    rcx, rcx
0x180008de4  jz      short loc_180008DEB
0x180008de6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008deb  mov     eax, [r14+38h]
0x180008def  imul    eax, [r14+34h]
0x180008df4  mov     ecx, eax
0x180008df6  neg     ecx
0x180008df8  cmovs   ecx, eax
0x180008dfb  shl     ecx, 2
0x180008dfe  movsxd  rcx, ecx; unsigned __int64
0x180008e01  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008e06  mov     [rbx+260h], rax
0x180008e0d  test    rax, rax
0x180008e10  jnz     short loc_180008E22
0x180008e12  mov     rcx, rdi; lpCriticalSection
0x180008e15  call    cs:__imp_LeaveCriticalSection
0x180008e1b  mov     eax, 80004005h
0x180008e20  jmp     short loc_180008E68
0x180008e22  test    byte ptr [rbx+1F0h], 2
0x180008e29  jnz     short loc_180008E4D
0x180008e2b  mov     [rbx+1E0h], rbp
0x180008e32  mov     eax, [r14+34h]
0x180008e36  mov     [rbx+1E8h], eax
0x180008e3c  mov     ecx, [r14+38h]
0x180008e40  neg     ecx
0x180008e42  cmovs   ecx, [r14+38h]
0x180008e47  mov     [rbx+1ECh], ecx
0x180008e4d  mov     rcx, rdi; lpCriticalSection
0x180008e50  call    cs:__imp_LeaveCriticalSection
0x180008e56  xor     eax, eax
0x180008e58  jmp     short loc_180008E68
0x180008e5a  mov     rcx, rdi; lpCriticalSection
0x180008e5d  call    cs:__imp_LeaveCriticalSection
0x180008e63  mov     eax, 80040205h
0x180008e68  mov     r14, [rsp+38h+arg_10]
0x180008e6d  mov     r12, [rsp+38h+arg_8]
0x180008e72  mov     rdi, [rsp+38h+arg_0]
0x180008e77  mov     r15, [rsp+38h+arg_18]
0x180008e7c  add     rsp, 20h
0x180008e80  pop     rsi
0x180008e81  pop     rbp
0x180008e82  pop     rbx
0x180008e83  retn
```
