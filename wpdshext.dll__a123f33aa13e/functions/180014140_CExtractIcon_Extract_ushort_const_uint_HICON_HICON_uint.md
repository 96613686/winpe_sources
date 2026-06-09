# CExtractIcon::Extract(ushort const *,uint,HICON__ * *,HICON__ * *,uint)

- ea: `0x180014140`
- end: `0x180014741`
- name: `?Extract@CExtractIcon@@UEAAJPEBGIPEAPEAUHICON__@@1I@Z`
- size: `1537`
- prototype: `int(CExtractIcon *__hidden this, const unsigned __int16 *, unsigned int, HICON *, HICON *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180014140`
- `0x180014748`
- `0x1800147ec`
- `0x180014dd0`
- `0x180014e88`
- `0x1800177dc`
- `0x1800285c8`
- `0x18002e738`
- `0x18002ff5c`
- `0x180035590`
- `0x180041ab0`
- `0x18005b288`
- `0x18006d490`
- `0x18006ef64`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180014358`
- `KERNEL32!GetLastError` at `0x180014358`
- `KERNEL32!DeleteFileW` at `0x180014508`
- `KERNEL32!DeleteFileW` at `0x180014508`
- `KERNEL32!QueryPerformanceCounter` at `0x1800141eb`
- `KERNEL32!QueryPerformanceCounter` at `0x180014537`
- `KERNEL32!QueryPerformanceCounter` at `0x1800146c6`
- `KERNEL32!QueryPerformanceCounter` at `0x1800141eb`
- `KERNEL32!QueryPerformanceCounter` at `0x180014537`
- `KERNEL32!QueryPerformanceCounter` at `0x1800146c6`
- `KERNEL32!QueryPerformanceFrequency` at `0x18001454a`
- `KERNEL32!QueryPerformanceFrequency` at `0x18001454a`
- `KERNEL32!GetCurrentThreadId` at `0x180014673`
- `KERNEL32!GetCurrentThreadId` at `0x180014673`
- `USER32!LoadImageW` at `0x18001430c`
- `USER32!LoadImageW` at `0x180014339`
- `USER32!LoadImageW` at `0x18001430c`
- `USER32!LoadImageW` at `0x180014339`
- `SHELL32!__imp_SHDefExtractIconW` at `0x18001443e`
- `SHELL32!__imp_SHDefExtractIconW` at `0x180014482`
- `SHELL32!__imp_SHDefExtractIconW` at `0x1800144aa`
- `SHELL32!__imp_SHDefExtractIconW` at `0x18001443e`
- `SHELL32!__imp_SHDefExtractIconW` at `0x180014482`
- `SHELL32!__imp_SHDefExtractIconW` at `0x1800144aa`

## string_xrefs

- `0x180014437`: `wpdshext.dll`
- `0x18001447b`: `imageres.dll`
- `0x1800144a3`: `shell32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CExtractIcon::Extract(
        CExtractIcon *this,
        const unsigned __int16 *a2,
        __int64 a3,
        HICON *a4,
        HICON *phiconSmall,
        UINT nIconSize)
{
  UINT v8; // r12d
  int v9; // r13d
  __int64 v10; // rdx
  const WCHAR *v11; // rbx
  int IconW; // r15d
  __int64 v13; // r8
  struct IUnknown *v14; // rbx
  int ResourceStream; // eax
  signed int LastError; // eax
  __int64 v17; // rax
  HRESULT v18; // eax
  ATL::CStringData *v19; // r12
  signed int LowPart; // edx
  signed int v21; // ebx
  bool v22; // zf
  int v23; // eax
  double v24; // xmm1_8
  const wchar_t *v25; // rsi
  char v26; // bl
  char v27; // di
  DWORD CurrentThreadId; // eax
  const unsigned __int16 *CommandName; // rax
  char v30; // cl
  char v31; // r8
  int cy[2]; // [rsp+28h] [rbp-E0h]
  __int64 fuLoad; // [rsp+30h] [rbp-D8h]
  int v35; // [rsp+50h] [rbp-B8h]
  int v36; // [rsp+60h] [rbp-A8h]
  LPCWSTR name; // [rsp+80h] [rbp-88h] BYREF
  struct IUnknown *v38; // [rsp+88h] [rbp-80h] BYREF
  struct IPortableDevice *v39; // [rsp+90h] [rbp-78h] BYREF
  char v40[8]; // [rsp+98h] [rbp-70h]
  char v41[8]; // [rsp+A0h] [rbp-68h]
  LARGE_INTEGER PerformanceCount[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v43; // [rsp+B8h] [rbp-50h]
  LARGE_INTEGER Frequency; // [rsp+C8h] [rbp-40h] BYREF
  char v45; // [rsp+D0h] [rbp-38h]
  unsigned __int16 v46[264]; // [rsp+D8h] [rbp-30h] BYREF

  v8 = nIconSize;
  v9 = 0;
  *(_QWORD *)v40 = 0;
  *(_QWORD *)v41 = 0;
  v45 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  v43 = 0;
  Frequency.QuadPart = 0;
  v11 = (const WCHAR *)(((__int64 (__fastcall *)(void ***, const unsigned __int16 *))ATL::g_strmgr[3])(
                          &ATL::g_strmgr,
                          a2)
                      + 24);
  name = v11;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(PerformanceCount);
    *(_QWORD *)v40 = 12;
    *(_QWORD *)v41 = 0;
    v43 = 0;
    v45 = 1;
  }
  if ( !a4 && !phiconSmall )
    goto LABEL_45;
  IconW = 0;
  if ( a4 )
    *a4 = 0;
  if ( phiconSmall )
    *phiconSmall = 0;
  if ( *((_DWORD *)this + 4) )
  {
    if ( !*((_DWORD *)this + 3) )
    {
LABEL_44:
      v8 = nIconSize;
LABEL_45:
      while ( 1 )
      {
        IconW = SHDefExtractIconW(L"imageres.dll", *((_DWORD *)this + 8), 0, a4, phiconSmall, v8);
        if ( IconW >= 0 )
          break;
        v18 = SHDefExtractIconW(L"shell32.dll", *((_DWORD *)this + 8), 0, a4, phiconSmall, v8);
        IconW = v18;
        if ( v18 >= 0 )
          break;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LODWORD(fuLoad) = v18;
          cy[0] = v8;
          WPP_SF_ddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_6b280ac677813e2ddcf838599857c188_Traceguids,
            *((unsigned int *)this + 8),
            *(_QWORD *)cy,
            fuLoad);
        }
      }
      v11 = name;
      goto LABEL_51;
    }
    if ( !*((_WORD *)this + 26) )
      goto LABEL_38;
    v39 = 0;
    v38 = 0;
    if ( (int)SHBindToIDList(*((_QWORD *)this + 72), v10, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v39) >= 0
      && (int)GetObjectID(v39, (unsigned __int16 *)this + 26, v46, 0x104u) >= 0 )
    {
      if ( (int)CTempFileStream::CreateInstance(0, &name, v13, &v38) >= 0 )
      {
        v14 = v38;
        ResourceStream = GetResourceStream(v39, v46, &WPD_RESOURCE_ICON, 0, (struct IStream *)v38);
        if ( ResourceStream >= 0 )
        {
          if ( v14 )
            ATL::AtlComPtrAssign(&v38, 0);
          v11 = name;
          v8 = nIconSize;
          if ( a4 )
            *a4 = (HICON)LoadImageW(0, name, 1u, (unsigned __int16)nIconSize, (unsigned __int16)nIconSize, 0x10u);
          if ( phiconSmall )
            *phiconSmall = (HICON)LoadImageW(0, v11, 1u, HIWORD(nIconSize), HIWORD(nIconSize), 0x10u);
          if ( (!a4 || *a4) && (!phiconSmall || *phiconSmall) )
          {
            IconW = 0;
            v9 = 1;
          }
          else
          {
            LastError = GetLastError();
            IconW = LastError;
            if ( LastError > 0 )
              IconW = (unsigned __int16)LastError | 0x80070000;
            if ( IconW < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  14,
                  WPP_6b280ac677813e2ddcf838599857c188_Traceguids,
                  (unsigned int)IconW);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
              goto LABEL_45;
            }
          }
          goto LABEL_37;
        }
        if ( ResourceStream == -2147024846 )
          *((_DWORD *)this + 3) = 0;
      }
      v11 = name;
    }
