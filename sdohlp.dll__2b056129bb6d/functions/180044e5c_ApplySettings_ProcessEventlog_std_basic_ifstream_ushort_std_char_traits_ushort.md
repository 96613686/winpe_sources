# ApplySettings::ProcessEventlog(std::basic_ifstream<ushort,std::char_traits<ushort>> &)

- ea: `0x180044e5c`
- end: `0x1800450d0`
- name: `?ProcessEventlog@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z`
- size: `628`
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
- `0x180044e5c`
- `0x1800471b4`
- `0x180058010`

## import_xrefs

- `msvcrt!wcstol` at `0x180044ed1`
- `msvcrt!wcstol` at `0x180044ed1`
- `KERNEL32!GetLastError` at `0x180044f18`
- `KERNEL32!GetLastError` at `0x180044f66`
- `KERNEL32!GetLastError` at `0x180045046`
- `KERNEL32!GetLastError` at `0x180044f18`
- `KERNEL32!GetLastError` at `0x180044f66`
- `KERNEL32!GetLastError` at `0x180045046`

## string_xrefs

- `0x180044fc3`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x18004501d`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180045097`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180045009`: `g_pService->put_LogRejectedRequests`
- `0x180044faf`: `g_pService->put_LogSuccessfulRequests`
- `0x180045083`: `g_pService->Apply`

## pseudocode

```c
__int64 __fastcall ApplySettings::ProcessEventlog(__int64 a1, __int64 a2)
{
  const wchar_t *v4; // rcx
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD); // rbx
  unsigned __int8 v8; // al
  unsigned int v9; // edi
  signed int v10; // eax
  char v11; // bl
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD); // rbx
  unsigned __int8 v14; // al
  signed int v15; // eax
  const char *v16; // rsi
  int v17; // r8d
  int v18; // r9d
  int v19; // edx
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
        v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 72LL))(*(_QWORD *)(a1 + 8));
        if ( v9 )
        {
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v11 = LastError;
          }
          else
          {
            v11 = 5;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v16 = "g_pService->Apply";
            WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
            v19 = 29;
            goto LABEL_35;
          }
        }
        return v9;
      }
      std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 80);
      std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 112);
      v4 = *(_QWORD *)(a1 + 72) < 8u ? (const wchar_t *)(a1 + 48) : *(const wchar_t **)(a1 + 48);
      v5 = wcstol(v4, 0, 10) - 1027;
      if ( !v5 )
        break;
      if ( v5 == 1 )
      {
        v6 = *(_QWORD *)(a1 + 8);
        v7 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 168LL);
        v8 = std::operator==<unsigned short>(a1 + 112, L"-1");
        v9 = v7(v6, v8);
        if ( v9 )
        {
          v10 = GetLastError();
          v11 = v10;
          if ( v10 )
          {
            if ( v10 > 0 )
              v11 = v10;
          }
          else
          {
            v11 = 5;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v16 = "g_pService->put_LogSuccessfulRequests";
            WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
            v19 = 28;
LABEL_35:
            WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v17, v18, (__int64)v16, v11);
            return v9;
          }
          return v9;
        }
      }
    }
    v12 = *(_QWORD *)(a1 + 8);
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 184LL);
    v14 = std::operator==<unsigned short>(a1 + 112, L"-1");
    v9 = v13(v12, v14);
  }
  while ( !v9 );
  v15 = GetLastError();
  v11 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v11 = v15;
  }
  else
  {
    v11 = 5;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v16 = "g_pService->put_LogRejectedRequests";
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
    v19 = 27;
    goto LABEL_35;
  }
  return v9;
}

