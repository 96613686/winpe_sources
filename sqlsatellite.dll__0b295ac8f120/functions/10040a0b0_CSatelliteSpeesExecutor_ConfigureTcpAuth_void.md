# CSatelliteSpeesExecutor::ConfigureTcpAuth(void)

- ea: `0x10040a0b0`
- end: `0x10040a513`
- name: `?ConfigureTcpAuth@CSatelliteSpeesExecutor@@AEAAJXZ`
- size: `1123`
- prototype: `__int64 __fastcall(CSatelliteSpeesExecutor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x100408970`

## callees

- `0x10040a0b0`
- `0x100480290`
- `0x100486af0`
- `0x100487cd6`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x10040a40a`
- `KERNEL32!SetEnvironmentVariableW` at `0x10040a40a`
- `KERNEL32!GetEnvironmentVariableW` at `0x10040a122`
- `KERNEL32!GetEnvironmentVariableW` at `0x10040a14f`
- `KERNEL32!GetEnvironmentVariableW` at `0x10040a17e`
- `KERNEL32!GetEnvironmentVariableW` at `0x10040a1ba`
- `KERNEL32!GetEnvironmentVariableW` at `0x10040a122`
- `KERNEL32!GetEnvironmentVariableW` at `0x10040a14f`
- `KERNEL32!GetEnvironmentVariableW` at `0x10040a17e`
- `KERNEL32!GetEnvironmentVariableW` at `0x10040a1ba`
- `KERNEL32!GetLastError` at `0x10040a261`
- `KERNEL32!GetLastError` at `0x10040a2ae`
- `KERNEL32!GetLastError` at `0x10040a303`
- `KERNEL32!GetLastError` at `0x10040a3e3`
- `KERNEL32!GetLastError` at `0x10040a414`
- `KERNEL32!GetLastError` at `0x10040a261`
- `KERNEL32!GetLastError` at `0x10040a2ae`
- `KERNEL32!GetLastError` at `0x10040a303`
- `KERNEL32!GetLastError` at `0x10040a3e3`
- `KERNEL32!GetLastError` at `0x10040a414`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10040a134`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10040a134`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040a4c7`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040a4c7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a39d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a39d`
- `sqldk!SystemThread_TlsIndex` at `0x10040a329`
- `sqldk!SystemThread_TlsOffset` at `0x10040a332`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040a34d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040a34d`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10040a12d`
- `CRYPT32!CryptBinaryToStringW` at `0x10040a2f3`
- `CRYPT32!CryptBinaryToStringW` at `0x10040a3d2`
- `CRYPT32!CryptBinaryToStringW` at `0x10040a2f3`
- `CRYPT32!CryptBinaryToStringW` at `0x10040a3d2`
- `CRYPT32!CryptHashCertificate` at `0x10040a257`
- `CRYPT32!CryptHashCertificate` at `0x10040a2a4`
- `CRYPT32!CryptHashCertificate` at `0x10040a257`
- `CRYPT32!CryptHashCertificate` at `0x10040a2a4`
- `CRYPT32!CertGetNameStringW` at `0x10040a456`
- `CRYPT32!CertGetNameStringW` at `0x10040a456`

## string_xrefs

- `0x10040a1b3`: `CERTIFICATE_PATH`
- `0x10040a38c`: `Sql\Ntdbms\extensibility\common\src\SatelliteUtils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSatelliteSpeesExecutor::ConfigureTcpAuth(CSatelliteSpeesExecutor *this)
{
  signed int v2; // edi
  wchar_t *v3; // rsi
  bool v4; // bl
  bool v5; // r12
  DWORD EnvironmentVariableW; // edi
  WCHAR *v7; // rbx
  const struct _CERT_CONTEXT *PfxFile; // rsi
  signed int LastError; // eax
  signed int v10; // eax
  DWORD v11; // r15d
  BOOL v12; // eax
  bool v13; // r14
  signed int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // rax
  struct IMemObj *v17; // r10
  unsigned __int64 v18; // rax
  signed int v19; // eax
  signed int v20; // eax
  _WORD *v21; // rcx
  __int64 v22; // rdx
  __int16 v23; // ax
  _WORD *v24; // rax
  char v25; // al
  struct ExtensibilityCertCreator::IssuerKeyInformation *cbEncoded; // [rsp+28h] [rbp-E0h]
  DWORD cbBinary[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR *v29; // [rsp+50h] [rbp-B8h]
  __int64 v30; // [rsp+58h] [rbp-B0h]
  BYTE pbBinary[272]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+178h] [rbp+70h] BYREF
  WCHAR pszNameString[256]; // [rsp+388h] [rbp+280h] BYREF
  WCHAR v34[264]; // [rsp+588h] [rbp+480h] BYREF

  v30 = -2;
  v2 = 0;
  v3 = CSatelliteGlobalContext::sm_pmo;
  memset_0(Buffer, 0, 0x208u);
  v4 = GetEnvironmentVariableW(L"SATELLITE_DISABLE_TCP", Buffer, 0x104u) == 0;
  v5 = OsInfo::IsLinux(SOS_OS_OsInfo) || GetEnvironmentVariableW(L"SATELLITE_USE_SSL", Buffer, 0x104u);
  if ( !v4 )
    *((_DWORD *)this + 789) &= ~1u;
  if ( GetEnvironmentVariableW(L"IS_WCOW", Buffer, 0x104u) )
  {
    memset_0(v34, 0, 0x208u);
    EnvironmentVariableW = GetEnvironmentVariableW(L"CERTIFICATE_PATH", v34, 0x104u);
    cbBinary[0] = 0;
    memset_0(pbBinary, 0, 0x104u);
    v7 = 0;
    v29 = 0;
    memset_0(pszNameString, 0, 0x1FEu);
    if ( EnvironmentVariableW )
    {
      LODWORD(cbEncoded) = 4096;
      PfxFile = ExtensibilityCertCreator::LoadPfxFile(v34, &word_1004A26DC, v3, 0, cbEncoded);
      if ( PfxFile )
      {
        if ( CryptHashCertificate(0, 0, 0, PfxFile->pbCertEncoded, PfxFile->cbCertEncoded, 0, cbBinary) )
          goto LABEL_19;
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( v2 >= 0 )
        {
LABEL_19:
          if ( CryptHashCertificate(0, 0, 0, PfxFile->pbCertEncoded, PfxFile->cbCertEncoded, pbBinary, cbBinary) )
            goto LABEL_20;
          v10 = GetLastError();
          v2 = v10;
          if ( v10 > 0 )
            v2 = (unsigned __int16)v10 | 0x80070000;
          if ( v2 >= 0 )
          {
LABEL_20:
            v11 = cbBinary[0];
            v2 = 0;
            cbBinary[1] = 0;
            v12 = CryptBinaryToStringW(pbBinary, cbBinary[0], 0x40000004u, 0, &cbBinary[1]);
            v13 = v12;
            if ( v12 )
              goto LABEL_24;
            v14 = GetLastError();
            v2 = v14;
            if ( v14 > 0 )
              v2 = (unsigned __int16)v14 | 0x80070000;
            if ( v2 >= 0 )
            {
LABEL_24:
              v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v16 = *(_QWORD *)(v15 + 256);
              if ( !v16 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v16 = *(_QWORD *)(v15 + 256);
              }
              v17 = *(struct IMemObj **)(*(_QWORD *)(v16 + 992) + 320LL);
              v18 = 2LL * cbBinary[1];
              if ( !is_mul_ok(cbBinary[1], 2u) )
                v18 = -1;
              v7 = (WCHAR *)operator new[](
                              v18,
                              v17,
                              1,
                              "Sql\\Ntdbms\\extensibility\\common\\src\\SatelliteUtils.cpp",
                              3801,
                              6u);
              v29 = v7;
              if ( v7 )
                v13 = CryptBinaryToStringW(pbBinary, v11, 0x40000004u, v7, &cbBinary[1]);
              else
                v2 = -2147024882;
            }
            if ( !v13 )
            {
              v19 = GetLastError();
              v2 = v19;
              if ( v19 > 0 )
                v2 = (unsigned __int16)v19 | 0x80070000;
            }
            if ( v2 >= 0 )
            {
              if ( SetEnvironmentVariableW(L"ExtensibilityCertificateHash", v7) )
                goto LABEL_39;
              v20 = GetLastError();
              v2 = v20;
              if ( v20 > 0 )
                v2 = (unsigned __int16)v20 | 0x80070000;
              if ( v2 >= 0 )
              {
LABEL_39:
                if ( CertGetNameStringW(PfxFile, 3u, 0, "2.5.4.3", pszNameString, 0x104u) == 1 )
                {
                  v2 = -2146885628;
                }
                else
                {
                  v21 = (_WORD *)((char *)this + 2622);
                  v22 = 255;
                  do
                  {
                    if ( v22 == -2147483391 )
                      break;
                    v23 = *(_WORD *)((char *)v21 + (char *)pszNameString - ((char *)this + 2622));
                    if ( !v23 )
                      break;
                    *v21++ = v23;
                    --v22;
                  }
                  while ( v22 );
                  v24 = v21 - 1;
                  if ( v22 )
                    v24 = v21;
                  *v24 = 0;
                  v2 = -2147024774;
                  if ( v22 )
                    v2 = 0;
                }
              }
            }
          }
        }
      }
      else
      {
        v2 = -2146885628;
      }
    }
    else
    {
      v2 = -2147024893;
    }
    operator delete[](v7);
  }
  v25 = CSQLSatelliteConnection::sm_useSSLAuth;
  if ( v5 )
    v25 = 1;
  CSQLSatelliteConnection::sm_useSSLAuth = v25;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x10040a0b0  mov     rax, rsp
0x10040a0b3  push    rbp
0x10040a0b4  push    r12
0x10040a0b6  push    r13
0x10040a0b8  push    r14
0x10040a0ba  push    r15
0x10040a0bc  lea     rbp, [rax-6C8h]
0x10040a0c3  sub     rsp, 7A0h
0x10040a0ca  mov     [rsp+7C0h+var_770], 0FFFFFFFFFFFFFFFEh
0x10040a0d3  mov     [rax+10h], rbx
0x10040a0d7  mov     [rax+18h], rsi
0x10040a0db  mov     [rax+20h], rdi
0x10040a0df  mov     rax, cs:__security_cookie
0x10040a0e6  xor     rax, rsp
0x10040a0e9  mov     [rbp+6C0h+var_30], rax
0x10040a0f0  mov     r13, rcx
0x10040a0f3  xor     r14d, r14d
0x10040a0f6  mov     edi, r14d
0x10040a0f9  mov     rsi, cs:?sm_pmo@CSatelliteGlobalContext@@0PEAVIMemObj@@EA; IMemObj * CSatelliteGlobalContext::sm_pmo
0x10040a100  xor     edx, edx; Val
0x10040a102  mov     r8d, 208h; Size
0x10040a108  lea     rcx, [rbp+6C0h+Buffer]; void *
0x10040a10c  call    memset_0
0x10040a111  mov     r8d, 104h; nSize
0x10040a117  lea     rdx, [rbp+6C0h+Buffer]; lpBuffer
0x10040a11b  lea     rcx, aSatelliteDisab; "SATELLITE_DISABLE_TCP"
0x10040a122  call    cs:__imp_GetEnvironmentVariableW
0x10040a128  test    eax, eax
0x10040a12a  setz    bl
0x10040a12d  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x10040a134  call    cs:__imp_?IsLinux@OsInfo@@QEBA?B_NXZ; OsInfo::IsLinux(void)
0x10040a13a  test    al, al
0x10040a13c  jnz     short loc_10040A15E
0x10040a13e  mov     r8d, 104h; nSize
0x10040a144  lea     rdx, [rbp+6C0h+Buffer]; lpBuffer
0x10040a148  lea     rcx, aSatelliteUseSs; "SATELLITE_USE_SSL"
0x10040a14f  call    cs:__imp_GetEnvironmentVariableW
0x10040a155  test    eax, eax
0x10040a157  jnz     short loc_10040A15E
0x10040a159  xor     r12b, r12b
0x10040a15c  jmp     short loc_10040A161
0x10040a15e  mov     r12b, 1
0x10040a161  test    bl, bl
0x10040a163  jnz     short loc_10040A16D
0x10040a165  and     dword ptr [r13+0C54h], 0FFFFFFFEh
0x10040a16d  mov     r8d, 104h; nSize
0x10040a173  lea     rdx, [rbp+6C0h+Buffer]; lpBuffer
0x10040a177  lea     rcx, aIsWcow; "IS_WCOW"
0x10040a17e  call    cs:__imp_GetEnvironmentVariableW
0x10040a184  mov     r15d, 1
0x10040a18a  test    eax, eax
0x10040a18c  jz      loc_10040A4CD
0x10040a192  xor     edx, edx; Val
0x10040a194  mov     r8d, 208h; Size
0x10040a19a  lea     rcx, [rbp+6C0h+var_240]; void *
0x10040a1a1  call    memset_0
0x10040a1a6  mov     r8d, 104h; nSize
0x10040a1ac  lea     rdx, [rbp+6C0h+var_240]; lpBuffer
0x10040a1b3  lea     rcx, aCertificatePat; "CERTIFICATE_PATH"
0x10040a1ba  call    cs:__imp_GetEnvironmentVariableW
0x10040a1c0  mov     edi, eax
0x10040a1c2  mov     [rsp+7C0h+cbBinary], r14d
0x10040a1c7  xor     edx, edx; Val
0x10040a1c9  mov     r8d, 104h; Size
0x10040a1cf  lea     rcx, [rsp+7C0h+pbBinary]; void *
0x10040a1d4  call    memset_0
0x10040a1d9  mov     rbx, r14
0x10040a1dc  mov     [rsp+7C0h+var_778], rbx
0x10040a1e1  xor     edx, edx; Val
0x10040a1e3  mov     r8d, 1FEh; Size
0x10040a1e9  lea     rcx, [rbp+6C0h+pszNameString]; void *
0x10040a1f0  call    memset_0
0x10040a1f5  test    edi, edi
0x10040a1f7  jnz     short loc_10040A203
0x10040a1f9  mov     edi, 80070003h
0x10040a1fe  jmp     loc_10040A4C4
0x10040a203  mov     [rsp+7C0h+cbEncoded], 1000h; struct ExtensibilityCertCreator::IssuerKeyInformation *
0x10040a20b  xor     r9d, r9d; struct IMemObj *
0x10040a20e  mov     r8, rsi; wchar_t *
0x10040a211  lea     rdx, word_1004A26DC; wchar_t *
0x10040a218  lea     rcx, [rbp+6C0h+var_240]; this
0x10040a21f  call    ?LoadPfxFile@ExtensibilityCertCreator@@YAPEBU_CERT_CONTEXT@@PEB_W0PEAVIMemObj@@PEAUIssuerKeyInformation@1@K@Z; ExtensibilityCertCreator::LoadPfxFile(wchar_t const *,wchar_t const *,IMemObj *,ExtensibilityCertCreator::IssuerKeyInformation *,ulong)
0x10040a224  mov     rsi, rax
0x10040a227  test    rax, rax
0x10040a22a  jnz     short loc_10040A236
0x10040a22c  mov     edi, 80092004h
0x10040a231  jmp     loc_10040A4C4
0x10040a236  lea     rax, [rsp+7C0h+cbBinary]
0x10040a23b  mov     [rsp+7C0h+pcbComputedHash], rax; pcbComputedHash
0x10040a240  mov     [rsp+7C0h+pbComputedHash], r14; pbComputedHash
0x10040a245  mov     eax, [rsi+10h]
0x10040a248  mov     [rsp+7C0h+cbEncoded], eax; cbEncoded
0x10040a24c  mov     r9, [rsi+8]; pbEncoded
0x10040a250  xor     r8d, r8d; dwFlags
0x10040a253  xor     edx, edx; Algid
0x10040a255  xor     ecx, ecx; hCryptProv
0x10040a257  call    cs:__imp_CryptHashCertificate
0x10040a25d  test    eax, eax
0x10040a25f  jnz     short loc_10040A27E
0x10040a261  call    cs:__imp_GetLastError
0x10040a267  mov     edi, eax
0x10040a269  test    eax, eax
0x10040a26b  jle     short loc_10040A276
0x10040a26d  movzx   edi, ax
0x10040a270  or      edi, 80070000h
0x10040a276  test    edi, edi
0x10040a278  js      loc_10040A4C4
0x10040a27e  lea     rax, [rsp+7C0h+cbBinary]
0x10040a283  mov     [rsp+7C0h+pcbComputedHash], rax; pcbComputedHash
0x10040a288  lea     rax, [rsp+7C0h+pbBinary]
0x10040a28d  mov     [rsp+7C0h+pbComputedHash], rax; pbComputedHash
0x10040a292  mov     eax, [rsi+10h]
0x10040a295  mov     [rsp+7C0h+cbEncoded], eax; cbEncoded
0x10040a299  mov     r9, [rsi+8]; pbEncoded
0x10040a29d  xor     r8d, r8d; dwFlags
0x10040a2a0  xor     edx, edx; Algid
0x10040a2a2  xor     ecx, ecx; hCryptProv
0x10040a2a4  call    cs:__imp_CryptHashCertificate
0x10040a2aa  test    eax, eax
0x10040a2ac  jnz     short loc_10040A2CB
0x10040a2ae  call    cs:__imp_GetLastError
0x10040a2b4  mov     edi, eax
0x10040a2b6  test    eax, eax
0x10040a2b8  jle     short loc_10040A2C3
0x10040a2ba  movzx   edi, ax
0x10040a2bd  or      edi, 80070000h
0x10040a2c3  test    edi, edi
0x10040a2c5  js      loc_10040A4C4
0x10040a2cb  mov     r15d, [rsp+7C0h+cbBinary]
0x10040a2d0  mov     edi, r14d
0x10040a2d3  mov     [rsp+7C0h+cbBinary+4], r14d
0x10040a2d8  lea     rax, [rsp+7C0h+cbBinary+4]
0x10040a2dd  mov     qword ptr [rsp+7C0h+cbEncoded], rax; pcchString
0x10040a2e2  xor     r9d, r9d; pszString
0x10040a2e5  mov     r8d, 40000004h; dwFlags
0x10040a2eb  mov     edx, r15d; cbBinary
0x10040a2ee  lea     rcx, [rsp+7C0h+pbBinary]; pbBinary
0x10040a2f3  call    cs:__imp_CryptBinaryToStringW
0x10040a2f9  test    eax, eax
0x10040a2fb  setnz   r14b
0x10040a2ff  test    eax, eax
0x10040a301  jnz     short loc_10040A320
0x10040a303  call    cs:__imp_GetLastError
0x10040a309  mov     edi, eax
0x10040a30b  test    eax, eax
0x10040a30d  jle     short loc_10040A318
0x10040a30f  movzx   edi, ax
0x10040a312  or      edi, 80070000h
0x10040a318  test    edi, edi
0x10040a31a  js      loc_10040A3DE
0x10040a320  mov     rdx, gs:58h
0x10040a329  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040a330  mov     ecx, [rax]
0x10040a332  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040a339  mov     ebx, [rax]
0x10040a33b  add     rbx, [rdx+rcx*8]
0x10040a33f  mov     rax, [rbx+100h]
0x10040a346  test    rax, rax
0x10040a349  jnz     short loc_10040A35A
0x10040a34b  xor     ecx, ecx
0x10040a34d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040a353  mov     rax, [rbx+100h]
0x10040a35a  mov     rax, [rax+3E0h]
0x10040a361  mov     r10, [rax+140h]
0x10040a368  mov     ecx, [rsp+7C0h+cbBinary+4]
0x10040a36c  mov     eax, 2
0x10040a371  mul     rcx
0x10040a374  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10040a37b  cmovo   rax, rcx
0x10040a37f  mov     byte ptr [rsp+7C0h+pbComputedHash], 6
0x10040a384  mov     [rsp+7C0h+cbEncoded], 0ED9h
0x10040a38c  lea     r9, aSqlNtdbmsExten_1; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x10040a393  lea     r8d, [rcx+2]
0x10040a397  mov     rdx, r10
0x10040a39a  mov     rcx, rax
0x10040a39d  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10040a3a3  mov     rbx, rax
0x10040a3a6  mov     [rsp+7C0h+var_778], rax
0x10040a3ab  test    rax, rax
0x10040a3ae  jnz     short loc_10040A3B7
0x10040a3b0  mov     edi, 8007000Eh
0x10040a3b5  jmp     short loc_10040A3DE
0x10040a3b7  lea     rax, [rsp+7C0h+cbBinary+4]
0x10040a3bc  mov     qword ptr [rsp+7C0h+cbEncoded], rax; pcchString
0x10040a3c1  mov     r9, rbx; pszString
0x10040a3c4  mov     r8d, 40000004h; dwFlags
0x10040a3ca  mov     edx, r15d; cbBinary
0x10040a3cd  lea     rcx, [rsp+7C0h+pbBinary]; pbBinary
0x10040a3d2  call    cs:__imp_CryptBinaryToStringW
0x10040a3d8  test    eax, eax
0x10040a3da  setnz   r14b
0x10040a3de  test    r14b, r14b
0x10040a3e1  jnz     short loc_10040A3F8
0x10040a3e3  call    cs:__imp_GetLastError
0x10040a3e9  mov     edi, eax
0x10040a3eb  test    eax, eax
0x10040a3ed  jle     short loc_10040A3F8
0x10040a3ef  movzx   edi, ax
0x10040a3f2  or      edi, 80070000h
0x10040a3f8  test    edi, edi
0x10040a3fa  js      loc_10040A4BE
0x10040a400  mov     rdx, rbx; lpValue
0x10040a403  lea     rcx, aExtensibilityc; "ExtensibilityCertificateHash"
0x10040a40a  call    cs:__imp_SetEnvironmentVariableW
0x10040a410  test    eax, eax
0x10040a412  jnz     short loc_10040A431
0x10040a414  call    cs:__imp_GetLastError
0x10040a41a  mov     edi, eax
0x10040a41c  test    eax, eax
0x10040a41e  jle     short loc_10040A429
0x10040a420  movzx   edi, ax
0x10040a423  or      edi, 80070000h
0x10040a429  test    edi, edi
0x10040a42b  js      loc_10040A4BE
0x10040a431  mov     dword ptr [rsp+7C0h+pbComputedHash], 104h; cchNameString
0x10040a439  lea     rax, [rbp+6C0h+pszNameString]
0x10040a440  mov     qword ptr [rsp+7C0h+cbEncoded], rax; pszNameString
0x10040a445  lea     r9, a2543; "2.5.4.3"
0x10040a44c  xor     r8d, r8d; dwFlags
0x10040a44f  lea     edx, [r8+3]; dwType
0x10040a453  mov     rcx, rsi; pCertContext
0x10040a456  call    cs:__imp_CertGetNameStringW
0x10040a45c  cmp     eax, 1
0x10040a45f  jnz     short loc_10040A468
0x10040a461  mov     edi, 80092004h
0x10040a466  jmp     short loc_10040A4BE
0x10040a468  lea     rcx, [r13+0A3Eh]
0x10040a46f  mov     edx, 0FFh
0x10040a474  lea     r8, [rbp+6C0h+pszNameString]
0x10040a47b  sub     r8, rcx
0x10040a47e  xchg    ax, ax
0x10040a480  lea     rax, [rdx+7FFFFEFFh]
0x10040a487  test    rax, rax
0x10040a48a  jz      short loc_10040A4A3
0x10040a48c  movzx   eax, word ptr [r8+rcx]
0x10040a491  test    ax, ax
0x10040a494  jz      short loc_10040A4A3
0x10040a496  mov     [rcx], ax
0x10040a499  add     rcx, 2
0x10040a49d  sub     rdx, 1
0x10040a4a1  jnz     short loc_10040A480
0x10040a4a3  lea     rax, [rcx-2]
0x10040a4a7  test    rdx, rdx
0x10040a4aa  cmovnz  rax, rcx
0x10040a4ae  xor     ecx, ecx
0x10040a4b0  mov     [rax], cx
0x10040a4b3  mov     edi, 8007007Ah
0x10040a4b8  test    rdx, rdx
0x10040a4bb  cmovnz  edi, ecx
0x10040a4be  mov     r15d, 1
0x10040a4c4  mov     rcx, rbx
0x10040a4c7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10040a4cd  movzx   eax, cs:?sm_useSSLAuth@CSQLSatelliteConnection@@2_NA; bool CSQLSatelliteConnection::sm_useSSLAuth
0x10040a4d4  test    r12b, r12b
0x10040a4d7  cmovnz  eax, r15d
0x10040a4db  mov     cs:?sm_useSSLAuth@CSQLSatelliteConnection@@2_NA, al; bool CSQLSatelliteConnection::sm_useSSLAuth
0x10040a4e1  mov     eax, edi
0x10040a4e3  mov     rcx, [rbp+6C0h+var_30]
0x10040a4ea  xor     rcx, rsp; StackCookie
0x10040a4ed  call    __security_check_cookie
0x10040a4f2  lea     r11, [rsp+7C0h+var_20]
0x10040a4fa  mov     rbx, [r11+38h]
0x10040a4fe  mov     rsi, [r11+40h]
0x10040a502  mov     rdi, [r11+48h]
0x10040a506  mov     rsp, r11
0x10040a509  pop     r15
0x10040a50b  pop     r14
0x10040a50d  pop     r13
0x10040a50f  pop     r12
0x10040a511  pop     rbp
0x10040a512  retn
```
