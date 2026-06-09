# SNI_Sec::SetPkgName(void)

- ea: `0x100429de0`
- end: `0x10042a061`
- name: `?SetPkgName@SNI_Sec@@AEAAKXZ`
- size: `641`
- prototype: `unsigned int __fastcall(SNI_Sec *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100441290`

## callees

- `0x100429de0`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100429edb`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100429edb`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100429f1b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100429f46`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100429f1b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100429f46`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100429e6a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100429fec`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100429e6a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100429fec`
- `sqldk!SystemThread_TlsIndex` at `0x100429e7d`
- `sqldk!SystemThread_TlsOffset` at `0x100429e86`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100429ea1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100429ea1`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x100429f33`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x100429f5f`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x100429f33`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x100429f5f`

## string_xrefs

- `0x100429e08`: `sql\common\dk\sni\src\sni_sspi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SNI_Sec::SetPkgName(SNI_Sec *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rax
  _OWORD *v5; // rax
  const wchar_t *v6; // r9
  unsigned int v7; // ebx
  const wchar_t *v8; // rsi
  __crt_locale_pointers *DefaultLocale; // rax
  __crt_locale_pointers *v10; // rax
  int v11; // eax
  int v12; // ecx
  __int64 v14; // [rsp+20h] [rbp-58h]
  __int64 v15; // [rsp+28h] [rbp-50h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\sni_sspi.cpp", "SNI_Sec::SetPkgName", 144, L"API|SNI\n");
  v2 = (_QWORD *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    ((void (__fastcall *)(_QWORD))g_pFuncs->FreeContextBuffer)(*v2);
    operator delete(*((void **)this + 5), 0x10u);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v5 = operator new(
         0x10u,
         *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v4 + 992) + 56LL) + 8LL),
         1,
         "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
         155,
         6u);
  *((_QWORD *)this + 5) = v5;
  if ( v5 )
  {
    *v5 = 0;
    v7 = ((__int64 (__fastcall *)(SNI_Sec *, __int64, _QWORD))g_pFuncs->QueryContextAttributesW)(
           this,
           12,
           *((_QWORD *)this + 5));
    if ( v7 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v14) = v7;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
          "SNI_Sec::SetPkgName",
          169,
          L"ERR|SNIdwRet: %d\n",
          v14);
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v15) = 0;
          LODWORD(v14) = 10;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
            "SNI_Sec::SetPkgName",
            170,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v14,
            v15,
            v7);
        }
      }
      SNISetLastError(0xAu, v7, 0xC3B4u);
      operator delete(*((void **)this + 5), 0x10u);
      *((_QWORD *)this + 5) = 0;
    }
    else
    {
      v8 = *(const wchar_t **)(**((_QWORD **)this + 5) + 16LL);
      DefaultLocale = GetDefaultLocale();
      if ( _wcsnicmp_l(L"NTLM", v8, 5u, DefaultLocale) )
      {
        v10 = GetDefaultLocale();
        v11 = _wcsnicmp_l(L"Kerberos", v8, 9u, v10);
        v12 = 8;
        if ( !v11 )
          v12 = 1;
        *((_DWORD *)this + 5) = v12;
      }
      else
      {
        *((_DWORD *)this + 5) = 0;
      }
    }
  }
  else
  {
    v7 = 14;
  }
  *((_DWORD *)this + 12) = v7;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v14) = v7;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
      "SNI_Sec::SetPkgName",
      183,
      L"RET|SNI%d{WINERR}\n",
      v14);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_sspi.cpp", "SNI_Sec::SetPkgName", 144, v6);
  return v7;
}

