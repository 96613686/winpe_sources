# InternalProcessXMLFile

- ea: `0x180008fd0`
- end: `0x1800093ed`
- name: `InternalProcessXMLFile`
- size: `1053`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009730`
- `0x180009d20`
- `0x18000b0c0`

## callees

- `0x180004370`
- `0x180008fd0`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000e87c`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000909a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000909a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180009059`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180009059`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000939d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000939d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800092aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800092aa`
- `OLEAUT32!__imp_SysFreeString` at `0x180009317`
- `OLEAUT32!__imp_SysFreeString` at `0x180009321`
- `OLEAUT32!__imp_SysFreeString` at `0x180009317`
- `OLEAUT32!__imp_SysFreeString` at `0x180009321`

## pseudocode

```c
__int64 __fastcall InternalProcessXMLFile(__int64 a1, va_list a2, unsigned int a3, WCHAR *a4, void *a5)
{
  LPVOID v6; // rcx
  BOOL v10; // edi
  HRESULT v11; // ebx
  HRESULT v12; // eax
  PVOID *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  unsigned int LastErrorHRESULT; // eax
  __int64 v19; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-79h] BYREF
  unsigned int v21; // [rsp+4Ch] [rbp-75h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-71h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-69h] BYREF
  BSTR v24; // [rsp+60h] [rbp-61h] BYREF
  va_list Arguments[2]; // [rsp+68h] [rbp-59h] BYREF
  __int128 v26; // [rsp+78h] [rbp-49h]
  BSTR v27; // [rsp+88h] [rbp-39h]
  unsigned __int16 v28[16]; // [rsp+90h] [rbp-31h] BYREF
  unsigned __int16 v29[16]; // [rsp+B0h] [rbp-11h] BYREF

  ppv = 0;
  v6 = a5;
  v19 = 0;
  if ( a4 )
    *(_QWORD *)a4 = 0;
  if ( a5 )
  {
    v10 = 0;
LABEL_5:
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, va_list, _QWORD, __int64 *))(*(_QWORD *)v6 + 184LL))(
            v6,
            a1,
            a2,
            a3,
            &v19);
LABEL_19:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  v12 = CoInitializeEx(0, 6u);
  v10 = v12 != -2147417850;
  v11 = 0;
  if ( v12 != -2147417850 )
    v11 = v12;
  if ( v11 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
        (unsigned int)v11);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_25;
  }
  v11 = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, &ppv);
  if ( v11 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v14 = 12;
      goto LABEL_18;
    }
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 216LL))(ppv, 1, a1);
    if ( v11 >= 0 )
    {
      v6 = ppv;
      goto LABEL_5;
    }
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v14 = 11;
LABEL_18:
      WPP_SF_d(v13[2], v14, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v11);
      goto LABEL_19;
    }
  }
LABEL_20:
  if ( v11 >= 0 )
    goto LABEL_43;
