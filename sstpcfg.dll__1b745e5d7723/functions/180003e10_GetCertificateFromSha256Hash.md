# GetCertificateFromSha256Hash

- ea: `0x180003e10`
- end: `0x180003ff9`
- name: `GetCertificateFromSha256Hash`
- size: `489`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x180001d10`
- `0x180005ea0`
- `0x180007450`
- `0x180008e70`

## callees

- `0x180003e10`
- `0x180004300`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180003ef9`
- `msvcrt!wcscpy_s` at `0x180003ef9`
- `msvcrt!wcsncat_s` at `0x180003ecb`
- `msvcrt!wcsncat_s` at `0x180003ee5`
- `msvcrt!wcsncat_s` at `0x180003ecb`
- `msvcrt!wcsncat_s` at `0x180003ee5`
- `CRYPT32!CertCloseStore` at `0x180003fbe`
- `CRYPT32!CertCloseStore` at `0x180003fbe`
- `CRYPT32!CertOpenStore` at `0x180003f17`
- `CRYPT32!CertOpenStore` at `0x180003f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f25`

## string_xrefs

- `0x180003f60`: `Unable to open the certificate store...%d`

## pseudocode

```c
__int64 __fastcall GetCertificateFromSha256Hash(wchar_t *Source, __int64 a2, __int64 a3, _QWORD *a4)
{
  unsigned int CertificateFromStoreForSha256Hash; // ebx
  HCERTSTORE v7; // rax
  void *v8; // rsi
  DWORD LastError; // eax
  __int64 v10; // r8
  wchar_t Destination[272]; // [rsp+30h] [rbp-A58h] BYREF
  int v13; // [rsp+250h] [rbp-838h] BYREF
  _BYTE v14[2044]; // [rsp+254h] [rbp-834h] BYREF

  memset_0(Destination, 0, 0x214u);
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0xC0) == 0xC0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39);
  if ( a4 )
  {
    *a4 = 0;
    if ( Source )
    {
      wcsncat_s(Destination, 0x10Au, Source, 0xFFu);
      wcsncat_s(Destination, 0x10Au, L"\\MY", 3u);
    }
    else
    {
      wcscpy_s(Destination, 0x10Au, L"MY");
    }
    v7 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20004u, Destination);
    v8 = v7;
    if ( v7 )
    {
      CertificateFromStoreForSha256Hash = GetCertificateFromStoreForSha256Hash(v7);
      CertCloseStore(v8, 2u);
    }
    else
    {
      LastError = GetLastError();
      CertificateFromStoreForSha256Hash = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v10, LastError);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"Unable to open the certificate store...%d", CertificateFromStoreForSha256Hash);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v13);
      }
    }
  }
  else
  {
    CertificateFromStoreForSha256Hash = 87;
  }
  if ( !*a4 )
    return 1168;
  return CertificateFromStoreForSha256Hash;
}

```

## disassembly

