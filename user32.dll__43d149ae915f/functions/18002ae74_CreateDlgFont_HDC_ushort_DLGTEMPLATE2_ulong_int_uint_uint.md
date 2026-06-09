# CreateDlgFont(HDC__ *,ushort * *,DLGTEMPLATE2 *,ulong,int *,uint,uint)

- ea: `0x18002ae74`
- end: `0x18002b287`
- name: `?CreateDlgFont@@YAPEAUHFONT__@@PEAUHDC__@@PEAPEAGPEAUDLGTEMPLATE2@@KPEAHII@Z`
- size: `1043`
- prototype: `HFONT __usercall@<rax>(HDC hdc@<rcx>, unsigned __int16 **@<rdx>, struct DLGTEMPLATE2 *@<r8>, unsigned int@<r9d>, int *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18002b854`

## callees

- `0x1800070e0`
- `0x180007640`
- `0x180029aac`
- `0x18002adfc`
- `0x18002ae74`
- `0x18002cbdc`
- `0x180073718`
- `0x1800968f4`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18002af6f`
- `ntdll!_wcsicmp` at `0x18002b0f8`
- `ntdll!_wcsicmp` at `0x18002af6f`
- `ntdll!_wcsicmp` at `0x18002b0f8`
- `GDI32!SelectObject` at `0x18002b057`
- `GDI32!SelectObject` at `0x18002b088`
- `GDI32!SelectObject` at `0x18002b057`
- `GDI32!SelectObject` at `0x18002b088`
- `GDI32!GetTextFaceAliasW` at `0x18002b0e9`
- `GDI32!GetTextFaceAliasW` at `0x18002b0e9`
- `GDI32!EnumFontsW` at `0x18002b21e`
- `GDI32!EnumFontsW` at `0x18002b21e`
- `GDI32!CreateFontIndirectW` at `0x18002b03f`
- `GDI32!CreateFontIndirectW` at `0x18002b03f`
- `GDI32!GetTextMetricsW` at `0x18002b075`
- `GDI32!GetTextMetricsW` at `0x18002b075`
- `GDI32!GetTextCharset` at `0x18002afca`
- `GDI32!GetTextCharset` at `0x18002afe6`
- `GDI32!GetTextCharset` at `0x18002afca`
- `GDI32!GetTextCharset` at `0x18002afe6`
- `GDI32!DeleteObject` at `0x18002b23b`
- `GDI32!DeleteObject` at `0x18002b23b`

## pseudocode

```c
HFONT __fastcall CreateDlgFont(
        HDC hdc,
        unsigned __int16 **a2,
        struct DLGTEMPLATE2 *a3,
        unsigned __int16 a4,
        int *a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned __int16 *v11; // rax
  int v12; // edx
  char v13; // r13
  unsigned int v14; // edx
  unsigned __int16 *v15; // rcx
  unsigned __int8 *v16; // rax
  const wchar_t *v17; // r8
  unsigned __int8 v18; // si
  unsigned __int8 v19; // di
  _BYTE *v20; // rbx
  int v21; // edx
  BYTE lfCharSet; // al
  char v23; // di
  int v24; // edx
  HFONT v25; // rax
  HFONT v26; // rbx
  HGDIOBJ v27; // rsi
  LONG lfWeight; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned int DpiForSystem; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  unsigned int v35; // eax
  __int64 DpiServerInfoForCurrentThread; // rax
  unsigned __int8 v37; // al
  LONG v38; // eax
  char v39; // [rsp+20h] [rbp-E0h]
  wchar_t *String2; // [rsp+28h] [rbp-D8h]
  LOGFONTW lf; // [rsp+30h] [rbp-D0h] BYREF
  struct tagTEXTMETRICW tm; // [rsp+90h] [rbp-70h] BYREF
  wchar_t String1[32]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(&lf, 0, sizeof(lf));
  v11 = *a2;
  memset(&tm, 0, sizeof(tm));
  v12 = (__int16)*v11;
  *a2 = v11 + 1;
  *a5 = v12;
  if ( v12 == 0x7FFF )
    return GetMessageBoxFontForDpi(a7);
  v13 = 0;
  v14 = (int)((unsigned __int64)(-954437177LL * (int)(a7 * v12 + 36)) >> 32) >> 4;
  lf.lfHeight = (v14 >> 31) + v14;
  if ( *(_WORD *)a3 )
  {
    v15 = *a2;
    lf.lfWeight = **a2;
    *a2 = v15 + 1;
    lf.lfItalic = *((_BYTE *)v15 + 2);
    *a2 = (unsigned __int16 *)((char *)v15 + 3);
    lf.lfCharSet = *((_BYTE *)v15 + 3);
    *a2 = v15 + 2;
  }
  String2 = *a2;
  v16 = SkipSz(*a2);
  *a2 = (unsigned __int16 *)&v16[-(int)v16 & 3];
  if ( _wcsicmp(v17, L"MS Shell Dlg") )
  {
    v18 = 0;
    v39 = 0;
LABEL_6:
    v19 = 0;
    v20 = (char *)a3 + 12;
    goto LABEL_7;
  }
  v20 = (char *)a3 + 12;
  v18 = 1;
  v39 = 1;
  if ( (*((_BYTE *)a3 + 12) & 0x48) != 0x48 || a4 < 0x400u || !*(_WORD *)a3 )
    goto LABEL_6;
  v19 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d493ec40129c3b98c6e07187e792ddd3_Traceguids);
  }
