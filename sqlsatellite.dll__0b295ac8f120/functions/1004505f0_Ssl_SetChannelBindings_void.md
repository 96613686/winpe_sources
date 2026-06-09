# Ssl::SetChannelBindings(void)

- ea: `0x1004505f0`
- end: `0x100450877`
- name: `?SetChannelBindings@Ssl@@AEAAKXZ`
- size: `647`
- prototype: `unsigned int __fastcall(Ssl *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10044d800`
- `0x10044f860`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x1004505f0`
- `0x10045d370`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004506c0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004506c0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004507b9`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004507e3`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004507b9`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004507e3`
- `sqldk!SystemThread_TlsIndex` at `0x100450666`
- `sqldk!SystemThread_TlsOffset` at `0x10045066f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10045068a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10045068a`

## string_xrefs

- `0x10045060f`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Ssl::SetChannelBindings(Ssl *this, __int64 a2, __int64 a3, const wchar_t *a4)
{
  unsigned int v5; // ebx
  __int64 v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v10; // [rsp+20h] [rbp-48h]
  __int64 v11; // [rsp+28h] [rbp-40h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::SetChannelBindings", 4006, L"API|SNI\n");
  if ( Ssl::s_fChannelBindingsSupported )
  {
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v7 = *(_QWORD *)(v6 + 256);
    if ( !v7 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v7 = *(_QWORD *)(v6 + 256);
    }
    *(_QWORD *)(*((_QWORD *)this + 4) + 12824LL) = operator new(
                                                     0x10u,
                                                     *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v7 + 992) + 56LL) + 8LL),
                                                     1,
                                                     "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                                                     4031,
                                                     6u);
    if ( *(_QWORD *)(*((_QWORD *)this + 4) + 12824LL) )
    {
      v8 = ((__int64 (__fastcall *)(char *, __int64))Ssl::s_pfTable->QueryContextAttributesW)((char *)this + 392, 25);
      v5 = v8;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v10) = v8;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::SetChannelBindings",
          4063,
          L"SNIQueryContextAttributes for SECPKG_ATTR_UNIQUE_BINDINGS return value: %d{DWORD}\n",
          v10);
      }
      if ( v5 == -2146893054 )
      {
        Ssl::s_fChannelBindingsSupported = 0;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v10) = -2146893054;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
            "Ssl::SetChannelBindings",
            4072,
            L"SNIQueryContextAttributes for SECPKG_ATTR_UNIQUE_BINDINGS returned SEC_E_UNSUPPORTED_FUNCTION. Channel Bindi"
             "ngs are not available to protect against Authentication Relay.\n",
            v10);
        }
        scierrlog(0x65D1u);
        operator delete(*(void **)(*((_QWORD *)this + 4) + 12824LL), 0);
        *(_QWORD *)(*((_QWORD *)this + 4) + 12824LL) = 0;
        v5 = 0;
      }
      else if ( v5 )
      {
        operator delete(*(void **)(*((_QWORD *)this + 4) + 12824LL), 0);
        *(_QWORD *)(*((_QWORD *)this + 4) + 12824LL) = 0;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v10) = v5;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
            "Ssl::SetChannelBindings",
            4095,
            L"ERR|SNIQueryContextAttributes for SECPKG_ATTR_UNIQUE_BINDINGS return value: %d{DWORD}\n",
            v10);
        }
      }
    }
    else
    {
      v5 = 14;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v11) = 0;
        LODWORD(v10) = 6;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::SetChannelBindings",
          4036,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v10,
          v11,
          14);
      }
      SNISetLastError(6u, 0xEu, 0xC3B4u);
    }
  }
  else
  {
    v5 = 0;
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v10) = v5;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::SetChannelBindings",
      4102,
      L"RET|SNI%d{WINERR}\n",
      v10);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::SetChannelBindings", 4006, a4);
  return v5;
}

```

## disassembly