LABEL_37:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
    if ( v9 )
      goto LABEL_51;
LABEL_38:
    v8 = nIconSize;
  }
  if ( !*((_DWORD *)this + 3) )
    goto LABEL_44;
  v17 = *(_QWORD *)((char *)this + 36) - *(_QWORD *)&WPD_CONTENT_TYPE_PLAYLIST.Data1;
  if ( !v17 )
    v17 = *(_QWORD *)((char *)this + 44) - *(_QWORD *)WPD_CONTENT_TYPE_PLAYLIST.Data4;
  if ( v17 )
    goto LABEL_44;
  IconW = SHDefExtractIconW(L"wpdshext.dll", -755, 0, a4, phiconSmall, v8);
  if ( IconW < 0 )
    goto LABEL_44;
LABEL_51:
  v19 = (ATL::CStringData *)(v11 - 12);
  if ( *((int *)v11 - 4) > 0 )
    DeleteFileW(v11);
  name = 0;
  if ( *(_DWORD *)v40 == 12 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter((LARGE_INTEGER *)&name);
    LowPart = Frequency.LowPart;
    if ( Frequency.QuadPart
      || QueryPerformanceFrequency(&Frequency) && (LowPart = Frequency.LowPart, Frequency.QuadPart) )
    {
      v21 = (_DWORD)name - PerformanceCount[0].LowPart;
      if ( *(_DWORD *)v40 > 7u )
      {
        if ( *(_DWORD *)v40 != 8 )
        {
          v23 = *(_DWORD *)v40 - 9;
          v22 = *(_DWORD *)v40 == 9;
          goto LABEL_68;
        }
      }
      else if ( *(_DWORD *)v40 != 7 )
      {
        if ( *(_DWORD *)v40 == 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids);
            LowPart = Frequency.LowPart;
          }
        }
        else if ( *(_DWORD *)v40 != 2 )
        {
          v23 = *(_DWORD *)v40 - 4;
          v22 = *(_DWORD *)v40 == 4;
LABEL_68:
          if ( !v22 && (unsigned int)(v23 - 1) >= 2 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
            goto LABEL_77;
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        v24 = (double)v21 / (double)LowPart * 1000.0;
        v25 = L"N/A";
        if ( this != (CExtractIcon *)-52LL )
          v25 = (const wchar_t *)((char *)this + 52);
        v26 = v40[4];
        v27 = v41[0];
        CurrentThreadId = GetCurrentThreadId();
        CommandName = CPerfTraceHelper::GetCommandName((CPerfTraceHelper *)CurrentThreadId, *(unsigned int *)v40);
        WPP_SF_dDSdiddddDS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v31,
          (__int64)CommandName,
          v30,
          v27,
          (int)v24,
          v35,
          v26,
          v36,
          IconW,
          (__int64)v25);
      }
      QueryPerformanceCounter(&PerformanceCount[1]);
      v45 = 0;
    }
  }
