# SNI_ServiceBindings::MatchSPN(wchar_t *,SNIAuthErrStates *)

- ea: `0x100449d20`
- end: `0x10044a090`
- name: `?MatchSPN@SNI_ServiceBindings@@SAKPEA_WPEAW4SNIAuthErrStates@@@Z`
- size: `880`
- prototype: `unsigned int __fastcall(wchar_t *Src, enum SNIAuthErrStates *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x10043eae0`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x100449d20`
- `0x10044aac0`
- `0x10044ac40`
- `0x100486250`

## import_xrefs

- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100449de5`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100449f40`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100449de5`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100449f40`
- `sqldk!??_V@YAXPEAX@Z` at `0x100449fef`
- `sqldk!??_V@YAXPEAX@Z` at `0x100449fef`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100449eeb`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100449eeb`
- `sqldk!SystemThread_TlsIndex` at `0x100449e83`
- `sqldk!SystemThread_TlsOffset` at `0x100449e8c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100449ea7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100449ea7`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x100449f59`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x100449f59`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100449dfe`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100449dfe`

## string_xrefs

- `0x100449d4a`: `sql\common\dk\sni\src\SNI_ServiceBindings.cpp`
- `0x100449d55`: `SNI_ServiceBindings::MatchSPN`
- `0x100449d9b`: `SNI_ServiceBindings::MatchWhitelist`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SNI_ServiceBindings::MatchSPN(
        wchar_t *Src,
        enum SNIAuthErrStates *a2,
        __int64 a3,
        const wchar_t *a4)
{
  unsigned int v6; // edi
  int v7; // ebx
  __crt_locale_pointers *DefaultLocale; // rax
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  char *v14; // rax
  char *v15; // rbp
  __crt_locale_pointers *v16; // rax
  char *v17; // rcx
  enum SNIAuthErrStates *v18; // rdx
  WCHAR *v19; // rcx
  unsigned int matched; // eax
  bool v22; // zf
  __int64 v23; // [rsp+20h] [rbp-78h]
  __int64 v24; // [rsp+28h] [rbp-70h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_ServiceBindings.cpp",
      "SNI_ServiceBindings::MatchSPN",
      200,
      L"API|SNIwszClientSuppliedSPN: %p{LPWSTR}, pSSPIFailureState: %p{SNIAuthErrStates*}\n",
      Src,
      a2,
      -2,
      "sql\\common\\dk\\sni\\src\\SNI_ServiceBindings.cpp",
      "SNI_ServiceBindings::MatchSPN",
      200);
  *(_DWORD *)a2 = 0;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_ServiceBindings.cpp",
      "SNI_ServiceBindings::MatchWhitelist",
      1665,
      L"API|SNIwszSPN: %p{LPWSTR}\n",
      Src);
  v6 = -2146892986;
  v7 = 0;
  if ( SNI_ServiceBindings::s_dwcSPN )
  {
    while ( 1 )
    {
      DefaultLocale = GetDefaultLocale();
      if ( !_wcsicmp_l(SNI_ServiceBindings::s_pwszSPN[v7], Src, DefaultLocale) )
        break;
      if ( ++v7 >= SNI_ServiceBindings::s_dwcSPN )
        goto LABEL_10;
    }
    v6 = 0;
  }
LABEL_10:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v23) = v6;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_ServiceBindings.cpp",
      "SNI_ServiceBindings::MatchWhitelist",
      1678,
      L"RET|SNI%d{WINERR}\n",
      v23);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_ServiceBindings.cpp",
      "SNI_ServiceBindings::MatchWhitelist",
      1665,
      a4);
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( Src[v9] );
    v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v11 = *(_QWORD *)(v10 + 256);
    if ( !v11 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v11 = *(_QWORD *)(v10 + 256);
    }
    v12 = *(_QWORD *)(*(_QWORD *)(v11 + 992) + 56LL);
    v13 = 2LL * (unsigned int)(v9 + 1);
    if ( !is_mul_ok((unsigned int)(v9 + 1), 2u) )
      v13 = -1;
    v14 = (char *)operator new[](
                    v13,
                    *(struct IMemObj **)(v12 + 8),
                    1,
                    "sql\\common\\dk\\sni\\src\\SNI_ServiceBindings.cpp",
                    226,
                    6u);
    v15 = v14;
    if ( !v14 )
    {
      v6 = 14;
      *(_DWORD *)a2 = 56;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v23) = 14;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_ServiceBindings.cpp",
          "SNI_ServiceBindings::MatchSPN",
          231,
          L"ERR|SNI%d{WINERR}\n",
          v23);
      }
      goto LABEL_35;
    }
    memmove(v14, Src, 2LL * (unsigned int)(v9 + 1));
    v16 = GetDefaultLocale();
    if ( _wcsnicmp_l(L"MSSQLSVC/", (const wchar_t *)v15, 9u, v16) )
    {
      *(_DWORD *)a2 = 53;
      v6 = -2146892986;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v23) = -2146892986;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_ServiceBindings.cpp",
          "SNI_ServiceBindings::MatchSPN",
          246,
          L"ERR|SNI%d{WINERR}\n",
          v23);
      }
      goto LABEL_34;
    }
    v17 = &v15[2 * (unsigned int)v9 - 2];
    if ( v17 < v15 + 18 )
    {
LABEL_31:
      v18 = a2;
      v19 = (WCHAR *)(v15 + 18);
    }
    else
    {
      while ( *(_WORD *)v17 != 58 )
      {
        if ( *(_WORD *)v17 == 93 )
        {
          *((_WORD *)v17 + 1) = 0;
          matched = SNI_ServiceBindings::MatchIPv6Address((LPWSTR)v15 + 9, a2);
          goto LABEL_33;
        }
        v17 -= 2;
        if ( v17 < v15 + 18 )
          goto LABEL_31;
      }
      *(_WORD *)v17 = 0;
      v22 = *((_WORD *)v17 - 1) == 93;
      v18 = a2;
      v19 = (WCHAR *)(v15 + 18);
      if ( v22 )
      {
        matched = SNI_ServiceBindings::MatchIPv6Address(v19, a2);
        goto LABEL_33;
      }
    }
    matched = SNI_ServiceBindings::MatchHostOrIPv4Address(v19, v18);
LABEL_33:
    v6 = matched;
LABEL_34:
    operator delete[](v15);
  }
LABEL_35:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v24) = *(_DWORD *)a2;
    LODWORD(v23) = v6;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_ServiceBindings.cpp",
      "SNI_ServiceBindings::MatchSPN",
      310,
      L"RET|SNI%d{WINERR}, %d{SNIAuthErrStates}\n",
      v23,
      v24);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_ServiceBindings.cpp", "SNI_ServiceBindings::MatchSPN", 200, a4);
  return v6;
}

```

