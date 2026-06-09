# HrImportCertFromFile(ushort *,_CertDisplayInfo * *)

- ea: `0x180005e68`
- end: `0x180006091`
- name: `?HrImportCertFromFile@@YAJPEAGPEAPEAU_CertDisplayInfo@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _CertDisplayInfo **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180050100`

## callees

- `0x180005448`
- `0x180005758`
- `0x180005d08`
- `0x180005e68`
- `0x18000683c`
- `0x180006974`
- `0x180006af4`
- `0x180033ae0`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180005f42`
- `KERNEL32!LocalAlloc` at `0x180005fe0`
- `KERNEL32!LocalAlloc` at `0x180005f42`
- `KERNEL32!LocalAlloc` at `0x180005fe0`
- `KERNEL32!CreateFileW` at `0x180005f0b`
- `KERNEL32!CreateFileW` at `0x180005f0b`
- `KERNEL32!CloseHandle` at `0x180005f91`
- `KERNEL32!CloseHandle` at `0x180005f91`
- `KERNEL32!GetFileSize` at `0x180005f26`
- `KERNEL32!GetFileSize` at `0x180005f26`
- `KERNEL32!ReadFile` at `0x180005f69`
- `KERNEL32!ReadFile` at `0x180005f69`
- `USER32!GetDesktopWindow` at `0x180006017`
- `USER32!GetDesktopWindow` at `0x180006017`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180006009`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180006009`

## pseudocode

```c
__int64 __fastcall HrImportCertFromFile(unsigned __int16 *a1, unsigned __int16 ***a2)
{
  unsigned __int16 **v3; // rdi
  unsigned __int16 *v5; // r8
  int v7; // ebx
  HANDLE FileW; // rax
  void *v9; // r14
  DWORD FileSize; // eax
  DWORD v11; // esi
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // r15
  int LastError; // eax
  HLOCAL v15; // rax
  const struct _CERT_CONTEXT *v16; // rbx
  HWND DesktopWindow; // rax
  unsigned int v18; // esi
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int8 *v20; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+50h] [rbp-20h] BYREF
  void *v22; // [rsp+58h] [rbp-18h] BYREF
  void *v23; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+C0h] [rbp+50h] BYREF
  DWORD NumberOfBytesRead; // [rsp+C8h] [rbp+58h] BYREF

  v22 = 0;
  v3 = 0;
  v21 = 0;
  pCertContext = 0;
  v23 = 0;
  v20 = 0;
  v24 = 0;
  if ( !(unsigned int)InitCryptoLib() )
    return 2147746076LL;
  v7 = OpenSysCertStore(&v22, &v21, v5);
  if ( v7 )
    goto LABEL_24;
  if ( (unsigned int)ReadMessageFromFile(a1, v21, &v20, &v24) )
  {
    NumberOfBytesRead = 0;
    FileW = CreateFileW(a1, 0x80000000, v7 + 3, 0, v7 + 3, 0, 0);
    v9 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v7 = -2147221226;
LABEL_16:
      CloseHandle(v9);
LABEL_17:
      if ( v7 )
        goto LABEL_24;
      goto LABEL_18;
    }
    FileSize = GetFileSize(FileW, 0);
    v11 = FileSize;
    if ( FileSize == -1 )
      goto LABEL_8;
    v12 = (unsigned __int8 *)LocalAlloc(0x40u, FileSize);
    v13 = v12;
    if ( v12 )
    {
      if ( !ReadFile(v9, v12, v11, &NumberOfBytesRead, 0) )
      {
LABEL_8:
        v7 = -2147221226;
        goto LABEL_15;
      }
      if ( v11 == NumberOfBytesRead )
      {
        v7 = 0;
        v20 = v13;
        v24 = v11;
      }
      else
      {
        v7 = -2147467259;
      }
    }
    else
    {
      v7 = -2147024882;
    }
LABEL_15:
    if ( !v9 )
      goto LABEL_17;
    goto LABEL_16;
  }
LABEL_18:
  if ( !(unsigned int)((__int64 (__fastcall *)(void *, __int64, unsigned __int8 *, _QWORD, int, PCCERT_CONTEXT *))gpfnCertAddEncodedCertificateToStore)(
                        v22,
                        1,
                        v20,
                        v24,
                        2,
                        &pCertContext) )
  {
    LastError = HrGetLastError();
LABEL_23:
    v7 = LastError;
    goto LABEL_24;
  }
  v15 = LocalAlloc(0x40u, 0x58u);
  v23 = v15;
  v3 = (unsigned __int16 **)v15;
  if ( v15 )
  {
    *((_QWORD *)v15 + 9) = 0;
    *((_QWORD *)v15 + 10) = 0;
    *((_DWORD *)v15 + 5) = 0;
    *((_QWORD *)v15 + 5) = CertDuplicateCertificateContext(pCertContext);
    v16 = pCertContext;
    DesktopWindow = GetDesktopWindow();
    LastError = GetCertsDisplayInfoFromContext(DesktopWindow, v16, v3);
    goto LABEL_23;
  }
  v7 = -2147024882;
