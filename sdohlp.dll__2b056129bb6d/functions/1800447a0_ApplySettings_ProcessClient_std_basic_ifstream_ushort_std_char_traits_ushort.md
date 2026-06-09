# ApplySettings::ProcessClient(std::basic_ifstream<ushort,std::char_traits<ushort>> &)

- ea: `0x1800447a0`
- end: `0x180044b8c`
- name: `?ProcessClient@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z`
- size: `1004`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043eec`

## callees

- `0x1800388a0`
- `0x180038ad0`
- `0x180042a80`
- `0x180043d8c`
- `0x1800447a0`
- `0x1800471b4`
- `0x180058010`

## import_xrefs

- `msvcrt!wcstol` at `0x1800449c7`
- `msvcrt!wcstol` at `0x1800449c7`
- `KERNEL32!GetLastError` at `0x180044816`
- `KERNEL32!GetLastError` at `0x1800448c5`
- `KERNEL32!GetLastError` at `0x1800449fc`
- `KERNEL32!GetLastError` at `0x180044a9f`
- `KERNEL32!GetLastError` at `0x180044816`
- `KERNEL32!GetLastError` at `0x1800448c5`
- `KERNEL32!GetLastError` at `0x1800449fc`
- `KERNEL32!GetLastError` at `0x180044a9f`
- `OLEAUT32!__imp_SysAllocString` at `0x180044896`
- `OLEAUT32!__imp_SysAllocString` at `0x180044896`
- `OLEAUT32!__imp_SysFreeString` at `0x1800448bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800448bb`
- `OLEAUT32!__imp_VariantInit` at `0x180044987`
- `OLEAUT32!__imp_VariantInit` at `0x180044987`
- `OLEAUT32!__imp_VariantClear` at `0x1800449ee`
- `OLEAUT32!__imp_VariantClear` at `0x1800449ee`

## string_xrefs

- `0x180044873`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180044922`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180044a59`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180044af0`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x18004485f`: `g_pService->get_Clients`

## pseudocode

```c
__int64 __fastcall ApplySettings::ProcessClient(_QWORD *a1, __int64 a2)
{
  const OLECHAR *v3; // rbx
  __int64 v5; // rcx
  unsigned int v6; // edi
  signed int LastError; // eax
  char v8; // bl
  const char *v9; // rsi
  int v10; // r8d
  int v11; // r9d
  int v12; // edx
  OLECHAR *v13; // rbx
  signed int v14; // eax
  __int64 v15; // rcx
  __int128 v16; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int64 (__fastcall *v18)(__int64, _QWORD, __int128 *); // rbx
  const wchar_t *v19; // rcx
  unsigned int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  VARIANTARG pvarg; // [rsp+38h] [rbp-29h] BYREF
  __int128 v25; // [rsp+58h] [rbp-9h] BYREF
  IRecordInfo *v26; // [rsp+68h] [rbp+7h]
  __int64 v27; // [rsp+C8h] [rbp+67h] BYREF
  __int64 v28; // [rsp+D8h] [rbp+77h] BYREF
  __int64 v29; // [rsp+E0h] [rbp+7Fh] BYREF

  v3 = (const OLECHAR *)(a1 + 2);
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 2);
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, v3);
  v5 = a1[1];
  v29 = 0;
  v27 = 0;
  v28 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 208LL))(v5, &v29);
  if ( v6 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = LastError;
    }
    else
    {
      v8 = 5;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v9 = "g_pService->get_Clients";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
      v12 = 23;
LABEL_43:
      WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v10, v11, (__int64)v9, v8);
    }
  }
  else
  {
    if ( *((_QWORD *)v3 + 3) >= 8u )
      v3 = *(const OLECHAR **)v3;
    v13 = SysAllocString(v3);
    v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v29 + 96LL))(v29, v13, &v27);
    SysFreeString(v13);
    if ( v6 )
    {
      v14 = GetLastError();
      v8 = v14;
      if ( v14 )
      {
        if ( v14 > 0 )
          v8 = v14;
      }
      else
      {
        v8 = 5;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v9 = "pClients->Add";
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
        v12 = 24;
        goto LABEL_43;
      }
    }
    else
    {
      while ( 1 )
      {
        std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 6);
        if ( (unsigned __int8)std::operator==<unsigned short>(
                                a1 + 6,
                                L"=================================================") )
          break;
        std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 10);
        std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 14);
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        ApplySettings::GetVariant(v15, a1 + 10, a1 + 14, &pvarg);
        v16 = *(_OWORD *)&pvarg.vt;
        pRecInfo = pvarg.pRecInfo;
        v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v27 + 64LL);
        if ( a1[9] < 8u )
          v19 = (const wchar_t *)(a1 + 6);
        else
          v19 = (const wchar_t *)a1[6];
        v20 = wcstol(v19, 0, 10);
        v25 = v16;
        v26 = pRecInfo;
        v6 = v18(v27, v20, &v25);
        VariantClear(&pvarg);
        if ( v6 )
        {
          v21 = GetLastError();
          v8 = v21;
          if ( v21 )
          {
            if ( v21 > 0 )
              v8 = v21;
          }
          else
          {
            v8 = 5;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v9 = "pItem->PutProperty";
            WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
            v12 = 25;
            goto LABEL_43;
          }
          goto LABEL_44;
        }
      }
      (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v27)(v27, &IID_IIASClient, &v28);
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 72LL))(v28);
      if ( v6 )
      {
        v22 = GetLastError();
        v8 = v22;
        if ( v22 )
        {
          if ( v22 > 0 )
            v8 = v22;
        }
        else
        {
          v8 = 5;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v9 = "pClient->Apply";
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
          v12 = 26;
          goto LABEL_43;
        }
      }
    }
  }
