# Ssl::IsCertKeyUsageExchange(_CERT_CONTEXT const *)

- ea: `0x10044fd00`
- end: `0x10044feb4`
- name: `?IsCertKeyUsageExchange@Ssl@@CAKPEBU_CERT_CONTEXT@@@Z`
- size: `436`
- prototype: `unsigned int __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10044cff0`

## callees

- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`
- `0x10044fd00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10044fe14`
- `KERNEL32!GetLastError` at `0x10044fe14`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044fe56`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044fe56`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044fde7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044fde7`
- `sqldk!SystemThread_TlsIndex` at `0x10044fd8d`
- `sqldk!SystemThread_TlsOffset` at `0x10044fd96`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044fdb1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044fdb1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x10044fd76`
- `CRYPT32!CertGetCertificateContextProperty` at `0x10044fe0a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x10044fd76`
- `CRYPT32!CertGetCertificateContextProperty` at `0x10044fe0a`

## string_xrefs

- `0x10044fd1e`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Ssl::IsCertKeyUsageExchange(PCCERT_CONTEXT pCertContext)
{
  DWORD LastError; // ebx
  _BYTE *v3; // rdi
  __int64 v4; // rdi
  __int64 v5; // rax
  _BYTE *v6; // rax
  const wchar_t *v7; // r9
  __int64 v9; // [rsp+20h] [rbp-48h]
  DWORD pcbData; // [rsp+78h] [rbp+10h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::IsCertKeyUsageExchange",
      3716,
      L"API|SNIpCertContext: %p{PCCERT_CONTEXT}\n",
      pCertContext);
  LastError = 0;
  v3 = 0;
  pcbData = 0;
  if ( CertGetCertificateContextProperty(pCertContext, 2u, 0, &pcbData) )
  {
    v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v5 = *(_QWORD *)(v4 + 256);
    if ( !v5 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v5 = *(_QWORD *)(v4 + 256);
    }
    v6 = operator new[](
           pcbData,
           *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v5 + 992) + 56LL) + 8LL),
           1,
           "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
           3731,
           6u);
    v3 = v6;
    if ( !v6 )
    {
      LastError = 14;
      goto LABEL_10;
    }
    if ( CertGetCertificateContextProperty(pCertContext, 2u, v6, &pcbData) )
    {
      if ( (v3[40] & 1) == 0 )
        LastError = -2146885628;
      goto LABEL_16;
    }
  }
  LastError = GetLastError();
LABEL_10:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v9) = LastError;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::IsCertKeyUsageExchange",
      3758,
      L"ERR|SNI%d{WINERR}\n",
      v9);
  }
  if ( v3 )
LABEL_16:
    operator delete[](v3);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v9) = LastError;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::IsCertKeyUsageExchange",
      3767,
      L"RET|SNI%d{WINERR}\n",
      v9);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::IsCertKeyUsageExchange", 3716, v7);
  return LastError;
}

```

## disassembly

