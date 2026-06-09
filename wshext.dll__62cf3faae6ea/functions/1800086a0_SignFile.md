# SignFile

- ea: `0x1800086a0`
- end: `0x180008940`
- name: `SignFile`
- size: `672`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800084d0`
- `0x180008950`

## callees

- `0x1800086a0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000877d`
- `KERNEL32!GetLastError` at `0x18000877d`
- `KERNEL32!GetProcAddress` at `0x18000873e`
- `KERNEL32!GetProcAddress` at `0x18000873e`
- `KERNEL32!FreeLibrary` at `0x18000891d`
- `KERNEL32!FreeLibrary` at `0x18000891d`
- `KERNEL32!LoadLibraryExW` at `0x18000871c`
- `KERNEL32!LoadLibraryExW` at `0x18000871c`
- `CRYPT32!CertOpenStore` at `0x18000876f`
- `CRYPT32!CertOpenStore` at `0x18000876f`
- `CRYPT32!CertFindCertificateInStore` at `0x1800087b7`
- `CRYPT32!CertFindCertificateInStore` at `0x180008804`
- `CRYPT32!CertFindCertificateInStore` at `0x1800087b7`
- `CRYPT32!CertFindCertificateInStore` at `0x180008804`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800087d2`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800087d2`
- `CRYPT32!CertCloseStore` at `0x180008914`
- `CRYPT32!CertCloseStore` at `0x180008914`
- `CRYPT32!CertFreeCertificateContext` at `0x1800088ed`
- `CRYPT32!CertFreeCertificateContext` at `0x1800088fb`
- `CRYPT32!CertFreeCertificateContext` at `0x180008909`
- `CRYPT32!CertFreeCertificateContext` at `0x1800088ed`
- `CRYPT32!CertFreeCertificateContext` at `0x1800088fb`
- `CRYPT32!CertFreeCertificateContext` at `0x180008909`

## string_xrefs

- `0x1800086c8`: `mssign32.dll`

## pseudocode

```c
__int64 __fastcall SignFile(__int64 a1, __int64 a2, const void *a3, const void *a4)
{
  HMODULE Library; // rax
  HMODULE v7; // r12
  signed int v8; // ebx
  FARPROC ProcAddress; // r13
  HCERTSTORE v10; // rax
  void *v11; // r15
  signed int LastError; // eax
  const CERT_CONTEXT *CertificateInStore; // rax
  const CERT_CONTEXT *pPrevCertContext; // rsi
  const CERT_CONTEXT *v15; // r14
  const CERT_CONTEXT *v16; // rax
  int v18; // [rsp+48h] [rbp-99h] BYREF
  __int128 v19; // [rsp+50h] [rbp-91h] BYREF
  __int64 v20; // [rsp+60h] [rbp-81h]
  __int128 v21; // [rsp+68h] [rbp-79h] BYREF
  __int64 v22; // [rsp+78h] [rbp-69h]
  _BYTE v23[40]; // [rsp+80h] [rbp-61h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-39h] BYREF
  __int128 v25; // [rsp+B8h] [rbp-29h]
  __int128 v26; // [rsp+C8h] [rbp-19h] BYREF
  __int128 v27; // [rsp+D8h] [rbp-9h]
  __int128 v28; // [rsp+E8h] [rbp+7h] BYREF
  __int128 v29; // [rsp+F8h] [rbp+17h]

  v22 = 0;
  v20 = 0;
  v28 = 0;
  v18 = 0;
  v29 = 0;
  v21 = 0;
  v19 = 0;
  v24 = 0;
  v25 = 0;
  memset(v23, 0, sizeof(v23));
  v26 = 0;
  v27 = 0;
  Library = LoadLibraryExW(L"mssign32.dll", 0, 0x800u);
  v7 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "SignerSign");
    if ( !ProcAddress )
    {
      v8 = -2147467259;
LABEL_21:
      FreeLibrary(v7);
      return (unsigned int)v8;
    }
    v10 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x18000u, a4);
    v11 = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_21;
    }
    CertificateInStore = CertFindCertificateInStore(v10, 0x10001u, 0, 0x80007u, a3, 0);
    pPrevCertContext = CertificateInStore;
    if ( !CertificateInStore )
    {
      v8 = -2146885620;
LABEL_20:
      CertCloseStore(v11, 0);
      goto LABEL_21;
    }
    v15 = CertDuplicateCertificateContext(CertificateInStore);
    if ( v15 )
    {
      v16 = CertFindCertificateInStore(v11, 0x10001u, 0, 0x80007u, a3, pPrevCertContext);
      if ( v16 )
      {
        v8 = -2147467259;
        CertFreeCertificateContext(v16);
LABEL_18:
        if ( v15 )
          CertFreeCertificateContext(v15);
        goto LABEL_20;
      }
      LODWORD(v28) = 32;
      LODWORD(v24) = 32;
      *((_QWORD *)&v28 + 1) = &v18;
      pPrevCertContext = v15;
      *(_QWORD *)&v26 = 32;
      LODWORD(v29) = 1;
      LODWORD(v21) = 24;
      *((_QWORD *)&v29 + 1) = &v21;
      v15 = 0;
      *((_QWORD *)&v21 + 1) = a2;
      v22 = a1;
      *((_QWORD *)&v19 + 1) = &v24;
      *(_QWORD *)&v23[16] = &v26;
      *(_QWORD *)&v19 = 0x200000018LL;
      v18 = 0;
      v20 = 0;
      *((_QWORD *)&v24 + 1) = pPrevCertContext;
      LODWORD(v25) = 4;
      *((_QWORD *)&v25 + 1) = 0;
      *(_DWORD *)v23 = 40;
      *(_QWORD *)&v23[4] = 0x100008003LL;
      *(_OWORD *)&v23[24] = 0;
      DWORD2(v26) = 0;
      v27 = 0;
      v8 = ((__int64 (__fastcall *)(__int128 *, __int128 *, _BYTE *))ProcAddress)(&v28, &v19, v23);
      if ( v8 >= 0 )
        v8 = 0;
    }
    else
    {
      v8 = -2147467259;
    }
    CertFreeCertificateContext(pPrevCertContext);
    goto LABEL_18;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x1800086a0  mov     rax, rsp
