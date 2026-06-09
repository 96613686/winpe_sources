# CryptoBase::ProcessAddProvider(SNIAuthErrOps *,SNIAuthErrStates *)

- ea: `0x100448a50`
- end: `0x100448d86`
- name: `?ProcessAddProvider@CryptoBase@@UEAAKPEAW4SNIAuthErrOps@@PEAW4SNIAuthErrStates@@@Z`
- size: `822`
- prototype: `unsigned int __fastcall(CryptoBase *__hidden this, enum SNIAuthErrOps *, enum SNIAuthErrStates *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x100418930`
- `0x1004189a0`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100448700`
- `0x1004487c0`
- `0x100448a50`
- `0x1004490f0`
- `0x1004494a0`
- `0x100449680`
- `0x100455660`

## import_xrefs

- `sqldk!?ReportAndBackoutHandler@@YAHHHHHPEAD@Z` at `0x100448ae8`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100448cbc`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100448cbc`
- `sqldk!SystemThread_TlsIndex` at `0x100448c84`
- `sqldk!SystemThread_TlsOffset` at `0x100448c8d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100448ca6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100448ca6`

## string_xrefs

- `0x100448a83`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100448c55`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CryptoBase::ProcessAddProvider(CryptoBase *this, enum SNIAuthErrOps *a2, enum SNIAuthErrStates *a3)
{
  enum SNIAuthErrStates *v3; // r14
  enum SNIAuthErrOps *v4; // r15
  int v6; // esi
  unsigned int AuthError; // ebx
  unsigned int SecurityToken; // eax
  const wchar_t *v9; // r9
  __int64 v10; // rdi
  __int64 v11; // rcx
  char v12; // al
  DWORD LastError; // ebx
  int (*v15)(int, int, int, int, char *); // [rsp+20h] [rbp-D8h]
  struct Worker *v16; // [rsp+28h] [rbp-D0h]
  __int64 v17; // [rsp+30h] [rbp-C8h]
  int v18; // [rsp+40h] [rbp-B8h]
  _BYTE v19[16]; // [rsp+68h] [rbp-90h] BYREF
  _BYTE v20[24]; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v21[104]; // [rsp+90h] [rbp-68h] BYREF

  v3 = a3;
  v4 = a2;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
      "CryptoBase::ProcessAddProvider",
      3927,
      L"API|SNI%u#, pConn: %p{SNI_Conn*}\n",
      *((_DWORD *)this + 11),
      *((_QWORD *)this + 4));
  v6 = *((_DWORD *)this + 12);
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v21, 0, 0, 0, ReportAndBackoutHandler, 0);
    AuthError = CryptoBase::GetAuthError(this, v4, v3);
    v18 = AuthError;
    if ( AuthError )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v16) = 0;
        LODWORD(v15) = *((_DWORD *)this + 6);
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
          "CryptoBase::ProcessAddProvider",
          3946,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v15,
          v16,
          AuthError);
      }
      SNISetLastError(*((_DWORD *)this + 6), AuthError, 0xC3B4u);
    }
    CryptoBase::SetLoginEvent(this, 3);
    while ( 1 )
    {
      if ( AuthError || (unsigned int)(v6 - 3) <= 1 )
      {
        ExcHandler::~ExcHandler((ExcHandler *)v21);
        goto LABEL_47;
      }
      if ( *((_DWORD *)this + 54) == 1 )
      {
        *((_DWORD *)this + 54) = 2;
        SecurityToken = CryptoBase::ReadSecurityToken(this);
      }
      else
      {
        if ( *((_DWORD *)this + 54) != 2 )
        {
          AuthError = -1;
          v18 = -1;
          CryptoBase::GetAuthError(this, v4, v3);
          goto LABEL_20;
        }
        *((_DWORD *)this + 54) = 1;
        SecurityToken = CryptoBase::ProcessAndWriteSecurityToken(this);
      }
      v18 = SecurityToken;
      AuthError = SecurityToken;
      if ( SecurityToken != 997 )
        break;
      if ( g_osviSNI.dwMajorVersion < 6 )
      {
        CryptoBase::WaitForIOCompletion(this, (unsigned int)(*((_DWORD *)this + 54) == 1) + 2);
        AuthError = CryptoBase::GetAuthError(this, v4, v3);
        v18 = AuthError;
LABEL_20:
        v6 = *((_DWORD *)this + 12);
      }
    }
    CryptoBase::GetAuthError(this, v4, v3);
    goto LABEL_20;
  }
  catch ( SQLError v20 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v19, (const struct SQLError *)v20);
      LastError = v18;
      if ( !v18 )
      {
        LastError = GetLastError();
        v18 = LastError;
      }
      *(_DWORD *)a2 = 0;
      *(_DWORD *)a3 = 40;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
          "CryptoBase::ProcessAddProvider",
          4046,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          *((_DWORD *)this + 6),
          0,
          LastError);
      SNISetLastError(*((_DWORD *)this + 6), LastError, 0xC3B4u);
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
          "CryptoBase::ProcessAddProvider",
          4048,
          L"ERR|SNIUnhandled exception in the authentication routine.\n");
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v19);
    }
    catch ( ShortStackException )
    {
    }
    v3 = a3;
    v4 = a2;
    v6 = 4;
    AuthError = v18;
  }