```asm
0x180003e10  mov     [rsp+arg_8], rbx
0x180003e15  push    rbp
0x180003e16  push    rsi
0x180003e17  push    rdi
0x180003e18  push    r12
0x180003e1a  push    r14
0x180003e1c  sub     rsp, 0A60h
0x180003e23  mov     rax, cs:__security_cookie
0x180003e2a  xor     rax, rsp
0x180003e2d  mov     [rsp+0A88h+var_38], rax
0x180003e35  mov     rbp, r8
0x180003e38  mov     r14d, edx
0x180003e3b  mov     rbx, rcx
0x180003e3e  xor     edx, edx; Val
0x180003e40  mov     r8d, 214h; Size
0x180003e46  lea     rcx, [rsp+0A88h+Destination]; void *
0x180003e4b  mov     rdi, r9
0x180003e4e  call    memset_0
0x180003e53  xor     eax, eax
0x180003e55  lea     rcx, [rsp+0A88h+var_834]; void *
0x180003e5d  xor     edx, edx; Val
0x180003e5f  mov     [rsp+0A88h+var_838], eax
0x180003e66  mov     r8d, 7FCh; Size
0x180003e6c  call    memset_0
0x180003e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e78  lea     r12, WPP_GLOBAL_Control
0x180003e7f  cmp     rcx, r12
0x180003e82  jz      short loc_180003E9E
0x180003e84  mov     eax, [rcx+1Ch]
0x180003e87  and     eax, 0C0h
0x180003e8c  cmp     al, 0C0h
0x180003e8e  jnz     short loc_180003E9E
0x180003e90  mov     rcx, [rcx+10h]
0x180003e94  mov     edx, 27h ; '''
0x180003e99  call    WPP_SF_
0x180003e9e  test    rdi, rdi
0x180003ea1  jnz     short loc_180003EAB
0x180003ea3  lea     ebx, [rdi+57h]
0x180003ea6  jmp     loc_180003FC4
0x180003eab  mov     qword ptr [rdi], 0
0x180003eb2  lea     rcx, [rsp+0A88h+Destination]; Destination
0x180003eb7  test    rbx, rbx
0x180003eba  jz      short loc_180003EED
0x180003ebc  mov     r9d, 0FFh; MaxCount
0x180003ec2  mov     r8, rbx; Source
0x180003ec5  lea     ebx, [r9+0Bh]
0x180003ec9  mov     edx, ebx; SizeInWords
0x180003ecb  call    cs:__imp_wcsncat_s
0x180003ed1  mov     r9d, 3; MaxCount
0x180003ed7  lea     r8, aMy_0; "\\MY"
0x180003ede  mov     edx, ebx; SizeInWords
0x180003ee0  lea     rcx, [rsp+0A88h+Destination]; Destination
0x180003ee5  call    cs:__imp_wcsncat_s
0x180003eeb  jmp     short loc_180003EFF
0x180003eed  lea     r8, aMy; "MY"
0x180003ef4  mov     edx, 10Ah; SizeInWords
0x180003ef9  call    cs:__imp_wcscpy_s
0x180003eff  xor     edx, edx; dwEncodingType
0x180003f01  lea     rax, [rsp+0A88h+Destination]
0x180003f06  mov     r9d, 20004h; dwFlags
0x180003f0c  mov     [rsp+0A88h+pvPara], rax; pvPara
0x180003f11  xor     r8d, r8d; hCryptProv
0x180003f14  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180003f17  call    cs:__imp_CertOpenStore
0x180003f1d  mov     rsi, rax
0x180003f20  test    rax, rax
0x180003f23  jnz     short loc_180003FA3
0x180003f25  call    cs:__imp_GetLastError
0x180003f2b  mov     ebx, eax
0x180003f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f34  cmp     rcx, r12
0x180003f37  jz      short loc_180003F54
0x180003f39  test    byte ptr [rcx+1Ch], 40h
0x180003f3d  jz      short loc_180003F54
0x180003f3f  cmp     byte ptr [rcx+19h], 1
0x180003f43  jb      short loc_180003F54
0x180003f45  mov     rcx, [rcx+10h]
0x180003f49  lea     edx, [rsi+28h]
0x180003f4c  mov     r9d, eax
0x180003f4f  call    WPP_SF_d
0x180003f54  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180003f5c  jz      short loc_180003FC4
0x180003f5e  xor     eax, eax
0x180003f60  lea     rdx, aUnableToOpenTh_0; "Unable to open the certificate store..."...
0x180003f67  mov     r8d, ebx
0x180003f6a  mov     word ptr [rsp+0A88h+var_838], ax
0x180003f72  lea     rcx, [rsp+0A88h+var_838]
0x180003f7a  call    FormatRRASErrorString
0x180003f7f  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180003f86  lea     r8, [rsp+0A88h+var_838]
0x180003f8e  mov     rcx, cs:gSstpCfgEtwContext
0x180003f95  mov     rax, cs:gSstpCfgTemplateFunc
0x180003f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fa1  jmp     short loc_180003FC4
0x180003fa3  mov     r9, rdi
0x180003fa6  mov     r8, rbp
0x180003fa9  mov     edx, r14d
0x180003fac  mov     rcx, rsi; hCertStore
0x180003faf  call    GetCertificateFromStoreForSha256Hash
0x180003fb4  mov     ebx, eax
0x180003fb6  mov     edx, 2; dwFlags
0x180003fbb  mov     rcx, rsi; hCertStore
0x180003fbe  call    cs:__imp_CertCloseStore
0x180003fc4  cmp     qword ptr [rdi], 0
0x180003fc8  mov     eax, 490h
0x180003fcd  cmovz   ebx, eax
0x180003fd0  mov     eax, ebx
0x180003fd2  mov     rcx, [rsp+0A88h+var_38]
0x180003fda  xor     rcx, rsp; StackCookie
0x180003fdd  call    __security_check_cookie
0x180003fe2  mov     rbx, [rsp+0A88h+arg_8]
0x180003fea  add     rsp, 0A60h
0x180003ff1  pop     r14
0x180003ff3  pop     r12
0x180003ff5  pop     rdi
0x180003ff6  pop     rsi
0x180003ff7  pop     rbp
0x180003ff8  retn
```
