# ReadMessageFromFile(ushort *,unsigned __int64,uchar * *,ulong *)

- ea: `0x180006af4`
- end: `0x180006f76`
- name: `?ReadMessageFromFile@@YAJPEAG_KPEAPEAEPEAK@Z`
- size: `1154`
- prototype: `int(unsigned __int16 *, unsigned __int64, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180005e68`

## callees

- `0x180005d08`
- `0x180006af4`
- `0x180033ae0`
- `0x180091e92`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180006ba3`
- `KERNEL32!LocalAlloc` at `0x180006cef`
- `KERNEL32!LocalAlloc` at `0x180006d96`
- `KERNEL32!LocalAlloc` at `0x180006eac`
- `KERNEL32!LocalAlloc` at `0x180006ba3`
- `KERNEL32!LocalAlloc` at `0x180006cef`
- `KERNEL32!LocalAlloc` at `0x180006d96`
- `KERNEL32!LocalAlloc` at `0x180006eac`
- `KERNEL32!LocalFree` at `0x180006f18`
- `KERNEL32!LocalFree` at `0x180006f18`
- `KERNEL32!CreateFileW` at `0x180006b6c`
- `KERNEL32!CreateFileW` at `0x180006b6c`
- `KERNEL32!CloseHandle` at `0x180006bff`
- `KERNEL32!CloseHandle` at `0x180006bff`
- `KERNEL32!GetFileSize` at `0x180006b87`
- `KERNEL32!GetFileSize` at `0x180006b87`
- `KERNEL32!ReadFile` at `0x180006bca`
- `KERNEL32!ReadFile` at `0x180006bca`
- `CRYPT32!CertCloseStore` at `0x180006f32`
- `CRYPT32!CertCloseStore` at `0x180006f32`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180006dd7`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180006dd7`
- `CRYPT32!CertOpenStore` at `0x180006d70`
- `CRYPT32!CertOpenStore` at `0x180006d70`

## pseudocode

```c
__int64 __fastcall ReadMessageFromFile(
        unsigned __int16 *a1,
        HCRYPTPROV_LEGACY a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  void *v4; // r15
  HCRYPTPROV_LEGACY v7; // r14
  HANDLE FileW; // rax
  void *v9; // rsi
  int LastError; // ebx
  DWORD FileSize; // eax
  DWORD v12; // edi
  HLOCAL v13; // rax
  void *v14; // r14
  const void *v15; // r14
  unsigned __int8 *v16; // rax
  HCERTSTORE v17; // r13
  _QWORD *v18; // rdi
  const CERT_CONTEXT *v19; // rsi
  __int64 i; // r15
  const CERT_CONTEXT *v21; // rax
  unsigned int v22; // eax
  __int64 j; // rsi
  __int64 v24; // rcx
  __int64 v25; // r15
  DWORD v26; // ecx
  __int64 v27; // rax
  unsigned __int8 *v28; // rax
  int v29; // r15d
  __int64 v30; // rsi
  unsigned int v32; // [rsp+40h] [rbp-30h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-2Ch] BYREF
  int v34; // [rsp+48h] [rbp-28h] BYREF
  int v35; // [rsp+4Ch] [rbp-24h]
  void *v36; // [rsp+50h] [rbp-20h] BYREF
  __int64 v37; // [rsp+60h] [rbp-10h]
  __int64 v38; // [rsp+68h] [rbp-8h]
  SIZE_T uBytes; // [rsp+C0h] [rbp+50h] BYREF
  unsigned int *v41; // [rsp+C8h] [rbp+58h]

  v41 = a4;
  v4 = 0;
  v32 = 0;
  LODWORD(uBytes) = 0;
  v36 = 0;
  v34 = 0;
  v7 = a2;
  if ( !a3 || !a4 )
    return 2147942487LL;
  *a3 = 0;
  *a4 = 0;
  NumberOfBytesRead = 0;
  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = -2147221226;
LABEL_16:
    CloseHandle(v9);
    goto LABEL_17;
  }
  FileSize = GetFileSize(FileW, 0);
  v12 = FileSize;
  if ( FileSize == -1 )
  {
    LastError = -2147221226;
  }
  else
  {
    v13 = LocalAlloc(0x40u, FileSize);
    v14 = v13;
    if ( v13 )
    {
      if ( ReadFile(v9, v13, v12, &NumberOfBytesRead, 0) )
      {
        if ( v12 == NumberOfBytesRead )
        {
          LastError = 0;
          v36 = v14;
          v4 = v14;
          LODWORD(uBytes) = v12;
        }
        else
        {
          LastError = -2147467259;
        }
      }
      else
      {
        LastError = -2147221226;
      }
    }
    else
    {
      LastError = -2147024882;
    }
    v7 = a2;
  }
  if ( v9 )
    goto LABEL_16;
