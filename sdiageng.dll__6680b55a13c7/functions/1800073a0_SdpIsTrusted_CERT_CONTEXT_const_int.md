# SdpIsTrusted(_CERT_CONTEXT const *,int *)

- ea: `0x1800073a0`
- end: `0x180007521`
- name: `?SdpIsTrusted@@YAJPEBU_CERT_CONTEXT@@PEAH@Z`
- size: `385`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011ba4`

## callees

- `0x1800073a0`
- `0x180026fa0`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000742c`
- `KERNEL32!GetLastError` at `0x1800074b5`
- `KERNEL32!GetLastError` at `0x18000742c`
- `KERNEL32!GetLastError` at `0x1800074b5`
- `CRYPT32!CertOpenSystemStoreW` at `0x18000745f`
- `CRYPT32!CertOpenSystemStoreW` at `0x18000745f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180007422`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180007422`
- `CRYPT32!CertFreeCertificateContext` at `0x1800074ad`
- `CRYPT32!CertFreeCertificateContext` at `0x1800074ad`
- `CRYPT32!CertCloseStore` at `0x1800074f8`
- `CRYPT32!CertCloseStore` at `0x1800074f8`
- `CRYPT32!CertFindCertificateInStore` at `0x180007493`
- `CRYPT32!CertFindCertificateInStore` at `0x180007493`

## pseudocode

```c
__int64 __fastcall SdpIsTrusted(const struct _CERT_CONTEXT *a1, int *a2)
{
  unsigned int v3; // r8d
  int v4; // r9d
  signed int v5; // ebx
  signed int LastError; // eax
  char *v7; // rdi
  const CERT_CONTEXT *CertificateInStore; // rax
  signed int v9; // eax
  DWORD pcbData[2]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE *v12; // [rsp+38h] [rbp-A0h]
  _BYTE pvData[128]; // [rsp+40h] [rbp-98h] BYREF

  pcbData[1] = 0;
  if ( !a1 )
  {
    v3 = 413;
LABEL_3:
    v4 = -2147024809;
    v5 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpIsTrusted", v3, v4);
    return (unsigned int)v5;
  }
  if ( !a2 )
  {
    v3 = 414;
    goto LABEL_3;
  }
  pcbData[0] = 128;
  v12 = pvData;
  if ( !CertGetCertificateContextProperty(a1, 0xFu, pvData, pcbData) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v3 = 423;
    if ( v5 >= 0 )
      v5 = -2147467259;
    v4 = v5;
    goto LABEL_4;
  }
  v7 = (char *)CertOpenSystemStoreW(0, L"TrustedPublisher");
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CertificateInStore = CertFindCertificateInStore(v7, 0, 0, 0xE0000u, pcbData, 0);
    *a2 = CertificateInStore != 0;
    v5 = 0;
    if ( CertificateInStore )
      CertFreeCertificateContext(CertificateInStore);
LABEL_21:
    CertCloseStore(v7, 0);
    return (unsigned int)v5;
  }
  v9 = GetLastError();
  v5 = v9;
  if ( v9 > 0 )
    v5 = (unsigned __int16)v9 | 0x80070000;
  if ( v5 >= 0 )
    v5 = -2147467259;
  SdpDebugTrace(1u, L"SdpIsTrusted", 0x1AAu, v5);
  if ( v7 )
    goto LABEL_21;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800073a0  mov     [rsp+arg_10], rbx
