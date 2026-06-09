# CDlpActionRecoverCrypto::VerifyFileSize(_ULARGE_INTEGER *)

- ea: `0x18002e458`
- end: `0x18002e5e3`
- name: `?VerifyFileSize@CDlpActionRecoverCrypto@@AEAAJPEAT_ULARGE_INTEGER@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800165d0`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18002e458`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002e534`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002e534`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e49e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e49e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e4bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e53e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e4bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e53e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e5cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e5cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpActionRecoverCrypto::VerifyFileSize(LPCWSTR *this, union _ULARGE_INTEGER *a2)
{
  __int64 FileW; // rbx
  signed int v5; // eax
  signed int v6; // edi
  __int64 v7; // rcx
  int v8; // eax
  signed int LastError; // eax
  LPCWSTR v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-38h]
  __int64 v13; // [rsp+28h] [rbp-30h]
  union _LARGE_INTEGER FileSize; // [rsp+60h] [rbp+8h] BYREF
  __int64 v15; // [rsp+70h] [rbp+18h]

  FileSize.QuadPart = 0;
  FileW = (__int64)CreateFileW(this[69], 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v15 = FileW;
    if ( GetFileSizeEx((HANDLE)FileW, &FileSize) )
    {
      v6 = 0;
      v10 = this[11];
      if ( v10 )
      {
        if ( (LPCWSTR)FileSize.QuadPart == this[90] )
          CDlpLogT<CEmptyType>::DlpLogFormat(v10, 2, L"RecoverCrypto: File size matches.");
        else
          CDlpLogT<CEmptyType>::DlpLogFormat(v10, 3, L"RecoverCrypto: File size DOES NOT match.");
      }
      *a2 = (union _ULARGE_INTEGER)FileSize.QuadPart;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v6 = -2147467259;
      }
      if ( this[11] )
      {
        v7 = 0;
        if ( v6 < 0 )
        {
          LODWORD(v13) = v6;
          LODWORD(v12) = 2575;
LABEL_9:
          v8 = CDlpLogT<CEmptyType>::DlpLogFormat(
                 this[11],
                 4,
                 L"%s(%d): Result = 0x%X",
                 L"CDlpActionRecoverCrypto::VerifyFileSize",
                 v12,
                 v13);
          v7 = (unsigned int)v8;
          if ( v8 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
        }
LABEL_11:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
      }
    }
  }
  else
  {
    FileW = -1;
    v15 = -1;
    v5 = GetLastError();
    v6 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( this[11] )
    {
      v7 = 0;
      if ( v6 < 0 )
      {
        LODWORD(v13) = v6;
        LODWORD(v12) = 2571;
        goto LABEL_9;
      }
      goto LABEL_11;
    }
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002e458  mov     rax, rsp
0x18002e45b  mov     [rax+10h], rbx
0x18002e45f  push    rsi
0x18002e460  push    rdi
0x18002e461  push    r14
0x18002e463  sub     rsp, 40h
0x18002e467  mov     r14, rdx
0x18002e46a  mov     rsi, rcx
0x18002e46d  mov     qword ptr [rax+8], 0
0x18002e475  mov     qword ptr [rax-28h], 0
0x18002e47d  mov     dword ptr [rax-30h], 8000000h
0x18002e484  mov     dword ptr [rax-38h], 3
0x18002e48b  xor     r9d, r9d; lpSecurityAttributes
0x18002e48e  mov     edx, 80000000h; dwDesiredAccess
0x18002e493  lea     r8d, [r9+3]; dwShareMode
0x18002e497  mov     rcx, [rcx+228h]; lpFileName
0x18002e49e  call    cs:__imp_CreateFileW
0x18002e4a4  mov     rbx, rax
0x18002e4a7  inc     rax
0x18002e4aa  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e4b0  jnz     short loc_18002E527
0x18002e4b2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e4b6  mov     [rsp+58h+arg_10], rbx
0x18002e4bb  call    cs:__imp_GetLastError
0x18002e4c1  mov     edi, eax
0x18002e4c3  test    eax, eax
0x18002e4c5  jnz     short loc_18002E4CE
0x18002e4c7  mov     edi, 80004005h
0x18002e4cc  jmp     short loc_18002E4D9
0x18002e4ce  jle     short loc_18002E4D9
0x18002e4d0  movzx   edi, ax
0x18002e4d3  or      edi, 80070000h
0x18002e4d9  cmp     qword ptr [rsi+58h], 0
0x18002e4de  jz      loc_18002E5B8
0x18002e4e4  xor     ecx, ecx
0x18002e4e6  test    edi, edi
0x18002e4e8  jns     short loc_18002E51D
0x18002e4ea  mov     dword ptr [rsp+58h+var_30], edi
0x18002e4ee  mov     dword ptr [rsp+58h+var_38], 0A0Bh
0x18002e4f6  lea     r9, aCdlpactionreco_26; "CDlpActionRecoverCrypto::VerifyFileSize"
0x18002e4fd  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002e504  mov     edx, 4
0x18002e509  mov     rcx, [rsi+58h]
0x18002e50d  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002e512  test    eax, eax
0x18002e514  mov     ecx, eax
0x18002e516  jns     short loc_18002E51D
0x18002e518  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002e51d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002e522  jmp     loc_18002E5B8
0x18002e527  mov     [rsp+58h+arg_10], rbx
0x18002e52c  lea     rdx, [rsp+58h+FileSize]; lpFileSize
0x18002e531  mov     rcx, rbx; hFile
0x18002e534  call    cs:__imp_GetFileSizeEx
0x18002e53a  test    eax, eax
0x18002e53c  jnz     short loc_18002E57A
0x18002e53e  call    cs:__imp_GetLastError
0x18002e544  mov     edi, eax
0x18002e546  test    eax, eax
0x18002e548  jnz     short loc_18002E551
0x18002e54a  mov     edi, 80004005h
0x18002e54f  jmp     short loc_18002E55C
0x18002e551  jle     short loc_18002E55C
0x18002e553  movzx   edi, ax
0x18002e556  or      edi, 80070000h
0x18002e55c  cmp     qword ptr [rsi+58h], 0
0x18002e561  jz      short loc_18002E5B8
0x18002e563  xor     ecx, ecx
0x18002e565  test    edi, edi
0x18002e567  jns     short loc_18002E51D
0x18002e569  mov     dword ptr [rsp+58h+var_30], edi
0x18002e56d  mov     dword ptr [rsp+58h+var_38], 0A0Fh
0x18002e575  jmp     loc_18002E4F6
0x18002e57a  xor     edi, edi
0x18002e57c  mov     rcx, [rsi+58h]
0x18002e580  test    rcx, rcx
0x18002e583  jz      short loc_18002E5B0
0x18002e585  mov     rax, [rsi+2D0h]
0x18002e58c  cmp     qword ptr [rsp+58h+FileSize], rax
0x18002e591  jnz     short loc_18002E59F
0x18002e593  lea     r8, aRecovercryptoF_0; "RecoverCrypto: File size matches."
0x18002e59a  lea     edx, [rdi+2]
0x18002e59d  jmp     short loc_18002E5AB
0x18002e59f  lea     r8, aRecovercryptoF_1; "RecoverCrypto: File size DOES NOT match"...
0x18002e5a6  mov     edx, 3
0x18002e5ab  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002e5b0  mov     rcx, qword ptr [rsp+58h+FileSize]
0x18002e5b5  mov     [r14], rcx
0x18002e5b8  mov     ecx, edi
0x18002e5ba  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002e5bf  nop
0x18002e5c0  lea     rcx, [rbx-1]
0x18002e5c4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002e5c8  ja      short loc_18002E5D3
0x18002e5ca  mov     rcx, rbx; hObject
0x18002e5cd  call    cs:__imp_CloseHandle
0x18002e5d3  mov     eax, edi
0x18002e5d5  mov     rbx, [rsp+58h+arg_8]
0x18002e5da  add     rsp, 40h
0x18002e5de  pop     r14
0x18002e5e0  pop     rdi
0x18002e5e1  pop     rsi
0x18002e5e2  retn
```