LABEL_17:
  if ( LastError >= 0 )
  {
    v15 = (const void *)((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, HCRYPTPROV_LEGACY, _QWORD, _QWORD))gpfnCryptMsgOpenToDecode)(
                          0x10000,
                          0,
                          0,
                          v7,
                          0,
                          0);
    if ( v15
      && (unsigned int)((__int64 (__fastcall *)(const void *, void *, _QWORD, __int64))gpfnCryptMsgUpdate)(
                         v15,
                         v4,
                         (unsigned int)uBytes,
                         1)
      && (LODWORD(uBytes) = 4,
          (unsigned int)((__int64 (__fastcall *)(const void *, __int64, _QWORD, unsigned int *, SIZE_T *))gpfnCryptMsgGetParam)(
                          v15,
                          11,
                          0,
                          &v32,
                          &uBytes)) )
    {
      if ( (_DWORD)uBytes != 4 )
        goto LABEL_23;
      if ( v32 != 1 )
      {
        v17 = CertOpenStore((LPCSTR)1, 1u, a2, 1u, v15);
        if ( v17 )
        {
          v18 = LocalAlloc(0x40u, 8LL * v32);
          if ( v18 )
          {
            v19 = 0;
            v35 = 0;
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              v21 = (const CERT_CONTEXT *)((__int64 (__fastcall *)(HCERTSTORE, const CERT_CONTEXT *))gpfnCertEnumCertificatesInStore)(
                                            v17,
                                            v19);
              v19 = v21;
              if ( !v21 )
                break;
              v18[i] = CertDuplicateCertificateContext(v21);
            }
            v22 = v32;
            for ( j = 0; ; j = (unsigned int)(j + 1) )
            {
              if ( (unsigned int)j >= v22 )
              {
                v29 = v35;
                goto LABEL_61;
              }
              v24 = v18[j];
              if ( !v24 )
              {
                LastError = -2147467259;
                goto LABEL_65;
              }
              v25 = 0;
              v37 = *(_QWORD *)(v24 + 24);
              v26 = 0;
              NumberOfBytesRead = 0;
              if ( !v22 )
                break;
              do
              {
                if ( (_DWORD)j != (_DWORD)v25 )
                {
                  v34 = 0;
                  v27 = ((__int64 (__fastcall *)(HCERTSTORE, _QWORD, _QWORD, int *))gpfnCertGetIssuerCertificateFromStore)(
                          v17,
                          v18[v25],
                          0,
                          &v34);
                  v38 = v27;
                  if ( v27 )
                  {
                    NumberOfBytesRead = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))gpfnCertCompareCertificate)(
                                          1,
                                          v37,
                                          *(_QWORD *)(v27 + 24));
                    ((void (__fastcall *)(__int64))gpfnCertFreeCertificateContext)(v38);
                    v26 = NumberOfBytesRead;
                    if ( NumberOfBytesRead )
                    {
                      v22 = v32;
                      goto LABEL_55;
                    }
                  }
                  else
                  {
                    v26 = NumberOfBytesRead;
                  }
                  v22 = v32;
                }
                v25 = (unsigned int)(v25 + 1);
              }
              while ( (unsigned int)v25 < v22 );
              if ( !v26 )
                break;
LABEL_55:
              ;
            }
            _mm_lfence();
            LODWORD(uBytes) = *(_DWORD *)(v18[j] + 16LL);
            v28 = (unsigned __int8 *)LocalAlloc(0x40u, (unsigned int)uBytes);
            *a3 = v28;
            if ( !v28 )
            {
              LastError = -2147024882;
              goto LABEL_65;
            }
            _mm_lfence();
            memcpy_0(v28, *(const void **)(v18[j] + 8LL), (unsigned int)uBytes);
            v29 = 1;
            *v41 = uBytes;
            v22 = v32;