LABEL_25:
  v15 = v19;
  if ( !v19 )
    goto LABEL_46;
  if ( a4 )
  {
    v20 = 0;
    v27 = 0;
    *(_OWORD *)Arguments = 0;
    v21 = 0;
    v26 = 0;
    v24 = 0;
    bstrString = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 88LL))(v19, &v20);
    if ( v16 < 0
      || (v16 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 96LL))(v19, &v21), v16 < 0)
      || (v16 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v19 + 72LL))(v19, &bstrString), v16 < 0)
      || (v16 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v19 + 80LL))(v19, &v24), v16 < 0) )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_43;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
        (unsigned int)v16);
    }
    else
    {
      swprintf_sfn(v28, 0xDu, L"%ld", v20);
      swprintf_sfn(v29, 0xDu, L"%ld", v21);
      Arguments[1] = (va_list)v28;
      Arguments[0] = a2;
      *(_QWORD *)&v26 = v29;
      *((_QWORD *)&v26 + 1) = bstrString;
      v27 = v24;
      if ( FormatMessageW(0x2900u, lpSource, 0xC0000004, 0, a4, 0, Arguments) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
            *(_QWORD *)a4,
            v11);
      }
      else
      {
        LastErrorHRESULT = GetLastErrorHRESULT();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
            LastErrorHRESULT);
      }
      SysFreeString(bstrString);
      SysFreeString(v24);
    }
    v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_43:
    v15 = v19;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_46:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    CoUninitialize();
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x10) != 0 )
    WPP_SF_d(v13[2], 17, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180008fd0  push    rbp
0x180008fd2  push    rbx
0x180008fd3  push    rsi
0x180008fd4  push    rdi
0x180008fd5  push    r12
0x180008fd7  push    r14
0x180008fd9  push    r15
0x180008fdb  lea     rbp, [rsp-1Fh]
0x180008fe0  sub     rsp, 0E0h
0x180008fe7  mov     rax, cs:__security_cookie
0x180008fee  xor     rax, rsp
0x180008ff1  mov     [rbp+4Fh+var_40], rax
0x180008ff5  mov     [rbp+4Fh+var_C0], 0
0x180008ffd  mov     r14, rcx
0x180009000  mov     rcx, [rbp+4Fh+arg_20]
0x180009004  mov     rsi, r9
0x180009007  mov     [rsp+110h+var_D0], 0
0x180009010  mov     r15d, r8d
0x180009013  mov     r12, rdx
0x180009016  test    r9, r9
0x180009019  jz      short loc_180009022
0x18000901b  mov     qword ptr [r9], 0
0x180009022  test    rcx, rcx
0x180009025  jz      short loc_180009052
0x180009027  xor     edi, edi
0x180009029  mov     rax, [rcx]
0x18000902c  lea     rdx, [rsp+110h+var_D0]
0x180009031  mov     [rsp+110h+ppv], rdx
0x180009036  mov     r9d, r15d
0x180009039  mov     r8, r12
0x18000903c  mov     rdx, r14
0x18000903f  mov     rax, [rax+0B8h]
0x180009046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000904b  mov     ebx, eax
0x18000904d  jmp     loc_180009121
0x180009052  mov     edx, 6; dwCoInit
0x180009057  xor     ecx, ecx; pvReserved
0x180009059  call    cs:__imp_CoInitializeEx
0x18000905f  xor     edi, edi
0x180009061  mov     ecx, 80010106h
0x180009066  cmp     eax, ecx
0x180009068  setnz   dil
0x18000906c  xor     ebx, ebx
0x18000906e  cmp     eax, ecx
0x180009070  cmovnz  ebx, eax
0x180009073  test    ebx, ebx
0x180009075  js      loc_180009139
0x18000907b  lea     rax, [rbp+4Fh+var_C0]
0x18000907f  xor     edx, edx; pUnkOuter
0x180009081  lea     r9, IID_IXWizard; riid
0x180009088  mov     [rsp+110h+ppv], rax; ppv
0x18000908d  mov     r8d, 401h; dwClsContext
0x180009093  lea     rcx, CLSID_CXWizard; rclsid
0x18000909a  call    cs:__imp_CoCreateInstance
0x1800090a0  mov     ebx, eax
0x1800090a2  test    eax, eax
0x1800090a4  js      short loc_1800090F0
0x1800090a6  mov     rcx, [rbp+4Fh+var_C0]
0x1800090aa  mov     r8, r14
0x1800090ad  mov     edx, 1
0x1800090b2  mov     rax, [rcx]
0x1800090b5  mov     rax, [rax+0D8h]
0x1800090bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090c1  mov     ebx, eax
0x1800090c3  test    eax, eax
0x1800090c5  js      short loc_1800090D0
0x1800090c7  mov     rcx, [rbp+4Fh+var_C0]
0x1800090cb  jmp     loc_180009029
0x1800090d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090d7  lea     rax, WPP_GLOBAL_Control
0x1800090de  cmp     rcx, rax
0x1800090e1  jz      short loc_180009128
0x1800090e3  test    byte ptr [rcx+1Ch], 10h
0x1800090e7  jz      short loc_180009128
0x1800090e9  mov     edx, 0Bh
0x1800090ee  jmp     short loc_18000910E
0x1800090f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090f7  lea     rax, WPP_GLOBAL_Control
0x1800090fe  cmp     rcx, rax
0x180009101  jz      short loc_180009128
0x180009103  test    byte ptr [rcx+1Ch], 4
0x180009107  jz      short loc_180009128
0x180009109  mov     edx, 0Ch
0x18000910e  mov     rcx, [rcx+10h]
0x180009112  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x180009119  mov     r9d, ebx
0x18000911c  call    WPP_SF_d
0x180009121  mov     rcx, cs:WPP_GLOBAL_Control
0x180009128  lea     r14, WPP_GLOBAL_Control
0x18000912f  test    ebx, ebx
0x180009131  jns     loc_18000935A
0x180009137  jmp     short loc_180009171
0x180009139  mov     rcx, cs:WPP_GLOBAL_Control
0x180009140  lea     r14, WPP_GLOBAL_Control
0x180009147  cmp     rcx, r14
0x18000914a  jz      short loc_180009171
0x18000914c  test    byte ptr [rcx+1Ch], 4
0x180009150  jz      short loc_180009171
0x180009152  mov     rcx, [rcx+10h]
0x180009156  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000915d  mov     edx, 0Dh
0x180009162  mov     r9d, ebx
0x180009165  call    WPP_SF_d
0x18000916a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009171  mov     r8, [rsp+110h+var_D0]
0x180009176  test    r8, r8
0x180009179  jz      loc_18000937A
0x18000917f  test    rsi, rsi
0x180009182  jz      loc_18000935F
0x180009188  xor     eax, eax
0x18000918a  mov     [rbp+4Fh+var_C8], 0
0x180009191  xorps   xmm0, xmm0
0x180009194  mov     [rbp+4Fh+var_88], rax
0x180009198  movups  xmmword ptr [rbp+4Fh+var_A8], xmm0
0x18000919c  mov     [rbp+4Fh+var_C4], 0
0x1800091a3  lea     rdx, [rbp+4Fh+var_C8]
0x1800091a7  movups  [rbp+4Fh+var_98], xmm0
0x1800091ab  mov     [rbp+4Fh+var_B0], 0
0x1800091b3  mov     rcx, r8
0x1800091b6  mov     [rbp+4Fh+bstrString], 0
0x1800091be  mov     rax, [r8]
0x1800091c1  mov     rax, [rax+58h]
0x1800091c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ca  test    eax, eax
0x1800091cc  js      loc_180009329
0x1800091d2  mov     rcx, [rsp+110h+var_D0]
0x1800091d7  lea     rdx, [rbp+4Fh+var_C4]
0x1800091db  mov     rax, [rcx]
0x1800091de  mov     rax, [rax+60h]
0x1800091e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091e7  test    eax, eax
0x1800091e9  js      loc_180009329
0x1800091ef  mov     rcx, [rsp+110h+var_D0]
0x1800091f4  lea     rdx, [rbp+4Fh+bstrString]
0x1800091f8  mov     rax, [rcx]
0x1800091fb  mov     rax, [rax+48h]
0x1800091ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009204  test    eax, eax
0x180009206  js      loc_180009329
0x18000920c  mov     rcx, [rsp+110h+var_D0]
0x180009211  lea     rdx, [rbp+4Fh+var_B0]
0x180009215  mov     rax, [rcx]
0x180009218  mov     rax, [rax+50h]
0x18000921c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009221  test    eax, eax
0x180009223  js      loc_180009329
0x180009229  mov     r9d, [rbp+4Fh+var_C8]
0x18000922d  lea     r8, aLd; "%ld"
0x180009234  mov     edx, 0Dh; unsigned __int64
0x180009239  lea     rcx, [rbp+4Fh+var_80]; unsigned __int16 *
0x18000923d  call    ?swprintf_sfn@@YAXPEAG_KPEBGZZ; swprintf_sfn(ushort *,unsigned __int64,ushort const *,...)
0x180009242  mov     r9d, [rbp+4Fh+var_C4]
0x180009246  lea     r8, aLd; "%ld"
0x18000924d  mov     edx, 0Dh; unsigned __int64
0x180009252  lea     rcx, [rbp+4Fh+var_60]; unsigned __int16 *
0x180009256  call    ?swprintf_sfn@@YAXPEAG_KPEBGZZ; swprintf_sfn(ushort *,unsigned __int64,ushort const *,...)
0x18000925b  mov     rdx, cs:lpSource; lpSource
0x180009262  lea     rax, [rbp+4Fh+var_80]
0x180009266  mov     [rbp+4Fh+var_A8+8], rax
0x18000926a  xor     r9d, r9d; dwLanguageId
0x18000926d  lea     rax, [rbp+4Fh+var_60]
0x180009271  mov     [rbp+4Fh+var_A8], r12
0x180009275  mov     qword ptr [rbp+4Fh+var_98], rax
0x180009279  mov     r8d, 0C0000004h; dwMessageId
0x18000927f  mov     rax, [rbp+4Fh+bstrString]
0x180009283  mov     ecx, 2900h; dwFlags
0x180009288  mov     qword ptr [rbp+4Fh+var_98+8], rax
0x18000928c  mov     rax, [rbp+4Fh+var_B0]
0x180009290  mov     [rbp+4Fh+var_88], rax
0x180009294  lea     rax, [rbp+4Fh+var_A8]
0x180009298  mov     [rsp+110h+Arguments], rax; Arguments
0x18000929d  mov     [rsp+110h+nSize], 0; nSize
0x1800092a5  mov     [rsp+110h+ppv], rsi; lpBuffer
0x1800092aa  call    cs:__imp_FormatMessageW
0x1800092b0  test    eax, eax
0x1800092b2  jz      short loc_1800092E4
0x1800092b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092bb  cmp     rcx, r14
0x1800092be  jz      short loc_180009313
0x1800092c0  test    byte ptr [rcx+1Ch], 4
0x1800092c4  jz      short loc_180009313
0x1800092c6  mov     r9, [rsi]
0x1800092c9  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x1800092d0  mov     rcx, [rcx+10h]
0x1800092d4  mov     edx, 0Eh
0x1800092d9  mov     dword ptr [rsp+110h+ppv], ebx
0x1800092dd  call    WPP_SF_SD
0x1800092e2  jmp     short loc_180009313
0x1800092e4  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800092e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092f0  cmp     rcx, r14
0x1800092f3  jz      short loc_180009313
0x1800092f5  test    byte ptr [rcx+1Ch], 4
0x1800092f9  jz      short loc_180009313
0x1800092fb  mov     rcx, [rcx+10h]
0x1800092ff  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x180009306  mov     edx, 0Fh
0x18000930b  mov     r9d, eax
0x18000930e  call    WPP_SF_d
0x180009313  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x180009317  call    cs:__imp_SysFreeString
0x18000931d  mov     rcx, [rbp+4Fh+var_B0]; bstrString
0x180009321  call    cs:__imp_SysFreeString
0x180009327  jmp     short loc_180009353
0x180009329  mov     rcx, cs:WPP_GLOBAL_Control
0x180009330  cmp     rcx, r14
0x180009333  jz      short loc_18000935A
0x180009335  test    byte ptr [rcx+1Ch], 4
0x180009339  jz      short loc_18000935A
0x18000933b  mov     rcx, [rcx+10h]
0x18000933f  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x180009346  mov     edx, 10h
0x18000934b  mov     r9d, eax
0x18000934e  call    WPP_SF_d
0x180009353  mov     rcx, cs:WPP_GLOBAL_Control
0x18000935a  mov     r8, [rsp+110h+var_D0]
0x18000935f  test    r8, r8
0x180009362  jz      short loc_18000937A
0x180009364  mov     rax, [r8]
0x180009367  mov     rcx, r8
0x18000936a  mov     rax, [rax+10h]
0x18000936e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009373  mov     rcx, cs:WPP_GLOBAL_Control
0x18000937a  mov     rdx, [rbp+4Fh+var_C0]
0x18000937e  test    rdx, rdx
0x180009381  jz      short loc_180009399
0x180009383  mov     rax, [rdx]
0x180009386  mov     rcx, rdx
0x180009389  mov     rax, [rax+10h]
0x18000938d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009392  mov     rcx, cs:WPP_GLOBAL_Control
0x180009399  test    edi, edi
0x18000939b  jz      short loc_1800093AA
0x18000939d  call    cs:__imp_CoUninitialize
0x1800093a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093aa  cmp     rcx, r14
0x1800093ad  jz      short loc_1800093CD
0x1800093af  test    byte ptr [rcx+1Ch], 10h
0x1800093b3  jz      short loc_1800093CD
0x1800093b5  mov     rcx, [rcx+10h]
0x1800093b9  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x1800093c0  mov     edx, 11h
0x1800093c5  mov     r9d, ebx
0x1800093c8  call    WPP_SF_d
0x1800093cd  mov     eax, ebx
0x1800093cf  mov     rcx, [rbp+4Fh+var_40]
0x1800093d3  xor     rcx, rsp; StackCookie
0x1800093d6  call    __security_check_cookie
0x1800093db  add     rsp, 0E0h
0x1800093e2  pop     r15
0x1800093e4  pop     r14
0x1800093e6  pop     r12
0x1800093e8  pop     rdi
0x1800093e9  pop     rsi
0x1800093ea  pop     rbx
0x1800093eb  pop     rbp
0x1800093ec  retn
```
