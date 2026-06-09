# CWebCrawler::OnDownloadComplete(uint,int)

- ea: `0x180020b50`
- end: `0x180021068`
- name: `?OnDownloadComplete@CWebCrawler@@UEAAJIH@Z`
- size: `1304`
- prototype: `__int64 __fastcall(CWebCrawler *__hidden this, unsigned int, int)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180006ee4`
- `0x18001dc84`
- `0x18001dcc4`
- `0x18001dd88`
- `0x18001e91c`
- `0x18001f4b4`
- `0x18001f7e0`
- `0x18001faa0`
- `0x18001fdc8`
- `0x1800200d8`
- `0x180020620`
- `0x180020b50`
- `0x1800215dc`
- `0x180021940`
- `0x18002211c`
- `0x1800228f0`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x180020e01`
- `KERNEL32!SystemTimeToFileTime` at `0x180020e01`
- `KERNEL32!LocalFree` at `0x180021031`
- `KERNEL32!LocalFree` at `0x180021031`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180021040`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180021040`

## pseudocode

```c
__int64 __fastcall CWebCrawler::OnDownloadComplete(CWebCrawler *this, __int64 a2, int a3)
{
  __int64 v3; // r15
  BOOL v6; // esi
  unsigned __int16 *v7; // r12
  __int64 v8; // rdx
  char *v9; // r14
  __int64 v10; // rdx
  struct _FILETIME v11; // rbx
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rcx
  CUrlDownload *v15; // r8
  unsigned int v16; // ecx
  int v17; // eax
  int Document; // eax
  struct _FILETIME v19; // r15
  int v20; // edx
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rax
  SYSTEMTIME *v24; // rcx
  int v25; // r13d
  int RealUrl; // eax
  unsigned int i; // ebx
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  int v31; // edx
  int v32; // eax
  int v34; // [rsp+30h] [rbp-39h] BYREF
  unsigned int dwLowDateTime_low; // [rsp+34h] [rbp-35h]
  struct _FILETIME FileTime; // [rsp+38h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-29h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-21h] BYREF
  BSTR v39; // [rsp+50h] [rbp-19h] BYREF
  struct _FILETIME v40; // [rsp+58h] [rbp-11h]
  SYSTEMTIME SystemTime; // [rsp+60h] [rbp-9h] BYREF

  v3 = *((int *)this + 62);
  dwLowDateTime_low = *((_DWORD *)this + 62);
  v34 = 0;
  v39 = 0;
  v6 = 0;
  hMem = 0;
  v7 = 0;
  if ( a3 != -1 )
    --*((_DWORD *)this + 66);
  v8 = *((_QWORD *)this + 7);
  v9 = (char *)this - 112;
  if ( *((_QWORD *)this + 32) == v8 )
  {
    v10 = *(_QWORD *)(v8 + 40);
    hMem = 0;
    if ( (int)CWebCrawler::ParseRobotsTxt(
                (CWebCrawler *)((char *)this - 112),
                *(const unsigned __int16 **)(v10 + 24 * v3),
                (struct CWCStringList **)&hMem) >= 0 )
      (*(void (__fastcall **)(_QWORD, _QWORD, HLOCAL))(**((_QWORD **)this + 7) + 32LL))(
        *((_QWORD *)this + 7),
        (unsigned int)v3,
        hMem);
    goto LABEL_82;
  }
  v11 = (struct _FILETIME)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v9 + 20) + 24LL))(
                            *((_QWORD *)v9 + 20),
                            (unsigned int)v3);
  v40 = v11;
  v12 = 1610612736;
  if ( a3 <= 0 )
    v12 = 0x40000000;
  v13 = v11.dwLowDateTime | v12;
  v14 = *((_QWORD *)this + 32);
  *(_QWORD *)&SystemTime.wYear = v13;
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 32LL))(v14, (unsigned int)v3, (unsigned int)v13);
  if ( *((_DWORD *)this + 49) == 1 )
  {
    v15 = (CUrlDownload *)*((_QWORD *)this + 29);
    v16 = *((_DWORD *)v15 + 48);
    if ( !v16 || v16 / 0x64 == 1 || v16 / 0x64 == 2 )
      goto LABEL_20;
    if ( v16 / 0x64 == 3 )
    {
      if ( v16 == 304 )
        goto LABEL_20;
    }
    else if ( v16 / 0x64 == 4 )
    {
      v17 = -2147024809;
      if ( v16 == 401 )
        v17 = -2146697207;
      *((_DWORD *)this - 1) = v17;
      goto LABEL_19;
    }
    *((_DWORD *)this - 1) = -2147024809;
LABEL_19:
    v6 = 1;
LABEL_20:
    bstrString = 0;
    FileTime = 0;
    Document = CUrlDownload::GetDocument(v15, (struct IHTMLDocument2 **)&FileTime);
    v19 = FileTime;
    if ( Document >= 0
      && *(_QWORD *)&FileTime
      && (*(int (__fastcall **)(struct _FILETIME, BSTR *))(**(_QWORD **)&FileTime + 384LL))(FileTime, &bstrString) >= 0
      && bstrString )
    {
      WriteOLESTR(*((struct ISubscriptionItem **)this - 4), L"CharSet", bstrString);
      SysFreeString(bstrString);
    }
    else
    {
      WriteEMPTY(*((struct ISubscriptionItem **)this - 4), L"CharSet");
    }
    if ( v19 )
    {
      FileTime = 0;
      if ( !(unsigned int)SearchForElementInHead(v19.dwLowDateTime, v20, v21, v22, (__int64)&FileTime) )
      {
        v11 = FileTime;
        (*(void (__fastcall **)(struct _FILETIME, BSTR *))(**(_QWORD **)&FileTime + 64LL))(FileTime, &v39);
        (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v11 + 16LL))(v11);
        LOBYTE(v11.dwLowDateTime) = v40.dwLowDateTime;
      }
      (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v19 + 16LL))(v19);
    }
    LODWORD(v3) = dwLowDateTime_low;
  }
  if ( (unsigned int)(a3 + 1) <= 1 )
  {
    v11.dwLowDateTime = LOBYTE(v11.dwLowDateTime);
    dwLowDateTime_low = LOBYTE(v11.dwLowDateTime);
    if ( !v6 )
    {
      if ( (*((_DWORD *)this - 17) & 0x40000000) != 0 )
      {
        v23 = *((_QWORD *)v9 + 43);
        SystemTime = 0;
        FileTime = 0;
        v24 = *(SYSTEMTIME **)(v23 + 184);
        if ( v24 )
        {
          SystemTime = *v24;
          if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
          {
            if ( (int)PostCheckUrlForChange((struct tagVARIANT *)((char *)this + 272), 0, FileTime) <= 0 )
              *((_DWORD *)this - 17) |= 0x80000000;
            WriteVariant(
              *((struct ISubscriptionItem **)this - 4),
              L"ChangeCode",
              (const struct tagVARIANT *)((char *)this + 272));
            v25 = v34;
LABEL_43:
            v11.dwLowDateTime = dwLowDateTime_low;
            goto LABEL_44;
          }
        }
      }
      else
      {
        RealUrl = CWebCrawler::GetRealUrl((CWebCrawler *)v9, v3, (unsigned __int16 **)&hMem);
        v7 = (unsigned __int16 *)hMem;
        if ( RealUrl >= 0 )
        {
          if ( !(_DWORD)v3 && *((_DWORD *)this + 7) && (*((_BYTE *)this + 24) & 0x20) == 0 && !*((_QWORD *)this + 26) )
            CWebCrawler::GetHostName((PCWSTR)hMem, (unsigned __int16 **)this + 26);
          LODWORD(bstrString) = 0;
          for ( i = 0; i <= 2; ++i )
          {
            v34 = 0;
            CWebCrawler::MakePageStickyAndGetSize((CWebCrawler *)v9, v7, (unsigned int *)&bstrString, &v34);
            v25 = v34;
            if ( !v34 || i >= 2 )
              break;
            v28 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD))(**((_QWORD **)this - 5) + 48LL))(
                    *((_QWORD *)this - 5),
                    (char *)this - 24,
                    2148274064LL,
                    0);
            if ( v28 == -2147483638 )
            {
              *((_DWORD *)this - 17) |= 0x400000u;
              goto LABEL_86;
            }
            if ( v28 != 790416 )
              break;
          }
          *((_DWORD *)this + 38) += (_DWORD)bstrString;
          if ( !v25 && !(_DWORD)v3 && !*(_DWORD *)(*((_QWORD *)this + 29) + 132LL) )
          {
            v29 = CWebCrawler::FindAndSubmitForm((CWebCrawler *)v9);
            if ( !v29 )
              return 0;
            if ( v29 < 0 )
            {
              *((_DWORD *)this - 1) = -2147467259;
              (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 120LL))(v9);
              return 0;
            }
          }
          if ( *((int *)this + 54) >= 0 )
            goto LABEL_43;
          v11.dwLowDateTime = dwLowDateTime_low;
          if ( !dwLowDateTime_low && (*(_DWORD *)&SystemTime.wYear & 0x10000000) == 0 )
          {
            v30 = *((_QWORD *)this + 7);
            if ( v30 )
              v31 = *(_DWORD *)(v30 + 12);
            else
              v31 = 0;
            *((_DWORD *)this + 54) = v31 + *(_DWORD *)(*((_QWORD *)this + 6) + 12LL);
          }