LABEL_61:
            v30 = 0;
            if ( v22 )
            {
              do
              {
                ((void (__fastcall *)(_QWORD))gpfnCertFreeCertificateContext)(v18[v30]);
                v30 = (unsigned int)(v30 + 1);
              }
              while ( (unsigned int)v30 < v32 );
            }
            LocalFree(v18);
            if ( !v29 )
              LastError = -2147221233;
LABEL_65:
            v4 = v36;
          }
          else
          {
            LastError = -2147024882;
          }
          CertCloseStore(v17, 0);
        }
        else
        {
          LastError = HrGetLastError();
        }
        goto LABEL_67;
      }
      LODWORD(uBytes) = 0;
      if ( !(unsigned int)((__int64 (__fastcall *)(const void *, __int64, _QWORD))gpfnCryptMsgGetParam)(v15, 12, 0)
        || !(_DWORD)uBytes )
      {
LABEL_23:
        LastError = -2147467259;
LABEL_67:
        ((void (__fastcall *)(const void *))gpfnCryptMsgClose)(v15);
        goto LABEL_68;
      }
      v16 = (unsigned __int8 *)LocalAlloc(0x40u, (unsigned int)uBytes);
      *a3 = v16;
      if ( !v16 )
      {
        LastError = -2147024882;
        goto LABEL_67;
      }
      if ( (unsigned int)((__int64 (__fastcall *)(const void *, __int64, _QWORD, unsigned __int8 *, SIZE_T *))gpfnCryptMsgGetParam)(
                           v15,
                           12,
                           0,
                           v16,
                           &uBytes) )
      {
        *a4 = uBytes;
        goto LABEL_67;
      }
      LastError = HrGetLastError();
      LocalFreeAndNull((void **)a3);
    }
    else
    {
      LastError = HrGetLastError();
    }
    if ( !LastError )
      LastError = -2147467259;
    if ( !v15 )
      goto LABEL_68;
    goto LABEL_67;
  }
LABEL_68:
  if ( v4 )
    LocalFreeAndNull(&v36);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180006af4  mov     rax, rsp
