# CWMResizeDMO::SetInputType(ulong,_AMMediaType const *,ulong)

- ea: `0x180008680`
- end: `0x18000898e`
- name: `?SetInputType@CWMResizeDMO@@MEAAJKPEBU_AMMediaType@@K@Z`
- size: `782`
- prototype: `int(CWMResizeDMO *__hidden this, unsigned int, const struct _AMMediaType *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001968`
- `0x1800019b4`
- `0x180003570`
- `0x180005610`
- `0x180008680`
- `0x180008ed0`
- `0x180008f40`
- `0x180009170`
- `0x180011ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008712`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000874f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008773`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008924`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000895f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000896c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008712`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000874f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008773`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008924`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000895f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000896c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800086bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800086bc`
- `msdmo!MoCopyMediaType` at `0x1800088bf`
- `msdmo!MoCopyMediaType` at `0x1800088bf`
- `msdmo!MoFreeMediaType` at `0x1800086e1`
- `msdmo!MoFreeMediaType` at `0x180008833`
- `msdmo!MoFreeMediaType` at `0x1800086e1`
- `msdmo!MoFreeMediaType` at `0x180008833`

## pseudocode

```c
__int64 __fastcall CWMResizeDMO::SetInputType(CWMResizeDMO *this, int a2, const struct _AMMediaType *a3, char a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  const struct _GUID *const *v9; // rdx
  unsigned int v10; // r8d
  CWMResizeDMO *v11; // rcx
  int VIH; // esi
  __int64 v13; // r14
  int v14; // eax
  int v15; // r10d
  unsigned int v16; // edx
  WMSDKRESIZER *v17; // rcx
  WMSDKRESIZER *v18; // rcx
  int v19; // ecx
  unsigned __int64 v20; // rdx
  HRESULT v21; // ebp
  void *v22; // rcx
  int v23; // ecx
  void *v24; // rax
  int v25; // ecx

  if ( a2 )
    return 2147746305LL;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 392);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  if ( (a4 & 2) != 0 )
  {
    if ( !*((_DWORD *)this + 2) )
    {
      LeaveCriticalSection(v8);
      return 1;
    }
    if ( (a4 & 1) == 0 )
    {
      *((_DWORD *)this + 2) = 0;
      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
      LeaveCriticalSection(v8);
      return 0;
    }
LABEL_47:
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
                *((struct tagVIDEOINFOHEADER **)this + 145),
                (struct tagVIDEOINFOHEADER **)this + 144),
        VIH < 0) )
  {
    LeaveCriticalSection(v8);
    return (unsigned int)VIH;
  }
  v13 = *((_QWORD *)this + 144);
  if ( !IsValidBitmapInfoHeader((const struct tagBITMAPINFOHEADER *)(v13 + 48)) )
  {
    LeaveCriticalSection(v8);
    return 2147942487LL;
  }
  v14 = biCompressionFromSubtype(&a3->subtype);
  if ( v14 == v15 && (unsigned int)ValidImageSize(v15, *(_DWORD *)(v13 + 52), *(_DWORD *)(v13 + 56)) )
  {
    if ( (*(_QWORD *)&a3->formattype.Data1 != *(_QWORD *)&FORMAT_VideoInfo.Data1
       || *(_QWORD *)a3->formattype.Data4 != *(_QWORD *)FORMAT_VideoInfo.Data4)
      && *(_QWORD *)&a3->formattype.Data1 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1
      && *(_QWORD *)a3->formattype.Data4 == *(_QWORD *)FORMAT_MFVideoFormat.Data4
      && *((_DWORD *)a3->pbFormat + 7) != 2 )
    {
      *((_DWORD *)this + 114) = 1;
    }
    if ( !*((_DWORD *)this + 3)
      || *(_QWORD *)&a3->subtype.Data1 == *((_QWORD *)this + 15)
      && *(_QWORD *)a3->subtype.Data4 == *((_QWORD *)this + 16) )
    {
      *((_DWORD *)this + 115) = 1;
      if ( *((_DWORD *)this + 2) )
      {
        MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
        *((_DWORD *)this + 2) = 0;
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
      *((_DWORD *)this + 144) = *(_DWORD *)(v13 + 64);
      *((_DWORD *)this + 145) = (int)((*(_DWORD *)(v13 + 52) * *(unsigned __int16 *)(v13 + 62) + 31) & 0xFFFFFFE0) / 8;
      v19 = *(_DWORD *)(v13 + 56);
      if ( v19 <= 0 )
        *((_DWORD *)this + 142) = (v19 >= 0) - 1;
      else
        *((_DWORD *)this + 142) = 1;
      v21 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 16), a3);
      if ( v21 < 0 )
      {
        *((_QWORD *)this + 144) = 0;
        LeaveCriticalSection(v8);
        return (unsigned int)v21;
      }
      v22 = (void *)*((_QWORD *)this + 75);
      *((_DWORD *)this + 2) = 1;
      if ( v22 )
        operator delete(v22, v20);
      v23 = -(*(_DWORD *)(v13 + 52) * *(_DWORD *)(v13 + 56));
      if ( *(_DWORD *)(v13 + 52) * *(_DWORD *)(v13 + 56) > 0 )
        v23 = *(_DWORD *)(v13 + 52) * *(_DWORD *)(v13 + 56);
      v24 = operator new[](4 * v23);
      *((_QWORD *)this + 75) = v24;
      if ( !v24 )
      {
        LeaveCriticalSection(v8);
        return 2147500037LL;
      }
      if ( (*((_BYTE *)this + 496) & 1) == 0 )
      {
        *((_QWORD *)this + 58) = 0;
        *((_DWORD *)this + 118) = *(_DWORD *)(v13 + 52);
        v25 = -*(_DWORD *)(v13 + 56);
        if ( *(int *)(v13 + 56) > 0 )
          v25 = *(_DWORD *)(v13 + 56);
        *((_DWORD *)this + 119) = v25;
      }
      goto LABEL_47;
    }
  }
  LeaveCriticalSection(v8);
  return 2147746309LL;
}

```

