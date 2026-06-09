# CDlpActionRecoverCrypto::GetImageRangesFromWim(void)

- ea: `0x18001ae2c`
- end: `0x18001b017`
- name: `?GetImageRangesFromWim@CDlpActionRecoverCrypto@@AEAAJXZ`
- size: `491`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001875c`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001ae2c`
- `0x18001fd60`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x18001af55`
- `WIMGAPI!WIMCloseHandle` at `0x18001af68`
- `WIMGAPI!WIMCloseHandle` at `0x18001aff8`
- `WIMGAPI!WIMCloseHandle` at `0x18001af55`
- `WIMGAPI!WIMCloseHandle` at `0x18001af68`
- `WIMGAPI!WIMCloseHandle` at `0x18001aff8`
- `WIMGAPI!WIMGetImageCount` at `0x18001af00`
- `WIMGAPI!WIMGetImageCount` at `0x18001af00`
- `WIMGAPI!WIMLoadImage` at `0x18001af44`
- `WIMGAPI!WIMLoadImage` at `0x18001af44`
- `WIMGAPI!WIMCreateFile` at `0x18001aea2`
- `WIMGAPI!WIMCreateFile` at `0x18001aea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aeb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aeb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af85`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDlpActionRecoverCrypto::GetImageRangesFromWim(CDlpActionRecoverCrypto *this)
{
  __int64 v2; // rcx
  signed int v3; // esi
  __int64 v4; // rax
  __int64 v5; // rbx
  signed int v6; // eax
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // r12d
  __int64 v10; // rcx
  unsigned int v11; // r14d
  __int64 v12; // r15
  signed int LastError; // eax
  int v14; // eax
  __int64 v16; // [rsp+20h] [rbp-38h]
  __int64 v17; // [rsp+28h] [rbp-30h]

  v2 = *((_QWORD *)this + 11);
  if ( v2 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v2, 2, L"RecoverCrypto:GetImageRangesFromWim -> Searching for Image ranges...");
  v3 = 1;
  *((_DWORD *)this + 182) = 1;
  v4 = WIMCreateFile(*((_QWORD *)this + 69), 0x80000000LL, 3, 0x20000000, 0, 0);
  v5 = v4;
  if ( v4 )
  {
    v8 = WIMGetImageCount(v4);
    v9 = v8;
    v10 = *((_QWORD *)this + 11);
    if ( v10 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v10, 2, L"RecoverCrypto:GetImageRangesFromWim -> ImageCount = [%d]", v8);
    if ( !v9 )
    {
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_30;
      v7 = 0;
      goto LABEL_29;
    }
    v11 = 1;
    while ( 1 )
    {
      v12 = WIMLoadImage(v5, v11);
      if ( !v12 )
        break;
      WIMCloseHandle(v12);
      if ( ++v11 > v9 )
      {
        v3 = 0;
        goto LABEL_30;
      }
    }
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v7 = 0;
      if ( v3 < 0 )
      {
        LODWORD(v17) = v3;
        LODWORD(v16) = 984;
LABEL_27:
        v14 = CDlpLogT<CEmptyType>::DlpLogFormat(
                *((_QWORD *)this + 11),
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionRecoverCrypto::GetImageRangesFromWim",
                v16,
                v17);
        v7 = (unsigned int)v14;
        if ( v14 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
      }
LABEL_29:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
    }
  }
  else
  {
    v6 = GetLastError();
    v3 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v7 = 0;
      if ( v3 < 0 )
      {
        LODWORD(v17) = v3;
        LODWORD(v16) = 969;
        goto LABEL_27;
      }
      goto LABEL_29;
    }
  }
LABEL_30:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  if ( v5 )
    WIMCloseHandle(v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001ae2c  mov     rax, rsp
0x18001ae2f  mov     [rax+18h], rbx
0x18001ae33  mov     [rax+20h], rbp
0x18001ae37  push    rsi
0x18001ae38  push    rdi
0x18001ae39  push    r12
0x18001ae3b  push    r14
0x18001ae3d  push    r15
0x18001ae3f  sub     rsp, 30h
0x18001ae43  mov     rbp, rcx
0x18001ae46  mov     qword ptr [rax+8], 0
0x18001ae4e  xor     edi, edi
0x18001ae50  mov     [rax+10h], rdi
0x18001ae54  mov     rcx, [rcx+58h]
0x18001ae58  lea     r14d, [rdi+2]
0x18001ae5c  test    rcx, rcx
0x18001ae5f  jz      short loc_18001AE70
0x18001ae61  lea     r8, aRecovercryptoG; "RecoverCrypto:GetImageRangesFromWim -> "...
0x18001ae68  mov     edx, r14d
0x18001ae6b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001ae70  mov     esi, 1
0x18001ae75  mov     [rbp+2D8h], esi
0x18001ae7b  mov     [rsp+58h+var_30], 0
0x18001ae84  mov     dword ptr [rsp+58h+var_38], 0
0x18001ae8c  mov     edx, 80000000h
0x18001ae91  mov     r9d, 20000000h
0x18001ae97  lea     r8d, [rsi+2]
0x18001ae9b  mov     rcx, [rbp+228h]
0x18001aea2  call    cs:__imp_WIMCreateFile
0x18001aea8  mov     rbx, rax
0x18001aeab  test    rax, rax
0x18001aeae  jnz     short loc_18001AEF8
0x18001aeb0  mov     [rsp+58h+arg_0], rax
0x18001aeb5  call    cs:__imp_GetLastError
0x18001aebb  mov     esi, eax
0x18001aebd  test    eax, eax
0x18001aebf  jnz     short loc_18001AEC8
0x18001aec1  mov     esi, 80004005h
0x18001aec6  jmp     short loc_18001AED3
0x18001aec8  jle     short loc_18001AED3
0x18001aeca  movzx   esi, ax
0x18001aecd  or      esi, 80070000h
0x18001aed3  cmp     [rbp+58h], rbx
0x18001aed7  jz      loc_18001AFE8
0x18001aedd  xor     ecx, ecx
0x18001aedf  test    esi, esi
0x18001aee1  jns     loc_18001AFE3
0x18001aee7  mov     dword ptr [rsp+58h+var_30], esi
0x18001aeeb  mov     dword ptr [rsp+58h+var_38], 3C9h
0x18001aef3  jmp     loc_18001AFBC
0x18001aef8  mov     [rsp+58h+arg_0], rbx
0x18001aefd  mov     rcx, rbx
0x18001af00  call    cs:__imp_WIMGetImageCount
0x18001af06  mov     r12d, eax
0x18001af09  mov     rcx, [rbp+58h]
0x18001af0d  test    rcx, rcx
0x18001af10  jz      short loc_18001AF24
0x18001af12  mov     r9d, eax
0x18001af15  lea     r8, aRecovercryptoG_0; "RecoverCrypto:GetImageRangesFromWim -> "...
0x18001af1c  mov     edx, r14d
0x18001af1f  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001af24  test    r12d, r12d
0x18001af27  jnz     short loc_18001AF3B
0x18001af29  cmp     qword ptr [rbp+58h], 0
0x18001af2e  jz      loc_18001AFE8
0x18001af34  xor     ecx, ecx
0x18001af36  jmp     loc_18001AFE3
0x18001af3b  mov     r14d, esi
0x18001af3e  mov     edx, r14d
0x18001af41  mov     rcx, rbx
0x18001af44  call    cs:__imp_WIMLoadImage
0x18001af4a  mov     r15, rax
0x18001af4d  test    rdi, rdi
0x18001af50  jz      short loc_18001AF5B
0x18001af52  mov     rcx, rdi
0x18001af55  call    cs:__imp_WIMCloseHandle
0x18001af5b  test    r15, r15
0x18001af5e  jz      short loc_18001AF7C
0x18001af60  mov     [rsp+58h+arg_8], r15
0x18001af65  mov     rcx, r15
0x18001af68  call    cs:__imp_WIMCloseHandle
0x18001af6e  xor     edi, edi
0x18001af70  add     r14d, esi
0x18001af73  cmp     r14d, r12d
0x18001af76  jbe     short loc_18001AF3E
0x18001af78  xor     esi, esi
0x18001af7a  jmp     short loc_18001AFE8
0x18001af7c  mov     [rsp+58h+arg_8], 0
0x18001af85  call    cs:__imp_GetLastError
0x18001af8b  mov     esi, eax
0x18001af8d  test    eax, eax
0x18001af8f  jnz     short loc_18001AF98
0x18001af91  mov     esi, 80004005h
0x18001af96  jmp     short loc_18001AFA3
0x18001af98  jle     short loc_18001AFA3
0x18001af9a  movzx   esi, ax
0x18001af9d  or      esi, 80070000h
0x18001afa3  cmp     qword ptr [rbp+58h], 0
0x18001afa8  jz      short loc_18001AFE8
0x18001afaa  xor     ecx, ecx
0x18001afac  test    esi, esi
0x18001afae  jns     short loc_18001AFE3
0x18001afb0  mov     dword ptr [rsp+58h+var_30], esi
0x18001afb4  mov     dword ptr [rsp+58h+var_38], 3D8h
0x18001afbc  lea     r9, aCdlpactionreco_31; "CDlpActionRecoverCrypto::GetImageRanges"...
0x18001afc3  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001afca  mov     edx, 4
0x18001afcf  mov     rcx, [rbp+58h]
0x18001afd3  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001afd8  test    eax, eax
0x18001afda  mov     ecx, eax
0x18001afdc  jns     short loc_18001AFE3
0x18001afde  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001afe3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001afe8  mov     ecx, esi
0x18001afea  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001afef  nop
0x18001aff0  test    rbx, rbx
0x18001aff3  jz      short loc_18001AFFE
0x18001aff5  mov     rcx, rbx
0x18001aff8  call    cs:__imp_WIMCloseHandle
0x18001affe  mov     eax, esi
0x18001b000  mov     rbx, [rsp+58h+arg_10]
0x18001b005  mov     rbp, [rsp+58h+arg_18]
0x18001b00a  add     rsp, 30h
0x18001b00e  pop     r15
0x18001b010  pop     r14
0x18001b012  pop     r12
0x18001b014  pop     rdi
0x18001b015  pop     rsi
0x18001b016  retn
```