0x180006af7  mov     [rax+8], rbx
0x180006afb  mov     [rax+20h], r9
0x180006aff  mov     [rax+10h], rdx
0x180006b03  push    rbp
0x180006b04  push    rsi
0x180006b05  push    rdi
0x180006b06  push    r12
0x180006b08  push    r13
0x180006b0a  push    r14
0x180006b0c  push    r15
0x180006b0e  mov     rbp, rsp
0x180006b11  sub     rsp, 70h
0x180006b15  xor     r15d, r15d
0x180006b18  mov     [rbp+var_30], 0
0x180006b1f  mov     dword ptr [rbp+uBytes], 0
0x180006b26  mov     r13, r9
0x180006b29  mov     [rbp+var_20], r15
0x180006b2d  mov     r12, r8
0x180006b30  mov     [rbp+var_28], r15d
0x180006b34  mov     r14, rdx
0x180006b37  test    r8, r8
0x180006b3a  jz      loc_180006F59
0x180006b40  test    r9, r9
0x180006b43  jz      loc_180006F59
0x180006b49  mov     [rax-78h], r15
0x180006b4d  mov     edx, 80000000h; dwDesiredAccess
0x180006b52  mov     [r8], r15
0x180006b55  lea     r8d, [r15+3]; dwShareMode
0x180006b59  mov     [r9], r15d
0x180006b5c  xor     r9d, r9d; lpSecurityAttributes
0x180006b5f  mov     [rax-80h], r15d
0x180006b63  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x180006b68  mov     [rbp+NumberOfBytesRead], r15d
0x180006b6c  call    cs:__imp_CreateFileW
0x180006b72  mov     rsi, rax
0x180006b75  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006b79  jnz     short loc_180006B82
0x180006b7b  mov     ebx, 80040116h
0x180006b80  jmp     short loc_180006BFC
0x180006b82  xor     edx, edx; lpFileSizeHigh
0x180006b84  mov     rcx, rsi; hFile
0x180006b87  call    cs:__imp_GetFileSize
0x180006b8d  mov     edi, eax
0x180006b8f  cmp     eax, 0FFFFFFFFh
0x180006b92  jnz     short loc_180006B9B
0x180006b94  mov     ebx, 80040116h
0x180006b99  jmp     short loc_180006BF7
0x180006b9b  mov     rdx, rdi; uBytes
0x180006b9e  mov     ecx, 40h ; '@'; uFlags
0x180006ba3  call    cs:__imp_LocalAlloc
0x180006ba9  mov     r14, rax
0x180006bac  test    rax, rax
0x180006baf  jnz     short loc_180006BB8
0x180006bb1  mov     ebx, 8007000Eh
0x180006bb6  jmp     short loc_180006BF3
0x180006bb8  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180006bbc  mov     qword ptr [rsp+70h+dwCreationDisposition], r15; lpOverlapped
0x180006bc1  mov     r8d, edi; nNumberOfBytesToRead
0x180006bc4  mov     rdx, r14; lpBuffer
0x180006bc7  mov     rcx, rsi; hFile
0x180006bca  call    cs:__imp_ReadFile
0x180006bd0  test    eax, eax
0x180006bd2  jnz     short loc_180006BDB
0x180006bd4  mov     ebx, 80040116h
0x180006bd9  jmp     short loc_180006BF3
0x180006bdb  cmp     edi, [rbp+NumberOfBytesRead]
0x180006bde  jz      short loc_180006BE7
0x180006be0  mov     ebx, 80004005h
0x180006be5  jmp     short loc_180006BF3
0x180006be7  xor     ebx, ebx
0x180006be9  mov     [rbp+var_20], r14
0x180006bed  mov     r15, r14
0x180006bf0  mov     dword ptr [rbp+uBytes], edi
0x180006bf3  mov     r14, [rbp+hCryptProv]
0x180006bf7  test    rsi, rsi
0x180006bfa  jz      short loc_180006C05
0x180006bfc  mov     rcx, rsi; hObject
0x180006bff  call    cs:__imp_CloseHandle
0x180006c05  test    ebx, ebx
0x180006c07  js      loc_180006F47
0x180006c0d  mov     rax, cs:?gpfnCryptMsgOpenToDecode@@3P6APEAXKKK_KPEAU_CERT_INFO@@PEAU_CMSG_STREAM_INFO@@@ZEA; void * (*gpfnCryptMsgOpenToDecode)(ulong,ulong,ulong,unsigned __int64,_CERT_INFO *,_CMSG_STREAM_INFO *)
0x180006c14  mov     r9, r14
0x180006c17  mov     [rsp+70h+var_48], 0
0x180006c20  xor     r8d, r8d
0x180006c23  xor     edx, edx
0x180006c25  mov     qword ptr [rsp+70h+dwCreationDisposition], 0
0x180006c2e  mov     ecx, 10000h
0x180006c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c38  mov     r14, rax
0x180006c3b  test    rax, rax
0x180006c3e  jnz     short loc_180006C4C
0x180006c40  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180006c45  mov     ebx, eax
0x180006c47  jmp     loc_180006D3B
0x180006c4c  mov     r8d, dword ptr [rbp+uBytes]
0x180006c50  mov     edi, 1
0x180006c55  mov     rax, cs:?gpfnCryptMsgUpdate@@3P6AHPEAXPEBEKH@ZEA; int (*gpfnCryptMsgUpdate)(void *,uchar const *,ulong,int)
0x180006c5c  mov     r9d, edi
0x180006c5f  mov     rdx, r15
0x180006c62  mov     rcx, r14
0x180006c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c6a  test    eax, eax
0x180006c6c  jz      short loc_180006C40
0x180006c6e  lea     rax, [rbp+uBytes]
0x180006c72  mov     dword ptr [rbp+uBytes], 4
0x180006c79  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180006c7e  lea     r9, [rbp+var_30]
0x180006c82  mov     rax, cs:?gpfnCryptMsgGetParam@@3P6AHPEAXKK0PEAK@ZEA; int (*gpfnCryptMsgGetParam)(void *,ulong,ulong,void *,ulong *)
0x180006c89  lea     edx, [rdi+0Ah]
0x180006c8c  xor     r8d, r8d
0x180006c8f  mov     rcx, r14
0x180006c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c97  test    eax, eax
0x180006c99  jz      short loc_180006C40
0x180006c9b  cmp     dword ptr [rbp+uBytes], 4
0x180006c9f  jz      short loc_180006CAB
0x180006ca1  mov     ebx, 80004005h
0x180006ca6  jmp     loc_180006F38
0x180006cab  cmp     [rbp+var_30], edi
0x180006cae  jnz     loc_180006D5F
0x180006cb4  xor     r9d, r9d
0x180006cb7  mov     dword ptr [rbp+uBytes], 0
0x180006cbe  lea     rax, [rbp+uBytes]
0x180006cc2  xor     r8d, r8d
0x180006cc5  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180006cca  mov     rcx, r14
0x180006ccd  mov     rax, cs:?gpfnCryptMsgGetParam@@3P6AHPEAXKK0PEAK@ZEA; int (*gpfnCryptMsgGetParam)(void *,ulong,ulong,void *,ulong *)
0x180006cd4  lea     edi, [r9+0Ch]
0x180006cd8  mov     edx, edi
0x180006cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cdf  test    eax, eax
0x180006ce1  jz      short loc_180006CA1
0x180006ce3  mov     eax, dword ptr [rbp+uBytes]
0x180006ce6  test    eax, eax
0x180006ce8  jz      short loc_180006CA1
0x180006cea  mov     edx, eax; uBytes
0x180006cec  lea     ecx, [rdi+34h]; uFlags
0x180006cef  call    cs:__imp_LocalAlloc
0x180006cf5  mov     [r12], rax
0x180006cf9  test    rax, rax
0x180006cfc  jnz     short loc_180006D08
0x180006cfe  mov     ebx, 8007000Eh
0x180006d03  jmp     loc_180006F38
0x180006d08  lea     rcx, [rbp+uBytes]
0x180006d0c  mov     r9, rax
0x180006d0f  mov     rax, cs:?gpfnCryptMsgGetParam@@3P6AHPEAXKK0PEAK@ZEA; int (*gpfnCryptMsgGetParam)(void *,ulong,ulong,void *,ulong *)
0x180006d16  xor     r8d, r8d
0x180006d19  mov     qword ptr [rsp+70h+dwCreationDisposition], rcx
0x180006d1e  mov     edx, edi
0x180006d20  mov     rcx, r14
0x180006d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d28  test    eax, eax
0x180006d2a  jnz     short loc_180006D53
0x180006d2c  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180006d31  mov     rcx, r12; void **
0x180006d34  mov     ebx, eax
0x180006d36  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180006d3b  test    ebx, ebx
0x180006d3d  mov     eax, 80004005h
0x180006d42  cmovz   ebx, eax
0x180006d45  test    r14, r14
0x180006d48  jz      loc_180006F47
0x180006d4e  jmp     loc_180006F38
0x180006d53  mov     eax, dword ptr [rbp+uBytes]
0x180006d56  mov     [r13+0], eax
0x180006d5a  jmp     loc_180006F38
0x180006d5f  mov     r8, [rbp+hCryptProv]; hCryptProv
0x180006d63  mov     r9d, edi; dwFlags
0x180006d66  mov     edx, edi; dwEncodingType
0x180006d68  mov     qword ptr [rsp+70h+dwCreationDisposition], r14; pvPara
0x180006d6d  mov     rcx, rdi; lpszStoreProvider
0x180006d70  call    cs:__imp_CertOpenStore
0x180006d76  mov     r13, rax
0x180006d79  test    rax, rax
0x180006d7c  jnz     short loc_180006D8A
0x180006d7e  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180006d83  mov     ebx, eax
0x180006d85  jmp     loc_180006F38
0x180006d8a  mov     edx, [rbp+var_30]
0x180006d8d  mov     ecx, 40h ; '@'; uFlags
0x180006d92  shl     rdx, 3; uBytes
0x180006d96  call    cs:__imp_LocalAlloc
0x180006d9c  mov     rdi, rax
0x180006d9f  test    rax, rax
0x180006da2  jnz     short loc_180006DAE
0x180006da4  mov     ebx, 8007000Eh
0x180006da9  jmp     loc_180006F2D
0x180006dae  xor     esi, esi
0x180006db0  mov     [rbp+var_24], 0
0x180006db7  xor     r15d, r15d
0x180006dba  mov     rax, cs:?gpfnCertEnumCertificatesInStore@@3P6APEBU_CERT_CONTEXT@@PEAXPEBU1@@ZEA; _CERT_CONTEXT const * (*gpfnCertEnumCertificatesInStore)(void *,_CERT_CONTEXT const *)
0x180006dc1  mov     rdx, rsi
0x180006dc4  mov     rcx, r13
0x180006dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dcc  mov     rsi, rax
0x180006dcf  test    rax, rax
0x180006dd2  jz      short loc_180006DE6
0x180006dd4  mov     rcx, rax; pCertContext
0x180006dd7  call    cs:__imp_CertDuplicateCertificateContext
0x180006ddd  mov     [rdi+r15*8], rax
0x180006de1  inc     r15d
0x180006de4  jmp     short loc_180006DBA
0x180006de6  mov     eax, [rbp+var_30]
0x180006de9  xor     esi, esi
0x180006deb  cmp     esi, eax
0x180006ded  jnb     loc_180006EF4
0x180006df3  mov     rcx, [rdi+rsi*8]
0x180006df7  test    rcx, rcx
0x180006dfa  jz      loc_180006EED
0x180006e00  mov     rcx, [rcx+18h]
0x180006e04  xor     r15d, r15d
0x180006e07  mov     [rbp+var_10], rcx
0x180006e0b  xor     ecx, ecx
0x180006e0d  mov     [rbp+NumberOfBytesRead], ecx
0x180006e10  test    eax, eax
0x180006e12  jz      loc_180006E98
0x180006e18  cmp     esi, r15d
0x180006e1b  jz      short loc_180006E85
0x180006e1d  mov     rax, cs:?gpfnCertGetIssuerCertificateFromStore@@3P6APEBU_CERT_CONTEXT@@PEAXPEBU1@1PEAK@ZEA; _CERT_CONTEXT const * (*gpfnCertGetIssuerCertificateFromStore)(void *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,ulong *)
0x180006e24  lea     r9, [rbp+var_28]
0x180006e28  mov     [rbp+var_28], 0
0x180006e2f  xor     r8d, r8d
0x180006e32  mov     rdx, [rdi+r15*8]
0x180006e36  mov     rcx, r13
0x180006e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3e  mov     [rbp+var_8], rax
0x180006e42  test    rax, rax
0x180006e45  jz      short loc_180006E7F
0x180006e47  mov     r8, [rax+18h]
0x180006e4b  mov     ecx, 1
0x180006e50  mov     rax, cs:?gpfnCertCompareCertificate@@3P6AHKPEAU_CERT_INFO@@0@ZEA; int (*gpfnCertCompareCertificate)(ulong,_CERT_INFO *,_CERT_INFO *)
0x180006e57  mov     rdx, [rbp+var_10]
0x180006e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e60  mov     rcx, [rbp+var_8]
0x180006e64  mov     [rbp+NumberOfBytesRead], eax
0x180006e67  mov     rax, cs:?gpfnCertFreeCertificateContext@@3P6AHPEBU_CERT_CONTEXT@@@ZEA; int (*gpfnCertFreeCertificateContext)(_CERT_CONTEXT const *)
0x180006e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e73  mov     ecx, [rbp+NumberOfBytesRead]
0x180006e76  test    ecx, ecx
0x180006e78  jz      short loc_180006E82
0x180006e7a  mov     eax, [rbp+var_30]
0x180006e7d  jmp     short loc_180006E91
0x180006e7f  mov     ecx, [rbp+NumberOfBytesRead]
0x180006e82  mov     eax, [rbp+var_30]
0x180006e85  inc     r15d
0x180006e88  cmp     r15d, eax
0x180006e8b  jb      short loc_180006E18
0x180006e8d  test    ecx, ecx
0x180006e8f  jz      short loc_180006E98
0x180006e91  inc     esi
0x180006e93  jmp     loc_180006DEB
0x180006e98  lfence
0x180006e9b  mov     rax, [rdi+rsi*8]
0x180006e9f  mov     ecx, [rax+10h]
0x180006ea2  mov     dword ptr [rbp+uBytes], ecx
0x180006ea5  mov     edx, ecx; uBytes
0x180006ea7  mov     ecx, 40h ; '@'; uFlags
0x180006eac  call    cs:__imp_LocalAlloc
0x180006eb2  mov     [r12], rax
0x180006eb6  test    rax, rax
0x180006eb9  jnz     short loc_180006EC2
0x180006ebb  mov     ebx, 8007000Eh
0x180006ec0  jmp     short loc_180006F29
0x180006ec2  lfence
0x180006ec5  mov     rdx, [rdi+rsi*8]
0x180006ec9  mov     rcx, rax; void *
0x180006ecc  mov     r8d, dword ptr [rbp+uBytes]; Size
0x180006ed0  mov     rdx, [rdx+8]; Src
0x180006ed4  call    memcpy_0
0x180006ed9  mov     eax, dword ptr [rbp+uBytes]
0x180006edc  mov     r15d, 1
0x180006ee2  mov     rcx, [rbp+arg_18]
0x180006ee6  mov     [rcx], eax
0x180006ee8  mov     eax, [rbp+var_30]
0x180006eeb  jmp     short loc_180006EF8
0x180006eed  mov     ebx, 80004005h
0x180006ef2  jmp     short loc_180006F29
0x180006ef4  mov     r15d, [rbp+var_24]
0x180006ef8  xor     esi, esi
0x180006efa  test    eax, eax
0x180006efc  jz      short loc_180006F15
0x180006efe  mov     rcx, [rdi+rsi*8]
0x180006f02  mov     rax, cs:?gpfnCertFreeCertificateContext@@3P6AHPEBU_CERT_CONTEXT@@@ZEA; int (*gpfnCertFreeCertificateContext)(_CERT_CONTEXT const *)
0x180006f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f0e  inc     esi
0x180006f10  cmp     esi, [rbp+var_30]
0x180006f13  jb      short loc_180006EFE
0x180006f15  mov     rcx, rdi; hMem
0x180006f18  call    cs:__imp_LocalFree
0x180006f1e  test    r15d, r15d
0x180006f21  mov     eax, 8004010Fh
0x180006f26  cmovz   ebx, eax
0x180006f29  mov     r15, [rbp+var_20]
0x180006f2d  xor     edx, edx; dwFlags
0x180006f2f  mov     rcx, r13; hCertStore
0x180006f32  call    cs:__imp_CertCloseStore
0x180006f38  mov     rax, cs:?gpfnCryptMsgClose@@3P6AHPEAX@ZEA; int (*gpfnCryptMsgClose)(void *)
0x180006f3f  mov     rcx, r14
0x180006f42  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
