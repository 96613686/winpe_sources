# CCryptoApiHelperT<CMSRSAAESCryptoApiHelper>::CreateRandomContainer(int,int)

- ea: `0x18000f1c0`
- end: `0x18000f35e`
- name: `?CreateRandomContainer@?$CCryptoApiHelperT@VCMSRSAAESCryptoApiHelper@@@@QEAAJHH@Z`
- size: `414`
- prototype: `__int64 __fastcall(HCRYPTPROV *phProv)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800131ec`
- `0x18001428c`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000ea20`
- `0x18000f1c0`
- `0x18001fd60`
- `0x180027d84`
- `0x180028640`
- `0x18007ed40`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000f1f6`
- `RPCRT4!UuidCreate` at `0x18000f1f6`
- `RPCRT4!RpcStringFreeW` at `0x18000f341`
- `RPCRT4!RpcStringFreeW` at `0x18000f341`
- `RPCRT4!UuidToStringW` at `0x18000f219`
- `RPCRT4!UuidToStringW` at `0x18000f219`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18000f27b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18000f27b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f314`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f314`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f323`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f285`

## pseudocode

```c
__int64 __fastcall CCryptoApiHelperT<CMSRSAAESCryptoApiHelper>::CreateRandomContainer(HCRYPTPROV *phProv)
{
  WCHAR *v2; // rbx
  __int64 v3; // rcx
  unsigned int v4; // edi
  int v5; // eax
  signed int LastError; // eax
  int StringCch; // eax
  HANDLE ProcessHeap; // rax
  LPCWSTR szContainer; // [rsp+30h] [rbp-38h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-28h] BYREF

  StringUuid = 0;
  v2 = 0;
  Uuid = 0;
  szContainer = 0;
  if ( UuidCreate(&Uuid) || UuidToStringW(&Uuid, &StringUuid) )
  {
    v3 = 2147549183LL;
    v4 = -2147418113;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
    goto LABEL_21;
  }
  v5 = STRAPI_Format((unsigned __int16 **)&szContainer, L"RC{%s}", StringUuid);
  v4 = v5;
  if ( v5 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v5);
    v2 = (WCHAR *)szContainer;
    goto LABEL_21;
  }
  v2 = (WCHAR *)szContainer;
  CCryptoApiHelperT<CMSRSAAESCryptoApiHelper>::Reset(phProv);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !CryptAcquireContextW(phProv, v2, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0x28u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
LABEL_17:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_18;
  }
  v4 = 0;
  if ( v2 )
  {
    LODWORD(szContainer) = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v2, &szContainer);
    v4 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v2),
          v4 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
    if ( (v4 & 0x80000000) != 0 )
      goto LABEL_17;
  }
LABEL_18:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
  {
    v3 = v4;
    goto LABEL_3;
  }
  *((_DWORD *)phProv + 4) = 1;
LABEL_21:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( StringUuid )
  {
    szContainer = StringUuid;
    RpcStringFreeW((RPC_WSTR *)&szContainer);
  }
  return v4;
}

```

## disassembly

