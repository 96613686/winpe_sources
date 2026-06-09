# HashBioPolicy(uchar const *,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x180006f90`
- end: `0x1800070d0`
- name: `?HashBioPolicy@@YAJPEBEPEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(PUCHAR pbInput)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006e14`
- `0x180053704`

## callees

- `0x1800058ec`
- `0x180006f90`
- `0x18001423c`
- `0x180017398`
- `0x1800530c4`
- `0x1800538b0`
- `0x1800602dc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006fe9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006fe9`
- `bcrypt!BCryptDestroyHash` at `0x1800070b8`
- `bcrypt!BCryptDestroyHash` at `0x1800070b8`
- `bcrypt!BCryptFinishHash` at `0x180007052`
- `bcrypt!BCryptFinishHash` at `0x180007052`
- `bcrypt!BCryptHashData` at `0x180006ffc`
- `bcrypt!BCryptHashData` at `0x180006ffc`
- `bcrypt!BCryptCreateHash` at `0x180006fd5`
- `bcrypt!BCryptCreateHash` at `0x180006fd5`

## string_xrefs

- `0x18000700b`: `onecore\ds\security\biometrics\service\trustlet\lib\hmac.cpp`
- `0x180007063`: `onecore\ds\security\biometrics\service\trustlet\lib\hmac.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HashBioPolicy(PUCHAR pbInput, __int64 a2)
{
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  DWORD LengthSid; // eax
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  int v10; // [rsp+20h] [rbp-40h]
  PUCHAR pbOutput[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v12; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+80h] [rbp+20h] BYREF

  phHash = 0;
  v4 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
  if ( v4 < 0 )
  {
    v5 = 23;
LABEL_5:
    v7 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v5,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\hmac.cpp",
           (const char *)(unsigned int)v4,
           v10);
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
    return v7;
  }
  LengthSid = GetLengthSid(pbInput);
  v4 = BCryptHashData(phHash, pbInput, LengthSid, 0);
  if ( v4 < 0 )
  {
    v5 = 30;
    goto LABEL_5;
  }
  *(_OWORD *)pbOutput = 0;
  v12 = 0;
  std::vector<unsigned char>::_Construct_n<>(pbOutput, 32);
  v8 = BCryptFinishHash(phHash, pbOutput[0], LODWORD(pbOutput[1]) - LODWORD(pbOutput[0]), 0);
  if ( v8 < 0 )
  {
    v7 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x26,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\hmac.cpp",
           (const char *)(unsigned int)v8,
           v10);
    std::vector<unsigned char>::_Tidy(pbOutput);
    goto LABEL_8;
  }
  std::vector<unsigned char>::operator=(a2, pbOutput);
  if ( pbOutput[0] )
    std::_Deallocate<16>(pbOutput[0], v12 - (unsigned __int64)pbOutput[0]);
  if ( phHash )
    BCryptDestroyHash(phHash);
  return 0;
}

```

## disassembly

```asm
0x180006f90  mov     rax, rsp
0x180006f93  mov     [rax+8], rbx
0x180006f97  mov     [rax+10h], rdi
0x180006f9b  push    rbp
0x180006f9c  mov     rbp, rsp
0x180006f9f  sub     rsp, 60h
0x180006fa3  mov     rdi, rdx
0x180006fa6  mov     rbx, rcx
0x180006fa9  mov     [rbp+phHash], 0
0x180006fb1  mov     dword ptr [rax-38h], 0
0x180006fb8  mov     dword ptr [rax-40h], 0
0x180006fbf  mov     qword ptr [rax-48h], 0
0x180006fc7  xor     r9d, r9d; cbHashObject
0x180006fca  xor     r8d, r8d; pbHashObject
0x180006fcd  lea     rdx, [rbp+phHash]; phHash
0x180006fd1  lea     ecx, [r9+41h]; hAlgorithm
0x180006fd5  call    cs:__imp_BCryptCreateHash
0x180006fdb  test    eax, eax
0x180006fdd  jns     short loc_180006FE6
0x180006fdf  mov     edx, 17h
0x180006fe4  jmp     short loc_18000700B
0x180006fe6  mov     rcx, rbx; pSid
0x180006fe9  call    cs:__imp_GetLengthSid
0x180006fef  xor     r9d, r9d; dwFlags
0x180006ff2  mov     r8d, eax; cbInput
0x180006ff5  mov     rdx, rbx; pbInput
0x180006ff8  mov     rcx, [rbp+phHash]; hHash
0x180006ffc  call    cs:__imp_BCryptHashData
0x180007002  test    eax, eax
0x180007004  jns     short loc_180007022
0x180007006  mov     edx, 1Eh; void *
0x18000700b  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\biometrics\\serv"...
0x180007012  mov     r9d, eax; char *
0x180007015  mov     rcx, [rbp+8]; this
0x180007019  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000701e  mov     ebx, eax
0x180007020  jmp     short loc_180007080
0x180007022  xorps   xmm0, xmm0
0x180007025  movdqu  xmmword ptr [rbp+pbOutput], xmm0
0x18000702a  mov     [rbp+var_10], 0
0x180007032  mov     edx, 20h ; ' '
0x180007037  lea     rcx, [rbp+pbOutput]
0x18000703b  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x180007040  mov     r8d, dword ptr [rbp+pbOutput+8]
0x180007044  mov     rdx, [rbp+pbOutput]; pbOutput
0x180007048  sub     r8d, edx; cbOutput
0x18000704b  xor     r9d, r9d; dwFlags
0x18000704e  mov     rcx, [rbp+phHash]; hHash
0x180007052  call    cs:__imp_BCryptFinishHash
0x180007058  test    eax, eax
0x18000705a  jns     short loc_18000708D
0x18000705c  mov     rcx, [rbp+8]; this
0x180007060  mov     r9d, eax; char *
0x180007063  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\biometrics\\serv"...
0x18000706a  mov     edx, 26h ; '&'; void *
0x18000706f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180007074  mov     ebx, eax
0x180007076  lea     rcx, [rbp+pbOutput]
0x18000707a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000707f  nop
0x180007080  lea     rcx, [rbp+phHash]
0x180007084  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007089  mov     eax, ebx
0x18000708b  jmp     short loc_1800070C0
0x18000708d  lea     rdx, [rbp+pbOutput]
0x180007091  mov     rcx, rdi
0x180007094  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180007099  mov     rcx, [rbp+pbOutput]
0x18000709d  test    rcx, rcx
0x1800070a0  jz      short loc_1800070AF
0x1800070a2  mov     rdx, [rbp+var_10]
0x1800070a6  sub     rdx, rcx
0x1800070a9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800070ae  nop
0x1800070af  mov     rcx, [rbp+phHash]; hHash
0x1800070b3  test    rcx, rcx
0x1800070b6  jz      short loc_1800070BE
0x1800070b8  call    cs:__imp_BCryptDestroyHash
0x1800070be  xor     eax, eax
0x1800070c0  mov     rbx, [rsp+60h+arg_0]
0x1800070c5  mov     rdi, [rsp+60h+arg_8]
0x1800070ca  add     rsp, 60h
0x1800070ce  pop     rbp
0x1800070cf  retn
```