```

## disassembly

```asm
0x100429de0  mov     rax, rsp
0x100429de3  push    r12
0x100429de5  push    r14
0x100429de7  push    r15
0x100429de9  sub     rsp, 60h
0x100429ded  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x100429df5  mov     [rax+8], rbx
0x100429df9  mov     [rax+10h], rbp
0x100429dfd  mov     [rax+18h], rsi
0x100429e01  mov     [rax+20h], rdi
0x100429e05  mov     rdi, rcx
0x100429e08  lea     rbp, aSqlCommonDkSni_20; "sql\\common\\dk\\sni\\src\\sni_sspi.cpp"
0x100429e0f  mov     [rax-30h], rbp
0x100429e13  lea     r14, aSniSecSetpkgna; "SNI_Sec::SetPkgName"
0x100429e1a  mov     [rax-28h], r14
0x100429e1e  mov     dword ptr [rax-20h], 90h
0x100429e25  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100429e2c  jz      short loc_100429E46
0x100429e2e  lea     r9, aApiSni_0; "API|SNI\n"
0x100429e35  mov     r8d, 90h; int
0x100429e3b  mov     rdx, r14; char *
0x100429e3e  mov     rcx, rbp; char *
0x100429e41  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100429e46  mov     rcx, [rdi+28h]
0x100429e4a  xor     r15d, r15d
0x100429e4d  test    rcx, rcx
0x100429e50  jz      short loc_100429E74
0x100429e52  mov     rcx, [rcx]
0x100429e55  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100429e5c  call    qword ptr [rax+80h]
0x100429e62  lea     edx, [r15+10h]
0x100429e66  mov     rcx, [rdi+28h]
0x100429e6a  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100429e70  mov     [rdi+28h], r15
0x100429e74  mov     rdx, gs:58h
0x100429e7d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100429e84  mov     ecx, [rax]
0x100429e86  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100429e8d  mov     ebx, [rax]
0x100429e8f  add     rbx, [rdx+rcx*8]
0x100429e93  mov     rax, [rbx+100h]
0x100429e9a  test    rax, rax
0x100429e9d  jnz     short loc_100429EAE
0x100429e9f  xor     ecx, ecx
0x100429ea1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100429ea7  mov     rax, [rbx+100h]
0x100429eae  mov     rax, [rax+3E0h]
0x100429eb5  mov     rcx, [rax+38h]
0x100429eb9  mov     byte ptr [rsp+78h+var_50], 6
0x100429ebe  mov     dword ptr [rsp+78h+var_58], 9Bh
0x100429ec6  mov     r9, rbp
0x100429ec9  mov     r12d, 1
0x100429ecf  mov     r8d, r12d
0x100429ed2  mov     rdx, [rcx+8]
0x100429ed6  lea     ecx, [r12+0Fh]
0x100429edb  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100429ee1  mov     [rdi+28h], rax
0x100429ee5  test    rax, rax
0x100429ee8  jz      loc_100429FF8
0x100429eee  xorps   xmm0, xmm0
0x100429ef1  movups  xmmword ptr [rax], xmm0
0x100429ef4  mov     r8, [rdi+28h]
0x100429ef8  lea     edx, [r12+0Bh]
0x100429efd  mov     rcx, rdi
0x100429f00  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100429f07  call    qword ptr [rax+58h]
0x100429f0a  mov     ebx, eax
0x100429f0c  test    eax, eax
0x100429f0e  jnz     short loc_100429F78
0x100429f10  mov     rcx, [rdi+28h]
0x100429f14  mov     rdx, [rcx]
0x100429f17  mov     rsi, [rdx+10h]
0x100429f1b  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100429f21  mov     r9, rax; Locale
0x100429f24  lea     r8d, [r12+4]; MaxCount
0x100429f29  mov     rdx, rsi; String2
0x100429f2c  lea     rcx, aNtlm_0; "NTLM"
0x100429f33  call    cs:__imp__wcsnicmp_l
0x100429f39  test    eax, eax
0x100429f3b  jnz     short loc_100429F46
0x100429f3d  mov     [rdi+14h], r15d
0x100429f41  jmp     loc_100429FFD
0x100429f46  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100429f4c  mov     r9, rax; Locale
0x100429f4f  mov     r8d, 9; MaxCount
0x100429f55  mov     rdx, rsi; String2
0x100429f58  lea     rcx, aKerberos_0; "Kerberos"
0x100429f5f  call    cs:__imp__wcsnicmp_l
0x100429f65  mov     ecx, 8
0x100429f6a  test    eax, eax
0x100429f6c  cmovz   ecx, r12d
0x100429f70  mov     [rdi+14h], ecx
0x100429f73  jmp     loc_100429FFD
0x100429f78  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100429f7e  test    al, 2
0x100429f80  jz      short loc_100429FD1
0x100429f82  mov     dword ptr [rsp+78h+var_58], ebx
0x100429f86  lea     r9, aErrSnidwretD; "ERR|SNIdwRet: %d\n"
0x100429f8d  mov     r8d, 0A9h; int
0x100429f93  mov     rdx, r14; char *
0x100429f96  mov     rcx, rbp; char *
0x100429f99  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100429f9e  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100429fa4  test    al, 2
0x100429fa6  jz      short loc_100429FD1
0x100429fa8  mov     [rsp+78h+var_48], ebx
0x100429fac  mov     dword ptr [rsp+78h+var_50], r15d
0x100429fb1  mov     dword ptr [rsp+78h+var_58], 0Ah
0x100429fb9  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100429fc0  mov     r8d, 0AAh; int
0x100429fc6  mov     rdx, r14; char *
0x100429fc9  mov     rcx, rbp; char *
0x100429fcc  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100429fd1  mov     r8d, 0C3B4h
0x100429fd7  mov     edx, ebx
0x100429fd9  mov     ecx, 0Ah
0x100429fde  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100429fe3  mov     edx, 10h
0x100429fe8  mov     rcx, [rdi+28h]
0x100429fec  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100429ff2  mov     [rdi+28h], r15
0x100429ff6  jmp     short loc_100429FFD
0x100429ff8  mov     ebx, 0Eh
0x100429ffd  mov     [rdi+30h], ebx
0x10042a000  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, r12b; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042a007  jz      short loc_10042A026
0x10042a009  mov     dword ptr [rsp+78h+var_58], ebx
0x10042a00d  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10042a014  mov     r8d, 0B7h; int
0x10042a01a  mov     rdx, r14; char *
0x10042a01d  mov     rcx, rbp; char *
0x10042a020  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10042a025  nop
0x10042a026  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042a02d  jz      short loc_10042A040
0x10042a02f  mov     r8d, 90h; int
0x10042a035  mov     rdx, r14; char *
0x10042a038  mov     rcx, rbp; char *
0x10042a03b  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10042a040  mov     eax, ebx
0x10042a042  lea     r11, [rsp+78h+var_18]
0x10042a047  mov     rbx, [r11+20h]
0x10042a04b  mov     rbp, [r11+28h]
0x10042a04f  mov     rsi, [r11+30h]
0x10042a053  mov     rdi, [r11+38h]
0x10042a057  mov     rsp, r11
0x10042a05a  pop     r15
0x10042a05c  pop     r14
0x10042a05e  pop     r12
0x10042a060  retn
```
