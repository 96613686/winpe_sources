# ApplySettings::ProcessService(std::basic_ifstream<ushort,std::char_traits<ushort>> &)

- ea: `0x18004667c`
- end: `0x1800468ed`
- name: `?ProcessService@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043eec`

## callees

- `0x1800388a0`
- `0x180038ad0`
- `0x180042a80`
- `0x18004667c`
- `0x1800471b4`
- `0x180058010`

## import_xrefs

- `msvcrt!wcstol` at `0x180046708`
- `msvcrt!wcstol` at `0x180046708`
- `KERNEL32!GetLastError` at `0x180046743`
- `KERNEL32!GetLastError` at `0x180046785`
- `KERNEL32!GetLastError` at `0x180046865`
- `KERNEL32!GetLastError` at `0x180046743`
- `KERNEL32!GetLastError` at `0x180046785`
- `KERNEL32!GetLastError` at `0x180046865`
- `OLEAUT32!__imp_SysAllocString` at `0x1800466ea`
- `OLEAUT32!__imp_SysAllocString` at `0x1800466ea`
- `OLEAUT32!__imp_SysFreeString` at `0x180046735`
- `OLEAUT32!__imp_SysFreeString` at `0x180046777`
- `OLEAUT32!__imp_SysFreeString` at `0x180046735`
- `OLEAUT32!__imp_SysFreeString` at `0x180046777`

## string_xrefs

- `0x1800467e2`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x18004683c`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x1800468b6`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x1800468a2`: `g_pService->Apply`
- `0x180046828`: `g_pService->put_AcctPorts`
- `0x1800467ce`: `g_pService->put_AuthPorts`

## pseudocode

```c
__int64 __fastcall ApplySettings::ProcessService(__int64 a1, __int64 a2)
{
  const OLECHAR *v4; // rdi
  OLECHAR *v5; // r14
  const wchar_t *v6; // rcx
  int v7; // eax
  unsigned int v8; // edi
  signed int v9; // eax
  char v10; // bl
  signed int v11; // eax
  const char *v12; // rsi
  int v13; // r8d
  int v14; // r9d
  int v15; // edx
  signed int LastError; // eax

  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 16);
  do
  {
    while ( 1 )
    {
      std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 48);
      if ( (unsigned __int8)std::operator==<unsigned short>(
                              a1 + 48,
                              L"=================================================") )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 72LL))(*(_QWORD *)(a1 + 8));
        if ( v8 )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v10 = LastError;
          }
          else
          {
            v10 = 5;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v12 = "g_pService->Apply";
            WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
            v15 = 39;
            goto LABEL_37;
          }
        }
        return v8;
      }
      std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 80);
      v4 = (const OLECHAR *)(a1 + 112);
      std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 112);
      if ( *(_QWORD *)(a1 + 136) >= 8u )
        v4 = *(const OLECHAR **)v4;
      v5 = SysAllocString(v4);
      v6 = *(_QWORD *)(a1 + 72) < 8u ? (const wchar_t *)(a1 + 48) : *(const wchar_t **)(a1 + 48);
      v7 = wcstol(v6, 0, 10) - 1027;
      if ( !v7 )
        break;
      if ( v7 == 1 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(**(_QWORD **)(a1 + 8) + 136LL))(*(_QWORD *)(a1 + 8), v5);
        SysFreeString(v5);
        if ( v8 )
        {
          v9 = GetLastError();
          v10 = v9;
          if ( v9 )
          {
            if ( v9 > 0 )
              v10 = v9;
          }
          else
          {
            v10 = 5;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v12 = "g_pService->put_AuthPorts";
            WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
            v15 = 38;
LABEL_37:
            WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v13, v14, (__int64)v12, v10);
            return v8;
          }
          return v8;
        }
      }
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(**(_QWORD **)(a1 + 8) + 152LL))(*(_QWORD *)(a1 + 8), v5);
    SysFreeString(v5);
  }
  while ( !v8 );
  v11 = GetLastError();
  v10 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v10 = v11;
  }
  else
  {
    v10 = 5;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v12 = "g_pService->put_AcctPorts";
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
    v15 = 37;
    goto LABEL_37;
  }
  return v8;
}