0x1800073a5  push    rdi
0x1800073a6  sub     rsp, 0D0h
0x1800073ad  mov     rax, cs:__security_cookie
0x1800073b4  xor     rax, rsp
0x1800073b7  mov     [rsp+0D8h+var_18], rax
0x1800073bf  mov     [rsp+0D8h+var_A4], 0
0x1800073c7  mov     rbx, rdx
0x1800073ca  test    rcx, rcx
0x1800073cd  jnz     short loc_1800073F4
0x1800073cf  mov     r8d, 19Dh; int
0x1800073d5  mov     r9d, 80070057h; int
0x1800073db  mov     ebx, r9d
0x1800073de  lea     rdx, aSdpistrusted; "SdpIsTrusted"
0x1800073e5  mov     ecx, 1; Level
0x1800073ea  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800073ef  jmp     loc_1800074FE
0x1800073f4  test    rbx, rbx
0x1800073f7  jnz     short loc_180007401
0x1800073f9  mov     r8d, 19Eh
0x1800073ff  jmp     short loc_1800073D5
0x180007401  lea     rax, [rsp+0D8h+pvData]
0x180007406  mov     [rsp+0D8h+pcbData], 80h
0x18000740e  lea     r9, [rsp+0D8h+pcbData]; pcbData
0x180007413  mov     [rsp+0D8h+var_A0], rax
0x180007418  lea     r8, [rsp+0D8h+pvData]; pvData
0x18000741d  mov     edx, 0Fh; dwPropId
0x180007422  call    cs:__imp_CertGetCertificateContextProperty
0x180007428  test    eax, eax
0x18000742a  jnz     short loc_180007456
0x18000742c  call    cs:__imp_GetLastError
0x180007432  mov     ebx, eax
0x180007434  test    eax, eax
0x180007436  jle     short loc_180007441
0x180007438  movzx   ebx, ax
0x18000743b  or      ebx, 80070000h
0x180007441  test    ebx, ebx
0x180007443  mov     eax, 80004005h
0x180007448  mov     r8d, 1A7h
0x18000744e  cmovns  ebx, eax
0x180007451  mov     r9d, ebx
0x180007454  jmp     short loc_1800073DE
0x180007456  lea     rdx, szSubsystemProtocol; "TrustedPublisher"
0x18000745d  xor     ecx, ecx; hProv
0x18000745f  call    cs:__imp_CertOpenSystemStoreW
0x180007465  mov     rdi, rax
0x180007468  lea     rcx, [rax-1]
0x18000746c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180007470  ja      short loc_1800074B5
0x180007472  lea     rax, [rsp+0D8h+pcbData]
0x180007477  mov     [rsp+0D8h+pPrevCertContext], 0; pPrevCertContext
0x180007480  mov     r9d, 0E0000h; dwFindType
0x180007486  mov     [rsp+0D8h+pvFindPara], rax; pvFindPara
0x18000748b  xor     r8d, r8d; dwFindFlags
0x18000748e  xor     edx, edx; dwCertEncodingType
0x180007490  mov     rcx, rdi; hCertStore
0x180007493  call    cs:__imp_CertFindCertificateInStore
0x180007499  xor     ecx, ecx
0x18000749b  test    rax, rax
0x18000749e  setnz   cl
0x1800074a1  mov     [rbx], ecx
0x1800074a3  xor     ebx, ebx
0x1800074a5  test    rax, rax
0x1800074a8  jz      short loc_1800074F3
0x1800074aa  mov     rcx, rax; pCertContext
0x1800074ad  call    cs:__imp_CertFreeCertificateContext
0x1800074b3  jmp     short loc_1800074F3
0x1800074b5  call    cs:__imp_GetLastError
0x1800074bb  mov     ebx, eax
0x1800074bd  test    eax, eax
0x1800074bf  jle     short loc_1800074CA
0x1800074c1  movzx   ebx, ax
0x1800074c4  or      ebx, 80070000h
0x1800074ca  mov     eax, 80004005h
0x1800074cf  lea     rdx, aSdpistrusted; "SdpIsTrusted"
0x1800074d6  test    ebx, ebx
0x1800074d8  mov     r8d, 1AAh; int
0x1800074de  mov     ecx, 1; Level
0x1800074e3  cmovns  ebx, eax
0x1800074e6  mov     r9d, ebx; int
0x1800074e9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800074ee  test    rdi, rdi
0x1800074f1  jz      short loc_1800074FE
0x1800074f3  xor     edx, edx; dwFlags
0x1800074f5  mov     rcx, rdi; hCertStore
0x1800074f8  call    cs:__imp_CertCloseStore
0x1800074fe  mov     eax, ebx
0x180007500  mov     rcx, [rsp+0D8h+var_18]
0x180007508  xor     rcx, rsp; StackCookie
0x18000750b  call    __security_check_cookie
0x180007510  mov     rbx, [rsp+0D8h+arg_10]
0x180007518  add     rsp, 0D0h
0x18000751f  pop     rdi
0x180007520  retn
```