## disassembly

```asm
0x180008680  push    rbx
0x180008682  push    rbp
0x180008683  push    rsi
0x180008684  sub     rsp, 20h
0x180008688  mov     esi, r9d
0x18000868b  mov     rbp, r8
0x18000868e  mov     rbx, rcx
0x180008691  cmp     edx, 1
0x180008694  jb      short loc_1800086A3
0x180008696  mov     eax, 80040201h
0x18000869b  add     rsp, 20h
0x18000869f  pop     rsi
0x1800086a0  pop     rbp
0x1800086a1  pop     rbx
0x1800086a2  retn
0x1800086a3  mov     [rsp+38h+arg_0], rdi
0x1800086a8  lea     rdi, [rcx+188h]
0x1800086af  mov     rcx, rdi; lpCriticalSection
0x1800086b2  mov     [rsp+38h+arg_8], r14
0x1800086b7  mov     [rsp+38h+arg_10], r15
0x1800086bc  call    cs:__imp_EnterCriticalSection
0x1800086c2  test    sil, 2
0x1800086c6  jz      short loc_18000870A
0x1800086c8  cmp     dword ptr [rbx+8], 0
0x1800086cc  jz      short loc_1800086F7
0x1800086ce  test    sil, 1
0x1800086d2  jnz     loc_18000895C
0x1800086d8  xor     esi, esi
0x1800086da  lea     rcx, [rbx+10h]; pmt
0x1800086de  mov     [rbx+8], esi
0x1800086e1  call    cs:__imp_MoFreeMediaType
0x1800086e7  mov     rcx, rdi; lpCriticalSection
0x1800086ea  call    cs:__imp_LeaveCriticalSection
0x1800086f0  xor     eax, eax
0x1800086f2  jmp     loc_180008977
0x1800086f7  mov     rcx, rdi; lpCriticalSection
0x1800086fa  call    cs:__imp_LeaveCriticalSection
0x180008700  mov     eax, 1
0x180008705  jmp     loc_180008977
0x18000870a  test    rbp, rbp
0x18000870d  jnz     short loc_180008722
0x18000870f  mov     rcx, rdi; lpCriticalSection
0x180008712  call    cs:__imp_LeaveCriticalSection
0x180008718  mov     eax, 80004003h
0x18000871d  jmp     loc_180008977
0x180008722  mov     rcx, rbp; struct _AMMediaType *
0x180008725  call    ?CheckType@@YAJPEBU_AMMediaType@@PEBQEBU_GUID@@I@Z; CheckType(_AMMediaType const *,_GUID const * const *,uint)
0x18000872a  mov     esi, eax
0x18000872c  test    eax, eax
0x18000872e  js      short loc_18000874C
0x180008730  mov     r8, [rbx+488h]; struct tagVIDEOINFOHEADER *
0x180008737  lea     r9, [rbx+480h]; struct tagVIDEOINFOHEADER **
0x18000873e  mov     rdx, rbp; struct _AMMediaType *
0x180008741  call    ?getVIH@CWMResizeDMO@@AEAAJPEBU_AMMediaType@@PEAUtagVIDEOINFOHEADER@@PEAPEAU3@@Z; CWMResizeDMO::getVIH(_AMMediaType const *,tagVIDEOINFOHEADER *,tagVIDEOINFOHEADER * *)
0x180008746  mov     esi, eax
0x180008748  test    eax, eax
0x18000874a  jns     short loc_18000875C
0x18000874c  mov     rcx, rdi; lpCriticalSection
0x18000874f  call    cs:__imp_LeaveCriticalSection
0x180008755  mov     eax, esi
0x180008757  jmp     loc_180008977
0x18000875c  mov     r14, [rbx+480h]
0x180008763  lea     rcx, [r14+30h]; struct tagBITMAPINFOHEADER *
0x180008767  call    ?IsValidBitmapInfoHeader@@YAHPEBUtagBITMAPINFOHEADER@@@Z; IsValidBitmapInfoHeader(tagBITMAPINFOHEADER const *)
0x18000876c  test    eax, eax
0x18000876e  jnz     short loc_180008783
0x180008770  mov     rcx, rdi; lpCriticalSection
0x180008773  call    cs:__imp_LeaveCriticalSection
0x180008779  mov     eax, 80070057h
0x18000877e  jmp     loc_180008977
0x180008783  mov     r10d, [r14+40h]
0x180008787  lea     rcx, [rbp+10h]
0x18000878b  call    biCompressionFromSubtype
0x180008790  cmp     eax, r10d
0x180008793  jnz     loc_180008969
0x180008799  mov     edx, [r14+34h]; int
0x18000879d  mov     ecx, r10d; unsigned int
0x1800087a0  mov     r8d, [r14+38h]; int
0x1800087a4  call    ?ValidImageSize@@YAHKJJ@Z; ValidImageSize(ulong,long,long)
0x1800087a9  test    eax, eax
0x1800087ab  jz      loc_180008969
0x1800087b1  mov     rax, [rbp+2Ch]
0x1800087b5  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800087bc  jnz     short loc_1800087CB
0x1800087be  mov     rax, [rbp+34h]
0x1800087c2  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800087c9  jz      short loc_1800087F9
0x1800087cb  mov     rax, [rbp+2Ch]
0x1800087cf  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800087d6  jnz     short loc_1800087F9
0x1800087d8  mov     rax, [rbp+34h]
0x1800087dc  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x1800087e3  jnz     short loc_1800087F9
0x1800087e5  mov     rax, [rbp+50h]
0x1800087e9  cmp     dword ptr [rax+1Ch], 2
0x1800087ed  jz      short loc_1800087F9
0x1800087ef  mov     dword ptr [rbx+1C8h], 1
0x1800087f9  cmp     dword ptr [rbx+0Ch], 0
0x1800087fd  jz      short loc_18000881E
0x1800087ff  mov     rax, [rbp+10h]
0x180008803  cmp     rax, [rbx+78h]
0x180008807  jnz     loc_180008969
0x18000880d  mov     rax, [rbp+18h]
0x180008811  cmp     rax, [rbx+80h]
0x180008818  jnz     loc_180008969
0x18000881e  xor     esi, esi
0x180008820  mov     dword ptr [rbx+1CCh], 1
0x18000882a  cmp     [rbx+8], esi
0x18000882d  jz      short loc_18000883C
0x18000882f  lea     rcx, [rbx+10h]; pmt
0x180008833  call    cs:__imp_MoFreeMediaType
0x180008839  mov     [rbx+8], esi
0x18000883c  mov     rcx, [rbx+1B0h]; this
0x180008843  test    rcx, rcx
0x180008846  jz      short loc_180008854
0x180008848  call    ??_GWMSDKRESIZER@@QEAAPEAXI@Z; WMSDKRESIZER::`scalar deleting destructor'(uint)
0x18000884d  mov     [rbx+1B0h], rsi
0x180008854  mov     rcx, [rbx+1C0h]; this
0x18000885b  test    rcx, rcx
0x18000885e  jz      short loc_18000886C
0x180008860  call    ??_GWMSDKRESIZER@@QEAAPEAXI@Z; WMSDKRESIZER::`scalar deleting destructor'(uint)
0x180008865  mov     [rbx+1C0h], rsi
0x18000886c  mov     eax, [r14+40h]
0x180008870  mov     [rbx+240h], eax
0x180008876  movzx   eax, word ptr [r14+3Eh]
0x18000887b  imul    eax, [r14+34h]
0x180008880  add     eax, 1Fh
0x180008883  and     eax, 0FFFFFFE0h
0x180008886  cdq
0x180008887  and     edx, 7
0x18000888a  add     eax, edx
0x18000888c  sar     eax, 3
0x18000888f  mov     [rbx+244h], eax
0x180008895  mov     ecx, [r14+38h]
0x180008899  test    ecx, ecx
0x18000889b  jle     short loc_1800088A9
0x18000889d  mov     dword ptr [rbx+238h], 1
0x1800088a7  jmp     short loc_1800088B8
0x1800088a9  test    ecx, ecx
0x1800088ab  mov     eax, esi
0x1800088ad  setns   al
0x1800088b0  dec     eax
0x1800088b2  mov     [rbx+238h], eax
0x1800088b8  lea     rcx, [rbx+10h]; pmtDest
0x1800088bc  mov     rdx, rbp; pmtSrc
0x1800088bf  call    cs:__imp_MoCopyMediaType
0x1800088c5  mov     ebp, eax
0x1800088c7  test    eax, eax
0x1800088c9  jns     short loc_1800088E2
0x1800088cb  mov     rcx, rdi; lpCriticalSection
0x1800088ce  mov     [rbx+480h], rsi
0x1800088d5  call    cs:__imp_LeaveCriticalSection
0x1800088db  mov     eax, ebp
0x1800088dd  jmp     loc_180008977
0x1800088e2  mov     rcx, [rbx+258h]; void *
0x1800088e9  mov     dword ptr [rbx+8], 1
0x1800088f0  test    rcx, rcx
0x1800088f3  jz      short loc_1800088FA
0x1800088f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800088fa  mov     eax, [r14+38h]
0x1800088fe  imul    eax, [r14+34h]
0x180008903  mov     ecx, eax
0x180008905  neg     ecx
0x180008907  cmovs   ecx, eax
0x18000890a  shl     ecx, 2
0x18000890d  movsxd  rcx, ecx; unsigned __int64
0x180008910  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008915  mov     [rbx+258h], rax
0x18000891c  test    rax, rax
0x18000891f  jnz     short loc_180008931
0x180008921  mov     rcx, rdi; lpCriticalSection
0x180008924  call    cs:__imp_LeaveCriticalSection
0x18000892a  mov     eax, 80004005h
0x18000892f  jmp     short loc_180008977
0x180008931  test    byte ptr [rbx+1F0h], 1
0x180008938  jnz     short loc_18000895C
0x18000893a  mov     [rbx+1D0h], rsi
0x180008941  mov     eax, [r14+34h]
0x180008945  mov     [rbx+1D8h], eax
0x18000894b  mov     ecx, [r14+38h]
0x18000894f  neg     ecx
0x180008951  cmovs   ecx, [r14+38h]
0x180008956  mov     [rbx+1DCh], ecx
0x18000895c  mov     rcx, rdi; lpCriticalSection
0x18000895f  call    cs:__imp_LeaveCriticalSection
0x180008965  xor     eax, eax
0x180008967  jmp     short loc_180008977
0x180008969  mov     rcx, rdi; lpCriticalSection
0x18000896c  call    cs:__imp_LeaveCriticalSection
0x180008972  mov     eax, 80040205h
0x180008977  mov     r14, [rsp+38h+arg_8]
0x18000897c  mov     rdi, [rsp+38h+arg_0]
0x180008981  mov     r15, [rsp+38h+arg_10]
0x180008986  add     rsp, 20h
0x18000898a  pop     rsi
0x18000898b  pop     rbp
0x18000898c  pop     rbx
0x18000898d  retn
```
