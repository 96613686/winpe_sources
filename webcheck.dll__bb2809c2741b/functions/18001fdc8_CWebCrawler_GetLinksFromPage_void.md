# CWebCrawler::GetLinksFromPage(void)

- ea: `0x18001fdc8`
- end: `0x1800200cf`
- name: `?GetLinksFromPage@CWebCrawler@@IEAAJXZ`
- size: `775`
- prototype: `__int64 __fastcall(CWebCrawler *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180020b50`

## callees

- `0x180006ee4`
- `0x1800152e8`
- `0x1800154a0`
- `0x18001ba08`
- `0x18001eed0`
- `0x18001fdc8`
- `0x180020280`
- `0x18002924e`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!StrCmpNIW` at `0x18001fee8`
- `SHLWAPI!StrCmpNIW` at `0x18001ff21`
- `SHLWAPI!StrCmpNIW` at `0x18001fee8`
- `SHLWAPI!StrCmpNIW` at `0x18001ff21`
- `SHLWAPI!StrChrW` at `0x18001ff38`
- `SHLWAPI!StrChrW` at `0x18001ff38`

## pseudocode

```c
__int64 __fastcall CWebCrawler::GetLinksFromPage(CUrlDownload **this)
{
  CWCDwordStringList *v2; // rdi
  struct IHTMLDocument2 *v3; // rsi
  int TagCollection; // eax
  struct IHTMLDocument2 *v5; // rcx
  int i; // ebx
  const WCHAR *v7; // rbx
  PWSTR v8; // rax
  _QWORD *v9; // rax
  struct IHTMLDocument2 v10; // rax
  int v11; // eax
  struct IHTMLDocument2 *v12; // rcx
  int v13; // eax
  struct IHTMLDocument2 *v14; // rcx
  unsigned int v15; // ebx
  void **v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h]
  int v19; // [rsp+40h] [rbp-C0h]
  __int64 v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[1024]; // [rsp+60h] [rbp-A0h] BYREF
  struct IHTMLDocument2 *v24; // [rsp+490h] [rbp+390h] BYREF

  v17 = &CWCStringList::`vftable';
  v18 = 0;
  v19 = 0;
  v21 = 0;
  v2 = 0;
  v20 = 0;
  v22 = 0;
  memset_0(v23, 0, 0x3F8u);
  v24 = 0;
  CWCStringList::Init((CWCStringList *)&v17, 2048);
  CUrlDownload::GetDocument(this[43], &v24);
  v3 = v24;
  if ( v24 )
  {
    v24 = 0;
    TagCollection = CHelperOM::GetTagCollection(v3, L"meta", (struct IHTMLElementCollection **)&v24);
    v5 = v24;
    if ( v24 )
    {
      if ( TagCollection >= 0 )
      {
        CHelperOM::EnumCollection(v24, &v17, 3, 0, 0);
        v5 = v24;
      }
      if ( v5 )
        ((void (__fastcall *)(struct IHTMLDocument2 *))v5->lpVtbl->Release)(v5);
    }
    for ( i = 0; i < SHIDWORD(v18); ++i )
    {
      if ( !StrCmpNIW(*(PCWSTR *)(v22 + 24LL * i), L"Robots\n", 7) )
      {
        _mm_lfence();
        v7 = (const WCHAR *)(*(_QWORD *)(v22 + 24LL * i) + 14LL);
        while ( v7 && *v7 )
        {
          if ( !StrCmpNIW(v7, L"NoFollow", 8) )
            goto LABEL_31;
          v8 = StrChrW(v7 + 1, 0x2Cu);
          v7 = v8;
          if ( v8 )
          {
            if ( *v8 )
              v7 = v8 + 1;
          }
        }
        break;
      }
    }
    v2 = this[22];
    if ( !v2 )
    {
      v9 = operator new(0x438u);
      v2 = (CWCDwordStringList *)v9;
      if ( !v9 )
      {
        v15 = -2147024882;
        goto LABEL_33;
      }
      v9[1] = 0;
      *((_DWORD *)v9 + 4) = 0;
      v9[4] = 0;
      v9[3] = 0;
      v9[5] = 0;
      memset_0(v9 + 6, 0, 0x3F8u);
      *((_QWORD *)v2 + 134) = 0;
      *(_QWORD *)v2 = &CWCDwordStringList::`vftable';
      CWCDwordStringList::Init(v2, -1);
    }
    v10.lpVtbl = v3->lpVtbl;
    v24 = 0;
    v11 = ((__int64 (__fastcall *)(struct IHTMLDocument2 *, struct IHTMLDocument2 **))v10.lpVtbl->get_links)(v3, &v24);
    v12 = v24;
    if ( v24 )
    {
      if ( v11 >= 0 )
      {
        CHelperOM::EnumCollection(v24, v2, 0, CWebCrawler::CheckLink, this);
        v12 = v24;
      }
      if ( v12 )
        ((void (__fastcall *)(struct IHTMLDocument2 *))v12->lpVtbl->Release)(v12);
    }
    v24 = 0;
    v13 = CHelperOM::GetTagCollection(v3, L"map", (struct IHTMLElementCollection **)&v24);
    v14 = v24;
    if ( v24 )
    {
      if ( v13 >= 0 )
      {
        CHelperOM::EnumCollection(v24, v2, 1, CWebCrawler::CheckLink, this);
        v14 = v24;
      }
      if ( v14 )
        ((void (__fastcall *)(struct IHTMLDocument2 *))v14->lpVtbl->Release)(v14);
    }
