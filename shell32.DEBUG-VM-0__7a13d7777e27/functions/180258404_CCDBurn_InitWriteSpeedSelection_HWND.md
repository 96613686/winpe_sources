# CCDBurn::_InitWriteSpeedSelection(HWND__ *)

- ea: `0x180258404`
- end: `0x18025874a`
- name: `?_InitWriteSpeedSelection@CCDBurn@@AEAAXPEAUHWND__@@@Z`
- size: `838`
- prototype: `void __fastcall(CCDBurn *__hidden this, HWND hDlg)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180259378`

## callees

- `0x1800e7fb0`
- `0x180117f7c`
- `0x180233280`
- `0x18025656c`
- `0x180256914`
- `0x180257c40`
- `0x180258404`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025871d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025871d`
- `USER32!EnableWindow` at `0x18025868e`
- `USER32!EnableWindow` at `0x18025868e`
- `USER32!SendMessageW` at `0x18025845b`
- `USER32!SendMessageW` at `0x1802585f8`
- `USER32!SendMessageW` at `0x180258612`
- `USER32!SendMessageW` at `0x180258646`
- `USER32!SendMessageW` at `0x18025845b`
- `USER32!SendMessageW` at `0x1802585f8`
- `USER32!SendMessageW` at `0x180258612`
- `USER32!SendMessageW` at `0x180258646`
- `USER32!GetDlgItem` at `0x180258440`
- `USER32!GetDlgItem` at `0x180258440`
- `USER32!SetDlgItemTextW` at `0x180258470`
- `USER32!SetDlgItemTextW` at `0x180258713`
- `USER32!SetDlgItemTextW` at `0x180258470`
- `USER32!SetDlgItemTextW` at `0x180258713`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18025867f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18025867f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1802584ab`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1802584ab`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180258675`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180258675`
- `PROPSYS!PSPropertyBag_ReadLONG` at `0x18025854b`
- `PROPSYS!PSPropertyBag_ReadLONG` at `0x180258567`
- `PROPSYS!PSPropertyBag_ReadLONG` at `0x18025854b`
- `PROPSYS!PSPropertyBag_ReadLONG` at `0x180258567`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802586a2`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802586b6`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802586a2`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802586b6`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18025851e`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18025851e`
- `PROPSYS!PSPropertyBag_WriteLONG` at `0x1802586cf`
- `PROPSYS!PSPropertyBag_WriteLONG` at `0x1802586cf`

## string_xrefs

- `0x18025853c`: `WriteSpeed`
- `0x1802586af`: `WriteSpeed`

## pseudocode

```c
void __fastcall CCDBurn::_InitWriteSpeedSelection(CCDBurn *this, WCHAR *hDlg)
{
  WCHAR *v2; // r15
  HWND v4; // r14
  int v5; // r13d
  int v6; // edi
  HRESULT XFactorString; // ebx
  IPropertyBag *v8; // rcx
  IPropertyBag *v9; // rcx
  LONG v10; // r14d
  LONG v11; // r12d
  __int64 v12; // r15
  int v13; // eax
  int v14; // [rsp+20h] [rbp-79h]
  LPCWSTR lpString; // [rsp+30h] [rbp-69h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-61h]
  int v17; // [rsp+40h] [rbp-59h] BYREF
  int v18; // [rsp+44h] [rbp-55h] BYREF
  ULONG cElements; // [rsp+48h] [rbp-51h]
  int v20; // [rsp+4Ch] [rbp-4Dh]
  SAFEARRAY *psa; // [rsp+50h] [rbp-49h] BYREF
  void *ppvData; // [rsp+58h] [rbp-41h] BYREF
  LONG v23; // [rsp+60h] [rbp-39h] BYREF
  LONG v24; // [rsp+64h] [rbp-35h] BYREF
  int v25; // [rsp+68h] [rbp-31h] BYREF
  DWORD value; // [rsp+6Ch] [rbp-2Dh] BYREF
  unsigned __int16 lParam[32]; // [rsp+70h] [rbp-29h] BYREF

  v2 = hDlg;
  lpString = hDlg;
  hWnd = GetDlgItem((HWND)hDlg, 14687);
  v4 = hWnd;
  SendMessageW(hWnd, 0x14Bu, 0, 0);
  SetDlgItemTextW((HWND)v2, 14680, (LPCWSTR)&pszStart);
  v5 = 0;
  v17 = 0;
  v18 = 0;
  psa = 0;
  v6 = 75;
  XFactorString = CCDBurn::_GetCurrentWriteSpeeds(this, &psa);
  if ( XFactorString >= 0 )
  {
    ppvData = 0;
    XFactorString = SafeArrayAccessData(psa, &ppvData);
    if ( XFactorString >= 0 )
    {
      cElements = psa->rgsabound[0].cElements;
      if ( cElements )
      {
        v25 = 0;
        CCDBurn::_GetCachedMediaInfo((const unsigned __int16 *)this + 66, L"Media Type", &v25, 4u);
        if ( (v25 & 6) == 0 )
          v6 = (v25 & 0x700000) != 0 ? 2195 : 680;
        v8 = (IPropertyBag *)*((_QWORD *)this + 86);
        value = 0;
        if ( PSPropertyBag_ReadDWORD(v8, L"HR", &value) >= 0 && value == -1062599936 )
        {
          v9 = (IPropertyBag *)*((_QWORD *)this + 86);
          v24 = 0;
          v23 = 0;
          if ( PSPropertyBag_ReadLONG(v9, L"WriteSpeed", &v24) >= 0
            && PSPropertyBag_ReadLONG(*((IPropertyBag **)this + 86), L"XConversion", &v23) >= 0 )
          {
            CCDBurn::_GetBurnXFactor(v24, v23, &v17, &v18);
            v5 = 1;
          }
        }
        v10 = 0;
        v11 = 0;
        v23 = 0;
        v12 = 0;
        v24 = 0;
        while ( (unsigned int)v12 < cElements )
        {
          v20 = *((_DWORD *)ppvData + 6 * v12 + 2);
          CCDBurn::_GetBurnXFactor(v20, v6, &v23, &v24);
          v11 = v24;
          v10 = v23;
          XFactorString = CCDBurn::_GetXFactorString(v23, v24, lParam, 0x20u);
          if ( XFactorString >= 0 )
          {
            v13 = SendMessageW(hWnd, 0x143u, 0, (LPARAM)lParam);
            if ( v13 < 0 )
            {
              XFactorString = -2147024882;
              goto LABEL_25;
            }
            if ( (unsigned int)SendMessageW(hWnd, 0x151u, v13, v20) == -1 )
              XFactorString = -2147467259;
          }
          v12 = (unsigned int)(v12 + 1);
          if ( XFactorString < 0 )
            goto LABEL_25;
        }
        SendMessageW(hWnd, 0x14Eu, 0, 0);
        if ( v5 && (v17 < v10 || v17 == v10 && v18 <= v11) )
          v5 = 0;
LABEL_25:
        v4 = hWnd;
        v2 = (WCHAR *)lpString;
      }
      else
      {
        XFactorString = -2147418113;
      }
      SafeArrayUnaccessData(psa);
    }
    SafeArrayDestroy(psa);
  }
  if ( XFactorString >= 0 )
  {
    PSPropertyBag_WriteLONG(*((IPropertyBag **)this + 86), L"XConversion", v6);
    if ( v5 )
    {
      lpString = 0;
      if ( (int)TResourceStringAllocCopyEx<unsigned short *>(g_hinst, v14, &lpString) >= 0 )
      {
        SetDlgItemTextW((HWND)v2, 14680, lpString);
        LocalFree((HLOCAL)lpString);
      }
    }
  }
  else
  {
    EnableWindow(v4, 0);
    PSPropertyBag_Delete(*((IPropertyBag **)this + 86), L"XConversion");
    PSPropertyBag_Delete(*((IPropertyBag **)this + 86), L"WriteSpeed");
  }
}

