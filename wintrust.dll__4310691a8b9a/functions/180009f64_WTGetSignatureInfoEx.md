# WTGetSignatureInfoEx

- ea: `0x180009f64`
- end: `0x18000a29d`
- name: `WTGetSignatureInfoEx`
- size: `825`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, unsigned int, __int64, __int64, PCCERT_CONTEXT *, __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180009f30`
- `0x180025030`
- `0x18003f450`

## callees

- `0x180009d2c`
- `0x180009f64`
- `0x18000a2a4`
- `0x18000b4ec`
- `0x18000c094`
- `0x18002d38c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a025`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a025`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0de`
- `CRYPT32!CertFreeCertificateContext` at `0x18000a1fc`
- `CRYPT32!CertFreeCertificateContext` at `0x18000a28b`
- `CRYPT32!CertFreeCertificateContext` at `0x18000a1fc`
- `CRYPT32!CertFreeCertificateContext` at `0x18000a28b`

## pseudocode

```c
__int64 __fastcall WTGetSignatureInfoEx(
        const WCHAR *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        PCCERT_CONTEXT *a6,
        __int64 *a7)
{
  PCCERT_CONTEXT *v7; // rdi
  __int64 v10; // r12
  __int64 *v12; // r14
  int ErrorError; // ebp
  __int64 v14; // rsi
  int v15; // ecx
  char v16; // al
  int v17; // esi
  int AuthenticodeSignatureInfo; // eax
  int v20; // esi
  int v21; // esi
  int CatalogSignatureInfo; // eax
  __int64 v23; // [rsp+40h] [rbp-58h] BYREF
  __int64 FileW; // [rsp+A0h] [rbp+8h]

  v7 = a6;
  v10 = a2;
  if ( a6 )
    *a6 = 0;
  v12 = &v23;
  v23 = 0;
  if ( a7 )
    v12 = a7;
  *v12 = 0;
  if ( !a1 || !a4 || *(_DWORD *)a4 < 0x58u || (a3 & 7) == 0 )
  {
    ErrorError = -2147024809;
LABEL_38:
    if ( v7 )
    {
      CertFreeCertificateContext(*v7);
      *v7 = 0;
    }
    if ( *v12 )
    {
      FreeWVTStateData(*v12);
      *v12 = 0;
    }
    goto LABEL_22;
  }
  ErrorError = 0;
  v14 = -1;
  *(_QWORD *)(a4 + 4) = 0;
  *(_QWORD *)(a4 + 12) = 0;
  FileW = -1;
  if ( (a3 & 3) != 0 )
  {
    if ( a2 == -1 )
    {
      FileW = (__int64)CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0x80u, 0);
      v10 = FileW;
      v14 = FileW;
      if ( FileW == -1 )
      {
        ErrorError = HRESULTFromLastErrorError();
        goto LABEL_18;
      }
    }
    v15 = a3 & 0x2000;
    LODWORD(a7) = v15;
    v16 = 0;
    LOBYTE(a6) = 0;
    v17 = a3 & ((v15 != 0) + 1);
    switch ( v17 )
    {
      case 0:
LABEL_26:
        v20 = (unsigned __int8)a3 & (unsigned __int8)~(_BYTE)v17 & 3;
        if ( !v20
          || *(_DWORD *)(a4 + 4) > 1u && (!v15 || !v16 && (*(_DWORD *)(a4 + 8) == 2 || *(_DWORD *)(a4 + 4) != 4)) )
        {
          goto LABEL_17;
        }
        *(_QWORD *)(a4 + 4) = 0;
        if ( v7 )
        {
          CertFreeCertificateContext(*v7);
          *v7 = 0;
        }
        FreeWVTStateData(*v12);
        *v12 = 0;
        v21 = v20 - 1;
        if ( v21 )
        {
          if ( v21 != 1 )
            goto LABEL_17;
          CatalogSignatureInfo = GetCatalogSignatureInfo(a1, v10, a3, a4, a5, v7, v12, 0);
        }
        else
        {
          CatalogSignatureInfo = GetAuthenticodeSignatureInfo((_DWORD)a1, v10, a3, a4, a5, (__int64)v7, (__int64)v12);
        }
        ErrorError = CatalogSignatureInfo;
        goto LABEL_17;
      case 1:
        AuthenticodeSignatureInfo = GetAuthenticodeSignatureInfo((_DWORD)a1, v10, a3, a4, a5, (__int64)v7, (__int64)v12);
        break;
      case 2:
        AuthenticodeSignatureInfo = GetCatalogSignatureInfo(a1, v10, a3, a4, a5, v7, v12, &a6);
        break;
      default:
LABEL_25:
        v16 = (char)a6;
        v15 = (int)a7;
        goto LABEL_26;
    }
    ErrorError = AuthenticodeSignatureInfo;
    if ( AuthenticodeSignatureInfo < 0 )
    {
LABEL_17:
      v14 = FileW;
      goto LABEL_18;
    }
    goto LABEL_25;
  }