LABEL_7:
  v21 = *(unsigned __int16 *)a3;
  if ( !*(_WORD *)a3 )
  {
    lf.lfWeight = 700;
    if ( v19 )
      goto LABEL_17;
    lf.lfCharSet = GetTextCharset(hdc);
    goto LABEL_16;
  }
  if ( v21 == 1 )
  {
    if ( v19 )
      goto LABEL_17;
    if ( (*(_BYTE *)gpsi & 2) != 0 )
    {
      if ( !lf.lfCharSet )
        lf.lfCharSet = 1;
LABEL_17:
      FixupDlgFaceName(&lf, v18, v19, String2);
      if ( *(_WORD *)a3 < 2u )
      {
        lfWeight = lf.lfWeight;
        if ( (*v20 & 4) != 0 )
          lfWeight = 400;
        lf.lfWeight = lfWeight;
      }
      lfCharSet = lf.lfCharSet;
      v23 = 0;
      while ( 1 )
      {
        v24 = 323;
        if ( lfCharSet == 1 )
        {
          EnumFontsW(hdc, lf.lfFaceName, GetCharsetEnumProc, (LPARAM)&lf);
          lfCharSet = lf.lfCharSet;
          v13 = 0;
          v24 = 323;
        }
        if ( !*(_WORD *)a3 )
        {
          v37 = lfCharSet + 0x80;
          if ( v37 <= 8u )
          {
            if ( _bittest(&v24, v37) )
            {
              v38 = lf.lfWeight;
              if ( lf.lfWeight != 400 )
                v38 = 400;
              lf.lfWeight = v38;
            }
          }
        }
        v25 = CreateFontIndirectW(&lf);
        v26 = v25;
        if ( !v25 )
          break;
        v27 = SelectObject(hdc, v25);
        if ( v27 )
        {
          if ( !v39 )
          {
            if ( !GetTextMetricsW(hdc, &tm)
              || (GetTextFaceAliasW(hdc, 32, String1), _wcsicmp(String1, String2))
              || ((unsigned __int8)(tm.tmCharSet + 0x80) > 8u
               || (v31 = 323, !_bittest((const int *)&v31, (unsigned __int8)(tm.tmCharSet + 0x80))))
              && ((DpiForSystem = GetDpiForSystem(v31, v30), (int)GetDpiDependentMetric(5, DpiForSystem) < 32)
               || (v35 = GetDpiForSystem(v34, v33), (int)GetDpiDependentMetric(6, v35) < 32))
              && (DpiServerInfoForCurrentThread = GetDpiServerInfoForCurrentThread(v34),
                  tm.tmHeight < *(_DWORD *)(DpiServerInfoForCurrentThread + 36)) )
            {
              v23 = 1;
            }
          }
          SelectObject(hdc, v27);
          if ( !v23 )
            return v26;
          v23 = 0;
        }
        DeleteObject(v26);
        v26 = 0;
        if ( !v13 )
          return v26;
        lfCharSet = 1;
        lf.lfCharSet = 1;
      }
      return 0;
    }
    if ( lf.lfCharSet )
    {
      if ( lf.lfCharSet == 1 )
        lf.lfCharSet = GetTextCharset(hdc);
      goto LABEL_17;
    }
LABEL_16:
    v13 = 1;
    goto LABEL_17;
  }
  if ( (unsigned __int16)v21 <= 0xAu )
    goto LABEL_17;
  return 0;
}

