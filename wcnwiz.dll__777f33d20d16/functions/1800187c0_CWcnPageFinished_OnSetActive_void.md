# CWcnPageFinished::OnSetActive(void)

- ea: `0x1800187c0`
- end: `0x180018a8a`
- name: `?OnSetActive@CWcnPageFinished@@QEAA_NXZ`
- size: `714`
- prototype: `bool __fastcall(CWcnPageFinished *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800099b4`

## callees

- `0x180001820`
- `0x180002294`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x1800184dc`
- `0x1800187c0`
- `0x180018a90`
- `0x1800196c0`
- `0x180019724`
- `0x18001b9a4`
- `0x18001f6b8`
- `0x18002de1c`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18001895a`
- `USER32!SystemParametersInfoW` at `0x18001895a`
- `USER32!SetDlgItemTextW` at `0x1800189f1`
- `USER32!SetDlgItemTextW` at `0x1800189f1`
- `USER32!PostMessageW` at `0x180018858`
- `USER32!PostMessageW` at `0x180018858`
- `USER32!SendMessageW` at `0x18001889d`
- `USER32!SendMessageW` at `0x1800188c2`
- `USER32!SendMessageW` at `0x18001889d`
- `USER32!SendMessageW` at `0x1800188c2`
- `USER32!GetDlgItem` at `0x1800188af`
- `USER32!GetDlgItem` at `0x1800188af`
- `GDI32!CreateSolidBrush` at `0x180018970`
- `GDI32!CreateSolidBrush` at `0x180018970`
- `GDI32!GetObjectW` at `0x1800188d9`
- `GDI32!GetObjectW` at `0x1800188d9`

## pseudocode

```c
char __fastcall CWcnPageFinished::OnSetActive(CWcnPageFinished *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  __int64 v4; // r8
  HWND DlgItem; // rax
  void *v6; // rax
  int Font; // eax
  int v8; // eax
  int v9; // edi
  __int64 v10; // r8
  unsigned int v11; // eax
  __int64 v12; // r10
  _DWORD pvParam[4]; // [rsp+30h] [rbp-188h] BYREF
  _DWORD pv[6]; // [rsp+40h] [rbp-178h] BYREF
  unsigned __int8 v16; // [rsp+5Bh] [rbp-15Dh]
  WCHAR lParam[128]; // [rsp+A0h] [rbp-118h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 14, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, Indent);
  }
  memset_0(pv, 0, 0x5Cu);
  CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::SetButtonActive(this, 6, 0);
  PostMessageW(*((HWND *)this + 20), 0x48Bu, 0, 1);
  LOBYTE(v4) = 1;
  CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::SetButtonActive(this, 16, v4);
  if ( (int)WcnUxLoadString(0xFA2u, 0x80u, lParam) >= 0 )
    SendMessageW(*((HWND *)this + 20), 0x48Cu, 0x10u, (LPARAM)lParam);
  DlgItem = GetDlgItem(*((HWND *)this + 21), 1617);
  v6 = (void *)SendMessageW(DlgItem, 0x31u, 0, 0);
  *((_QWORD *)this + 25) = v6;
  GetObjectW(v6, 92, pv);
  Font = WcnSysCreateFont(pv[0] - 3, pv[1], 0, v16, 700, (HFONT *)this + 27);
  if ( Font < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids,
      (unsigned int)Font);
  if ( !*((_QWORD *)this + 28) )
  {
    pvParam[0] = 0;
    if ( !SystemParametersInfoW(0x1040u, 0, pvParam, 0) || !pvParam[0] )
      *((_QWORD *)this + 28) = CreateSolidBrush(0xA1FAFFu);
  }
  v8 = CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::FormatPageTitleWithSsid(
         this,
         *((_QWORD *)this + 24) + 752LL);
  v9 = v8;
  if ( v8 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, (unsigned int)v8);
  v10 = *((_QWORD *)this + 24);
  if ( *(_BYTE *)(v10 + 792) && *(_QWORD *)(v10 + 800) )
  {
    SetDlgItemTextW(*((HWND *)this + 21), 1618, *(LPCWSTR *)(v10 + 232));
    CWcnPageFinished::ResizeThePassphraseBox(this);
  }
  else
  {
    CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::SetDlgItemVisible(this, 1618);
    CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::SetDlgItemVisible(this, 1617);
    CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::SetDlgItemVisible(this, 1621);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v9 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v11 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v12 + 16), 17, (unsigned int)WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, v11, v9);
  }
  return 1;
}

```

## disassembly

