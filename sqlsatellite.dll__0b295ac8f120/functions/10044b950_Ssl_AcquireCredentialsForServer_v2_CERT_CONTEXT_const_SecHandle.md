# Ssl::AcquireCredentialsForServer_v2(_CERT_CONTEXT const *,_SecHandle * *)

- ea: `0x10044b950`
- end: `0x10044bbe9`
- name: `?AcquireCredentialsForServer_v2@Ssl@@SAKPEBU_CERT_CONTEXT@@PEAPEAU_SecHandle@@@Z`
- size: `665`
- prototype: `unsigned int __fastcall(const struct _CERT_CONTEXT *, struct _SecHandle **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10044cff0`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x10044b950`
- `0x10045d370`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044ba80`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044ba80`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044bb86`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044bb86`
- `sqldk!SystemThread_TlsIndex` at `0x10044ba26`
- `sqldk!SystemThread_TlsOffset` at `0x10044ba2f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044ba4a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044ba4a`

## string_xrefs

- `0x10044b976`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044bac3`: `Microsoft Unified Security Protocol Provider`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Ssl::AcquireCredentialsForServer_v2(const struct _CERT_CONTEXT *a1, struct _SecHandle **a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  struct _SecHandle *v5; // rax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  const wchar_t *v8; // r9
  _QWORD *v10; // [rsp+20h] [rbp-B8h]
  __int64 v11; // [rsp+28h] [rbp-B0h]
  __int64 v12; // [rsp+30h] [rbp-A8h]
  _QWORD v13[4]; // [rsp+70h] [rbp-68h] BYREF
  __int128 v14; // [rsp+90h] [rbp-48h]
  __int128 v15; // [rsp+A0h] [rbp-38h]
  __int64 v16; // [rsp+B0h] [rbp-28h]
  const struct _CERT_CONTEXT *v17; // [rsp+E0h] [rbp+8h] BYREF

  v17 = a1;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::AcquireCredentialsForServer_v2",
      545,
      L"API|SNIpHandle: %p{PCCERT_CONTEXT}\n",
      v17);
  v13[1] = 1;
  v13[3] = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = 5;
  v13[2] = &v17;
  if ( Ssl::s_fDisableSchannelSessionResumption )
    DWORD1(v15) |= 0x80u;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v5 = (struct _SecHandle *)operator new(
                              0x10u,
                              *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v4 + 992) + 56LL) + 8LL),
                              1,
                              "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                              568,
                              6u);
  *a2 = v5;
  if ( !v5 )
  {
    v6 = 14;
LABEL_14:
    scierrlog(0x659Au, v6);
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v12) = v6;
      LODWORD(v11) = 0;
      LODWORD(v10) = 6;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::AcquireCredentialsForServer_v2",
        593,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v10,
        v11,
        v12);
    }
    SNISetLastError(6u, v6, 0xC3B4u);
    operator delete(*a2, 0x10u);
    *a2 = 0;
    goto LABEL_17;
  }
  HIDWORD(v12) = 0;
  HIDWORD(v11) = 0;
  v10 = v13;
  v7 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, __int64))Ssl::s_pfTable->AcquireCredentialsHandleW)(
         0,
         L"Microsoft Unified Security Protocol Provider",
         1);
  v6 = v7;
  if ( v7 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v10) = v7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::AcquireCredentialsForServer_v2",
        586,
        L"ERR|SNIAcquireCredentialsHandle return value: %d{DWORD}\n",
        v10);
    }
    goto LABEL_14;
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) == 0 )
    goto LABEL_19;
  LODWORD(v10) = 0;
  SNIXE_SNI_TRACE_ON(
    "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
    "Ssl::AcquireCredentialsForServer_v2",
    586,
    L"SNIAcquireCredentialsHandle return value: %d{DWORD}\n",
    v10);
LABEL_17:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v10) = v6;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::AcquireCredentialsForServer_v2",
      599,
      L"RET|SNI%d{WINERR}\n",
      v10);
  }
