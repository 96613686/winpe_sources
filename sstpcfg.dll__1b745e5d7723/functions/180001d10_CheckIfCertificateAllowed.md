# CheckIfCertificateAllowed

- ea: `0x180001d10`
- end: `0x18000246c`
- name: `CheckIfCertificateAllowed`
- size: `1884`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task`

## callees

- `0x180001d10`
- `0x180003510`
- `0x180003820`
- `0x180003aac`
- `0x180003e10`
- `0x180004000`
- `0x180004f10`
- `0x18000a014`
- `0x18000a044`
- `0x18000a414`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001e61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001e61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002405`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001f15`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001f8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001f15`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001f8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800022d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002349`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800022d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002349`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800022c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002337`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800022c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002337`
- `CRYPT32!CertFreeCertificateContext` at `0x180002413`
- `CRYPT32!CertFreeCertificateContext` at `0x180002421`
- `CRYPT32!CertFreeCertificateContext` at `0x18000242f`
- `CRYPT32!CertFreeCertificateContext` at `0x180002413`
- `CRYPT32!CertFreeCertificateContext` at `0x180002421`
- `CRYPT32!CertFreeCertificateContext` at `0x18000242f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002358`
- `HTTPAPI!HttpInitialize` at `0x180001db8`
- `HTTPAPI!HttpInitialize` at `0x180001db8`
- `HTTPAPI!HttpTerminate` at `0x18000243a`
- `HTTPAPI!HttpTerminate` at `0x18000243a`

## string_xrefs

- `0x180001e53`: `System\CurrentControlSet\Services\SstpSvc\Parameters`
- `0x180001eac`: `Unable to open the SSTPSVC Params Key: %d`
- `0x180001fd8`: `Unable to open the SSTPSVC Params Key: %d`
- `0x180001e0e`: `HttpInitialize for configuration Failed: %d`

## pseudocode

