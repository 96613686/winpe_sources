# ApplySettings::ProcessDatabaseAccounting(std::basic_ifstream<ushort,std::char_traits<ushort>> &)

- ea: `0x180044b94`
- end: `0x180044e55`
- name: `?ProcessDatabaseAccounting@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z`
- size: `705`
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
- `0x180044b94`
- `0x1800471b4`
- `0x180058010`

## import_xrefs

- `msvcrt!wcstol` at `0x180044ceb`
- `msvcrt!wcstol` at `0x180044ceb`
- `KERNEL32!GetLastError` at `0x180044bdd`
- `KERNEL32!GetLastError` at `0x180044d20`
- `KERNEL32!GetLastError` at `0x180044da6`
- `KERNEL32!GetLastError` at `0x180044bdd`
- `KERNEL32!GetLastError` at `0x180044d20`
- `KERNEL32!GetLastError` at `0x180044da6`
- `OLEAUT32!__imp_VariantInit` at `0x180044cab`
- `OLEAUT32!__imp_VariantInit` at `0x180044cab`
- `OLEAUT32!__imp_VariantClear` at `0x180044d12`
- `OLEAUT32!__imp_VariantClear` at `0x180044d12`

## string_xrefs

- `0x180044c3a`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180044d7d`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180044df7`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180044c26`: `g_pService->get_SQLAccountingLogs`

## pseudocode

```c
__int64 __fastcall ApplySettings::ProcessDatabaseAccounting(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rcx
  unsigned int v5; // edi
  signed int LastError; // eax
  char v7; // bl
  const char *v8; // rsi
  int v9; // r8d
  int v10; // r9d
  int v11; // edx
  __int64 v12; // rcx
  __int128 v13; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int64 (__fastcall *v15)(__int64, _QWORD, __int128 *); // rbx
  const wchar_t *v16; // rcx
  unsigned int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  VARIANTARG pvarg; // [rsp+38h] [rbp-39h] BYREF
  __int128 v22; // [rsp+58h] [rbp-19h] BYREF
  IRecordInfo *v23; // [rsp+68h] [rbp-9h]
  __int64 v24; // [rsp+D8h] [rbp+67h] BYREF

  v3 = a1[1];
  v24 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 200LL))(v3, &v24);
  if ( v5 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = LastError;
    }
    else
    {
      v7 = 5;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v8 = "g_pService->get_SQLAccountingLogs";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
      v11 = 33;
LABEL_33:
      WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v9, v10, (__int64)v8, v7);
    }
  }
  else
  {
    std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 2);
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
      ApplySettings::GetVariant(v12, a1 + 10, a1 + 14, &pvarg);
      v13 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v24 + 64LL);
      if ( a1[9] < 8u )
        v16 = (const wchar_t *)(a1 + 6);
      else
        v16 = (const wchar_t *)a1[6];
      v17 = wcstol(v16, 0, 10);
      v22 = v13;
      v23 = pRecInfo;
      v5 = v15(v24, v17, &v22);
      VariantClear(&pvarg);
      if ( v5 )
      {
        v18 = GetLastError();
        v7 = v18;
        if ( v18 )
        {
          if ( v18 > 0 )
            v7 = v18;
        }
        else
        {
          v7 = 5;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v8 = "pSQLAcct->PutProperty";
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
          v11 = 34;
          goto LABEL_33;
        }
        goto LABEL_34;
      }
    }
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 72LL))(v24);
    if ( v5 )
    {
      v19 = GetLastError();
      v7 = v19;
      if ( v19 )
      {
        if ( v19 > 0 )
          v7 = v19;
      }
      else
      {
        v7 = 5;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v8 = "pSQLAcct->Apply";
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
        v11 = 35;
        goto LABEL_33;
      }
    }
  }
LABEL_34:
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return v5;
}