LABEL_44:
          if ( (*((_DWORD *)this - 17) & 0x200000) != 0 )
          {
            v6 = 1;
          }
          else if ( !v6 && v25 )
          {
LABEL_78:
            *((_DWORD *)this - 1) = v25 != 0 ? -2146693246 : -2146693248;
            goto LABEL_35;
          }
          v32 = *((_DWORD *)this + 8);
          if ( !v32 || *((_DWORD *)this + 38) < (unsigned int)(v32 << 10) )
          {
            if ( !v6 )
            {
              CWebCrawler::GetDependencyLinksFromPage((CWebCrawler *)v9, v7, v11.dwLowDateTime);
              if ( v11.dwLowDateTime )
              {
                CWebCrawler::GetLinksFromPage((CWebCrawler *)v9);
                *((_DWORD *)this + 37) = v11.dwLowDateTime - 1;
              }
            }
            goto LABEL_82;
          }
          goto LABEL_78;
        }
        v6 = 1;
      }
    }
    v25 = v34;
    goto LABEL_44;
  }
  if ( a3 == 5 )
    goto LABEL_82;
  ++*((_DWORD *)this + 55);
  if ( a3 != 3 )
    goto LABEL_82;
  *((_DWORD *)this - 1) = -2146693248;
LABEL_35:
  v6 = 1;
