# GetCertificateFromHash

- ea: `0x180003820`
- end: `0x180003aa5`
- name: `GetCertificateFromHash`
- size: `645`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180001d10`
- `0x180005ea0`
- `0x180007450`

## callees

- `0x180003820`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000390e`
- `msvcrt!wcscpy_s` at `0x18000390e`
- `msvcrt!wcsncat_s` at `0x1800038e0`
- `msvcrt!wcsncat_s` at `0x1800038fa`
- `msvcrt!wcsncat_s` at `0x1800038e0`
- `msvcrt!wcsncat_s` at `0x1800038fa`
- `CRYPT32!CertCloseStore` at `0x180003a7c`
- `CRYPT32!CertCloseStore` at `0x180003a7c`
- `CRYPT32!CertOpenStore` at `0x18000392c`
- `CRYPT32!CertOpenStore` at `0x18000392c`
- `CRYPT32!CertFindCertificateInStore` at `0x1800039eb`
- `CRYPT32!CertFindCertificateInStore` at `0x1800039eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000393e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000393e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039f9`

## string_xrefs

- `0x18000397d`: `Unable to open the certificate store...%d`

## pseudocode

```c
__int64 __fastcall GetCertificateFromHash(wchar_t *Source, int a2, __int64 a3, PCCERT_CONTEXT *a4)
{
  DWORD v8; // ebx
  HCERTSTORE v9; // rdi
  DWORD v10; // eax
  __int64 v11; // r8
  PCCERT_CONTEXT CertificateInStore; // rax
  DWORD LastError; // eax
  __int64 v14; // r8
  __int128 pvFindPara; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Destination[272]; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v19[2044]; // [rsp+264h] [rbp+164h] BYREF

  pvFindPara = 0;
  memset_0(Destination, 0, 0x214u);
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0xC0) == 0xC0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41);
  if ( a4 )
  {
    if ( Source )
    {
      wcsncat_s(Destination, 0x10Au, Source, 0xFFu);
      wcsncat_s(Destination, 0x10Au, L"\\MY", 3u);
    }
    else
    {
      wcscpy_s(Destination, 0x10Au, L"MY");
    }
    v9 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20004u, Destination);
    if ( v9 )
    {
      LODWORD(pvFindPara) = a2;
      *((_QWORD *)&pvFindPara + 1) = a3;
      v8 = 0;
      CertificateInStore = CertFindCertificateInStore(v9, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
      *a4 = CertificateInStore;
      if ( !CertificateInStore )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v14, LastError);
        }
        if ( (_QWORD)xmmword_1800146E0 )
        {
          LOWORD(v18) = 0;
          FormatRRASErrorString(&v18, L"Unable to locate the certificate with the given hash: %d", v8);
          ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
            gSstpCfgEtwContext,
            xmmword_1800146E0,
            &v18);
        }
      }
      CertCloseStore(v9, 2u);
    }
    else
    {
      v10 = GetLastError();
      v8 = v10;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v11, v10);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"Unable to open the certificate store...%d", v8);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v18);
      }
    }
  }
  else
  {
    return 87;
  }
  return v8;
}

```

## disassembly