LABEL_19:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::AcquireCredentialsForServer_v2", 545, v8);
  return v6;
}

```

## disassembly

```asm
0x10044b950  mov     rax, rsp
0x10044b953  mov     [rax+8], rcx
0x10044b957  push    rsi
0x10044b958  push    rdi
0x10044b959  push    r14
0x10044b95b  sub     rsp, 0C0h
0x10044b962  mov     [rsp+0D8h+var_88], 0FFFFFFFFFFFFFFFEh
0x10044b96b  mov     [rax+18h], rbx
0x10044b96f  mov     [rax+20h], rbp
0x10044b973  mov     rdi, rdx
0x10044b976  lea     rsi, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044b97d  mov     [rax-80h], rsi
0x10044b981  lea     r14, aSslAcquirecred_2; "Ssl::AcquireCredentialsForServer_v2"
0x10044b988  mov     [rax-78h], r14
0x10044b98c  mov     dword ptr [rax-70h], 221h
0x10044b993  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044b99a  jz      short loc_10044B9BD
0x10044b99c  mov     rax, [rax+8]
0x10044b9a0  mov     [rsp+0D8h+var_B8], rax
0x10044b9a5  lea     r9, aApiSniphandleP_0; "API|SNIpHandle: %p{PCCERT_CONTEXT}\n"
0x10044b9ac  mov     r8d, 221h; int
0x10044b9b2  mov     rdx, r14; char *
0x10044b9b5  mov     rcx, rsi; char *
0x10044b9b8  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10044b9bd  xor     ebp, ebp
0x10044b9bf  mov     [rsp+0D8h+var_60], 1
0x10044b9c8  mov     [rsp+0D8h+var_50], rbp
0x10044b9d0  xorps   xmm0, xmm0
0x10044b9d3  movdqa  [rsp+0D8h+var_48], xmm0
0x10044b9dc  xorps   xmm1, xmm1
0x10044b9df  movdqa  [rsp+0D8h+var_38], xmm1
0x10044b9e8  mov     [rsp+0D8h+var_28], rbp
0x10044b9f0  mov     [rsp+0D8h+var_68], 5
0x10044b9f9  lea     rax, [rsp+0D8h+arg_0]
0x10044ba01  mov     [rsp+0D8h+var_58], rax
0x10044ba09  cmp     cs:?s_fDisableSchannelSessionResumption@Ssl@@0_NA, bpl; bool Ssl::s_fDisableSchannelSessionResumption
0x10044ba10  jz      short loc_10044BA1D
0x10044ba12  or      dword ptr [rsp+0D8h+var_38+4], 80h
0x10044ba1d  mov     rdx, gs:58h
0x10044ba26  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044ba2d  mov     ecx, [rax]
0x10044ba2f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044ba36  mov     ebx, [rax]
0x10044ba38  add     rbx, [rdx+rcx*8]
0x10044ba3c  mov     rax, [rbx+100h]
0x10044ba43  test    rax, rax
0x10044ba46  jnz     short loc_10044BA57
0x10044ba48  xor     ecx, ecx
0x10044ba4a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044ba50  mov     rax, [rbx+100h]
0x10044ba57  mov     rax, [rax+3E0h]
0x10044ba5e  mov     rcx, [rax+38h]
0x10044ba62  mov     byte ptr [rsp+0D8h+var_B0], 6
0x10044ba67  mov     dword ptr [rsp+0D8h+var_B8], 238h
0x10044ba6f  mov     r9, rsi
0x10044ba72  mov     r8d, 1
0x10044ba78  mov     rdx, [rcx+8]
0x10044ba7c  lea     ecx, [r8+0Fh]
0x10044ba80  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10044ba86  mov     [rdi], rax
0x10044ba89  test    rax, rax
0x10044ba8c  jnz     short loc_10044BA96
0x10044ba8e  lea     ebx, [rax+0Eh]
0x10044ba91  jmp     loc_10044BB2F
0x10044ba96  lea     rcx, [rsp+0D8h+arg_8]
0x10044ba9e  mov     [rsp+0D8h+var_98], rcx
0x10044baa3  mov     [rsp+0D8h+var_A0], rax
0x10044baa8  mov     [rsp+0D8h+var_A8], rbp
0x10044baad  mov     [rsp+0D8h+var_B0], rbp
0x10044bab2  lea     rax, [rsp+0D8h+var_68]
0x10044bab7  mov     [rsp+0D8h+var_B8], rax
0x10044babc  xor     r9d, r9d
0x10044babf  lea     r8d, [r9+1]
0x10044bac3  lea     rdx, aMicrosoftUnifi; "Microsoft Unified Security Protocol Pro"...
0x10044baca  xor     ecx, ecx
0x10044bacc  mov     rax, cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x10044bad3  call    qword ptr [rax+18h]
0x10044bad6  mov     ebx, eax
0x10044bad8  test    eax, eax
0x10044bada  jnz     short loc_10044BB0A
0x10044badc  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044bae3  jz      loc_10044BBB5
0x10044bae9  mov     dword ptr [rsp+0D8h+var_B8], ebp
0x10044baed  lea     r9, aSniacquirecred; "SNIAcquireCredentialsHandle return valu"...
0x10044baf4  mov     r8d, 24Ah; int
0x10044bafa  mov     rdx, r14; char *
0x10044bafd  mov     rcx, rsi; char *
0x10044bb00  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044bb05  jmp     loc_10044BB8F
0x10044bb0a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044bb11  jz      short loc_10044BB2F
0x10044bb13  mov     dword ptr [rsp+0D8h+var_B8], eax
0x10044bb17  lea     r9, aErrSniacquirec; "ERR|SNIAcquireCredentialsHandle return "...
0x10044bb1e  mov     r8d, 24Ah; int
0x10044bb24  mov     rdx, r14; char *
0x10044bb27  mov     rcx, rsi; char *
0x10044bb2a  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10044bb2f  mov     edx, ebx
0x10044bb31  mov     ecx, 659Ah; unsigned int
0x10044bb36  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10044bb3b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044bb42  jz      short loc_10044BB6C
0x10044bb44  mov     dword ptr [rsp+0D8h+var_A8], ebx
0x10044bb48  mov     dword ptr [rsp+0D8h+var_B0], ebp
0x10044bb4c  mov     dword ptr [rsp+0D8h+var_B8], 6
0x10044bb54  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10044bb5b  mov     r8d, 251h; int
0x10044bb61  mov     rdx, r14; char *
0x10044bb64  mov     rcx, rsi; char *
0x10044bb67  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10044bb6c  mov     r8d, 0C3B4h
0x10044bb72  mov     edx, ebx
0x10044bb74  mov     ecx, 6
0x10044bb79  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10044bb7e  mov     edx, 10h
0x10044bb83  mov     rcx, [rdi]
0x10044bb86  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10044bb8c  mov     [rdi], rbp
0x10044bb8f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044bb96  jz      short loc_10044BBB5
0x10044bb98  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x10044bb9c  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10044bba3  mov     r8d, 257h; int
0x10044bba9  mov     rdx, r14; char *
0x10044bbac  mov     rcx, rsi; char *
0x10044bbaf  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044bbb4  nop
0x10044bbb5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044bbbc  jz      short loc_10044BBCF
0x10044bbbe  mov     r8d, 221h; int
0x10044bbc4  mov     rdx, r14; char *
0x10044bbc7  mov     rcx, rsi; char *
0x10044bbca  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10044bbcf  mov     eax, ebx
0x10044bbd1  lea     r11, [rsp+0D8h+var_18]
0x10044bbd9  mov     rbx, [r11+30h]
0x10044bbdd  mov     rbp, [r11+38h]
0x10044bbe1  mov     rsp, r11
0x10044bbe4  pop     r14
0x10044bbe6  pop     rdi
0x10044bbe7  pop     rsi
0x10044bbe8  retn
```