LABEL_77:
  if ( IconW < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_6b280ac677813e2ddcf838599857c188_Traceguids,
      (unsigned int)IconW);
  ATL::CStringData::Release(v19);
  return (unsigned int)IconW;
}

```

## disassembly

```asm
0x180014140  mov     rax, rsp
0x180014143  mov     [rax+10h], rbx
0x180014147  push    rbp
0x180014148  push    rsi
0x180014149  push    rdi
0x18001414a  push    r12
0x18001414c  push    r13
0x18001414e  push    r14
0x180014150  push    r15
0x180014152  lea     rbp, [rax-238h]
0x180014159  sub     rsp, 300h
0x180014160  movaps  xmmword ptr [rax-48h], xmm6
0x180014164  mov     rax, cs:__security_cookie
0x18001416b  xor     rax, rsp
0x18001416e  mov     [rbp+230h+var_50], rax
0x180014175  mov     rdi, r9
0x180014178  mov     r14, rcx
0x18001417b  mov     rsi, [rbp+230h+phiconSmall]
0x180014182  mov     r12d, [rbp+230h+nIconSize]
0x180014189  mov     dword ptr [rsp+330h+var_2C0], r12d
0x18001418e  xor     r13d, r13d
0x180014191  mov     qword ptr [rbp+230h+var_2A0], r13
0x180014195  mov     qword ptr [rbp+230h+var_298], r13
0x180014199  mov     [rbp+230h+var_268], r13b
0x18001419d  xorps   xmm0, xmm0
0x1800141a0  movdqa  xmmword ptr [rbp+230h+PerformanceCount], xmm0
0x1800141a5  xorps   xmm1, xmm1
0x1800141a8  movdqa  [rbp+230h+var_280], xmm1
0x1800141ad  mov     qword ptr [rbp+230h+Frequency], r13
0x1800141b1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800141b8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800141bf  mov     rax, [rax+18h]
0x1800141c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141c8  lea     rbx, [rax+18h]
0x1800141cc  mov     [rsp+330h+name], rbx
0x1800141d1  cmp     [rbp+230h+var_268], r13b
0x1800141d5  jnz     short loc_180014209
0x1800141d7  mov     rax, cs:WPP_GLOBAL_Control
0x1800141de  test    dword ptr [rax+1Ch], 800h
0x1800141e5  jz      short loc_180014209
0x1800141e7  lea     rcx, [rbp+230h+PerformanceCount]; lpPerformanceCount
0x1800141eb  call    cs:__imp_QueryPerformanceCounter
0x1800141f1  mov     qword ptr [rbp+230h+var_2A0], 0Ch
0x1800141f9  mov     qword ptr [rbp+230h+var_298], r13
0x1800141fd  xorps   xmm0, xmm0
0x180014200  movdqa  [rbp+230h+var_280], xmm0
0x180014205  mov     [rbp+230h+var_268], 1
0x180014209  test    rdi, rdi
0x18001420c  jnz     short loc_180014217
0x18001420e  test    rsi, rsi
0x180014211  jz      loc_180014460
0x180014217  xor     ecx, ecx
0x180014219  mov     r15d, ecx
0x18001421c  test    rdi, rdi
0x18001421f  jz      short loc_180014224
0x180014221  mov     [rdi], rcx
0x180014224  test    rsi, rsi
0x180014227  jz      short loc_18001422C
0x180014229  mov     [rsi], rcx
0x18001422c  cmp     [r14+10h], ecx
0x180014230  jz      loc_1800143FF
0x180014236  cmp     [r14+0Ch], ecx
0x18001423a  jz      loc_18001444F
0x180014240  cmp     [r14+34h], cx
0x180014245  jz      loc_1800143FA
0x18001424b  mov     [rbp+230h+var_2A8], rcx
0x18001424f  mov     [rbp+230h+var_2B0], rcx
0x180014253  lea     r9, [rbp+230h+var_2A8]
0x180014257  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x18001425e  mov     rcx, [r14+240h]
0x180014265  call    SHBindToIDList
0x18001426a  test    eax, eax
0x18001426c  js      loc_1800143DC
0x180014272  mov     r9d, 104h; unsigned int
0x180014278  lea     r8, [rbp+230h+var_260]; unsigned __int16 *
0x18001427c  lea     rdx, [r14+34h]; unsigned __int16 *
0x180014280  mov     rcx, [rbp+230h+var_2A8]; struct IPortableDevice *
0x180014284  call    ?GetObjectID@@YAJPEAUIPortableDevice@@PEAG1I@Z; GetObjectID(IPortableDevice *,ushort *,ushort *,uint)
0x180014289  test    eax, eax
0x18001428b  js      loc_1800143DC
0x180014291  lea     r9, [rbp+230h+var_2B0]
0x180014295  lea     rdx, [rsp+330h+name]
0x18001429a  xor     ecx, ecx
0x18001429c  call    ?CreateInstance@CTempFileStream@@SAJHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAPEAUIStream@@@Z; CTempFileStream::CreateInstance(int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,IStream * *)
0x1800142a1  test    eax, eax
0x1800142a3  js      loc_1800143D7
0x1800142a9  mov     rbx, [rbp+230h+var_2B0]
0x1800142ad  mov     qword ptr [rsp+330h+cy], rbx; struct IStream *
0x1800142b2  xor     r9d, r9d; struct CProgressUI *
0x1800142b5  lea     r8, WPD_RESOURCE_ICON; struct _tagpropertykey *
0x1800142bc  lea     rdx, [rbp+230h+var_260]; unsigned __int16 *
0x1800142c0  mov     rcx, [rbp+230h+var_2A8]; struct IPortableDevice *
0x1800142c4  call    ?GetResourceStream@@YAJPEAUIPortableDevice@@PEBGAEBU_tagpropertykey@@PEAVCProgressUI@@PEAUIStream@@@Z; GetResourceStream(IPortableDevice *,ushort const *,_tagpropertykey const &,CProgressUI *,IStream *)
0x1800142c9  test    eax, eax
0x1800142cb  js      loc_1800143C8
0x1800142d1  test    rbx, rbx
0x1800142d4  jz      short loc_1800142E1
0x1800142d6  xor     edx, edx; struct IUnknown *
0x1800142d8  lea     rcx, [rbp+230h+var_2B0]; struct IUnknown **
0x1800142dc  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800142e1  mov     rbx, [rsp+330h+name]
0x1800142e6  mov     r12d, dword ptr [rsp+330h+var_2C0]
0x1800142eb  test    rdi, rdi
0x1800142ee  jz      short loc_180014315
0x1800142f0  movzx   r9d, r12w; cx
0x1800142f4  mov     dword ptr [rsp+330h+fuLoad], 10h; fuLoad
0x1800142fc  mov     [rsp+330h+cy], r9d; cy
0x180014301  mov     r8d, 1; type
0x180014307  mov     rdx, rbx; name
0x18001430a  xor     ecx, ecx; hInst
0x18001430c  call    cs:__imp_LoadImageW
0x180014312  mov     [rdi], rax
0x180014315  test    rsi, rsi
0x180014318  jz      short loc_180014342
0x18001431a  mov     r9d, r12d
0x18001431d  shr     r9d, 10h; cx
0x180014321  mov     dword ptr [rsp+330h+fuLoad], 10h; fuLoad
0x180014329  mov     [rsp+330h+cy], r9d; cy
0x18001432e  mov     r8d, 1; type
0x180014334  mov     rdx, rbx; name
0x180014337  xor     ecx, ecx; hInst
0x180014339  call    cs:__imp_LoadImageW
0x18001433f  mov     [rsi], rax
0x180014342  test    rdi, rdi
0x180014345  jz      short loc_18001434D
0x180014347  cmp     qword ptr [rdi], 0
0x18001434b  jz      short loc_180014358
0x18001434d  test    rsi, rsi
0x180014350  jz      short loc_1800143BF
0x180014352  cmp     qword ptr [rsi], 0
0x180014356  jnz     short loc_1800143BF
0x180014358  call    cs:__imp_GetLastError
0x18001435e  mov     r15d, eax
0x180014361  test    eax, eax
0x180014363  jle     short loc_180014370
0x180014365  movzx   r15d, ax
0x180014369  or      r15d, 80070000h
0x180014370  test    r15d, r15d
0x180014373  jns     short loc_1800143DC
0x180014375  mov     rcx, cs:WPP_GLOBAL_Control
0x18001437c  lea     rax, WPP_GLOBAL_Control
0x180014383  cmp     rcx, rax
0x180014386  jz      short loc_1800143A7
0x180014388  test    byte ptr [rcx+1Ch], 2
0x18001438c  jz      short loc_1800143A7
0x18001438e  mov     edx, 0Eh
0x180014393  mov     r9d, r15d
0x180014396  lea     r8, WPP_6b280ac677813e2ddcf838599857c188_Traceguids
0x18001439d  mov     rcx, [rcx+10h]
0x1800143a1  call    WPP_SF_d
0x1800143a6  nop
0x1800143a7  lea     rcx, [rbp+230h+var_2B0]
0x1800143ab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800143b0  nop
0x1800143b1  lea     rcx, [rbp+230h+var_2A8]
0x1800143b5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800143ba  jmp     loc_18001445D
0x1800143bf  xor     r15d, r15d
0x1800143c2  lea     r13d, [r15+1]
0x1800143c6  jmp     short loc_1800143DC
0x1800143c8  cmp     eax, 80070032h
0x1800143cd  jnz     short loc_1800143D7
0x1800143cf  mov     dword ptr [r14+0Ch], 0
0x1800143d7  mov     rbx, [rsp+330h+name]
0x1800143dc  lea     rcx, [rbp+230h+var_2B0]
0x1800143e0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800143e5  nop
0x1800143e6  lea     rcx, [rbp+230h+var_2A8]
0x1800143ea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800143ef  xor     ecx, ecx
0x1800143f1  test    r13d, r13d
0x1800143f4  jnz     loc_1800144F7
0x1800143fa  mov     r12d, dword ptr [rsp+330h+var_2C0]
0x1800143ff  cmp     [r14+0Ch], ecx
0x180014403  jz      short loc_18001444F
0x180014405  mov     rax, [r14+24h]
0x180014409  sub     rax, qword ptr cs:WPD_CONTENT_TYPE_PLAYLIST.Data1
0x180014410  jnz     short loc_18001441D
0x180014412  mov     rax, [r14+2Ch]
0x180014416  sub     rax, qword ptr cs:WPD_CONTENT_TYPE_PLAYLIST.Data4
0x18001441d  test    rax, rax
0x180014420  jnz     short loc_18001444F
0x180014422  mov     dword ptr [rsp+330h+fuLoad], r12d; nIconSize
0x180014427  mov     qword ptr [rsp+330h+cy], rsi; phiconSmall
0x18001442c  mov     r9, rdi; phiconLarge
0x18001442f  xor     r8d, r8d; uFlags
0x180014432  mov     edx, 0FFFFFD0Dh; iIndex
0x180014437  lea     rcx, szFile; "wpdshext.dll"
0x18001443e  call    cs:__imp_SHDefExtractIconW
0x180014444  mov     r15d, eax
0x180014447  test    eax, eax
0x180014449  jns     loc_1800144F7
0x18001444f  test    r13d, r13d
0x180014452  jnz     loc_1800144F7
0x180014458  mov     r12d, dword ptr [rsp+330h+var_2C0]
0x18001445d  xor     r13d, r13d
0x180014460  lea     rbx, WPP_GLOBAL_Control
0x180014467  mov     dword ptr [rsp+330h+fuLoad], r12d; nIconSize
0x18001446c  mov     qword ptr [rsp+330h+cy], rsi; phiconSmall
0x180014471  mov     r9, rdi; phiconLarge
0x180014474  xor     r8d, r8d; uFlags
0x180014477  mov     edx, [r14+20h]; iIndex
0x18001447b  lea     rcx, aImageresDll; "imageres.dll"
0x180014482  call    cs:__imp_SHDefExtractIconW
0x180014488  mov     r15d, eax
0x18001448b  test    eax, eax
0x18001448d  jns     short loc_1800144F0
0x18001448f  mov     dword ptr [rsp+330h+fuLoad], r12d; nIconSize
0x180014494  mov     qword ptr [rsp+330h+cy], rsi; phiconSmall
0x180014499  mov     r9, rdi; phiconLarge
0x18001449c  xor     r8d, r8d; uFlags
0x18001449f  mov     edx, [r14+20h]; iIndex
0x1800144a3  lea     rcx, aShell32Dll_0; "shell32.dll"
0x1800144aa  call    cs:__imp_SHDefExtractIconW
0x1800144b0  mov     r15d, eax
0x1800144b3  test    eax, eax
0x1800144b5  jns     short loc_1800144F0
0x1800144b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144be  cmp     rcx, rbx
0x1800144c1  jz      short loc_180014467
0x1800144c3  test    byte ptr [rcx+1Ch], 2
0x1800144c7  jz      short loc_180014467
0x1800144c9  mov     edx, 0Fh
0x1800144ce  mov     dword ptr [rsp+330h+fuLoad], eax
0x1800144d2  mov     [rsp+330h+cy], r12d
0x1800144d7  mov     r9d, [r14+20h]
0x1800144db  lea     r8, WPP_6b280ac677813e2ddcf838599857c188_Traceguids
0x1800144e2  mov     rcx, [rcx+10h]
0x1800144e6  call    WPP_SF_ddd
0x1800144eb  jmp     loc_180014467
0x1800144f0  mov     rbx, [rsp+330h+name]
0x1800144f5  jmp     short loc_1800144FA
0x1800144f7  xor     r13d, r13d
0x1800144fa  lea     r12, [rbx-18h]
0x1800144fe  cmp     [r12+8], r13d
0x180014503  jle     short loc_18001450E
0x180014505  mov     rcx, rbx; lpFileName
0x180014508  call    cs:__imp_DeleteFileW
0x18001450e  mov     [rsp+330h+name], r13
0x180014513  cmp     dword ptr [rbp+230h+var_2A0], 0Ch
0x180014517  jnz     loc_1800146D0
0x18001451d  mov     rax, cs:WPP_GLOBAL_Control
0x180014524  mov     edi, 800h
0x180014529  test    [rax+1Ch], edi
0x18001452c  jz      loc_1800146D0
0x180014532  lea     rcx, [rsp+330h+name]; lpPerformanceCount
0x180014537  call    cs:__imp_QueryPerformanceCounter
0x18001453d  mov     rdx, qword ptr [rbp+230h+Frequency]
0x180014541  test    rdx, rdx
0x180014544  jnz     short loc_180014565
0x180014546  lea     rcx, [rbp+230h+Frequency]; lpFrequency
0x18001454a  call    cs:__imp_QueryPerformanceFrequency
0x180014550  test    eax, eax
0x180014552  jz      loc_1800146D0
0x180014558  mov     rdx, qword ptr [rbp+230h+Frequency]
0x18001455c  test    rdx, rdx
0x18001455f  jz      loc_1800146D0
0x180014565  mov     rbx, [rsp+330h+name]
0x18001456a  mov     r8, qword ptr [rbp+230h+PerformanceCount]
0x18001456e  sub     rbx, r8
0x180014571  mov     eax, dword ptr [rbp+230h+var_2A0]
0x180014574  cmp     eax, 7
0x180014577  ja      short loc_1800145C1
0x180014579  jz      short loc_1800145E9
0x18001457b  sub     eax, 1
0x18001457e  jz      short loc_18001458A
0x180014580  sub     eax, 1
0x180014583  jz      short loc_1800145E9
0x180014585  sub     eax, 2
0x180014588  jmp     short loc_1800145C9
0x18001458a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014591  lea     r9, WPP_GLOBAL_Control
0x180014598  cmp     rcx, r9
0x18001459b  jz      short loc_1800145F0
0x18001459d  test    [rcx+1Ch], edi
0x1800145a0  jz      short loc_1800145F0
0x1800145a2  mov     edx, 7Dh ; '}'
0x1800145a7  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x1800145ae  mov     rcx, [rcx+10h]
0x1800145b2  call    WPP_SF_
0x1800145b7  mov     rdx, qword ptr [rbp+230h+Frequency]
0x1800145bb  mov     r8, qword ptr [rbp+230h+PerformanceCount]
0x1800145bf  jmp     short loc_1800145E9
0x1800145c1  sub     eax, 8
0x1800145c4  jz      short loc_1800145E9
0x1800145c6  sub     eax, 1
0x1800145c9  jz      short loc_1800145E9
0x1800145cb  sub     eax, 1
0x1800145ce  jz      short loc_1800145E9
0x1800145d0  cmp     eax, 1
0x1800145d3  jz      short loc_1800145E9
0x1800145d5  mov     rax, cs:WPP_GLOBAL_Control
0x1800145dc  test    dword ptr [rax+1Ch], 1000h
0x1800145e3  jz      loc_1800146D0
0x1800145e9  lea     r9, WPP_GLOBAL_Control
0x1800145f0  movsd   xmm2, cs:__real@408f400000000000
0x1800145f8  mov     rax, qword ptr [rbp+230h+PerformanceCount+8]
0x1800145fc  test    rax, rax
0x1800145ff  jnz     short loc_180014606
0x180014601  xorps   xmm6, xmm6
  ... truncated ...
```
