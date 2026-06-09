# TpmPolicySession::GenerateAuthorizationHmac(uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar *,ulong,ulong *)

- ea: `0x1800069b0`
- end: `0x180006db3`
- name: `?GenerateAuthorizationHmac@TpmPolicySession@@YAJPEBEK0K0KPEAEKPEAK@Z`
- size: `1027`
- prototype: `__int64 __fastcall(TpmPolicySession *__hidden this, ULONG cbSecret, PUCHAR pbInput, ULONG cbInput, PUCHAR, ULONG, PUCHAR, ULONG cbOutput, UCHAR, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006e14`
- `0x1800538d4`

## callees

- `0x1800058ec`
- `0x1800069b0`
- `0x18001423c`
- `0x1800530c4`
- `0x18005388c`
- `0x1800538b0`
- `0x1800602dc`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180006a84`
- `bcrypt!BCryptDestroyHash` at `0x180006b4a`
- `bcrypt!BCryptDestroyHash` at `0x180006bb8`
- `bcrypt!BCryptDestroyHash` at `0x180006c44`
- `bcrypt!BCryptDestroyHash` at `0x180006caf`
- `bcrypt!BCryptDestroyHash` at `0x180006a84`
- `bcrypt!BCryptDestroyHash` at `0x180006b4a`
- `bcrypt!BCryptDestroyHash` at `0x180006bb8`
- `bcrypt!BCryptDestroyHash` at `0x180006c44`
- `bcrypt!BCryptDestroyHash` at `0x180006caf`
- `bcrypt!BCryptFinishHash` at `0x180006bf7`
- `bcrypt!BCryptFinishHash` at `0x180006d43`
- `bcrypt!BCryptFinishHash` at `0x180006bf7`
- `bcrypt!BCryptFinishHash` at `0x180006d43`
- `bcrypt!BCryptHashData` at `0x180006ab6`
- `bcrypt!BCryptHashData` at `0x180006b18`
- `bcrypt!BCryptHashData` at `0x180006b86`
- `bcrypt!BCryptHashData` at `0x180006ce2`
- `bcrypt!BCryptHashData` at `0x180006ab6`
- `bcrypt!BCryptHashData` at `0x180006b18`
- `bcrypt!BCryptHashData` at `0x180006b86`
- `bcrypt!BCryptHashData` at `0x180006ce2`
- `bcrypt!BCryptCreateHash` at `0x180006a52`
- `bcrypt!BCryptCreateHash` at `0x180006c7a`
- `bcrypt!BCryptCreateHash` at `0x180006a52`
- `bcrypt!BCryptCreateHash` at `0x180006c7a`

## string_xrefs

- `0x1800069ed`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180006a67`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180006acb`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180006b2d`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180006b9b`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180006c0c`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180006c8f`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180006cf7`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x180006d58`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c
__int64 __fastcall TpmPolicySession::GenerateAuthorizationHmac(
        UCHAR *this,
        ULONG cbSecret,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR a5,
        ULONG cbInputa,
        PUCHAR a7,
        ULONG cbOutput,
        _DWORD *pbInputa)
{
  __int64 result; // rax
  NTSTATUS v14; // eax
  unsigned int v15; // ebx
  const char *v16; // r9
  NTSTATUS v17; // eax
  unsigned int v18; // ebx
  NTSTATUS v19; // eax
  unsigned int v20; // ebx
  NTSTATUS v21; // eax
  unsigned int v22; // ebx
  UCHAR *v23; // rbx
  ULONG v24; // edi
  NTSTATUS v25; // eax
  unsigned int v26; // ebx
  NTSTATUS Hash; // eax
  unsigned int v28; // edi
  NTSTATUS v29; // eax
  unsigned int v30; // ebx
  NTSTATUS v31; // eax
  unsigned int v32; // ebx
  int pbSecret; // [rsp+20h] [rbp-68h]
  int pbSecreta; // [rsp+20h] [rbp-68h]
  int pbSecretb; // [rsp+20h] [rbp-68h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-48h] BYREF
  PUCHAR pbOutput[2]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v38; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *pbInputa = 32;
  if ( cbOutput >= 0x20 )
  {
    *(_OWORD *)pbOutput = 0;
    v38 = 0;
    try
    {
      std::vector<unsigned char>::_Construct_n<>(pbOutput, 32);
      phHash = 0;
      v14 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
      if ( v14 >= 0 )
      {
        v17 = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( v17 >= 0 )
        {
          LODWORD(pbInputa) = -486539265;
          v19 = BCryptHashData(phHash, (PUCHAR)&pbInputa, 4u, 0);
          if ( v19 >= 0 )
          {
            v21 = BCryptHashData(phHash, a5, cbInputa, 0);
            if ( v21 >= 0 )
            {
              v23 = pbOutput[0];
              v24 = LODWORD(pbOutput[1]) - LODWORD(pbOutput[0]);
              v25 = BCryptFinishHash(phHash, pbOutput[0], LODWORD(pbOutput[1]) - LODWORD(pbOutput[0]), 0);
              if ( v25 >= 0 )
              {
                if ( phHash )
                  BCryptDestroyHash(phHash);
                pbInputa = 0;
                Hash = BCryptCreateHash(
                         (BCRYPT_ALG_HANDLE)0xB1,
                         (BCRYPT_HASH_HANDLE *)&pbInputa,
                         0,
                         0,
                         this,
                         cbSecret,
                         0);
                if ( Hash >= 0 )
                {
                  v29 = BCryptHashData(pbInputa, v23, v24, 0);
                  if ( v29 >= 0 )
                  {
                    v31 = BCryptFinishHash(pbInputa, a7, cbOutput, 0);
                    if ( v31 >= 0 )
                    {
                      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInputa);
                      std::vector<unsigned char>::_Tidy(pbOutput);
                      result = 0;
                    }
                    else
                    {
                      v32 = wil::details::in1diag3::Return_NtStatus(
                              retaddr,
                              (void *)0x1FE,
                              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                              (const char *)(unsigned int)v31,
                              pbSecretb);
                      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInputa);
                      std::vector<unsigned char>::_Tidy(pbOutput);
                      result = v32;
                    }
                  }
                  else
                  {
                    v30 = wil::details::in1diag3::Return_NtStatus(
                            retaddr,
                            (void *)0x1F7,
                            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                            (const char *)(unsigned int)v29,
                            pbSecretb);
                    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInputa);
                    std::vector<unsigned char>::_Tidy(pbOutput);
                    result = v30;
                  }
                }
                else
                {
                  v28 = wil::details::in1diag3::Return_NtStatus(
                          retaddr,
                          (void *)0x1F0,
                          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                          (const char *)(unsigned int)Hash,
                          pbSecretb);
                  if ( pbInputa )
                    BCryptDestroyHash(pbInputa);
                  if ( v23 )
                    std::_Deallocate<16>(v23, v38 - (_QWORD)v23);
                  result = v28;
                }
              }
              else
              {
                v26 = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x1E2,
                        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                        (const char *)(unsigned int)v25,
                        pbSecreta);
                wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
                std::vector<unsigned char>::_Tidy(pbOutput);
                result = v26;
              }
            }
            else
            {
              v22 = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x1DB,
                      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                      (const char *)(unsigned int)v21,
                      pbSecreta);
              if ( phHash )
                BCryptDestroyHash(phHash);
              if ( pbOutput[0] )
                std::_Deallocate<16>(pbOutput[0], v38 - (unsigned __int64)pbOutput[0]);
              result = v22;
            }
          }
          else
          {
            v20 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x1D4,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                    (const char *)(unsigned int)v19,
                    pbSecreta);
            if ( phHash )
              BCryptDestroyHash(phHash);
            if ( pbOutput[0] )
              std::_Deallocate<16>(pbOutput[0], v38 - (unsigned __int64)pbOutput[0]);
            result = v20;
          }
        }
        else
        {
          v18 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x1C7,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                  (const char *)(unsigned int)v17,
                  pbSecreta);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
          std::vector<unsigned char>::_Tidy(pbOutput);
          result = v18;
        }
      }
      else
      {
        v15 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x1C0,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                (const char *)(unsigned int)v14,
                pbSecreta);
        if ( phHash )
          BCryptDestroyHash(phHash);
        if ( pbOutput[0] )
          std::_Deallocate<16>(pbOutput[0], v38 - (unsigned __int64)pbOutput[0]);
        result = v15;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x201,
                             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                             v16);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
      (const char *)0x8007007ALL,
      pbSecret);
    return 2147942522LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800069b0  push    rbx
0x1800069b2  push    rsi
0x1800069b3  push    rdi
0x1800069b4  push    r14
0x1800069b6  sub     rsp, 68h
0x1800069ba  mov     ebx, r9d
0x1800069bd  mov     rdi, r8
0x1800069c0  mov     esi, edx
0x1800069c2  mov     r14, rcx
0x1800069c5  mov     edx, 20h ; ' '
0x1800069ca  mov     rax, [rsp+88h+pbInput]
0x1800069d2  mov     [rax], edx
0x1800069d4  cmp     [rsp+88h+cbOutput], edx
0x1800069db  jnb     short loc_180006A05
0x1800069dd  mov     rcx, [rsp+88h]; this
0x1800069e5  mov     ebx, 8007007Ah
0x1800069ea  mov     r9d, ebx; char *
0x1800069ed  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1800069f4  mov     edx, 1B2h; void *
0x1800069f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069fe  mov     eax, ebx
0x180006a00  jmp     loc_180006DA9
0x180006a05  xorps   xmm0, xmm0
0x180006a08  movdqu  xmmword ptr [rsp+88h+pbOutput], xmm0
0x180006a0e  mov     [rsp+88h+var_30], 0
0x180006a17  lea     rcx, [rsp+88h+pbOutput]
0x180006a1c  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x180006a21  mov     [rsp+88h+phHash], 0
0x180006a2a  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180006a32  mov     [rsp+88h+cbSecret], 0; cbSecret
0x180006a3a  mov     [rsp+88h+pbSecret], 0; int
0x180006a43  xor     r9d, r9d; cbHashObject
0x180006a46  xor     r8d, r8d; pbHashObject
0x180006a49  lea     rdx, [rsp+88h+phHash]; phHash
0x180006a4e  lea     ecx, [r9+41h]; hAlgorithm
0x180006a52  call    cs:__imp_BCryptCreateHash
0x180006a58  test    eax, eax
0x180006a5a  jns     short loc_180006AA8
0x180006a5c  mov     rcx, [rsp+88h]; this
0x180006a64  mov     r9d, eax; char *
0x180006a67  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180006a6e  mov     edx, 1C0h; void *
0x180006a73  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006a78  mov     ebx, eax
0x180006a7a  mov     rcx, [rsp+88h+phHash]; hHash
0x180006a7f  test    rcx, rcx
0x180006a82  jz      short loc_180006A8A
0x180006a84  call    cs:__imp_BCryptDestroyHash
0x180006a8a  mov     rcx, [rsp+88h+pbOutput]
0x180006a8f  test    rcx, rcx
0x180006a92  jz      short loc_180006AA1
0x180006a94  mov     rdx, [rsp+88h+var_30]
0x180006a99  sub     rdx, rcx
0x180006a9c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006aa1  mov     eax, ebx
0x180006aa3  jmp     loc_180006DA9
0x180006aa8  xor     r9d, r9d; dwFlags
0x180006aab  mov     r8d, ebx; cbInput
0x180006aae  mov     rdx, rdi; pbInput
0x180006ab1  mov     rcx, [rsp+88h+phHash]; hHash
0x180006ab6  call    cs:__imp_BCryptHashData
0x180006abc  test    eax, eax
0x180006abe  jns     short loc_180006AF9
0x180006ac0  mov     rcx, [rsp+88h]; this
0x180006ac8  mov     r9d, eax; char *
0x180006acb  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180006ad2  mov     edx, 1C7h; void *
0x180006ad7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006adc  mov     ebx, eax
0x180006ade  lea     rcx, [rsp+88h+phHash]
0x180006ae3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180006ae8  lea     rcx, [rsp+88h+pbOutput]
0x180006aed  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180006af2  mov     eax, ebx
0x180006af4  jmp     loc_180006DA9
0x180006af9  mov     dword ptr [rsp+88h+pbInput], 0E2FFFFFFh
0x180006b04  xor     r9d, r9d; dwFlags
0x180006b07  lea     r8d, [r9+4]; cbInput
0x180006b0b  lea     rdx, [rsp+88h+pbInput]; pbInput
0x180006b13  mov     rcx, [rsp+88h+phHash]; hHash
0x180006b18  call    cs:__imp_BCryptHashData
0x180006b1e  test    eax, eax
0x180006b20  jns     short loc_180006B6E
0x180006b22  mov     rcx, [rsp+88h]; this
0x180006b2a  mov     r9d, eax; char *
0x180006b2d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180006b34  mov     edx, 1D4h; void *
0x180006b39  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006b3e  mov     ebx, eax
0x180006b40  mov     rcx, [rsp+88h+phHash]; hHash
0x180006b45  test    rcx, rcx
0x180006b48  jz      short loc_180006B50
0x180006b4a  call    cs:__imp_BCryptDestroyHash
0x180006b50  mov     rcx, [rsp+88h+pbOutput]
0x180006b55  test    rcx, rcx
0x180006b58  jz      short loc_180006B67
0x180006b5a  mov     rdx, [rsp+88h+var_30]
0x180006b5f  sub     rdx, rcx
0x180006b62  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006b67  mov     eax, ebx
0x180006b69  jmp     loc_180006DA9
0x180006b6e  xor     r9d, r9d; dwFlags
0x180006b71  mov     r8d, [rsp+88h+cbInput]; cbInput
0x180006b79  mov     rdx, [rsp+88h+arg_20]; pbInput
0x180006b81  mov     rcx, [rsp+88h+phHash]; hHash
0x180006b86  call    cs:__imp_BCryptHashData
0x180006b8c  test    eax, eax
0x180006b8e  jns     short loc_180006BDC
0x180006b90  mov     rcx, [rsp+88h]; this
0x180006b98  mov     r9d, eax; char *
0x180006b9b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180006ba2  mov     edx, 1DBh; void *
0x180006ba7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006bac  mov     ebx, eax
0x180006bae  mov     rcx, [rsp+88h+phHash]; hHash
0x180006bb3  test    rcx, rcx
0x180006bb6  jz      short loc_180006BBE
0x180006bb8  call    cs:__imp_BCryptDestroyHash
0x180006bbe  mov     rcx, [rsp+88h+pbOutput]
0x180006bc3  test    rcx, rcx
0x180006bc6  jz      short loc_180006BD5
0x180006bc8  mov     rdx, [rsp+88h+var_30]
0x180006bcd  sub     rdx, rcx
0x180006bd0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006bd5  mov     eax, ebx
0x180006bd7  jmp     loc_180006DA9
0x180006bdc  mov     eax, dword ptr [rsp+88h+pbOutput+8]
0x180006be0  mov     rbx, [rsp+88h+pbOutput]
0x180006be5  sub     eax, ebx
0x180006be7  mov     edi, eax
0x180006be9  xor     r9d, r9d; dwFlags
0x180006bec  mov     r8d, eax; cbOutput
0x180006bef  mov     rdx, rbx; pbOutput
0x180006bf2  mov     rcx, [rsp+88h+phHash]; hHash
0x180006bf7  call    cs:__imp_BCryptFinishHash
0x180006bfd  test    eax, eax
0x180006bff  jns     short loc_180006C3A
0x180006c01  mov     rcx, [rsp+88h]; this
0x180006c09  mov     r9d, eax; char *
0x180006c0c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180006c13  mov     edx, 1E2h; void *
0x180006c18  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006c1d  mov     ebx, eax
0x180006c1f  lea     rcx, [rsp+88h+phHash]
0x180006c24  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180006c29  lea     rcx, [rsp+88h+pbOutput]
0x180006c2e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180006c33  mov     eax, ebx
0x180006c35  jmp     loc_180006DA9
0x180006c3a  mov     rcx, [rsp+88h+phHash]; hHash
0x180006c3f  test    rcx, rcx
0x180006c42  jz      short loc_180006C4A
0x180006c44  call    cs:__imp_BCryptDestroyHash
0x180006c4a  mov     [rsp+88h+pbInput], 0
0x180006c56  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180006c5e  mov     [rsp+88h+cbSecret], esi; cbSecret
0x180006c62  mov     [rsp+88h+pbSecret], r14; int
0x180006c67  xor     r9d, r9d; cbHashObject
0x180006c6a  xor     r8d, r8d; pbHashObject
0x180006c6d  lea     rdx, [rsp+88h+pbInput]; phHash
0x180006c75  mov     ecx, 0B1h; hAlgorithm
0x180006c7a  call    cs:__imp_BCryptCreateHash
0x180006c80  test    eax, eax
0x180006c82  jns     short loc_180006CD1
0x180006c84  mov     rcx, [rsp+88h]; this
0x180006c8c  mov     r9d, eax; char *
0x180006c8f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180006c96  mov     edx, 1F0h; void *
0x180006c9b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006ca0  mov     edi, eax
0x180006ca2  mov     rcx, [rsp+88h+pbInput]; hHash
0x180006caa  test    rcx, rcx
0x180006cad  jz      short loc_180006CB5
0x180006caf  call    cs:__imp_BCryptDestroyHash
0x180006cb5  test    rbx, rbx
0x180006cb8  jz      short loc_180006CCA
0x180006cba  mov     rdx, [rsp+88h+var_30]
0x180006cbf  sub     rdx, rbx
0x180006cc2  mov     rcx, rbx
0x180006cc5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006cca  mov     eax, edi
0x180006ccc  jmp     loc_180006DA9
0x180006cd1  xor     r9d, r9d; dwFlags
0x180006cd4  mov     r8d, edi; cbInput
0x180006cd7  mov     rdx, rbx; pbInput
0x180006cda  mov     rcx, [rsp+88h+pbInput]; hHash
0x180006ce2  call    cs:__imp_BCryptHashData
0x180006ce8  test    eax, eax
0x180006cea  jns     short loc_180006D28
0x180006cec  mov     rcx, [rsp+88h]; this
0x180006cf4  mov     r9d, eax; char *
0x180006cf7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180006cfe  mov     edx, 1F7h; void *
0x180006d03  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006d08  mov     ebx, eax
0x180006d0a  lea     rcx, [rsp+88h+pbInput]
0x180006d12  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180006d17  lea     rcx, [rsp+88h+pbOutput]
0x180006d1c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180006d21  mov     eax, ebx
0x180006d23  jmp     loc_180006DA9
0x180006d28  xor     r9d, r9d; dwFlags
0x180006d2b  mov     r8d, [rsp+88h+cbOutput]; cbOutput
0x180006d33  mov     rdx, [rsp+88h+arg_30]; pbOutput
0x180006d3b  mov     rcx, [rsp+88h+pbInput]; hHash
0x180006d43  call    cs:__imp_BCryptFinishHash
0x180006d49  test    eax, eax
0x180006d4b  jns     short loc_180006D86
0x180006d4d  mov     rcx, [rsp+88h]; this
0x180006d55  mov     r9d, eax; char *
0x180006d58  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x180006d5f  mov     edx, 1FEh; void *
0x180006d64  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006d69  mov     ebx, eax
0x180006d6b  lea     rcx, [rsp+88h+pbInput]
0x180006d73  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180006d78  lea     rcx, [rsp+88h+pbOutput]
0x180006d7d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180006d82  mov     eax, ebx
0x180006d84  jmp     short loc_180006DA9
0x180006d86  lea     rcx, [rsp+88h+pbInput]
0x180006d8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180006d93  lea     rcx, [rsp+88h+pbOutput]
0x180006d98  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180006d9d  nop
0x180006d9e  xor     eax, eax
0x180006da0  jmp     short loc_180006DA9
0x180006da2  mov     eax, [rsp+88h+cbOutput]
0x180006da9  add     rsp, 68h
0x180006dad  pop     r14
0x180006daf  pop     rdi
0x180006db0  pop     rsi
0x180006db1  pop     rbx
0x180006db2  retn
```
