# TraceNamedPipeClientAccessDenied(void)

- ea: `0x1800ec9f0`
- end: `0x1800ecc0e`
- name: `?TraceNamedPipeClientAccessDenied@@YAJXZ`
- size: `542`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005ded0`

## callees

- `0x18000a590`
- `0x180045938`
- `0x1800ebaf8`
- `0x1800ebe8c`
- `0x1800ebf18`
- `0x1800ebfac`
- `0x1800ec9f0`
- `0x1800fc2fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800ecab8`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800ecab8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ecae5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ecafc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ecbd6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ecae5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ecafc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ecbd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800eca3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800eca3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800eca4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800eca4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ecbe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ecbe5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800ecbc8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800ecbc8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ecaa8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ecaa8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800ecb70`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800ecb70`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800ecad8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800ecad8`

## pseudocode

```c
__int64 TraceNamedPipeClientAccessDenied(void)
{
  wchar_t *v0; // rbx
  enum _TOKEN_INFORMATION_CLASS v1; // edx
  int LogonStringSid; // edi
  int ACStringSid; // eax
  HANDLE CurrentProcess; // rax
  void *v5; // rsi
  int TokenInformation; // eax
  PSID *v7; // r14
  unsigned int v8; // ecx
  __int64 v9; // r15
  size_t LengthSid; // r12
  void *v11; // rax
  enum _TOKEN_INFORMATION_CLASS v12; // edx
  unsigned int v13; // r14d
  unsigned int *v14; // r15
  const wchar_t *v15; // rcx
  wchar_t *v16; // rax
  void *v18; // [rsp+20h] [rbp-20h] BYREF
  PSID pSid; // [rsp+28h] [rbp-18h] BYREF
  const wchar_t *v20; // [rsp+30h] [rbp-10h] BYREF
  void *Block; // [rsp+80h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+48h] BYREF
  wchar_t *v23; // [rsp+90h] [rbp+50h] BYREF
  const wchar_t *v24; // [rsp+98h] [rbp+58h] BYREF

  v24 = 0;
  v0 = 0;
  LogonStringSid = SpGetLogonStringSid((struct CSpDynamicString *)&v24);
  v23 = 0;
  if ( LogonStringSid >= 0 )
  {
    ACStringSid = SpGetACStringSid(&v23);
    v0 = v23;
    LogonStringSid = ACStringSid;
  }
  TokenHandle = 0;
  if ( LogonStringSid >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      LogonStringSid = SpHrFromLastWin32Error();
  }
  v5 = 0;
  if ( LogonStringSid >= 0 )
  {
    Block = 0;
    TokenInformation = SpGetTokenInformation(TokenHandle, v1, &Block);
    v7 = (PSID *)Block;
    v8 = 0;
    LogonStringSid = TokenInformation;
    if ( TokenInformation >= 0 )
    {
      while ( v8 < *(_DWORD *)Block )
      {
        v9 = 2LL * v8;
        if ( (*((_DWORD *)Block + 4 * v8 + 4) & 0xC0000000) == 0xC0000000 )
        {
          LengthSid = GetLengthSid(*((PSID *)Block + 2 * v8 + 1));
          v11 = calloc(1u, LengthSid);
          v5 = v11;
          if ( !v11 )
          {
            LogonStringSid = -2147024882;
            goto LABEL_16;
          }
          if ( !CopySid(LengthSid, v11, v7[v9 + 1]) )
            free(v5);
          goto LABEL_17;
        }
        ++v8;
      }
    }
    LogonStringSid = -2147418113;
LABEL_16:
    v5 = 0;
LABEL_17:
    if ( v7 )
      free(v7);
  }
  pSid = 0;
  if ( LogonStringSid >= 0 )
  {
    LogonStringSid = SpGetACSid(&pSid);
    if ( LogonStringSid >= 0 )
    {
      if ( v5 )
      {
        v18 = 0;
        LODWORD(Block) = 0;
        v13 = 0;
        LogonStringSid = SpGetTokenInformation(TokenHandle, v12, &v18);
        if ( LogonStringSid >= 0 )
        {
          v14 = (unsigned int *)v18;
          while ( v13 < *v14 )
          {
            if ( EqualSid(v5, *(PSID *)&v14[4 * v13 + 2]) )
            {
              LODWORD(Block) = 1;
              break;
            }
            ++v13;
          }
        }
        if ( LogonStringSid >= 0 )
        {
          v15 = L"NULL";
          v16 = L"NULL";
          if ( v0 )
            v16 = v0;
          v18 = v16;
          if ( v24 )
            v15 = v24;
          v20 = v15;
          SPTelemetry::SrNamedPipeClientErrorNoAccess<unsigned short const *,int &,unsigned short const *>(
            &v20,
            &Block,
            &v18);
        }
      }
      else
      {
        LogonStringSid = -2147024809;
      }
    }
  }
  if ( pSid )
    FreeSid(pSid);
  if ( v5 )
    free(v5);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v23);
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v24);
  return (unsigned int)LogonStringSid;
}

```

