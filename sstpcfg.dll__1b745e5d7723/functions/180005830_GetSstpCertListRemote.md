# GetSstpCertListRemote

- ea: `0x180005830`
- end: `0x180005e94`
- name: `GetSstpCertListRemote`
- size: `1636`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180001a6c`
- `0x180002a00`
- `0x180003150`
- `0x180003280`
- `0x180004f10`
- `0x180005830`
- `0x1800070f0`
- `0x180007408`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800058d4`
- `msvcrt!wcscpy_s` at `0x180005916`
- `msvcrt!wcscpy_s` at `0x1800058d4`
- `msvcrt!wcscpy_s` at `0x180005916`
- `msvcrt!wcsncat_s` at `0x1800058e8`
- `msvcrt!wcsncat_s` at `0x180005902`
- `msvcrt!wcsncat_s` at `0x1800058e8`
- `msvcrt!wcsncat_s` at `0x180005902`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000596a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a18`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005b7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bb4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000596a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a18`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005b7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005958`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ba5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005958`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ba5`
- `CRYPT32!CertCloseStore` at `0x180005caa`
- `CRYPT32!CertCloseStore` at `0x180005caa`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180005c7a`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180005c7a`
- `CRYPT32!CertOpenStore` at `0x180005934`
- `CRYPT32!CertOpenStore` at `0x180005934`
- `CRYPT32!CertFreeCertificateContext` at `0x180005e5a`
- `CRYPT32!CertFreeCertificateContext` at `0x180005e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000594b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000597c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005daf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000594b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000597c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005daf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e87`

## pseudocode

```c
__int64 __fastcall GetSstpCertListRemote(wchar_t *Source, _QWORD *a2)
{
  HCERTSTORE v4; // r13
  DWORD LastError; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v7; // rax
  _DWORD *v8; // r14
  DWORD v9; // eax
  __int64 v10; // r8
  HANDLE v11; // rax
  _WORD *v12; // rax
  const wchar_t *v13; // rsi
  unsigned __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rcx
  const wchar_t *v17; // r8
  _WORD *v18; // rcx
  HANDLE v19; // rax
  _WORD *v20; // rax
  unsigned __int64 v21; // rdx
  _WORD *v22; // rcx
  const CERT_CONTEXT *v23; // rdx
  __int64 v24; // rdx
  const wchar_t *v25; // r8
  PCCERT_CONTEXT v26; // rax
  const CERT_CONTEXT *v27; // rbx
  __int64 v28; // rbx
  DWORD v29; // eax
  __int64 v30; // r8
  DWORD v31; // eax
  _DWORD *v33; // [rsp+38h] [rbp-C8h]
  wchar_t Destination[272]; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+270h] [rbp+170h] BYREF
  char v37[2044]; // [rsp+274h] [rbp+174h] BYREF

  memset_0(Destination, 0, 0x214u);
  v33 = 0;
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  if ( !a2 )
  {
    v4 = 0;
    LastError = 87;
LABEL_60:
    FreeSstpCertList(0);
    goto LABEL_50;
  }
  if ( Source )
  {
    wcscpy_s(Destination, 0x10Au, L"\\\\");
    wcsncat_s(Destination, 0x10Au, Source, 0xFFu);
    wcsncat_s(Destination, 0x10Au, L"\\MY", 3u);
  }
  else
  {
    wcscpy_s(Destination, 0x10Au, L"MY");
  }
  LastError = 0;
  v4 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20004u, Destination);
  if ( !v4 )
    goto LABEL_7;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, 0x60u);
  v8 = v7;
  if ( v7 )
  {
    v7[8] = 16;
    v11 = GetProcessHeap();
    v12 = HeapAlloc(v11, 8u, 0x10u);
    *((_QWORD *)v8 + 5) = v12;
    if ( !v12 )
      goto LABEL_7;
    v13 = L"Default";
    v14 = (unsigned __int64)(unsigned int)v8[8] >> 1;
    v15 = 2147483646;
    if ( v14 )
    {
      v16 = 2147483646;
      v17 = L"Default";
      do
      {
        if ( !v16 )
          break;
        if ( !*v17 )
          break;
        *v12++ = *v17++;
        --v16;
        --v14;
      }
      while ( v14 );
      v18 = v12 - 1;
      if ( v14 )
        v18 = v12;
      *v18 = 0;
    }
    v8[16] = 16;
    v19 = GetProcessHeap();
    v20 = HeapAlloc(v19, 8u, 0x10u);
    *((_QWORD *)v8 + 9) = v20;
    if ( !v20 )
    {
LABEL_7:
      LastError = GetLastError();
      goto LABEL_59;
    }
    v21 = (unsigned __int64)(unsigned int)v8[16] >> 1;
    if ( v21 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v13 )
          break;
        *v20++ = *v13++;
        --v15;
        --v21;
      }
      while ( v21 );
      v22 = v20 - 1;
      if ( v21 )
        v22 = v20;
      *v22 = 0;
    }
    v8[4] = 0;
    v23 = 0;
    v8[2] = 1;
    v33 = v8;
    while ( 1 )
    {
      v26 = CertEnumCertificatesInStore(v4, v23);
      v27 = v26;
      if ( !v26 )
        goto LABEL_49;
      if ( (unsigned __int8)IsPrivateKeyPresent(v26) )
      {
        IsCertificateEKUServerAuth(v27);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 186);
        }
        v24 = xmmword_1800146E0;
        if ( (_QWORD)xmmword_1800146E0 )
        {
          v25 = L"Skipping certificate as it is not for All purpose or Server Auth";
LABEL_46:
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v24, v25);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 187);
        }
        v24 = xmmword_1800146E0;
        if ( (_QWORD)xmmword_1800146E0 )
        {
          v25 = L"Skipping certificate as it doesn't have private key";
          goto LABEL_46;
        }
      }
      v23 = v27;
    }
  }
  v9 = GetLastError();
  LastError = v9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, v10, v9);
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v36) = 0;
    FormatRRASErrorString(&v36, L"LocalAlloc failed and returned %d", LastError);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v36);
  }