## disassembly

```asm
0x100449d20  mov     rax, rsp
0x100449d23  push    rdi
0x100449d24  push    r12
0x100449d26  push    r13
0x100449d28  push    r14
0x100449d2a  push    r15
0x100449d2c  sub     rsp, 70h
0x100449d30  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x100449d38  mov     [rax+8], rbx
0x100449d3c  mov     [rax+10h], rbp
0x100449d40  mov     [rax+18h], rsi
0x100449d44  mov     r14, rdx
0x100449d47  mov     rsi, rcx
0x100449d4a  lea     r15, aSqlCommonDkSni_0; "sql\\common\\dk\\sni\\src\\SNI_ServiceB"...
0x100449d51  mov     [rax-60h], r15
0x100449d55  lea     r12, aSniServicebind_0; "SNI_ServiceBindings::MatchSPN"
0x100449d5c  mov     [rax-58h], r12
0x100449d60  mov     dword ptr [rax-50h], 0C8h
0x100449d67  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100449d6e  jz      short loc_100449D90
0x100449d70  mov     [rax-70h], rdx
0x100449d74  mov     [rax-78h], rcx
0x100449d78  lea     r9, aApiSniwszclien; "API|SNIwszClientSuppliedSPN: %p{LPWSTR}"...
0x100449d7f  mov     r8d, 0C8h; int
0x100449d85  mov     rdx, r12; char *
0x100449d88  mov     rcx, r15; char *
0x100449d8b  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100449d90  xor     r13d, r13d
0x100449d93  mov     [r14], r13d
0x100449d96  mov     [rsp+98h+var_48], r15
0x100449d9b  lea     rbp, aSniServicebind_6; "SNI_ServiceBindings::MatchWhitelist"
0x100449da2  mov     [rsp+98h+var_40], rbp
0x100449da7  mov     [rsp+98h+var_38], 681h
0x100449daf  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100449db6  jz      short loc_100449DD5
0x100449db8  mov     [rsp+98h+var_78], rsi
0x100449dbd  lea     r9, aApiSniwszspnPL; "API|SNIwszSPN: %p{LPWSTR}\n"
0x100449dc4  mov     r8d, 681h; int
0x100449dca  mov     rdx, rbp; char *
0x100449dcd  mov     rcx, r15; char *
0x100449dd0  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100449dd5  mov     edi, 80090346h
0x100449dda  mov     ebx, r13d
0x100449ddd  cmp     cs:?s_dwcSPN@SNI_ServiceBindings@@0KA, ebx; ulong SNI_ServiceBindings::s_dwcSPN
0x100449de3  jbe     short loc_100449E17
0x100449de5  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100449deb  mov     r8, rax; Locale
0x100449dee  mov     eax, ebx
0x100449df0  mov     rdx, rsi; String2
0x100449df3  mov     rcx, cs:?s_pwszSPN@SNI_ServiceBindings@@0PEAPEA_WEA; wchar_t * * SNI_ServiceBindings::s_pwszSPN
0x100449dfa  mov     rcx, [rcx+rax*8]; String1
0x100449dfe  call    cs:__imp__wcsicmp_l
0x100449e04  test    eax, eax
0x100449e06  jz      short loc_100449E14
0x100449e08  inc     ebx
0x100449e0a  cmp     ebx, cs:?s_dwcSPN@SNI_ServiceBindings@@0KA; ulong SNI_ServiceBindings::s_dwcSPN
0x100449e10  jb      short loc_100449DE5
0x100449e12  jmp     short loc_100449E17
0x100449e14  mov     edi, r13d
0x100449e17  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100449e1e  jz      short loc_100449E3D
0x100449e20  mov     dword ptr [rsp+98h+var_78], edi
0x100449e24  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100449e2b  mov     r8d, 68Eh; int
0x100449e31  mov     rdx, rbp; char *
0x100449e34  mov     rcx, r15; char *
0x100449e37  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100449e3c  nop
0x100449e3d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100449e44  jz      short loc_100449E57
0x100449e46  mov     r8d, 681h; int
0x100449e4c  mov     rdx, rbp; char *
0x100449e4f  mov     rcx, r15; char *
0x100449e52  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100449e57  test    edi, edi
0x100449e59  jz      loc_100449FF5
0x100449e5f  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x100449e66  mov     rbx, rbp
0x100449e69  nop     dword ptr [rax+00000000h]
0x100449e70  inc     rbx
0x100449e73  cmp     word ptr [rsi+rbx*2], 0
0x100449e78  jnz     short loc_100449E70
0x100449e7a  mov     rdx, gs:58h
0x100449e83  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100449e8a  mov     ecx, [rax]
0x100449e8c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100449e93  mov     edi, [rax]
0x100449e95  add     rdi, [rdx+rcx*8]
0x100449e99  mov     rax, [rdi+100h]
0x100449ea0  test    rax, rax
0x100449ea3  jnz     short loc_100449EB4
0x100449ea5  xor     ecx, ecx
0x100449ea7  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100449ead  mov     rax, [rdi+100h]
0x100449eb4  mov     rax, [rax+3E0h]
0x100449ebb  mov     rcx, [rax+38h]
0x100449ebf  lea     edi, [rbx+1]
0x100449ec2  mov     eax, 2
0x100449ec7  mul     rdi
0x100449eca  cmovo   rax, rbp
0x100449ece  mov     byte ptr [rsp+98h+var_70], 6
0x100449ed3  mov     dword ptr [rsp+98h+var_78], 0E2h
0x100449edb  mov     r9, r15
0x100449ede  mov     r8d, 1
0x100449ee4  mov     rdx, [rcx+8]
0x100449ee8  mov     rcx, rax
0x100449eeb  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100449ef1  mov     rbp, rax
0x100449ef4  test    rax, rax
0x100449ef7  jnz     short loc_100449F31
0x100449ef9  lea     edi, [rax+0Eh]
0x100449efc  mov     dword ptr [r14], 38h ; '8'
0x100449f03  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100449f0a  jz      loc_100449FF5
0x100449f10  mov     dword ptr [rsp+98h+var_78], edi
0x100449f14  lea     r9, aErrSniDWinerr; "ERR|SNI%d{WINERR}\n"
0x100449f1b  mov     r8d, 0E7h; int
0x100449f21  mov     rdx, r12; char *
0x100449f24  mov     rcx, r15; char *
0x100449f27  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100449f2c  jmp     loc_100449FF5
0x100449f31  lea     r8, [rdi+rdi]; Size
0x100449f35  mov     rdx, rsi; Src
0x100449f38  mov     rcx, rbp; void *
0x100449f3b  call    memmove
0x100449f40  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100449f46  mov     r9, rax; Locale
0x100449f49  mov     r8d, 9; MaxCount
0x100449f4f  mov     rdx, rbp; String2
0x100449f52  lea     rcx, aMssqlsvc; "MSSQLSVC/"
0x100449f59  call    cs:__imp__wcsnicmp_l
0x100449f5f  test    eax, eax
0x100449f61  jz      short loc_100449F96
0x100449f63  mov     dword ptr [r14], 35h ; '5'
0x100449f6a  mov     edi, 80090346h
0x100449f6f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100449f76  jz      short loc_100449FEC
0x100449f78  mov     dword ptr [rsp+98h+var_78], edi
0x100449f7c  lea     r9, aErrSniDWinerr; "ERR|SNI%d{WINERR}\n"
0x100449f83  mov     r8d, 0F6h; int
0x100449f89  mov     rdx, r12; char *
0x100449f8c  mov     rcx, r15; char *
0x100449f8f  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100449f94  jmp     short loc_100449FEC
0x100449f96  mov     eax, ebx
0x100449f98  lea     rcx, [rbp-2]
0x100449f9c  lea     rcx, [rcx+rax*2]
0x100449fa0  lea     r8, [rbp+12h]
0x100449fa4  cmp     rcx, r8
0x100449fa7  jb      short loc_100449FDF
0x100449fa9  mov     edx, 5Dh ; ']'
0x100449fae  mov     r9d, 3Ah ; ':'
0x100449fb4  nop     dword ptr [rax+00h]
0x100449fb8  nop     dword ptr [rax+rax+00000000h]
0x100449fc0  movzx   eax, word ptr [rcx]
0x100449fc3  cmp     r9w, ax
0x100449fc7  jz      loc_10044A071
0x100449fcd  cmp     dx, ax
0x100449fd0  jz      loc_10044A05C
0x100449fd6  sub     rcx, 2
0x100449fda  cmp     rcx, r8
0x100449fdd  jnb     short loc_100449FC0
0x100449fdf  mov     rdx, r14; enum SNIAuthErrStates *
0x100449fe2  mov     rcx, r8; String2
0x100449fe5  call    ?MatchHostOrIPv4Address@SNI_ServiceBindings@@CAKPEA_WPEAW4SNIAuthErrStates@@@Z; SNI_ServiceBindings::MatchHostOrIPv4Address(wchar_t *,SNIAuthErrStates *)
0x100449fea  mov     edi, eax
0x100449fec  mov     rcx, rbp
0x100449fef  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100449ff5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100449ffc  jz      short loc_10044A022
0x100449ffe  mov     eax, [r14]
0x10044a001  mov     dword ptr [rsp+98h+var_70], eax
0x10044a005  mov     dword ptr [rsp+98h+var_78], edi
0x10044a009  lea     r9, aRetSniDWinerrD; "RET|SNI%d{WINERR}, %d{SNIAuthErrStates}"...
0x10044a010  mov     r8d, 136h; int
0x10044a016  mov     rdx, r12; char *
0x10044a019  mov     rcx, r15; char *
0x10044a01c  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044a021  nop
0x10044a022  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044a029  jz      short loc_10044A03C
0x10044a02b  mov     r8d, 0C8h; int
0x10044a031  mov     rdx, r12; char *
0x10044a034  mov     rcx, r15; char *
0x10044a037  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10044a03c  mov     eax, edi
0x10044a03e  lea     r11, [rsp+98h+var_28]
0x10044a043  mov     rbx, [r11+30h]
0x10044a047  mov     rbp, [r11+38h]
0x10044a04b  mov     rsi, [r11+40h]
0x10044a04f  mov     rsp, r11
0x10044a052  pop     r15
0x10044a054  pop     r14
0x10044a056  pop     r13
0x10044a058  pop     r12
0x10044a05a  pop     rdi
0x10044a05b  retn
0x10044a05c  mov     [rcx+2], r13w
0x10044a061  mov     rdx, r14; enum SNIAuthErrStates *
0x10044a064  mov     rcx, r8; AddressString
0x10044a067  call    ?MatchIPv6Address@SNI_ServiceBindings@@CAKPEA_WPEAW4SNIAuthErrStates@@@Z; SNI_ServiceBindings::MatchIPv6Address(wchar_t *,SNIAuthErrStates *)
0x10044a06c  jmp     loc_100449FEA
0x10044a071  mov     [rcx], r13w
0x10044a075  cmp     dx, [rcx-2]
0x10044a079  mov     rdx, r14; enum SNIAuthErrStates *
0x10044a07c  mov     rcx, r8; AddressString
0x10044a07f  jnz     loc_100449FE5
0x10044a085  call    ?MatchIPv6Address@SNI_ServiceBindings@@CAKPEA_WPEAW4SNIAuthErrStates@@@Z; SNI_ServiceBindings::MatchIPv6Address(wchar_t *,SNIAuthErrStates *)
0x10044a08a  jmp     loc_100449FEA
```
