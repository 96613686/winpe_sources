# CSBE2Crossbar::SetReaderProfile(CDVRReaderProfile *)

- ea: `0x180038180`
- end: `0x18003881c`
- name: `?SetReaderProfile@CSBE2Crossbar@@UEAAJPEAVCDVRReaderProfile@@@Z`
- size: `1692`
- prototype: `__int64 __fastcall(CSBE2Crossbar *__hidden this, struct CDVRReaderProfile *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001c00`
- `0x18000256c`
- `0x180006944`
- `0x180006af8`
- `0x180006c04`
- `0x180006c44`
- `0x180006c8c`
- `0x180006f64`
- `0x180029ea4`
- `0x180033bdc`
- `0x180036fa8`
- `0x180038180`
- `0x18004fe98`
- `0x18004feb0`
- `0x1800b33ed`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800387da`
- `KERNEL32!LeaveCriticalSection` at `0x1800387da`
- `KERNEL32!EnterCriticalSection` at `0x1800381fd`
- `KERNEL32!EnterCriticalSection` at `0x1800381fd`
- `ole32!CoCreateInstance` at `0x180038437`
- `ole32!CoCreateInstance` at `0x180038437`

## pseudocode

```c
__int64 __fastcall CSBE2Crossbar::SetReaderProfile(CSBE2Crossbar *this, struct CDVRReaderProfile *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  signed int Instance; // ebx
  unsigned int j; // edi
  int *v7; // r8
  GUID v8; // xmm1
  int v9; // eax
  struct ISBE2MediaTypeProfile **v10; // r14
  unsigned int i; // edi
  int *v12; // r8
  GUID v13; // xmm1
  struct ISBE2MediaTypeProfileVtbl *lpVtbl; // rax
  unsigned int v15; // edi
  _DWORD v17[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct _AMMediaType v18; // [rsp+40h] [rbp-C0h] BYREF
  struct _AMMediaType v19; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v21; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 v22[2]; // [rsp+10Ch] [rbp+Ch] BYREF
  struct _AMMediaType Buf1; // [rsp+110h] [rbp+10h] BYREF

  v21 = 0;
  v22[0] = 0;
  v20 = 0;
  memset_0(&Buf1, 0, sizeof(Buf1));
  Buf1.lSampleSize = 1;
  Buf1.bFixedSizeSamples = 1;
  memset_0(&v18, 0, sizeof(v18));
  v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 10);
  v18.lSampleSize = 1;
  v18.bFixedSizeSamples = 1;
  EnterCriticalSection(v4);
  if ( *((_QWORD *)this + 57) )
  {
LABEL_34:
    v9 = *((_DWORD *)this + 34);
    if ( (v9 & 1) == 0 && (v9 & 4) == 0 )
    {
      if ( !*((_QWORD *)this + 58) )
      {
        Instance = -2147418113;
        goto LABEL_85;
      }
LABEL_84:
      Instance = (*(unsigned int (__fastcall **)(CSBE2Crossbar *, struct CDVRReaderProfile *))(*(_QWORD *)this + 80LL))(
                   this,
                   a2) == 0
               ? 0x8000FFFF
               : 0;
      goto LABEL_85;
    }
    v10 = (struct ISBE2MediaTypeProfile **)((char *)this + 464);
    if ( *((_QWORD *)this + 58) )
      goto LABEL_84;
    Instance = CSBE2MediaTypeProfile::CreateInstance((struct ISBE2MediaTypeProfile **)this + 58);
    if ( Instance < 0 )
      goto LABEL_85;
    Instance = CDVRReaderProfile::EnumWMStreams(a2, &v21);
    if ( Instance < 0 )
    {
LABEL_74:
      lpVtbl = (*v10)->lpVtbl;
      if ( Instance >= 0 )
      {
        Instance = ((__int64 (__fastcall *)(struct ISBE2MediaTypeProfile *, unsigned int *))lpVtbl->GetStreamCount)(
                     *v10,
                     &v21);
        if ( Instance >= 0 )
        {
          v15 = 0;
          if ( !v21 )
            goto LABEL_85;
          while ( Instance >= 0 )
          {
            Instance = ((__int64 (__fastcall *)(struct ISBE2MediaTypeProfile *, _QWORD, __int64 *))(*v10)->lpVtbl->GetStream)(
                         *v10,
                         v15,
                         &v20);
            if ( Instance >= 0 )
              Instance = (*(__int64 (__fastcall **)(CSBE2Crossbar *, _QWORD, __int64))(*(_QWORD *)this + 152LL))(
                           this,
                           v15,
                           v20);
            if ( ++v15 >= v21 )
            {
              if ( Instance >= 0 )
                goto LABEL_85;
              break;
            }
          }
        }
        CSBE2Crossbar::RemoveAllPins_(this);
        lpVtbl = (*v10)->lpVtbl;
      }
      ((void (*)(void))lpVtbl->Release)();
      *v10 = 0;
      goto LABEL_85;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= v21 || Instance < 0 )
        goto LABEL_74;
      Instance = CDVRReaderProfile::GetStream(a2, i, v22, &Buf1);
      if ( Instance >= 0 )
        break;
LABEL_73:
      FreeMediaType(&Buf1);
      memset_0(&Buf1, 0, sizeof(Buf1));
      Buf1.bFixedSizeSamples = 1;
      Buf1.lSampleSize = 1;
    }
    if ( m_fSbeSourceSimpleMode )
    {
      if ( memcmp_0(&Buf1, &MEDIATYPE_Video, 0x10u) && memcmp_0(&Buf1, &MEDIATYPE_Audio, 0x10u) )
        goto LABEL_73;
    }
    else if ( (*((_BYTE *)this + 136) & 4) == 0 )
    {
LABEL_69:
      if ( (*((_BYTE *)this + 136) & 1) == 0 && memcmp_0(&Buf1, &MEDIATYPE_Video, 0x10u)
        || !(unsigned int)CSBE2Crossbar::IsMediaTypeInProfile_(this, &Buf1, *v10) )
      {
        ((void (__fastcall *)(struct ISBE2MediaTypeProfile *, struct _AMMediaType *))(*v10)->lpVtbl->AddStream)(
          *v10,
          &Buf1);
      }
      goto LABEL_73;
    }
    CMediaType::CMediaType((CMediaType *)&v19, (const struct CMediaType *)&Buf1, v12);
    if ( (!memcmp_0(&Buf1.subtype, &MEDIASUBTYPE_CPFilters_Processed, 0x10u)
       || !memcmp_0(&Buf1.formattype, &FORMATTYPE_CPFilters_Processed, 0x10u)
       || !memcmp_0(&Buf1.subtype, &MEDIASUBTYPE_ETDTFilter_Tagged_SBE, 0x10u)
       || !memcmp_0(&Buf1.formattype, &FORMATTYPE_ETDTFilter_Tagged_SBE, 0x10u))
      && Buf1.cbFormat >= 0x20 )
    {
      v13 = *(GUID *)&Buf1.pbFormat[Buf1.cbFormat - 16];
      v19.subtype = *(GUID *)&Buf1.pbFormat[Buf1.cbFormat - 32];
      v19.formattype = v13;
      if ( (signed int)(Buf1.cbFormat - 32) <= 0 )
      {
        CMediaType::ResetFormatBuffer((CMediaType *)&v19);
      }
      else if ( !(unsigned int)CMediaType::SetFormat((LPVOID *)&v19, Buf1.pbFormat, Buf1.cbFormat - 32) )
      {
        goto LABEL_20;
      }
      CMediaType::Set(&v18, &v19);
      if ( !memcmp_0(&v18.formattype, &FORMAT_WaveFormatEx, 0x10u) )
      {
        v17[0] = 0;
        if ( (int)ValidateMediaType(&v18, v17) < 0
          && v17[0]
          && v18.cbFormat >= 0x12
          && (unsigned __int64)*((unsigned __int16 *)v18.pbFormat + 8) + 18 > v18.cbFormat )
        {
          *((_WORD *)v18.pbFormat + 8) = LOWORD(v18.cbFormat) - 18;
        }
      }
      Instance = 0;
    }
    else
    {
      Instance = CMediaType::Set(&v18, &Buf1);
    }
    FreeMediaType(&v19);
    if ( Instance < 0 )
      goto LABEL_85;
    CMediaType::Set(&Buf1, &v18);
    goto LABEL_69;
  }
  Instance = CSBE2MediaTypeProfile::CreateInstance((struct ISBE2MediaTypeProfile **)this + 57);
  if ( Instance >= 0 )
  {
    Instance = CDVRReaderProfile::EnumWMStreams(a2, &v21);
    if ( Instance >= 0 )
    {
      for ( j = 0; ; ++j )
      {
        if ( j >= v21 )
          goto LABEL_34;
        Instance = CDVRReaderProfile::GetStream(a2, j, v22, &Buf1);
        if ( Instance < 0 )
          goto LABEL_85;
        if ( m_fSbeSourceSimpleMode )
          break;
        if ( (*((_BYTE *)this + 136) & 4) != 0 )
          goto LABEL_12;
LABEL_32:
        Instance = (*(__int64 (__fastcall **)(_QWORD, struct _AMMediaType *))(**((_QWORD **)this + 57) + 40LL))(
                     *((_QWORD *)this + 57),
                     &Buf1);
        if ( Instance < 0 )
          goto LABEL_85;
LABEL_33:
        FreeMediaType(&Buf1);
        memset_0(&Buf1, 0, sizeof(Buf1));
        Buf1.lSampleSize = 1;
        Buf1.bFixedSizeSamples = 1;
      }
      if ( memcmp_0(&Buf1, &MEDIATYPE_Video, 0x10u) && memcmp_0(&Buf1, &MEDIATYPE_Audio, 0x10u) )
        goto LABEL_33;
LABEL_12:
      CMediaType::CMediaType((CMediaType *)&v19, (const struct CMediaType *)&Buf1, v7);
      if ( (!memcmp_0(&Buf1.subtype, &MEDIASUBTYPE_CPFilters_Processed, 0x10u)
         || !memcmp_0(&Buf1.formattype, &FORMATTYPE_CPFilters_Processed, 0x10u)
         || !memcmp_0(&Buf1.subtype, &MEDIASUBTYPE_ETDTFilter_Tagged_SBE, 0x10u)
         || !memcmp_0(&Buf1.formattype, &FORMATTYPE_ETDTFilter_Tagged_SBE, 0x10u))
        && Buf1.cbFormat >= 0x20 )
      {
        v8 = *(GUID *)&Buf1.pbFormat[Buf1.cbFormat - 16];
        v19.subtype = *(GUID *)&Buf1.pbFormat[Buf1.cbFormat - 32];
        v19.formattype = v8;
        if ( (signed int)(Buf1.cbFormat - 32) <= 0 )
        {
          CMediaType::ResetFormatBuffer((CMediaType *)&v19);
        }
        else if ( !(unsigned int)CMediaType::SetFormat((LPVOID *)&v19, Buf1.pbFormat, Buf1.cbFormat - 32) )
        {
LABEL_20:
          FreeMediaType(&v19);
          Instance = -2147024882;
          goto LABEL_85;
        }
        CMediaType::Set(&v18, &v19);
        if ( !memcmp_0(&v18.formattype, &FORMAT_WaveFormatEx, 0x10u) )
        {
          v17[0] = 0;
          if ( (int)ValidateMediaType(&v18, v17) < 0
            && v17[0]
            && v18.cbFormat >= 0x12
            && (unsigned __int64)*((unsigned __int16 *)v18.pbFormat + 8) + 18 > v18.cbFormat )
          {
            *((_WORD *)v18.pbFormat + 8) = LOWORD(v18.cbFormat) - 18;
          }
        }
        Instance = 0;
      }
      else
      {
        Instance = CMediaType::Set(&v18, &Buf1);
      }
      FreeMediaType(&v19);
      if ( Instance < 0 )
        goto LABEL_85;
      CMediaType::Set(&Buf1, &v18);
      if ( !*((_QWORD *)this + 120) )
        CoCreateInstance(&CLSID_BroadcastEventService, 0, 1u, &IID_IBroadcastEventEx, (LPVOID *)this + 120);
      goto LABEL_32;
    }
  }