LABEL_31:
    ((void (__fastcall *)(struct IHTMLDocument2 *))v3->lpVtbl->Release)(v3);
  }
  this[22] = v2;
  v15 = 0;
LABEL_33:
  v17 = &CWCStringList::`vftable';
  CWCStringList::CleanUp((CWCStringList *)&v17);
  return v15;
}

```

## disassembly

```asm
0x18001fdc8  mov     [rsp-8+arg_8], rbx
0x18001fdcd  mov     [rsp-8+arg_10], rsi
0x18001fdd2  push    rbp
0x18001fdd3  push    rdi
0x18001fdd4  push    r12
0x18001fdd6  push    r14
0x18001fdd8  push    r15
0x18001fdda  lea     rbp, [rsp-360h]
0x18001fde2  sub     rsp, 460h
0x18001fde9  xor     r12d, r12d
0x18001fdec  lea     r15, ??_7CWCStringList@@6B@; const CWCStringList::`vftable'
0x18001fdf3  mov     r14, rcx
0x18001fdf6  mov     [rsp+480h+var_450], r15
0x18001fdfb  lea     rcx, [rsp+480h+var_420]; void *
0x18001fe00  mov     [rsp+480h+var_448], r12
0x18001fe05  xor     edx, edx; Val
0x18001fe07  mov     [rsp+480h+var_440], r12d
0x18001fe0c  mov     r8d, 3F8h; Size
0x18001fe12  mov     [rsp+480h+var_430], r12
0x18001fe17  mov     edi, r12d
0x18001fe1a  mov     [rsp+480h+var_438], r12
0x18001fe1f  mov     [rsp+480h+var_428], r12
0x18001fe24  call    memset_0
0x18001fe29  mov     edx, 800h; int
0x18001fe2e  mov     [rbp+380h+arg_0], r12
0x18001fe35  lea     rcx, [rsp+480h+var_450]; this
0x18001fe3a  call    ?Init@CWCStringList@@UEAAHH@Z; CWCStringList::Init(int)
0x18001fe3f  mov     rcx, [r14+158h]; this
0x18001fe46  lea     rdx, [rbp+380h+arg_0]; struct IHTMLDocument2 **
0x18001fe4d  call    ?GetDocument@CUrlDownload@@QEAAJPEAPEAUIHTMLDocument2@@@Z; CUrlDownload::GetDocument(IHTMLDocument2 * *)
0x18001fe52  mov     rsi, [rbp+380h+arg_0]
0x18001fe59  test    rsi, rsi
0x18001fe5c  jz      loc_18002008A
0x18001fe62  lea     r8, [rbp+380h+arg_0]; struct IHTMLElementCollection **
0x18001fe69  mov     [rbp+380h+arg_0], r12
0x18001fe70  lea     rdx, aMeta; "meta"
0x18001fe77  mov     rcx, rsi; struct IHTMLDocument2 *
0x18001fe7a  call    ?GetTagCollection@CHelperOM@@SAJPEAUIHTMLDocument2@@PEBGPEAPEAUIHTMLElementCollection@@@Z; CHelperOM::GetTagCollection(IHTMLDocument2 *,ushort const *,IHTMLElementCollection * *)
0x18001fe7f  mov     rcx, [rbp+380h+arg_0]
0x18001fe86  test    rcx, rcx
0x18001fe89  jz      short loc_18001FEBE
0x18001fe8b  test    eax, eax
0x18001fe8d  js      short loc_18001FEAD
0x18001fe8f  xor     r9d, r9d
0x18001fe92  mov     [rsp+480h+var_460], r12
0x18001fe97  lea     r8d, [r12+3]
0x18001fe9c  lea     rdx, [rsp+480h+var_450]
0x18001fea1  call    ?EnumCollection@CHelperOM@@SAJPEAUIHTMLElementCollection@@PEAVCWCStringList@@W4CollectionType@1@P6AJPEAUIUnknown@@PEAPEAG_KPEAK@Z5@Z; CHelperOM::EnumCollection(IHTMLElementCollection *,CWCStringList *,CHelperOM::CollectionType,long (*)(IUnknown *,ushort * *,unsigned __int64,ulong *),unsigned __int64)
0x18001fea6  mov     rcx, [rbp+380h+arg_0]
0x18001fead  test    rcx, rcx
0x18001feb0  jz      short loc_18001FEBE
0x18001feb2  mov     rax, [rcx]
0x18001feb5  mov     rax, [rax+10h]
0x18001feb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001febe  mov     ebx, r12d
0x18001fec1  cmp     ebx, dword ptr [rsp+480h+var_448+4]
0x18001fec5  jge     loc_18001FF52
0x18001fecb  mov     rcx, [rsp+480h+var_428]
0x18001fed0  lea     rdx, psz2; "Robots\n"
0x18001fed7  movsxd  rax, ebx
0x18001feda  mov     r8d, 7; nChar
0x18001fee0  lea     r15, [rax+rax*2]
0x18001fee4  mov     rcx, [rcx+r15*8]; psz1
0x18001fee8  call    cs:__imp_StrCmpNIW
0x18001feee  test    eax, eax
0x18001fef0  jz      short loc_18001FEF6
0x18001fef2  inc     ebx
0x18001fef4  jmp     short loc_18001FEC1
0x18001fef6  lfence
0x18001fef9  mov     rax, [rsp+480h+var_428]
0x18001fefe  mov     rbx, [rax+r15*8]
0x18001ff02  add     rbx, 0Eh
0x18001ff06  test    rbx, rbx
0x18001ff09  jz      short loc_18001FF52
0x18001ff0b  cmp     [rbx], r12w
0x18001ff0f  jz      short loc_18001FF52
0x18001ff11  mov     r8d, 8; nChar
0x18001ff17  lea     rdx, aNofollow; "NoFollow"
0x18001ff1e  mov     rcx, rbx; psz1
0x18001ff21  call    cs:__imp_StrCmpNIW
0x18001ff27  test    eax, eax
0x18001ff29  jz      loc_180020074
0x18001ff2f  mov     edx, 2Ch ; ','; wMatch
0x18001ff34  lea     rcx, [rbx+2]; pszStart
0x18001ff38  call    cs:__imp_StrChrW
0x18001ff3e  mov     rbx, rax
0x18001ff41  test    rax, rax
0x18001ff44  jz      short loc_18001FF06
0x18001ff46  cmp     [rax], r12w
0x18001ff4a  jz      short loc_18001FF06
0x18001ff4c  add     rbx, 2
0x18001ff50  jmp     short loc_18001FF06
0x18001ff52  mov     rdi, [r14+0B0h]
0x18001ff59  test    rdi, rdi
0x18001ff5c  jnz     short loc_18001FFB9
0x18001ff5e  mov     ecx, 438h; dwBytes
0x18001ff63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ff68  mov     rdi, rax
0x18001ff6b  test    rax, rax
0x18001ff6e  jz      loc_1800200C1
0x18001ff74  lea     rcx, [rax+30h]; void *
0x18001ff78  mov     [rax+8], r12
0x18001ff7c  xor     edx, edx; Val
0x18001ff7e  mov     [rax+10h], r12d
0x18001ff82  mov     r8d, 3F8h; Size
0x18001ff88  mov     [rax+20h], r12
0x18001ff8c  mov     [rax+18h], r12
0x18001ff90  mov     [rax+28h], r12
0x18001ff94  call    memset_0
0x18001ff99  lea     rax, ??_7CWCDwordStringList@@6B@; const CWCDwordStringList::`vftable'
0x18001ffa0  mov     [rdi+430h], r12
0x18001ffa7  mov     [rdi], rax
0x18001ffaa  or      edx, 0FFFFFFFFh
0x18001ffad  mov     rax, [rax+8]
0x18001ffb1  mov     rcx, rdi
0x18001ffb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffb9  mov     rax, [rsi]
0x18001ffbc  lea     rdx, [rbp+380h+arg_0]
0x18001ffc3  mov     rcx, rsi
0x18001ffc6  mov     [rbp+380h+arg_0], r12
0x18001ffcd  mov     rax, [rax+68h]
0x18001ffd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffd6  mov     rcx, [rbp+380h+arg_0]
0x18001ffdd  test    rcx, rcx
0x18001ffe0  jz      short loc_180020015
0x18001ffe2  test    eax, eax
0x18001ffe4  js      short loc_180020004
0x18001ffe6  lea     r9, ?CheckLink@CWebCrawler@@KAJPEAUIUnknown@@PEAPEAG_KPEAK@Z; CWebCrawler::CheckLink(IUnknown *,ushort * *,unsigned __int64,ulong *)
0x18001ffed  mov     [rsp+480h+var_460], r14
0x18001fff2  xor     r8d, r8d
0x18001fff5  mov     rdx, rdi
0x18001fff8  call    ?EnumCollection@CHelperOM@@SAJPEAUIHTMLElementCollection@@PEAVCWCStringList@@W4CollectionType@1@P6AJPEAUIUnknown@@PEAPEAG_KPEAK@Z5@Z; CHelperOM::EnumCollection(IHTMLElementCollection *,CWCStringList *,CHelperOM::CollectionType,long (*)(IUnknown *,ushort * *,unsigned __int64,ulong *),unsigned __int64)
0x18001fffd  mov     rcx, [rbp+380h+arg_0]
0x180020004  test    rcx, rcx
0x180020007  jz      short loc_180020015
0x180020009  mov     rax, [rcx]
0x18002000c  mov     rax, [rax+10h]
0x180020010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020015  lea     r8, [rbp+380h+arg_0]; struct IHTMLElementCollection **
0x18002001c  mov     [rbp+380h+arg_0], r12
0x180020023  lea     rdx, aMap; "map"
0x18002002a  mov     rcx, rsi; struct IHTMLDocument2 *
0x18002002d  call    ?GetTagCollection@CHelperOM@@SAJPEAUIHTMLDocument2@@PEBGPEAPEAUIHTMLElementCollection@@@Z; CHelperOM::GetTagCollection(IHTMLDocument2 *,ushort const *,IHTMLElementCollection * *)
0x180020032  mov     rcx, [rbp+380h+arg_0]
0x180020039  test    rcx, rcx
0x18002003c  jz      short loc_180020074
0x18002003e  test    eax, eax
0x180020040  js      short loc_180020063
0x180020042  lea     r9, ?CheckLink@CWebCrawler@@KAJPEAUIUnknown@@PEAPEAG_KPEAK@Z; CWebCrawler::CheckLink(IUnknown *,ushort * *,unsigned __int64,ulong *)
0x180020049  mov     [rsp+480h+var_460], r14
0x18002004e  mov     r8d, 1
0x180020054  mov     rdx, rdi
0x180020057  call    ?EnumCollection@CHelperOM@@SAJPEAUIHTMLElementCollection@@PEAVCWCStringList@@W4CollectionType@1@P6AJPEAUIUnknown@@PEAPEAG_KPEAK@Z5@Z; CHelperOM::EnumCollection(IHTMLElementCollection *,CWCStringList *,CHelperOM::CollectionType,long (*)(IUnknown *,ushort * *,unsigned __int64,ulong *),unsigned __int64)
0x18002005c  mov     rcx, [rbp+380h+arg_0]
0x180020063  test    rcx, rcx
0x180020066  jz      short loc_180020074
0x180020068  mov     rax, [rcx]
0x18002006b  mov     rax, [rax+10h]
0x18002006f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020074  mov     rax, [rsi]
0x180020077  mov     rcx, rsi
0x18002007a  mov     rax, [rax+10h]
0x18002007e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020083  lea     r15, ??_7CWCStringList@@6B@; const CWCStringList::`vftable'
0x18002008a  mov     [r14+0B0h], rdi
0x180020091  mov     ebx, r12d
0x180020094  lea     rcx, [rsp+480h+var_450]; this
0x180020099  mov     [rsp+480h+var_450], r15
0x18002009e  call    ?CleanUp@CWCStringList@@IEAAXXZ; CWCStringList::CleanUp(void)
0x1800200a3  lea     r11, [rsp+480h+var_20]
0x1800200ab  mov     eax, ebx
0x1800200ad  mov     rbx, [r11+38h]
0x1800200b1  mov     rsi, [r11+40h]
0x1800200b5  mov     rsp, r11
0x1800200b8  pop     r15
0x1800200ba  pop     r14
0x1800200bc  pop     r12
0x1800200be  pop     rdi
0x1800200bf  pop     rbp
0x1800200c0  retn
0x1800200c1  mov     ebx, 8007000Eh
0x1800200c6  lea     r15, ??_7CWCStringList@@6B@; const CWCStringList::`vftable'
0x1800200cd  jmp     short loc_180020094
```