```asm
0x10044fd00  mov     rax, rsp
0x10044fd03  push    rsi
0x10044fd04  push    rdi
0x10044fd05  push    r14
0x10044fd07  sub     rsp, 50h
0x10044fd0b  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x10044fd13  mov     [rax+8], rbx
0x10044fd17  mov     [rax+18h], rbp
0x10044fd1b  mov     rsi, rcx
0x10044fd1e  lea     rbp, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044fd25  mov     [rax-30h], rbp
0x10044fd29  lea     r14, aSslIscertkeyus; "Ssl::IsCertKeyUsageExchange"
0x10044fd30  mov     [rax-28h], r14
0x10044fd34  mov     dword ptr [rax-20h], 0E84h
0x10044fd3b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044fd42  jz      short loc_10044FD60
0x10044fd44  mov     [rax-48h], rcx
0x10044fd48  lea     r9, aApiSnipcertcon; "API|SNIpCertContext: %p{PCCERT_CONTEXT}"...
0x10044fd4f  mov     r8d, 0E84h; int
0x10044fd55  mov     rdx, r14; char *
0x10044fd58  mov     rcx, rbp; char *
0x10044fd5b  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10044fd60  xor     ebx, ebx
0x10044fd62  mov     edi, ebx
0x10044fd64  mov     [rsp+68h+pcbData], ebx
0x10044fd68  lea     r9, [rsp+68h+pcbData]; pcbData
0x10044fd6d  xor     r8d, r8d; pvData
0x10044fd70  lea     edx, [rbx+2]; dwPropId
0x10044fd73  mov     rcx, rsi; pCertContext
0x10044fd76  call    cs:__imp_CertGetCertificateContextProperty
0x10044fd7c  test    eax, eax
0x10044fd7e  jz      loc_10044FE14
0x10044fd84  mov     rdx, gs:58h
0x10044fd8d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044fd94  mov     ecx, [rax]
0x10044fd96  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044fd9d  mov     edi, [rax]
0x10044fd9f  add     rdi, [rdx+rcx*8]
0x10044fda3  mov     rax, [rdi+100h]
0x10044fdaa  test    rax, rax
0x10044fdad  jnz     short loc_10044FDBE
0x10044fdaf  xor     ecx, ecx
0x10044fdb1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044fdb7  mov     rax, [rdi+100h]
0x10044fdbe  mov     rax, [rax+3E0h]
0x10044fdc5  mov     rcx, [rax+38h]
0x10044fdc9  mov     rdx, [rcx+8]
0x10044fdcd  mov     ecx, [rsp+68h+pcbData]
0x10044fdd1  mov     [rsp+68h+var_40], 6
0x10044fdd6  mov     dword ptr [rsp+68h+var_48], 0E93h
0x10044fdde  mov     r9, rbp
0x10044fde1  mov     r8d, 1
0x10044fde7  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10044fded  mov     rdi, rax
0x10044fdf0  test    rax, rax
0x10044fdf3  jnz     short loc_10044FDFA
0x10044fdf5  lea     ebx, [rax+0Eh]
0x10044fdf8  jmp     short loc_10044FE1C
0x10044fdfa  lea     r9, [rsp+68h+pcbData]; pcbData
0x10044fdff  mov     r8, rdi; pvData
0x10044fe02  mov     edx, 2; dwPropId
0x10044fe07  mov     rcx, rsi; pCertContext
0x10044fe0a  call    cs:__imp_CertGetCertificateContextProperty
0x10044fe10  test    eax, eax
0x10044fe12  jnz     short loc_10044FE48
0x10044fe14  call    cs:__imp_GetLastError
0x10044fe1a  mov     ebx, eax
0x10044fe1c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044fe23  jz      short loc_10044FE41
0x10044fe25  mov     dword ptr [rsp+68h+var_48], ebx
0x10044fe29  lea     r9, aErrSniDWinerr; "ERR|SNI%d{WINERR}\n"
0x10044fe30  mov     r8d, 0EAEh; int
0x10044fe36  mov     rdx, r14; char *
0x10044fe39  mov     rcx, rbp; char *
0x10044fe3c  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044fe41  test    rdi, rdi
0x10044fe44  jz      short loc_10044FE5C
0x10044fe46  jmp     short loc_10044FE53
0x10044fe48  test    byte ptr [rdi+28h], 1
0x10044fe4c  jnz     short loc_10044FE53
0x10044fe4e  mov     ebx, 80092004h
0x10044fe53  mov     rcx, rdi
0x10044fe56  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044fe5c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044fe63  jz      short loc_10044FE82
0x10044fe65  mov     dword ptr [rsp+68h+var_48], ebx
0x10044fe69  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10044fe70  mov     r8d, 0EB7h; int
0x10044fe76  mov     rdx, r14; char *
0x10044fe79  mov     rcx, rbp; char *
0x10044fe7c  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044fe81  nop
0x10044fe82  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044fe89  jz      short loc_10044FE9C
0x10044fe8b  mov     r8d, 0E84h; int
0x10044fe91  mov     rdx, r14; char *
0x10044fe94  mov     rcx, rbp; char *
0x10044fe97  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10044fe9c  mov     eax, ebx
0x10044fe9e  mov     rbx, [rsp+68h+arg_0]
0x10044fea3  mov     rbp, [rsp+68h+arg_10]
0x10044feab  add     rsp, 50h
0x10044feaf  pop     r14
0x10044feb1  pop     rdi
0x10044feb2  pop     rsi
0x10044feb3  retn
```