```asm
0x1004505f0  mov     rax, rsp
0x1004505f3  push    rdi
0x1004505f4  sub     rsp, 60h
0x1004505f8  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x100450600  mov     [rax+8], rbx
0x100450604  mov     [rax+10h], rbp
0x100450608  mov     [rax+18h], rsi
0x10045060c  mov     rdi, rcx
0x10045060f  lea     rsi, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x100450616  mov     [rax-20h], rsi
0x10045061a  lea     rbp, aSslSetchannelb; "Ssl::SetChannelBindings"
0x100450621  mov     [rax-18h], rbp
0x100450625  mov     dword ptr [rax-10h], 0FA6h
0x10045062c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100450633  jz      short loc_10045064D
0x100450635  lea     r9, aApiSni_0; "API|SNI\n"
0x10045063c  mov     r8d, 0FA6h; int
0x100450642  mov     rdx, rbp; char *
0x100450645  mov     rcx, rsi; char *
0x100450648  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10045064d  cmp     cs:?s_fChannelBindingsSupported@Ssl@@0_NA, 0; bool Ssl::s_fChannelBindingsSupported
0x100450654  jnz     short loc_10045065D
0x100450656  xor     ebx, ebx
0x100450658  jmp     loc_10045081D
0x10045065d  mov     rdx, gs:58h
0x100450666  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045066d  mov     ecx, [rax]
0x10045066f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100450676  mov     ebx, [rax]
0x100450678  add     rbx, [rdx+rcx*8]
0x10045067c  mov     rax, [rbx+100h]
0x100450683  test    rax, rax
0x100450686  jnz     short loc_100450697
0x100450688  xor     ecx, ecx
0x10045068a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100450690  mov     rax, [rbx+100h]
0x100450697  mov     rax, [rax+3E0h]
0x10045069e  mov     rcx, [rax+38h]
0x1004506a2  mov     byte ptr [rsp+68h+var_40], 6
0x1004506a7  mov     dword ptr [rsp+68h+var_48], 0FBFh
0x1004506af  mov     r9, rsi
0x1004506b2  mov     r8d, 1
0x1004506b8  mov     rdx, [rcx+8]
0x1004506bc  lea     ecx, [r8+0Fh]
0x1004506c0  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004506c6  mov     rcx, rax
0x1004506c9  mov     rax, [rdi+20h]
0x1004506cd  mov     [rax+3218h], rcx
0x1004506d4  mov     rax, [rdi+20h]
0x1004506d8  mov     r8, [rax+3218h]
0x1004506df  test    r8, r8
0x1004506e2  jnz     short loc_100450731
0x1004506e4  lea     ebx, [r8+0Eh]
0x1004506e8  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004506ef  jz      short loc_10045071A
0x1004506f1  mov     [rsp+68h+var_38], ebx
0x1004506f5  mov     dword ptr [rsp+68h+var_40], r8d
0x1004506fa  mov     dword ptr [rsp+68h+var_48], 6
0x100450702  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100450709  mov     r8d, 0FC4h; int
0x10045070f  mov     rdx, rbp; char *
0x100450712  mov     rcx, rsi; char *
0x100450715  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10045071a  mov     r8d, 0C3B4h
0x100450720  mov     edx, ebx
0x100450722  mov     ecx, 6
0x100450727  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10045072c  jmp     loc_10045081D
0x100450731  lea     rcx, [rdi+188h]
0x100450738  mov     edx, 19h
0x10045073d  mov     rax, cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x100450744  call    qword ptr [rax+58h]
0x100450747  mov     ebx, eax
0x100450749  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100450750  jz      short loc_10045076E
0x100450752  mov     dword ptr [rsp+68h+var_48], eax
0x100450756  lea     r9, aSniquerycontex; "SNIQueryContextAttributes for SECPKG_AT"...
0x10045075d  mov     r8d, 0FDFh; int
0x100450763  mov     rdx, rbp; char *
0x100450766  mov     rcx, rsi; char *
0x100450769  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10045076e  cmp     ebx, 80090302h
0x100450774  jnz     short loc_1004507D2
0x100450776  mov     cs:?s_fChannelBindingsSupported@Ssl@@0_NA, 0; bool Ssl::s_fChannelBindingsSupported
0x10045077d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100450784  jz      short loc_1004507A2
0x100450786  mov     dword ptr [rsp+68h+var_48], ebx
0x10045078a  lea     r9, aSniquerycontex_1; "SNIQueryContextAttributes for SECPKG_AT"...
0x100450791  mov     r8d, 0FE8h; int
0x100450797  mov     rdx, rbp; char *
0x10045079a  mov     rcx, rsi; char *
0x10045079d  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004507a2  mov     ecx, 65D1h; unsigned int
0x1004507a7  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1004507ac  mov     rax, [rdi+20h]
0x1004507b0  xor     edx, edx
0x1004507b2  mov     rcx, [rax+3218h]
0x1004507b9  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1004507bf  mov     rax, [rdi+20h]
0x1004507c3  mov     qword ptr [rax+3218h], 0
0x1004507ce  xor     ebx, ebx
0x1004507d0  jmp     short loc_10045081D
0x1004507d2  test    ebx, ebx
0x1004507d4  jz      short loc_10045081D
0x1004507d6  mov     rax, [rdi+20h]
0x1004507da  xor     edx, edx
0x1004507dc  mov     rcx, [rax+3218h]
0x1004507e3  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1004507e9  mov     rax, [rdi+20h]
0x1004507ed  mov     qword ptr [rax+3218h], 0
0x1004507f8  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004507ff  jz      short loc_10045081D
0x100450801  mov     dword ptr [rsp+68h+var_48], ebx
0x100450805  lea     r9, aErrSniquerycon_0; "ERR|SNIQueryContextAttributes for SECPK"...
0x10045080c  mov     r8d, 0FFFh; int
0x100450812  mov     rdx, rbp; char *
0x100450815  mov     rcx, rsi; char *
0x100450818  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10045081d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100450824  jz      short loc_100450843
0x100450826  mov     dword ptr [rsp+68h+var_48], ebx
0x10045082a  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100450831  mov     r8d, 1006h; int
0x100450837  mov     rdx, rbp; char *
0x10045083a  mov     rcx, rsi; char *
0x10045083d  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100450842  nop
0x100450843  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045084a  jz      short loc_10045085D
0x10045084c  mov     r8d, 0FA6h; int
0x100450852  mov     rdx, rbp; char *
0x100450855  mov     rcx, rsi; char *
0x100450858  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10045085d  mov     eax, ebx
0x10045085f  mov     rbx, [rsp+68h+arg_0]
0x100450864  mov     rbp, [rsp+68h+arg_8]
0x100450869  mov     rsi, [rsp+68h+arg_10]
0x100450871  add     rsp, 60h
0x100450875  pop     rdi
0x100450876  retn
```