LABEL_18:
  *(_DWORD *)(a4 + 16) = *(_DWORD *)(a4 + 12);
  if ( ErrorError >= 0 && (a3 & 4) != 0 )
    ErrorError = FillVersionInformation(a1, v10, a4);
  if ( v14 != -1 )
    CloseHandle((HANDLE)v14);
  if ( ErrorError < 0 )
    goto LABEL_38;
LABEL_22:
  if ( v23 )
    FreeWVTStateData(v23);
  return (unsigned int)ErrorError;
}

```

## disassembly

```asm
0x180009f64  push    rbx
0x180009f66  push    rbp
0x180009f67  push    rsi
0x180009f68  push    rdi
0x180009f69  push    r12
0x180009f6b  push    r13
0x180009f6d  push    r14
0x180009f6f  push    r15
0x180009f71  sub     rsp, 58h
0x180009f75  mov     rdi, [rsp+98h+arg_28]
0x180009f7d  mov     rbx, r9
0x180009f80  mov     r15d, r8d
0x180009f83  mov     r12, rdx
0x180009f86  mov     r13, rcx
0x180009f89  test    rdi, rdi
0x180009f8c  jz      short loc_180009F95
0x180009f8e  mov     qword ptr [rdi], 0
0x180009f95  mov     rax, [rsp+98h+arg_30]
0x180009f9d  lea     r14, [rsp+98h+var_58]
0x180009fa2  test    rax, rax
0x180009fa5  mov     [rsp+98h+var_58], 0
0x180009fae  cmovnz  r14, rax
0x180009fb2  mov     qword ptr [r14], 0
0x180009fb9  test    r13, r13
0x180009fbc  jz      loc_18000A1EF
0x180009fc2  test    rbx, rbx
0x180009fc5  jz      loc_18000A1EF
0x180009fcb  cmp     dword ptr [r9], 58h ; 'X'
0x180009fcf  jb      loc_18000A1EF
0x180009fd5  test    r15b, 7
0x180009fd9  jz      loc_18000A1EF
0x180009fdf  xor     ebp, ebp
0x180009fe1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009fe5  mov     [r9+4], rbp
0x180009fe9  mov     [r9+0Ch], rbp
0x180009fed  mov     [rsp+98h+arg_0], rsi
0x180009ff5  test    r15b, 3
0x180009ff9  jz      loc_18000A0C7
0x180009fff  cmp     rdx, rsi
0x18000a002  jnz     short loc_18000A043
0x18000a004  mov     [rsp+98h+hTemplateFile], rbp; hTemplateFile
0x18000a009  lea     r8d, [rbp+5]; dwShareMode
0x18000a00d  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000a015  xor     r9d, r9d; lpSecurityAttributes
0x18000a018  mov     edx, 80000000h; dwDesiredAccess
0x18000a01d  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a025  call    cs:__imp_CreateFileW
0x18000a02b  mov     [rsp+98h+arg_0], rax
0x18000a033  mov     r12, rax
0x18000a036  mov     rsi, rax
0x18000a039  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a03d  jz      loc_18000A226
0x18000a043  mov     ecx, r15d
0x18000a046  and     ecx, 2000h
0x18000a04c  mov     eax, ecx
0x18000a04e  mov     dword ptr [rsp+98h+arg_30], ecx
0x18000a055  neg     eax
0x18000a057  mov     al, bpl
0x18000a05a  sbb     esi, esi
0x18000a05c  mov     byte ptr [rsp+98h+arg_28], al
0x18000a063  neg     esi
0x18000a065  inc     esi
0x18000a067  and     esi, r15d
0x18000a06a  jz      loc_18000A11B
0x18000a070  mov     ecx, esi
0x18000a072  sub     ecx, 1
0x18000a075  jz      loc_18000A1C2
0x18000a07b  cmp     ecx, 1
0x18000a07e  jnz     loc_18000A10D
0x18000a084  lea     rax, [rsp+98h+arg_28]
0x18000a08c  mov     r9, rbx
0x18000a08f  mov     [rsp+98h+var_60], rax
0x18000a094  mov     r8d, r15d
0x18000a097  mov     rax, [rsp+98h+arg_20]
0x18000a09f  mov     rdx, r12
0x18000a0a2  mov     [rsp+98h+hTemplateFile], r14
0x18000a0a7  mov     rcx, r13
0x18000a0aa  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rdi
0x18000a0af  mov     qword ptr [rsp+98h+dwCreationDisposition], rax
0x18000a0b4  call    _GetCatalogSignatureInfo
0x18000a0b9  mov     ebp, eax
0x18000a0bb  test    eax, eax
0x18000a0bd  jns     short loc_18000A10D
0x18000a0bf  mov     rsi, [rsp+98h+arg_0]
0x18000a0c7  mov     eax, [rbx+0Ch]
0x18000a0ca  mov     [rbx+10h], eax
0x18000a0cd  test    ebp, ebp
0x18000a0cf  jns     loc_18000A1A3
0x18000a0d5  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000a0d9  jz      short loc_18000A0E4
0x18000a0db  mov     rcx, rsi; hObject
0x18000a0de  call    cs:__imp_CloseHandle
0x18000a0e4  test    ebp, ebp
0x18000a0e6  js      loc_18000A1F4
0x18000a0ec  mov     rcx, [rsp+98h+var_58]
0x18000a0f1  test    rcx, rcx
0x18000a0f4  jnz     loc_18000A199
0x18000a0fa  mov     eax, ebp
0x18000a0fc  add     rsp, 58h
0x18000a100  pop     r15
0x18000a102  pop     r14
0x18000a104  pop     r13
0x18000a106  pop     r12
0x18000a108  pop     rdi
0x18000a109  pop     rsi
0x18000a10a  pop     rbp
0x18000a10b  pop     rbx
0x18000a10c  retn
0x18000a10d  mov     al, byte ptr [rsp+98h+arg_28]
0x18000a114  mov     ecx, dword ptr [rsp+98h+arg_30]
0x18000a11b  not     esi
0x18000a11d  and     esi, r15d
0x18000a120  and     esi, 3
0x18000a123  jz      short loc_18000A0BF
0x18000a125  cmp     dword ptr [rbx+4], 1
0x18000a129  ja      loc_18000A25F
0x18000a12f  mov     qword ptr [rbx+4], 0
0x18000a137  test    rdi, rdi
0x18000a13a  jnz     loc_18000A288
0x18000a140  mov     rcx, [r14]
0x18000a143  call    _FreeWVTStateData
0x18000a148  mov     qword ptr [r14], 0
0x18000a14f  sub     esi, 1
0x18000a152  jz      loc_18000A232
0x18000a158  cmp     esi, 1
0x18000a15b  jnz     loc_18000A0BF
0x18000a161  mov     rax, [rsp+98h+arg_20]
0x18000a169  mov     r9, rbx
0x18000a16c  mov     [rsp+98h+var_60], 0
0x18000a175  mov     r8d, r15d
0x18000a178  mov     [rsp+98h+hTemplateFile], r14
0x18000a17d  mov     rdx, r12
0x18000a180  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rdi
0x18000a185  mov     rcx, r13
0x18000a188  mov     qword ptr [rsp+98h+dwCreationDisposition], rax
0x18000a18d  call    _GetCatalogSignatureInfo
0x18000a192  mov     ebp, eax
0x18000a194  jmp     loc_18000A0BF
0x18000a199  call    _FreeWVTStateData
0x18000a19e  jmp     loc_18000A0FA
0x18000a1a3  test    r15b, 4
0x18000a1a7  jz      loc_18000A0D5
0x18000a1ad  mov     r8, rbx
0x18000a1b0  mov     rdx, r12
0x18000a1b3  mov     rcx, r13
0x18000a1b6  call    _FillVersionInformation
0x18000a1bb  mov     ebp, eax
0x18000a1bd  jmp     loc_18000A0D5
0x18000a1c2  mov     rax, [rsp+98h+arg_20]
0x18000a1ca  mov     r9, rbx
0x18000a1cd  mov     [rsp+98h+hTemplateFile], r14
0x18000a1d2  mov     r8d, r15d
0x18000a1d5  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rdi
0x18000a1da  mov     rdx, r12
0x18000a1dd  mov     rcx, r13
0x18000a1e0  mov     qword ptr [rsp+98h+dwCreationDisposition], rax
0x18000a1e5  call    _GetAuthenticodeSignatureInfo
0x18000a1ea  jmp     loc_18000A0B9
0x18000a1ef  mov     ebp, 80070057h
0x18000a1f4  test    rdi, rdi
0x18000a1f7  jz      short loc_18000A209
0x18000a1f9  mov     rcx, [rdi]; pCertContext
0x18000a1fc  call    cs:__imp_CertFreeCertificateContext
0x18000a202  mov     qword ptr [rdi], 0
0x18000a209  mov     rcx, [r14]
0x18000a20c  test    rcx, rcx
0x18000a20f  jz      loc_18000A0EC
0x18000a215  call    _FreeWVTStateData
0x18000a21a  mov     qword ptr [r14], 0
0x18000a221  jmp     loc_18000A0EC
0x18000a226  call    HRESULTFromLastErrorError
0x18000a22b  mov     ebp, eax
0x18000a22d  jmp     loc_18000A0C7
0x18000a232  mov     rax, [rsp+98h+arg_20]
0x18000a23a  mov     r9, rbx
0x18000a23d  mov     [rsp+98h+hTemplateFile], r14
0x18000a242  mov     r8d, r15d
0x18000a245  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rdi
0x18000a24a  mov     rdx, r12
0x18000a24d  mov     rcx, r13
0x18000a250  mov     qword ptr [rsp+98h+dwCreationDisposition], rax
0x18000a255  call    _GetAuthenticodeSignatureInfo
0x18000a25a  jmp     loc_18000A192
0x18000a25f  test    ecx, ecx
0x18000a261  jz      loc_18000A0BF
0x18000a267  test    al, al
0x18000a269  jnz     loc_18000A12F
0x18000a26f  cmp     dword ptr [rbx+8], 2
0x18000a273  jz      loc_18000A0BF
0x18000a279  cmp     dword ptr [rbx+4], 4
0x18000a27d  jz      loc_18000A12F
0x18000a283  jmp     loc_18000A0BF
0x18000a288  mov     rcx, [rdi]; pCertContext
0x18000a28b  call    cs:__imp_CertFreeCertificateContext
0x18000a291  mov     qword ptr [rdi], 0
0x18000a298  jmp     loc_18000A140
```