```

## disassembly

```asm
0x18004667c  push    rbx
0x18004667e  push    rbp
0x18004667f  push    rsi
0x180046680  push    rdi
0x180046681  push    r14
0x180046683  sub     rsp, 30h
0x180046687  mov     rbp, rdx
0x18004668a  mov     rbx, rcx
0x18004668d  lea     rdx, [rcx+10h]
0x180046691  mov     rcx, rbp
0x180046694  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180046699  lea     rsi, [rbx+30h]
0x18004669d  mov     rdx, rsi
0x1800466a0  mov     rcx, rbp
0x1800466a3  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800466a8  lea     rdx, asc_180066850; "======================================="...
0x1800466af  mov     rcx, rsi
0x1800466b2  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x1800466b7  test    al, al
0x1800466b9  jnz     loc_18004684F
0x1800466bf  lea     rdx, [rbx+50h]
0x1800466c3  mov     rcx, rbp
0x1800466c6  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800466cb  lea     rdi, [rbx+70h]
0x1800466cf  mov     rcx, rbp
0x1800466d2  mov     rdx, rdi
0x1800466d5  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800466da  cmp     qword ptr [rbx+88h], 8
0x1800466e2  jb      short loc_1800466E7
0x1800466e4  mov     rdi, [rdi]
0x1800466e7  mov     rcx, rdi; psz
0x1800466ea  call    cs:__imp_SysAllocString
0x1800466f0  cmp     qword ptr [rbx+48h], 8
0x1800466f5  mov     r14, rax
0x1800466f8  jb      short loc_1800466FF
0x1800466fa  mov     rcx, [rsi]
0x1800466fd  jmp     short loc_180046702
0x1800466ff  mov     rcx, rsi; String
0x180046702  xor     edx, edx; EndPtr
0x180046704  lea     r8d, [rdx+0Ah]; Radix
0x180046708  call    cs:__imp_wcstol
0x18004670e  sub     eax, 403h
0x180046713  jz      short loc_18004675C
0x180046715  cmp     eax, 1
0x180046718  jnz     short loc_18004669D
0x18004671a  mov     rcx, [rbx+8]
0x18004671e  mov     rdx, r14
0x180046721  mov     rax, [rcx]
0x180046724  mov     rax, [rax+88h]
0x18004672b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046730  mov     rcx, r14; bstrString
0x180046733  mov     edi, eax
0x180046735  call    cs:__imp_SysFreeString
0x18004673b  test    edi, edi
0x18004673d  jz      loc_18004669D
0x180046743  call    cs:__imp_GetLastError
0x180046749  mov     ebx, eax
0x18004674b  test    eax, eax
0x18004674d  jz      short loc_18004679E
0x18004674f  jle     short loc_1800467A3
0x180046751  movzx   ebx, ax
0x180046754  or      ebx, 80070000h
0x18004675a  jmp     short loc_1800467A3
0x18004675c  mov     rcx, [rbx+8]
0x180046760  mov     rdx, r14
0x180046763  mov     rax, [rcx]
0x180046766  mov     rax, [rax+98h]
0x18004676d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046772  mov     rcx, r14; bstrString
0x180046775  mov     edi, eax
0x180046777  call    cs:__imp_SysFreeString
0x18004677d  test    edi, edi
0x18004677f  jz      loc_18004669D
0x180046785  call    cs:__imp_GetLastError
0x18004678b  mov     ebx, eax
0x18004678d  test    eax, eax
0x18004678f  jz      short loc_1800467F8
0x180046791  jle     short loc_1800467FD
0x180046793  movzx   ebx, ax
0x180046796  or      ebx, 80070000h
0x18004679c  jmp     short loc_1800467FD
0x18004679e  mov     ebx, 80004005h
0x1800467a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800467aa  lea     rax, WPP_GLOBAL_Control
0x1800467b1  cmp     rcx, rax
0x1800467b4  jz      loc_1800468E0
0x1800467ba  cmp     byte ptr [rcx+19h], 2
0x1800467be  jb      loc_1800468E0
0x1800467c4  test    byte ptr [rcx+1Ch], 10h
0x1800467c8  jz      loc_1800468E0
0x1800467ce  lea     rsi, aGPservicePutAu; "g_pService->put_AuthPorts"
0x1800467d5  mov     r9d, ebx
0x1800467d8  mov     r8, rsi
0x1800467db  lea     rdx, aNpsds; "NPSDS"
0x1800467e2  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x1800467e9  call    WppDbgPrint
0x1800467ee  mov     edx, 26h ; '&'
0x1800467f3  jmp     loc_1800468C7
0x1800467f8  mov     ebx, 80004005h
0x1800467fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180046804  lea     rax, WPP_GLOBAL_Control
0x18004680b  cmp     rcx, rax
0x18004680e  jz      loc_1800468E0
0x180046814  cmp     byte ptr [rcx+19h], 2
0x180046818  jb      loc_1800468E0
0x18004681e  test    byte ptr [rcx+1Ch], 10h
0x180046822  jz      loc_1800468E0
0x180046828  lea     rsi, aGPservicePutAc; "g_pService->put_AcctPorts"
0x18004682f  mov     r9d, ebx
0x180046832  mov     r8, rsi
0x180046835  lea     rdx, aNpsds; "NPSDS"
0x18004683c  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180046843  call    WppDbgPrint
0x180046848  mov     edx, 25h ; '%'
0x18004684d  jmp     short loc_1800468C7
0x18004684f  mov     rcx, [rbx+8]
0x180046853  mov     rax, [rcx]
0x180046856  mov     rax, [rax+48h]
0x18004685a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004685f  mov     edi, eax
0x180046861  test    eax, eax
0x180046863  jz      short loc_1800468E0
0x180046865  call    cs:__imp_GetLastError
0x18004686b  mov     ebx, eax
0x18004686d  test    eax, eax
0x18004686f  jz      short loc_18004687E
0x180046871  jle     short loc_180046883
0x180046873  movzx   ebx, ax
0x180046876  or      ebx, 80070000h
0x18004687c  jmp     short loc_180046883
0x18004687e  mov     ebx, 80004005h
0x180046883  mov     rcx, cs:WPP_GLOBAL_Control
0x18004688a  lea     rax, WPP_GLOBAL_Control
0x180046891  cmp     rcx, rax
0x180046894  jz      short loc_1800468E0
0x180046896  cmp     byte ptr [rcx+19h], 2
0x18004689a  jb      short loc_1800468E0
0x18004689c  test    byte ptr [rcx+1Ch], 10h
0x1800468a0  jz      short loc_1800468E0
0x1800468a2  lea     rsi, aGPserviceApply; "g_pService->Apply"
0x1800468a9  mov     r9d, ebx
0x1800468ac  mov     r8, rsi
0x1800468af  lea     rdx, aNpsds; "NPSDS"
0x1800468b6  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x1800468bd  call    WppDbgPrint
0x1800468c2  mov     edx, 27h ; '''
0x1800468c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800468ce  mov     [rsp+58h+var_30], ebx
0x1800468d2  mov     [rsp+58h+var_38], rsi
0x1800468d7  mov     rcx, [rcx+10h]
0x1800468db  call    WPP_SF_ssd
0x1800468e0  mov     eax, edi
0x1800468e2  add     rsp, 30h
0x1800468e6  pop     r14
0x1800468e8  pop     rdi
0x1800468e9  pop     rsi
0x1800468ea  pop     rbp
0x1800468eb  pop     rbx
0x1800468ec  retn
```