LABEL_82:
  if ( !*((_DWORD *)v9 + 104) && !v6 )
    v6 = (int)CWebCrawler::StartNextDownload((CWebCrawler *)v9) < 0;
  CWebCrawler::CheckOperationComplete((CWebCrawler *)v9, v6);
LABEL_86:
  if ( v7 )
    LocalFree(v7);
  if ( v39 )
    SysFreeString(v39);
  return 0;
}

```

## disassembly

```asm
0x180020b50  push    rbp
0x180020b52  push    rbx
0x180020b53  push    rsi
0x180020b54  push    rdi
0x180020b55  push    r12
0x180020b57  push    r13
0x180020b59  push    r14
0x180020b5b  push    r15
0x180020b5d  lea     rbp, [rsp-1Fh]
0x180020b62  sub     rsp, 88h
0x180020b69  mov     rax, cs:__security_cookie
0x180020b70  xor     rax, rsp
0x180020b73  mov     [rbp+57h+var_50], rax
0x180020b77  movsxd  r15, dword ptr [rcx+0F8h]
0x180020b7e  xor     eax, eax
0x180020b80  mov     [rbp+57h+var_8C], r15d
0x180020b84  mov     r13d, r8d
0x180020b87  mov     [rbp+57h+var_90], eax
0x180020b8a  mov     rdi, rcx
0x180020b8d  mov     [rbp+57h+var_70], rax
0x180020b91  mov     esi, eax
0x180020b93  mov     [rbp+57h+hMem], rax
0x180020b97  mov     r12d, eax
0x180020b9a  cmp     r8d, 0FFFFFFFFh
0x180020b9e  jz      short loc_180020BA6
0x180020ba0  dec     dword ptr [rcx+108h]
0x180020ba6  mov     rdx, [rcx+38h]
0x180020baa  lea     r14, [rcx-70h]
0x180020bae  mov     ebx, 1
0x180020bb3  cmp     [rcx+100h], rdx
0x180020bba  jnz     short loc_180020BFC
0x180020bbc  mov     rdx, [rdx+28h]
0x180020bc0  lea     rcx, [r15+r15*2]
0x180020bc4  lea     r8, [rbp+57h+hMem]; struct CWCStringList **
0x180020bc8  mov     [rbp+57h+hMem], rax
0x180020bcc  mov     rdx, [rdx+rcx*8]; unsigned __int16 *
0x180020bd0  mov     rcx, r14; this
0x180020bd3  call    ?ParseRobotsTxt@CWebCrawler@@IEAAJPEBGPEAPEAVCWCStringList@@@Z; CWebCrawler::ParseRobotsTxt(ushort const *,CWCStringList * *)
0x180020bd8  test    eax, eax
0x180020bda  js      loc_180021004
0x180020be0  mov     rcx, [rdi+38h]
0x180020be4  mov     edx, r15d
0x180020be7  mov     r8, [rbp+57h+hMem]
0x180020beb  mov     rax, [rcx]
0x180020bee  mov     rax, [rax+20h]
0x180020bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bf7  jmp     loc_180021004
0x180020bfc  mov     rcx, [r14+0A0h]
0x180020c03  mov     edx, r15d
0x180020c06  mov     rax, [rcx]
0x180020c09  mov     rax, [rax+18h]
0x180020c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c12  mov     rbx, rax
0x180020c15  mov     [rbp+57h+var_68], rax
0x180020c19  mov     eax, 40000000h
0x180020c1e  mov     ecx, 60000000h
0x180020c23  test    r13d, r13d
0x180020c26  cmovle  ecx, eax
0x180020c29  or      ecx, ebx
0x180020c2b  mov     eax, ecx
0x180020c2d  mov     rcx, [rdi+100h]
0x180020c34  mov     r8d, eax
0x180020c37  mov     qword ptr [rbp+57h+SystemTime.wYear], rax
0x180020c3b  mov     rdx, [rcx]
0x180020c3e  mov     rax, [rdx+20h]
0x180020c42  mov     edx, r15d
0x180020c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c4a  cmp     dword ptr [rdi+0C4h], 1
0x180020c51  jnz     loc_180020D7E
0x180020c57  mov     r8, [rdi+0E8h]
0x180020c5e  mov     ecx, [r8+0C0h]
0x180020c65  test    ecx, ecx
0x180020c67  jz      short loc_180020CB3
0x180020c69  mov     eax, 51EB851Fh
0x180020c6e  mul     ecx
0x180020c70  shr     edx, 5
0x180020c73  sub     edx, 1
0x180020c76  jz      short loc_180020CB3
0x180020c78  sub     edx, 1
0x180020c7b  jz      short loc_180020CB3
0x180020c7d  sub     edx, 1
0x180020c80  jz      short loc_180020C9F
0x180020c82  cmp     edx, 1
0x180020c85  jnz     short loc_180020CA7
0x180020c87  cmp     ecx, 191h
0x180020c8d  mov     eax, 80070057h
0x180020c92  mov     edx, 800C0009h
0x180020c97  cmovz   eax, edx
0x180020c9a  mov     [rdi-4], eax
0x180020c9d  jmp     short loc_180020CAE
0x180020c9f  cmp     ecx, 130h
0x180020ca5  jz      short loc_180020CB3
0x180020ca7  mov     dword ptr [rdi-4], 80070057h
0x180020cae  mov     esi, 1
0x180020cb3  lea     rdx, [rbp+57h+FileTime]; struct IHTMLDocument2 **
0x180020cb7  mov     [rbp+57h+bstrString], r12
0x180020cbb  mov     rcx, r8; this
0x180020cbe  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r12
0x180020cc2  call    ?GetDocument@CUrlDownload@@QEAAJPEAPEAUIHTMLDocument2@@@Z; CUrlDownload::GetDocument(IHTMLDocument2 * *)
0x180020cc7  mov     r15, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180020ccb  test    eax, eax
0x180020ccd  js      short loc_180020D13
0x180020ccf  test    r15, r15
0x180020cd2  jz      short loc_180020D13
0x180020cd4  mov     rax, [r15]
0x180020cd7  lea     rdx, [rbp+57h+bstrString]
0x180020cdb  mov     rcx, r15
0x180020cde  mov     rax, [rax+180h]
0x180020ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cea  test    eax, eax
0x180020cec  js      short loc_180020D13
0x180020cee  mov     r8, [rbp+57h+bstrString]; unsigned __int16 *
0x180020cf2  test    r8, r8
0x180020cf5  jz      short loc_180020D13
0x180020cf7  mov     rcx, [rdi-20h]; struct ISubscriptionItem *
0x180020cfb  lea     rdx, ?c_szPropCharSet@@3QBGB; "CharSet"
0x180020d02  call    ?WriteOLESTR@@YAJPEAUISubscriptionItem@@PEBG1@Z; WriteOLESTR(ISubscriptionItem *,ushort const *,ushort const *)
0x180020d07  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180020d0b  call    cs:__imp_SysFreeString
0x180020d11  jmp     short loc_180020D23
0x180020d13  mov     rcx, [rdi-20h]; struct ISubscriptionItem *
0x180020d17  lea     rdx, ?c_szPropCharSet@@3QBGB; "CharSet"
0x180020d1e  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x180020d23  test    r15, r15
0x180020d26  jz      short loc_180020D7A
0x180020d28  lea     rax, [rbp+57h+FileTime]
0x180020d2c  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r12
0x180020d30  mov     rcx, r15
0x180020d33  mov     [rsp+0C0h+var_A0], rax
0x180020d38  call    SearchForElementInHead
0x180020d3d  test    eax, eax
0x180020d3f  jnz     short loc_180020D6B
0x180020d41  mov     rbx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180020d45  lea     rdx, [rbp+57h+var_70]
0x180020d49  mov     rcx, rbx
0x180020d4c  mov     rax, [rbx]
0x180020d4f  mov     rax, [rax+40h]
0x180020d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d58  mov     rax, [rbx]
0x180020d5b  mov     rcx, rbx
0x180020d5e  mov     rax, [rax+10h]
0x180020d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d67  mov     rbx, [rbp+57h+var_68]
0x180020d6b  mov     rax, [r15]
0x180020d6e  mov     rcx, r15
0x180020d71  mov     rax, [rax+10h]
0x180020d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d7a  mov     r15d, [rbp+57h+var_8C]
0x180020d7e  lea     eax, [r13+1]
0x180020d82  cmp     eax, 1
0x180020d85  jbe     short loc_180020DB4
0x180020d87  cmp     r13d, 5
0x180020d8b  jz      loc_180020FFF
0x180020d91  inc     dword ptr [rdi+0DCh]
0x180020d97  cmp     r13d, 3
0x180020d9b  jnz     loc_180020FFF
0x180020da1  mov     dword ptr [rdi-4], 800C0F80h
0x180020da8  mov     esi, 1
0x180020dad  mov     ebx, esi
0x180020daf  jmp     loc_180021004
0x180020db4  movzx   ebx, bl
0x180020db7  mov     [rbp+57h+var_8C], ebx
0x180020dba  test    esi, esi
0x180020dbc  jnz     loc_180020E76
0x180020dc2  test    dword ptr [rdi-44h], 40000000h
0x180020dc9  jz      loc_180020E5A
0x180020dcf  mov     rax, [r14+158h]
0x180020dd6  xorps   xmm0, xmm0
0x180020dd9  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180020ddd  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r12
0x180020de1  mov     rcx, [rax+0B8h]
0x180020de8  test    rcx, rcx
0x180020deb  jz      loc_180020E76
0x180020df1  movups  xmm0, xmmword ptr [rcx]
0x180020df4  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180020df8  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180020dfc  movdqu  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180020e01  call    cs:__imp_SystemTimeToFileTime
0x180020e07  test    eax, eax
0x180020e09  jz      short loc_180020E76
0x180020e0b  mov     r8, qword ptr [rbp+57h+FileTime.dwLowDateTime]; struct _FILETIME
0x180020e0f  lea     rbx, [rdi+110h]
0x180020e16  mov     rcx, rbx; struct tagVARIANT *
0x180020e19  xor     edx, edx; struct _INTERNET_CACHE_ENTRY_INFOW *
0x180020e1b  call    ?PostCheckUrlForChange@@YAJPEAUtagVARIANT@@PEAU_INTERNET_CACHE_ENTRY_INFOW@@U_FILETIME@@@Z; PostCheckUrlForChange(tagVARIANT *,_INTERNET_CACHE_ENTRY_INFOW *,_FILETIME)
0x180020e20  test    eax, eax
0x180020e22  jg      short loc_180020E29
0x180020e24  bts     dword ptr [rdi-44h], 1Fh
0x180020e29  mov     rcx, [rdi-20h]; struct ISubscriptionItem *
0x180020e2d  lea     rdx, ?c_szPropChangeCode@@3QBGB; "ChangeCode"
0x180020e34  mov     r8, rbx; struct tagVARIANT *
0x180020e37  call    ?WriteVariant@@YAJPEAUISubscriptionItem@@PEBGPEBUtagVARIANT@@@Z; WriteVariant(ISubscriptionItem *,ushort const *,tagVARIANT const *)
0x180020e3c  mov     r13d, [rbp+57h+var_90]
0x180020e40  mov     ebx, [rbp+57h+var_8C]
0x180020e43  test    dword ptr [rdi-44h], 200000h
0x180020e4a  jz      loc_180020FA8
0x180020e50  mov     esi, 1
0x180020e55  jmp     loc_180020FB1
0x180020e5a  lea     r8, [rbp+57h+hMem]; unsigned __int16 **
0x180020e5e  mov     edx, r15d; int
0x180020e61  mov     rcx, r14; this
0x180020e64  call    ?GetRealUrl@CWebCrawler@@IEAAJHPEAPEAG@Z; CWebCrawler::GetRealUrl(int,ushort * *)
0x180020e69  mov     r12, [rbp+57h+hMem]
0x180020e6d  test    eax, eax
0x180020e6f  jns     short loc_180020E7C
0x180020e71  mov     esi, 1
0x180020e76  mov     r13d, [rbp+57h+var_90]
0x180020e7a  jmp     short loc_180020E43
0x180020e7c  test    r15d, r15d
0x180020e7f  jnz     short loc_180020EA2
0x180020e81  cmp     [rdi+1Ch], r15d
0x180020e85  jbe     short loc_180020EA2
0x180020e87  test    byte ptr [rdi+18h], 20h
0x180020e8b  jnz     short loc_180020EA2
0x180020e8d  lea     rdx, [rdi+0D0h]; unsigned __int16 **
0x180020e94  cmp     qword ptr [rdx], 0
0x180020e98  jnz     short loc_180020EA2
0x180020e9a  mov     rcx, r12; pwszSrc
0x180020e9d  call    ?GetHostName@CWebCrawler@@KAJPEBGPEAPEAG@Z; CWebCrawler::GetHostName(ushort const *,ushort * *)
0x180020ea2  mov     dword ptr [rbp+57h+bstrString], 0
0x180020ea9  xor     ebx, ebx
0x180020eab  lea     r9, [rbp+57h+var_90]; int *
0x180020eaf  mov     [rbp+57h+var_90], 0
0x180020eb6  lea     r8, [rbp+57h+bstrString]; unsigned int *
0x180020eba  mov     rdx, r12; unsigned __int16 *
0x180020ebd  mov     rcx, r14; this
0x180020ec0  call    ?MakePageStickyAndGetSize@CWebCrawler@@IEAAJPEBGPEAKPEAH@Z; CWebCrawler::MakePageStickyAndGetSize(ushort const *,ulong *,int *)
0x180020ec5  mov     r13d, [rbp+57h+var_90]
0x180020ec9  test    r13d, r13d
0x180020ecc  jz      short loc_180020F05
0x180020ece  cmp     ebx, 2
0x180020ed1  jnb     short loc_180020F05
0x180020ed3  mov     rcx, [rdi-28h]
0x180020ed7  lea     rdx, [rdi-18h]
0x180020edb  xor     r9d, r9d
0x180020ede  mov     r8d, 800C0F90h
0x180020ee4  mov     rax, [rcx]
0x180020ee7  mov     rax, [rax+30h]
0x180020eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ef0  cmp     eax, 8000000Ah
0x180020ef5  jz      short loc_180020F55
0x180020ef7  cmp     eax, 0C0F90h
0x180020efc  jnz     short loc_180020F05
0x180020efe  inc     ebx
0x180020f00  cmp     ebx, 2
0x180020f03  jbe     short loc_180020EAB
0x180020f05  mov     eax, dword ptr [rbp+57h+bstrString]
0x180020f08  add     [rdi+98h], eax
0x180020f0e  test    r13d, r13d
0x180020f11  jnz     short loc_180020F5F
0x180020f13  test    r15d, r15d
0x180020f16  jnz     short loc_180020F5F
0x180020f18  mov     rax, [rdi+0E8h]
0x180020f1f  cmp     [rax+84h], r15d
0x180020f26  jnz     short loc_180020F5F
0x180020f28  mov     rcx, r14; this
0x180020f2b  call    ?FindAndSubmitForm@CWebCrawler@@IEAAJXZ; CWebCrawler::FindAndSubmitForm(void)
0x180020f30  test    eax, eax
0x180020f32  jz      loc_180021046
0x180020f38  jns     short loc_180020F5F
0x180020f3a  mov     dword ptr [rdi-4], 80004005h
0x180020f41  mov     rcx, r14
0x180020f44  mov     rax, [r14]
0x180020f47  mov     rax, [rax+78h]
0x180020f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f50  jmp     loc_180021046
0x180020f55  bts     dword ptr [rdi-44h], 16h
0x180020f5a  jmp     loc_180021029
0x180020f5f  cmp     dword ptr [rdi+0D8h], 0
0x180020f66  jge     loc_180020E40
0x180020f6c  mov     ebx, [rbp+57h+var_8C]
0x180020f6f  test    ebx, ebx
0x180020f71  jnz     loc_180020E43
0x180020f77  test    dword ptr [rbp+57h+SystemTime.wYear], 10000000h
0x180020f7e  jnz     loc_180020E43
0x180020f84  mov     rax, [rdi+38h]
0x180020f88  test    rax, rax
0x180020f8b  jz      short loc_180020F92
0x180020f8d  mov     edx, [rax+0Ch]
0x180020f90  jmp     short loc_180020F94
0x180020f92  xor     edx, edx
0x180020f94  mov     rax, [rdi+30h]
0x180020f98  mov     eax, [rax+0Ch]
0x180020f9b  add     eax, edx
0x180020f9d  mov     [rdi+0D8h], eax
0x180020fa3  jmp     loc_180020E43
0x180020fa8  test    esi, esi
0x180020faa  jnz     short loc_180020FB1
0x180020fac  test    r13d, r13d
0x180020faf  jnz     short loc_180020FC3
0x180020fb1  mov     eax, [rdi+20h]
0x180020fb4  test    eax, eax
0x180020fb6  jz      short loc_180020FD8
0x180020fb8  shl     eax, 0Ah
0x180020fbb  cmp     [rdi+98h], eax
0x180020fc1  jb      short loc_180020FD8
0x180020fc3  neg     r13d
0x180020fc6  sbb     eax, eax
0x180020fc8  and     eax, 2
0x180020fcb  add     eax, 800C0F80h
  ... truncated ...
```
