# SetSslCertificateToHttpV6

- ea: `0x180008be4`
- end: `0x180008e5f`
- name: `SetSslCertificateToHttpV6`
- size: `635`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180006b6c`
- `0x180007450`

## callees

- `0x18000863c`
- `0x180008be4`
- `0x18000a044`
- `0x18000a110`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000af10`
- `0x18000c010`

## import_xrefs

- `CRYPT32!CertNameToStrW` at `0x180008c9b`
- `CRYPT32!CertNameToStrW` at `0x180008c9b`
- `rtutils!RouterLogEventStringW` at `0x180008dc3`
- `rtutils!RouterLogEventStringW` at `0x180008dc3`

## pseudocode

```c
__int64 __fastcall SetSslCertificateToHttpV6(__int16 a1, const CERT_CONTEXT *a2)
{
  DWORD dwErrorCode; // ebx
  struct _CRYPTOAPI_BLOB *pCertInfo; // rdx
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  LPWSTR plpszSubStringArray[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v11[16]; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v13[2044]; // [rsp+74h] [rbp-8Ch] BYREF
  WCHAR psz; // [rsp+870h] [rbp+770h] BYREF
  _BYTE v15[2046]; // [rsp+872h] [rbp+772h] BYREF

  v12 = 0;
  dwErrorCode = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( a2 )
  {
    memset_0(v15, 0, sizeof(v15));
    pCertInfo = (struct _CRYPTOAPI_BLOB *)a2->pCertInfo;
    plpszSubStringArray[0] = &psz;
    plpszSubStringArray[1] = 0;
    memset(v11, 0, 28);
    psz = 0;
    CertNameToStrW(0x10001u, pCertInfo + 5, 3u, &psz, 0x400u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, v6, &psz);
    }
    if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString((wchar_t *)&v12, L"Using certificate %ws for V6 binding to SSL.", &psz);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        *((_QWORD *)&xmmword_1800146E0 + 1),
        &v12);
    }
    v11[0] = 23;
    v11[1] = __ROR2__(a1, 8);
    dwErrorCode = SetCertificateToSsl(a2, (__int64)v11);
    if ( dwErrorCode )
    {
      RouterLogEventStringW(EventSource, 1u, 0xDu, 1u, plpszSubStringArray, dwErrorCode, 0);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x48u, v8, dwErrorCode);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v12) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v12,
          L"Unable to bind the certificate for IPv6 address port pair. Error: %d",
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
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, v7, &psz);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v12) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v12,
          L"binding the certificate for IPv6 address port pair successful for %ws",
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
0x180008be4  mov     [rsp-8+arg_10], rbx
0x180008be9  mov     [rsp-8+arg_18], rsi
0x180008bee  push    rbp
0x180008bef  push    rdi
0x180008bf0  push    r12
0x180008bf2  lea     rbp, [rsp-0F80h]
0x180008bfa  mov     eax, 1080h
0x180008bff  call    _alloca_probe
0x180008c04  sub     rsp, rax
0x180008c07  mov     rax, cs:__security_cookie
0x180008c0e  xor     rax, rsp
0x180008c11  mov     [rbp+0F90h+var_20], rax
0x180008c18  mov     rsi, rdx
0x180008c1b  mov     edi, ecx
0x180008c1d  xor     eax, eax
0x180008c1f  lea     rcx, [rsp+1090h+var_101C]; void *
0x180008c24  xor     edx, edx; Val
0x180008c26  mov     [rsp+1090h+var_1020], eax
0x180008c2a  mov     r8d, 7FCh; Size
0x180008c30  xor     ebx, ebx
0x180008c32  call    memset_0
0x180008c37  test    rsi, rsi
0x180008c3a  jz      loc_180008E36
0x180008c40  xor     edx, edx; Val
0x180008c42  lea     rcx, [rbp+0F90h+var_81E]; void *
0x180008c49  mov     r8d, 7FEh; Size
0x180008c4f  call    memset_0
0x180008c54  mov     rdx, [rsi+18h]
0x180008c58  lea     rax, [rbp+0F90h+psz]
0x180008c5f  xorps   xmm0, xmm0
0x180008c62  mov     [rsp+1090h+plpszSubStringArray], rax
0x180008c67  xor     eax, eax
0x180008c69  mov     [rsp+1090h+var_1048], rbx
0x180008c6e  movups  xmmword ptr [rsp+1090h+var_1040], xmm0
0x180008c73  add     rdx, 50h ; 'P'; pName
0x180008c77  mov     [rbp+0F90h+psz], ax
0x180008c7e  lea     r9, [rbp+0F90h+psz]; psz
0x180008c85  mov     [rsp+1090h+csz], 400h; csz
0x180008c8d  mov     ecx, 10001h; dwCertEncodingType
0x180008c92  lea     r8d, [rbx+3]; dwStrType
0x180008c96  movups  xmmword ptr [rsp+1090h+var_1040+0Ch], xmm0
0x180008c9b  call    cs:__imp_CertNameToStrW
0x180008ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ca8  lea     r12, WPP_GLOBAL_Control
0x180008caf  cmp     rcx, r12
0x180008cb2  jz      short loc_180008CD3
0x180008cb4  test    byte ptr [rcx+1Ch], 40h
0x180008cb8  jz      short loc_180008CD3
0x180008cba  cmp     byte ptr [rcx+19h], 3
0x180008cbe  jb      short loc_180008CD3
0x180008cc0  mov     rcx, [rcx+10h]
0x180008cc4  lea     edx, [rbx+46h]
0x180008cc7  lea     r9, [rbp+0F90h+psz]
0x180008cce  call    WPP_SF_S
0x180008cd3  cmp     qword ptr cs:xmmword_1800146E0+8, rbx
0x180008cda  jz      short loc_180008D1A
0x180008cdc  xor     eax, eax
0x180008cde  lea     r8, [rbp+0F90h+psz]
0x180008ce5  lea     rdx, aUsingCertifica_0; "Using certificate %ws for V6 binding to"...
0x180008cec  mov     word ptr [rsp+1090h+var_1020], ax
0x180008cf1  lea     rcx, [rsp+1090h+var_1020]
0x180008cf6  call    FormatRRASErrorString
0x180008cfb  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x180008d02  lea     r8, [rsp+1090h+var_1020]
0x180008d07  mov     rcx, cs:gSstpCfgEtwContext
0x180008d0e  mov     rax, cs:gSstpCfgTemplateFunc
0x180008d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d1a  mov     eax, 17h
0x180008d1f  ror     di, 8
0x180008d23  lea     rdx, [rsp+1090h+var_1040]
0x180008d28  mov     [rsp+1090h+var_1040], ax
0x180008d2d  mov     rcx, rsi; pCertContext
0x180008d30  mov     [rsp+1090h+var_1040+2], di
0x180008d35  call    SetCertificateToSsl
0x180008d3a  mov     ebx, eax
0x180008d3c  test    eax, eax
0x180008d3e  jnz     short loc_180008D9A
0x180008d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d47  cmp     rcx, r12
0x180008d4a  jz      short loc_180008D6B
0x180008d4c  test    byte ptr [rcx+1Ch], 40h
0x180008d50  jz      short loc_180008D6B
0x180008d52  cmp     byte ptr [rcx+19h], 1
0x180008d56  jb      short loc_180008D6B
0x180008d58  mov     rcx, [rcx+10h]
0x180008d5c  lea     edx, [rax+47h]
0x180008d5f  lea     r9, [rbp+0F90h+psz]
0x180008d66  call    WPP_SF_S
0x180008d6b  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180008d73  jz      loc_180008E36
0x180008d79  xor     eax, eax
0x180008d7b  lea     r8, [rbp+0F90h+psz]
0x180008d82  lea     rdx, aBindingTheCert_0; "binding the certificate for IPv6 addres"...
0x180008d89  mov     word ptr [rsp+1090h+var_1020], ax
0x180008d8e  lea     rcx, [rsp+1090h+var_1020]
0x180008d93  call    FormatRRASErrorString
0x180008d98  jmp     short loc_180008E17
0x180008d9a  mov     rcx, cs:EventSource; hLogHandle
0x180008da1  lea     rax, [rsp+1090h+plpszSubStringArray]
0x180008da6  mov     edx, 1; dwEventType
0x180008dab  mov     [rsp+1090h+dwErrorIndex], 0; dwErrorIndex
0x180008db3  mov     [rsp+1090h+dwErrorCode], ebx; dwErrorCode
0x180008db7  mov     r9d, edx; dwSubStringCount
0x180008dba  mov     qword ptr [rsp+1090h+csz], rax; plpszSubStringArray
0x180008dbf  lea     r8d, [rdx+0Ch]; dwMessageId
0x180008dc3  call    cs:__imp_RouterLogEventStringW
0x180008dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dd0  cmp     rcx, r12
0x180008dd3  jz      short loc_180008DF2
0x180008dd5  test    byte ptr [rcx+1Ch], 40h
0x180008dd9  jz      short loc_180008DF2
0x180008ddb  cmp     byte ptr [rcx+19h], 1
0x180008ddf  jb      short loc_180008DF2
0x180008de1  mov     rcx, [rcx+10h]
0x180008de5  mov     edx, 48h ; 'H'
0x180008dea  mov     r9d, ebx
0x180008ded  call    WPP_SF_d
0x180008df2  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180008dfa  jz      short loc_180008E36
0x180008dfc  xor     eax, eax
0x180008dfe  lea     rdx, aUnableToBindTh; "Unable to bind the certificate for IPv6"...
0x180008e05  mov     r8d, ebx
0x180008e08  mov     word ptr [rsp+1090h+var_1020], ax
0x180008e0d  lea     rcx, [rsp+1090h+var_1020]
0x180008e12  call    FormatRRASErrorString
0x180008e17  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180008e1e  lea     r8, [rsp+1090h+var_1020]
0x180008e23  mov     rcx, cs:gSstpCfgEtwContext
0x180008e2a  mov     rax, cs:gSstpCfgTemplateFunc
0x180008e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e36  mov     eax, ebx
0x180008e38  mov     rcx, [rbp+0F90h+var_20]
0x180008e3f  xor     rcx, rsp; StackCookie
0x180008e42  call    __security_check_cookie
0x180008e47  lea     r11, [rsp+1090h+var_10]
0x180008e4f  mov     rbx, [r11+30h]
0x180008e53  mov     rsi, [r11+38h]
0x180008e57  mov     rsp, r11
0x180008e5a  pop     r12
0x180008e5c  pop     rdi
0x180008e5d  pop     rbp
0x180008e5e  retn
```
