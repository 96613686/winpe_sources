# GetCertificateFromSslInfo

- ea: `0x180004000`
- end: `0x1800042f8`
- name: `GetCertificateFromSslInfo`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180001d10`
- `0x180007450`

## callees

- `0x180004000`
- `0x18000a014`
- `0x18000a044`
- `0x18000a38c`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x18000422a`
- `CRYPT32!CertCloseStore` at `0x18000422a`
- `CRYPT32!CertOpenStore` at `0x1800040c1`
- `CRYPT32!CertOpenStore` at `0x1800040c1`
- `CRYPT32!CertFindCertificateInStore` at `0x18000418f`
- `CRYPT32!CertFindCertificateInStore` at `0x18000418f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419d`

## string_xrefs

- `0x180004120`: `Unable to open the certificate store...%d`

## pseudocode

```c
__int64 __fastcall GetCertificateFromSslInfo(char a1, __int64 a2, PCCERT_CONTEXT *a3)
{
  __int64 v6; // r8
  _QWORD *v7; // rcx
  unsigned int v8; // ebx
  const wchar_t *pvPara; // rax
  HCERTSTORE v10; // rax
  void *v11; // rdi
  DWORD v12; // eax
  PCCERT_CONTEXT CertificateInStore; // rax
  DWORD LastError; // eax
  __int64 v15; // r8
  __int64 v16; // rcx
  const char *v17; // r9
  const wchar_t *v18; // r8
  __int128 pvFindPara; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v21 = 0;
  pvFindPara = 0;
  memset_0(v22, 0, sizeof(v22));
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0xC0) == 0xC0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    pvPara = L"MY";
    if ( *(_QWORD *)(a2 + 40) )
      pvPara = *(const wchar_t **)(a2 + 40);
    v10 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20004u, pvPara);
    v11 = v10;
    if ( v10 )
    {
      LODWORD(pvFindPara) = *(_DWORD *)(a2 + 8);
      v8 = 0;
      *((_QWORD *)&pvFindPara + 1) = *(_QWORD *)(a2 + 16);
      CertificateInStore = CertFindCertificateInStore(v10, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
      *a3 = CertificateInStore;
      if ( !CertificateInStore )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v15, LastError);
        }
        if ( (_QWORD)xmmword_1800146E0 )
        {
          LOWORD(v21) = 0;
          FormatRRASErrorString(&v21, L"Unable to locate the certificate with the given hash: %d", v8);
          ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
            gSstpCfgEtwContext,
            xmmword_1800146E0,
            &v21);
        }
      }
      CertCloseStore(v11, 2u);
    }
    else
    {
      v12 = GetLastError();
      v8 = v12;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v6, v12);
        v7 = WPP_GLOBAL_Control;
      }
      if ( !(_QWORD)xmmword_1800146E0 )
      {
LABEL_24:
        if ( !v8 )
          return v8;
        goto LABEL_25;
      }
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"Unable to open the certificate store...%d", v8);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v21);
    }
    v7 = WPP_GLOBAL_Control;
    goto LABEL_24;
  }
  v8 = 87;
LABEL_25:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) )
  {
    v16 = v7[2];
    v17 = "IPV4";
    if ( !a1 )
      v17 = "IPV6";
    WPP_SF_sD(v16, 36, v6, (_DWORD)v17, v8);
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    v18 = L"IPV4";
    LOWORD(v21) = 0;
    if ( !a1 )
      v18 = L"IPV6";
    FormatRRASErrorString(&v21, L"Unable to bind the certificate for %ws address port pair. Error: %d", v18, v8);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v21);
  }
  return v8;
}

```

## disassembly