```

## disassembly

```asm
0x18002ae74  mov     [rsp-8+arg_10], rbx
0x18002ae79  push    rbp
0x18002ae7a  push    rsi
0x18002ae7b  push    rdi
0x18002ae7c  push    r12
0x18002ae7e  push    r13
0x18002ae80  push    r14
0x18002ae82  push    r15
0x18002ae84  lea     rbp, [rsp-20h]
0x18002ae89  sub     rsp, 120h
0x18002ae90  mov     rax, cs:__security_cookie
0x18002ae97  xor     rax, rsp
0x18002ae9a  mov     [rbp+50h+var_40], rax
0x18002ae9e  mov     rbx, [rbp+50h+arg_20]
0x18002aea5  mov     rdi, rdx
0x18002aea8  mov     esi, [rbp+50h+arg_30]
0x18002aeae  xor     edx, edx; Val
0x18002aeb0  mov     r15, r8
0x18002aeb3  mov     r12, rcx
0x18002aeb6  lea     rcx, [rsp+150h+lf]; void *
0x18002aebb  mov     r14d, r9d
0x18002aebe  lea     r8d, [rdx+5Ch]; Size
0x18002aec2  call    memset_0
0x18002aec7  mov     rax, [rdi]
0x18002aeca  xorps   xmm0, xmm0
0x18002aecd  movups  xmmword ptr [rbp+50h+tm.tmOverhang], xmm0
0x18002aed1  movups  xmmword ptr [rbp+50h+tm.tmHeight], xmm0
0x18002aed5  movups  xmmword ptr [rbp+50h+tm.tmExternalLeading], xmm0
0x18002aed9  movups  xmmword ptr [rbp+50h+tm.tmFirstChar], xmm0
0x18002aedd  movsx   edx, word ptr [rax]
0x18002aee0  add     rax, 2
0x18002aee4  mov     [rdi], rax
0x18002aee7  mov     [rbx], edx
0x18002aee9  cmp     edx, 7FFFh
0x18002aeef  jz      loc_18002B0D4
0x18002aef5  imul    edx, esi
0x18002aef8  xor     ecx, ecx
0x18002aefa  mov     eax, 0C71C71C7h
0x18002aeff  mov     r13b, cl
0x18002af02  add     edx, 24h ; '$'
0x18002af05  imul    edx
0x18002af07  sar     edx, 4
0x18002af0a  mov     eax, edx
0x18002af0c  shr     eax, 1Fh
0x18002af0f  add     edx, eax
0x18002af11  mov     [rsp+150h+lf.lfHeight], edx
0x18002af15  cmp     [r15], cx
0x18002af19  jz      short loc_18002AF46
0x18002af1b  mov     rcx, [rdi]
0x18002af1e  movzx   eax, word ptr [rcx]
0x18002af21  mov     [rsp+150h+lf.lfWeight], eax
0x18002af25  lea     rax, [rcx+2]
0x18002af29  mov     [rdi], rax
0x18002af2c  mov     al, [rax]
0x18002af2e  mov     [rsp+150h+lf.lfItalic], al
0x18002af32  lea     rax, [rcx+3]
0x18002af36  mov     [rdi], rax
0x18002af39  mov     al, [rax]
0x18002af3b  mov     [rsp+150h+lf.lfCharSet], al
0x18002af3f  lea     rax, [rcx+4]
0x18002af43  mov     [rdi], rax
0x18002af46  mov     r8, [rdi]
0x18002af49  mov     rcx, r8; unsigned __int16 *
0x18002af4c  mov     [rsp+150h+String2], r8
0x18002af51  call    ?SkipSz@@YAPEAEPEAG@Z; SkipSz(ushort *)
0x18002af56  mov     rcx, rax
0x18002af59  lea     rdx, aMsShellDlg; "MS Shell Dlg"
0x18002af60  neg     rcx
0x18002af63  and     ecx, 3
0x18002af66  add     rcx, rax
0x18002af69  mov     [rdi], rcx
0x18002af6c  mov     rcx, r8; String1
0x18002af6f  call    cs:__imp__wcsicmp
0x18002af75  xor     r8d, r8d
0x18002af78  mov     r9d, 0Ah
0x18002af7e  test    eax, eax
0x18002af80  jz      loc_18002B18B
0x18002af86  mov     sil, r8b
0x18002af89  mov     [rsp+150h+var_130], r8b
0x18002af8e  mov     dil, r8b
0x18002af91  lea     rbx, [r15+0Ch]
0x18002af95  movzx   edx, word ptr [r15]
0x18002af99  test    edx, edx
0x18002af9b  jz      short loc_18002AFD6
0x18002af9d  cmp     edx, 1
0x18002afa0  jnz     loc_18002B25D
0x18002afa6  test    dil, dil
0x18002afa9  jnz     short loc_18002AFF3
0x18002afab  mov     rax, cs:gpsi
0x18002afb2  test    byte ptr [rax], 2
0x18002afb5  jnz     loc_18002B26E
0x18002afbb  mov     al, [rsp+150h+lf.lfCharSet]
0x18002afbf  test    al, al
0x18002afc1  jz      short loc_18002AFF0
0x18002afc3  cmp     al, dl
0x18002afc5  jnz     short loc_18002AFF3
0x18002afc7  mov     rcx, r12; hdc
0x18002afca  call    cs:__imp_GetTextCharset
0x18002afd0  mov     [rsp+150h+lf.lfCharSet], al
0x18002afd4  jmp     short loc_18002AFF3
0x18002afd6  mov     [rsp+150h+lf.lfWeight], 2BCh
0x18002afde  test    dil, dil
0x18002afe1  jnz     short loc_18002AFF3
0x18002afe3  mov     rcx, r12; hdc
0x18002afe6  call    cs:__imp_GetTextCharset
0x18002afec  mov     [rsp+150h+lf.lfCharSet], al
0x18002aff0  mov     r13b, 1
0x18002aff3  mov     r9, [rsp+150h+String2]; unsigned __int16 *
0x18002aff8  lea     rcx, [rsp+150h+lf]; struct tagLOGFONTW *
0x18002affd  mov     r8b, dil; unsigned __int8
0x18002b000  mov     dl, sil; unsigned __int8
0x18002b003  call    ?FixupDlgFaceName@@YAXPEAUtagLOGFONTW@@EEPEBG@Z; FixupDlgFaceName(tagLOGFONTW *,uchar,uchar,ushort const *)
0x18002b008  cmp     word ptr [r15], 2
0x18002b00d  mov     ecx, 190h
0x18002b012  jb      loc_18002B0C1
0x18002b018  mov     al, [rsp+150h+lf.lfCharSet]
0x18002b01c  xor     edi, edi
0x18002b01e  mov     r14b, [rsp+150h+var_130]
0x18002b023  mov     edx, 143h
0x18002b028  cmp     al, 1
0x18002b02a  jz      loc_18002B20A
0x18002b030  cmp     [r15], di
0x18002b034  jz      loc_18002B163
0x18002b03a  lea     rcx, [rsp+150h+lf]; lplf
0x18002b03f  call    cs:__imp_CreateFontIndirectW
0x18002b045  mov     rbx, rax
0x18002b048  test    rax, rax
0x18002b04b  jz      loc_18002B267
0x18002b051  mov     rdx, rax; h
0x18002b054  mov     rcx, r12; hdc
0x18002b057  call    cs:__imp_SelectObject
0x18002b05d  mov     rsi, rax
0x18002b060  test    rax, rax
0x18002b063  jz      loc_18002B238
0x18002b069  test    r14b, r14b
0x18002b06c  jnz     short loc_18002B082
0x18002b06e  lea     rdx, [rbp+50h+tm]; lptm
0x18002b072  mov     rcx, r12; hdc
0x18002b075  call    cs:__imp_GetTextMetricsW
0x18002b07b  test    eax, eax
0x18002b07d  jnz     short loc_18002B0DD
0x18002b07f  mov     dil, 1
0x18002b082  mov     rdx, rsi; h
0x18002b085  mov     rcx, r12; hdc
0x18002b088  call    cs:__imp_SelectObject
0x18002b08e  test    dil, dil
0x18002b091  jnz     loc_18002B283
0x18002b097  mov     rax, rbx
0x18002b09a  mov     rcx, [rbp+50h+var_40]
0x18002b09e  xor     rcx, rsp; StackCookie
0x18002b0a1  call    __security_check_cookie
0x18002b0a6  mov     rbx, [rsp+150h+arg_10]
0x18002b0ae  add     rsp, 120h
0x18002b0b5  pop     r15
0x18002b0b7  pop     r14
0x18002b0b9  pop     r13
0x18002b0bb  pop     r12
0x18002b0bd  pop     rdi
0x18002b0be  pop     rsi
0x18002b0bf  pop     rbp
0x18002b0c0  retn
0x18002b0c1  mov     eax, [rsp+150h+lf.lfWeight]
0x18002b0c5  test    byte ptr [rbx], 4
0x18002b0c8  cmovnz  eax, ecx
0x18002b0cb  mov     [rsp+150h+lf.lfWeight], eax
0x18002b0cf  jmp     loc_18002B018
0x18002b0d4  mov     ecx, esi; unsigned int
0x18002b0d6  call    ?GetMessageBoxFontForDpi@@YAPEAUHFONT__@@I@Z; GetMessageBoxFontForDpi(uint)
0x18002b0db  jmp     short loc_18002B09A
0x18002b0dd  lea     r8, [rbp+50h+String1]
0x18002b0e1  mov     edx, 20h ; ' '
0x18002b0e6  mov     rcx, r12
0x18002b0e9  call    cs:__imp_GetTextFaceAliasW
0x18002b0ef  mov     rdx, [rsp+150h+String2]; String2
0x18002b0f4  lea     rcx, [rbp+50h+String1]; String1
0x18002b0f8  call    cs:__imp__wcsicmp
0x18002b0fe  test    eax, eax
0x18002b100  jnz     loc_18002B07F
0x18002b106  mov     al, [rbp+50h+tm.tmCharSet]
0x18002b109  sub     al, 80h
0x18002b10b  cmp     al, 8
0x18002b10d  ja      short loc_18002B11D
0x18002b10f  mov     ecx, 143h
0x18002b114  bt      ecx, eax
0x18002b117  jb      loc_18002B082
0x18002b11d  call    GetDpiForSystem
0x18002b122  mov     edx, eax
0x18002b124  mov     ecx, 5
0x18002b129  call    GetDpiDependentMetric
0x18002b12e  cmp     eax, 20h ; ' '
0x18002b131  jl      short loc_18002B14D
0x18002b133  call    GetDpiForSystem
0x18002b138  mov     edx, eax
0x18002b13a  mov     ecx, 6
0x18002b13f  call    GetDpiDependentMetric
0x18002b144  cmp     eax, 20h ; ' '
0x18002b147  jge     loc_18002B082
0x18002b14d  call    GetDpiServerInfoForCurrentThread
0x18002b152  mov     ecx, [rax+24h]
0x18002b155  cmp     [rbp+50h+tm.tmHeight], ecx
0x18002b158  jge     loc_18002B082
0x18002b15e  jmp     loc_18002B07F
0x18002b163  sub     al, 80h
0x18002b165  cmp     al, 8
0x18002b167  ja      loc_18002B03A
0x18002b16d  movzx   eax, al
0x18002b170  bt      edx, eax
0x18002b173  jnb     loc_18002B03A
0x18002b179  mov     eax, [rsp+150h+lf.lfWeight]
0x18002b17d  cmp     eax, ecx
0x18002b17f  cmovnz  eax, ecx
0x18002b182  mov     [rsp+150h+lf.lfWeight], eax
0x18002b186  jmp     loc_18002B03A
0x18002b18b  lea     rbx, [r15+0Ch]
0x18002b18f  mov     sil, 1
0x18002b192  mov     eax, [rbx]
0x18002b194  and     eax, 48h
0x18002b197  mov     [rsp+150h+var_130], sil
0x18002b19c  cmp     al, 48h ; 'H'
0x18002b19e  jnz     loc_18002AF8E
0x18002b1a4  mov     eax, 400h
0x18002b1a9  cmp     r14w, ax
0x18002b1ad  jb      loc_18002AF8E
0x18002b1b3  cmp     [r15], r8w
0x18002b1b7  jz      loc_18002AF8E
0x18002b1bd  mov     dil, sil
0x18002b1c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1c7  lea     rax, WPP_GLOBAL_Control
0x18002b1ce  cmp     rcx, rax
0x18002b1d1  jz      loc_18002AF95
0x18002b1d7  test    byte ptr [rcx+1Ch], 10h
0x18002b1db  jz      loc_18002AF95
0x18002b1e1  cmp     byte ptr [rcx+19h], 4
0x18002b1e5  jb      loc_18002AF95
0x18002b1eb  mov     rcx, [rcx+10h]
0x18002b1ef  lea     r8, WPP_d493ec40129c3b98c6e07187e792ddd3_Traceguids
0x18002b1f6  mov     edx, r9d
0x18002b1f9  call    WPP_SF_
0x18002b1fe  xor     r8d, r8d
0x18002b201  lea     r9d, [r8+0Ah]
0x18002b205  jmp     loc_18002AF95
0x18002b20a  lea     r9, [rsp+150h+lf]; lParam
0x18002b20f  mov     rcx, r12; hdc
0x18002b212  lea     r8, ?GetCharsetEnumProc@@YAHPEAUtagLOGFONTW@@PEAUtagTEXTMETRICW@@K_J@Z; lpProc
0x18002b219  lea     rdx, [rsp+150h+lf.lfFaceName]; lpLogfont
0x18002b21e  call    cs:__imp_EnumFontsW
0x18002b224  mov     al, [rsp+150h+lf.lfCharSet]
0x18002b228  mov     ecx, 190h
0x18002b22d  mov     r13b, dil
0x18002b230  lea     edx, [rcx-4Dh]
0x18002b233  jmp     loc_18002B030
0x18002b238  mov     rcx, rbx; ho
0x18002b23b  call    cs:__imp_DeleteObject
0x18002b241  mov     rbx, rdi
0x18002b244  test    r13b, r13b
0x18002b247  jz      loc_18002B097
0x18002b24d  mov     al, 1
0x18002b24f  mov     ecx, 190h
0x18002b254  mov     [rsp+150h+lf.lfCharSet], al
0x18002b258  jmp     loc_18002B023
0x18002b25d  cmp     dx, r9w
0x18002b261  jbe     loc_18002AFF3
0x18002b267  xor     eax, eax
0x18002b269  jmp     loc_18002B09A
0x18002b26e  cmp     [rsp+150h+lf.lfCharSet], r8b
0x18002b273  jnz     loc_18002AFF3
0x18002b279  mov     [rsp+150h+lf.lfCharSet], 1
0x18002b27e  jmp     loc_18002AFF3
0x18002b283  xor     edi, edi
0x18002b285  jmp     short loc_18002B238
```
