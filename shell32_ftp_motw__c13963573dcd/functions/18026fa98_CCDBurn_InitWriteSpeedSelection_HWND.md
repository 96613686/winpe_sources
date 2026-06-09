# CCDBurn::_InitWriteSpeedSelection(HWND__ *)

- ea: `0x18026fa98`
- end: `0x18026fe4b`
- name: `?_InitWriteSpeedSelection@CCDBurn@@AEAAXPEAUHWND__@@@Z`
- size: `947`
- prototype: `void __fastcall(CCDBurn *__hidden this, HWND hDlg)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180270b28`

## callees

- `0x1800e8e90`
- `0x1801197ac`
- `0x180249490`
- `0x18026d93c`
- `0x18026dd08`
- `0x18026f140`
- `0x18026fa98`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18026fe17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18026fe17`
- `USER32!EnableWindow` at `0x18026fd6a`
- `USER32!EnableWindow` at `0x18026fd6a`
- `USER32!GetDlgItem` at `0x18026fad4`
- `USER32!GetDlgItem` at `0x18026fad4`
- `USER32!SetDlgItemTextW` at `0x18026fb10`
- `USER32!SetDlgItemTextW` at `0x18026fe07`
- `USER32!SetDlgItemTextW` at `0x18026fb10`
- `USER32!SetDlgItemTextW` at `0x18026fe07`
- `USER32!SendMessageW` at `0x18026faf5`
- `USER32!SendMessageW` at `0x18026fcb6`
- `USER32!SendMessageW` at `0x18026fcd6`
- `USER32!SendMessageW` at `0x18026fd10`
- `USER32!SendMessageW` at `0x18026faf5`
- `USER32!SendMessageW` at `0x18026fcb6`
- `USER32!SendMessageW` at `0x18026fcd6`
- `USER32!SendMessageW` at `0x18026fd10`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18026fd55`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18026fd55`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18026fb51`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18026fb51`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18026fd45`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18026fd45`
- `PROPSYS!PSPropertyBag_ReadLONG` at `0x18026fbfd`
- `PROPSYS!PSPropertyBag_ReadLONG` at `0x18026fc1f`
- `PROPSYS!PSPropertyBag_ReadLONG` at `0x18026fbfd`
- `PROPSYS!PSPropertyBag_ReadLONG` at `0x18026fc1f`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18026fbca`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18026fbca`
- `PROPSYS!PSPropertyBag_Delete` at `0x18026fd84`
- `PROPSYS!PSPropertyBag_Delete` at `0x18026fd9e`
- `PROPSYS!PSPropertyBag_Delete` at `0x18026fd84`
- `PROPSYS!PSPropertyBag_Delete` at `0x18026fd9e`
- `PROPSYS!PSPropertyBag_WriteLONG` at `0x18026fdbd`
- `PROPSYS!PSPropertyBag_WriteLONG` at `0x18026fdbd`

## string_xrefs

- `0x18026fbee`: `WriteSpeed`
- `0x18026fd97`: `WriteSpeed`

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
  SetDlgItemTextW((HWND)v2, 14680, &pszStart);
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
0x18026fa98  mov     [rsp-8+arg_10], rbx
0x18026fa9d  push    rbp
0x18026fa9e  push    rsi
0x18026fa9f  push    rdi
0x18026faa0  push    r12
0x18026faa2  push    r13
0x18026faa4  push    r14
0x18026faa6  push    r15
0x18026faa8  lea     rbp, [rsp-27h]
0x18026faad  sub     rsp, 0C0h
0x18026fab4  mov     rax, cs:__security_cookie
0x18026fabb  xor     rax, rsp
0x18026fabe  mov     [rbp+57h+var_40], rax
0x18026fac2  mov     r15, rdx
0x18026fac5  mov     [rbp+57h+lpString], rdx
0x18026fac9  mov     rsi, rcx
0x18026facc  mov     edx, 395Fh; nIDDlgItem
0x18026fad1  mov     rcx, r15; hDlg
0x18026fad4  call    cs:__imp_GetDlgItem
0x18026fadb  nop     dword ptr [rax+rax+00h]
0x18026fae0  xor     r9d, r9d; lParam
0x18026fae3  xor     r8d, r8d; wParam
0x18026fae6  mov     rcx, rax; hWnd
0x18026fae9  mov     [rbp+57h+hWnd], rax
0x18026faed  mov     edx, 14Bh; Msg
0x18026faf2  mov     r14, rax
0x18026faf5  call    cs:__imp_SendMessageW
0x18026fafc  nop     dword ptr [rax+rax+00h]
0x18026fb01  lea     r8, pszStart; lpString
0x18026fb08  mov     edx, 3958h; nIDDlgItem
0x18026fb0d  mov     rcx, r15; hDlg
0x18026fb10  call    cs:__imp_SetDlgItemTextW
0x18026fb17  nop     dword ptr [rax+rax+00h]
0x18026fb1c  xor     r13d, r13d
0x18026fb1f  lea     rdx, [rbp+57h+psa]; struct tagSAFEARRAY **
0x18026fb23  mov     rcx, rsi; this
0x18026fb26  mov     [rbp+57h+var_B0], r13d
0x18026fb2a  mov     [rbp+57h+var_AC], r13d
0x18026fb2e  mov     [rbp+57h+psa], r13
0x18026fb32  lea     edi, [r13+4Bh]
0x18026fb36  call    ?_GetCurrentWriteSpeeds@CCDBurn@@AEAAJPEAPEAUtagSAFEARRAY@@@Z; CCDBurn::_GetCurrentWriteSpeeds(tagSAFEARRAY * *)
0x18026fb3b  mov     ebx, eax
0x18026fb3d  test    eax, eax
0x18026fb3f  js      loc_18026FD61
0x18026fb45  mov     rcx, [rbp+57h+psa]; psa
0x18026fb49  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18026fb4d  mov     [rbp+57h+ppvData], r13
0x18026fb51  call    cs:__imp_SafeArrayAccessData
0x18026fb58  nop     dword ptr [rax+rax+00h]
0x18026fb5d  mov     ebx, eax
0x18026fb5f  test    eax, eax
0x18026fb61  js      loc_18026FD51
0x18026fb67  mov     rax, [rbp+57h+psa]
0x18026fb6b  mov     eax, [rax+18h]
0x18026fb6e  mov     [rbp+57h+var_A8], eax
0x18026fb71  test    eax, eax
0x18026fb73  jz      loc_18026FD3C
0x18026fb79  lea     rcx, [rsi+84h]; unsigned __int16 *
0x18026fb80  mov     [rbp+57h+var_88], r13d
0x18026fb84  lea     r9d, [r13+4]; unsigned int
0x18026fb88  lea     r8, [rbp+57h+var_88]; void *
0x18026fb8c  lea     rdx, aMediaType; "Media Type"
0x18026fb93  call    ?_GetCachedMediaInfo@CCDBurn@@CAJPEBG0PEAXK@Z; CCDBurn::_GetCachedMediaInfo(ushort const *,ushort const *,void *,ulong)
0x18026fb98  mov     eax, [rbp+57h+var_88]
0x18026fb9b  test    al, 6
0x18026fb9d  jnz     short loc_18026FBB4
0x18026fb9f  and     eax, 700000h
0x18026fba4  neg     eax
0x18026fba6  sbb     edi, edi
0x18026fba8  and     edi, 5EBh
0x18026fbae  add     edi, 2A8h
0x18026fbb4  mov     rcx, [rsi+2B0h]; propBag
0x18026fbbb  lea     r8, [rbp+57h+value]; value
0x18026fbbf  lea     rdx, aHr; "HR"
0x18026fbc6  mov     [rbp+57h+value], r13d
0x18026fbca  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18026fbd1  nop     dword ptr [rax+rax+00h]
0x18026fbd6  test    eax, eax
0x18026fbd8  js      short loc_18026FC48
0x18026fbda  cmp     [rbp+57h+value], 0C0AA0300h
0x18026fbe1  jnz     short loc_18026FC48
0x18026fbe3  mov     rcx, [rsi+2B0h]; propBag
0x18026fbea  lea     r8, [rbp+57h+var_8C]; value
0x18026fbee  lea     rdx, aWritespeed; "WriteSpeed"
0x18026fbf5  mov     [rbp+57h+var_8C], r13d
0x18026fbf9  mov     [rbp+57h+var_90], r13d
0x18026fbfd  call    cs:__imp_PSPropertyBag_ReadLONG
0x18026fc04  nop     dword ptr [rax+rax+00h]
0x18026fc09  test    eax, eax
0x18026fc0b  js      short loc_18026FC48
0x18026fc0d  mov     rcx, [rsi+2B0h]; propBag
0x18026fc14  lea     r8, [rbp+57h+var_90]; value
0x18026fc18  lea     rdx, aXconversion; "XConversion"
0x18026fc1f  call    cs:__imp_PSPropertyBag_ReadLONG
0x18026fc26  nop     dword ptr [rax+rax+00h]
0x18026fc2b  test    eax, eax
0x18026fc2d  js      short loc_18026FC48
0x18026fc2f  mov     edx, [rbp+57h+var_90]; int
0x18026fc32  lea     r9, [rbp+57h+var_AC]; int *
0x18026fc36  mov     ecx, [rbp+57h+var_8C]; int
0x18026fc39  lea     r8, [rbp+57h+var_B0]; int *
0x18026fc3d  call    ?_GetBurnXFactor@CCDBurn@@CAXJJPEAJ0@Z; CCDBurn::_GetBurnXFactor(long,long,long *,long *)
0x18026fc42  mov     r13d, 1
0x18026fc48  xor     r14d, r14d
0x18026fc4b  xor     r12d, r12d
0x18026fc4e  mov     [rbp+57h+var_90], r14d
0x18026fc52  xor     r15d, r15d
0x18026fc55  mov     [rbp+57h+var_8C], r12d
0x18026fc59  cmp     r15d, [rbp+57h+var_A8]
0x18026fc5d  jnb     loc_18026FD01
0x18026fc63  mov     rax, [rbp+57h+ppvData]
0x18026fc67  lea     rcx, [r15+r15*2]
0x18026fc6b  lea     r9, [rbp+57h+var_8C]; int *
0x18026fc6f  mov     edx, edi; int
0x18026fc71  lea     r8, [rbp+57h+var_90]; int *
0x18026fc75  mov     eax, [rax+rcx*8+8]
0x18026fc79  mov     ecx, eax; int
0x18026fc7b  mov     [rbp+57h+var_A4], eax
0x18026fc7e  call    ?_GetBurnXFactor@CCDBurn@@CAXJJPEAJ0@Z; CCDBurn::_GetBurnXFactor(long,long,long *,long *)
0x18026fc83  mov     r12d, [rbp+57h+var_8C]
0x18026fc87  lea     r8, [rbp+57h+lParam]; unsigned __int16 *
0x18026fc8b  mov     r14d, [rbp+57h+var_90]
0x18026fc8f  mov     edx, r12d; int
0x18026fc92  mov     ecx, r14d; int
0x18026fc95  mov     r9d, 20h ; ' '; unsigned int
0x18026fc9b  call    ?_GetXFactorString@CCDBurn@@CAJJJPEAGI@Z; CCDBurn::_GetXFactorString(long,long,ushort *,uint)
0x18026fca0  mov     ebx, eax
0x18026fca2  test    eax, eax
0x18026fca4  js      short loc_18026FCED
0x18026fca6  mov     rcx, [rbp+57h+hWnd]; hWnd
0x18026fcaa  lea     r9, [rbp+57h+lParam]; lParam
0x18026fcae  xor     r8d, r8d; wParam
0x18026fcb1  mov     edx, 143h; Msg
0x18026fcb6  call    cs:__imp_SendMessageW
0x18026fcbd  nop     dword ptr [rax+rax+00h]
0x18026fcc2  test    eax, eax
0x18026fcc4  js      short loc_18026FCFA
0x18026fcc6  movsxd  r9, [rbp+57h+var_A4]; lParam
0x18026fcca  mov     edx, 151h; Msg
0x18026fccf  mov     rcx, [rbp+57h+hWnd]; hWnd
0x18026fcd3  movsxd  r8, eax; wParam
0x18026fcd6  call    cs:__imp_SendMessageW
0x18026fcdd  nop     dword ptr [rax+rax+00h]
0x18026fce2  cmp     eax, 0FFFFFFFFh
0x18026fce5  mov     ecx, 80004005h
0x18026fcea  cmovz   ebx, ecx
0x18026fced  inc     r15d
0x18026fcf0  test    ebx, ebx
0x18026fcf2  jns     loc_18026FC59
0x18026fcf8  jmp     short loc_18026FD32
0x18026fcfa  mov     ebx, 8007000Eh
0x18026fcff  jmp     short loc_18026FD32
0x18026fd01  mov     rcx, [rbp+57h+hWnd]; hWnd
0x18026fd05  xor     r9d, r9d; lParam
0x18026fd08  xor     r8d, r8d; wParam
0x18026fd0b  mov     edx, 14Eh; Msg
0x18026fd10  call    cs:__imp_SendMessageW
0x18026fd17  nop     dword ptr [rax+rax+00h]
0x18026fd1c  test    r13d, r13d
0x18026fd1f  jz      short loc_18026FD32
0x18026fd21  cmp     [rbp+57h+var_B0], r14d
0x18026fd25  jl      short loc_18026FD2F
0x18026fd27  jnz     short loc_18026FD32
0x18026fd29  cmp     [rbp+57h+var_AC], r12d
0x18026fd2d  jg      short loc_18026FD32
0x18026fd2f  xor     r13d, r13d
0x18026fd32  mov     r14, [rbp+57h+hWnd]
0x18026fd36  mov     r15, [rbp+57h+lpString]
0x18026fd3a  jmp     short loc_18026FD41
0x18026fd3c  mov     ebx, 8000FFFFh
0x18026fd41  mov     rcx, [rbp+57h+psa]; psa
0x18026fd45  call    cs:__imp_SafeArrayUnaccessData
0x18026fd4c  nop     dword ptr [rax+rax+00h]
0x18026fd51  mov     rcx, [rbp+57h+psa]; psa
0x18026fd55  call    cs:__imp_SafeArrayDestroy
0x18026fd5c  nop     dword ptr [rax+rax+00h]
0x18026fd61  test    ebx, ebx
0x18026fd63  jns     short loc_18026FDAC
0x18026fd65  xor     edx, edx; bEnable
0x18026fd67  mov     rcx, r14; hWnd
0x18026fd6a  call    cs:__imp_EnableWindow
0x18026fd71  nop     dword ptr [rax+rax+00h]
0x18026fd76  mov     rcx, [rsi+2B0h]; propBag
0x18026fd7d  lea     rdx, aXconversion; "XConversion"
0x18026fd84  call    cs:__imp_PSPropertyBag_Delete
0x18026fd8b  nop     dword ptr [rax+rax+00h]
0x18026fd90  mov     rcx, [rsi+2B0h]; propBag
0x18026fd97  lea     rdx, aWritespeed; "WriteSpeed"
0x18026fd9e  call    cs:__imp_PSPropertyBag_Delete
0x18026fda5  nop     dword ptr [rax+rax+00h]
0x18026fdaa  jmp     short loc_18026FE23
0x18026fdac  mov     rcx, [rsi+2B0h]; propBag
0x18026fdb3  lea     rdx, aXconversion; "XConversion"
0x18026fdba  mov     r8d, edi; value
0x18026fdbd  call    cs:__imp_PSPropertyBag_WriteLONG
0x18026fdc4  nop     dword ptr [rax+rax+00h]
0x18026fdc9  test    r13d, r13d
0x18026fdcc  jz      short loc_18026FE23
0x18026fdce  mov     rcx, cs:g_hinst; hModule
0x18026fdd5  lea     rax, [rbp+57h+lpString]
0x18026fdd9  lea     r9, _ResourceStringAllocCopyExLocalAlloc
0x18026fde0  mov     [rsp+0F0h+var_C8], rax; void *
0x18026fde5  mov     edx, 3135h
0x18026fdea  mov     [rbp+57h+lpString], 0
0x18026fdf2  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18026fdf7  test    eax, eax
0x18026fdf9  js      short loc_18026FE23
0x18026fdfb  mov     r8, [rbp+57h+lpString]; lpString
0x18026fdff  mov     edx, 3958h; nIDDlgItem
0x18026fe04  mov     rcx, r15; hDlg
0x18026fe07  call    cs:__imp_SetDlgItemTextW
0x18026fe0e  nop     dword ptr [rax+rax+00h]
0x18026fe13  mov     rcx, [rbp+57h+lpString]; hMem
0x18026fe17  call    cs:__imp_LocalFree
0x18026fe1e  nop     dword ptr [rax+rax+00h]
0x18026fe23  mov     rcx, [rbp+57h+var_40]
0x18026fe27  xor     rcx, rsp; StackCookie
0x18026fe2a  call    __security_check_cookie
0x18026fe2f  mov     rbx, [rsp+0F0h+arg_10]
0x18026fe37  add     rsp, 0C0h
0x18026fe3e  pop     r15
0x18026fe40  pop     r14
0x18026fe42  pop     r13
0x18026fe44  pop     r12
0x18026fe46  pop     rdi
0x18026fe47  pop     rsi
0x18026fe48  pop     rbp
0x18026fe49  retn
```