```asm
0x18000f1c0  push    rbp
0x18000f1c2  push    rbx
0x18000f1c3  push    rsi
0x18000f1c4  push    rdi
0x18000f1c5  mov     rbp, rsp
0x18000f1c8  sub     rsp, 68h
0x18000f1cc  mov     rax, cs:__security_cookie
0x18000f1d3  xor     rax, rsp
0x18000f1d6  mov     [rbp+var_18], rax
0x18000f1da  mov     rsi, rcx
0x18000f1dd  mov     [rbp+StringUuid], 0
0x18000f1e5  xorps   xmm0, xmm0
0x18000f1e8  lea     rcx, [rbp+Uuid]; Uuid
0x18000f1ec  xor     ebx, ebx
0x18000f1ee  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18000f1f2  mov     [rbp+szContainer], rbx
0x18000f1f6  call    cs:__imp_UuidCreate
0x18000f1fc  test    eax, eax
0x18000f1fe  jz      short loc_18000F211
0x18000f200  mov     ecx, 8000FFFFh
0x18000f205  mov     edi, ecx
0x18000f207  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f20c  jmp     loc_18000F308
0x18000f211  lea     rdx, [rbp+StringUuid]; StringUuid
0x18000f215  lea     rcx, [rbp+Uuid]; Uuid
0x18000f219  call    cs:__imp_UuidToStringW
0x18000f21f  test    eax, eax
0x18000f221  jnz     short loc_18000F200
0x18000f223  mov     r8, [rbp+StringUuid]
0x18000f227  lea     rdx, aRcS; "RC{%s}"
0x18000f22e  lea     rcx, [rbp+szContainer]; unsigned __int16 **
0x18000f232  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x18000f237  mov     edi, eax
0x18000f239  test    eax, eax
0x18000f23b  jns     short loc_18000F24D
0x18000f23d  mov     ecx, eax
0x18000f23f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f244  mov     rbx, [rbp+szContainer]
0x18000f248  jmp     loc_18000F308
0x18000f24d  mov     rbx, [rbp+szContainer]
0x18000f251  mov     rcx, rsi
0x18000f254  call    ?Reset@?$CCryptoApiHelperT@VCMSRSAAESCryptoApiHelper@@@@AEAAJXZ; CCryptoApiHelperT<CMSRSAAESCryptoApiHelper>::Reset(void)
0x18000f259  xor     ecx, ecx
0x18000f25b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f260  mov     r9d, 18h; dwProvType
0x18000f266  mov     [rsp+68h+dwFlags], 28h ; '('; dwFlags
0x18000f26e  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18000f275  mov     rdx, rbx; szContainer
0x18000f278  mov     rcx, rsi; phProv
0x18000f27b  call    cs:__imp_CryptAcquireContextW
0x18000f281  test    eax, eax
0x18000f283  jnz     short loc_18000F2A5
0x18000f285  call    cs:__imp_GetLastError
0x18000f28b  mov     edi, eax
0x18000f28d  test    eax, eax
0x18000f28f  jnz     short loc_18000F298
0x18000f291  mov     edi, 80004005h
0x18000f296  jmp     short loc_18000F2E8
0x18000f298  jle     short loc_18000F2E8
0x18000f29a  movzx   edi, ax
0x18000f29d  or      edi, 80070000h
0x18000f2a3  jmp     short loc_18000F2E8
0x18000f2a5  xor     edi, edi
0x18000f2a7  test    rbx, rbx
0x18000f2aa  jz      short loc_18000F2EF
0x18000f2ac  lea     rdx, [rbp+szContainer]
0x18000f2b0  mov     dword ptr [rbp+szContainer], edi
0x18000f2b3  mov     rcx, rbx
0x18000f2b6  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18000f2bb  mov     edi, eax
0x18000f2bd  test    eax, eax
0x18000f2bf  js      short loc_18000F2D6
0x18000f2c1  mov     edx, dword ptr [rbp+szContainer]
0x18000f2c4  lea     r8, [rsi+8]
0x18000f2c8  mov     rcx, rbx; Src
0x18000f2cb  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18000f2d0  mov     edi, eax
0x18000f2d2  test    eax, eax
0x18000f2d4  jns     short loc_18000F2DD
0x18000f2d6  mov     ecx, eax
0x18000f2d8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f2dd  mov     ecx, edi
0x18000f2df  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f2e4  test    edi, edi
0x18000f2e6  jns     short loc_18000F2EF
0x18000f2e8  mov     ecx, edi
0x18000f2ea  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f2ef  mov     ecx, edi
0x18000f2f1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f2f6  test    edi, edi
0x18000f2f8  jns     short loc_18000F301
0x18000f2fa  mov     ecx, edi
0x18000f2fc  jmp     loc_18000F207
0x18000f301  mov     dword ptr [rsi+10h], 1
0x18000f308  mov     ecx, edi
0x18000f30a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f30f  test    rbx, rbx
0x18000f312  jz      short loc_18000F330
0x18000f314  call    cs:__imp_GetProcessHeap
0x18000f31a  lea     r8, [rbx-4]; lpMem
0x18000f31e  xor     edx, edx; dwFlags
0x18000f320  mov     rcx, rax; hHeap
0x18000f323  call    cs:__imp_HeapFree
0x18000f329  xor     ecx, ecx
0x18000f32b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f330  mov     rax, [rbp+StringUuid]
0x18000f334  test    rax, rax
0x18000f337  jz      short loc_18000F347
0x18000f339  lea     rcx, [rbp+szContainer]; String
0x18000f33d  mov     [rbp+szContainer], rax
0x18000f341  call    cs:__imp_RpcStringFreeW
0x18000f347  mov     eax, edi
0x18000f349  mov     rcx, [rbp+var_18]
0x18000f34d  xor     rcx, rsp; StackCookie
0x18000f350  call    __security_check_cookie
0x18000f355  add     rsp, 68h
0x18000f359  pop     rdi
0x18000f35a  pop     rsi
0x18000f35b  pop     rbx
0x18000f35c  pop     rbp
0x18000f35d  retn
```