```c
__int64 __fastcall CheckIfCertificateAllowed(__int64 a1, __int64 a2, __int64 a3)
{
  const CERT_CONTEXT *v6; // rsi
  const CERT_CONTEXT *v7; // rdi
  const CERT_CONTEXT *v8; // r12
  unsigned int CertificateBindingFromAddress; // ebx
  __int64 v10; // r8
  _QWORD *v11; // rax
  __int64 v12; // rdx
  const wchar_t *v13; // rdx
  unsigned __int16 v14; // di
  __int64 v15; // r8
  __int64 v16; // r8
  const wchar_t *v17; // rdx
  __int64 v18; // rdx
  const wchar_t *v19; // r8
  int CertificateFromHash; // eax
  int CertificateFromName; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r15
  unsigned int CertificateFromSslInfo; // eax
  __int64 v27; // r8
  HKEY *v28; // rdi
  unsigned int v29; // eax
  HANDLE ProcessHeap; // rax
  LPVOID v31; // rax
  __int64 v32; // r8
  _QWORD *v33; // rax
  __int64 v34; // rdx
  HANDLE v35; // rax
  LPVOID v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  const CERT_CONTEXT *v40; // [rsp+50h] [rbp-B0h] BYREF
  char v41; // [rsp+58h] [rbp-A8h] BYREF
  char v42; // [rsp+59h] [rbp-A7h] BYREF
  char v43; // [rsp+5Ah] [rbp-A6h] BYREF
  char v44; // [rsp+5Bh] [rbp-A5h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  const CERT_CONTEXT *v47; // [rsp+68h] [rbp-98h] BYREF
  int v48; // [rsp+70h] [rbp-90h]
  DWORD Type; // [rsp+74h] [rbp-8Ch] BYREF
  int v50; // [rsp+78h] [rbp-88h] BYREF
  const CERT_CONTEXT *v51; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  ULONG v53; // [rsp+90h] [rbp-70h] BYREF
  ULONG v54; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v55; // [rsp+98h] [rbp-68h] BYREF
  HKEY *v56; // [rsp+A0h] [rbp-60h] BYREF
  int v57; // [rsp+B0h] [rbp-50h] BYREF
  char v58[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  cbData = 4;
  v55 = 0;
  v56 = 0;
  v6 = 0;
  v53 = 0;
  v7 = 0;
  v54 = 0;
  v50 = 0;
  v8 = 0;
  v47 = 0;
  v40 = 0;
  v51 = 0;
  v44 = 0;
  v43 = 0;
  v42 = 0;
  v41 = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  v57 = 0;
  v48 = 2;
  memset_0(v58, 0, sizeof(v58));
  CertificateBindingFromAddress = HttpInitialize((HTTPAPI_VERSION)2, 2u, 0);
  if ( !CertificateBindingFromAddress )
  {
    CertificateBindingFromAddress = RegOpenKeyExW(
                                      HKEY_LOCAL_MACHINE,
                                      L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters",
                                      0,
                                      0x2001Fu,
                                      &hKey);
    if ( CertificateBindingFromAddress )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_14;
      }
      v12 = 192;
LABEL_13:
      WPP_SF_d(v11[2], v12, v10, CertificateBindingFromAddress);
LABEL_14:
      if ( !(_QWORD)xmmword_1800146E0 )
      {
LABEL_105:
        if ( hKey )
          RegCloseKey(hKey);
        if ( v6 )
          CertFreeCertificateContext(v6);
        if ( v7 )
          CertFreeCertificateContext(v7);
        if ( v8 )
          CertFreeCertificateContext(v8);
        HttpTerminate(2u, 0);
        return CertificateBindingFromAddress;
      }
      v13 = L"Unable to open the SSTPSVC Params Key: %d";
LABEL_16:
      LOWORD(v57) = 0;
      FormatRRASErrorString(&v57, v13, CertificateBindingFromAddress);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v57);
      goto LABEL_105;
    }
    cbData = 4;
    CertificateBindingFromAddress = RegQueryValueExW(hKey, L"ListenerPort", 0, &Type, Data, &cbData);
    if ( CertificateBindingFromAddress )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_14;
      }
      v12 = 193;
      goto LABEL_13;
    }
    v14 = *(_WORD *)Data;
    cbData = 4;
    CertificateBindingFromAddress = RegQueryValueExW(hKey, L"UseHttps", 0, &Type, Data, &cbData);
    if ( CertificateBindingFromAddress )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, v15, CertificateBindingFromAddress);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_104;
      v16 = CertificateBindingFromAddress;
      v17 = L"Unable to open the SSTPSVC Params Key: %d";
      goto LABEL_29;
    }
    if ( !*(_WORD *)Data )
      return 0;
    if ( !v14 )
      v14 = 443;
    if ( a2 && *(_DWORD *)(a2 + 8) == 20 )
    {
      CertificateFromHash = GetCertificateFromHash(0);
    }
    else
    {
      if ( !a3 || *(_DWORD *)(a3 + 8) != 32 )
      {
        if ( !a1 )
        {
          CertificateBindingFromAddress = 87;
          goto LABEL_104;
        }
        CertificateFromName = GetCertificateFromName(a1, &v47, &v50);
        v6 = v47;
        if ( CertificateFromName || v50 != 1 || !v47 )
          goto LABEL_39;
        goto LABEL_47;
      }
      CertificateFromHash = GetCertificateFromSha256Hash(0);
    }
    v6 = v47;
    if ( CertificateFromHash )
    {
LABEL_39:
      CertificateBindingFromAddress = 1168;
      goto LABEL_104;
    }
LABEL_47:
    CertificateBindingFromAddress = GetCertificateBindingFromAddress(2, v14, (void **)&v55, &v53);
    if ( CertificateBindingFromAddress )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, v24, v14);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_104;
      v16 = v14;
      v17 = L"Unable to get cert binding for V4 port: %d.";
      goto LABEL_29;
    }
    v25 = v55;
    if ( v55 )
    {
      LOBYTE(v23) = 1;
      CertificateFromSslInfo = GetCertificateFromSslInfo(v23, v55, &v40);
      CertificateBindingFromAddress = CertificateFromSslInfo;
      if ( CertificateFromSslInfo != -2146885628 )
      {
        if ( CertificateFromSslInfo )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 196);
          }
          v18 = xmmword_1800146E0;
          if ( !(_QWORD)xmmword_1800146E0 )
            goto LABEL_104;
          v19 = L"Unable to get cert for v4";
          goto LABEL_30;
        }
      }
    }
    CertificateBindingFromAddress = GetCertificateBindingFromAddress(23, v14, (void **)&v56, &v54);
    if ( CertificateBindingFromAddress )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, v27, v14);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_104;
      v16 = v14;
      v17 = L"Unable to get cert binding for V6 port: %d.";
LABEL_29:
      LOWORD(v57) = 0;
      FormatRRASErrorString(&v57, v17, v16);
      v18 = xmmword_1800146E0;
      v19 = (const wchar_t *)&v57;
LABEL_30:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v18, v19);
LABEL_104:
      v7 = v40;
      goto LABEL_105;
    }
    v28 = v56;
    if ( v56 )
    {
      v29 = GetCertificateFromSslInfo(0, v56, &v51);
      CertificateBindingFromAddress = v29;
      if ( v29 != -2146885628 && v29 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 198);
        }
        if ( (_QWORD)xmmword_1800146E0 )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
            gSstpCfgEtwContext,
            xmmword_1800146E0,
            L"Unable to get cert for v6");
        v8 = v51;
        goto LABEL_104;
      }
      v8 = v51;
    }
    phkResult = v28;
    v7 = v40;
    CertificateBindingFromAddress = handleV4V6RegCertMismatch(
                                      (__int64)v6,
                                      (__int64)v40,
                                      v25,
                                      (__int64)v8,
                                      (__int64)phkResult,
                                      &v44,
                                      &v43,
                                      &v42,
                                      &v41);
    if ( CertificateBindingFromAddress )
      goto LABEL_105;
    ProcessHeap = GetProcessHeap();
    v31 = HeapAlloc(ProcessHeap, 8u, 0x20u);
    *(_QWORD *)(a3 + 16) = v31;
    if ( v31 )
    {
      v35 = GetProcessHeap();
      v36 = HeapAlloc(v35, 8u, 0x14u);
      *(_QWORD *)(a2 + 16) = v36;
      if ( v36 )
      {
        LOBYTE(v37) = 3;
        CertificateBindingFromAddress = GetHashFromCertificate(v6, v37, v36, *(_QWORD *)(a3 + 16));
        if ( !CertificateBindingFromAddress )
        {
          *(_DWORD *)(a3 + 8) = 32;
          *(_DWORD *)(a2 + 8) = 20;
          goto LABEL_105;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, v38, CertificateBindingFromAddress);
        }
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_105;
        v13 = L"Unable to get Hash from cert name: %d";
        goto LABEL_16;
      }
      CertificateBindingFromAddress = GetLastError();
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
LABEL_88:
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_105;
        v13 = L"HeapAlloc failed and returned %d";
        goto LABEL_16;
      }
      v34 = 200;
    }
    else
    {
      CertificateBindingFromAddress = GetLastError();
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_88;
      }
      v34 = 199;
    }
    WPP_SF_d(v33[2], v34, v32, CertificateBindingFromAddress);
    goto LABEL_88;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, WPP_GLOBAL_Control, CertificateBindingFromAddress);
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v57) = 0;
    FormatRRASErrorString(&v57, L"HttpInitialize for configuration Failed: %d", CertificateBindingFromAddress);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v57);
  }
  return CertificateBindingFromAddress;
}

```

