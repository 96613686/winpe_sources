# EncryptionHelper::GetSha256Hash(uchar const *,ulong,uchar *,ulong)

- ea: `0x1800283a8`
- end: `0x180028500`
- name: `?GetSha256Hash@EncryptionHelper@@SAJPEBEKPEAEK@Z`
- size: `344`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, BYTE *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028508`
- `0x18003eb1c`

## callees

- `0x18000e5ac`
- `0x18001e06c`
- `0x1800260ec`
- `0x18002610c`
- `0x1800283a8`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800284ad`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800284ad`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002844f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002844f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180028486`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180028486`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002840b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002840b`

## pseudocode

```c
__int64 __fastcall EncryptionHelper::GetSha256Hash(BYTE *pbData, DWORD dwDataLen, BYTE *a3, DWORD a4)
{
  unsigned int LastError; // ebx
  const char *v8; // r9
  const char *v9; // r9
  __int64 v10; // rdx
  int dwFlags; // [rsp+20h] [rbp-28h]
  int dwFlagsa; // [rsp+20h] [rbp-28h]
  HCRYPTHASH phHash; // [rsp+30h] [rbp-18h] BYREF
  HCRYPTPROV phProv[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  DWORD pdwDataLen; // [rsp+88h] [rbp+40h] BYREF

  pdwDataLen = a4;
  if ( a4 == 32 )
  {
    phProv[0] = 0;
    if ( !CryptAcquireContextW(phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000040) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2D,
                    (unsigned int)"onecore\\base\\flighting\\OneSettings\\libs\\inc\\EncryptionHelper.h",
                    v8);
LABEL_16:
      __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(phProv);
      return LastError;
    }
    phHash = 0;
    if ( CryptCreateHash(phProv[0], 0x800Cu, 0, 0, &phHash) )
    {
      if ( CryptHashData(phHash, pbData, dwDataLen, 0) )
      {
        if ( CryptGetHashParam(phHash, 2u, a3, &pdwDataLen, 0) )
        {
          if ( pdwDataLen == 32 )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phHash);
            LastError = 0;
            goto LABEL_16;
          }
          LastError = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x38,
            (unsigned int)"onecore\\base\\flighting\\OneSettings\\libs\\inc\\EncryptionHelper.h",
            (const char *)0x8000FFFFLL,
            dwFlagsa);
          goto LABEL_8;
        }
        v10 = 55;
      }
      else
      {
        v10 = 52;
      }
    }
    else
    {
      v10 = 49;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecore\\base\\flighting\\OneSettings\\libs\\inc\\EncryptionHelper.h",
                  v9);
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phHash);
    goto LABEL_16;
  }
  LastError = -2147024774;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x29,
    (unsigned int)"onecore\\base\\flighting\\OneSettings\\libs\\inc\\EncryptionHelper.h",
    (const char *)0x8007007ALL,
    dwFlags);
  return LastError;
}

```

## disassembly