LABEL_47:
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  if ( *(_DWORD *)(v11 + 556) )
    ExceptionPostCatchActions((struct Worker *)v11);
  v12 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v16) = v6;
    LODWORD(v15) = AuthError;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
      "CryptoBase::ProcessAddProvider",
      4056,
      L"SNIdwError: %d{DWORD}, authState: %d{SNIAuthProvState}\n",
      v15,
      v16);
    v12 = g_XeSniPkg_enabledBitmap;
  }
  if ( AuthError != 997 )
  {
    if ( (v12 & 1) != 0 )
    {
      LODWORD(v15) = AuthError;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
        "CryptoBase::ProcessAddProvider",
        4071,
        L"SNIFinalizing negotiation. dwError: %d{DWORD}\n",
        v15);
    }
    SNIAutoEvent::Release((SNIAutoEvent *)v11);
    v12 = g_XeSniPkg_enabledBitmap;
  }
  if ( (v12 & 1) != 0 )
  {
    LODWORD(v17) = *(_DWORD *)v3;
    LODWORD(v16) = *(_DWORD *)v4;
    LODWORD(v15) = AuthError;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
      "CryptoBase::ProcessAddProvider",
      4084,
      L"RET|SNIdwError: %d{DWORD}, errOp: %d{DWORD}, errState: %d{DWORD}\n",
      v15,
      v16,
      v17);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp", "CryptoBase::ProcessAddProvider", 3927, v9);
  return AuthError;
}

