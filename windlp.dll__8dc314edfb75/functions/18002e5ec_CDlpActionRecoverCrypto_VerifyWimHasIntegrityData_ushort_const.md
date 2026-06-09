# CDlpActionRecoverCrypto::VerifyWimHasIntegrityData(ushort const *)

- ea: `0x18002e5ec`
- end: `0x18002e7d6`
- name: `?VerifyWimHasIntegrityData@CDlpActionRecoverCrypto@@AEAAJPEBG@Z`
- size: `490`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000fb18`
- `0x180013c10`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18002e5ec`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `WIMGAPI!WIMGetAttributes` at `0x18002e6ef`
- `WIMGAPI!WIMGetAttributes` at `0x18002e6ef`
- `WIMGAPI!WIMCloseHandle` at `0x18002e7ab`
- `WIMGAPI!WIMCloseHandle` at `0x18002e7ab`
- `WIMGAPI!WIMCreateFile` at `0x18002e676`
- `WIMGAPI!WIMCreateFile` at `0x18002e676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e6f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpActionRecoverCrypto::VerifyWimHasIntegrityData(
        CDlpActionRecoverCrypto *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rbx
  signed int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rax
  signed int v8; // eax
  __int64 v9; // rcx
  signed int LastError; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v14; // [rsp+20h] [rbp-278h]
  __int64 v15; // [rsp+28h] [rbp-270h]
  __int64 v16; // [rsp+30h] [rbp-268h]
  _BYTE v17[560]; // [rsp+40h] [rbp-258h] BYREF

  v4 = 0;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = *((_QWORD *)this + 11);
    if ( !v6 )
      goto LABEL_29;
    LODWORD(v15) = -2147024809;
    LODWORD(v14) = 2606;
    goto LABEL_26;
  }
  v7 = WIMCreateFile(a2, 0, 3, 0x20000000, 0, 0);
  v4 = v7;
  if ( v7 )
  {
    v16 = v7;
    memset_0(v17, 0, sizeof(v17));
    if ( (unsigned int)WIMGetAttributes(v4, v17, 560) )
    {
      v5 = 0;
      if ( (v17[552] & 4) == 0 )
      {
        v11 = *((_QWORD *)this + 11);
        if ( v11 )
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v11,
            2u,
            (__int64)L"RecoverCrypto: The source file [%s] is not a WIM that contains integrity data",
            a2);
        v5 = -2147024883;
        v6 = *((_QWORD *)this + 11);
        if ( v6 )
        {
          LODWORD(v15) = -2147024883;
          LODWORD(v14) = 2622;
LABEL_26:
          v12 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v6,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpActionRecoverCrypto::VerifyWimHasIntegrityData",
                  v14,
                  v15,
                  v16);
          v9 = (unsigned int)v12;
          if ( v12 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
          goto LABEL_28;
        }
      }
    }
    else
    {
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
      if ( *((_QWORD *)this + 11) )
      {
        v9 = 0;
        if ( v5 < 0 )
        {
          LODWORD(v15) = v5;
          LODWORD(v14) = 2617;
          goto LABEL_12;
        }
LABEL_28:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
      }
    }
  }
  else
  {
    v16 = 0;
    v8 = GetLastError();
    v5 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v9 = 0;
      if ( v5 < 0 )
      {
        LODWORD(v15) = v5;
        LODWORD(v14) = 2614;
LABEL_12:
        v6 = *((_QWORD *)this + 11);
        goto LABEL_26;
      }
      goto LABEL_28;
    }
  }
LABEL_29:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( v4 )
    WIMCloseHandle(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002e5ec  mov     [rsp+arg_10], rbx
0x18002e5f1  push    rbp
0x18002e5f2  push    rsi
0x18002e5f3  push    rdi
0x18002e5f4  sub     rsp, 280h
0x18002e5fb  mov     rax, cs:__security_cookie
0x18002e602  xor     rax, rsp
0x18002e605  mov     [rsp+298h+var_28], rax
0x18002e60d  mov     rbp, rdx
0x18002e610  mov     rsi, rcx
0x18002e613  xor     ebx, ebx
0x18002e615  mov     [rsp+298h+var_268], rbx
0x18002e61a  mov     edi, 230h
0x18002e61f  mov     r8d, edi; Size
0x18002e622  xor     edx, edx; Val
0x18002e624  lea     rcx, [rsp+298h+var_258]; void *
0x18002e629  call    memset_0
0x18002e62e  test    rbp, rbp
0x18002e631  jnz     short loc_18002E656
0x18002e633  mov     edi, 80070057h
0x18002e638  mov     rcx, [rsi+58h]
0x18002e63c  test    rcx, rcx
0x18002e63f  jz      loc_18002E79B
0x18002e645  mov     dword ptr [rsp+298h+var_270], edi
0x18002e649  mov     dword ptr [rsp+298h+var_278], 0A2Eh
0x18002e651  jmp     loc_18002E773
0x18002e656  mov     [rsp+298h+var_270], 0
0x18002e65f  mov     dword ptr [rsp+298h+var_278], 0
0x18002e667  xor     edx, edx
0x18002e669  mov     r9d, 20000000h
0x18002e66f  lea     r8d, [rdx+3]
0x18002e673  mov     rcx, rbp
0x18002e676  call    cs:__imp_WIMCreateFile
0x18002e67c  mov     rbx, rax
0x18002e67f  test    rax, rax
0x18002e682  jnz     short loc_18002E6D0
0x18002e684  mov     [rsp+298h+var_268], rax
0x18002e689  call    cs:__imp_GetLastError
0x18002e68f  mov     edi, eax
0x18002e691  test    eax, eax
0x18002e693  jnz     short loc_18002E69C
0x18002e695  mov     edi, 80004005h
0x18002e69a  jmp     short loc_18002E6A7
0x18002e69c  jle     short loc_18002E6A7
0x18002e69e  movzx   edi, ax
0x18002e6a1  or      edi, 80070000h
0x18002e6a7  cmp     [rsi+58h], rbx
0x18002e6ab  jz      loc_18002E79B
0x18002e6b1  xor     ecx, ecx
0x18002e6b3  test    edi, edi
0x18002e6b5  jns     loc_18002E796
0x18002e6bb  mov     dword ptr [rsp+298h+var_270], edi
0x18002e6bf  mov     dword ptr [rsp+298h+var_278], 0A36h
0x18002e6c7  mov     rcx, [rsi+58h]
0x18002e6cb  jmp     loc_18002E773
0x18002e6d0  mov     [rsp+298h+var_268], rbx
0x18002e6d5  mov     r8, rdi; Size
0x18002e6d8  xor     edx, edx; Val
0x18002e6da  lea     rcx, [rsp+298h+var_258]; void *
0x18002e6df  call    memset_0
0x18002e6e4  mov     r8d, edi
0x18002e6e7  lea     rdx, [rsp+298h+var_258]
0x18002e6ec  mov     rcx, rbx
0x18002e6ef  call    cs:__imp_WIMGetAttributes
0x18002e6f5  test    eax, eax
0x18002e6f7  jnz     short loc_18002E732
0x18002e6f9  call    cs:__imp_GetLastError
0x18002e6ff  mov     edi, eax
0x18002e701  test    eax, eax
0x18002e703  jnz     short loc_18002E70C
0x18002e705  mov     edi, 80004005h
0x18002e70a  jmp     short loc_18002E717
0x18002e70c  jle     short loc_18002E717
0x18002e70e  movzx   edi, ax
0x18002e711  or      edi, 80070000h
0x18002e717  cmp     qword ptr [rsi+58h], 0
0x18002e71c  jz      short loc_18002E79B
0x18002e71e  xor     ecx, ecx
0x18002e720  test    edi, edi
0x18002e722  jns     short loc_18002E796
0x18002e724  mov     dword ptr [rsp+298h+var_270], edi
0x18002e728  mov     dword ptr [rsp+298h+var_278], 0A39h
0x18002e730  jmp     short loc_18002E6C7
0x18002e732  xor     edi, edi
0x18002e734  test    [rsp+298h+var_30], 4
0x18002e73c  jnz     short loc_18002E79B
0x18002e73e  mov     rcx, [rsi+58h]
0x18002e742  test    rcx, rcx
0x18002e745  jz      short loc_18002E759
0x18002e747  mov     r9, rbp
0x18002e74a  lea     r8, aRecovercryptoT_0; "RecoverCrypto: The source file [%s] is "...
0x18002e751  lea     edx, [rdi+2]
0x18002e754  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002e759  mov     edi, 8007000Dh
0x18002e75e  mov     rcx, [rsi+58h]
0x18002e762  test    rcx, rcx
0x18002e765  jz      short loc_18002E79B
0x18002e767  mov     dword ptr [rsp+298h+var_270], edi
0x18002e76b  mov     dword ptr [rsp+298h+var_278], 0A3Eh
0x18002e773  lea     r9, aCdlpactionreco_17; "CDlpActionRecoverCrypto::VerifyWimHasIn"...
0x18002e77a  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002e781  mov     edx, 4
0x18002e786  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002e78b  test    eax, eax
0x18002e78d  mov     ecx, eax
0x18002e78f  jns     short loc_18002E796
0x18002e791  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002e796  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002e79b  mov     ecx, edi
0x18002e79d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002e7a2  nop
0x18002e7a3  test    rbx, rbx
0x18002e7a6  jz      short loc_18002E7B1
0x18002e7a8  mov     rcx, rbx
0x18002e7ab  call    cs:__imp_WIMCloseHandle
0x18002e7b1  mov     eax, edi
0x18002e7b3  mov     rcx, [rsp+298h+var_28]
0x18002e7bb  xor     rcx, rsp; StackCookie
0x18002e7be  call    __security_check_cookie
0x18002e7c3  mov     rbx, [rsp+298h+arg_10]
0x18002e7cb  add     rsp, 280h
0x18002e7d2  pop     rdi
0x18002e7d3  pop     rsi
0x18002e7d4  pop     rbp
0x18002e7d5  retn
```