## disassembly

```asm
0x1800ec9f0  push    rbp
0x1800ec9f2  push    rbx
0x1800ec9f3  push    rsi
0x1800ec9f4  push    rdi
0x1800ec9f5  push    r12
0x1800ec9f7  push    r14
0x1800ec9f9  push    r15
0x1800ec9fb  mov     rbp, rsp
0x1800ec9fe  sub     rsp, 40h
0x1800eca02  lea     rcx, [rbp+arg_18]; this
0x1800eca06  mov     [rbp+arg_18], 0
0x1800eca0e  call    ?SpGetLogonStringSid@@YAJAEAVCSpDynamicString@@@Z; SpGetLogonStringSid(CSpDynamicString &)
0x1800eca13  xor     ebx, ebx
0x1800eca15  mov     edi, eax
0x1800eca17  mov     [rbp+arg_10], rbx
0x1800eca1b  test    eax, eax
0x1800eca1d  js      short loc_1800ECA2E
0x1800eca1f  lea     rcx, [rbp+arg_10]
0x1800eca23  call    SpGetACStringSid
0x1800eca28  mov     rbx, [rbp+arg_10]
0x1800eca2c  mov     edi, eax
0x1800eca2e  mov     [rbp+TokenHandle], 0
0x1800eca36  test    edi, edi
0x1800eca38  js      short loc_1800ECA5D
0x1800eca3a  call    cs:__imp_GetCurrentProcess
0x1800eca40  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800eca44  mov     edx, 8; DesiredAccess
0x1800eca49  mov     rcx, rax; ProcessHandle
0x1800eca4c  call    cs:__imp_OpenProcessToken
0x1800eca52  test    eax, eax
0x1800eca54  jnz     short loc_1800ECA5D
0x1800eca56  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800eca5b  mov     edi, eax
0x1800eca5d  xor     esi, esi
0x1800eca5f  test    edi, edi
0x1800eca61  js      loc_1800ECB02
0x1800eca67  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800eca6b  lea     r8, [rbp+Block]; void **
0x1800eca6f  mov     [rbp+Block], rsi
0x1800eca73  call    ?SpGetTokenInformation@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; SpGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x1800eca78  mov     r14, [rbp+Block]
0x1800eca7c  xor     ecx, ecx
0x1800eca7e  mov     edi, eax
0x1800eca80  test    eax, eax
0x1800eca82  js      short loc_1800ECAED
0x1800eca84  mov     edx, 0C0000000h
0x1800eca89  cmp     ecx, [r14]
0x1800eca8c  jnb     short loc_1800ECAED
0x1800eca8e  mov     r15d, ecx
0x1800eca91  add     r15, r15
0x1800eca94  mov     eax, [r14+r15*8+10h]
0x1800eca99  and     eax, edx
0x1800eca9b  cmp     eax, edx
0x1800eca9d  jz      short loc_1800ECAA3
0x1800eca9f  inc     ecx
0x1800ecaa1  jmp     short loc_1800ECA89
0x1800ecaa3  mov     rcx, [r14+r15*8+8]; pSid
0x1800ecaa8  call    cs:__imp_GetLengthSid
0x1800ecaae  mov     edx, eax; Size
0x1800ecab0  mov     ecx, 1; Count
0x1800ecab5  mov     r12d, eax
0x1800ecab8  call    cs:__imp_calloc
0x1800ecabe  mov     rsi, rax
0x1800ecac1  test    rax, rax
0x1800ecac4  jnz     short loc_1800ECACD
0x1800ecac6  mov     edi, 8007000Eh
0x1800ecacb  jmp     short loc_1800ECAF2
0x1800ecacd  mov     r8, [r14+r15*8+8]; pSourceSid
0x1800ecad2  mov     rdx, rsi; pDestinationSid
0x1800ecad5  mov     ecx, r12d; nDestinationSidLength
0x1800ecad8  call    cs:__imp_CopySid
0x1800ecade  test    eax, eax
0x1800ecae0  jnz     short loc_1800ECAF4
0x1800ecae2  mov     rcx, rsi; Block
0x1800ecae5  call    cs:__imp_free
0x1800ecaeb  jmp     short loc_1800ECAF4
0x1800ecaed  mov     edi, 8000FFFFh
0x1800ecaf2  xor     esi, esi
0x1800ecaf4  test    r14, r14
0x1800ecaf7  jz      short loc_1800ECB02
0x1800ecaf9  mov     rcx, r14; Block
0x1800ecafc  call    cs:__imp_free
0x1800ecb02  mov     [rbp+pSid], 0
0x1800ecb0a  test    edi, edi
0x1800ecb0c  js      loc_1800ECBBF
0x1800ecb12  lea     rcx, [rbp+pSid]; pSid
0x1800ecb16  call    SpGetACSid
0x1800ecb1b  mov     edi, eax
0x1800ecb1d  test    eax, eax
0x1800ecb1f  js      loc_1800ECBBF
0x1800ecb25  test    rsi, rsi
0x1800ecb28  jnz     short loc_1800ECB34
0x1800ecb2a  mov     edi, 80070057h
0x1800ecb2f  jmp     loc_1800ECBBF
0x1800ecb34  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ecb38  lea     r8, [rbp+var_20]; void **
0x1800ecb3c  mov     [rbp+var_20], 0
0x1800ecb44  mov     dword ptr [rbp+Block], 0
0x1800ecb4b  call    ?SpGetTokenInformation@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; SpGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x1800ecb50  xor     r14d, r14d
0x1800ecb53  mov     edi, eax
0x1800ecb55  test    eax, eax
0x1800ecb57  js      short loc_1800ECB86
0x1800ecb59  mov     r15, [rbp+var_20]
0x1800ecb5d  cmp     r14d, [r15]
0x1800ecb60  jnb     short loc_1800ECB86
0x1800ecb62  mov     edx, r14d
0x1800ecb65  mov     rcx, rsi; pSid1
0x1800ecb68  add     rdx, rdx
0x1800ecb6b  mov     rdx, [r15+rdx*8+8]; pSid2
0x1800ecb70  call    cs:__imp_EqualSid
0x1800ecb76  test    eax, eax
0x1800ecb78  jnz     short loc_1800ECB7F
0x1800ecb7a  inc     r14d
0x1800ecb7d  jmp     short loc_1800ECB5D
0x1800ecb7f  mov     dword ptr [rbp+Block], 1
0x1800ecb86  test    edi, edi
0x1800ecb88  js      short loc_1800ECBBF
0x1800ecb8a  test    rbx, rbx
0x1800ecb8d  lea     rcx, aNull_1; "NULL"
0x1800ecb94  mov     rax, rcx
0x1800ecb97  lea     r8, [rbp+var_20]
0x1800ecb9b  cmovnz  rax, rbx
0x1800ecb9f  lea     rdx, [rbp+Block]
0x1800ecba3  mov     [rbp+var_20], rax
0x1800ecba7  mov     rax, [rbp+arg_18]
0x1800ecbab  test    rax, rax
0x1800ecbae  cmovnz  rcx, rax
0x1800ecbb2  mov     [rbp+var_10], rcx
0x1800ecbb6  lea     rcx, [rbp+var_10]
0x1800ecbba  call    ??$SrNamedPipeClientErrorNoAccess@PEBGAEAHPEBG@SPTelemetry@@SAX$$QEAPEBGAEAH0@Z; SPTelemetry::SrNamedPipeClientErrorNoAccess<ushort const *,int &,ushort const *>(ushort const * &&,int &,ushort const * &&)
0x1800ecbbf  mov     rcx, [rbp+pSid]; pSid
0x1800ecbc3  test    rcx, rcx
0x1800ecbc6  jz      short loc_1800ECBCE
0x1800ecbc8  call    cs:__imp_FreeSid
0x1800ecbce  test    rsi, rsi
0x1800ecbd1  jz      short loc_1800ECBDC
0x1800ecbd3  mov     rcx, rsi; Block
0x1800ecbd6  call    cs:__imp_free
0x1800ecbdc  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ecbe0  test    rcx, rcx
0x1800ecbe3  jz      short loc_1800ECBEB
0x1800ecbe5  call    cs:__imp_CloseHandle
0x1800ecbeb  lea     rcx, [rbp+arg_10]; this
0x1800ecbef  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ecbf4  lea     rcx, [rbp+arg_18]; this
0x1800ecbf8  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ecbfd  mov     eax, edi
0x1800ecbff  add     rsp, 40h
0x1800ecc03  pop     r15
0x1800ecc05  pop     r14
0x1800ecc07  pop     r12
0x1800ecc09  pop     rdi
0x1800ecc0a  pop     rsi
0x1800ecc0b  pop     rbx
0x1800ecc0c  pop     rbp
0x1800ecc0d  retn
```