```

## disassembly

```asm
0x180044e5c  push    rbx
0x180044e5e  push    rbp
0x180044e5f  push    rsi
0x180044e60  push    rdi
0x180044e61  push    r14
0x180044e63  push    r15
0x180044e65  sub     rsp, 38h
0x180044e69  mov     rbp, rdx
0x180044e6c  mov     rsi, rcx
0x180044e6f  lea     rdx, [rcx+10h]
0x180044e73  mov     rcx, rbp
0x180044e76  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180044e7b  lea     r14, [rsi+30h]
0x180044e7f  mov     rdx, r14
0x180044e82  mov     rcx, rbp
0x180044e85  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180044e8a  lea     rdx, asc_180066850; "======================================="...
0x180044e91  mov     rcx, r14
0x180044e94  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180044e99  test    al, al
0x180044e9b  jnz     loc_180045030
0x180044ea1  lea     rdx, [rsi+50h]
0x180044ea5  mov     rcx, rbp
0x180044ea8  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180044ead  lea     r15, [rsi+70h]
0x180044eb1  mov     rcx, rbp
0x180044eb4  mov     rdx, r15
0x180044eb7  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180044ebc  cmp     qword ptr [rsi+48h], 8
0x180044ec1  jb      short loc_180044EC8
0x180044ec3  mov     rcx, [r14]
0x180044ec6  jmp     short loc_180044ECB
0x180044ec8  mov     rcx, r14; String
0x180044ecb  xor     edx, edx; EndPtr
0x180044ecd  lea     r8d, [rdx+0Ah]; Radix
0x180044ed1  call    cs:__imp_wcstol
0x180044ed7  sub     eax, 403h
0x180044edc  jz      short loc_180044F31
0x180044ede  cmp     eax, 1
0x180044ee1  jnz     short loc_180044E7F
0x180044ee3  mov     rdi, [rsi+8]
0x180044ee7  lea     rdx, a1; "-1"
0x180044eee  mov     rcx, r15
0x180044ef1  mov     rax, [rdi]
0x180044ef4  mov     rbx, [rax+0A8h]
0x180044efb  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180044f00  movzx   edx, al
0x180044f03  mov     rcx, rdi
0x180044f06  mov     rax, rbx
0x180044f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f0e  mov     edi, eax
0x180044f10  test    eax, eax
0x180044f12  jz      loc_180044E7F
0x180044f18  call    cs:__imp_GetLastError
0x180044f1e  mov     ebx, eax
0x180044f20  test    eax, eax
0x180044f22  jz      short loc_180044F7F
0x180044f24  jle     short loc_180044F84
0x180044f26  movzx   ebx, ax
0x180044f29  or      ebx, 80070000h
0x180044f2f  jmp     short loc_180044F84
0x180044f31  mov     rdi, [rsi+8]
0x180044f35  lea     rdx, a1; "-1"
0x180044f3c  mov     rcx, r15
0x180044f3f  mov     rax, [rdi]
0x180044f42  mov     rbx, [rax+0B8h]
0x180044f49  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180044f4e  movzx   edx, al
0x180044f51  mov     rcx, rdi
0x180044f54  mov     rax, rbx
0x180044f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f5c  mov     edi, eax
0x180044f5e  test    eax, eax
0x180044f60  jz      loc_180044E7F
0x180044f66  call    cs:__imp_GetLastError
0x180044f6c  mov     ebx, eax
0x180044f6e  test    eax, eax
0x180044f70  jz      short loc_180044FD9
0x180044f72  jle     short loc_180044FDE
0x180044f74  movzx   ebx, ax
0x180044f77  or      ebx, 80070000h
0x180044f7d  jmp     short loc_180044FDE
0x180044f7f  mov     ebx, 80004005h
0x180044f84  mov     rcx, cs:WPP_GLOBAL_Control
0x180044f8b  lea     rax, WPP_GLOBAL_Control
0x180044f92  cmp     rcx, rax
0x180044f95  jz      loc_1800450C1
0x180044f9b  cmp     byte ptr [rcx+19h], 2
0x180044f9f  jb      loc_1800450C1
0x180044fa5  test    byte ptr [rcx+1Ch], 10h
0x180044fa9  jz      loc_1800450C1
0x180044faf  lea     rsi, aGPservicePutLo_0; "g_pService->put_LogSuccessfulRequests"
0x180044fb6  mov     r9d, ebx
0x180044fb9  mov     r8, rsi
0x180044fbc  lea     rdx, aNpsds; "NPSDS"
0x180044fc3  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180044fca  call    WppDbgPrint
0x180044fcf  mov     edx, 1Ch
0x180044fd4  jmp     loc_1800450A8
0x180044fd9  mov     ebx, 80004005h
0x180044fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180044fe5  lea     rax, WPP_GLOBAL_Control
0x180044fec  cmp     rcx, rax
0x180044fef  jz      loc_1800450C1
0x180044ff5  cmp     byte ptr [rcx+19h], 2
0x180044ff9  jb      loc_1800450C1
0x180044fff  test    byte ptr [rcx+1Ch], 10h
0x180045003  jz      loc_1800450C1
0x180045009  lea     rsi, aGPservicePutLo; "g_pService->put_LogRejectedRequests"
0x180045010  mov     r9d, ebx
0x180045013  mov     r8, rsi
0x180045016  lea     rdx, aNpsds; "NPSDS"
0x18004501d  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180045024  call    WppDbgPrint
0x180045029  mov     edx, 1Bh
0x18004502e  jmp     short loc_1800450A8
0x180045030  mov     rcx, [rsi+8]
0x180045034  mov     rax, [rcx]
0x180045037  mov     rax, [rax+48h]
0x18004503b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045040  mov     edi, eax
0x180045042  test    eax, eax
0x180045044  jz      short loc_1800450C1
0x180045046  call    cs:__imp_GetLastError
0x18004504c  mov     ebx, eax
0x18004504e  test    eax, eax
0x180045050  jz      short loc_18004505F
0x180045052  jle     short loc_180045064
0x180045054  movzx   ebx, ax
0x180045057  or      ebx, 80070000h
0x18004505d  jmp     short loc_180045064
0x18004505f  mov     ebx, 80004005h
0x180045064  mov     rcx, cs:WPP_GLOBAL_Control
0x18004506b  lea     rax, WPP_GLOBAL_Control
0x180045072  cmp     rcx, rax
0x180045075  jz      short loc_1800450C1
0x180045077  cmp     byte ptr [rcx+19h], 2
0x18004507b  jb      short loc_1800450C1
0x18004507d  test    byte ptr [rcx+1Ch], 10h
0x180045081  jz      short loc_1800450C1
0x180045083  lea     rsi, aGPserviceApply; "g_pService->Apply"
0x18004508a  mov     r9d, ebx
0x18004508d  mov     r8, rsi
0x180045090  lea     rdx, aNpsds; "NPSDS"
0x180045097  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18004509e  call    WppDbgPrint
0x1800450a3  mov     edx, 1Dh
0x1800450a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800450af  mov     [rsp+68h+var_40], ebx
0x1800450b3  mov     [rsp+68h+var_48], rsi
0x1800450b8  mov     rcx, [rcx+10h]
0x1800450bc  call    WPP_SF_ssd
0x1800450c1  mov     eax, edi
0x1800450c3  add     rsp, 38h
0x1800450c7  pop     r15
0x1800450c9  pop     r14
0x1800450cb  pop     rdi
0x1800450cc  pop     rsi
0x1800450cd  pop     rbp
0x1800450ce  pop     rbx
0x1800450cf  retn
```
