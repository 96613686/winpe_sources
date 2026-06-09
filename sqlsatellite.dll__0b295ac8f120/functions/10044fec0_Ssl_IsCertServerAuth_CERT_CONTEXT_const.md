# Ssl::IsCertServerAuth(_CERT_CONTEXT const *)

- ea: `0x10044fec0`
- end: `0x1004500f2`
- name: `?IsCertServerAuth@Ssl@@CAKPEBU_CERT_CONTEXT@@@Z`
- size: `562`
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
- `0x10044fec0`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x100450075`
- `KERNEL32!CompareStringA` at `0x100450075`
- `KERNEL32!GetLastError` at `0x100450009`
- `KERNEL32!GetLastError` at `0x100450019`
- `KERNEL32!GetLastError` at `0x100450009`
- `KERNEL32!GetLastError` at `0x100450019`
- `sqldk!??_V@YAXPEAX@Z` at `0x100450091`
- `sqldk!??_V@YAXPEAX@Z` at `0x100450091`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044ffab`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044ffab`
- `sqldk!SystemThread_TlsIndex` at `0x10044ff4e`
- `sqldk!SystemThread_TlsOffset` at `0x10044ff57`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044ff72`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044ff72`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x10044ff3f`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x10044ffff`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x10044ff3f`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x10044ffff`

## string_xrefs

- `0x10044fee2`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Ssl::IsCertServerAuth(PCCERT_CONTEXT pCertContext)
{
  __int64 v2; // rdi
  __int64 v3; // rax
  struct _CTL_USAGE *v4; // rax
  const wchar_t *v5; // r9
  struct _CTL_USAGE *v6; // rsi
  DWORD LastError; // ebx
  DWORD v8; // eax
  signed int v9; // edi
  __int64 v10; // r14
  PCNZCH lpString2; // [rsp+20h] [rbp-58h]
  DWORD pcbUsage; // [rsp+88h] [rbp+10h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::IsCertServerAuth",
      3774,
      L"API|SNIpCertContext: %p{PCCERT_CONTEXT}\n",
      pCertContext);
  pcbUsage = 0;
  CertGetEnhancedKeyUsage(pCertContext, 0, 0, &pcbUsage);
  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  v4 = (struct _CTL_USAGE *)operator new[](
                              pcbUsage,
                              *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v3 + 992) + 56LL) + 8LL),
                              1,
                              "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                              3782,
                              6u);
  v6 = v4;
  if ( !v4 )
  {
    LastError = 14;
    goto LABEL_7;
  }
  if ( !CertGetEnhancedKeyUsage(pCertContext, 0, v4, &pcbUsage) )
  {
    LastError = GetLastError();
    goto LABEL_7;
  }
  if ( v6->cUsageIdentifier )
  {
    LastError = -2146885628;
    v9 = 0;
    if ( (int)v6->cUsageIdentifier <= 0 )
      goto LABEL_23;
    v10 = 0;
    while ( CompareStringA(0x800u, 0x20000u, v6->rgpszUsageIdentifier[v10], -1, "1.3.6.1.5.5.7.3.1", -1) != 2 )
    {
      ++v9;
      ++v10;
      if ( v9 >= (signed int)v6->cUsageIdentifier )
        goto LABEL_23;
    }
LABEL_22:
    LastError = 0;
    goto LABEL_23;
  }
  v8 = GetLastError();
  LastError = v8;
  if ( v8 == -2146885628 )
    goto LABEL_22;
  if ( !v8 )
  {
    LastError = -2146885628;
LABEL_23:
    operator delete[](v6);
    goto LABEL_24;
  }
LABEL_7:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpString2) = LastError;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::IsCertServerAuth",
      3850,
      L"ERR|SNI%d{WINERR}\n",
      lpString2);
  }
  if ( v6 )
    goto LABEL_23;
LABEL_24:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpString2) = LastError;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::IsCertServerAuth",
      3857,
      L"RET|SNI%d{WINERR}\n",
      lpString2);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::IsCertServerAuth", 3774, v5);
  return LastError;
}

```

## disassembly

