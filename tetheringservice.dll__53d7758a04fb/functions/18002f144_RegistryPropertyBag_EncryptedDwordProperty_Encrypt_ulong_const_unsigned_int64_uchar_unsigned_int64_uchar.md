# RegistryPropertyBag::EncryptedDwordProperty::_Encrypt(ulong const &,unsigned __int64,uchar *,unsigned __int64 *,uchar * *)

- ea: `0x18002f144`
- end: `0x18002f271`
- name: `?_Encrypt@EncryptedDwordProperty@RegistryPropertyBag@@AEAAJAEBK_KPEAEPEA_KPEAPEAE@Z`
- size: `301`
- prototype: `__int64 __fastcall(RegistryPropertyBag::EncryptedDwordProperty *this, BYTE *, DWORD, unsigned __int8 *, unsigned __int64 *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002ee44`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18002f144`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f212`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f212`
- `CRYPT32!CryptProtectData` at `0x18002f1e6`
- `CRYPT32!CryptProtectData` at `0x18002f1e6`

## pseudocode

```c
__int64 __fastcall RegistryPropertyBag::EncryptedDwordProperty::_Encrypt(
        RegistryPropertyBag::EncryptedDwordProperty *this,
        BYTE *a2,
        DWORD a3,
        unsigned __int8 *a4,
        unsigned __int64 *a5,
        unsigned __int8 **a6)
{
  unsigned int v9; // ebx
  signed int LastError; // eax
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-30h] BYREF
  DATA_BLOB pOptionalEntropy; // [rsp+50h] [rbp-20h] BYREF
  DATA_BLOB pDataIn; // [rsp+60h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
  }
  v9 = 0;
  *a5 = 0;
  *a6 = 0;
  *(_QWORD *)&pDataIn.cbData = 4;
  *(&pOptionalEntropy.cbData + 1) = 0;
  pDataOut = 0;
  pDataIn.pbData = a2;
  pOptionalEntropy.cbData = a3;
  pOptionalEntropy.pbData = a4;
  if ( CryptProtectData(&pDataIn, 0, &pOptionalEntropy, 0, 0, 5u, &pDataOut) )
    goto LABEL_10;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( (v9 & 0x80000000) == 0 )
  {
LABEL_10:
    *a5 = pDataOut.cbData;
    *a6 = pDataOut.pbData;
    pDataOut.pbData = 0;
  }
  else if ( pDataOut.pbData )
  {
    LocalFree(pDataOut.pbData);
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18002f144  push    rbp
0x18002f146  push    rbx
0x18002f147  push    rsi
0x18002f148  push    rdi
0x18002f149  push    r12
0x18002f14b  push    r14
0x18002f14d  push    r15
0x18002f14f  mov     rbp, rsp
0x18002f152  sub     rsp, 70h
0x18002f156  mov     r14, r9
0x18002f159  mov     r15, r8
0x18002f15c  mov     r12, rdx
0x18002f15f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f166  lea     rax, WPP_GLOBAL_Control
0x18002f16d  cmp     rcx, rax
0x18002f170  jz      short loc_18002F18D
0x18002f172  test    byte ptr [rcx+1Ch], 10h
0x18002f176  jz      short loc_18002F18D
0x18002f178  mov     rcx, [rcx+10h]
0x18002f17c  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x18002f183  mov     edx, 2Fh ; '/'
0x18002f188  call    WPP_SF_
0x18002f18d  mov     rdi, [rbp+arg_20]
0x18002f191  lea     rax, [rbp+var_30]
0x18002f195  mov     rsi, [rbp+arg_28]
0x18002f199  lea     r8, [rbp+pOptionalEntropy]; pOptionalEntropy
0x18002f19d  mov     [rsp+70h+pDataOut], rax; pDataOut
0x18002f1a2  lea     rcx, [rbp+pDataIn]; pDataIn
0x18002f1a6  xor     ebx, ebx
0x18002f1a8  mov     [rsp+70h+dwFlags], 5; dwFlags
0x18002f1b0  xorps   xmm0, xmm0
0x18002f1b3  mov     qword ptr [rdi], 0
0x18002f1ba  xor     r9d, r9d; pvReserved
0x18002f1bd  mov     qword ptr [rsi], 0
0x18002f1c4  xor     edx, edx; szDataDescr
0x18002f1c6  mov     qword ptr [rbp+pDataIn.cbData], 4
0x18002f1ce  mov     dword ptr [rbp+pOptionalEntropy+4], ebx
0x18002f1d1  movups  xmmword ptr [rbp+var_30.cbData], xmm0
0x18002f1d5  mov     [rbp+pDataIn.pbData], r12
0x18002f1d9  mov     [rbp+pOptionalEntropy.cbData], r15d
0x18002f1dd  mov     [rbp+pOptionalEntropy.pbData], r14
0x18002f1e1  mov     [rsp+70h+pPromptStruct], rbx; pPromptStruct
0x18002f1e6  call    cs:__imp_CryptProtectData
0x18002f1ec  test    eax, eax
0x18002f1ee  jnz     short loc_18002F21A
0x18002f1f0  call    cs:__imp_GetLastError
0x18002f1f6  mov     ebx, eax
0x18002f1f8  test    eax, eax
0x18002f1fa  jle     short loc_18002F205
0x18002f1fc  movzx   ebx, ax
0x18002f1ff  or      ebx, 80070000h
0x18002f205  test    ebx, ebx
0x18002f207  jns     short loc_18002F21A
0x18002f209  mov     rcx, [rbp+var_30.pbData]; hMem
0x18002f20d  test    rcx, rcx
0x18002f210  jz      short loc_18002F22F
0x18002f212  call    cs:__imp_LocalFree
0x18002f218  jmp     short loc_18002F22F
0x18002f21a  mov     eax, [rbp+var_30.cbData]
0x18002f21d  mov     [rdi], rax
0x18002f220  mov     rax, [rbp+var_30.pbData]
0x18002f224  mov     [rsi], rax
0x18002f227  mov     [rbp+var_30.pbData], 0
0x18002f22f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f236  lea     rax, WPP_GLOBAL_Control
0x18002f23d  cmp     rcx, rax
0x18002f240  jz      short loc_18002F260
0x18002f242  test    byte ptr [rcx+1Ch], 10h
0x18002f246  jz      short loc_18002F260
0x18002f248  mov     rcx, [rcx+10h]
0x18002f24c  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x18002f253  mov     edx, 30h ; '0'
0x18002f258  mov     r9d, ebx
0x18002f25b  call    WPP_SF_d
0x18002f260  mov     eax, ebx
0x18002f262  add     rsp, 70h
0x18002f266  pop     r15
0x18002f268  pop     r14
0x18002f26a  pop     r12
0x18002f26c  pop     rdi
0x18002f26d  pop     rsi
0x18002f26e  pop     rbx
0x18002f26f  pop     rbp
0x18002f270  retn
```