```asm
0x180004000  mov     [rsp-8+arg_0], rbx
0x180004005  push    rbp
0x180004006  push    rsi
0x180004007  push    rdi
0x180004008  push    r14
0x18000400a  push    r15
0x18000400c  lea     rbp, [rsp-750h]
0x180004014  sub     rsp, 850h
0x18000401b  mov     rax, cs:__security_cookie
0x180004022  xor     rax, rsp
0x180004025  mov     [rbp+770h+var_30], rax
0x18000402c  mov     rsi, r8
0x18000402f  mov     r14, rdx
0x180004032  mov     r15b, cl
0x180004035  xorps   xmm0, xmm0
0x180004038  xor     eax, eax
0x18000403a  lea     rcx, [rsp+870h+var_82C]; void *
0x18000403f  xor     edx, edx; Val
0x180004041  mov     [rsp+870h+var_830], eax
0x180004045  mov     r8d, 7FCh; Size
0x18000404b  movups  [rsp+870h+pvFindPara], xmm0
0x180004050  call    memset_0
0x180004055  mov     rcx, cs:WPP_GLOBAL_Control
0x18000405c  lea     rax, WPP_GLOBAL_Control
0x180004063  cmp     rcx, rax
0x180004066  jz      short loc_180004089
0x180004068  mov     eax, [rcx+1Ch]
0x18000406b  and     eax, 0C0h
0x180004070  cmp     al, 0C0h
0x180004072  jnz     short loc_180004089
0x180004074  mov     rcx, [rcx+10h]
0x180004078  mov     edx, 21h ; '!'
0x18000407d  call    WPP_SF_
0x180004082  mov     rcx, cs:WPP_GLOBAL_Control
0x180004089  test    rsi, rsi
0x18000408c  jnz     short loc_18000409D
0x18000408e  lea     ebx, [rsi+57h]
0x180004091  lea     rsi, WPP_GLOBAL_Control
0x180004098  jmp     loc_18000423F
0x18000409d  cmp     qword ptr [r14+28h], 0
0x1800040a2  lea     rax, aMy; "MY"
0x1800040a9  mov     r9d, 20004h; dwFlags
0x1800040af  cmovnz  rax, [r14+28h]
0x1800040b4  xor     edx, edx; dwEncodingType
0x1800040b6  xor     r8d, r8d; hCryptProv
0x1800040b9  mov     [rsp+870h+pvPara], rax; pvPara
0x1800040be  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800040c1  call    cs:__imp_CertOpenStore
0x1800040c7  mov     rdi, rax
0x1800040ca  test    rax, rax
0x1800040cd  jnz     loc_18000415D
0x1800040d3  call    cs:__imp_GetLastError
0x1800040d9  mov     ebx, eax
0x1800040db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040e2  lea     rsi, WPP_GLOBAL_Control
0x1800040e9  cmp     rcx, rsi
0x1800040ec  jz      short loc_180004110
0x1800040ee  test    byte ptr [rcx+1Ch], 40h
0x1800040f2  jz      short loc_180004110
0x1800040f4  cmp     byte ptr [rcx+19h], 1
0x1800040f8  jb      short loc_180004110
0x1800040fa  mov     rcx, [rcx+10h]
0x1800040fe  lea     edx, [rdi+22h]
0x180004101  mov     r9d, eax
0x180004104  call    WPP_SF_d
0x180004109  mov     rcx, cs:WPP_GLOBAL_Control
0x180004110  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180004118  jz      loc_180004237
0x18000411e  xor     eax, eax
0x180004120  lea     rdx, aUnableToOpenTh_0; "Unable to open the certificate store..."...
0x180004127  mov     r8d, ebx
0x18000412a  mov     word ptr [rsp+870h+var_830], ax
0x18000412f  lea     rcx, [rsp+870h+var_830]
0x180004134  call    FormatRRASErrorString
0x180004139  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180004140  lea     r8, [rsp+870h+var_830]
0x180004145  mov     rcx, cs:gSstpCfgEtwContext
0x18000414c  mov     rax, cs:gSstpCfgTemplateFunc
0x180004153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004158  jmp     loc_180004230
0x18000415d  mov     eax, [r14+8]
0x180004161  mov     r9d, 10000h; dwFindType
0x180004167  mov     dword ptr [rsp+870h+pvFindPara], eax
0x18000416b  xor     ebx, ebx
0x18000416d  mov     rax, [r14+10h]
0x180004171  xor     r8d, r8d; dwFindFlags
0x180004174  mov     qword ptr [rsp+870h+pvFindPara+8], rax
0x180004179  mov     rcx, rdi; hCertStore
0x18000417c  lea     rax, [rsp+870h+pvFindPara]
0x180004181  mov     [rsp+870h+pPrevCertContext], rbx; pPrevCertContext
0x180004186  lea     edx, [r9+1]; dwCertEncodingType
0x18000418a  mov     [rsp+870h+pvPara], rax; pvFindPara
0x18000418f  call    cs:__imp_CertFindCertificateInStore
0x180004195  mov     [rsi], rax
0x180004198  test    rax, rax
0x18000419b  jnz     short loc_18000421B
0x18000419d  call    cs:__imp_GetLastError
0x1800041a3  mov     ebx, eax
0x1800041a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041ac  lea     rsi, WPP_GLOBAL_Control
0x1800041b3  cmp     rcx, rsi
0x1800041b6  jz      short loc_1800041D5
0x1800041b8  test    byte ptr [rcx+1Ch], 40h
0x1800041bc  jz      short loc_1800041D5
0x1800041be  cmp     byte ptr [rcx+19h], 1
0x1800041c2  jb      short loc_1800041D5
0x1800041c4  mov     rcx, [rcx+10h]
0x1800041c8  mov     edx, 23h ; '#'
0x1800041cd  mov     r9d, eax
0x1800041d0  call    WPP_SF_d
0x1800041d5  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800041dd  jz      short loc_180004222
0x1800041df  xor     eax, eax
0x1800041e1  lea     rdx, aUnableToLocate; "Unable to locate the certificate with t"...
0x1800041e8  mov     r8d, ebx
0x1800041eb  mov     word ptr [rsp+870h+var_830], ax
0x1800041f0  lea     rcx, [rsp+870h+var_830]
0x1800041f5  call    FormatRRASErrorString
0x1800041fa  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180004201  lea     r8, [rsp+870h+var_830]
0x180004206  mov     rcx, cs:gSstpCfgEtwContext
0x18000420d  mov     rax, cs:gSstpCfgTemplateFunc
0x180004214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004219  jmp     short loc_180004222
0x18000421b  lea     rsi, WPP_GLOBAL_Control
0x180004222  mov     edx, 2; dwFlags
0x180004227  mov     rcx, rdi; hCertStore
0x18000422a  call    cs:__imp_CertCloseStore
0x180004230  mov     rcx, cs:WPP_GLOBAL_Control
0x180004237  test    ebx, ebx
0x180004239  jz      loc_1800042D0
0x18000423f  cmp     rcx, rsi
0x180004242  jz      short loc_180004277
0x180004244  test    byte ptr [rcx+1Ch], 40h
0x180004248  jz      short loc_180004277
0x18000424a  cmp     byte ptr [rcx+19h], 1
0x18000424e  jb      short loc_180004277
0x180004250  mov     rcx, [rcx+10h]
0x180004254  lea     rax, aIpv6; "IPV6"
0x18000425b  test    r15b, r15b
0x18000425e  mov     dword ptr [rsp+870h+pvPara], ebx
0x180004262  lea     r9, aIpv4; "IPV4"
0x180004269  mov     edx, 24h ; '$'
0x18000426e  cmovz   r9, rax
0x180004272  call    WPP_SF_sD
0x180004277  cmp     qword ptr cs:xmmword_1800146E0, 0
0x18000427f  jz      short loc_1800042D0
0x180004281  xor     eax, eax
0x180004283  lea     r8, aIpv4_1; "IPV4"
0x18000428a  mov     word ptr [rsp+870h+var_830], ax
0x18000428f  lea     rdx, aUnableToBindTh_0; "Unable to bind the certificate for %ws "...
0x180004296  lea     rax, aIpv6_2; "IPV6"
0x18000429d  test    r15b, r15b
0x1800042a0  mov     r9d, ebx
0x1800042a3  lea     rcx, [rsp+870h+var_830]
0x1800042a8  cmovz   r8, rax
0x1800042ac  call    FormatRRASErrorString
0x1800042b1  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800042b8  lea     r8, [rsp+870h+var_830]
0x1800042bd  mov     rcx, cs:gSstpCfgEtwContext
0x1800042c4  mov     rax, cs:gSstpCfgTemplateFunc
0x1800042cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042d0  mov     eax, ebx
0x1800042d2  mov     rcx, [rbp+770h+var_30]
0x1800042d9  xor     rcx, rsp; StackCookie
0x1800042dc  call    __security_check_cookie
0x1800042e1  mov     rbx, [rsp+870h+arg_0]
0x1800042e9  add     rsp, 850h
0x1800042f0  pop     r15
0x1800042f2  pop     r14
0x1800042f4  pop     rdi
0x1800042f5  pop     rsi
0x1800042f6  pop     rbp
0x1800042f7  retn
```
