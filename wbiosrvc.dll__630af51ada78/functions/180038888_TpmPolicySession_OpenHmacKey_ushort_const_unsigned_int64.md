# TpmPolicySession::OpenHmacKey(ushort const *,unsigned __int64 *)

- ea: `0x180038888`
- end: `0x180038990`
- name: `?OpenHmacKey@TpmPolicySession@@YAJPEBGPEA_K@Z`
- size: `264`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800387e4`

## callees

- `0x180038888`
- `0x1800430bc`
- `0x18005388c`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x18003890d`
- `ncrypt!NCryptOpenKey` at `0x18003890d`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800388b3`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800388b3`
- `ncrypt!NCryptFreeObject` at `0x1800388e4`
- `ncrypt!NCryptFreeObject` at `0x180038927`
- `ncrypt!NCryptFreeObject` at `0x180038936`
- `ncrypt!NCryptFreeObject` at `0x1800388e4`
- `ncrypt!NCryptFreeObject` at `0x180038927`
- `ncrypt!NCryptFreeObject` at `0x180038936`

## string_xrefs

- `0x1800388c3`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180038948`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c
__int64 __fastcall TpmPolicySession::OpenHmacKey(LPCWSTR pszKeyName, unsigned __int16 *a2, unsigned __int64 *a3)
{
  SECURITY_STATUS v5; // eax
  unsigned int v6; // ebx
  SECURITY_STATUS v7; // eax
  DWORD dwFlags; // [rsp+20h] [rbp-10h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp+30h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+68h] [rbp+38h] BYREF

  phProvider = 0;
  v5 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
      (const char *)(unsigned int)v5,
      dwFlags);
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return v6;
  }
  phKey = 0;
  v7 = NCryptOpenKey(phProvider, &phKey, pszKeyName, 0, 0);
  v6 = v7;
  if ( v7 != -2146893802 )
  {
    if ( v7 >= 0 )
    {
      v6 = 0;
      *(_QWORD *)a2 = phKey;
      phKey = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)v7,
        dwFlagsa);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return v6;
  }
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return 2148073494LL;
}

```

## disassembly

```asm
0x180038888  mov     [rsp-18h+arg_0], rbx
0x18003888d  push    rbp
0x18003888e  push    rsi
0x18003888f  push    rdi
0x180038890  mov     rbp, rsp
0x180038893  sub     rsp, 30h
0x180038897  mov     rdi, rdx
0x18003889a  mov     [rbp+phProvider], 0
0x1800388a2  mov     rsi, rcx
0x1800388a5  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x1800388ac  lea     rcx, [rbp+phProvider]; phProvider
0x1800388b0  xor     r8d, r8d; dwFlags
0x1800388b3  call    cs:__imp_NCryptOpenStorageProvider
0x1800388b9  mov     ebx, eax
0x1800388bb  test    eax, eax
0x1800388bd  jns     short loc_1800388EF
0x1800388bf  mov     rcx, [rbp+18h]; this
0x1800388c3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1800388ca  mov     r9d, eax; char *
0x1800388cd  mov     edx, 4Fh ; 'O'; void *
0x1800388d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800388d7  mov     rcx, [rbp+phProvider]; hObject
0x1800388db  test    rcx, rcx
0x1800388de  jz      loc_180038981
0x1800388e4  call    cs:__imp_NCryptFreeObject
0x1800388ea  jmp     loc_180038981
0x1800388ef  mov     rcx, [rbp+phProvider]; hProvider
0x1800388f3  lea     rdx, [rbp+phKey]; phKey
0x1800388f7  xor     r9d, r9d; dwLegacyKeySpec
0x1800388fa  mov     [rbp+phKey], 0
0x180038902  mov     r8, rsi; pszKeyName
0x180038905  mov     [rsp+30h+dwFlags], 0; int
0x18003890d  call    cs:__imp_NCryptOpenKey
0x180038913  mov     esi, 80090016h
0x180038918  mov     ebx, eax
0x18003891a  cmp     eax, esi
0x18003891c  jnz     short loc_180038940
0x18003891e  mov     rcx, [rbp+phKey]; hObject
0x180038922  test    rcx, rcx
0x180038925  jz      short loc_18003892D
0x180038927  call    cs:__imp_NCryptFreeObject
0x18003892d  mov     rcx, [rbp+phProvider]; hObject
0x180038931  test    rcx, rcx
0x180038934  jz      short loc_18003893C
0x180038936  call    cs:__imp_NCryptFreeObject
0x18003893c  mov     eax, esi
0x18003893e  jmp     short loc_180038983
0x180038940  test    eax, eax
0x180038942  jns     short loc_18003895E
0x180038944  mov     rcx, [rbp+18h]; this
0x180038948  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x18003894f  mov     r9d, eax; char *
0x180038952  mov     edx, 5Bh ; '['; void *
0x180038957  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003895c  jmp     short loc_18003896F
0x18003895e  mov     rax, [rbp+phKey]
0x180038962  xor     ebx, ebx
0x180038964  mov     [rdi], rax
0x180038967  mov     [rbp+phKey], 0
0x18003896f  lea     rcx, [rbp+phKey]
0x180038973  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180038978  lea     rcx, [rbp+phProvider]
0x18003897c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180038981  mov     eax, ebx
0x180038983  mov     rbx, [rsp+30h+arg_0]
0x180038988  add     rsp, 30h
0x18003898c  pop     rdi
0x18003898d  pop     rsi
0x18003898e  pop     rbp
0x18003898f  retn
```