0x1800086a3  mov     [rax+18h], rbx
0x1800086a7  mov     [rax+10h], rdx
0x1800086ab  mov     [rax+8], rcx
0x1800086af  push    rbp
0x1800086b0  push    rsi
0x1800086b1  push    rdi
0x1800086b2  push    r12
0x1800086b4  push    r13
0x1800086b6  push    r14
0x1800086b8  push    r15
0x1800086ba  lea     rbp, [rax-5Fh]
0x1800086be  sub     rsp, 100h
0x1800086c5  xorps   xmm0, xmm0
0x1800086c8  lea     rcx, LibFileName; "mssign32.dll"
0x1800086cf  xor     eax, eax
0x1800086d1  xorps   xmm1, xmm1
0x1800086d4  mov     rbx, r8
0x1800086d7  mov     [rbp+57h+var_C0], rax
0x1800086db  mov     r8d, 800h; dwFlags
0x1800086e1  mov     [rsp+130h+var_D8], rax
0x1800086e6  xor     edx, edx; hFile
0x1800086e8  mov     [rbp+57h+var_98], rax
0x1800086ec  movups  [rbp+57h+var_50], xmm0
0x1800086f0  mov     dword ptr [rsp+130h+var_F0], eax
0x1800086f4  mov     rdi, r9
0x1800086f7  movups  [rbp+57h+var_40], xmm0
0x1800086fb  movups  [rbp+57h+var_D0], xmm1
0x1800086ff  movups  [rsp+130h+var_F0+8], xmm0
0x180008704  movups  [rbp+57h+var_90], xmm1
0x180008708  movups  [rbp+57h+var_80], xmm1
0x18000870c  movups  [rbp+57h+var_B8], xmm0
0x180008710  movups  [rbp+57h+var_A8], xmm0
0x180008714  movups  [rbp+57h+var_70], xmm0
0x180008718  movups  [rbp+57h+var_60], xmm0
0x18000871c  call    cs:__imp_LoadLibraryExW
0x180008722  mov     r12, rax
0x180008725  test    rax, rax
0x180008728  jnz     short loc_180008734
0x18000872a  mov     ebx, 80004005h
0x18000872f  jmp     loc_180008923
0x180008734  lea     rdx, ProcName; "SignerSign"
0x18000873b  mov     rcx, r12; hModule
0x18000873e  call    cs:__imp_GetProcAddress
0x180008744  mov     r13, rax
0x180008747  test    rax, rax
0x18000874a  jnz     short loc_180008756
0x18000874c  mov     ebx, 80004005h
0x180008751  jmp     loc_18000891A
0x180008756  xor     r8d, r8d; hCryptProv
0x180008759  mov     [rsp+130h+pvPara], rdi; pvPara
0x18000875e  mov     edi, 10001h
0x180008763  mov     r9d, 18000h; dwFlags
0x180008769  mov     edx, edi; dwEncodingType
0x18000876b  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x18000876f  call    cs:__imp_CertOpenStore
0x180008775  mov     r15, rax
0x180008778  test    rax, rax
0x18000877b  jnz     short loc_18000879B
0x18000877d  call    cs:__imp_GetLastError
0x180008783  mov     ebx, eax
0x180008785  test    eax, eax
0x180008787  jle     loc_18000891A
0x18000878d  movzx   ebx, ax
0x180008790  or      ebx, 80070000h
0x180008796  jmp     loc_18000891A
0x18000879b  mov     [rsp+130h+pPrevCertContext], 0; pPrevCertContext
0x1800087a4  mov     r9d, 80007h; dwFindType
0x1800087aa  xor     r8d, r8d; dwFindFlags
0x1800087ad  mov     [rsp+130h+pvPara], rbx; pvFindPara
0x1800087b2  mov     edx, edi; dwCertEncodingType
0x1800087b4  mov     rcx, r15; hCertStore
0x1800087b7  call    cs:__imp_CertFindCertificateInStore
0x1800087bd  mov     rsi, rax
0x1800087c0  test    rax, rax
0x1800087c3  jnz     short loc_1800087CF
0x1800087c5  mov     ebx, 8009200Ch
0x1800087ca  jmp     loc_18000890F
0x1800087cf  mov     rcx, rsi; pCertContext
0x1800087d2  call    cs:__imp_CertDuplicateCertificateContext
0x1800087d8  mov     r14, rax
0x1800087db  test    rax, rax
0x1800087de  jnz     short loc_1800087EC
0x1800087e0  xor     edi, edi
0x1800087e2  mov     ebx, 80004005h
0x1800087e7  jmp     loc_1800088EA
0x1800087ec  mov     [rsp+130h+pPrevCertContext], rsi; pPrevCertContext
0x1800087f1  mov     r9d, 80007h; dwFindType
0x1800087f7  xor     r8d, r8d; dwFindFlags
0x1800087fa  mov     [rsp+130h+pvPara], rbx; pvFindPara
0x1800087ff  mov     edx, edi; dwCertEncodingType
0x180008801  mov     rcx, r15; hCertStore
0x180008804  call    cs:__imp_CertFindCertificateInStore
0x18000880a  xor     r9d, r9d
0x18000880d  mov     rdi, rax
0x180008810  test    rax, rax
0x180008813  jz      short loc_18000881F
0x180008815  mov     ebx, 80004005h
0x18000881a  jmp     loc_1800088F8
0x18000881f  mov     r8d, 20h ; ' '
0x180008825  mov     [rsp+30h], r9
0x18000882a  xorps   xmm0, xmm0
0x18000882d  mov     dword ptr [rbp+57h+var_50], r8d
0x180008831  lea     rax, [rsp+130h+var_F0]
0x180008836  mov     dword ptr [rbp+57h+var_90], r8d
0x18000883a  mov     qword ptr [rbp+57h+var_50+8], rax
0x18000883e  mov     rsi, r14
0x180008841  lea     edx, [r8-1Fh]
0x180008845  mov     qword ptr [rbp+57h+var_70], r8
0x180008849  lea     ecx, [rdx+17h]
0x18000884c  mov     dword ptr [rbp+57h+var_40], edx
0x18000884f  lea     rax, [rbp+57h+var_D0]
0x180008853  mov     dword ptr [rbp+57h+var_D0], ecx
0x180008856  mov     qword ptr [rbp+57h+var_40+8], rax
0x18000885a  lea     r8, [rbp+57h+var_B8]
0x18000885e  mov     rax, [rbp+57h+arg_8]
0x180008862  mov     r14, r9
0x180008865  mov     qword ptr [rbp+57h+var_D0+8], rax
0x180008869  mov     rax, [rbp+57h+arg_0]
0x18000886d  mov     [rbp+57h+var_C0], rax
0x180008871  lea     rax, [rbp+57h+var_90]
0x180008875  mov     [rsp+130h+var_E0], rax
0x18000887a  lea     rax, [rbp+57h+var_70]
0x18000887e  mov     qword ptr [rbp+57h+var_A8], rax
0x180008882  mov     rax, r13
0x180008885  mov     dword ptr [rsp+130h+var_F0+8], ecx
0x180008889  lea     rcx, [rbp+57h+var_50]
0x18000888d  mov     dword ptr [rbp+57h+var_B8+8], edx
0x180008890  lea     rdx, [rsp+130h+var_F0+8]
0x180008895  mov     [rsp+130h+pPrevCertContext], r9
0x18000889a  mov     dword ptr [rsp+130h+var_F0], r9d
0x18000889f  mov     dword ptr [rsp+130h+var_F0+0Ch], 2
0x1800088a7  mov     [rsp+130h+var_D8], r9
0x1800088ac  mov     qword ptr [rbp+57h+var_90+8], rsi
0x1800088b0  mov     dword ptr [rbp+57h+var_80], 4
0x1800088b7  mov     qword ptr [rbp+57h+var_80+8], r9
0x1800088bb  mov     dword ptr [rbp+57h+var_B8], 28h ; '('
0x1800088c2  mov     dword ptr [rbp+57h+var_B8+4], 8003h
0x1800088c9  movdqu  [rbp+57h+var_A8+8], xmm0
0x1800088ce  mov     dword ptr [rbp+57h+var_70+8], r9d
0x1800088d2  movdqu  [rbp+57h+var_60], xmm0
0x1800088d7  mov     [rsp+130h+pvPara], r9
0x1800088dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088e1  mov     ebx, eax
0x1800088e3  xor     eax, eax
0x1800088e5  test    ebx, ebx
0x1800088e7  cmovns  ebx, eax
0x1800088ea  mov     rcx, rsi; pCertContext
0x1800088ed  call    cs:__imp_CertFreeCertificateContext
0x1800088f3  test    rdi, rdi
0x1800088f6  jz      short loc_180008901
0x1800088f8  mov     rcx, rdi; pCertContext
0x1800088fb  call    cs:__imp_CertFreeCertificateContext
0x180008901  test    r14, r14
0x180008904  jz      short loc_18000890F
0x180008906  mov     rcx, r14; pCertContext
0x180008909  call    cs:__imp_CertFreeCertificateContext
0x18000890f  xor     edx, edx; dwFlags
0x180008911  mov     rcx, r15; hCertStore
0x180008914  call    cs:__imp_CertCloseStore
0x18000891a  mov     rcx, r12; hLibModule
0x18000891d  call    cs:__imp_FreeLibrary
0x180008923  mov     eax, ebx
0x180008925  mov     rbx, [rsp+130h+arg_10]
0x18000892d  add     rsp, 100h
0x180008934  pop     r15
0x180008936  pop     r14
0x180008938  pop     r13
0x18000893a  pop     r12
0x18000893c  pop     rdi
0x18000893d  pop     rsi
0x18000893e  pop     rbp
0x18000893f  retn
```
