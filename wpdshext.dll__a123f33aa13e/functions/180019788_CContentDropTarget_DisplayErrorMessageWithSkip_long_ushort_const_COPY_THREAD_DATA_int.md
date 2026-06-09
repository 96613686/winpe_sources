# CContentDropTarget::_DisplayErrorMessageWithSkip(long,ushort const *,COPY_THREAD_DATA *,int)

- ea: `0x180019788`
- end: `0x180019d8a`
- name: `?_DisplayErrorMessageWithSkip@CContentDropTarget@@AEAAJJPEBGPEAVCOPY_THREAD_DATA@@H@Z`
- size: `1538`
- prototype: `__int64 __fastcall(CContentDropTarget *__hidden this, int, const unsigned __int16 *, struct COPY_THREAD_DATA *, int)`
- caller_count: `5`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180017c88`
- `0x180019e44`
- `0x18003c074`
- `0x18003cce4`
- `0x18003ee9c`

## callees

- `0x180019788`
- `0x180019d90`
- `0x18002ff5c`
- `0x180035590`
- `0x180053834`
- `0x18006d310`
- `0x180071ff0`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180019802`
- `KERNEL32!LocalFree` at `0x18001980b`
- `KERNEL32!LocalFree` at `0x180019802`
- `KERNEL32!LocalFree` at `0x18001980b`
- `SHLWAPI!PathFindFileNameW` at `0x180019c0f`
- `SHLWAPI!PathFindFileNameW` at `0x180019c62`
- `SHLWAPI!PathFindFileNameW` at `0x180019c0f`
- `SHLWAPI!PathFindFileNameW` at `0x180019c62`
- `USER32!LoadStringW` at `0x180019c04`
- `USER32!LoadStringW` at `0x180019c42`
- `USER32!LoadStringW` at `0x180019c04`
- `USER32!LoadStringW` at `0x180019c42`

## pseudocode

