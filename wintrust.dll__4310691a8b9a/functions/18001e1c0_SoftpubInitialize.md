# SoftpubInitialize

- ea: `0x18001e1c0`
- end: `0x18001e3b1`
- name: `SoftpubInitialize`
- size: `497`
- prototype: `__int64 __fastcall(struct _CRYPT_PROVIDER_DATA *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18001e1c0`
- `0x180027714`
- `0x180046cdc`
- `0x18004de6a`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e2d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e34b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e34b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e394`

## pseudocode

```c
__int64 __fastcall SoftpubInitialize(struct _CRYPT_PROVIDER_DATA *a1, __int64 a2)
{
  DWORD *padwTrustStepErrors; // rax
  DWORD dwProvFlags; // eax
  WINTRUST_DATA *pWintrustData; // rcx
  DWORD dwUnionChoice; // eax
  struct WINTRUST_FILE_INFO_ *pFile; // rax
  const WCHAR *pcwszFilePath; // rdi
  _QWORD *p_hFile; // rsi
  struct _PROVDATA_SIP *v10; // rax
  HANDLE FileW; // rax
  DWORD v13; // eax
  struct WINTRUST_FILE_INFO_ *v14; // rax
  DWORD v15; // eax
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  padwTrustStepErrors = a1->padwTrustStepErrors;
  if ( !padwTrustStepErrors || padwTrustStepErrors[30] )
    return 1;
  padwTrustStepErrors[31] = 0;
  a1->padwTrustStepErrors[2] = 0;
  if ( a1->cbStruct <= 0xB0 || !a1->fRecallWithState )
  {
    if ( a1->cbStruct > 0xA8 )
      a1->pszUsageOID = "1.3.6.1.5.5.7.3.3";
    dwProvFlags = a1->dwProvFlags;
    if ( (dwProvFlags & 0x8000) != 0 )
    {
      v16 = 0;
      a1->dwProvFlags = dwProvFlags | 0x100000;
      if ( (unsigned int)wintrust_test::CallTestOrDefaultFn<0,int (&)(int *),std::nullptr_t>(a1, a2, &v16) )
        GetWhqlEnforcementDateTime(a1);
    }
  }
  pWintrustData = a1->pWintrustData;
  dwUnionChoice = pWintrustData->dwUnionChoice;
  if ( dwUnionChoice == 1 )
  {
    pFile = pWintrustData->pFile;
    pcwszFilePath = pFile->pcwszFilePath;
    p_hFile = &pFile->hFile;
  }
  else
  {
    v13 = dwUnionChoice - 2;
    if ( v13 )
    {
      v15 = v13 - 1;
      if ( v15 && v15 != 3 )
        return 0;
      p_hFile = 0;
      pcwszFilePath = 0;
    }
    else
    {
      v14 = pWintrustData->pFile;
      pcwszFilePath = (const WCHAR *)v14->pgKnownSubject;
      p_hFile = &v14[1].cbStruct;
    }
  }
  if ( !a1->pPDSip )
  {
    v10 = (struct _PROVDATA_SIP *)((__int64 (__fastcall *)(__int64))a1->psPfns->pfnAlloc)(64);
    a1->pPDSip = v10;
    if ( !v10 )
    {
      a1->dwError = GetLastError();
      a1->padwTrustStepErrors[31] = -2146869247;
      return 2147942414LL;
    }
    a1->dwSubjectChoice = 1;
    memset_0(v10, 0, sizeof(struct _PROVDATA_SIP));
    a1->pPDSip->cbStruct = 64;
  }
  if ( pcwszFilePath )
  {
    a1->fOpenedFile = 0;
    if ( ((*p_hFile + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      FileW = CreateFileW(pcwszFilePath, 0x80000000, 5u, 0, 3u, 0x80u, 0);
      *p_hFile = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        a1->padwTrustStepErrors[2] = GetLastError();
        a1->padwTrustStepErrors[31] = -2146885629;
      }
      else
      {
        a1->fOpenedFile = 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001e1c0  push    rbx
0x18001e1c2  sub     rsp, 40h
0x18001e1c6  mov     rax, [rcx+50h]
0x18001e1ca  mov     rbx, rcx
0x18001e1cd  test    rax, rax
0x18001e1d0  jz      loc_18001E315
0x18001e1d6  cmp     dword ptr [rax+78h], 0
0x18001e1da  jnz     loc_18001E315
0x18001e1e0  mov     [rsp+48h+arg_8], rbp
0x18001e1e5  xor     ebp, ebp
0x18001e1e7  mov     [rax+7Ch], ebp
0x18001e1ea  mov     rax, [rcx+50h]
0x18001e1ee  mov     [rax+8], ebp
0x18001e1f1  mov     eax, [rcx]
0x18001e1f3  cmp     eax, 0B0h
0x18001e1f8  jbe     short loc_18001E202
0x18001e1fa  cmp     [rcx+0B0h], ebp
0x18001e200  jnz     short loc_18001E21D
0x18001e202  cmp     eax, 0A8h
0x18001e207  ja      loc_18001E302
0x18001e20d  mov     eax, [rcx+0C8h]
0x18001e213  bt      eax, 0Fh
0x18001e217  jb      loc_18001E366
0x18001e21d  mov     rcx, [rbx+8]
0x18001e221  mov     [rsp+48h+arg_10], rsi
0x18001e226  mov     [rsp+48h+arg_18], rdi
0x18001e22b  mov     eax, [rcx+20h]
0x18001e22e  cmp     eax, 1
0x18001e231  jnz     loc_18001E320
0x18001e237  mov     rax, [rcx+28h]
0x18001e23b  mov     rdi, [rax+8]
0x18001e23f  lea     rsi, [rax+10h]
0x18001e243  cmp     [rbx+0A0h], rbp
0x18001e24a  jnz     short loc_18001E295
0x18001e24c  mov     rax, [rbx+40h]
0x18001e250  mov     ecx, 40h ; '@'
0x18001e255  mov     rax, [rax+8]
0x18001e259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e25e  mov     [rbx+0A0h], rax
0x18001e265  test    rax, rax
0x18001e268  jz      loc_18001E34B
0x18001e26e  xor     edx, edx; Val
0x18001e270  mov     dword ptr [rbx+98h], 1
0x18001e27a  mov     r8d, 40h ; '@'; Size
0x18001e280  mov     rcx, rax; void *
0x18001e283  call    memset_0
0x18001e288  mov     rax, [rbx+0A0h]
0x18001e28f  mov     dword ptr [rax], 40h ; '@'
0x18001e295  test    rdi, rdi
0x18001e298  jz      short loc_18001E2EB
0x18001e29a  mov     [rbx+10h], ebp
0x18001e29d  mov     rax, [rsi]
0x18001e2a0  inc     rax
0x18001e2a3  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001e2a9  jnz     short loc_18001E2EB
0x18001e2ab  mov     [rsp+48h+hTemplateFile], rbp; hTemplateFile
0x18001e2b0  xor     r9d, r9d; lpSecurityAttributes
0x18001e2b3  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001e2bb  mov     edx, 80000000h; dwDesiredAccess
0x18001e2c0  mov     r8d, 5; dwShareMode
0x18001e2c6  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18001e2ce  mov     rcx, rdi; lpFileName
0x18001e2d1  call    cs:__imp_CreateFileW
0x18001e2d7  mov     [rsi], rax
0x18001e2da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e2de  jz      loc_18001E394
0x18001e2e4  mov     dword ptr [rbx+10h], 1
0x18001e2eb  xor     eax, eax
0x18001e2ed  mov     rsi, [rsp+48h+arg_10]
0x18001e2f2  mov     rdi, [rsp+48h+arg_18]
0x18001e2f7  mov     rbp, [rsp+48h+arg_8]
0x18001e2fc  add     rsp, 40h
0x18001e300  pop     rbx
0x18001e301  retn
0x18001e302  lea     rax, a136155733; "1.3.6.1.5.5.7.3.3"
0x18001e309  mov     [rcx+0A8h], rax
0x18001e310  jmp     loc_18001E20D
0x18001e315  mov     eax, 1
0x18001e31a  add     rsp, 40h
0x18001e31e  pop     rbx
0x18001e31f  retn
0x18001e320  sub     eax, 2
0x18001e323  jnz     short loc_18001E336
0x18001e325  mov     rax, [rcx+28h]
0x18001e329  mov     rdi, [rax+18h]
0x18001e32d  lea     rsi, [rax+20h]
0x18001e331  jmp     loc_18001E243
0x18001e336  sub     eax, 1
0x18001e339  jz      short loc_18001E340
0x18001e33b  cmp     eax, 3
0x18001e33e  jnz     short loc_18001E2EB
0x18001e340  mov     rsi, rbp
0x18001e343  mov     rdi, rbp
0x18001e346  jmp     loc_18001E243
0x18001e34b  call    cs:__imp_GetLastError
0x18001e351  mov     [rbx+30h], eax
0x18001e354  mov     rax, [rbx+50h]
0x18001e358  mov     dword ptr [rax+7Ch], 80096001h
0x18001e35f  mov     eax, 8007000Eh
0x18001e364  jmp     short loc_18001E2ED
0x18001e366  bts     eax, 14h
0x18001e36a  mov     [rsp+48h+arg_0], rbp
0x18001e36f  lea     r8, [rsp+48h+arg_0]
0x18001e374  mov     [rcx+0C8h], eax
0x18001e37a  call    ??$CallTestOrDefaultFn@$0A@A6AHPEAH@Z$$T@wintrust_test@@YAHPEAU_CRYPT_PROVIDER_DATA@@A6AHPEAH@Z$$QEA$$T@Z
0x18001e37f  test    eax, eax
0x18001e381  jz      loc_18001E21D
0x18001e387  mov     rcx, rbx; struct _CRYPT_PROVIDER_DATA *
0x18001e38a  call    ?GetWhqlEnforcementDateTime@@YAJPEAU_CRYPT_PROVIDER_DATA@@@Z; GetWhqlEnforcementDateTime(_CRYPT_PROVIDER_DATA *)
0x18001e38f  jmp     loc_18001E21D
0x18001e394  call    cs:__imp_GetLastError
0x18001e39a  mov     rcx, [rbx+50h]
0x18001e39e  mov     [rcx+8], eax
0x18001e3a1  mov     rax, [rbx+50h]
0x18001e3a5  mov     dword ptr [rax+7Ch], 80092003h
0x18001e3ac  jmp     loc_18001E2EB
```
