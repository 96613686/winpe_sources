# ApplySettings::ProcessAccounting(std::basic_ifstream<ushort,std::char_traits<ushort>> &)

- ea: `0x1800444d8`
- end: `0x180044799`
- name: `?ProcessAccounting@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z`
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
- `0x1800444d8`
- `0x1800471b4`
- `0x180058010`

## import_xrefs

- `msvcrt!wcstol` at `0x18004462f`
- `msvcrt!wcstol` at `0x18004462f`
- `KERNEL32!GetLastError` at `0x180044521`
- `KERNEL32!GetLastError` at `0x180044664`
- `KERNEL32!GetLastError` at `0x1800446ea`
- `KERNEL32!GetLastError` at `0x180044521`
- `KERNEL32!GetLastError` at `0x180044664`
- `KERNEL32!GetLastError` at `0x1800446ea`
- `OLEAUT32!__imp_VariantInit` at `0x1800445ef`
- `OLEAUT32!__imp_VariantInit` at `0x1800445ef`
- `OLEAUT32!__imp_VariantClear` at `0x180044656`
- `OLEAUT32!__imp_VariantClear` at `0x180044656`

## string_xrefs

- `0x18004457e`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x1800446c1`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x18004473b`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x18004456a`: `g_pService->get_FileAccountingLogs`

## pseudocode

```c
__int64 __fastcall ApplySettings::ProcessAccounting(_QWORD *a1, __int64 a2)
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
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 192LL))(v3, &v24);
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
      v8 = "g_pService->get_FileAccountingLogs";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
      v11 = 30;
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
          v8 = "pFileAcct->PutProperty";
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
          v11 = 31;
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
        v8 = "pFileAcct->Apply";
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
        v11 = 32;
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
0x1800444d8  mov     rax, rsp
0x1800444db  push    rbp
0x1800444dc  push    rbx
0x1800444dd  push    rsi
0x1800444de  push    rdi
0x1800444df  push    r14
0x1800444e1  push    r15
0x1800444e3  lea     rbp, [rax-5Fh]
0x1800444e7  sub     rsp, 98h
0x1800444ee  movaps  xmmword ptr [rax-48h], xmm6
0x1800444f2  mov     r14, rcx
0x1800444f5  mov     rcx, [rcx+8]
0x1800444f9  mov     r15, rdx
0x1800444fc  movaps  xmmword ptr [rax-58h], xmm7
0x180044500  lea     rdx, [rbp+57h+arg_0]
0x180044504  mov     [rbp+57h+arg_0], 0
0x18004450c  mov     rax, [rcx]
0x18004450f  mov     rax, [rax+0C0h]
0x180044516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004451b  mov     edi, eax
0x18004451d  test    eax, eax
0x18004451f  jz      short loc_180044594
0x180044521  call    cs:__imp_GetLastError
0x180044527  mov     ebx, eax
0x180044529  test    eax, eax
0x18004452b  jz      short loc_18004453A
0x18004452d  jle     short loc_18004453F
0x18004452f  movzx   ebx, ax
0x180044532  or      ebx, 80070000h
0x180044538  jmp     short loc_18004453F
0x18004453a  mov     ebx, 80004005h
0x18004453f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044546  lea     rax, WPP_GLOBAL_Control
0x18004454d  cmp     rcx, rax
0x180044550  jz      loc_180044765
0x180044556  cmp     byte ptr [rcx+19h], 2
0x18004455a  jb      loc_180044765
0x180044560  test    byte ptr [rcx+1Ch], 10h
0x180044564  jz      loc_180044765
0x18004456a  lea     rsi, aGPserviceGetFi; "g_pService->get_FileAccountingLogs"
0x180044571  mov     r9d, ebx
0x180044574  mov     r8, rsi
0x180044577  lea     rdx, aNpsds; "NPSDS"
0x18004457e  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180044585  call    WppDbgPrint
0x18004458a  mov     edx, 1Eh
0x18004458f  jmp     loc_18004474C
0x180044594  lea     rdx, [r14+10h]
0x180044598  mov     rcx, r15
0x18004459b  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800445a0  lea     rsi, [r14+30h]
0x1800445a4  mov     rdx, rsi
0x1800445a7  mov     rcx, r15
0x1800445aa  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800445af  lea     rdx, asc_180066850; "======================================="...
0x1800445b6  mov     rcx, rsi
0x1800445b9  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x1800445be  test    al, al
0x1800445c0  jnz     loc_1800446D4
0x1800445c6  lea     rdx, [r14+50h]
0x1800445ca  mov     rcx, r15
0x1800445cd  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800445d2  lea     rdx, [r14+70h]
0x1800445d6  mov     rcx, r15
0x1800445d9  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800445de  xorps   xmm0, xmm0
0x1800445e1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800445e5  xor     eax, eax
0x1800445e7  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800445eb  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800445ef  call    cs:__imp_VariantInit
0x1800445f5  lea     r9, [rbp+57h+pvarg]
0x1800445f9  lea     r8, [r14+70h]
0x1800445fd  lea     rdx, [r14+50h]
0x180044601  call    ?GetVariant@ApplySettings@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAUtagVARIANT@@@Z; ApplySettings::GetVariant(std::wstring &,std::wstring &,tagVARIANT &)
0x180044606  cmp     qword ptr [r14+48h], 8
0x18004460b  mov     rax, [rbp+57h+arg_0]
0x18004460f  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x180044613  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x180044618  mov     rcx, [rax]
0x18004461b  mov     rbx, [rcx+40h]
0x18004461f  jb      short loc_180044626
0x180044621  mov     rcx, [rsi]
0x180044624  jmp     short loc_180044629
0x180044626  mov     rcx, rsi; String
0x180044629  xor     edx, edx; EndPtr
0x18004462b  lea     r8d, [rdx+0Ah]; Radix
0x18004462f  call    cs:__imp_wcstol
0x180044635  mov     rcx, [rbp+57h+arg_0]
0x180044639  lea     r8, [rbp+57h+var_70]
0x18004463d  mov     edx, eax
0x18004463f  movaps  [rbp+57h+var_70], xmm6
0x180044643  mov     rax, rbx
0x180044646  movsd   [rbp+57h+var_60], xmm7
0x18004464b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044650  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180044654  mov     edi, eax
0x180044656  call    cs:__imp_VariantClear
0x18004465c  test    edi, edi
0x18004465e  jz      loc_1800445A4
0x180044664  call    cs:__imp_GetLastError
0x18004466a  mov     ebx, eax
0x18004466c  test    eax, eax
0x18004466e  jz      short loc_18004467D
0x180044670  jle     short loc_180044682
0x180044672  movzx   ebx, ax
0x180044675  or      ebx, 80070000h
0x18004467b  jmp     short loc_180044682
0x18004467d  mov     ebx, 80004005h
0x180044682  mov     rcx, cs:WPP_GLOBAL_Control
0x180044689  lea     rax, WPP_GLOBAL_Control
0x180044690  cmp     rcx, rax
0x180044693  jz      loc_180044765
0x180044699  cmp     byte ptr [rcx+19h], 2
0x18004469d  jb      loc_180044765
0x1800446a3  test    byte ptr [rcx+1Ch], 10h
0x1800446a7  jz      loc_180044765
0x1800446ad  lea     rsi, aPfileacctPutpr; "pFileAcct->PutProperty"
0x1800446b4  mov     r9d, ebx
0x1800446b7  mov     r8, rsi
0x1800446ba  lea     rdx, aNpsds; "NPSDS"
0x1800446c1  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x1800446c8  call    WppDbgPrint
0x1800446cd  mov     edx, 1Fh
0x1800446d2  jmp     short loc_18004474C
0x1800446d4  mov     rcx, [rbp+57h+arg_0]
0x1800446d8  mov     rax, [rcx]
0x1800446db  mov     rax, [rax+48h]
0x1800446df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446e4  mov     edi, eax
0x1800446e6  test    eax, eax
0x1800446e8  jz      short loc_180044765
0x1800446ea  call    cs:__imp_GetLastError
0x1800446f0  mov     ebx, eax
0x1800446f2  test    eax, eax
0x1800446f4  jz      short loc_180044703
0x1800446f6  jle     short loc_180044708
0x1800446f8  movzx   ebx, ax
0x1800446fb  or      ebx, 80070000h
0x180044701  jmp     short loc_180044708
0x180044703  mov     ebx, 80004005h
0x180044708  mov     rcx, cs:WPP_GLOBAL_Control
0x18004470f  lea     rax, WPP_GLOBAL_Control
0x180044716  cmp     rcx, rax
0x180044719  jz      short loc_180044765
0x18004471b  cmp     byte ptr [rcx+19h], 2
0x18004471f  jb      short loc_180044765
0x180044721  test    byte ptr [rcx+1Ch], 10h
0x180044725  jz      short loc_180044765
0x180044727  lea     rsi, aPfileacctApply; "pFileAcct->Apply"
0x18004472e  mov     r9d, ebx
0x180044731  mov     r8, rsi
0x180044734  lea     rdx, aNpsds; "NPSDS"
0x18004473b  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180044742  call    WppDbgPrint
0x180044747  mov     edx, 20h ; ' '
0x18004474c  mov     rcx, cs:WPP_GLOBAL_Control
0x180044753  mov     [rsp+28h], ebx
0x180044757  mov     qword ptr [rsp+0C0h+var_A0], rsi
0x18004475c  mov     rcx, [rcx+10h]
0x180044760  call    WPP_SF_ssd
0x180044765  mov     rcx, [rbp+57h+arg_0]
0x180044769  test    rcx, rcx
0x18004476c  jz      short loc_18004477A
0x18004476e  mov     rax, [rcx]
0x180044771  mov     rax, [rax+10h]
0x180044775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004477a  movaps  xmm6, [rsp+0C0h+var_48+8]
0x180044782  mov     eax, edi
0x180044784  movaps  xmm7, [rsp+0C0h+var_58+8]
0x180044789  add     rsp, 98h
0x180044790  pop     r15
0x180044792  pop     r14
0x180044794  pop     rdi
0x180044795  pop     rsi
0x180044796  pop     rbx
0x180044797  pop     rbp
0x180044798  retn
```
