# SetSslCertificateToHttpV4

- ea: `0x180008968`
- end: `0x180008bde`
- name: `SetSslCertificateToHttpV4`
- size: `630`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180006b6c`
- `0x180007450`

## callees

- `0x18000863c`
- `0x180008968`
- `0x18000a044`
- `0x18000a110`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000af10`
- `0x18000c010`

## import_xrefs

- `CRYPT32!CertNameToStrW` at `0x180008a1a`
- `CRYPT32!CertNameToStrW` at `0x180008a1a`
- `rtutils!RouterLogEventStringW` at `0x180008b42`
- `rtutils!RouterLogEventStringW` at `0x180008b42`

## pseudocode

```c
__int64 __fastcall SetSslCertificateToHttpV4(__int16 a1, const CERT_CONTEXT *a2)
{
  DWORD dwErrorCode; // ebx
  struct _CRYPTOAPI_BLOB *pCertInfo; // rdx
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  LPWSTR plpszSubStringArray[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v13[2044]; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR psz; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v15[2046]; // [rsp+862h] [rbp+762h] BYREF

  v12 = 0;
  dwErrorCode = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( a2 )
  {
    memset_0(v15, 0, sizeof(v15));
    pCertInfo = (struct _CRYPTOAPI_BLOB *)a2->pCertInfo;
    plpszSubStringArray[0] = &psz;
    plpszSubStringArray[1] = 0;
    psz = 0;
    v11 = 0;
    CertNameToStrW(0x10001u, pCertInfo + 5, 3u, &psz, 0x400u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, v6, &psz);
    }
    if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString((wchar_t *)&v12, L"Using certificate %ws for V4 binding to SSL.", &psz);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        *((_QWORD *)&xmmword_1800146E0 + 1),
        &v12);
    }
    LOWORD(v11) = 2;
    WORD1(v11) = __ROR2__(a1, 8);
    dwErrorCode = SetCertificateToSsl(a2, (__int64)&v11);
    if ( dwErrorCode )
    {
      RouterLogEventStringW(EventSource, 1u, 0xCu, 1u, plpszSubStringArray, dwErrorCode, 0);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x45u, v8, dwErrorCode);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v12) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v12,
          L"Unable to bind the certificate for IPv4 address port pair. Error: %d",
          dwErrorCode);
        goto LABEL_21;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, v7, &psz);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v12) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v12,
          L"binding the certificate for IPv4 address port pair successful for %ws",
          &psz);
LABEL_21:
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v12);
      }
    }
  }
  return dwErrorCode;
}

```

## disassembly