```

## disassembly

```asm
0x180044b94  mov     rax, rsp
0x180044b97  push    rbp
0x180044b98  push    rbx
0x180044b99  push    rsi
0x180044b9a  push    rdi
0x180044b9b  push    r14
0x180044b9d  push    r15
0x180044b9f  lea     rbp, [rax-5Fh]
0x180044ba3  sub     rsp, 98h
0x180044baa  movaps  xmmword ptr [rax-48h], xmm6
0x180044bae  mov     r14, rcx
0x180044bb1  mov     rcx, [rcx+8]
0x180044bb5  mov     r15, rdx
0x180044bb8  movaps  xmmword ptr [rax-58h], xmm7
0x180044bbc  lea     rdx, [rbp+57h+arg_0]
0x180044bc0  mov     [rbp+57h+arg_0], 0
0x180044bc8  mov     rax, [rcx]
0x180044bcb  mov     rax, [rax+0C8h]
0x180044bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bd7  mov     edi, eax
0x180044bd9  test    eax, eax
0x180044bdb  jz      short loc_180044C50
0x180044bdd  call    cs:__imp_GetLastError
0x180044be3  mov     ebx, eax
0x180044be5  test    eax, eax
0x180044be7  jz      short loc_180044BF6
0x180044be9  jle     short loc_180044BFB
0x180044beb  movzx   ebx, ax
0x180044bee  or      ebx, 80070000h
0x180044bf4  jmp     short loc_180044BFB
0x180044bf6  mov     ebx, 80004005h
0x180044bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180044c02  lea     rax, WPP_GLOBAL_Control
0x180044c09  cmp     rcx, rax
0x180044c0c  jz      loc_180044E21
0x180044c12  cmp     byte ptr [rcx+19h], 2
0x180044c16  jb      loc_180044E21
0x180044c1c  test    byte ptr [rcx+1Ch], 10h
0x180044c20  jz      loc_180044E21
0x180044c26  lea     rsi, aGPserviceGetSq; "g_pService->get_SQLAccountingLogs"
0x180044c2d  mov     r9d, ebx
0x180044c30  mov     r8, rsi
0x180044c33  lea     rdx, aNpsds; "NPSDS"
0x180044c3a  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180044c41  call    WppDbgPrint
0x180044c46  mov     edx, 21h ; '!'
0x180044c4b  jmp     loc_180044E08
0x180044c50  lea     rdx, [r14+10h]
0x180044c54  mov     rcx, r15
0x180044c57  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180044c5c  lea     rsi, [r14+30h]
0x180044c60  mov     rdx, rsi
0x180044c63  mov     rcx, r15
0x180044c66  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180044c6b  lea     rdx, asc_180066850; "======================================="...
0x180044c72  mov     rcx, rsi
0x180044c75  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180044c7a  test    al, al
0x180044c7c  jnz     loc_180044D90
0x180044c82  lea     rdx, [r14+50h]
0x180044c86  mov     rcx, r15
0x180044c89  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180044c8e  lea     rdx, [r14+70h]
0x180044c92  mov     rcx, r15
0x180044c95  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180044c9a  xorps   xmm0, xmm0
0x180044c9d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180044ca1  xor     eax, eax
0x180044ca3  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180044ca7  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180044cab  call    cs:__imp_VariantInit
0x180044cb1  lea     r9, [rbp+57h+pvarg]
0x180044cb5  lea     r8, [r14+70h]
0x180044cb9  lea     rdx, [r14+50h]
0x180044cbd  call    ?GetVariant@ApplySettings@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAUtagVARIANT@@@Z; ApplySettings::GetVariant(std::wstring &,std::wstring &,tagVARIANT &)
0x180044cc2  cmp     qword ptr [r14+48h], 8
0x180044cc7  mov     rax, [rbp+57h+arg_0]
0x180044ccb  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x180044ccf  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x180044cd4  mov     rcx, [rax]
0x180044cd7  mov     rbx, [rcx+40h]
0x180044cdb  jb      short loc_180044CE2
0x180044cdd  mov     rcx, [rsi]
0x180044ce0  jmp     short loc_180044CE5
0x180044ce2  mov     rcx, rsi; String
0x180044ce5  xor     edx, edx; EndPtr
0x180044ce7  lea     r8d, [rdx+0Ah]; Radix
0x180044ceb  call    cs:__imp_wcstol
0x180044cf1  mov     rcx, [rbp+57h+arg_0]
0x180044cf5  lea     r8, [rbp+57h+var_70]
0x180044cf9  mov     edx, eax
0x180044cfb  movaps  [rbp+57h+var_70], xmm6
0x180044cff  mov     rax, rbx
0x180044d02  movsd   [rbp+57h+var_60], xmm7
0x180044d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d0c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180044d10  mov     edi, eax
0x180044d12  call    cs:__imp_VariantClear
0x180044d18  test    edi, edi
0x180044d1a  jz      loc_180044C60
0x180044d20  call    cs:__imp_GetLastError
0x180044d26  mov     ebx, eax
0x180044d28  test    eax, eax
0x180044d2a  jz      short loc_180044D39
0x180044d2c  jle     short loc_180044D3E
0x180044d2e  movzx   ebx, ax
0x180044d31  or      ebx, 80070000h
0x180044d37  jmp     short loc_180044D3E
0x180044d39  mov     ebx, 80004005h
0x180044d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180044d45  lea     rax, WPP_GLOBAL_Control
0x180044d4c  cmp     rcx, rax
0x180044d4f  jz      loc_180044E21
0x180044d55  cmp     byte ptr [rcx+19h], 2
0x180044d59  jb      loc_180044E21
0x180044d5f  test    byte ptr [rcx+1Ch], 10h
0x180044d63  jz      loc_180044E21
0x180044d69  lea     rsi, aPsqlacctPutpro; "pSQLAcct->PutProperty"
0x180044d70  mov     r9d, ebx
0x180044d73  mov     r8, rsi
0x180044d76  lea     rdx, aNpsds; "NPSDS"
0x180044d7d  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180044d84  call    WppDbgPrint
0x180044d89  mov     edx, 22h ; '"'
0x180044d8e  jmp     short loc_180044E08
0x180044d90  mov     rcx, [rbp+57h+arg_0]
0x180044d94  mov     rax, [rcx]
0x180044d97  mov     rax, [rax+48h]
0x180044d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044da0  mov     edi, eax
0x180044da2  test    eax, eax
0x180044da4  jz      short loc_180044E21
0x180044da6  call    cs:__imp_GetLastError
0x180044dac  mov     ebx, eax
0x180044dae  test    eax, eax
0x180044db0  jz      short loc_180044DBF
0x180044db2  jle     short loc_180044DC4
0x180044db4  movzx   ebx, ax
0x180044db7  or      ebx, 80070000h
0x180044dbd  jmp     short loc_180044DC4
0x180044dbf  mov     ebx, 80004005h
0x180044dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180044dcb  lea     rax, WPP_GLOBAL_Control
0x180044dd2  cmp     rcx, rax
0x180044dd5  jz      short loc_180044E21
0x180044dd7  cmp     byte ptr [rcx+19h], 2
0x180044ddb  jb      short loc_180044E21
0x180044ddd  test    byte ptr [rcx+1Ch], 10h
0x180044de1  jz      short loc_180044E21
0x180044de3  lea     rsi, aPsqlacctApply; "pSQLAcct->Apply"
0x180044dea  mov     r9d, ebx
0x180044ded  mov     r8, rsi
0x180044df0  lea     rdx, aNpsds; "NPSDS"
0x180044df7  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180044dfe  call    WppDbgPrint
0x180044e03  mov     edx, 23h ; '#'
0x180044e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180044e0f  mov     [rsp+28h], ebx
0x180044e13  mov     qword ptr [rsp+0C0h+var_A0], rsi
0x180044e18  mov     rcx, [rcx+10h]
0x180044e1c  call    WPP_SF_ssd
0x180044e21  mov     rcx, [rbp+57h+arg_0]
0x180044e25  test    rcx, rcx
0x180044e28  jz      short loc_180044E36
0x180044e2a  mov     rax, [rcx]
0x180044e2d  mov     rax, [rax+10h]
0x180044e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e36  movaps  xmm6, [rsp+0C0h+var_48+8]
0x180044e3e  mov     eax, edi
0x180044e40  movaps  xmm7, [rsp+0C0h+var_58+8]
0x180044e45  add     rsp, 98h
0x180044e4c  pop     r15
0x180044e4e  pop     r14
0x180044e50  pop     rdi
0x180044e51  pop     rsi
0x180044e52  pop     rbx
0x180044e53  pop     rbp
0x180044e54  retn
```