## disassembly

```asm
0x180001d10  mov     [rsp-8+arg_18], rbx
0x180001d15  push    rbp
0x180001d16  push    rsi
0x180001d17  push    rdi
0x180001d18  push    r12
0x180001d1a  push    r13
0x180001d1c  push    r14
0x180001d1e  push    r15
0x180001d20  lea     rbp, [rsp-7C0h]
0x180001d28  sub     rsp, 8C0h
0x180001d2f  mov     rax, cs:__security_cookie
0x180001d36  xor     rax, rsp
0x180001d39  mov     [rbp+7F0h+var_40], rax
0x180001d40  mov     r15, rcx
0x180001d43  mov     [rsp+8F0h+cbData], 4
0x180001d4b  xor     ecx, ecx
0x180001d4d  mov     r14, r8
0x180001d50  mov     r13, rdx
0x180001d53  mov     [rbp+7F0h+var_858], rcx
0x180001d57  mov     [rbp+7F0h+var_850], rcx
0x180001d5b  mov     esi, ecx
0x180001d5d  mov     [rbp+7F0h+var_860], ecx
0x180001d60  mov     edi, ecx
0x180001d62  lea     ebx, [rcx+2]
0x180001d65  mov     [rbp+7F0h+var_85C], ecx
0x180001d68  mov     [rsp+8F0h+var_878], ecx
0x180001d6c  mov     r12d, ecx
0x180001d6f  mov     [rsp+8F0h+var_888], rcx
0x180001d74  xor     edx, edx; Val
0x180001d76  mov     [rsp+8F0h+var_8A0], rcx
0x180001d7b  mov     r8d, 7FCh; Size
0x180001d81  mov     [rbp+7F0h+var_870], rcx
0x180001d85  mov     [rsp+8F0h+var_895], cl
0x180001d89  mov     [rsp+8F0h+var_896], cl
0x180001d8d  mov     [rsp+8F0h+var_897], cl
0x180001d91  mov     [rsp+8F0h+var_898], cl
0x180001d95  mov     [rbp+7F0h+hKey], rcx
0x180001d99  mov     [rsp+8F0h+Type], ecx
0x180001d9d  mov     dword ptr [rsp+8F0h+Data], ecx
0x180001da1  mov     [rbp+7F0h+var_840], ecx
0x180001da4  lea     rcx, [rbp+7F0h+var_83C]; void *
0x180001da8  mov     [rsp+8F0h+var_880], ebx
0x180001dac  call    memset_0
0x180001db1  xor     r8d, r8d; pReserved
0x180001db4  mov     edx, ebx; Flags
0x180001db6  mov     ecx, ebx; Version
0x180001db8  call    cs:__imp_HttpInitialize
0x180001dbe  mov     ebx, eax
0x180001dc0  xor     eax, eax
0x180001dc2  test    ebx, ebx
0x180001dc4  jz      short loc_180001E41
0x180001dc6  mov     r8, cs:WPP_GLOBAL_Control
0x180001dcd  lea     rcx, WPP_GLOBAL_Control
0x180001dd4  cmp     r8, rcx
0x180001dd7  jz      short loc_180001DFA
0x180001dd9  test    byte ptr [r8+1Ch], 40h
0x180001dde  jz      short loc_180001DFA
0x180001de0  cmp     byte ptr [r8+19h], 1
0x180001de5  jb      short loc_180001DFA
0x180001de7  mov     rcx, [r8+10h]
0x180001deb  mov     edx, 0BFh
0x180001df0  mov     r9d, ebx
0x180001df3  call    WPP_SF_d
0x180001df8  xor     eax, eax
0x180001dfa  cmp     qword ptr cs:xmmword_1800146E0, rax
0x180001e01  jz      loc_180002440
0x180001e07  mov     r8d, ebx
0x180001e0a  mov     word ptr [rbp+7F0h+var_840], ax
0x180001e0e  lea     rdx, aHttpinitialize_0; "HttpInitialize for configuration Failed"...
0x180001e15  lea     rcx, [rbp+7F0h+var_840]
0x180001e19  call    FormatRRASErrorString
0x180001e1e  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180001e25  lea     r8, [rbp+7F0h+var_840]
0x180001e29  mov     rcx, cs:gSstpCfgEtwContext
0x180001e30  mov     rax, cs:gSstpCfgTemplateFunc
0x180001e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e3c  jmp     loc_180002440
0x180001e41  lea     rax, [rbp+7F0h+hKey]
0x180001e45  mov     r9d, 2001Fh; samDesired
0x180001e4b  xor     r8d, r8d; ulOptions
0x180001e4e  mov     [rsp+8F0h+phkResult], rax; phkResult
0x180001e53  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ss"...
0x180001e5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001e61  call    cs:__imp_RegOpenKeyExW
0x180001e67  mov     ebx, eax
0x180001e69  test    eax, eax
0x180001e6b  jz      short loc_180001EE6
0x180001e6d  mov     rax, cs:WPP_GLOBAL_Control
0x180001e74  lea     rcx, WPP_GLOBAL_Control
0x180001e7b  cmp     rax, rcx
0x180001e7e  jz      short loc_180001E9D
0x180001e80  test    byte ptr [rax+1Ch], 40h
0x180001e84  jz      short loc_180001E9D
0x180001e86  cmp     byte ptr [rax+19h], 1
0x180001e8a  jb      short loc_180001E9D
0x180001e8c  mov     edx, 0C0h
0x180001e91  mov     rcx, [rax+10h]
0x180001e95  mov     r9d, ebx
0x180001e98  call    WPP_SF_d
0x180001e9d  xor     ecx, ecx
0x180001e9f  cmp     qword ptr cs:xmmword_1800146E0, rcx
0x180001ea6  jz      loc_1800023FC
0x180001eac  lea     rdx, aUnableToOpenTh; "Unable to open the SSTPSVC Params Key: "...
0x180001eb3  mov     word ptr [rbp+7F0h+var_840], cx
0x180001eb7  mov     r8d, ebx
0x180001eba  lea     rcx, [rbp+7F0h+var_840]
0x180001ebe  call    FormatRRASErrorString
0x180001ec3  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180001eca  lea     r8, [rbp+7F0h+var_840]
0x180001ece  mov     rcx, cs:gSstpCfgEtwContext
0x180001ed5  mov     rax, cs:gSstpCfgTemplateFunc
0x180001edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ee1  jmp     loc_1800023FC
0x180001ee6  mov     rcx, [rbp+7F0h+hKey]; hKey
0x180001eea  lea     rax, [rsp+8F0h+cbData]
0x180001eef  mov     [rsp+8F0h+lpcbData], rax; lpcbData
0x180001ef4  lea     r9, [rsp+8F0h+Type]; lpType
0x180001ef9  lea     rax, [rsp+8F0h+Data]
0x180001efe  mov     [rsp+8F0h+cbData], 4
0x180001f06  xor     r8d, r8d; lpReserved
0x180001f09  mov     [rsp+8F0h+phkResult], rax; lpData
0x180001f0e  lea     rdx, ValueName; "ListenerPort"
0x180001f15  call    cs:__imp_RegQueryValueExW
0x180001f1b  mov     ebx, eax
0x180001f1d  test    eax, eax
0x180001f1f  jz      short loc_180001F56
0x180001f21  mov     rax, cs:WPP_GLOBAL_Control
0x180001f28  lea     rcx, WPP_GLOBAL_Control
0x180001f2f  cmp     rax, rcx
0x180001f32  jz      loc_180001E9D
0x180001f38  test    byte ptr [rax+1Ch], 40h
0x180001f3c  jz      loc_180001E9D
0x180001f42  cmp     byte ptr [rax+19h], 1
0x180001f46  jb      loc_180001E9D
0x180001f4c  mov     edx, 0C1h
0x180001f51  jmp     loc_180001E91
0x180001f56  mov     rcx, [rbp+7F0h+hKey]; hKey
0x180001f5a  lea     rax, [rsp+8F0h+cbData]
0x180001f5f  movzx   edi, word ptr [rsp+8F0h+Data]
0x180001f64  lea     r9, [rsp+8F0h+Type]; lpType
0x180001f69  mov     [rsp+8F0h+lpcbData], rax; lpcbData
0x180001f6e  lea     rdx, aUsehttps; "UseHttps"
0x180001f75  lea     rax, [rsp+8F0h+Data]
0x180001f7a  mov     [rsp+8F0h+cbData], 4
0x180001f82  xor     r8d, r8d; lpReserved
0x180001f85  mov     [rsp+8F0h+phkResult], rax; lpData
0x180001f8a  call    cs:__imp_RegQueryValueExW
0x180001f90  mov     ebx, eax
0x180001f92  test    eax, eax
0x180001f94  jz      short loc_18000200F
0x180001f96  mov     rax, cs:WPP_GLOBAL_Control
0x180001f9d  lea     rcx, WPP_GLOBAL_Control
0x180001fa4  cmp     rax, rcx
0x180001fa7  jz      short loc_180001FC6
0x180001fa9  test    byte ptr [rax+1Ch], 40h
0x180001fad  jz      short loc_180001FC6
0x180001faf  cmp     byte ptr [rax+19h], 1
0x180001fb3  jb      short loc_180001FC6
0x180001fb5  mov     rcx, [rax+10h]
0x180001fb9  mov     edx, 0C2h
0x180001fbe  mov     r9d, ebx
0x180001fc1  call    WPP_SF_d
0x180001fc6  xor     ecx, ecx
0x180001fc8  cmp     qword ptr cs:xmmword_1800146E0, rcx
0x180001fcf  jz      loc_1800023F7
0x180001fd5  mov     r8d, ebx
0x180001fd8  lea     rdx, aUnableToOpenTh; "Unable to open the SSTPSVC Params Key: "...
0x180001fdf  mov     word ptr [rbp+7F0h+var_840], cx
0x180001fe3  lea     rcx, [rbp+7F0h+var_840]
0x180001fe7  call    FormatRRASErrorString
0x180001fec  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180001ff3  lea     r8, [rbp+7F0h+var_840]
0x180001ff7  mov     rcx, cs:gSstpCfgEtwContext
0x180001ffe  mov     rax, cs:gSstpCfgTemplateFunc
0x180002005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000200a  jmp     loc_1800023F7
0x18000200f  xor     ebx, ebx
0x180002011  cmp     word ptr [rsp+8F0h+Data], bx
0x180002016  jnz     short loc_18000201F
0x180002018  xor     eax, eax
0x18000201a  jmp     loc_180002442
0x18000201f  cmp     bx, di
0x180002022  jnz     short loc_180002029
0x180002024  mov     edi, 1BBh
0x180002029  test    r13, r13
0x18000202c  jz      short loc_18000205D
0x18000202e  cmp     dword ptr [r13+8], 14h
0x180002033  jnz     short loc_18000205D
0x180002035  mov     r8, [r13+10h]
0x180002039  lea     r9, [rsp+8F0h+var_888]
0x18000203e  mov     edx, 14h
0x180002043  xor     ecx, ecx; Source
0x180002045  call    GetCertificateFromHash
0x18000204a  mov     rsi, [rsp+8F0h+var_888]
0x18000204f  test    eax, eax
0x180002051  jz      short loc_1800020B0
0x180002053  mov     ebx, 490h
0x180002058  jmp     loc_1800023F7
0x18000205d  test    r14, r14
0x180002060  jz      short loc_180002080
0x180002062  cmp     dword ptr [r14+8], 20h ; ' '
0x180002067  jnz     short loc_180002080
0x180002069  mov     r8, [r14+10h]
0x18000206d  lea     r9, [rsp+8F0h+var_888]
0x180002072  mov     edx, 20h ; ' '
0x180002077  xor     ecx, ecx; Source
0x180002079  call    GetCertificateFromSha256Hash
0x18000207e  jmp     short loc_18000204A
0x180002080  test    r15, r15
0x180002083  jz      loc_1800023F2
0x180002089  lea     r8, [rsp+8F0h+var_878]
0x18000208e  mov     rcx, r15
0x180002091  lea     rdx, [rsp+8F0h+var_888]
0x180002096  call    GetCertificateFromName
0x18000209b  mov     rsi, [rsp+8F0h+var_888]
0x1800020a0  test    eax, eax
0x1800020a2  jnz     short loc_180002053
0x1800020a4  cmp     [rsp+8F0h+var_878], 1
0x1800020a9  jnz     short loc_180002053
0x1800020ab  test    rsi, rsi
0x1800020ae  jz      short loc_180002053
0x1800020b0  movzx   edi, di
0x1800020b3  lea     r9, [rbp+7F0h+var_860]
0x1800020b7  mov     edx, edi
0x1800020b9  lea     r8, [rbp+7F0h+var_858]
0x1800020bd  mov     ecx, 2
0x1800020c2  call    GetCertificateBindingFromAddress
0x1800020c7  mov     ebx, eax
0x1800020c9  test    eax, eax
0x1800020cb  jz      short loc_18000211B
0x1800020cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800020d4  lea     rcx, WPP_GLOBAL_Control
0x1800020db  cmp     rax, rcx
0x1800020de  jz      short loc_1800020FD
0x1800020e0  test    byte ptr [rax+1Ch], 40h
0x1800020e4  jz      short loc_1800020FD
0x1800020e6  cmp     byte ptr [rax+19h], 1
0x1800020ea  jb      short loc_1800020FD
0x1800020ec  mov     rcx, [rax+10h]
0x1800020f0  mov     edx, 0C3h
0x1800020f5  mov     r9d, edi
0x1800020f8  call    WPP_SF_d
0x1800020fd  xor     ecx, ecx
0x1800020ff  cmp     qword ptr cs:xmmword_1800146E0, rcx
0x180002106  jz      loc_1800023F7
0x18000210c  mov     r8d, edi
0x18000210f  lea     rdx, aUnableToGetCer_0; "Unable to get cert binding for V4 port:"...
0x180002116  jmp     loc_180001FDF
0x18000211b  mov     r15, [rbp+7F0h+var_858]
0x18000211f  test    r15, r15
0x180002122  jz      short loc_180002189
0x180002124  lea     r8, [rsp+8F0h+var_8A0]
0x180002129  mov     rdx, r15
0x18000212c  mov     cl, 1
0x18000212e  call    GetCertificateFromSslInfo
0x180002133  mov     ebx, eax
0x180002135  cmp     eax, 80092004h
0x18000213a  jz      short loc_180002189
0x18000213c  test    eax, eax
0x18000213e  jz      short loc_180002189
0x180002140  mov     rax, cs:WPP_GLOBAL_Control
0x180002147  lea     rcx, WPP_GLOBAL_Control
0x18000214e  cmp     rax, rcx
0x180002151  jz      short loc_18000216D
0x180002153  test    byte ptr [rax+1Ch], 40h
0x180002157  jz      short loc_18000216D
0x180002159  cmp     byte ptr [rax+19h], 1
0x18000215d  jb      short loc_18000216D
0x18000215f  mov     rcx, [rax+10h]
0x180002163  mov     edx, 0C4h
0x180002168  call    WPP_SF_
0x18000216d  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180002174  test    rdx, rdx
0x180002177  jz      loc_1800023F7
0x18000217d  lea     r8, aUnableToGetCer; "Unable to get cert for v4"
0x180002184  jmp     loc_180001FF7
0x180002189  mov     ecx, 17h
0x18000218e  lea     r9, [rbp+7F0h+var_85C]
0x180002192  lea     r8, [rbp+7F0h+var_850]
0x180002196  mov     edx, edi
0x180002198  call    GetCertificateBindingFromAddress
0x18000219d  mov     ebx, eax
0x18000219f  test    eax, eax
0x1800021a1  jz      short loc_1800021F1
0x1800021a3  mov     rax, cs:WPP_GLOBAL_Control
0x1800021aa  lea     rcx, WPP_GLOBAL_Control
0x1800021b1  cmp     rax, rcx
0x1800021b4  jz      short loc_1800021D3
0x1800021b6  test    byte ptr [rax+1Ch], 40h
0x1800021ba  jz      short loc_1800021D3
0x1800021bc  cmp     byte ptr [rax+19h], 1
0x1800021c0  jb      short loc_1800021D3
0x1800021c2  mov     rcx, [rax+10h]
0x1800021c6  mov     edx, 0C5h
0x1800021cb  mov     r9d, edi
0x1800021ce  call    WPP_SF_d
0x1800021d3  xor     ecx, ecx
0x1800021d5  cmp     qword ptr cs:xmmword_1800146E0, rcx
0x1800021dc  jz      loc_1800023F7
0x1800021e2  mov     r8d, edi
  ... truncated ...
```