```asm
0x1800187c0  mov     [rsp+arg_8], rbx
0x1800187c5  mov     [rsp+arg_10], rbp
0x1800187ca  push    rdi
0x1800187cb  sub     rsp, 1B0h
0x1800187d2  mov     rax, cs:__security_cookie
0x1800187d9  xor     rax, rsp
0x1800187dc  mov     [rsp+1B8h+var_18], rax
0x1800187e4  mov     rbx, rcx
0x1800187e7  mov     r10, cs:WPP_GLOBAL_Control
0x1800187ee  lea     rbp, WPP_GLOBAL_Control
0x1800187f5  cmp     r10, rbp
0x1800187f8  jz      short loc_180018823
0x1800187fa  cmp     byte ptr [r10+19h], 6
0x1800187ff  jb      short loc_180018823
0x180018801  mov     ecx, 1; int
0x180018806  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001880b  mov     rcx, [r10+10h]
0x18001880f  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x180018816  mov     edx, 0Eh
0x18001881b  mov     r9, rax
0x18001881e  call    WPP_SF_s
0x180018823  mov     edi, 5Ch ; '\'
0x180018828  lea     rcx, [rsp+1B8h+pv]; void *
0x18001882d  mov     r8d, edi; Size
0x180018830  xor     edx, edx; Val
0x180018832  call    memset_0
0x180018837  xor     r8d, r8d
0x18001883a  lea     edx, [rdi-56h]
0x18001883d  mov     rcx, rbx
0x180018840  call    ?SetButtonActive@?$CWcnPageTemplate@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0CAA@$0NAL@$0A@@@QEAAXK_N@Z; CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::SetButtonActive(ulong,bool)
0x180018845  mov     rcx, [rbx+0A0h]; hWnd
0x18001884c  lea     r9d, [rdi-5Bh]; lParam
0x180018850  xor     r8d, r8d; wParam
0x180018853  mov     edx, 48Bh; Msg
0x180018858  call    cs:__imp_PostMessageW
0x18001885e  mov     r8b, 1
0x180018861  lea     edx, [rdi-4Ch]
0x180018864  mov     rcx, rbx
0x180018867  call    ?SetButtonActive@?$CWcnPageTemplate@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0CAA@$0NAL@$0A@@@QEAAXK_N@Z; CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::SetButtonActive(ulong,bool)
0x18001886c  lea     r8, [rsp+1B8h+lParam]; lpBuffer
0x180018874  mov     ecx, 0FA2h; uID
0x180018879  lea     edx, [rdi+24h]; cchBufferMax
0x18001887c  call    ?WcnUxLoadString@@YAJIKPEAG@Z; WcnUxLoadString(uint,ulong,ushort *)
0x180018881  test    eax, eax
0x180018883  js      short loc_1800188A3
0x180018885  mov     rcx, [rbx+0A0h]; hWnd
0x18001888c  lea     r9, [rsp+1B8h+lParam]; lParam
0x180018894  mov     edx, 48Ch; Msg
0x180018899  lea     r8d, [rdi-4Ch]; wParam
0x18001889d  call    cs:__imp_SendMessageW
0x1800188a3  mov     rcx, [rbx+0A8h]; hDlg
0x1800188aa  mov     edx, 651h; nIDDlgItem
0x1800188af  call    cs:__imp_GetDlgItem
0x1800188b5  xor     r9d, r9d; lParam
0x1800188b8  xor     r8d, r8d; wParam
0x1800188bb  mov     rcx, rax; hWnd
0x1800188be  lea     edx, [r9+31h]; Msg
0x1800188c2  call    cs:__imp_SendMessageW
0x1800188c8  lea     r8, [rsp+1B8h+pv]; pv
0x1800188cd  mov     edx, edi; c
0x1800188cf  mov     rcx, rax; h
0x1800188d2  mov     [rbx+0C8h], rax
0x1800188d9  call    cs:__imp_GetObjectW
0x1800188df  mov     ecx, [rsp+1B8h+pv]
0x1800188e3  lea     rax, [rbx+0D8h]
0x1800188ea  mov     r9b, [rsp+1B8h+var_15D]; unsigned __int8
0x1800188ef  add     ecx, 0FFFFFFFDh; cHeight
0x1800188f2  mov     edx, [rsp+1B8h+cWidth]; cWidth
0x1800188f6  xor     r8d, r8d; unsigned __int8
0x1800188f9  mov     [rsp+1B8h+var_190], rax; HFONT *
0x1800188fe  mov     [rsp+1B8h+var_198], 2BCh; int
0x180018906  call    ?WcnSysCreateFont@@YAJJJEEJPEAPEAUHFONT__@@@Z; WcnSysCreateFont(long,long,uchar,uchar,long,HFONT__ * *)
0x18001890b  test    eax, eax
0x18001890d  jns     short loc_180018939
0x18001890f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018916  cmp     rcx, rbp
0x180018919  jz      short loc_180018939
0x18001891b  cmp     byte ptr [rcx+19h], 3
0x18001891f  jb      short loc_180018939
0x180018921  mov     rcx, [rcx+10h]
0x180018925  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x18001892c  mov     edx, 0Fh
0x180018931  mov     r9d, eax
0x180018934  call    WPP_SF_d
0x180018939  cmp     qword ptr [rbx+0E0h], 0
0x180018941  jnz     short loc_18001897D
0x180018943  xor     r9d, r9d; fWinIni
0x180018946  mov     [rsp+1B8h+pvParam], 0
0x18001894e  lea     r8, [rsp+1B8h+pvParam]; pvParam
0x180018953  xor     edx, edx; uiParam
0x180018955  mov     ecx, 1040h; uiAction
0x18001895a  call    cs:__imp_SystemParametersInfoW
0x180018960  test    eax, eax
0x180018962  jz      short loc_18001896B
0x180018964  cmp     [rsp+1B8h+pvParam], 0
0x180018969  jnz     short loc_18001897D
0x18001896b  mov     ecx, 0A1FAFFh; color
0x180018970  call    cs:__imp_CreateSolidBrush
0x180018976  mov     [rbx+0E0h], rax
0x18001897d  mov     rdx, [rbx+0C0h]
0x180018984  mov     rcx, rbx
0x180018987  add     rdx, 2F0h
0x18001898e  call    ?FormatPageTitleWithSsid@?$CWcnPageTemplate@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0CAA@$0NAL@$0A@@@QEAAJPEAU_DOT11_SSID@@II@Z; CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::FormatPageTitleWithSsid(_DOT11_SSID *,uint,uint)
0x180018993  mov     edi, eax
0x180018995  test    eax, eax
0x180018997  jns     short loc_1800189C3
0x180018999  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189a0  cmp     rcx, rbp
0x1800189a3  jz      short loc_1800189C3
0x1800189a5  cmp     byte ptr [rcx+19h], 3
0x1800189a9  jb      short loc_1800189C3
0x1800189ab  mov     rcx, [rcx+10h]
0x1800189af  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x1800189b6  mov     edx, 10h
0x1800189bb  mov     r9d, eax
0x1800189be  call    WPP_SF_d
0x1800189c3  mov     r8, [rbx+0C0h]
0x1800189ca  cmp     byte ptr [r8+318h], 0
0x1800189d2  jz      short loc_180018A01
0x1800189d4  cmp     qword ptr [r8+320h], 0
0x1800189dc  jz      short loc_180018A01
0x1800189de  mov     r8, [r8+0E8h]; lpString
0x1800189e5  mov     edx, 652h; nIDDlgItem
0x1800189ea  mov     rcx, [rbx+0A8h]; hDlg
0x1800189f1  call    cs:__imp_SetDlgItemTextW
0x1800189f7  mov     rcx, rbx; this
0x1800189fa  call    ?ResizeThePassphraseBox@CWcnPageFinished@@AEAAXXZ; CWcnPageFinished::ResizeThePassphraseBox(void)
0x1800189ff  jmp     short loc_180018A28
0x180018a01  mov     edx, 652h
0x180018a06  mov     rcx, rbx
0x180018a09  call    ?SetDlgItemVisible@?$CWcnPageTemplate@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0CAA@$0NAL@$0A@@@QEAAXH_N@Z; CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::SetDlgItemVisible(int,bool)
0x180018a0e  mov     edx, 651h
0x180018a13  mov     rcx, rbx
0x180018a16  call    ?SetDlgItemVisible@?$CWcnPageTemplate@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0CAA@$0NAL@$0A@@@QEAAXH_N@Z; CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::SetDlgItemVisible(int,bool)
0x180018a1b  mov     edx, 655h
0x180018a20  mov     rcx, rbx
0x180018a23  call    ?SetDlgItemVisible@?$CWcnPageTemplate@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0CAA@$0NAL@$0A@@@QEAAXH_N@Z; CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::SetDlgItemVisible(int,bool)
0x180018a28  mov     r10, cs:WPP_GLOBAL_Control
0x180018a2f  cmp     r10, rbp
0x180018a32  jz      short loc_180018A63
0x180018a34  test    edi, edi
0x180018a36  js      short loc_180018A3F
0x180018a38  cmp     byte ptr [r10+19h], 6
0x180018a3d  jb      short loc_180018A63
0x180018a3f  or      ecx, 0FFFFFFFFh; int
0x180018a42  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018a47  mov     rcx, [r10+10h]
0x180018a4b  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x180018a52  mov     edx, 11h
0x180018a57  mov     [rsp+1B8h+var_198], edi
0x180018a5b  mov     r9, rax
0x180018a5e  call    WPP_SF_sd
0x180018a63  mov     al, 1
0x180018a65  mov     rcx, [rsp+1B8h+var_18]
0x180018a6d  xor     rcx, rsp; StackCookie
0x180018a70  call    __security_check_cookie
0x180018a75  lea     r11, [rsp+1B8h+var_8]
0x180018a7d  mov     rbx, [r11+18h]
0x180018a81  mov     rbp, [r11+20h]
0x180018a85  mov     rsp, r11
0x180018a88  pop     rdi
0x180018a89  retn
```