LABEL_44:
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return v6;
}

```

## disassembly

```asm
0x1800447a0  mov     rax, rsp
0x1800447a3  mov     [rax+10h], rbx
0x1800447a7  push    rbp
0x1800447a8  push    rsi
0x1800447a9  push    rdi
0x1800447aa  push    r14
0x1800447ac  push    r15
0x1800447ae  lea     rbp, [rax-5Fh]
0x1800447b2  sub     rsp, 90h
0x1800447b9  mov     r15, rdx
0x1800447bc  movaps  xmmword ptr [rax-38h], xmm6
0x1800447c0  lea     rbx, [rcx+10h]
0x1800447c4  movaps  xmmword ptr [rax-48h], xmm7
0x1800447c8  mov     r14, rcx
0x1800447cb  mov     rdx, rbx
0x1800447ce  mov     rcx, r15
0x1800447d1  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800447d6  mov     rdx, rbx
0x1800447d9  mov     rcx, r15
0x1800447dc  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800447e1  mov     rcx, [r14+8]
0x1800447e5  lea     rdx, [rbp+57h+arg_18]
0x1800447e9  mov     [rbp+57h+arg_18], 0
0x1800447f1  mov     [rbp+57h+arg_0], 0
0x1800447f9  mov     [rbp+57h+arg_10], 0
0x180044801  mov     rax, [rcx]
0x180044804  mov     rax, [rax+0D0h]
0x18004480b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044810  mov     edi, eax
0x180044812  test    eax, eax
0x180044814  jz      short loc_180044889
0x180044816  call    cs:__imp_GetLastError
0x18004481c  mov     ebx, eax
0x18004481e  test    eax, eax
0x180044820  jz      short loc_18004482F
0x180044822  jle     short loc_180044834
0x180044824  movzx   ebx, ax
0x180044827  or      ebx, 80070000h
0x18004482d  jmp     short loc_180044834
0x18004482f  mov     ebx, 80004005h
0x180044834  mov     rcx, cs:WPP_GLOBAL_Control
0x18004483b  lea     rax, WPP_GLOBAL_Control
0x180044842  cmp     rcx, rax
0x180044845  jz      loc_180044B1A
0x18004484b  cmp     byte ptr [rcx+19h], 2
0x18004484f  jb      loc_180044B1A
0x180044855  test    byte ptr [rcx+1Ch], 10h
0x180044859  jz      loc_180044B1A
0x18004485f  lea     rsi, aGPserviceGetCl; "g_pService->get_Clients"
0x180044866  mov     r9d, ebx
0x180044869  mov     r8, rsi
0x18004486c  lea     rdx, aNpsds; "NPSDS"
0x180044873  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18004487a  call    WppDbgPrint
0x18004487f  mov     edx, 17h
0x180044884  jmp     loc_180044B01
0x180044889  cmp     qword ptr [rbx+18h], 8
0x18004488e  jb      short loc_180044893
0x180044890  mov     rbx, [rbx]
0x180044893  mov     rcx, rbx; psz
0x180044896  call    cs:__imp_SysAllocString
0x18004489c  mov     rcx, [rbp+57h+arg_18]
0x1800448a0  lea     r8, [rbp+57h+arg_0]
0x1800448a4  mov     rbx, rax
0x1800448a7  mov     rdx, [rcx]
0x1800448aa  mov     rax, [rdx+60h]
0x1800448ae  mov     rdx, rbx
0x1800448b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448b6  mov     rcx, rbx; bstrString
0x1800448b9  mov     edi, eax
0x1800448bb  call    cs:__imp_SysFreeString
0x1800448c1  test    edi, edi
0x1800448c3  jz      short loc_180044938
0x1800448c5  call    cs:__imp_GetLastError
0x1800448cb  mov     ebx, eax
0x1800448cd  test    eax, eax
0x1800448cf  jz      short loc_1800448DE
0x1800448d1  jle     short loc_1800448E3
0x1800448d3  movzx   ebx, ax
0x1800448d6  or      ebx, 80070000h
0x1800448dc  jmp     short loc_1800448E3
0x1800448de  mov     ebx, 80004005h
0x1800448e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800448ea  lea     rax, WPP_GLOBAL_Control
0x1800448f1  cmp     rcx, rax
0x1800448f4  jz      loc_180044B1A
0x1800448fa  cmp     byte ptr [rcx+19h], 2
0x1800448fe  jb      loc_180044B1A
0x180044904  test    byte ptr [rcx+1Ch], 10h
0x180044908  jz      loc_180044B1A
0x18004490e  lea     rsi, aPclientsAdd; "pClients->Add"
0x180044915  mov     r9d, ebx
0x180044918  mov     r8, rsi
0x18004491b  lea     rdx, aNpsds; "NPSDS"
0x180044922  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180044929  call    WppDbgPrint
0x18004492e  mov     edx, 18h
0x180044933  jmp     loc_180044B01
0x180044938  lea     rsi, [r14+30h]
0x18004493c  mov     rdx, rsi
0x18004493f  mov     rcx, r15
0x180044942  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180044947  lea     rdx, asc_180066850; "======================================="...
0x18004494e  mov     rcx, rsi
0x180044951  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180044956  test    al, al
0x180044958  jnz     loc_180044A6F
0x18004495e  lea     rdx, [r14+50h]
0x180044962  mov     rcx, r15
0x180044965  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x18004496a  lea     rdx, [r14+70h]
0x18004496e  mov     rcx, r15
0x180044971  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180044976  xorps   xmm0, xmm0
0x180044979  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004497d  xor     eax, eax
0x18004497f  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180044983  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180044987  call    cs:__imp_VariantInit
0x18004498d  lea     r9, [rbp+57h+pvarg]
0x180044991  lea     r8, [r14+70h]
0x180044995  lea     rdx, [r14+50h]
0x180044999  call    ?GetVariant@ApplySettings@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAUtagVARIANT@@@Z; ApplySettings::GetVariant(std::wstring &,std::wstring &,tagVARIANT &)
0x18004499e  cmp     qword ptr [r14+48h], 8
0x1800449a3  mov     rax, [rbp+57h+arg_0]
0x1800449a7  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x1800449ab  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x1800449b0  mov     rcx, [rax]
0x1800449b3  mov     rbx, [rcx+40h]
0x1800449b7  jb      short loc_1800449BE
0x1800449b9  mov     rcx, [rsi]
0x1800449bc  jmp     short loc_1800449C1
0x1800449be  mov     rcx, rsi; String
0x1800449c1  xor     edx, edx; EndPtr
0x1800449c3  lea     r8d, [rdx+0Ah]; Radix
0x1800449c7  call    cs:__imp_wcstol
0x1800449cd  mov     rcx, [rbp+57h+arg_0]
0x1800449d1  lea     r8, [rbp+57h+var_60]
0x1800449d5  mov     edx, eax
0x1800449d7  movaps  [rbp+57h+var_60], xmm6
0x1800449db  mov     rax, rbx
0x1800449de  movsd   [rbp+57h+var_50], xmm7
0x1800449e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800449e8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800449ec  mov     edi, eax
0x1800449ee  call    cs:__imp_VariantClear
0x1800449f4  test    edi, edi
0x1800449f6  jz      loc_18004493C
0x1800449fc  call    cs:__imp_GetLastError
0x180044a02  mov     ebx, eax
0x180044a04  test    eax, eax
0x180044a06  jz      short loc_180044A15
0x180044a08  jle     short loc_180044A1A
0x180044a0a  movzx   ebx, ax
0x180044a0d  or      ebx, 80070000h
0x180044a13  jmp     short loc_180044A1A
0x180044a15  mov     ebx, 80004005h
0x180044a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180044a21  lea     rax, WPP_GLOBAL_Control
0x180044a28  cmp     rcx, rax
0x180044a2b  jz      loc_180044B1A
0x180044a31  cmp     byte ptr [rcx+19h], 2
0x180044a35  jb      loc_180044B1A
0x180044a3b  test    byte ptr [rcx+1Ch], 10h
0x180044a3f  jz      loc_180044B1A
0x180044a45  lea     rsi, aPitemPutproper; "pItem->PutProperty"
0x180044a4c  mov     r9d, ebx
0x180044a4f  mov     r8, rsi
0x180044a52  lea     rdx, aNpsds; "NPSDS"
0x180044a59  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180044a60  call    WppDbgPrint
0x180044a65  mov     edx, 19h
0x180044a6a  jmp     loc_180044B01
0x180044a6f  mov     rcx, [rbp+57h+arg_0]
0x180044a73  lea     r8, [rbp+57h+arg_10]
0x180044a77  lea     rdx, IID_IIASClient
0x180044a7e  mov     rax, [rcx]
0x180044a81  mov     rax, [rax]
0x180044a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a89  mov     rcx, [rbp+57h+arg_10]
0x180044a8d  mov     rax, [rcx]
0x180044a90  mov     rax, [rax+48h]
0x180044a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a99  mov     edi, eax
0x180044a9b  test    eax, eax
0x180044a9d  jz      short loc_180044B1A
0x180044a9f  call    cs:__imp_GetLastError
0x180044aa5  mov     ebx, eax
0x180044aa7  test    eax, eax
0x180044aa9  jz      short loc_180044AB8
0x180044aab  jle     short loc_180044ABD
0x180044aad  movzx   ebx, ax
0x180044ab0  or      ebx, 80070000h
0x180044ab6  jmp     short loc_180044ABD
0x180044ab8  mov     ebx, 80004005h
0x180044abd  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ac4  lea     rax, WPP_GLOBAL_Control
0x180044acb  cmp     rcx, rax
0x180044ace  jz      short loc_180044B1A
0x180044ad0  cmp     byte ptr [rcx+19h], 2
0x180044ad4  jb      short loc_180044B1A
0x180044ad6  test    byte ptr [rcx+1Ch], 10h
0x180044ada  jz      short loc_180044B1A
0x180044adc  lea     rsi, aPclientApply; "pClient->Apply"
0x180044ae3  mov     r9d, ebx
0x180044ae6  mov     r8, rsi
0x180044ae9  lea     rdx, aNpsds; "NPSDS"
0x180044af0  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180044af7  call    WppDbgPrint
0x180044afc  mov     edx, 1Ah
0x180044b01  mov     rcx, cs:WPP_GLOBAL_Control
0x180044b08  mov     [rsp+0B0h+var_88], ebx
0x180044b0c  mov     qword ptr [rsp+0B0h+var_90], rsi
0x180044b11  mov     rcx, [rcx+10h]
0x180044b15  call    WPP_SF_ssd
0x180044b1a  mov     rcx, [rbp+57h+arg_10]
0x180044b1e  test    rcx, rcx
0x180044b21  jz      short loc_180044B37
0x180044b23  mov     rax, [rcx]
0x180044b26  mov     rax, [rax+10h]
0x180044b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b2f  mov     [rbp+57h+arg_10], 0
0x180044b37  mov     rcx, [rbp+57h+arg_0]
0x180044b3b  test    rcx, rcx
0x180044b3e  jz      short loc_180044B54
0x180044b40  mov     rax, [rcx]
0x180044b43  mov     rax, [rax+10h]
0x180044b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b4c  mov     [rbp+57h+arg_0], 0
0x180044b54  mov     rcx, [rbp+57h+arg_18]
0x180044b58  test    rcx, rcx
0x180044b5b  jz      short loc_180044B69
0x180044b5d  mov     rax, [rcx]
0x180044b60  mov     rax, [rax+10h]
0x180044b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b69  movaps  xmm7, [rsp+0B0h+var_48+8]
0x180044b6e  lea     r11, [rsp+0B0h+var_20]
0x180044b76  mov     rbx, [r11+38h]
0x180044b7a  mov     eax, edi
0x180044b7c  movaps  xmm6, xmmword ptr [r11-10h]
0x180044b81  mov     rsp, r11
0x180044b84  pop     r15
0x180044b86  pop     r14
0x180044b88  pop     rdi
0x180044b89  pop     rsi
0x180044b8a  pop     rbp
0x180044b8b  retn
```