```asm
0x180003820  push    rbp
0x180003822  push    rbx
0x180003823  push    rsi
0x180003824  push    rdi
0x180003825  push    r13
0x180003827  push    r14
0x180003829  push    r15
0x18000382b  lea     rbp, [rsp-970h]
0x180003833  sub     rsp, 0A70h
0x18000383a  mov     rax, cs:__security_cookie
0x180003841  xor     rax, rsp
0x180003844  mov     [rbp+9A0h+var_40], rax
0x18000384b  mov     r15, r8
0x18000384e  mov     r14d, edx
0x180003851  mov     rbx, rcx
0x180003854  xorps   xmm0, xmm0
0x180003857  xor     edx, edx; Val
0x180003859  lea     rcx, [rsp+0AA0h+Destination]; void *
0x18000385e  mov     r8d, 214h; Size
0x180003864  mov     rsi, r9
0x180003867  movups  [rsp+0AA0h+pvFindPara], xmm0
0x18000386c  call    memset_0
0x180003871  xor     eax, eax
0x180003873  lea     rcx, [rbp+9A0h+var_83C]; void *
0x18000387a  xor     edx, edx; Val
0x18000387c  mov     [rbp+9A0h+var_840], eax
0x180003882  mov     r8d, 7FCh; Size
0x180003888  call    memset_0
0x18000388d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003894  lea     r13, WPP_GLOBAL_Control
0x18000389b  cmp     rcx, r13
0x18000389e  jz      short loc_1800038BA
0x1800038a0  mov     eax, [rcx+1Ch]
0x1800038a3  and     eax, 0C0h
0x1800038a8  cmp     al, 0C0h
0x1800038aa  jnz     short loc_1800038BA
0x1800038ac  mov     rcx, [rcx+10h]
0x1800038b0  mov     edx, 29h ; ')'
0x1800038b5  call    WPP_SF_
0x1800038ba  test    rsi, rsi
0x1800038bd  jnz     short loc_1800038C7
0x1800038bf  lea     ebx, [rsi+57h]
0x1800038c2  jmp     loc_180003A82
0x1800038c7  lea     rcx, [rsp+0AA0h+Destination]; Destination
0x1800038cc  test    rbx, rbx
0x1800038cf  jz      short loc_180003902
0x1800038d1  mov     r9d, 0FFh; MaxCount
0x1800038d7  mov     r8, rbx; Source
0x1800038da  lea     ebx, [r9+0Bh]
0x1800038de  mov     edx, ebx; SizeInWords
0x1800038e0  call    cs:__imp_wcsncat_s
0x1800038e6  mov     r9d, 3; MaxCount
0x1800038ec  lea     r8, aMy_0; "\\MY"
0x1800038f3  mov     edx, ebx; SizeInWords
0x1800038f5  lea     rcx, [rsp+0AA0h+Destination]; Destination
0x1800038fa  call    cs:__imp_wcsncat_s
0x180003900  jmp     short loc_180003914
0x180003902  lea     r8, aMy; "MY"
0x180003909  mov     edx, 10Ah; SizeInWords
0x18000390e  call    cs:__imp_wcscpy_s
0x180003914  xor     edx, edx; dwEncodingType
0x180003916  lea     rax, [rsp+0AA0h+Destination]
0x18000391b  mov     r9d, 20004h; dwFlags
0x180003921  mov     [rsp+0AA0h+pvPara], rax; pvPara
0x180003926  xor     r8d, r8d; hCryptProv
0x180003929  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18000392c  call    cs:__imp_CertOpenStore
0x180003932  mov     rdi, rax
0x180003935  test    rax, rax
0x180003938  jnz     loc_1800039C0
0x18000393e  call    cs:__imp_GetLastError
0x180003944  mov     ebx, eax
0x180003946  mov     rcx, cs:WPP_GLOBAL_Control
0x18000394d  cmp     rcx, r13
0x180003950  jz      short loc_18000396D
0x180003952  test    byte ptr [rcx+1Ch], 40h
0x180003956  jz      short loc_18000396D
0x180003958  cmp     byte ptr [rcx+19h], 1
0x18000395c  jb      short loc_18000396D
0x18000395e  mov     rcx, [rcx+10h]
0x180003962  lea     edx, [rdi+2Ah]
0x180003965  mov     r9d, eax
0x180003968  call    WPP_SF_d
0x18000396d  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180003975  jz      loc_180003A82
0x18000397b  xor     eax, eax
0x18000397d  lea     rdx, aUnableToOpenTh_0; "Unable to open the certificate store..."...
0x180003984  mov     r8d, ebx
0x180003987  mov     word ptr [rbp+9A0h+var_840], ax
0x18000398e  lea     rcx, [rbp+9A0h+var_840]
0x180003995  call    FormatRRASErrorString
0x18000399a  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800039a1  lea     r8, [rbp+9A0h+var_840]
0x1800039a8  mov     rcx, cs:gSstpCfgEtwContext
0x1800039af  mov     rax, cs:gSstpCfgTemplateFunc
0x1800039b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039bb  jmp     loc_180003A82
0x1800039c0  mov     r9d, 10000h; dwFindType
0x1800039c6  mov     dword ptr [rsp+0AA0h+pvFindPara], r14d
0x1800039cb  lea     rax, [rsp+0AA0h+pvFindPara]
0x1800039d0  mov     qword ptr [rsp+0AA0h+pvFindPara+8], r15
0x1800039d5  xor     ebx, ebx
0x1800039d7  xor     r8d, r8d; dwFindFlags
0x1800039da  mov     [rsp+0AA0h+pPrevCertContext], rbx; pPrevCertContext
0x1800039df  mov     rcx, rdi; hCertStore
0x1800039e2  lea     edx, [r9+1]; dwCertEncodingType
0x1800039e6  mov     [rsp+0AA0h+pvPara], rax; pvFindPara
0x1800039eb  call    cs:__imp_CertFindCertificateInStore
0x1800039f1  mov     [rsi], rax
0x1800039f4  test    rax, rax
0x1800039f7  jnz     short loc_180003A74
0x1800039f9  call    cs:__imp_GetLastError
0x1800039ff  mov     ebx, eax
0x180003a01  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a08  cmp     rcx, r13
0x180003a0b  jz      short loc_180003A2A
0x180003a0d  test    byte ptr [rcx+1Ch], 40h
0x180003a11  jz      short loc_180003A2A
0x180003a13  cmp     byte ptr [rcx+19h], 1
0x180003a17  jb      short loc_180003A2A
0x180003a19  mov     rcx, [rcx+10h]
0x180003a1d  mov     edx, 2Bh ; '+'
0x180003a22  mov     r9d, eax
0x180003a25  call    WPP_SF_d
0x180003a2a  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180003a32  jz      short loc_180003A74
0x180003a34  xor     eax, eax
0x180003a36  lea     rdx, aUnableToLocate; "Unable to locate the certificate with t"...
0x180003a3d  mov     r8d, ebx
0x180003a40  mov     word ptr [rbp+9A0h+var_840], ax
0x180003a47  lea     rcx, [rbp+9A0h+var_840]
0x180003a4e  call    FormatRRASErrorString
0x180003a53  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180003a5a  lea     r8, [rbp+9A0h+var_840]
0x180003a61  mov     rcx, cs:gSstpCfgEtwContext
0x180003a68  mov     rax, cs:gSstpCfgTemplateFunc
0x180003a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a74  mov     edx, 2; dwFlags
0x180003a79  mov     rcx, rdi; hCertStore
0x180003a7c  call    cs:__imp_CertCloseStore
0x180003a82  mov     eax, ebx
0x180003a84  mov     rcx, [rbp+9A0h+var_40]
0x180003a8b  xor     rcx, rsp; StackCookie
0x180003a8e  call    __security_check_cookie
0x180003a93  add     rsp, 0A70h
0x180003a9a  pop     r15
0x180003a9c  pop     r14
0x180003a9e  pop     r13
0x180003aa0  pop     rdi
0x180003aa1  pop     rsi
0x180003aa2  pop     rbx
0x180003aa3  pop     rbp
0x180003aa4  retn
```
