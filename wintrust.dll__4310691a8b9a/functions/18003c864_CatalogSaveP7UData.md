# CatalogSaveP7UData

- ea: `0x18003c864`
- end: `0x18003ca1a`
- name: `CatalogSaveP7UData`
- size: `438`
- prototype: `__int64 __fastcall(struct CRYPTCATSTORE_ *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18003a230`
- `0x18003ba40`

## callees

- `0x1800077b0`
- `0x18003c2c4`
- `0x18003c734`
- `0x18003c864`
- `0x180047fec`
- `0x18004de6a`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c993`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c993`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003c9c0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003c9c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c9e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c9e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c9ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c9ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c9d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c9d7`
- `CRYPT32!CryptMsgEncodeAndSignCTL` at `0x18003c90a`
- `CRYPT32!CryptMsgEncodeAndSignCTL` at `0x18003c948`
- `CRYPT32!CryptMsgEncodeAndSignCTL` at `0x18003c90a`
- `CRYPT32!CryptMsgEncodeAndSignCTL` at `0x18003c948`

## pseudocode

```c
__int64 __fastcall CatalogSaveP7UData(struct CRYPTCATSTORE_ *a1)
{
  unsigned int v2; // edx
  unsigned int v3; // r8d
  unsigned __int8 v4; // r9
  Stack_ **hReserved; // rax
  DWORD dwEncodingType; // ecx
  BYTE *pbEncoded; // rdi
  unsigned int v8; // ebx
  DWORD LastError; // r14d
  HANDLE FileW; // rax
  void *v11; // rsi
  _CMSG_SIGNED_ENCODE_INFO pSignInfo; // [rsp+40h] [rbp-69h] BYREF
  struct _CTL_INFO pCtlInfo; // [rsp+70h] [rbp-39h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+110h] [rbp+67h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+118h] [rbp+6Fh] BYREF

  memset(&pSignInfo, 0, sizeof(pSignInfo));
  memset_0(&pCtlInfo, 0, sizeof(pCtlInfo));
  hReserved = (Stack_ **)a1->hReserved;
  nNumberOfBytesToWrite = 0;
  if ( *hReserved )
    Stack_::Sort(*hReserved, v2, v3, v4);
  memset(&pSignInfo, 0, sizeof(pSignInfo));
  pSignInfo.cbSize = 48;
  if ( !(unsigned int)CatalogFillCTL(a1, &pCtlInfo) )
    return 0;
  dwEncodingType = a1->dwEncodingType;
  nNumberOfBytesToWrite = 0;
  CryptMsgEncodeAndSignCTL(dwEncodingType, &pCtlInfo, &pSignInfo, 0, 0, &nNumberOfBytesToWrite);
  if ( !nNumberOfBytesToWrite || (pbEncoded = (BYTE *)CatalogNew(nNumberOfBytesToWrite)) == 0 )
  {
    CatalogFreeCTL(&pCtlInfo);
    return 0;
  }
  v8 = CryptMsgEncodeAndSignCTL(a1->dwEncodingType, &pCtlInfo, &pSignInfo, 0, pbEncoded, &nNumberOfBytesToWrite);
  CatalogFreeCTL(&pCtlInfo);
  if ( v8 )
  {
    LastError = GetLastError();
    FileW = CreateFileW(a1->pwszP7File, 0xC0000000, 4u, 0, 2u, 0x80u, 0);
    v11 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      NumberOfBytesWritten = 0;
      if ( !WriteFile(FileW, pbEncoded, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
        || nNumberOfBytesToWrite != NumberOfBytesWritten )
      {
        v8 = 0;
      }
      CloseHandle(v11);
      if ( v8 )
        SetLastError(LastError);
    }
  }
  LocalFree(pbEncoded);
  return v8;
}