```asm
0x10044fec0  mov     rax, rsp
0x10044fec3  push    rsi
0x10044fec4  push    rdi
0x10044fec5  push    r12
0x10044fec7  push    r14
0x10044fec9  push    r15
0x10044fecb  sub     rsp, 50h
0x10044fecf  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x10044fed7  mov     [rax+8], rbx
0x10044fedb  mov     [rax+18h], rbp
0x10044fedf  mov     rbx, rcx
0x10044fee2  lea     rbp, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044fee9  mov     [rax-40h], rbp
0x10044feed  lea     r15, aSslIscertserve; "Ssl::IsCertServerAuth"
0x10044fef4  mov     [rax-38h], r15
0x10044fef8  mov     dword ptr [rax-30h], 0EBEh
0x10044feff  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044ff06  jz      short loc_10044FF24
0x10044ff08  mov     [rax-58h], rcx
0x10044ff0c  lea     r9, aApiSnipcertcon; "API|SNIpCertContext: %p{PCCERT_CONTEXT}"...
0x10044ff13  mov     r8d, 0EBEh; int
0x10044ff19  mov     rdx, r15; char *
0x10044ff1c  mov     rcx, rbp; char *
0x10044ff1f  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10044ff24  mov     [rsp+78h+pcbUsage], 0
0x10044ff2f  lea     r9, [rsp+78h+pcbUsage]; pcbUsage
0x10044ff37  xor     r8d, r8d; pUsage
0x10044ff3a  xor     edx, edx; dwFlags
0x10044ff3c  mov     rcx, rbx; pCertContext
0x10044ff3f  call    cs:__imp_CertGetEnhancedKeyUsage
0x10044ff45  mov     rdx, gs:58h
0x10044ff4e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044ff55  mov     ecx, [rax]
0x10044ff57  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044ff5e  mov     edi, [rax]
0x10044ff60  add     rdi, [rdx+rcx*8]
0x10044ff64  mov     rax, [rdi+100h]
0x10044ff6b  test    rax, rax
0x10044ff6e  jnz     short loc_10044FF7F
0x10044ff70  xor     ecx, ecx
0x10044ff72  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044ff78  mov     rax, [rdi+100h]
0x10044ff7f  mov     rax, [rax+3E0h]
0x10044ff86  mov     rcx, [rax+38h]
0x10044ff8a  mov     rdx, [rcx+8]
0x10044ff8e  mov     ecx, [rsp+78h+pcbUsage]
0x10044ff95  mov     byte ptr [rsp+78h+cchCount2], 6
0x10044ff9a  mov     dword ptr [rsp+78h+lpString2], 0EC6h
0x10044ffa2  mov     r9, rbp
0x10044ffa5  mov     r8d, 1
0x10044ffab  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10044ffb1  mov     rsi, rax
0x10044ffb4  test    rax, rax
0x10044ffb7  jnz     short loc_10044FFEF
0x10044ffb9  lea     ebx, [rax+0Eh]
0x10044ffbc  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044ffc3  jz      short loc_10044FFE1
0x10044ffc5  mov     dword ptr [rsp+78h+lpString2], ebx
0x10044ffc9  lea     r9, aErrSniDWinerr; "ERR|SNI%d{WINERR}\n"
0x10044ffd0  mov     r8d, 0F0Ah; int
0x10044ffd6  mov     rdx, r15; char *
0x10044ffd9  mov     rcx, rbp; char *
0x10044ffdc  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044ffe1  test    rsi, rsi
0x10044ffe4  jz      loc_100450097
0x10044ffea  jmp     loc_10045008E
0x10044ffef  lea     r9, [rsp+78h+pcbUsage]; pcbUsage
0x10044fff7  mov     r8, rsi; pUsage
0x10044fffa  xor     edx, edx; dwFlags
0x10044fffc  mov     rcx, rbx; pCertContext
0x10044ffff  call    cs:__imp_CertGetEnhancedKeyUsage
0x100450005  test    eax, eax
0x100450007  jnz     short loc_100450013
0x100450009  call    cs:__imp_GetLastError
0x10045000f  mov     ebx, eax
0x100450011  jmp     short loc_10044FFBC
0x100450013  mov     eax, [rsi]
0x100450015  test    eax, eax
0x100450017  jnz     short loc_100450033
0x100450019  call    cs:__imp_GetLastError
0x10045001f  mov     ebx, eax
0x100450021  cmp     eax, 80092004h
0x100450026  jz      short loc_10045008C
0x100450028  test    eax, eax
0x10045002a  jnz     short loc_10044FFBC
0x10045002c  mov     ebx, 80092004h
0x100450031  jmp     short loc_10045008E
0x100450033  mov     ebx, 80092004h
0x100450038  xor     edi, edi
0x10045003a  test    eax, eax
0x10045003c  jle     short loc_10045008E
0x10045003e  xor     r14d, r14d
0x100450041  lea     r12, a136155731; "1.3.6.1.5.5.7.3.1"
0x100450048  nop     dword ptr [rax+rax+00000000h]
0x100450050  mov     rax, [rsi+8]
0x100450054  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x10045005c  mov     [rsp+78h+lpString2], r12; lpString2
0x100450061  mov     r9d, 0FFFFFFFFh; cchCount1
0x100450067  mov     r8, [r14+rax]; lpString1
0x10045006b  mov     edx, 20000h; dwCmpFlags
0x100450070  mov     ecx, 800h; Locale
0x100450075  call    cs:__imp_CompareStringA
0x10045007b  cmp     eax, 2
0x10045007e  jz      short loc_10045008C
0x100450080  inc     edi
0x100450082  add     r14, 8
0x100450086  cmp     edi, [rsi]
0x100450088  jl      short loc_100450050
0x10045008a  jmp     short loc_10045008E
0x10045008c  xor     ebx, ebx
0x10045008e  mov     rcx, rsi
0x100450091  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100450097  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045009e  jz      short loc_1004500BD
0x1004500a0  mov     dword ptr [rsp+78h+lpString2], ebx
0x1004500a4  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004500ab  mov     r8d, 0F11h; int
0x1004500b1  mov     rdx, r15; char *
0x1004500b4  mov     rcx, rbp; char *
0x1004500b7  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004500bc  nop
0x1004500bd  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004500c4  jz      short loc_1004500D7
0x1004500c6  mov     r8d, 0EBEh; int
0x1004500cc  mov     rdx, r15; char *
0x1004500cf  mov     rcx, rbp; char *
0x1004500d2  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004500d7  mov     eax, ebx
0x1004500d9  lea     r11, [rsp+78h+var_28]
0x1004500de  mov     rbx, [r11+30h]
0x1004500e2  mov     rbp, [r11+40h]
0x1004500e6  mov     rsp, r11
0x1004500e9  pop     r15
0x1004500eb  pop     r14
0x1004500ed  pop     r12
0x1004500ef  pop     rdi
0x1004500f0  pop     rsi
0x1004500f1  retn
```