```c
__int64 __fastcall CContentDropTarget::_DisplayErrorMessageWithSkip(
        CContentDropTarget *this,
        int a2,
        const unsigned __int16 *a3,
        struct COPY_THREAD_DATA *a4,
        int a5)
{
  __int64 v5; // r15
  unsigned __int16 *v9; // rdi
  int v11; // ecx
  int v12; // r12d
  int v13; // r14d
  UINT v14; // edi
  UINT v15; // eax
  HWND v16; // r13
  __int64 v17; // rcx
  signed int i; // ecx
  __int64 v19; // rax
  LPWSTR FileNameW; // rax
  LPWSTR v21; // rax
  unsigned __int16 *v22; // rax
  int v23; // eax
  unsigned __int16 *v24; // [rsp+30h] [rbp-D0h]
  int v25; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+3Ch] [rbp-C4h] BYREF
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  UINT uID; // [rsp+44h] [rbp-BCh]
  LPCWSTR pszPath; // [rsp+48h] [rbp-B8h]
  HLOCAL hMem; // [rsp+50h] [rbp-B0h]
  CContentDropTarget *v31; // [rsp+58h] [rbp-A8h]
  _DWORD v32[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v34; // [rsp+70h] [rbp-90h]
  WCHAR Buffer[1024]; // [rsp+80h] [rbp-80h] BYREF

  v5 = *((_QWORD *)a4 + 557);
  pszPath = a3;
  v31 = this;
  v24 = 0;
  hMem = 0;
  if ( v5 && *(_DWORD *)(v5 + 104) )
  {
    a2 = -2147023673;
LABEL_4:
    v9 = v24;
    goto LABEL_5;
  }
  if ( a2 == -2147023673 )
    goto LABEL_111;
  v11 = *((_DWORD *)a4 + 1138);
  v12 = -1;
  if ( v11 == 2 )
    v13 = (a5 != 0) + 222;
  else
    v13 = (a5 != 0) + 249;
  v14 = 226;
  if ( v11 != 2 )
    v14 = 253;
  v15 = 224;
  if ( v11 != 2 )
    v15 = 238;
  uID = v15;
  if ( v5 )
    v16 = *(HWND *)(v5 + 120);
  else
    v16 = 0;
  if ( a2 > -2147024894 )
  {
    if ( a2 <= -1072879832 )
    {
      if ( a2 != -1072879832 )
      {
        switch ( a2 )
        {
          case -2147024891:
            v14 = 229;
            goto LABEL_87;
          case -2147024882:
            v14 = 252;
            goto LABEL_87;
          case -2147024877:
            v14 = 247;
            goto LABEL_87;
          case -2147024816:
            goto LABEL_70;
          case -2147024784:
            v14 = 263;
            goto LABEL_87;
          case -2147024713:
LABEL_70:
            v14 = 256;
            goto LABEL_87;
          case -1072879855:
          case -1072879843:
            v14 = 390;
            goto LABEL_87;
        }
        goto LABEL_81;
      }
LABEL_86:
      v14 = 388;
      goto LABEL_87;
    }
    if ( a2 == -1072879828 )
      goto LABEL_86;
    if ( a2 != -1072879791 )
    {
      if ( a2 == -1072879758 )
      {
        v14 = 391;
        goto LABEL_87;
      }
      if ( a2 == -1072879757 || a2 == -1072879755 || a2 == -1072879751 )
        goto LABEL_86;
      if ( a2 != -1072879745 )
      {
LABEL_81:
        if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 192LL))(
               *((_QWORD *)this + 10),
               *(_QWORD *)(*((_QWORD *)this + 10) + 64LL)) )
        {
          v17 = *((_QWORD *)a4 + 559);
          v25 = 0;
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 88LL))(v17, &v25);
          if ( v25 == 1 )
            v14 = 356 - (*((_DWORD *)a4 + 1138) != 2);
          goto LABEL_87;
        }
        goto LABEL_55;
      }
    }
    v14 = 389;
    goto LABEL_87;
  }
  if ( a2 == -2147024894 )
  {
    if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 192LL))(
            *((_QWORD *)this + 10),
            *(_QWORD *)(*((_QWORD *)this + 10) + 64LL)) )
    {
LABEL_55:
      *((_WORD *)a4 + 420) = 0;
      goto LABEL_56;
    }
    goto LABEL_57;
  }
  if ( a2 > -2147483171 )
  {
    switch ( a2 )
    {
      case -2147213306:
      case -2147213286:
      case -2147213283:
        v14 = 230;
        goto LABEL_87;
      case -2147201023:
LABEL_56:
        v14 = 255;
        goto LABEL_87;
      case -2147201018:
        v14 = 251;
        goto LABEL_87;
      case -2147201009:
        v14 = 265;
        goto LABEL_87;
      case -2147201007:
        v14 = 266;
        goto LABEL_87;
      case -2147178487:
        v14 = 231;
        goto LABEL_87;
    }
    goto LABEL_81;
  }
  switch ( a2 )
  {
    case -2147483171:
LABEL_57:
      v14 = 477;
      goto LABEL_87;
    case -2147483400:
      v14 = 248;
      goto LABEL_87;
    case -2147483387:
      v14 = 261;
      goto LABEL_87;
    case -2147483297:
      v14 = 351;
      goto LABEL_87;
    case -2147483296:
      v14 = 352;
      goto LABEL_87;
    case -2147483178:
      v14 = 470;
      goto LABEL_87;
    case -2147483177:
      v14 = 471;
      goto LABEL_87;
    case -2147483176:
      v14 = 472;
      goto LABEL_87;
  }
  if ( a2 != -2147483175 )
    goto LABEL_81;
  v14 = 473;
LABEL_87:
  for ( i = 0; (unsigned int)i < 0x20; ++i )
  {
    if ( v14 == *((_DWORD *)a4 + 3 * i + 114) )
    {
      v19 = 12LL * i;
      goto LABEL_94;
    }
    if ( !*((_DWORD *)a4 + 3 * i + 114) )
    {
      *((_DWORD *)a4 + 3 * i + 114) = v14;
      v19 = 12LL * i;
      *(_DWORD *)((char *)a4 + v19 + 460) = 0;
LABEL_94:
      if ( *(_DWORD *)((char *)a4 + v19 + 460) )
      {
        a2 = 1;
        goto LABEL_112;
      }
      v12 = i;
      break;
    }
  }
  LoadStringW(g_hInst, uID, Buffer, 1024);
  FileNameW = PathFindFileNameW(pszPath);
  v24 = FormatString(Buffer, FileNameW);
  if ( !v24
    || (LoadStringW(g_hInst, v14, Buffer, 1024),
        StringCchCatW(Buffer, 0x400u, (const unsigned __int16 *)a4 + 420),
        v21 = PathFindFileNameW(pszPath),
        v22 = FormatString(Buffer, v21),
        (hMem = v22) == 0) )
  {
LABEL_111:
    if ( a2 != 1 )
      goto LABEL_4;
LABEL_112:
    v9 = v24;
LABEL_113:
    *(_DWORD *)a4 = 1;
    goto LABEL_5;
  }
  v9 = v24;
  v33 = v24;
  v32[1] = 0;
  v32[0] = v13;
  v34 = v22;
  v26 = 0;
  v27 = 0;
  if ( !v16 )
    v16 = (HWND)*((_QWORD *)v31 + 3);
  v23 = TaskDialog_Skip((struct CProgressUI *)v5, v16, g_hInst, (const struct ERROR_DLG_PARAMS *)v32, &v26, &v27);
  a2 = v23;
  if ( v23 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)v23);
    goto LABEL_5;
  }
  if ( v26 == 1 )
  {
    a2 = 1;
    if ( v27 && v12 != -1 )
      *((_DWORD *)a4 + 3 * v12 + 115) = 1;
    goto LABEL_113;
  }
  a2 = -2147023673;
  if ( v5 )
    CProgressUI::_ForceCancel((CProgressUI *)v5);
LABEL_5:
  LocalFree(hMem);
  LocalFree(v9);
  if ( a2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      138,
      WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
      (unsigned int)a2);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x180019788  push    rbp
0x18001978a  push    rbx
0x18001978b  push    rsi
0x18001978c  push    rdi
0x18001978d  push    r12
0x18001978f  push    r13
0x180019791  push    r14
0x180019793  push    r15
0x180019795  lea     rbp, [rsp-798h]
0x18001979d  sub     rsp, 898h
0x1800197a4  mov     rax, cs:__security_cookie
0x1800197ab  xor     rax, rsp
0x1800197ae  mov     [rbp+7D0h+var_50], rax
0x1800197b5  mov     r15, [r9+1168h]
0x1800197bc  mov     ebx, edx
0x1800197be  mov     [rsp+8D0h+pszPath], r8
0x1800197c3  mov     rsi, r9
0x1800197c6  mov     [rsp+8D0h+var_878], rcx
0x1800197cb  mov     rdx, rcx
0x1800197ce  mov     [rsp+8D0h+var_8A0], 0
0x1800197d7  mov     [rsp+8D0h+hMem], 0
0x1800197e0  test    r15, r15
0x1800197e3  jz      short loc_180019864
0x1800197e5  cmp     dword ptr [r15+68h], 0
0x1800197ea  jz      short loc_180019864
0x1800197ec  mov     ebx, 800704C7h
0x1800197f1  mov     rdi, [rsp+8D0h+var_8A0]
0x1800197f6  lea     rsi, WPP_GLOBAL_Control
0x1800197fd  mov     rcx, [rsp+8D0h+hMem]; hMem
0x180019802  call    cs:__imp_LocalFree
0x180019808  mov     rcx, rdi; hMem
0x18001980b  call    cs:__imp_LocalFree
0x180019811  test    ebx, ebx
0x180019813  jns     short loc_18001983F
0x180019815  mov     rcx, cs:WPP_GLOBAL_Control
0x18001981c  cmp     rcx, rsi
0x18001981f  jz      short loc_18001983F
0x180019821  test    byte ptr [rcx+1Ch], 2
0x180019825  jz      short loc_18001983F
0x180019827  mov     rcx, [rcx+10h]
0x18001982b  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x180019832  mov     edx, 8Ah
0x180019837  mov     r9d, ebx
0x18001983a  call    WPP_SF_d
0x18001983f  mov     eax, ebx
0x180019841  mov     rcx, [rbp+7D0h+var_50]
0x180019848  xor     rcx, rsp; StackCookie
0x18001984b  call    __security_check_cookie
0x180019850  add     rsp, 898h
0x180019857  pop     r15
0x180019859  pop     r14
0x18001985b  pop     r13
0x18001985d  pop     r12
0x18001985f  pop     rdi
0x180019860  pop     rsi
0x180019861  pop     rbx
0x180019862  pop     rbp
0x180019863  retn
0x180019864  cmp     ebx, 800704C7h
0x18001986a  jz      loc_180019D71
0x180019870  mov     ecx, [r9+11C8h]
0x180019877  or      r12d, 0FFFFFFFFh
0x18001987b  mov     eax, [rbp+7D0h+arg_20]
0x180019881  cmp     ecx, 2
0x180019884  jnz     short loc_180019897
0x180019886  neg     eax
0x180019888  sbb     r14d, r14d
0x18001988b  neg     r14d
0x18001988e  add     r14d, 0DEh
0x180019895  jmp     short loc_1800198A6
0x180019897  neg     eax
0x180019899  sbb     r14d, r14d
0x18001989c  neg     r14d
0x18001989f  add     r14d, 0F9h
0x1800198a6  cmp     ecx, 2
0x1800198a9  mov     edi, 0E2h
0x1800198ae  lea     eax, [rdi+1Bh]
0x1800198b1  cmovnz  edi, eax
0x1800198b4  mov     eax, 0E0h
0x1800198b9  lea     r8d, [rax+0Eh]
0x1800198bd  cmovnz  eax, r8d
0x1800198c1  mov     [rsp+8D0h+uID], eax
0x1800198c5  test    r15, r15
0x1800198c8  jz      short loc_1800198D0
0x1800198ca  mov     r13, [r15+78h]
0x1800198ce  jmp     short loc_1800198D3
0x1800198d0  xor     r13d, r13d
0x1800198d3  mov     eax, 80070002h
0x1800198d8  cmp     ebx, eax
0x1800198da  jg      loc_180019A3F
0x1800198e0  jz      loc_180019A07
0x1800198e6  mov     eax, 800001DDh
0x1800198eb  cmp     ebx, eax
0x1800198ed  jg      loc_180019991
0x1800198f3  jz      loc_180019A35
0x1800198f9  cmp     ebx, 800000F8h
0x1800198ff  jz      loc_180019987
0x180019905  cmp     ebx, 80000105h
0x18001990b  jz      short loc_18001997D
0x18001990d  cmp     ebx, 8000015Fh
0x180019913  jz      short loc_180019973
0x180019915  cmp     ebx, 80000160h
0x18001991b  jz      short loc_180019969
0x18001991d  cmp     ebx, 800001D6h
0x180019923  jz      short loc_18001995F
0x180019925  cmp     ebx, 800001D7h
0x18001992b  jz      short loc_180019955
0x18001992d  cmp     ebx, 800001D8h
0x180019933  jz      short loc_18001994B
0x180019935  cmp     ebx, 800001D9h
0x18001993b  jnz     loc_180019B1A
0x180019941  mov     edi, 1D9h
0x180019946  jmp     loc_180019B8A
0x18001994b  mov     edi, 1D8h
0x180019950  jmp     loc_180019B8A
0x180019955  mov     edi, 1D7h
0x18001995a  jmp     loc_180019B8A
0x18001995f  mov     edi, 1D6h
0x180019964  jmp     loc_180019B8A
0x180019969  mov     edi, 160h
0x18001996e  jmp     loc_180019B8A
0x180019973  mov     edi, 15Fh
0x180019978  jmp     loc_180019B8A
0x18001997d  mov     edi, 105h
0x180019982  jmp     loc_180019B8A
0x180019987  mov     edi, 0F8h
0x18001998c  jmp     loc_180019B8A
0x180019991  cmp     ebx, 80042006h
0x180019997  jz      short loc_1800199FD
0x180019999  cmp     ebx, 8004201Ah
0x18001999f  jz      short loc_1800199FD
0x1800199a1  cmp     ebx, 8004201Dh
0x1800199a7  jz      short loc_1800199FD
0x1800199a9  cmp     ebx, 80045001h
0x1800199af  jz      short loc_180019A2B
0x1800199b1  cmp     ebx, 80045006h
0x1800199b7  jz      short loc_1800199F3
0x1800199b9  cmp     ebx, 8004500Fh
0x1800199bf  jz      short loc_1800199E9
0x1800199c1  cmp     ebx, 80045011h
0x1800199c7  jz      short loc_1800199DF
0x1800199c9  cmp     ebx, 8004A809h
0x1800199cf  jnz     loc_180019B1A
0x1800199d5  mov     edi, 0E7h
0x1800199da  jmp     loc_180019B8A
0x1800199df  mov     edi, 10Ah
0x1800199e4  jmp     loc_180019B8A
0x1800199e9  mov     edi, 109h
0x1800199ee  jmp     loc_180019B8A
0x1800199f3  mov     edi, 0FBh
0x1800199f8  jmp     loc_180019B8A
0x1800199fd  mov     edi, 0E6h
0x180019a02  jmp     loc_180019B8A
0x180019a07  mov     rcx, [rdx+50h]
0x180019a0b  mov     rax, [rcx]
0x180019a0e  mov     rdx, [rcx+40h]
0x180019a12  mov     rax, [rax+0C0h]
0x180019a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a1e  test    eax, eax
0x180019a20  jnz     short loc_180019A35
0x180019a22  xor     eax, eax
0x180019a24  mov     [rsi+348h], ax
0x180019a2b  mov     edi, 0FFh
0x180019a30  jmp     loc_180019B8A
0x180019a35  mov     edi, 1DDh
0x180019a3a  jmp     loc_180019B8A
0x180019a3f  mov     eax, 0C00D2728h
0x180019a44  cmp     ebx, eax
0x180019a46  jg      loc_180019AD2
0x180019a4c  jz      loc_180019B85
0x180019a52  cmp     ebx, 80070005h
0x180019a58  jz      short loc_180019AC8
0x180019a5a  cmp     ebx, 8007000Eh
0x180019a60  jz      short loc_180019ABE
0x180019a62  cmp     ebx, 80070013h
0x180019a68  jz      short loc_180019AB4
0x180019a6a  cmp     ebx, 80070050h
0x180019a70  jz      short loc_180019AAA
0x180019a72  cmp     ebx, 80070070h
0x180019a78  jz      short loc_180019AA0
0x180019a7a  cmp     ebx, 800700B7h
0x180019a80  jz      short loc_180019AAA
0x180019a82  cmp     ebx, 0C00D2711h
0x180019a88  jz      short loc_180019A96
0x180019a8a  cmp     ebx, 0C00D271Dh
0x180019a90  jnz     loc_180019B1A
0x180019a96  mov     edi, 186h
0x180019a9b  jmp     loc_180019B8A
0x180019aa0  mov     edi, 107h
0x180019aa5  jmp     loc_180019B8A
0x180019aaa  mov     edi, 100h
0x180019aaf  jmp     loc_180019B8A
0x180019ab4  mov     edi, 0F7h
0x180019ab9  jmp     loc_180019B8A
0x180019abe  mov     edi, 0FCh
0x180019ac3  jmp     loc_180019B8A
0x180019ac8  mov     edi, 0E5h
0x180019acd  jmp     loc_180019B8A
0x180019ad2  cmp     ebx, 0C00D272Ch
0x180019ad8  jz      loc_180019B85
0x180019ade  cmp     ebx, 0C00D2751h
0x180019ae4  jz      loc_180019B7E
0x180019aea  cmp     ebx, 0C00D2772h
0x180019af0  jz      loc_180019B77
0x180019af6  cmp     ebx, 0C00D2773h
0x180019afc  jz      loc_180019B85
0x180019b02  cmp     ebx, 0C00D2775h
0x180019b08  jz      short loc_180019B85
0x180019b0a  cmp     ebx, 0C00D2779h
0x180019b10  jz      short loc_180019B85
0x180019b12  cmp     ebx, 0C00D277Fh
0x180019b18  jz      short loc_180019B7E
0x180019b1a  mov     rcx, [rdx+50h]
0x180019b1e  mov     rax, [rcx]
0x180019b21  mov     rdx, [rcx+40h]
0x180019b25  mov     rax, [rax+0C0h]
0x180019b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b31  test    eax, eax
0x180019b33  jz      loc_180019A22
0x180019b39  mov     rcx, [rsi+1178h]
0x180019b40  lea     rdx, [rsp+8D0h+var_898]
0x180019b45  mov     [rsp+8D0h+var_898], 0
0x180019b4d  mov     rax, [rcx]
0x180019b50  mov     rax, [rax+58h]
0x180019b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b59  cmp     [rsp+8D0h+var_898], 1
0x180019b5e  jnz     short loc_180019B8A
0x180019b60  mov     eax, 2
0x180019b65  sub     eax, [rsi+11C8h]
0x180019b6b  neg     eax
0x180019b6d  sbb     edi, edi
0x180019b6f  add     edi, 164h
0x180019b75  jmp     short loc_180019B8A
0x180019b77  mov     edi, 187h
0x180019b7c  jmp     short loc_180019B8A
0x180019b7e  mov     edi, 185h
0x180019b83  jmp     short loc_180019B8A
0x180019b85  mov     edi, 184h
0x180019b8a  xor     ecx, ecx
0x180019b8c  cmp     ecx, 20h ; ' '
0x180019b8f  jnb     short loc_180019BEF
0x180019b91  movsxd  rax, ecx
0x180019b94  lea     rdx, [rax+rax*2]
0x180019b98  cmp     edi, [rsi+rdx*4+1C8h]
0x180019b9f  jz      short loc_180019BCB
0x180019ba1  cmp     dword ptr [rsi+rdx*4+1C8h], 0
0x180019ba9  jz      short loc_180019BAF
0x180019bab  inc     ecx
0x180019bad  jmp     short loc_180019B8C
0x180019baf  lea     rax, [rax+rax*2]
0x180019bb3  mov     [rsi+rdx*4+1C8h], edi
0x180019bba  shl     rax, 2
0x180019bbe  mov     dword ptr [rax+rsi+1CCh], 0
0x180019bc9  jmp     short loc_180019BD3
0x180019bcb  lea     rax, [rax+rax*2]
0x180019bcf  shl     rax, 2
0x180019bd3  cmp     ecx, 0FFFFFFFFh
0x180019bd6  jz      short loc_180019BEC
0x180019bd8  cmp     dword ptr [rsi+rax+1CCh], 0
0x180019be0  jz      short loc_180019BEC
0x180019be2  mov     ebx, 1
0x180019be7  jmp     loc_180019D7A
0x180019bec  mov     r12d, ecx
0x180019bef  mov     edx, [rsp+8D0h+uID]; uID
0x180019bf3  lea     r8, [rbp+7D0h+Buffer]; lpBuffer
0x180019bf7  mov     rcx, cs:g_hInst; hInstance
0x180019bfe  mov     r9d, 400h; cchBufferMax
0x180019c04  call    cs:__imp_LoadStringW
0x180019c0a  mov     rcx, [rsp+8D0h+pszPath]; pszPath
0x180019c0f  call    cs:__imp_PathFindFileNameW
0x180019c15  mov     rdx, rax
0x180019c18  lea     rcx, [rbp+7D0h+Buffer]; lpSource
0x180019c1c  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x180019c21  mov     [rsp+8D0h+var_8A0], rax
0x180019c26  test    rax, rax
0x180019c29  jz      loc_180019D71
0x180019c2f  mov     rcx, cs:g_hInst; hInstance
0x180019c36  lea     r8, [rbp+7D0h+Buffer]; lpBuffer
0x180019c3a  mov     r9d, 400h; cchBufferMax
0x180019c40  mov     edx, edi; uID
0x180019c42  call    cs:__imp_LoadStringW
0x180019c48  lea     r8, [rsi+348h]; unsigned __int16 *
0x180019c4f  mov     edx, 400h; unsigned __int64
0x180019c54  lea     rcx, [rbp+7D0h+Buffer]; unsigned __int16 *
0x180019c58  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019c5d  mov     rcx, [rsp+8D0h+pszPath]; pszPath
0x180019c62  call    cs:__imp_PathFindFileNameW
0x180019c68  mov     rdx, rax
0x180019c6b  lea     rcx, [rbp+7D0h+Buffer]; lpSource
0x180019c6f  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x180019c74  mov     [rsp+8D0h+hMem], rax
0x180019c79  test    rax, rax
0x180019c7c  jz      loc_180019D71
0x180019c82  mov     rdi, [rsp+8D0h+var_8A0]
0x180019c87  mov     [rsp+8D0h+var_868], rdi
0x180019c8c  mov     [rsp+8D0h+var_86C], 0
0x180019c94  mov     [rsp+8D0h+var_870], r14d
0x180019c99  mov     [rsp+8D0h+var_860], rax
0x180019c9e  mov     [rsp+8D0h+var_894], 0
0x180019ca6  mov     [rsp+8D0h+var_890], 0
  ... truncated ...
```