LABEL_24:
  if ( pCertContext )
    ((void (*)(void))gpfnCertFreeCertificateContext)();
  v18 = CloseCertStore(v22, v21);
  if ( v7 )
    v18 = v7;
  if ( v18 || !a2 )
    LocalFreeAndNull(&v23);
  else
    *a2 = v3;
  LocalFreeAndNull((void **)&v20);
  return v18;
}

```

## disassembly

```asm
0x180005e68  mov     [rsp-38h+arg_0], rbx
0x180005e6d  push    rbp
0x180005e6e  push    rsi
0x180005e6f  push    rdi
0x180005e70  push    r12
0x180005e72  push    r13
0x180005e74  push    r14
0x180005e76  push    r15
0x180005e78  mov     rbp, rsp
0x180005e7b  sub     rsp, 70h
0x180005e7f  xor     r13d, r13d
0x180005e82  mov     r12, rdx
0x180005e85  mov     [rbp+var_18], r13
0x180005e89  mov     edi, r13d
0x180005e8c  mov     [rbp+var_20], r13
0x180005e90  mov     rsi, rcx
0x180005e93  mov     [rbp+pCertContext], r13
0x180005e97  mov     [rbp+var_10], r13
0x180005e9b  mov     [rbp+var_28], r13
0x180005e9f  mov     [rbp+arg_10], r13d
0x180005ea3  call    ?InitCryptoLib@@YAHXZ; InitCryptoLib(void)
0x180005ea8  test    eax, eax
0x180005eaa  jnz     short loc_180005EB6
0x180005eac  mov     eax, 8004011Ch
0x180005eb1  jmp     loc_180006079
0x180005eb6  lea     rdx, [rbp+var_20]; unsigned __int64 *
0x180005eba  lea     rcx, [rbp+var_18]; void **
0x180005ebe  call    ?OpenSysCertStore@@YAJPEAPEAXPEA_KPEAG@Z; OpenSysCertStore(void * *,unsigned __int64 *,ushort *)
0x180005ec3  mov     ebx, eax
0x180005ec5  test    eax, eax
0x180005ec7  jnz     loc_18000602D
0x180005ecd  mov     rdx, [rbp+var_20]; unsigned __int64
0x180005ed1  lea     r9, [rbp+arg_10]; unsigned int *
0x180005ed5  lea     r8, [rbp+var_28]; unsigned __int8 **
0x180005ed9  mov     rcx, rsi; unsigned __int16 *
0x180005edc  call    ?ReadMessageFromFile@@YAJPEAG_KPEAPEAEPEAK@Z; ReadMessageFromFile(ushort *,unsigned __int64,uchar * *,ulong *)
0x180005ee1  test    eax, eax
0x180005ee3  jz      loc_180005F9F
0x180005ee9  mov     [rsp+70h+hTemplateFile], r13; hTemplateFile
0x180005eee  lea     r8d, [rbx+3]; dwShareMode
0x180005ef2  mov     [rsp+70h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180005ef7  xor     r9d, r9d; lpSecurityAttributes
0x180005efa  mov     edx, 80000000h; dwDesiredAccess
0x180005eff  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x180005f04  mov     rcx, rsi; lpFileName
0x180005f07  mov     [rbp+NumberOfBytesRead], r13d
0x180005f0b  call    cs:__imp_CreateFileW
0x180005f11  mov     r14, rax
0x180005f14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005f18  jnz     short loc_180005F21
0x180005f1a  mov     ebx, 80040116h
0x180005f1f  jmp     short loc_180005F8E
0x180005f21  xor     edx, edx; lpFileSizeHigh
0x180005f23  mov     rcx, r14; hFile
0x180005f26  call    cs:__imp_GetFileSize
0x180005f2c  mov     esi, eax
0x180005f2e  cmp     eax, 0FFFFFFFFh
0x180005f31  jnz     short loc_180005F3A
0x180005f33  mov     ebx, 80040116h
0x180005f38  jmp     short loc_180005F89
0x180005f3a  mov     rdx, rsi; uBytes
0x180005f3d  mov     ecx, 40h ; '@'; uFlags
0x180005f42  call    cs:__imp_LocalAlloc
0x180005f48  mov     r15, rax
0x180005f4b  test    rax, rax
0x180005f4e  jnz     short loc_180005F57
0x180005f50  mov     ebx, 8007000Eh
0x180005f55  jmp     short loc_180005F89
0x180005f57  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180005f5b  mov     qword ptr [rsp+70h+dwCreationDisposition], r13; lpOverlapped
0x180005f60  mov     r8d, esi; nNumberOfBytesToRead
0x180005f63  mov     rdx, r15; lpBuffer
0x180005f66  mov     rcx, r14; hFile
0x180005f69  call    cs:__imp_ReadFile
0x180005f6f  test    eax, eax
0x180005f71  jz      short loc_180005F33
0x180005f73  cmp     esi, [rbp+NumberOfBytesRead]
0x180005f76  jz      short loc_180005F7F
0x180005f78  mov     ebx, 80004005h
0x180005f7d  jmp     short loc_180005F89
0x180005f7f  mov     ebx, r13d
0x180005f82  mov     [rbp+var_28], r15
0x180005f86  mov     [rbp+arg_10], esi
0x180005f89  test    r14, r14
0x180005f8c  jz      short loc_180005F97
0x180005f8e  mov     rcx, r14; hObject
0x180005f91  call    cs:__imp_CloseHandle
0x180005f97  test    ebx, ebx
0x180005f99  jnz     loc_18000602D
0x180005f9f  mov     r9d, [rbp+arg_10]
0x180005fa3  lea     rax, [rbp+pCertContext]
0x180005fa7  mov     r8, [rbp+var_28]
0x180005fab  mov     edx, 1
0x180005fb0  mov     rcx, [rbp+var_18]
0x180005fb4  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x180005fb9  mov     rax, cs:?gpfnCertAddEncodedCertificateToStore@@3P6AHPEAXKPEBEKKPEAPEBU_CERT_CONTEXT@@@ZEA; int (*gpfnCertAddEncodedCertificateToStore)(void *,ulong,uchar const *,ulong,ulong,_CERT_CONTEXT const * *)
0x180005fc0  mov     [rsp+70h+dwCreationDisposition], 2
0x180005fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fcd  test    eax, eax
0x180005fcf  jnz     short loc_180005FD8
0x180005fd1  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180005fd6  jmp     short loc_18000602B
0x180005fd8  mov     edx, 58h ; 'X'; uBytes
0x180005fdd  lea     ecx, [rdx-18h]; uFlags
0x180005fe0  call    cs:__imp_LocalAlloc
0x180005fe6  mov     [rbp+var_10], rax
0x180005fea  mov     rdi, rax
0x180005fed  test    rax, rax
0x180005ff0  jnz     short loc_180005FF9
0x180005ff2  mov     ebx, 8007000Eh
0x180005ff7  jmp     short loc_18000602D
0x180005ff9  mov     [rax+48h], r13
0x180005ffd  mov     [rax+50h], r13
0x180006001  mov     [rax+14h], r13d
0x180006005  mov     rcx, [rbp+pCertContext]; pCertContext
0x180006009  call    cs:__imp_CertDuplicateCertificateContext
0x18000600f  mov     [rdi+28h], rax
0x180006013  mov     rbx, [rbp+pCertContext]
0x180006017  call    cs:__imp_GetDesktopWindow
0x18000601d  mov     r8, rdi; unsigned __int16 **
0x180006020  mov     rdx, rbx; struct _CERT_CONTEXT *
0x180006023  mov     rcx, rax; hwnd
0x180006026  call    ?GetCertsDisplayInfoFromContext@@YAJPEAUHWND__@@PEBU_CERT_CONTEXT@@PEAU_CertDisplayInfo@@@Z; GetCertsDisplayInfoFromContext(HWND__ *,_CERT_CONTEXT const *,_CertDisplayInfo *)
0x18000602b  mov     ebx, eax
0x18000602d  mov     rcx, [rbp+pCertContext]
0x180006031  test    rcx, rcx
0x180006034  jz      short loc_180006042
0x180006036  mov     rax, cs:?gpfnCertFreeCertificateContext@@3P6AHPEBU_CERT_CONTEXT@@@ZEA; int (*gpfnCertFreeCertificateContext)(_CERT_CONTEXT const *)
0x18000603d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006042  mov     rdx, [rbp+var_20]; unsigned __int64
0x180006046  mov     rcx, [rbp+var_18]; void *
0x18000604a  call    ?CloseCertStore@@YAJPEAX_K@Z; CloseCertStore(void *,unsigned __int64)
0x18000604f  test    ebx, ebx
0x180006051  mov     esi, eax
0x180006053  cmovnz  esi, ebx
0x180006056  test    esi, esi
0x180006058  jnz     short loc_180006065
0x18000605a  test    r12, r12
0x18000605d  jz      short loc_180006065
0x18000605f  mov     [r12], rdi
0x180006063  jmp     short loc_18000606E
0x180006065  lea     rcx, [rbp+var_10]; void **
0x180006069  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x18000606e  lea     rcx, [rbp+var_28]; void **
0x180006072  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180006077  mov     eax, esi
0x180006079  mov     rbx, [rsp+70h+arg_0]
0x180006081  add     rsp, 70h
0x180006085  pop     r15
0x180006087  pop     r14
0x180006089  pop     r13
0x18000608b  pop     r12
0x18000608d  pop     rdi
0x18000608e  pop     rsi
0x18000608f  pop     rbp
0x180006090  retn
```