```asm
0x180008968  mov     [rsp-8+arg_10], rbx
0x18000896d  mov     [rsp-8+arg_18], rsi
0x180008972  push    rbp
0x180008973  push    rdi
0x180008974  push    r12
0x180008976  lea     rbp, [rsp-0F70h]
0x18000897e  mov     eax, 1070h
0x180008983  call    _alloca_probe
0x180008988  sub     rsp, rax
0x18000898b  mov     rax, cs:__security_cookie
0x180008992  xor     rax, rsp
0x180008995  mov     [rbp+0F80h+var_20], rax
0x18000899c  mov     rsi, rdx
0x18000899f  mov     edi, ecx
0x1800089a1  xor     eax, eax
0x1800089a3  lea     rcx, [rsp+1080h+var_101C]; void *
0x1800089a8  xor     edx, edx; Val
0x1800089aa  mov     [rsp+1080h+var_1020], eax
0x1800089ae  mov     r8d, 7FCh; Size
0x1800089b4  xor     ebx, ebx
0x1800089b6  call    memset_0
0x1800089bb  test    rsi, rsi
0x1800089be  jz      loc_180008BB5
0x1800089c4  xor     edx, edx; Val
0x1800089c6  lea     rcx, [rbp+0F80h+var_81E]; void *
0x1800089cd  mov     r8d, 7FEh; Size
0x1800089d3  call    memset_0
0x1800089d8  mov     rdx, [rsi+18h]
0x1800089dc  lea     rax, [rbp+0F80h+psz]
0x1800089e3  mov     [rsp+1080h+plpszSubStringArray], rax
0x1800089e8  lea     r9, [rbp+0F80h+psz]; psz
0x1800089ef  xor     eax, eax
0x1800089f1  mov     [rsp+1080h+var_1038], rbx
0x1800089f6  xorps   xmm0, xmm0
0x1800089f9  mov     [rbp+0F80h+psz], ax
0x180008a00  add     rdx, 50h ; 'P'; pName
0x180008a04  mov     [rsp+1080h+csz], 400h; csz
0x180008a0c  mov     ecx, 10001h; dwCertEncodingType
0x180008a11  lea     r8d, [rbx+3]; dwStrType
0x180008a15  movups  [rsp+1080h+var_1030], xmm0
0x180008a1a  call    cs:__imp_CertNameToStrW
0x180008a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a27  lea     r12, WPP_GLOBAL_Control
0x180008a2e  cmp     rcx, r12
0x180008a31  jz      short loc_180008A52
0x180008a33  test    byte ptr [rcx+1Ch], 40h
0x180008a37  jz      short loc_180008A52
0x180008a39  cmp     byte ptr [rcx+19h], 3
0x180008a3d  jb      short loc_180008A52
0x180008a3f  mov     rcx, [rcx+10h]
0x180008a43  lea     edx, [rbx+43h]
0x180008a46  lea     r9, [rbp+0F80h+psz]
0x180008a4d  call    WPP_SF_S
0x180008a52  cmp     qword ptr cs:xmmword_1800146E0+8, rbx
0x180008a59  jz      short loc_180008A99
0x180008a5b  xor     eax, eax
0x180008a5d  lea     r8, [rbp+0F80h+psz]
0x180008a64  lea     rdx, aUsingCertifica; "Using certificate %ws for V4 binding to"...
0x180008a6b  mov     word ptr [rsp+1080h+var_1020], ax
0x180008a70  lea     rcx, [rsp+1080h+var_1020]
0x180008a75  call    FormatRRASErrorString
0x180008a7a  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x180008a81  lea     r8, [rsp+1080h+var_1020]
0x180008a86  mov     rcx, cs:gSstpCfgEtwContext
0x180008a8d  mov     rax, cs:gSstpCfgTemplateFunc
0x180008a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a99  mov     eax, 2
0x180008a9e  ror     di, 8
0x180008aa2  lea     rdx, [rsp+1080h+var_1030]
0x180008aa7  mov     word ptr [rsp+1080h+var_1030], ax
0x180008aac  mov     rcx, rsi; pCertContext
0x180008aaf  mov     word ptr [rsp+1080h+var_1030+2], di
0x180008ab4  call    SetCertificateToSsl
0x180008ab9  mov     ebx, eax
0x180008abb  test    eax, eax
0x180008abd  jnz     short loc_180008B19
0x180008abf  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ac6  cmp     rcx, r12
0x180008ac9  jz      short loc_180008AEA
0x180008acb  test    byte ptr [rcx+1Ch], 40h
0x180008acf  jz      short loc_180008AEA
0x180008ad1  cmp     byte ptr [rcx+19h], 1
0x180008ad5  jb      short loc_180008AEA
0x180008ad7  mov     rcx, [rcx+10h]
0x180008adb  lea     edx, [rax+44h]
0x180008ade  lea     r9, [rbp+0F80h+psz]
0x180008ae5  call    WPP_SF_S
0x180008aea  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180008af2  jz      loc_180008BB5
0x180008af8  xor     eax, eax
0x180008afa  lea     r8, [rbp+0F80h+psz]
0x180008b01  lea     rdx, aBindingTheCert; "binding the certificate for IPv4 addres"...
0x180008b08  mov     word ptr [rsp+1080h+var_1020], ax
0x180008b0d  lea     rcx, [rsp+1080h+var_1020]
0x180008b12  call    FormatRRASErrorString
0x180008b17  jmp     short loc_180008B96
0x180008b19  mov     rcx, cs:EventSource; hLogHandle
0x180008b20  lea     rax, [rsp+1080h+plpszSubStringArray]
0x180008b25  mov     edx, 1; dwEventType
0x180008b2a  mov     [rsp+1080h+dwErrorIndex], 0; dwErrorIndex
0x180008b32  mov     [rsp+1080h+dwErrorCode], ebx; dwErrorCode
0x180008b36  mov     r9d, edx; dwSubStringCount
0x180008b39  mov     qword ptr [rsp+1080h+csz], rax; plpszSubStringArray
0x180008b3e  lea     r8d, [rdx+0Bh]; dwMessageId
0x180008b42  call    cs:__imp_RouterLogEventStringW
0x180008b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b4f  cmp     rcx, r12
0x180008b52  jz      short loc_180008B71
0x180008b54  test    byte ptr [rcx+1Ch], 40h
0x180008b58  jz      short loc_180008B71
0x180008b5a  cmp     byte ptr [rcx+19h], 1
0x180008b5e  jb      short loc_180008B71
0x180008b60  mov     rcx, [rcx+10h]
0x180008b64  mov     edx, 45h ; 'E'
0x180008b69  mov     r9d, ebx
0x180008b6c  call    WPP_SF_d
0x180008b71  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180008b79  jz      short loc_180008BB5
0x180008b7b  xor     eax, eax
0x180008b7d  lea     rdx, aUnableToBindTh_1; "Unable to bind the certificate for IPv4"...
0x180008b84  mov     r8d, ebx
0x180008b87  mov     word ptr [rsp+1080h+var_1020], ax
0x180008b8c  lea     rcx, [rsp+1080h+var_1020]
0x180008b91  call    FormatRRASErrorString
0x180008b96  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180008b9d  lea     r8, [rsp+1080h+var_1020]
0x180008ba2  mov     rcx, cs:gSstpCfgEtwContext
0x180008ba9  mov     rax, cs:gSstpCfgTemplateFunc
0x180008bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bb5  mov     eax, ebx
0x180008bb7  mov     rcx, [rbp+0F80h+var_20]
0x180008bbe  xor     rcx, rsp; StackCookie
0x180008bc1  call    __security_check_cookie
0x180008bc6  lea     r11, [rsp+1080h+var_10]
0x180008bce  mov     rbx, [r11+30h]
0x180008bd2  mov     rsi, [r11+38h]
0x180008bd6  mov     rsp, r11
0x180008bd9  pop     r12
0x180008bdb  pop     rdi
0x180008bdc  pop     rbp
0x180008bdd  retn
```