```

## disassembly

```asm
0x100448a50  mov     [rsp+arg_10], r8
0x100448a55  mov     [rsp+arg_8], rdx
0x100448a5a  mov     [rsp+arg_0], rcx
0x100448a5f  push    rbx
0x100448a60  push    rsi
0x100448a61  push    rdi
0x100448a62  push    r12
0x100448a64  push    r13
0x100448a66  push    r14
0x100448a68  push    r15
0x100448a6a  sub     rsp, 0C0h
0x100448a71  mov     [rsp+0F8h+var_98], 0FFFFFFFFFFFFFFFEh
0x100448a7a  mov     r14, r8
0x100448a7d  mov     r15, rdx
0x100448a80  mov     rdi, rcx
0x100448a83  lea     r12, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100448a8a  mov     [rsp+0F8h+var_B0], r12
0x100448a8f  lea     r13, aCryptobaseProc_0; "CryptoBase::ProcessAddProvider"
0x100448a96  mov     [rsp+0F8h+var_A8], r13
0x100448a9b  mov     [rsp+0F8h+var_A0], 0F57h
0x100448aa3  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100448aaa  jz      short loc_100448AD4
0x100448aac  mov     rax, [rcx+20h]
0x100448ab0  mov     [rsp+0F8h+var_D0], rax
0x100448ab5  mov     eax, [rcx+2Ch]
0x100448ab8  mov     dword ptr [rsp+0F8h+var_D8], eax
0x100448abc  lea     r9, aApiSniUPconnPS; "API|SNI%u#, pConn: %p{SNI_Conn*}\n"
0x100448ac3  mov     r8d, 0F57h; int
0x100448ac9  mov     rdx, r13; char *
0x100448acc  mov     rcx, r12; char *
0x100448acf  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100448ad4  mov     esi, [rdi+30h]
0x100448ad7  mov     [rsp+0F8h+var_B4], esi
0x100448adb  xor     eax, eax
0x100448add  mov     [rsp+0F8h+var_B8], eax
0x100448ae1  xor     edx, edx; unsigned __int16
0x100448ae3  mov     [rsp+0F8h+var_D0], rax; struct Worker *
0x100448ae8  mov     rax, cs:__imp_?ReportAndBackoutHandler@@YAHHHHHPEAD@Z; ReportAndBackoutHandler(int,int,int,int,char *)
0x100448aef  mov     [rsp+0F8h+var_D8], rax; int (*)(int, int, int, int, char *)
0x100448af4  xor     r9d, r9d; unsigned __int8
0x100448af7  xor     r8d, r8d; unsigned __int8
0x100448afa  lea     rcx, [rsp+0F8h+var_68]; this
0x100448b02  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x100448b07  nop
0x100448b08  mov     r8, r14; enum SNIAuthErrStates *
0x100448b0b  mov     rdx, r15; enum SNIAuthErrOps *
0x100448b0e  mov     rcx, rdi; this
0x100448b11  call    ?GetAuthError@CryptoBase@@QEAAKPEAW4SNIAuthErrOps@@PEAW4SNIAuthErrStates@@@Z; CryptoBase::GetAuthError(SNIAuthErrOps *,SNIAuthErrStates *)
0x100448b16  mov     ebx, eax
0x100448b18  mov     [rsp+0F8h+var_B8], eax
0x100448b1c  test    eax, eax
0x100448b1e  jz      short loc_100448B74
0x100448b20  xor     eax, eax
0x100448b22  mov     [rsp+0F8h+arg_18], eax
0x100448b29  mov     [rsp+0F8h+arg_1C], 2
0x100448b34  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100448b3b  jz      short loc_100448B64
0x100448b3d  mov     [rsp+0F8h+var_C8], ebx
0x100448b41  mov     dword ptr [rsp+0F8h+var_D0], eax
0x100448b45  mov     eax, [rdi+18h]
0x100448b48  mov     dword ptr [rsp+0F8h+var_D8], eax
0x100448b4c  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100448b53  mov     r8d, 0F6Ah; int
0x100448b59  mov     rdx, r13; char *
0x100448b5c  mov     rcx, r12; char *
0x100448b5f  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100448b64  mov     r8d, 0C3B4h
0x100448b6a  mov     edx, ebx
0x100448b6c  mov     ecx, [rdi+18h]
0x100448b6f  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100448b74  mov     edx, 3
0x100448b79  lea     r8d, [rdx-2]
0x100448b7d  mov     rcx, rdi
0x100448b80  call    ?SetLoginEvent@CryptoBase@@QEAAXW4SNIAuthTimerEvent@@W4SNIAuthTimerEventType@@@Z; CryptoBase::SetLoginEvent(SNIAuthTimerEvent,SNIAuthTimerEventType)
0x100448b85  test    ebx, ebx
0x100448b87  jnz     loc_100448C45
0x100448b8d  lea     eax, [rsi-3]
0x100448b90  cmp     eax, 1
0x100448b93  jbe     loc_100448C45
0x100448b99  mov     ecx, [rdi+0D8h]
0x100448b9f  sub     ecx, 1
0x100448ba2  jz      short loc_100448BD6
0x100448ba4  cmp     ecx, 1
0x100448ba7  jz      short loc_100448BC2
0x100448ba9  mov     ebx, 0FFFFFFFFh
0x100448bae  mov     [rsp+0F8h+var_B8], ebx
0x100448bb2  mov     r8, r14; enum SNIAuthErrStates *
0x100448bb5  mov     rdx, r15; enum SNIAuthErrOps *
0x100448bb8  mov     rcx, rdi; this
0x100448bbb  call    ?GetAuthError@CryptoBase@@QEAAKPEAW4SNIAuthErrOps@@PEAW4SNIAuthErrStates@@@Z; CryptoBase::GetAuthError(SNIAuthErrOps *,SNIAuthErrStates *)
0x100448bc0  jmp     short loc_100448C39
0x100448bc2  mov     dword ptr [rdi+0D8h], 1
0x100448bcc  mov     rcx, rdi; this
0x100448bcf  call    ?ProcessAndWriteSecurityToken@CryptoBase@@AEAAKXZ; CryptoBase::ProcessAndWriteSecurityToken(void)
0x100448bd4  jmp     short loc_100448BE8
0x100448bd6  mov     dword ptr [rdi+0D8h], 2
0x100448be0  mov     rcx, rdi; this
0x100448be3  call    ?ReadSecurityToken@CryptoBase@@AEAAKXZ; CryptoBase::ReadSecurityToken(void)
0x100448be8  mov     [rsp+0F8h+var_B8], eax
0x100448bec  mov     ebx, eax
0x100448bee  cmp     eax, 3E5h
0x100448bf3  jz      short loc_100448C05
0x100448bf5  mov     r8, r14; enum SNIAuthErrStates *
0x100448bf8  mov     rdx, r15; enum SNIAuthErrOps *
0x100448bfb  mov     rcx, rdi; this
0x100448bfe  call    ?GetAuthError@CryptoBase@@QEAAKPEAW4SNIAuthErrOps@@PEAW4SNIAuthErrStates@@@Z; CryptoBase::GetAuthError(SNIAuthErrOps *,SNIAuthErrStates *)
0x100448c03  jmp     short loc_100448C39
0x100448c05  cmp     cs:?g_osviSNI@@3U_OSVERSIONINFOEXW@@A.dwMajorVersion, 6; _OSVERSIONINFOEXW g_osviSNI ...
0x100448c0c  jnb     short loc_100448C40
0x100448c0e  xor     edx, edx
0x100448c10  cmp     dword ptr [rdi+0D8h], 1
0x100448c17  setz    dl
0x100448c1a  add     edx, 2
0x100448c1d  mov     rcx, rdi
0x100448c20  call    ?WaitForIOCompletion@CryptoBase@@AEAAXW4SNIAuthErrOps@@@Z; CryptoBase::WaitForIOCompletion(SNIAuthErrOps)
0x100448c25  mov     r8, r14; enum SNIAuthErrStates *
0x100448c28  mov     rdx, r15; enum SNIAuthErrOps *
0x100448c2b  mov     rcx, rdi; this
0x100448c2e  call    ?GetAuthError@CryptoBase@@QEAAKPEAW4SNIAuthErrOps@@PEAW4SNIAuthErrStates@@@Z; CryptoBase::GetAuthError(SNIAuthErrOps *,SNIAuthErrStates *)
0x100448c33  mov     ebx, eax
0x100448c35  mov     [rsp+0F8h+var_B8], eax
0x100448c39  mov     esi, [rdi+30h]
0x100448c3c  mov     [rsp+0F8h+var_B4], esi
0x100448c40  jmp     loc_100448B85
0x100448c45  lea     rcx, [rsp+0F8h+var_68]; this
0x100448c4d  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x100448c52  nop
0x100448c53  jmp     short loc_100448C7B
0x100448c55  lea     r12, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100448c5c  lea     r13, aCryptobaseProc_0; "CryptoBase::ProcessAddProvider"
0x100448c63  mov     r14, [rsp+0F8h+arg_10]
0x100448c6b  mov     r15, [rsp+0F8h+arg_8]
0x100448c73  mov     esi, [rsp+0F8h+var_B4]
0x100448c77  mov     ebx, [rsp+0F8h+var_B8]
0x100448c7b  mov     rdx, gs:58h
0x100448c84  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100448c8b  mov     ecx, [rax]
0x100448c8d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100448c94  mov     edi, [rax]
0x100448c96  add     rdi, [rdx+rcx*8]
0x100448c9a  mov     rcx, [rdi+100h]
0x100448ca1  test    rcx, rcx
0x100448ca4  jnz     short loc_100448CB3
0x100448ca6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100448cac  mov     rcx, [rdi+100h]
0x100448cb3  cmp     dword ptr [rcx+22Ch], 0
0x100448cba  jz      short loc_100448CC2
0x100448cbc  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x100448cc2  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100448cc8  test    al, 1
0x100448cca  jz      short loc_100448CF2
0x100448ccc  mov     dword ptr [rsp+0F8h+var_D0], esi
0x100448cd0  mov     dword ptr [rsp+0F8h+var_D8], ebx
0x100448cd4  lea     r9, aSnidwerrorDDwo; "SNIdwError: %d{DWORD}, authState: %d{SN"...
0x100448cdb  mov     r8d, 0FD8h; int
0x100448ce1  mov     rdx, r13; char *
0x100448ce4  mov     rcx, r12; char *
0x100448ce7  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100448cec  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100448cf2  cmp     ebx, 3E5h
0x100448cf8  jz      short loc_100448D25
0x100448cfa  test    al, 1
0x100448cfc  jz      short loc_100448D1A
0x100448cfe  mov     dword ptr [rsp+0F8h+var_D8], ebx
0x100448d02  lea     r9, aSnifinalizingN; "SNIFinalizing negotiation. dwError: %d{"...
0x100448d09  mov     r8d, 0FE7h; int
0x100448d0f  mov     rdx, r13; char *
0x100448d12  mov     rcx, r12; char *
0x100448d15  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100448d1a  call    ?Release@SNIAutoEvent@@QEAAXXZ; SNIAutoEvent::Release(void)
0x100448d1f  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100448d25  test    al, 1
0x100448d27  jz      short loc_100448D54
0x100448d29  mov     eax, [r14]
0x100448d2c  mov     [rsp+0F8h+var_C8], eax
0x100448d30  mov     eax, [r15]
0x100448d33  mov     dword ptr [rsp+0F8h+var_D0], eax
0x100448d37  mov     dword ptr [rsp+0F8h+var_D8], ebx
0x100448d3b  lea     r9, aRetSnidwerrorD; "RET|SNIdwError: %d{DWORD}, errOp: %d{DW"...
0x100448d42  mov     r8d, 0FF4h; int
0x100448d48  mov     rdx, r13; char *
0x100448d4b  mov     rcx, r12; char *
0x100448d4e  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100448d53  nop
0x100448d54  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100448d5b  jz      short loc_100448D71
0x100448d5d  mov     r8d, [rsp+0F8h+var_A0]; int
0x100448d62  mov     rdx, [rsp+0F8h+var_A8]; char *
0x100448d67  mov     rcx, [rsp+0F8h+var_B0]; char *
0x100448d6c  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100448d71  mov     eax, ebx
0x100448d73  add     rsp, 0C0h
0x100448d7a  pop     r15
0x100448d7c  pop     r14
0x100448d7e  pop     r13
0x100448d80  pop     r12
0x100448d82  pop     rdi
0x100448d83  pop     rsi
0x100448d84  pop     rbx
0x100448d85  retn
```