```

## disassembly

```asm
0x180258404  mov     [rsp-8+arg_10], rbx
0x180258409  push    rbp
0x18025840a  push    rsi
0x18025840b  push    rdi
0x18025840c  push    r12
0x18025840e  push    r13
0x180258410  push    r14
0x180258412  push    r15
0x180258414  lea     rbp, [rsp-27h]
0x180258419  sub     rsp, 0C0h
0x180258420  mov     rax, cs:__security_cookie
0x180258427  xor     rax, rsp
0x18025842a  mov     [rbp+57h+var_40], rax
0x18025842e  mov     r15, rdx
0x180258431  mov     [rbp+57h+lpString], rdx
0x180258435  mov     rsi, rcx
0x180258438  mov     edx, 395Fh; nIDDlgItem
0x18025843d  mov     rcx, r15; hDlg
0x180258440  call    cs:__imp_GetDlgItem
0x180258446  xor     r9d, r9d; lParam
0x180258449  xor     r8d, r8d; wParam
0x18025844c  mov     rcx, rax; hWnd
0x18025844f  mov     [rbp+57h+hWnd], rax
0x180258453  mov     edx, 14Bh; Msg
0x180258458  mov     r14, rax
0x18025845b  call    cs:__imp_SendMessageW
0x180258461  lea     r8, pszStart; lpString
0x180258468  mov     edx, 3958h; nIDDlgItem
0x18025846d  mov     rcx, r15; hDlg
0x180258470  call    cs:__imp_SetDlgItemTextW
0x180258476  xor     r13d, r13d
0x180258479  lea     rdx, [rbp+57h+psa]; struct tagSAFEARRAY **
0x18025847d  mov     rcx, rsi; this
0x180258480  mov     [rbp+57h+var_B0], r13d
0x180258484  mov     [rbp+57h+var_AC], r13d
0x180258488  mov     [rbp+57h+psa], r13
0x18025848c  lea     edi, [r13+4Bh]
0x180258490  call    ?_GetCurrentWriteSpeeds@CCDBurn@@AEAAJPEAPEAUtagSAFEARRAY@@@Z; CCDBurn::_GetCurrentWriteSpeeds(tagSAFEARRAY * *)
0x180258495  mov     ebx, eax
0x180258497  test    eax, eax
0x180258499  js      loc_180258685
0x18025849f  mov     rcx, [rbp+57h+psa]; psa
0x1802584a3  lea     rdx, [rbp+57h+ppvData]; ppvData
0x1802584a7  mov     [rbp+57h+ppvData], r13
0x1802584ab  call    cs:__imp_SafeArrayAccessData
0x1802584b1  mov     ebx, eax
0x1802584b3  test    eax, eax
0x1802584b5  js      loc_18025867B
0x1802584bb  mov     rax, [rbp+57h+psa]
0x1802584bf  mov     eax, [rax+18h]
0x1802584c2  mov     [rbp+57h+var_A8], eax
0x1802584c5  test    eax, eax
0x1802584c7  jz      loc_18025866C
0x1802584cd  lea     rcx, [rsi+84h]; unsigned __int16 *
0x1802584d4  mov     [rbp+57h+var_88], r13d
0x1802584d8  lea     r9d, [r13+4]; unsigned int
0x1802584dc  lea     r8, [rbp+57h+var_88]; void *
0x1802584e0  lea     rdx, aMediaType; "Media Type"
0x1802584e7  call    ?_GetCachedMediaInfo@CCDBurn@@CAJPEBG0PEAXK@Z; CCDBurn::_GetCachedMediaInfo(ushort const *,ushort const *,void *,ulong)
0x1802584ec  mov     eax, [rbp+57h+var_88]
0x1802584ef  test    al, 6
0x1802584f1  jnz     short loc_180258508
0x1802584f3  and     eax, 700000h
0x1802584f8  neg     eax
0x1802584fa  sbb     edi, edi
0x1802584fc  and     edi, 5EBh
0x180258502  add     edi, 2A8h
0x180258508  mov     rcx, [rsi+2B0h]; propBag
0x18025850f  lea     r8, [rbp+57h+value]; value
0x180258513  lea     rdx, aHr; "HR"
0x18025851a  mov     [rbp+57h+value], r13d
0x18025851e  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180258524  test    eax, eax
0x180258526  js      short loc_18025858A
0x180258528  cmp     [rbp+57h+value], 0C0AA0300h
0x18025852f  jnz     short loc_18025858A
0x180258531  mov     rcx, [rsi+2B0h]; propBag
0x180258538  lea     r8, [rbp+57h+var_8C]; value
0x18025853c  lea     rdx, aWritespeed; "WriteSpeed"
0x180258543  mov     [rbp+57h+var_8C], r13d
0x180258547  mov     [rbp+57h+var_90], r13d
0x18025854b  call    cs:__imp_PSPropertyBag_ReadLONG
0x180258551  test    eax, eax
0x180258553  js      short loc_18025858A
0x180258555  mov     rcx, [rsi+2B0h]; propBag
0x18025855c  lea     r8, [rbp+57h+var_90]; value
0x180258560  lea     rdx, aXconversion; "XConversion"
0x180258567  call    cs:__imp_PSPropertyBag_ReadLONG
0x18025856d  test    eax, eax
0x18025856f  js      short loc_18025858A
0x180258571  mov     edx, [rbp+57h+var_90]; int
0x180258574  lea     r9, [rbp+57h+var_AC]; int *
0x180258578  mov     ecx, [rbp+57h+var_8C]; int
0x18025857b  lea     r8, [rbp+57h+var_B0]; int *
0x18025857f  call    ?_GetBurnXFactor@CCDBurn@@CAXJJPEAJ0@Z; CCDBurn::_GetBurnXFactor(long,long,long *,long *)
0x180258584  mov     r13d, 1
0x18025858a  xor     r14d, r14d
0x18025858d  xor     r12d, r12d
0x180258590  mov     [rbp+57h+var_90], r14d
0x180258594  xor     r15d, r15d
0x180258597  mov     [rbp+57h+var_8C], r12d
0x18025859b  cmp     r15d, [rbp+57h+var_A8]
0x18025859f  jnb     loc_180258637
0x1802585a5  mov     rax, [rbp+57h+ppvData]
0x1802585a9  lea     rcx, [r15+r15*2]
0x1802585ad  lea     r9, [rbp+57h+var_8C]; int *
0x1802585b1  mov     edx, edi; int
0x1802585b3  lea     r8, [rbp+57h+var_90]; int *
0x1802585b7  mov     eax, [rax+rcx*8+8]
0x1802585bb  mov     ecx, eax; int
0x1802585bd  mov     [rbp+57h+var_A4], eax
0x1802585c0  call    ?_GetBurnXFactor@CCDBurn@@CAXJJPEAJ0@Z; CCDBurn::_GetBurnXFactor(long,long,long *,long *)
0x1802585c5  mov     r12d, [rbp+57h+var_8C]
0x1802585c9  lea     r8, [rbp+57h+lParam]; unsigned __int16 *
0x1802585cd  mov     r14d, [rbp+57h+var_90]
0x1802585d1  mov     edx, r12d; int
0x1802585d4  mov     ecx, r14d; int
0x1802585d7  mov     r9d, 20h ; ' '; unsigned int
0x1802585dd  call    ?_GetXFactorString@CCDBurn@@CAJJJPEAGI@Z; CCDBurn::_GetXFactorString(long,long,ushort *,uint)
0x1802585e2  mov     ebx, eax
0x1802585e4  test    eax, eax
0x1802585e6  js      short loc_180258623
0x1802585e8  mov     rcx, [rbp+57h+hWnd]; hWnd
0x1802585ec  lea     r9, [rbp+57h+lParam]; lParam
0x1802585f0  xor     r8d, r8d; wParam
0x1802585f3  mov     edx, 143h; Msg
0x1802585f8  call    cs:__imp_SendMessageW
0x1802585fe  test    eax, eax
0x180258600  js      short loc_180258630
0x180258602  movsxd  r9, [rbp+57h+var_A4]; lParam
0x180258606  mov     edx, 151h; Msg
0x18025860b  mov     rcx, [rbp+57h+hWnd]; hWnd
0x18025860f  movsxd  r8, eax; wParam
0x180258612  call    cs:__imp_SendMessageW
0x180258618  cmp     eax, 0FFFFFFFFh
0x18025861b  mov     ecx, 80004005h
0x180258620  cmovz   ebx, ecx
0x180258623  inc     r15d
0x180258626  test    ebx, ebx
0x180258628  jns     loc_18025859B
0x18025862e  jmp     short loc_180258662
0x180258630  mov     ebx, 8007000Eh
0x180258635  jmp     short loc_180258662
0x180258637  mov     rcx, [rbp+57h+hWnd]; hWnd
0x18025863b  xor     r9d, r9d; lParam
0x18025863e  xor     r8d, r8d; wParam
0x180258641  mov     edx, 14Eh; Msg
0x180258646  call    cs:__imp_SendMessageW
0x18025864c  test    r13d, r13d
0x18025864f  jz      short loc_180258662
0x180258651  cmp     [rbp+57h+var_B0], r14d
0x180258655  jl      short loc_18025865F
0x180258657  jnz     short loc_180258662
0x180258659  cmp     [rbp+57h+var_AC], r12d
0x18025865d  jg      short loc_180258662
0x18025865f  xor     r13d, r13d
0x180258662  mov     r14, [rbp+57h+hWnd]
0x180258666  mov     r15, [rbp+57h+lpString]
0x18025866a  jmp     short loc_180258671
0x18025866c  mov     ebx, 8000FFFFh
0x180258671  mov     rcx, [rbp+57h+psa]; psa
0x180258675  call    cs:__imp_SafeArrayUnaccessData
0x18025867b  mov     rcx, [rbp+57h+psa]; psa
0x18025867f  call    cs:__imp_SafeArrayDestroy
0x180258685  test    ebx, ebx
0x180258687  jns     short loc_1802586BE
0x180258689  xor     edx, edx; bEnable
0x18025868b  mov     rcx, r14; hWnd
0x18025868e  call    cs:__imp_EnableWindow
0x180258694  mov     rcx, [rsi+2B0h]; propBag
0x18025869b  lea     rdx, aXconversion; "XConversion"
0x1802586a2  call    cs:__imp_PSPropertyBag_Delete
0x1802586a8  mov     rcx, [rsi+2B0h]; propBag
0x1802586af  lea     rdx, aWritespeed; "WriteSpeed"
0x1802586b6  call    cs:__imp_PSPropertyBag_Delete
0x1802586bc  jmp     short loc_180258723
0x1802586be  mov     rcx, [rsi+2B0h]; propBag
0x1802586c5  lea     rdx, aXconversion; "XConversion"
0x1802586cc  mov     r8d, edi; value
0x1802586cf  call    cs:__imp_PSPropertyBag_WriteLONG
0x1802586d5  test    r13d, r13d
0x1802586d8  jz      short loc_180258723
0x1802586da  mov     rcx, cs:g_hinst; hModule
0x1802586e1  lea     rax, [rbp+57h+lpString]
0x1802586e5  lea     r9, _ResourceStringAllocCopyExLocalAlloc
0x1802586ec  mov     [rsp+0F0h+var_C8], rax; void *
0x1802586f1  mov     edx, 3135h
0x1802586f6  mov     [rbp+57h+lpString], 0
0x1802586fe  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180258703  test    eax, eax
0x180258705  js      short loc_180258723
0x180258707  mov     r8, [rbp+57h+lpString]; lpString
0x18025870b  mov     edx, 3958h; nIDDlgItem
0x180258710  mov     rcx, r15; hDlg
0x180258713  call    cs:__imp_SetDlgItemTextW
0x180258719  mov     rcx, [rbp+57h+lpString]; hMem
0x18025871d  call    cs:__imp_LocalFree
0x180258723  mov     rcx, [rbp+57h+var_40]
0x180258727  xor     rcx, rsp; StackCookie
0x18025872a  call    __security_check_cookie
0x18025872f  mov     rbx, [rsp+0F0h+arg_10]
0x180258737  add     rsp, 0C0h
0x18025873e  pop     r15
0x180258740  pop     r14
0x180258742  pop     r13
0x180258744  pop     r12
0x180258746  pop     rdi
0x180258747  pop     rsi
0x180258748  pop     rbp
0x180258749  retn
```
