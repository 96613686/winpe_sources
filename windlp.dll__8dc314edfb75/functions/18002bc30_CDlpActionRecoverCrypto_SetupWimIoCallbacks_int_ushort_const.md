# CDlpActionRecoverCrypto::SetupWimIoCallbacks(int,ushort const *)

- ea: `0x18002bc30`
- end: `0x18002beac`
- name: `?SetupWimIoCallbacks@CDlpActionRecoverCrypto@@AEAAJHPEBG@Z`
- size: `636`
- prototype: `int(CDlpActionRecoverCrypto *__hidden this, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180013444`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18002bc30`
- `0x180081010`

## import_xrefs

- `WIMGAPI!WIMSetFileIOCallbackTemporaryPath` at `0x18002bd59`
- `WIMGAPI!WIMSetFileIOCallbackTemporaryPath` at `0x18002bddc`
- `WIMGAPI!WIMSetFileIOCallbackTemporaryPath` at `0x18002bd59`
- `WIMGAPI!WIMSetFileIOCallbackTemporaryPath` at `0x18002bddc`
- `WIMGAPI!WIMInitFileIOCallbacks` at `0x18002bd04`
- `WIMGAPI!WIMInitFileIOCallbacks` at `0x18002be2c`
- `WIMGAPI!WIMInitFileIOCallbacks` at `0x18002bd04`
- `WIMGAPI!WIMInitFileIOCallbacks` at `0x18002be2c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002bcaf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002bcaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bde6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bde6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be36`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDlpActionRecoverCrypto::SetupWimIoCallbacks(
        CDlpActionRecoverCrypto *this,
        int a2,
        const unsigned __int16 *a3)
{
  signed int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int LastError; // eax
  int v14; // [rsp+20h] [rbp-48h]
  int v15; // [rsp+28h] [rbp-40h]
  __int128 v16; // [rsp+30h] [rbp-38h] BYREF
  __int128 v17; // [rsp+40h] [rbp-28h]
  __int64 (__fastcall *v18)(void *, union _LARGE_INTEGER *); // [rsp+50h] [rbp-18h]

  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( !a2 )
  {
    if ( (unsigned int)WIMSetFileIOCallbackTemporaryPath(0) )
    {
      if ( (unsigned int)WIMInitFileIOCallbacks(0) )
      {
        v5 = 0;
        if ( g_spWimIoCallbackInstance )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)g_spWimIoCallbackInstance + 16LL))(g_spWimIoCallbackInstance);
          g_spWimIoCallbackInstance = 0;
        }
        goto LABEL_46;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v5 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_46;
      v8 = 0;
      if ( v5 < 0 )
      {
        v15 = v5;
        v14 = 910;
        goto LABEL_16;
      }
    }
    else
    {
      v11 = GetLastError();
      v5 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v5 = (unsigned __int16)v11 | 0x80070000;
      }
      else
      {
        v5 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_46;
      v8 = 0;
      if ( v5 < 0 )
      {
        v15 = v5;
        v14 = 909;
        goto LABEL_16;
      }
    }
    goto LABEL_7;
  }
  if ( a3 )
  {
    GetFileAttributesW(a3);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *(_QWORD *)&v16 = CDlpActionRecoverCrypto::WimIoCallbackOpenFile;
    *((_QWORD *)&v16 + 1) = CDlpActionRecoverCrypto::WimIoCallbackCloseFile;
    *(_QWORD *)&v17 = CDlpActionRecoverCrypto::WimIoCallbackReadFile;
    *((_QWORD *)&v17 + 1) = CDlpActionRecoverCrypto::WimIoCallbackSetFilePointer;
    v18 = CDlpActionRecoverCrypto::WimIoCallbackGetFileSize;
    if ( (unsigned int)WIMInitFileIOCallbacks(&v16) )
    {
      if ( (unsigned int)WIMSetFileIOCallbackTemporaryPath(a3) )
      {
        v5 = 0;
        if ( g_spWimIoCallbackInstance )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)g_spWimIoCallbackInstance + 16LL))(g_spWimIoCallbackInstance);
        g_spWimIoCallbackInstance = (__int64)this;
        (*(void (__fastcall **)(CDlpActionRecoverCrypto *))(*(_QWORD *)this + 8LL))(this);
        goto LABEL_46;
      }
      v10 = GetLastError();
      v5 = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          v5 = (unsigned __int16)v10 | 0x80070000;
      }
      else
      {
        v5 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_46;
      v8 = 0;
      if ( v5 < 0 )
      {
        v15 = v5;
        v14 = 901;
        goto LABEL_16;
      }
    }
    else
    {
      v9 = GetLastError();
      v5 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
      }
      else
      {
        v5 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_46;
      v8 = 0;
      if ( v5 < 0 )
      {
        v15 = v5;
        v14 = 900;
LABEL_16:
        v6 = *((_QWORD *)this + 11);
LABEL_5:
        v7 = CDlpLogT<CEmptyType>::DlpLogFormat(
               v6,
               4u,
               (__int64)L"%s(%d): Result = 0x%X",
               L"CDlpActionRecoverCrypto::SetupWimIoCallbacks",
               v14,
               v15,
               v16,
               v17,
               v18);
        v8 = (unsigned int)v7;
        if ( v7 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
      }
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
    goto LABEL_46;
  }
  v5 = -2147024809;
  v6 = *((_QWORD *)this + 11);
  if ( v6 )
  {
    v15 = -2147024809;
    v14 = 890;
    goto LABEL_5;
  }
LABEL_46:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002bc30  mov     [rsp+arg_0], rbx
0x18002bc35  push    rdi
0x18002bc36  sub     rsp, 60h
0x18002bc3a  mov     rbx, r8
0x18002bc3d  mov     rdi, rcx
0x18002bc40  xorps   xmm0, xmm0
0x18002bc43  xor     eax, eax
0x18002bc45  movups  [rsp+68h+var_38], xmm0
0x18002bc4a  movups  [rsp+68h+var_28], xmm0
0x18002bc4f  mov     [rsp+68h+var_18], rax
0x18002bc54  test    edx, edx
0x18002bc56  jz      loc_18002BDDA
0x18002bc5c  test    rbx, rbx
0x18002bc5f  jnz     short loc_18002BCAC
0x18002bc61  mov     ebx, 80070057h
0x18002bc66  mov     rcx, [rcx+58h]
0x18002bc6a  test    rcx, rcx
0x18002bc6d  jz      loc_18002BE98
0x18002bc73  mov     [rsp+68h+var_40], ebx
0x18002bc77  mov     [rsp+68h+var_48], 37Ah
0x18002bc7f  lea     r9, aCdlpactionreco_7; "CDlpActionRecoverCrypto::SetupWimIoCall"...
0x18002bc86  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002bc8d  mov     edx, 4
0x18002bc92  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002bc97  test    eax, eax
0x18002bc99  mov     ecx, eax
0x18002bc9b  jns     short loc_18002BCA2
0x18002bc9d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002bca2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002bca7  jmp     loc_18002BE98
0x18002bcac  mov     rcx, rbx; lpFileName
0x18002bcaf  call    cs:__imp_GetFileAttributesW
0x18002bcb5  xor     ecx, ecx
0x18002bcb7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002bcbc  xor     ecx, ecx
0x18002bcbe  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002bcc3  lea     rax, ?WimIoCallbackOpenFile@CDlpActionRecoverCrypto@@SAPEAXPEBG@Z; CDlpActionRecoverCrypto::WimIoCallbackOpenFile(ushort const *)
0x18002bcca  mov     qword ptr [rsp+68h+var_38], rax
0x18002bccf  lea     rax, ?WimIoCallbackCloseFile@CDlpActionRecoverCrypto@@SAHPEAX@Z; CDlpActionRecoverCrypto::WimIoCallbackCloseFile(void *)
0x18002bcd6  mov     qword ptr [rsp+68h+var_38+8], rax
0x18002bcdb  lea     rax, ?WimIoCallbackReadFile@CDlpActionRecoverCrypto@@SAHPEAX0KPEAKPEAU_OVERLAPPED@@@Z; CDlpActionRecoverCrypto::WimIoCallbackReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *)
0x18002bce2  mov     qword ptr [rsp+68h+var_28], rax
0x18002bce7  lea     rax, ?WimIoCallbackSetFilePointer@CDlpActionRecoverCrypto@@SAHPEAXT_LARGE_INTEGER@@PEAT2@K@Z; CDlpActionRecoverCrypto::WimIoCallbackSetFilePointer(void *,_LARGE_INTEGER,_LARGE_INTEGER *,ulong)
0x18002bcee  mov     qword ptr [rsp+68h+var_28+8], rax
0x18002bcf3  lea     rax, ?WimIoCallbackGetFileSize@CDlpActionRecoverCrypto@@SAHPEAXPEAT_LARGE_INTEGER@@@Z; CDlpActionRecoverCrypto::WimIoCallbackGetFileSize(void *,_LARGE_INTEGER *)
0x18002bcfa  mov     [rsp+68h+var_18], rax
0x18002bcff  lea     rcx, [rsp+68h+var_38]
0x18002bd04  call    cs:__imp_WIMInitFileIOCallbacks
0x18002bd0a  test    eax, eax
0x18002bd0c  jnz     short loc_18002BD56
0x18002bd0e  call    cs:__imp_GetLastError
0x18002bd14  mov     ebx, eax
0x18002bd16  test    eax, eax
0x18002bd18  jnz     short loc_18002BD21
0x18002bd1a  mov     ebx, 80004005h
0x18002bd1f  jmp     short loc_18002BD2C
0x18002bd21  jle     short loc_18002BD2C
0x18002bd23  movzx   ebx, ax
0x18002bd26  or      ebx, 80070000h
0x18002bd2c  cmp     qword ptr [rdi+58h], 0
0x18002bd31  jz      loc_18002BE98
0x18002bd37  xor     ecx, ecx
0x18002bd39  test    ebx, ebx
0x18002bd3b  jns     loc_18002BCA2
0x18002bd41  mov     [rsp+68h+var_40], ebx
0x18002bd45  mov     [rsp+68h+var_48], 384h
0x18002bd4d  mov     rcx, [rdi+58h]
0x18002bd51  jmp     loc_18002BC7F
0x18002bd56  mov     rcx, rbx
0x18002bd59  call    cs:__imp_WIMSetFileIOCallbackTemporaryPath
0x18002bd5f  test    eax, eax
0x18002bd61  jnz     short loc_18002BDA4
0x18002bd63  call    cs:__imp_GetLastError
0x18002bd69  mov     ebx, eax
0x18002bd6b  test    eax, eax
0x18002bd6d  jnz     short loc_18002BD76
0x18002bd6f  mov     ebx, 80004005h
0x18002bd74  jmp     short loc_18002BD81
0x18002bd76  jle     short loc_18002BD81
0x18002bd78  movzx   ebx, ax
0x18002bd7b  or      ebx, 80070000h
0x18002bd81  cmp     qword ptr [rdi+58h], 0
0x18002bd86  jz      loc_18002BE98
0x18002bd8c  xor     ecx, ecx
0x18002bd8e  test    ebx, ebx
0x18002bd90  jns     loc_18002BCA2
0x18002bd96  mov     [rsp+68h+var_40], ebx
0x18002bd9a  mov     [rsp+68h+var_48], 385h
0x18002bda2  jmp     short loc_18002BD4D
0x18002bda4  xor     ebx, ebx
0x18002bda6  mov     rcx, cs:?g_spWimIoCallbackInstance@@3V?$SP_COM@VCDlpActionRecoverCrypto@@@@A; SP_COM<CDlpActionRecoverCrypto> g_spWimIoCallbackInstance
0x18002bdad  test    rcx, rcx
0x18002bdb0  jz      short loc_18002BDBF
0x18002bdb2  mov     rax, [rcx]
0x18002bdb5  mov     rax, [rax+10h]
0x18002bdb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdbe  nop
0x18002bdbf  mov     cs:?g_spWimIoCallbackInstance@@3V?$SP_COM@VCDlpActionRecoverCrypto@@@@A, rdi; SP_COM<CDlpActionRecoverCrypto> g_spWimIoCallbackInstance
0x18002bdc6  mov     rax, [rdi]
0x18002bdc9  mov     rcx, rdi
0x18002bdcc  mov     rax, [rax+8]
0x18002bdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdd5  jmp     loc_18002BE98
0x18002bdda  xor     ecx, ecx
0x18002bddc  call    cs:__imp_WIMSetFileIOCallbackTemporaryPath
0x18002bde2  test    eax, eax
0x18002bde4  jnz     short loc_18002BE2A
0x18002bde6  call    cs:__imp_GetLastError
0x18002bdec  mov     ebx, eax
0x18002bdee  test    eax, eax
0x18002bdf0  jnz     short loc_18002BDF9
0x18002bdf2  mov     ebx, 80004005h
0x18002bdf7  jmp     short loc_18002BE04
0x18002bdf9  jle     short loc_18002BE04
0x18002bdfb  movzx   ebx, ax
0x18002bdfe  or      ebx, 80070000h
0x18002be04  cmp     qword ptr [rdi+58h], 0
0x18002be09  jz      loc_18002BE98
0x18002be0f  xor     ecx, ecx
0x18002be11  test    ebx, ebx
0x18002be13  jns     loc_18002BCA2
0x18002be19  mov     [rsp+68h+var_40], ebx
0x18002be1d  mov     [rsp+68h+var_48], 38Dh
0x18002be25  jmp     loc_18002BD4D
0x18002be2a  xor     ecx, ecx
0x18002be2c  call    cs:__imp_WIMInitFileIOCallbacks
0x18002be32  test    eax, eax
0x18002be34  jnz     short loc_18002BE76
0x18002be36  call    cs:__imp_GetLastError
0x18002be3c  mov     ebx, eax
0x18002be3e  test    eax, eax
0x18002be40  jnz     short loc_18002BE49
0x18002be42  mov     ebx, 80004005h
0x18002be47  jmp     short loc_18002BE54
0x18002be49  jle     short loc_18002BE54
0x18002be4b  movzx   ebx, ax
0x18002be4e  or      ebx, 80070000h
0x18002be54  cmp     qword ptr [rdi+58h], 0
0x18002be59  jz      short loc_18002BE98
0x18002be5b  xor     ecx, ecx
0x18002be5d  test    ebx, ebx
0x18002be5f  jns     loc_18002BCA2
0x18002be65  mov     [rsp+68h+var_40], ebx
0x18002be69  mov     [rsp+68h+var_48], 38Eh
0x18002be71  jmp     loc_18002BD4D
0x18002be76  xor     ebx, ebx
0x18002be78  mov     rcx, cs:?g_spWimIoCallbackInstance@@3V?$SP_COM@VCDlpActionRecoverCrypto@@@@A; SP_COM<CDlpActionRecoverCrypto> g_spWimIoCallbackInstance
0x18002be7f  test    rcx, rcx
0x18002be82  jz      short loc_18002BE98
0x18002be84  mov     rdx, [rcx]
0x18002be87  mov     rax, [rdx+10h]
0x18002be8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be90  nop
0x18002be91  mov     cs:?g_spWimIoCallbackInstance@@3V?$SP_COM@VCDlpActionRecoverCrypto@@@@A, rbx; SP_COM<CDlpActionRecoverCrypto> g_spWimIoCallbackInstance
0x18002be98  mov     ecx, ebx
0x18002be9a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002be9f  mov     eax, ebx
0x18002bea1  mov     rbx, [rsp+68h+arg_0]
0x18002bea6  add     rsp, 60h
0x18002beaa  pop     rdi
0x18002beab  retn
```