LABEL_59:
  if ( LastError )
    goto LABEL_60;
LABEL_49:
  *a2 = v33;
LABEL_50:
  if ( v4 && !CertCloseStore(v4, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v28 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v29 = GetLastError();
      WPP_SF_d(v28, 188, v30, v29);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v36) = 0;
      v31 = GetLastError();
      FormatRRASErrorString(&v36, L"CertCloseStore failed and returned 0x%x", v31);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v36);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180005830  mov     [rsp-8+arg_10], rbx
0x180005835  mov     [rsp-8+arg_18], rsi
0x18000583a  push    rbp
0x18000583b  push    rdi
0x18000583c  push    r12
0x18000583e  push    r13
0x180005840  push    r14
0x180005842  lea     rbp, [rsp-980h]
0x18000584a  sub     rsp, 0A80h
0x180005851  mov     rax, cs:__security_cookie
0x180005858  xor     rax, rsp
0x18000585b  mov     [rbp+9A0h+var_30], rax
0x180005862  mov     rbx, rdx
0x180005865  mov     [rsp+0AA0h+var_A60], rdx
0x18000586a  mov     rdi, rcx
0x18000586d  xor     edx, edx; Val
0x18000586f  lea     rcx, [rsp+0AA0h+Destination]; void *
0x180005874  mov     r8d, 214h; Size
0x18000587a  call    memset_0
0x18000587f  xor     r14d, r14d
0x180005882  lea     rcx, [rbp+9A0h+var_82C]; void *
0x180005889  xor     edx, edx; Val
0x18000588b  mov     [rsp+0AA0h+var_A68], r14
0x180005890  mov     r8d, 7FCh; Size
0x180005896  mov     [rbp+9A0h+var_830], r14d
0x18000589d  mov     esi, r14d
0x1800058a0  call    memset_0
0x1800058a5  lea     r12, WPP_GLOBAL_Control
0x1800058ac  test    rbx, rbx
0x1800058af  jnz     short loc_1800058BC
0x1800058b1  mov     r13d, r14d
0x1800058b4  lea     edi, [rbx+57h]
0x1800058b7  jmp     loc_180005E6D
0x1800058bc  lea     rcx, [rsp+0AA0h+Destination]; Destination
0x1800058c1  test    rdi, rdi
0x1800058c4  jz      short loc_18000590A
0x1800058c6  mov     ebx, 10Ah
0x1800058cb  lea     r8, asc_180011550; "\\\\"
0x1800058d2  mov     edx, ebx; SizeInWords
0x1800058d4  call    cs:__imp_wcscpy_s
0x1800058da  lea     r9d, [rbx-0Bh]; MaxCount
0x1800058de  mov     r8, rdi; Source
0x1800058e1  mov     edx, ebx; SizeInWords
0x1800058e3  lea     rcx, [rsp+0AA0h+Destination]; Destination
0x1800058e8  call    cs:__imp_wcsncat_s
0x1800058ee  mov     r9d, 3; MaxCount
0x1800058f4  lea     r8, aMy_0; "\\MY"
0x1800058fb  mov     edx, ebx; SizeInWords
0x1800058fd  lea     rcx, [rsp+0AA0h+Destination]; Destination
0x180005902  call    cs:__imp_wcsncat_s
0x180005908  jmp     short loc_18000591C
0x18000590a  lea     r8, aMy; "MY"
0x180005911  mov     edx, 10Ah; SizeInWords
0x180005916  call    cs:__imp_wcscpy_s
0x18000591c  xor     edx, edx; dwEncodingType
0x18000591e  lea     rax, [rsp+0AA0h+Destination]
0x180005923  mov     r9d, 20004h; dwFlags
0x180005929  mov     [rsp+0AA0h+pvPara], rax; pvPara
0x18000592e  xor     r8d, r8d; hCryptProv
0x180005931  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180005934  call    cs:__imp_CertOpenStore
0x18000593a  xor     edi, edi
0x18000593c  lea     r12, WPP_GLOBAL_Control
0x180005943  mov     r13, rax
0x180005946  test    rax, rax
0x180005949  jnz     short loc_180005958
0x18000594b  call    cs:__imp_GetLastError
0x180005951  mov     edi, eax
0x180005953  jmp     loc_180005E65
0x180005958  call    cs:__imp_GetProcessHeap
0x18000595e  mov     edx, 8; dwFlags
0x180005963  mov     rcx, rax; hHeap
0x180005966  lea     r8d, [rdx+58h]; dwBytes
0x18000596a  call    cs:__imp_HeapAlloc
0x180005970  mov     r14, rax
0x180005973  test    rax, rax
0x180005976  jnz     loc_180005A01
0x18000597c  call    cs:__imp_GetLastError
0x180005982  mov     edi, eax
0x180005984  mov     rcx, cs:WPP_GLOBAL_Control
0x18000598b  cmp     rcx, r12
0x18000598e  jz      short loc_1800059AD
0x180005990  test    byte ptr [rcx+1Ch], 40h
0x180005994  jz      short loc_1800059AD
0x180005996  cmp     byte ptr [rcx+19h], 1
0x18000599a  jb      short loc_1800059AD
0x18000599c  mov     rcx, [rcx+10h]
0x1800059a0  mov     edx, 0B6h
0x1800059a5  mov     r9d, eax
0x1800059a8  call    WPP_SF_d
0x1800059ad  xor     r14d, r14d
0x1800059b0  cmp     qword ptr cs:xmmword_1800146E0, r14
0x1800059b7  jz      loc_180005E65
0x1800059bd  mov     r8d, edi
0x1800059c0  mov     word ptr [rbp+9A0h+var_830], r14w
0x1800059c8  lea     rdx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x1800059cf  lea     rcx, [rbp+9A0h+var_830]
0x1800059d6  call    FormatRRASErrorString
0x1800059db  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800059e2  lea     r8, [rbp+9A0h+var_830]
0x1800059e9  mov     rcx, cs:gSstpCfgEtwContext
0x1800059f0  mov     rax, cs:gSstpCfgTemplateFunc
0x1800059f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059fc  jmp     loc_180005E65
0x180005a01  mov     ebx, 10h
0x180005a06  mov     [rax+20h], ebx
0x180005a09  call    cs:__imp_GetProcessHeap
0x180005a0f  mov     r8d, ebx; dwBytes
0x180005a12  lea     edx, [rbx-8]; dwFlags
0x180005a15  mov     rcx, rax; hHeap
0x180005a18  call    cs:__imp_HeapAlloc
0x180005a1e  mov     [r14+28h], rax
0x180005a22  test    rax, rax
0x180005a25  jz      loc_180005E87
0x180005a2b  mov     edx, [r14+20h]
0x180005a2f  lea     rsi, aDefault; "Default"
0x180005a36  shr     rdx, 1
0x180005a39  mov     ebx, 7FFFFFFEh
0x180005a3e  jz      short loc_180005A77
0x180005a40  mov     ecx, ebx
0x180005a42  mov     r8, rsi
0x180005a45  test    rcx, rcx
0x180005a48  jz      short loc_180005A69
0x180005a4a  movzx   r9d, word ptr [r8]
0x180005a4e  test    r9w, r9w
0x180005a52  jz      short loc_180005A69
0x180005a54  mov     [rax], r9w
0x180005a58  add     r8, 2
0x180005a5c  add     rax, 2
0x180005a60  dec     rcx
0x180005a63  sub     rdx, 1
0x180005a67  jnz     short loc_180005A45
0x180005a69  test    rdx, rdx
0x180005a6c  lea     rcx, [rax-2]
0x180005a70  cmovnz  rcx, rax
0x180005a74  mov     [rcx], di
0x180005a77  mov     dword ptr [r14+40h], 10h
0x180005a7f  call    cs:__imp_GetProcessHeap
0x180005a85  mov     edx, 8; dwFlags
0x180005a8a  mov     rcx, rax; hHeap
0x180005a8d  lea     r8d, [rdx+8]; dwBytes
0x180005a91  call    cs:__imp_HeapAlloc
0x180005a97  mov     [r14+48h], rax
0x180005a9b  test    rax, rax
0x180005a9e  jz      loc_180005E7A
0x180005aa4  mov     edx, [r14+40h]
0x180005aa8  shr     rdx, 1
0x180005aab  jz      short loc_180005AE0
0x180005aad  test    rbx, rbx
0x180005ab0  jz      short loc_180005ACE
0x180005ab2  movzx   ecx, word ptr [rsi]
0x180005ab5  test    cx, cx
0x180005ab8  jz      short loc_180005ACE
0x180005aba  mov     [rax], cx
0x180005abd  add     rsi, 2
0x180005ac1  add     rax, 2
0x180005ac5  dec     rbx
0x180005ac8  sub     rdx, 1
0x180005acc  jnz     short loc_180005AAD
0x180005ace  xor     esi, esi
0x180005ad0  lea     rcx, [rax-2]
0x180005ad4  test    rdx, rdx
0x180005ad7  cmovnz  rcx, rax
0x180005adb  mov     [rcx], si
0x180005ade  jmp     short loc_180005AE2
0x180005ae0  xor     esi, esi
0x180005ae2  mov     [r14+10h], esi
0x180005ae6  xor     edx, edx
0x180005ae8  mov     dword ptr [r14+8], 1
0x180005af0  mov     [rsp+0AA0h+var_A68], r14
0x180005af5  jmp     loc_180005C77
0x180005afa  mov     rcx, rbx
0x180005afd  call    IsPrivateKeyPresent
0x180005b02  test    al, al
0x180005b04  jz      loc_180005C28
0x180005b0a  lea     rdx, [rsp+0AA0h+var_A70]
0x180005b0f  mov     [rsp+0AA0h+var_A70], esi
0x180005b13  mov     rcx, rbx; pCertContext
0x180005b16  call    IsCertificateEKUServerAuth
0x180005b1b  mov     eax, [rsp+0AA0h+var_A70]
0x180005b1f  dec     eax
0x180005b21  cmp     eax, 1
0x180005b24  jbe     short loc_180005B68
0x180005b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b2d  cmp     rcx, r12
0x180005b30  jz      short loc_180005B4C
0x180005b32  test    byte ptr [rcx+1Ch], 40h
0x180005b36  jz      short loc_180005B4C
0x180005b38  cmp     byte ptr [rcx+19h], 1
0x180005b3c  jb      short loc_180005B4C
0x180005b3e  mov     rcx, [rcx+10h]
0x180005b42  mov     edx, 0BAh
0x180005b47  call    WPP_SF_
0x180005b4c  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180005b53  test    rdx, rdx
0x180005b56  jz      loc_180005C74
0x180005b5c  lea     r8, aSkippingCertif_0; "Skipping certificate as it is not for A"...
0x180005b63  jmp     loc_180005C61
0x180005b68  call    cs:__imp_GetProcessHeap
0x180005b6e  mov     edi, 8
0x180005b73  mov     rcx, rax; hHeap
0x180005b76  mov     edx, edi; dwFlags
0x180005b78  lea     r8d, [rdi+58h]; dwBytes
0x180005b7c  call    cs:__imp_HeapAlloc
0x180005b82  mov     rsi, rax
0x180005b85  test    rax, rax
0x180005b88  jz      loc_180005DD6
0x180005b8e  lea     r8, [rax+20h]
0x180005b92  mov     rcx, rbx; pCertContext
0x180005b95  lea     rdx, [rax+28h]
0x180005b99  call    GetCertFriendlyName
0x180005b9e  mov     dword ptr [rsi+10h], 20h ; ' '
0x180005ba5  call    cs:__imp_GetProcessHeap
0x180005bab  lea     r8d, [rdi+18h]; dwBytes
0x180005baf  mov     edx, edi; dwFlags
0x180005bb1  mov     rcx, rax; hHeap
0x180005bb4  call    cs:__imp_HeapAlloc
0x180005bba  mov     [rsi+18h], rax
0x180005bbe  test    rax, rax
0x180005bc1  jz      loc_180005DAF
0x180005bc7  mov     r9, rax
0x180005bca  xor     r8d, r8d
0x180005bcd  mov     dl, 2
0x180005bcf  mov     rcx, rbx
0x180005bd2  call    GetHashFromCertificate
0x180005bd7  mov     edi, eax
0x180005bd9  test    eax, eax
0x180005bdb  jnz     loc_180005D65
0x180005be1  mov     [rsi+8], eax
0x180005be4  lea     r8, [rsi+50h]
0x180005be8  mov     rcx, [rbx+18h]
0x180005bec  lea     rdx, [rsi+58h]
0x180005bf0  mov     rcx, [rcx+48h]
0x180005bf4  call    FFileTimeToStr
0x180005bf9  lea     r9, [rsi+30h]
0x180005bfd  mov     rcx, rbx; pCertContext
0x180005c00  lea     r8, [rsi+38h]
0x180005c04  lea     edx, [rdi+1]; dwFlags
0x180005c07  call    CertPropertyToStr
0x180005c0c  lea     r9, [rsi+40h]
0x180005c10  xor     edx, edx; dwFlags
0x180005c12  lea     r8, [rsi+48h]
0x180005c16  mov     rcx, rbx; pCertContext
0x180005c19  call    CertPropertyToStr
0x180005c1e  mov     [r14], rsi
0x180005c21  mov     r14, rsi
0x180005c24  xor     esi, esi
0x180005c26  jmp     short loc_180005C74
0x180005c28  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c2f  cmp     rcx, r12
0x180005c32  jz      short loc_180005C4E
0x180005c34  test    byte ptr [rcx+1Ch], 40h
0x180005c38  jz      short loc_180005C4E
0x180005c3a  cmp     byte ptr [rcx+19h], 1
0x180005c3e  jb      short loc_180005C4E
0x180005c40  mov     rcx, [rcx+10h]
0x180005c44  mov     edx, 0BBh
0x180005c49  call    WPP_SF_
0x180005c4e  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180005c55  test    rdx, rdx
0x180005c58  jz      short loc_180005C74
0x180005c5a  lea     r8, aSkippingCertif; "Skipping certificate as it doesn't have"...
0x180005c61  mov     rcx, cs:gSstpCfgEtwContext
0x180005c68  mov     rax, cs:gSstpCfgTemplateFunc
0x180005c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c74  mov     rdx, rbx; pPrevCertContext
0x180005c77  mov     rcx, r13; hCertStore
0x180005c7a  call    cs:__imp_CertEnumCertificatesInStore
0x180005c80  mov     rbx, rax
0x180005c83  test    rax, rax
0x180005c86  jnz     loc_180005AFA
0x180005c8c  xor     r14d, r14d
0x180005c8f  mov     rcx, [rsp+0AA0h+var_A60]
0x180005c94  mov     rax, [rsp+0AA0h+var_A68]
0x180005c99  mov     [rcx], rax
0x180005c9c  test    r13, r13
0x180005c9f  jz      loc_180005D38
0x180005ca5  xor     edx, edx; dwFlags
0x180005ca7  mov     rcx, r13; hCertStore
0x180005caa  call    cs:__imp_CertCloseStore
0x180005cb0  test    eax, eax
0x180005cb2  jnz     loc_180005D38
0x180005cb8  mov     rbx, cs:WPP_GLOBAL_Control
0x180005cbf  cmp     rbx, r12
0x180005cc2  jz      short loc_180005CEA
0x180005cc4  test    byte ptr [rbx+1Ch], 40h
0x180005cc8  jz      short loc_180005CEA
0x180005cca  cmp     byte ptr [rbx+19h], 1
0x180005cce  jb      short loc_180005CEA
0x180005cd0  mov     rbx, [rbx+10h]
0x180005cd4  call    cs:__imp_GetLastError
0x180005cda  mov     edx, 0BCh
0x180005cdf  mov     rcx, rbx
0x180005ce2  mov     r9d, eax
0x180005ce5  call    WPP_SF_d
0x180005cea  cmp     qword ptr cs:xmmword_1800146E0, r14
0x180005cf1  jz      short loc_180005D38
0x180005cf3  mov     word ptr [rbp+9A0h+var_830], r14w
0x180005cfb  call    cs:__imp_GetLastError
0x180005d01  mov     r8d, eax
  ... truncated ...
```