LABEL_85:
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  FreeMediaType(&v18);
  FreeMediaType(&Buf1);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180038180  mov     [rsp-8+arg_10], rbx
0x180038185  push    rbp
0x180038186  push    rsi
0x180038187  push    rdi
0x180038188  push    r12
0x18003818a  push    r13
0x18003818c  push    r14
0x18003818e  push    r15
0x180038190  lea     rbp, [rsp-80h]
0x180038195  sub     rsp, 180h
0x18003819c  mov     rax, cs:__security_cookie
0x1800381a3  xor     rax, rsp
0x1800381a6  mov     [rbp+0B0h+var_40], rax
0x1800381aa  xor     r12d, r12d
0x1800381ad  mov     r15, rdx
0x1800381b0  mov     rsi, rcx
0x1800381b3  mov     [rbp+0B0h+var_A8], r12d
0x1800381b7  xor     edx, edx; Val
0x1800381b9  mov     [rbp+0B0h+var_A4], r12w
0x1800381be  lea     rcx, [rbp+0B0h+Buf1]; void *
0x1800381c2  mov     [rbp+0B0h+var_B0], r12
0x1800381c6  lea     ebx, [r12+58h]
0x1800381cb  mov     r8d, ebx; Size
0x1800381ce  call    memset_0
0x1800381d3  lea     r13d, [r12+1]
0x1800381d8  mov     r8d, ebx; Size
0x1800381db  xor     edx, edx; Val
0x1800381dd  mov     [rbp+0B0h+var_78], r13d
0x1800381e1  lea     rcx, [rsp+1B0h+var_170]; void *
0x1800381e6  mov     [rbp+0B0h+var_80], r13d
0x1800381ea  call    memset_0
0x1800381ef  mov     rcx, [rsi+50h]; lpCriticalSection
0x1800381f3  mov     [rsp+1B0h+var_170.lSampleSize], r13d
0x1800381f8  mov     [rsp+1B0h+var_170.bFixedSizeSamples], r13d
0x1800381fd  call    cs:__imp_EnterCriticalSection
0x180038203  lea     r14, [rsi+1C8h]
0x18003820a  cmp     [r14], r12
0x18003820d  jnz     loc_180038482
0x180038213  mov     rcx, r14; struct ISBE2MediaTypeProfile **
0x180038216  call    ?CreateInstance@CSBE2MediaTypeProfile@@SAJPEAPEAUISBE2MediaTypeProfile@@@Z; CSBE2MediaTypeProfile::CreateInstance(ISBE2MediaTypeProfile * *)
0x18003821b  mov     ebx, eax
0x18003821d  test    eax, eax
0x18003821f  js      loc_1800387D6
0x180038225  lea     rdx, [rbp+0B0h+var_A8]; unsigned int *
0x180038229  mov     rcx, r15; this
0x18003822c  call    ?EnumWMStreams@CDVRReaderProfile@@QEAAJPEAK@Z; CDVRReaderProfile::EnumWMStreams(ulong *)
0x180038231  mov     ebx, eax
0x180038233  test    eax, eax
0x180038235  js      loc_1800387D6
0x18003823b  mov     edi, r12d
0x18003823e  cmp     edi, [rbp+0B0h+var_A8]
0x180038241  jnb     loc_180038482
0x180038247  lea     r9, [rbp+0B0h+Buf1]; struct _AMMediaType *
0x18003824b  mov     edx, edi; unsigned int
0x18003824d  lea     r8, [rbp+0B0h+var_A4]; unsigned __int16 *
0x180038251  mov     rcx, r15; this
0x180038254  call    ?GetStream@CDVRReaderProfile@@QEAAJKPEAGPEAU_AMMediaType@@@Z; CDVRReaderProfile::GetStream(ulong,ushort *,_AMMediaType *)
0x180038259  mov     ebx, eax
0x18003825b  test    eax, eax
0x18003825d  js      loc_1800387D6
0x180038263  cmp     cs:?m_fSbeSourceSimpleMode@@3_NA, r12b; bool m_fSbeSourceSimpleMode
0x18003826a  jz      short loc_1800382A5
0x18003826c  mov     ebx, 10h
0x180038271  lea     rdx, MEDIATYPE_Video; Buf2
0x180038278  mov     r8d, ebx; Size
0x18003827b  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x18003827f  call    memcmp_0
0x180038284  test    eax, eax
0x180038286  jz      short loc_1800382B7
0x180038288  mov     r8d, ebx; Size
0x18003828b  lea     rdx, MEDIATYPE_Audio; Buf2
0x180038292  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x180038296  call    memcmp_0
0x18003829b  test    eax, eax
0x18003829d  jnz     loc_18003845A
0x1800382a3  jmp     short loc_1800382B7
0x1800382a5  test    byte ptr [rsi+88h], 4
0x1800382ac  jz      loc_18003843D
0x1800382b2  mov     ebx, 10h
0x1800382b7  lea     rdx, [rbp+0B0h+Buf1]; struct CMediaType *
0x1800382bb  lea     rcx, [rbp+0B0h+var_110]; this
0x1800382bf  call    ??0CMediaType@@QEAA@AEBV0@PEAJ@Z; CMediaType::CMediaType(CMediaType const &,long *)
0x1800382c4  mov     r8, rbx; Size
0x1800382c7  lea     rdx, MEDIASUBTYPE_CPFilters_Processed; Buf2
0x1800382ce  lea     rcx, [rbp+0B0h+var_90]; Buf1
0x1800382d2  call    memcmp_0
0x1800382d7  test    eax, eax
0x1800382d9  jz      short loc_180038335
0x1800382db  mov     r8, rbx; Size
0x1800382de  lea     rdx, FORMATTYPE_CPFilters_Processed; Buf2
0x1800382e5  lea     rcx, [rbp+0B0h+var_74]; Buf1
0x1800382e9  call    memcmp_0
0x1800382ee  test    eax, eax
0x1800382f0  jz      short loc_180038335
0x1800382f2  mov     r8, rbx; Size
0x1800382f5  lea     rdx, MEDIASUBTYPE_ETDTFilter_Tagged_SBE; Buf2
0x1800382fc  lea     rcx, [rbp+0B0h+var_90]; Buf1
0x180038300  call    memcmp_0
0x180038305  test    eax, eax
0x180038307  jz      short loc_180038335
0x180038309  mov     r8, rbx; Size
0x18003830c  lea     rdx, FORMATTYPE_ETDTFilter_Tagged_SBE; Buf2
0x180038313  lea     rcx, [rbp+0B0h+var_74]; Buf1
0x180038317  call    memcmp_0
0x18003831c  test    eax, eax
0x18003831e  jz      short loc_180038335
0x180038320  lea     rdx, [rbp+0B0h+Buf1]; struct _AMMediaType *
0x180038324  lea     rcx, [rsp+1B0h+var_170]; this
0x180038329  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18003832e  mov     ebx, eax
0x180038330  jmp     loc_1800383F4
0x180038335  movsxd  rcx, [rbp+0B0h+var_58]
0x180038339  cmp     ecx, 20h ; ' '
0x18003833c  jb      short loc_180038320
0x18003833e  mov     rdx, [rbp+0B0h+var_50]; unsigned __int8 *
0x180038342  lea     r8d, [rcx-20h]; unsigned int
0x180038346  movups  xmm0, xmmword ptr [rdx+rcx-20h]
0x18003834b  movups  xmm1, xmmword ptr [rdx+rcx-10h]
0x180038350  lea     rcx, [rbp+0B0h+var_110]; this
0x180038354  movdqu  xmmword ptr [rbp+0B0h+var_110.subtype.Data1], xmm0
0x180038359  movdqu  xmmword ptr [rbp+0B0h+var_110.formattype.Data1], xmm1
0x18003835e  test    r8d, r8d
0x180038361  jle     short loc_18003837F
0x180038363  call    ?SetFormat@CMediaType@@QEAAHPEAEK@Z; CMediaType::SetFormat(uchar *,ulong)
0x180038368  test    eax, eax
0x18003836a  jnz     short loc_180038384
0x18003836c  lea     rcx, [rbp+0B0h+var_110]; struct _AMMediaType *
0x180038370  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180038375  mov     ebx, 8007000Eh
0x18003837a  jmp     loc_1800387D6
0x18003837f  call    ?ResetFormatBuffer@CMediaType@@QEAAXXZ; CMediaType::ResetFormatBuffer(void)
0x180038384  lea     rdx, [rbp+0B0h+var_110]; struct _AMMediaType *
0x180038388  lea     rcx, [rsp+1B0h+var_170]; this
0x18003838d  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x180038392  mov     r8, rbx; Size
0x180038395  lea     rdx, FORMAT_WaveFormatEx; Buf2
0x18003839c  lea     rcx, [rsp+1B0h+var_170.formattype]; Buf1
0x1800383a1  call    memcmp_0
0x1800383a6  test    eax, eax
0x1800383a8  jnz     short loc_1800383F1
0x1800383aa  lea     rdx, [rsp+1B0h+var_180]
0x1800383af  mov     [rsp+1B0h+var_180], r12d
0x1800383b4  lea     rcx, [rsp+1B0h+var_170]
0x1800383b9  call    ValidateMediaType
0x1800383be  test    eax, eax
0x1800383c0  jns     short loc_1800383F1
0x1800383c2  cmp     [rsp+1B0h+var_180], r12d
0x1800383c7  jz      short loc_1800383F1
0x1800383c9  mov     edx, [rbp+0B0h+var_170.cbFormat]
0x1800383cc  mov     r9d, 12h
0x1800383d2  cmp     edx, r9d
0x1800383d5  jb      short loc_1800383F1
0x1800383d7  mov     r8, [rbp+0B0h+var_170.pbFormat]
0x1800383db  movzx   ecx, word ptr [r8+10h]
0x1800383e0  add     rcx, r9
0x1800383e3  cmp     rcx, rdx
0x1800383e6  jbe     short loc_1800383F1
0x1800383e8  sub     dx, r9w
0x1800383ec  mov     [r8+10h], dx
0x1800383f1  mov     ebx, r12d
0x1800383f4  lea     rcx, [rbp+0B0h+var_110]; struct _AMMediaType *
0x1800383f8  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800383fd  test    ebx, ebx
0x1800383ff  js      loc_1800387D6
0x180038405  lea     rdx, [rsp+1B0h+var_170]; struct _AMMediaType *
0x18003840a  lea     rcx, [rbp+0B0h+Buf1]; this
0x18003840e  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x180038413  lea     rax, [rsi+3C0h]
0x18003841a  cmp     [rax], r12
0x18003841d  jnz     short loc_18003843D
0x18003841f  lea     r9, IID_IBroadcastEventEx; riid
0x180038426  mov     [rsp+1B0h+ppv], rax; ppv
0x18003842b  mov     r8d, r13d; dwClsContext
0x18003842e  lea     rcx, CLSID_BroadcastEventService; rclsid
0x180038435  xor     edx, edx; pUnkOuter
0x180038437  call    cs:__imp_CoCreateInstance
0x18003843d  mov     rcx, [r14]
0x180038440  lea     rdx, [rbp+0B0h+Buf1]
0x180038444  mov     rax, [rcx]
0x180038447  mov     rax, [rax+28h]
0x18003844b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038450  mov     ebx, eax
0x180038452  test    eax, eax
0x180038454  js      loc_1800387D6
0x18003845a  lea     rcx, [rbp+0B0h+Buf1]; struct _AMMediaType *
0x18003845e  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180038463  xor     edx, edx; Val
0x180038465  lea     rcx, [rbp+0B0h+Buf1]; void *
0x180038469  lea     r8d, [rdx+58h]; Size
0x18003846d  call    memset_0
0x180038472  add     edi, r13d
0x180038475  mov     [rbp+0B0h+var_78], r13d
0x180038479  mov     [rbp+0B0h+var_80], r13d
0x18003847d  jmp     loc_18003823E
0x180038482  mov     eax, [rsi+88h]
0x180038488  test    r13b, al
0x18003848b  jnz     short loc_1800384A8
0x18003848d  test    al, 4
0x18003848f  jnz     short loc_1800384A8
0x180038491  cmp     [rsi+1D0h], r12
0x180038498  jnz     loc_1800387B7
0x18003849e  mov     ebx, 8000FFFFh
0x1800384a3  jmp     loc_1800387D6
0x1800384a8  lea     r14, [rsi+1D0h]
0x1800384af  cmp     [r14], r12
0x1800384b2  jnz     loc_1800387B7
0x1800384b8  mov     rcx, r14; struct ISBE2MediaTypeProfile **
0x1800384bb  call    ?CreateInstance@CSBE2MediaTypeProfile@@SAJPEAPEAUISBE2MediaTypeProfile@@@Z; CSBE2MediaTypeProfile::CreateInstance(ISBE2MediaTypeProfile * *)
0x1800384c0  mov     ebx, eax
0x1800384c2  test    eax, eax
0x1800384c4  js      loc_1800387D6
0x1800384ca  lea     rdx, [rbp+0B0h+var_A8]; unsigned int *
0x1800384ce  mov     rcx, r15; this
0x1800384d1  call    ?EnumWMStreams@CDVRReaderProfile@@QEAAJPEAK@Z; CDVRReaderProfile::EnumWMStreams(ulong *)
0x1800384d6  mov     ebx, eax
0x1800384d8  test    eax, eax
0x1800384da  js      loc_180038726
0x1800384e0  mov     edi, r12d
0x1800384e3  cmp     edi, [rbp+0B0h+var_A8]
0x1800384e6  jnb     loc_180038726
0x1800384ec  test    ebx, ebx
0x1800384ee  js      loc_180038726
0x1800384f4  lea     r9, [rbp+0B0h+Buf1]; struct _AMMediaType *
0x1800384f8  mov     edx, edi; unsigned int
0x1800384fa  lea     r8, [rbp+0B0h+var_A4]; unsigned __int16 *
0x1800384fe  mov     rcx, r15; this
0x180038501  call    ?GetStream@CDVRReaderProfile@@QEAAJKPEAGPEAU_AMMediaType@@@Z; CDVRReaderProfile::GetStream(ulong,ushort *,_AMMediaType *)
0x180038506  mov     ebx, eax
0x180038508  test    eax, eax
0x18003850a  js      loc_1800386FC
0x180038510  cmp     cs:?m_fSbeSourceSimpleMode@@3_NA, r12b; bool m_fSbeSourceSimpleMode
0x180038517  jz      short loc_180038552
0x180038519  mov     r8d, 10h; Size
0x18003851f  lea     rdx, MEDIATYPE_Video; Buf2
0x180038526  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x18003852a  call    memcmp_0
0x18003852f  test    eax, eax
0x180038531  jz      short loc_18003855F
0x180038533  mov     r8d, 10h; Size
0x180038539  lea     rdx, MEDIATYPE_Audio; Buf2
0x180038540  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x180038544  call    memcmp_0
0x180038549  test    eax, eax
0x18003854b  jz      short loc_18003855F
0x18003854d  jmp     loc_1800386FC
0x180038552  test    byte ptr [rsi+88h], 4
0x180038559  jz      loc_1800386B3
0x18003855f  lea     rdx, [rbp+0B0h+Buf1]; struct CMediaType *
0x180038563  lea     rcx, [rbp+0B0h+var_110]; this
0x180038567  call    ??0CMediaType@@QEAA@AEBV0@PEAJ@Z; CMediaType::CMediaType(CMediaType const &,long *)
0x18003856c  mov     ebx, 10h
0x180038571  lea     rdx, MEDIASUBTYPE_CPFilters_Processed; Buf2
0x180038578  mov     r8d, ebx; Size
0x18003857b  lea     rcx, [rbp+0B0h+var_90]; Buf1
0x18003857f  call    memcmp_0
0x180038584  test    eax, eax
0x180038586  jz      short loc_1800385E2
0x180038588  mov     r8d, ebx; Size
0x18003858b  lea     rdx, FORMATTYPE_CPFilters_Processed; Buf2
0x180038592  lea     rcx, [rbp+0B0h+var_74]; Buf1
0x180038596  call    memcmp_0
0x18003859b  test    eax, eax
0x18003859d  jz      short loc_1800385E2
0x18003859f  mov     r8d, ebx; Size
0x1800385a2  lea     rdx, MEDIASUBTYPE_ETDTFilter_Tagged_SBE; Buf2
0x1800385a9  lea     rcx, [rbp+0B0h+var_90]; Buf1
0x1800385ad  call    memcmp_0
0x1800385b2  test    eax, eax
0x1800385b4  jz      short loc_1800385E2
0x1800385b6  mov     r8d, ebx; Size
0x1800385b9  lea     rdx, FORMATTYPE_ETDTFilter_Tagged_SBE; Buf2
0x1800385c0  lea     rcx, [rbp+0B0h+var_74]; Buf1
0x1800385c4  call    memcmp_0
0x1800385c9  test    eax, eax
0x1800385cb  jz      short loc_1800385E2
0x1800385cd  lea     rdx, [rbp+0B0h+Buf1]; struct _AMMediaType *
0x1800385d1  lea     rcx, [rsp+1B0h+var_170]; this
0x1800385d6  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x1800385db  mov     ebx, eax
0x1800385dd  jmp     loc_180038694
0x1800385e2  movsxd  rcx, [rbp+0B0h+var_58]
0x1800385e6  cmp     ecx, 20h ; ' '
0x1800385e9  jb      short loc_1800385CD
0x1800385eb  mov     rdx, [rbp+0B0h+var_50]; unsigned __int8 *
0x1800385ef  lea     r8d, [rcx-20h]; unsigned int
0x1800385f3  movups  xmm0, xmmword ptr [rdx+rcx-20h]
0x1800385f8  movups  xmm1, xmmword ptr [rdx+rcx-10h]
0x1800385fd  lea     rcx, [rbp+0B0h+var_110]; this
0x180038601  movdqu  xmmword ptr [rbp+0B0h+var_110.subtype.Data1], xmm0
0x180038606  movdqu  xmmword ptr [rbp+0B0h+var_110.formattype.Data1], xmm1
0x18003860b  test    r8d, r8d
0x18003860e  jle     short loc_18003861F
0x180038610  call    ?SetFormat@CMediaType@@QEAAHPEAEK@Z; CMediaType::SetFormat(uchar *,ulong)
0x180038615  test    eax, eax
0x180038617  jz      loc_18003836C
0x18003861d  jmp     short loc_180038624
0x18003861f  call    ?ResetFormatBuffer@CMediaType@@QEAAXXZ; CMediaType::ResetFormatBuffer(void)
0x180038624  lea     rdx, [rbp+0B0h+var_110]; struct _AMMediaType *
0x180038628  lea     rcx, [rsp+1B0h+var_170]; this
0x18003862d  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
  ... truncated ...
```