```

## disassembly

```asm
0x18003c864  mov     [rsp-8+arg_10], rbx
0x18003c869  mov     [rsp-8+arg_18], rsi
0x18003c86e  push    rbp
0x18003c86f  push    rdi
0x18003c870  push    r14
0x18003c872  lea     rbp, [rsp-47h]
0x18003c877  sub     rsp, 0F0h
0x18003c87e  xorps   xmm0, xmm0
0x18003c881  mov     rsi, rcx
0x18003c884  lea     rcx, [rbp+57h+pCtlInfo]; void *
0x18003c888  xor     edx, edx; Val
0x18003c88a  mov     r8d, 80h; Size
0x18003c890  movups  xmmword ptr [rbp+57h+pSignInfo.cbSize], xmm0
0x18003c894  movups  xmmword ptr [rbp+57h+pSignInfo.cCertEncoded], xmm0
0x18003c898  movups  xmmword ptr [rbp+57h+pSignInfo.cCrlEncoded], xmm0
0x18003c89c  call    memset_0
0x18003c8a1  mov     rax, [rsi+20h]
0x18003c8a5  mov     [rbp+57h+nNumberOfBytesToWrite], 0
0x18003c8ac  mov     rcx, [rax]; this
0x18003c8af  test    rcx, rcx
0x18003c8b2  jz      short loc_18003C8B9
0x18003c8b4  call    ?Sort@Stack_@@QEAAXKKE@Z; Stack_::Sort(ulong,ulong,uchar)
0x18003c8b9  xorps   xmm0, xmm0
0x18003c8bc  lea     rdx, [rbp+57h+pCtlInfo]; struct _CTL_INFO *
0x18003c8c0  movups  xmmword ptr [rbp+57h+pSignInfo.cbSize], xmm0
0x18003c8c4  mov     rcx, rsi; struct CRYPTCATSTORE_ *
0x18003c8c7  mov     [rbp+57h+pSignInfo.cbSize], 30h ; '0'
0x18003c8ce  movups  xmmword ptr [rbp+57h+pSignInfo.cCertEncoded], xmm0
0x18003c8d2  movups  xmmword ptr [rbp+57h+pSignInfo.cCrlEncoded], xmm0
0x18003c8d6  call    ?CatalogFillCTL@@YAHPEAUCRYPTCATSTORE_@@PEAU_CTL_INFO@@@Z; CatalogFillCTL(CRYPTCATSTORE_ *,_CTL_INFO *)
0x18003c8db  test    eax, eax
0x18003c8dd  jz      loc_18003CA00
0x18003c8e3  mov     ecx, [rsi+18h]; dwMsgEncodingType
0x18003c8e6  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x18003c8ea  mov     [rsp+100h+pcbEncoded], rax; pcbEncoded
0x18003c8ef  lea     r8, [rbp+57h+pSignInfo]; pSignInfo
0x18003c8f3  xor     r9d, r9d; dwFlags
0x18003c8f6  mov     [rsp+100h+pbEncoded], 0; pbEncoded
0x18003c8ff  lea     rdx, [rbp+57h+pCtlInfo]; pCtlInfo
0x18003c903  mov     [rbp+57h+nNumberOfBytesToWrite], 0
0x18003c90a  call    cs:__imp_CryptMsgEncodeAndSignCTL
0x18003c910  mov     ecx, [rbp+57h+nNumberOfBytesToWrite]; uBytes
0x18003c913  test    ecx, ecx
0x18003c915  jz      loc_18003C9F7
0x18003c91b  call    CatalogNew
0x18003c920  mov     rdi, rax
0x18003c923  test    rax, rax
0x18003c926  jz      loc_18003C9F7
0x18003c92c  mov     ecx, [rsi+18h]; dwMsgEncodingType
0x18003c92f  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x18003c933  mov     [rsp+100h+pcbEncoded], rax; pcbEncoded
0x18003c938  lea     r8, [rbp+57h+pSignInfo]; pSignInfo
0x18003c93c  xor     r9d, r9d; dwFlags
0x18003c93f  mov     [rsp+100h+pbEncoded], rdi; pbEncoded
0x18003c944  lea     rdx, [rbp+57h+pCtlInfo]; pCtlInfo
0x18003c948  call    cs:__imp_CryptMsgEncodeAndSignCTL
0x18003c94e  lea     rcx, [rbp+57h+pCtlInfo]; struct _CTL_INFO *
0x18003c952  mov     ebx, eax
0x18003c954  call    ?CatalogFreeCTL@@YAHPEAU_CTL_INFO@@@Z; CatalogFreeCTL(_CTL_INFO *)
0x18003c959  test    ebx, ebx
0x18003c95b  jz      loc_18003C9EA
0x18003c961  call    cs:__imp_GetLastError
0x18003c967  mov     rcx, [rsi+8]; lpFileName
0x18003c96b  xor     r9d, r9d; lpSecurityAttributes
0x18003c96e  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x18003c977  mov     edx, 0C0000000h; dwDesiredAccess
0x18003c97c  mov     dword ptr [rsp+100h+pcbEncoded], 80h; dwFlagsAndAttributes
0x18003c984  mov     r14d, eax
0x18003c987  mov     dword ptr [rsp+100h+pbEncoded], 2; dwCreationDisposition
0x18003c98f  lea     r8d, [r9+4]; dwShareMode
0x18003c993  call    cs:__imp_CreateFileW
0x18003c999  mov     rsi, rax
0x18003c99c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c9a0  jz      short loc_18003C9EA
0x18003c9a2  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18003c9a6  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003c9aa  mov     rdx, rdi; lpBuffer
0x18003c9ad  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18003c9b4  mov     rcx, rax; hFile
0x18003c9b7  mov     [rsp+100h+pbEncoded], 0; lpOverlapped
0x18003c9c0  call    cs:__imp_WriteFile
0x18003c9c6  test    eax, eax
0x18003c9c8  jz      short loc_18003C9D2
0x18003c9ca  mov     eax, [rbp+57h+NumberOfBytesWritten]
0x18003c9cd  cmp     [rbp+57h+nNumberOfBytesToWrite], eax
0x18003c9d0  jz      short loc_18003C9D4
0x18003c9d2  xor     ebx, ebx
0x18003c9d4  mov     rcx, rsi; hObject
0x18003c9d7  call    cs:__imp_CloseHandle
0x18003c9dd  test    ebx, ebx
0x18003c9df  jz      short loc_18003C9EA
0x18003c9e1  mov     ecx, r14d; dwErrCode
0x18003c9e4  call    cs:__imp_SetLastError
0x18003c9ea  mov     rcx, rdi; hMem
0x18003c9ed  call    cs:__imp_LocalFree
0x18003c9f3  mov     eax, ebx
0x18003c9f5  jmp     short loc_18003CA02
0x18003c9f7  lea     rcx, [rbp+57h+pCtlInfo]; struct _CTL_INFO *
0x18003c9fb  call    ?CatalogFreeCTL@@YAHPEAU_CTL_INFO@@@Z; CatalogFreeCTL(_CTL_INFO *)
0x18003ca00  xor     eax, eax
0x18003ca02  lea     r11, [rsp+100h+var_10]
0x18003ca0a  mov     rbx, [r11+30h]
0x18003ca0e  mov     rsi, [r11+38h]
0x18003ca12  mov     rsp, r11
0x18003ca15  pop     r14
0x18003ca17  pop     rdi
0x18003ca18  pop     rbp
0x18003ca19  retn
```