```asm
0x1800283a8  mov     [rsp-20h+pdwDataLen], r9d
0x1800283ad  push    rbp
0x1800283ae  push    rbx
0x1800283af  push    rsi
0x1800283b0  push    rdi
0x1800283b1  mov     rbp, rsp
0x1800283b4  sub     rsp, 48h
0x1800283b8  mov     rbx, r8
0x1800283bb  mov     edi, edx
0x1800283bd  mov     rsi, rcx
0x1800283c0  cmp     r9d, 20h ; ' '
0x1800283c4  jz      short loc_1800283E8
0x1800283c6  mov     rcx, [rbp+20h]; this
0x1800283ca  lea     r8, aOnecoreBaseFli_33; "onecore\\base\\flighting\\OneSettings\\"...
0x1800283d1  mov     ebx, 8007007Ah
0x1800283d6  mov     edx, 29h ; ')'; void *
0x1800283db  mov     r9d, ebx; char *
0x1800283de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800283e3  jmp     loc_1800284F5
0x1800283e8  mov     r9d, 18h; dwProvType
0x1800283ee  mov     [rbp+phProv], 0
0x1800283f6  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x1800283fd  mov     [rsp+48h+dwFlags], 0F0000040h; dwFlags
0x180028405  xor     edx, edx; szContainer
0x180028407  lea     rcx, [rbp+phProv]; phProv
0x18002840b  call    cs:__imp_CryptAcquireContextW
0x180028411  test    eax, eax
0x180028413  jnz     short loc_18002842F
0x180028415  mov     rcx, [rbp+20h]; this
0x180028419  lea     r8, aOnecoreBaseFli_33; "onecore\\base\\flighting\\OneSettings\\"...
0x180028420  lea     edx, [rax+2Dh]; void *
0x180028423  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028428  mov     ebx, eax
0x18002842a  jmp     loc_1800284EC
0x18002842f  mov     rcx, [rbp+phProv]; hProv
0x180028433  lea     rax, [rbp+phHash]
0x180028437  xor     r9d, r9d; dwFlags
0x18002843a  mov     qword ptr [rsp+48h+dwFlags], rax; phHash
0x18002843f  xor     r8d, r8d; hKey
0x180028442  mov     [rbp+phHash], 0
0x18002844a  mov     edx, 800Ch; Algid
0x18002844f  call    cs:__imp_CryptCreateHash
0x180028455  test    eax, eax
0x180028457  jnz     short loc_180028479
0x180028459  lea     edx, [rax+31h]; void *
0x18002845c  mov     rcx, [rbp+20h]; this
0x180028460  lea     r8, aOnecoreBaseFli_33; "onecore\\base\\flighting\\OneSettings\\"...
0x180028467  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002846c  mov     ebx, eax
0x18002846e  lea     rcx, [rbp+phHash]
0x180028472  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyHash@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180028477  jmp     short loc_1800284EC
0x180028479  mov     rcx, [rbp+phHash]; hHash
0x18002847d  xor     r9d, r9d; dwFlags
0x180028480  mov     r8d, edi; dwDataLen
0x180028483  mov     rdx, rsi; pbData
0x180028486  call    cs:__imp_CryptHashData
0x18002848c  test    eax, eax
0x18002848e  jnz     short loc_180028495
0x180028490  lea     edx, [rax+34h]
0x180028493  jmp     short loc_18002845C
0x180028495  mov     rcx, [rbp+phHash]; hHash
0x180028499  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18002849d  mov     r8, rbx; pbData
0x1800284a0  mov     [rsp+48h+dwFlags], 0; int
0x1800284a8  mov     edx, 2; dwParam
0x1800284ad  call    cs:__imp_CryptGetHashParam
0x1800284b3  test    eax, eax
0x1800284b5  jnz     short loc_1800284BC
0x1800284b7  lea     edx, [rax+37h]
0x1800284ba  jmp     short loc_18002845C
0x1800284bc  cmp     [rbp+pdwDataLen], 20h ; ' '
0x1800284c0  jz      short loc_1800284E1
0x1800284c2  mov     rcx, [rbp+20h]; this
0x1800284c6  lea     r8, aOnecoreBaseFli_33; "onecore\\base\\flighting\\OneSettings\\"...
0x1800284cd  mov     ebx, 8000FFFFh
0x1800284d2  mov     edx, 38h ; '8'; void *
0x1800284d7  mov     r9d, ebx; char *
0x1800284da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800284df  jmp     short loc_18002846E
0x1800284e1  lea     rcx, [rbp+phHash]
0x1800284e5  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyHash@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800284ea  xor     ebx, ebx
0x1800284ec  lea     rcx, [rbp+phProv]
0x1800284f0  call    ??1?$unique_storage@U?$resource_policy@_KP6AX_K@_E$1?CryptReleaseContextNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800284f5  mov     eax, ebx
0x1800284f7  add     rsp, 48h
0x1800284fb  pop     rdi
0x1800284fc  pop     rsi
0x1800284fd  pop     rbx
0x1800284fe  pop     rbp
0x1800284ff  retn
```
