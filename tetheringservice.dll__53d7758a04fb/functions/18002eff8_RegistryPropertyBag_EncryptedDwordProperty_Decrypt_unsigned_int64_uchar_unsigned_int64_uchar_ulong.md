# RegistryPropertyBag::EncryptedDwordProperty::_Decrypt(unsigned __int64,uchar *,unsigned __int64,uchar *,ulong *)

- ea: `0x18002eff8`
- end: `0x18002f13b`
- name: `?_Decrypt@EncryptedDwordProperty@RegistryPropertyBag@@AEAAJ_KPEAE01PEAK@Z`
- size: `323`
- prototype: `__int64 __fastcall(RegistryPropertyBag::EncryptedDwordProperty *this, __int64, unsigned __int8 *, __int64, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ec14`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18002eff8`
- `0x180031190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f0b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f0b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f0fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f0fa`
- `CRYPT32!CryptUnprotectData` at `0x18002f0aa`
- `CRYPT32!CryptUnprotectData` at `0x18002f0aa`

## pseudocode

```c
__int64 __fastcall RegistryPropertyBag::EncryptedDwordProperty::_Decrypt(
        RegistryPropertyBag::EncryptedDwordProperty *this,
        __int64 a2,
        unsigned __int8 *a3,
        __int64 a4,
        unsigned __int8 *a5,
        unsigned int *a6)
{
  unsigned int v9; // ebx
  signed int LastError; // eax
  BYTE *pbData; // rdx
  DATA_BLOB pOptionalEntropy; // [rsp+40h] [rbp-30h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-20h] BYREF
  DATA_BLOB pDataOut; // [rsp+60h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
  }
  v9 = 0;
  pDataIn = 0;
  pOptionalEntropy = 0;
  pDataOut = 0;
  if ( !a2 || !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 || !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  pDataIn.cbData = a2;
  pDataIn.pbData = a3;
  pOptionalEntropy.cbData = a4;
  pOptionalEntropy.pbData = a5;
  if ( CryptUnprotectData(&pDataIn, 0, &pOptionalEntropy, 0, 0, 1u, &pDataOut) )
    goto LABEL_15;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( (v9 & 0x80000000) == 0 )
  {
LABEL_15:
    pbData = pDataOut.pbData;
    if ( pDataOut.pbData )
    {
      *a6 = *pDataOut.pbData;
    }
    else
    {
      *a6 = 0;
      v9 = -2147467259;
    }
  }
  else
  {
    pbData = pDataOut.pbData;
  }
  if ( pbData )
    LocalFree(pbData);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18002eff8  push    rbp
0x18002effa  push    rbx
0x18002effb  push    rsi
0x18002effc  push    rdi
0x18002effd  push    r12
0x18002efff  push    r14
0x18002f001  push    r15
0x18002f003  mov     rbp, rsp
0x18002f006  sub     rsp, 70h
0x18002f00a  mov     r14, r9
0x18002f00d  mov     rsi, r8
0x18002f010  mov     r15, rdx
0x18002f013  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f01a  lea     r12, WPP_GLOBAL_Control
0x18002f021  cmp     rcx, r12
0x18002f024  jz      short loc_18002F041
0x18002f026  test    byte ptr [rcx+1Ch], 10h
0x18002f02a  jz      short loc_18002F041
0x18002f02c  mov     rcx, [rcx+10h]
0x18002f030  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x18002f037  mov     edx, 31h ; '1'
0x18002f03c  call    WPP_SF_
0x18002f041  xorps   xmm0, xmm0
0x18002f044  xor     ebx, ebx
0x18002f046  xorps   xmm1, xmm1
0x18002f049  movups  xmmword ptr [rbp+pDataIn.cbData], xmm0
0x18002f04d  movups  xmmword ptr [rbp+pOptionalEntropy.cbData], xmm1
0x18002f051  movups  xmmword ptr [rbp+var_10.cbData], xmm0
0x18002f055  test    r15, r15
0x18002f058  jz      short loc_18002F05F
0x18002f05a  test    rsi, rsi
0x18002f05d  jnz     short loc_18002F064
0x18002f05f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002f064  mov     rdi, [rbp+arg_20]
0x18002f068  test    r14, r14
0x18002f06b  jz      short loc_18002F072
0x18002f06d  test    rdi, rdi
0x18002f070  jnz     short loc_18002F077
0x18002f072  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002f077  lea     rax, [rbp+var_10]
0x18002f07b  mov     [rbp+pDataIn.cbData], r15d
0x18002f07f  mov     [rsp+70h+pDataOut], rax; pDataOut
0x18002f084  lea     r8, [rbp+pOptionalEntropy]; pOptionalEntropy
0x18002f088  mov     [rsp+70h+dwFlags], 1; dwFlags
0x18002f090  lea     rcx, [rbp+pDataIn]; pDataIn
0x18002f094  xor     r9d, r9d; pvReserved
0x18002f097  mov     [rsp+70h+pPromptStruct], rbx; pPromptStruct
0x18002f09c  xor     edx, edx; ppszDataDescr
0x18002f09e  mov     [rbp+pDataIn.pbData], rsi
0x18002f0a2  mov     [rbp+pOptionalEntropy.cbData], r14d
0x18002f0a6  mov     [rbp+pOptionalEntropy.pbData], rdi
0x18002f0aa  call    cs:__imp_CryptUnprotectData
0x18002f0b0  test    eax, eax
0x18002f0b2  jnz     short loc_18002F0D3
0x18002f0b4  call    cs:__imp_GetLastError
0x18002f0ba  mov     ebx, eax
0x18002f0bc  test    eax, eax
0x18002f0be  jle     short loc_18002F0C9
0x18002f0c0  movzx   ebx, ax
0x18002f0c3  or      ebx, 80070000h
0x18002f0c9  test    ebx, ebx
0x18002f0cb  jns     short loc_18002F0D3
0x18002f0cd  mov     rdx, [rbp+var_10.pbData]
0x18002f0d1  jmp     short loc_18002F0F2
0x18002f0d3  mov     rdx, [rbp+var_10.pbData]
0x18002f0d7  mov     rax, [rbp+arg_28]
0x18002f0db  test    rdx, rdx
0x18002f0de  jz      short loc_18002F0E7
0x18002f0e0  movzx   ecx, byte ptr [rdx]
0x18002f0e3  mov     [rax], ecx
0x18002f0e5  jmp     short loc_18002F0F2
0x18002f0e7  mov     dword ptr [rax], 0
0x18002f0ed  mov     ebx, 80004005h
0x18002f0f2  test    rdx, rdx
0x18002f0f5  jz      short loc_18002F100
0x18002f0f7  mov     rcx, rdx; hMem
0x18002f0fa  call    cs:__imp_LocalFree
0x18002f100  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f107  cmp     rcx, r12
0x18002f10a  jz      short loc_18002F12A
0x18002f10c  test    byte ptr [rcx+1Ch], 10h
0x18002f110  jz      short loc_18002F12A
0x18002f112  mov     rcx, [rcx+10h]
0x18002f116  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x18002f11d  mov     edx, 32h ; '2'
0x18002f122  mov     r9d, ebx
0x18002f125  call    WPP_SF_d
0x18002f12a  mov     eax, ebx
0x18002f12c  add     rsp, 70h
0x18002f130  pop     r15
0x18002f132  pop     r14
0x18002f134  pop     r12
0x18002f136  pop     rdi
0x18002f137  pop     rsi
0x18002f138  pop     rbx
0x18002f139  pop     rbp
0x18002f13a  retn
```
