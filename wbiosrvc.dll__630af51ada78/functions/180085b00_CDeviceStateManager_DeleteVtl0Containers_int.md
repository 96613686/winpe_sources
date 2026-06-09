# CDeviceStateManager::DeleteVtl0Containers(int &)

- ea: `0x180085b00`
- end: `0x180085e33`
- name: `?DeleteVtl0Containers@CDeviceStateManager@@QEAAJAEAH@Z`
- size: `819`
- prototype: `__int64 __fastcall(CDeviceStateManager *__hidden this, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180073538`
- `0x18009aab0`

## callees

- `0x180002350`
- `0x180016d38`
- `0x18003c468`
- `0x18003f2dc`
- `0x180044b1c`
- `0x18005388c`
- `0x180056358`
- `0x18006035c`
- `0x180068f60`
- `0x180069cc8`
- `0x180085b00`
- `0x1800be44c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085d19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085e1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085d19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085e1e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180085bff`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180085bff`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180085c12`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180085c12`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180085bb2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180085bb2`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180085bca`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180085bca`
- `cryptngc!NgcDeleteContainerEx` at `0x180085c8d`
- `cryptngc!NgcDeleteContainerEx` at `0x180085c8d`
- `cryptngc!NgcEnumContainers` at `0x180085b64`
- `cryptngc!NgcEnumContainers` at `0x180085ced`
- `cryptngc!NgcEnumContainers` at `0x180085b64`
- `cryptngc!NgcEnumContainers` at `0x180085ced`
- `WININET!InternetGetConnectedState` at `0x180085d26`
- `WININET!InternetGetConnectedState` at `0x180085d26`

## string_xrefs

- `0x180085b81`: `onecore\ds\security\biometrics\service\server\devicestatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDeviceStateManager::DeleteVtl0Containers(CDeviceStateManager *this, int *a2)
{
  unsigned __int8 v3; // r15
  unsigned __int8 v4; // r14
  int v5; // esi
  int LastError; // ebx
  HLOCAL v7; // rcx
  const char *v8; // r9
  unsigned int *v9; // r9
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  HLOCAL v13; // rcx
  __int64 v14; // rcx
  ULONG v15; // r8d
  __int64 v17; // rdx
  HLOCAL v18; // rcx
  int v19; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+58h] [rbp-A8h] BYREF
  struct _WINBIO_IDENTITY v22; // [rsp+5Ch] [rbp-A4h] BYREF
  _BYTE pDestinationSid[72]; // [rsp+A8h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *(_QWORD *)&v22.Value.AccountSid.Data[12] = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  *a2 = 0;
  *(_DWORD *)&v22.Value.AccountSid.Data[20] = 0;
  hMem = 0;
  *(_OWORD *)&v22.Value.AccountSid.Data[28] = (unsigned __int64)&hMem;
  v22.Value.AccountSid.Data[44] = 1;
  LastError = NgcEnumContainers(0, &v22.Value.AccountSid.Data[36], &v22.Value.AccountSid.Data[12]);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v22.Value.AccountSid.Data[28]);
  if ( LastError == -2146893782 )
  {
LABEL_19:
    v13 = hMem;
    hMem = 0;
    if ( v13 )
      LocalFree(v13);
    InternetGetConnectedState((LPDWORD)&v22.Value.AccountSid.Data[20], 0);
    if ( (unsigned int)dword_18010F170 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
      {
        v22.Value.Null = v15;
        v22.Type = v3;
        v21 = v4;
        *(_DWORD *)&v22.Value.AccountSid.Data[4] = *a2;
        LODWORD(hMem) = v5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v14,
          (__int64)word_1800EF07A);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22.Value.AccountSid.Data[12]);
    return 0;
  }
  else
  {
    while ( LastError >= 0 )
    {
      v7 = hMem;
      if ( (*((_BYTE *)hMem + 56) & 4) == 0 )
      {
        v21 = 0;
        *(_QWORD *)&v22.Value.AccountSid.Data[4] = 0;
        if ( ConvertStringSidToSidW(*((LPCWSTR *)hMem + 3), (PSID *)&v22.Value.AccountSid.Data[4]) )
        {
          LsaLookupUserAccountType(*(_QWORD *)&v22.Value.AccountSid.Data[4], &v21);
          if ( v21 == 4 )
            v3 = 1;
          memset_0(&v22.Value.AccountSid.Data[60], 0, sizeof(struct _WINBIO_IDENTITY));
          if ( !CopySid(0x44u, pDestinationSid, *(PSID *)&v22.Value.AccountSid.Data[4]) )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x18B,
                          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\devicestatemanager.cpp",
                          v8);
            goto LABEL_29;
          }
          *(_DWORD *)&v22.Value.AccountSid.Data[64] = GetLengthSid(*(PSID *)&v22.Value.AccountSid.Data[4]);
          *(_DWORD *)&v22.Value.AccountSid.Data[60] = 3;
          v22.Type = 0;
          v22.Value.Null = 0;
          LastError = winbio::GetEnrolledFactorsCommon(
                        (winbio *)&v22.Value.AccountSid.Data[60],
                        &v22,
                        &v22.Value.Null,
                        v9);
          if ( LastError < 0 )
          {
            v17 = 400;
            goto LABEL_28;
          }
          if ( (v22.Type & 2) != 0 )
          {
            v11 = winbio::SetBioRegKeyValue(v10, 5, 1);
            if ( v11 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x194,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\devicestatemanager.cpp",
                (const char *)(unsigned int)v11,
                v19);
          }
        }
        v4 = 1;
        v12 = NgcDeleteContainerEx(*((_QWORD *)hMem + 3), 0);
        if ( v12 >= 0 )
          ++*a2;
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x198,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\devicestatemanager.cpp",
            (const char *)(unsigned int)v12,
            v19);
        v7 = hMem;
      }
      ++v5;
      hMem = 0;
      if ( v7 )
        LocalFree(v7);
      hMem = 0;
      *(_QWORD *)&v22.Value.AccountSid.Data[28] = &hMem;
      *(_QWORD *)&v22.Value.AccountSid.Data[36] = 0;
      v22.Value.AccountSid.Data[44] = 1;
      LastError = NgcEnumContainers(0, &v22.Value.AccountSid.Data[36], &v22.Value.AccountSid.Data[12]);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v22.Value.AccountSid.Data[28]);
      if ( LastError == -2146893782 )
        goto LABEL_19;
    }
    v17 = 376;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\devicestatemanager.cpp",
      (const char *)(unsigned int)LastError,
      v19);
LABEL_29:
    v18 = hMem;
    hMem = 0;
    if ( v18 )
      LocalFree(v18);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22.Value.AccountSid.Data[12]);
    return (unsigned int)LastError;
  }
}

```

## disassembly

```asm
0x180085b00  push    rbp
0x180085b02  push    rbx
0x180085b03  push    rsi
0x180085b04  push    rdi
0x180085b05  push    r12
0x180085b07  push    r13
0x180085b09  push    r14
0x180085b0b  push    r15
0x180085b0d  lea     rbp, [rsp-8]
0x180085b12  sub     rsp, 108h
0x180085b19  mov     rax, cs:__security_cookie
0x180085b20  xor     rax, rsp
0x180085b23  mov     [rbp+40h+var_50], rax
0x180085b27  mov     rdi, rdx
0x180085b2a  xor     r12d, r12d
0x180085b2d  mov     qword ptr [rsp+140h+var_E4.Value+10h], r12
0x180085b32  mov     r15b, r12b
0x180085b35  mov     r14b, r12b
0x180085b38  mov     esi, r12d
0x180085b3b  mov     [rdx], r12d
0x180085b3e  mov     dword ptr [rsp+140h+var_E4.Value+18h], r12d
0x180085b43  mov     [rsp+140h+hMem], r12
0x180085b48  lea     rax, [rsp+140h+hMem]
0x180085b4d  mov     qword ptr [rbp+40h+var_E4.Value+20h], rax
0x180085b51  mov     qword ptr [rbp+40h+var_E4.Value+28h], r12
0x180085b55  mov     byte ptr [rbp+40h+var_E4.Value+30h], 1
0x180085b59  lea     r8, [rsp+140h+var_E4.Value+10h]
0x180085b5e  lea     rdx, [rbp+40h+var_E4.Value+28h]
0x180085b62  xor     ecx, ecx
0x180085b64  call    cs:__imp_NgcEnumContainers
0x180085b6a  mov     ebx, eax
0x180085b6c  lea     rcx, [rbp+40h+var_E4.Value+20h]
0x180085b70  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180085b75  cmp     ebx, 8009002Ah
0x180085b7b  jz      loc_180085D0A
0x180085b81  lea     r13, aOnecoreDsSecur_44; "onecore\\ds\\security\\biometrics\\serv"...
0x180085b88  test    ebx, ebx
0x180085b8a  js      loc_180085DFA
0x180085b90  mov     rcx, [rsp+140h+hMem]; hMem
0x180085b95  test    byte ptr [rcx+38h], 4
0x180085b99  jnz     loc_180085CB6
0x180085b9f  mov     [rsp+140h+var_E8], r12d
0x180085ba4  mov     qword ptr [rsp+140h+var_E4.Value+8], r12
0x180085ba9  lea     rdx, [rsp+140h+var_E4.Value+8]; Sid
0x180085bae  mov     rcx, [rcx+18h]; StringSid
0x180085bb2  call    cs:__imp_ConvertStringSidToSidW
0x180085bb8  test    eax, eax
0x180085bba  jz      loc_180085C7A
0x180085bc0  lea     rdx, [rsp+140h+var_E8]
0x180085bc5  mov     rcx, qword ptr [rsp+140h+var_E4.Value+8]
0x180085bca  call    cs:__imp_LsaLookupUserAccountType
0x180085bd0  movzx   r15d, r15b
0x180085bd4  cmp     [rsp+140h+var_E8], 4
0x180085bd9  mov     eax, 1
0x180085bde  cmovz   r15d, eax
0x180085be2  xor     edx, edx; Val
0x180085be4  lea     r8d, [rax+4Bh]; Size
0x180085be8  lea     rcx, [rbp+40h+var_E4.Value+40h]; void *
0x180085bec  call    memset_0
0x180085bf1  mov     r8, qword ptr [rsp+140h+var_E4.Value+8]; pSourceSid
0x180085bf6  lea     rdx, [rbp+40h+pDestinationSid]; pDestinationSid
0x180085bfa  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180085bff  call    cs:__imp_CopySid
0x180085c05  test    eax, eax
0x180085c07  jz      loc_180085DE5
0x180085c0d  mov     rcx, qword ptr [rsp+140h+var_E4.Value+8]; pSid
0x180085c12  call    cs:__imp_GetLengthSid
0x180085c18  mov     dword ptr [rbp+40h+var_E4.Value+44h], eax
0x180085c1b  mov     dword ptr [rbp+40h+var_E4.Value+40h], 3
0x180085c22  mov     [rsp+140h+var_E4.Type], r12d
0x180085c27  mov     dword ptr [rsp+140h+var_E4.Value], r12d
0x180085c2c  lea     r8, [rsp+140h+var_E4.Value]; unsigned int *
0x180085c31  lea     rdx, [rsp+140h+var_E4]; struct _WINBIO_IDENTITY *
0x180085c36  lea     rcx, [rbp+40h+var_E4.Value+40h]; this
0x180085c3a  call    ?GetEnrolledFactorsCommon@winbio@@YAJPEAU_WINBIO_IDENTITY@@PEAI1@Z; winbio::GetEnrolledFactorsCommon(_WINBIO_IDENTITY *,uint *,uint *)
0x180085c3f  mov     ebx, eax
0x180085c41  test    eax, eax
0x180085c43  js      loc_180085DDE
0x180085c49  mov     ebx, 1
0x180085c4e  test    byte ptr [rsp+140h+var_E4.Type], 2
0x180085c53  jz      short loc_180085C7F
0x180085c55  mov     r8d, ebx
0x180085c58  lea     edx, [rbx+4]
0x180085c5b  call    ?SetBioRegKeyValue@winbio@@YAJPEAU_WINBIO_IDENTITY@@W4RegKeyName@1@K@Z; winbio::SetBioRegKeyValue(_WINBIO_IDENTITY *,winbio::RegKeyName,ulong)
0x180085c60  mov     rcx, [rbp+48h]; this
0x180085c64  test    eax, eax
0x180085c66  jns     short loc_180085C7F
0x180085c68  mov     r9d, eax; char *
0x180085c6b  mov     r8, r13; unsigned int
0x180085c6e  mov     edx, 194h; void *
0x180085c73  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180085c78  jmp     short loc_180085C7F
0x180085c7a  mov     ebx, 1
0x180085c7f  mov     r14b, bl
0x180085c82  xor     edx, edx
0x180085c84  mov     rcx, [rsp+140h+hMem]
0x180085c89  mov     rcx, [rcx+18h]
0x180085c8d  call    cs:__imp_NgcDeleteContainerEx
0x180085c93  mov     rcx, [rbp+48h]; this
0x180085c97  test    eax, eax
0x180085c99  jns     short loc_180085CB2
0x180085c9b  mov     r9d, eax; char *
0x180085c9e  mov     r8, r13; unsigned int
0x180085ca1  mov     edx, 198h; void *
0x180085ca6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180085cab  mov     rcx, [rsp+140h+hMem]
0x180085cb0  jmp     short loc_180085CBB
0x180085cb2  add     [rdi], ebx
0x180085cb4  jmp     short loc_180085CAB
0x180085cb6  mov     ebx, 1
0x180085cbb  add     esi, ebx
0x180085cbd  mov     [rsp+140h+hMem], r12
0x180085cc2  test    rcx, rcx
0x180085cc5  jz      short loc_180085CCD
0x180085cc7  call    cs:__imp_LocalFree
0x180085ccd  mov     [rsp+140h+hMem], r12
0x180085cd2  lea     rax, [rsp+140h+hMem]
0x180085cd7  mov     qword ptr [rbp+40h+var_E4.Value+20h], rax
0x180085cdb  mov     qword ptr [rbp+40h+var_E4.Value+28h], r12
0x180085cdf  mov     byte ptr [rbp+40h+var_E4.Value+30h], bl
0x180085ce2  lea     r8, [rsp+140h+var_E4.Value+10h]
0x180085ce7  lea     rdx, [rbp+40h+var_E4.Value+28h]
0x180085ceb  xor     ecx, ecx
0x180085ced  call    cs:__imp_NgcEnumContainers
0x180085cf3  mov     ebx, eax
0x180085cf5  lea     rcx, [rbp+40h+var_E4.Value+20h]
0x180085cf9  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180085cfe  cmp     ebx, 8009002Ah
0x180085d04  jnz     loc_180085B88
0x180085d0a  mov     rcx, [rsp+140h+hMem]; hMem
0x180085d0f  mov     [rsp+140h+hMem], r12
0x180085d14  test    rcx, rcx
0x180085d17  jz      short loc_180085D1F
0x180085d19  call    cs:__imp_LocalFree
0x180085d1f  xor     edx, edx; dwReserved
0x180085d21  lea     rcx, [rsp+140h+var_E4.Value+18h]; lpdwFlags
0x180085d26  call    cs:__imp_InternetGetConnectedState
0x180085d2c  mov     r8d, eax
0x180085d2f  mov     ecx, cs:dword_18010F170
0x180085d35  cmp     ecx, 5
0x180085d38  jbe     short loc_180085DB2
0x180085d3a  mov     rdx, 400000000000h
0x180085d44  lea     rcx, dword_18010F170
0x180085d4b  call    _tlgKeywordOn
0x180085d50  test    al, al
0x180085d52  jz      short loc_180085DB2
0x180085d54  mov     dword ptr [rsp+140h+var_E4.Value], r8d
0x180085d59  movzx   eax, r15b
0x180085d5d  mov     [rsp+140h+var_E4.Type], eax
0x180085d61  movzx   eax, r14b
0x180085d65  mov     [rsp+140h+var_E8], eax
0x180085d69  mov     eax, [rdi]
0x180085d6b  mov     dword ptr [rsp+140h+var_E4.Value+8], eax
0x180085d6f  mov     dword ptr [rsp+140h+hMem], esi
0x180085d73  lea     rax, [rsp+140h+var_E4.Value]
0x180085d78  mov     [rsp+140h+var_100], rax
0x180085d7d  lea     rax, [rsp+140h+var_E4]
0x180085d82  mov     [rsp+140h+var_108], rax
0x180085d87  lea     rax, [rsp+140h+var_E8]
0x180085d8c  mov     [rsp+140h+var_110], rax
0x180085d91  lea     rax, [rsp+140h+var_E4.Value+8]
0x180085d96  mov     [rsp+140h+var_118], rax
0x180085d9b  lea     rax, [rsp+140h+hMem]
0x180085da0  mov     [rsp+140h+var_120], rax
0x180085da5  lea     rdx, word_1800EF07A
0x180085dac  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180085db1  nop
0x180085db2  lea     rcx, [rsp+140h+var_E4.Value+10h]
0x180085db7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?NgcFreeEnumState@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180085dbc  xor     eax, eax
0x180085dbe  mov     rcx, [rbp+40h+var_50]
0x180085dc2  xor     rcx, rsp; StackCookie
0x180085dc5  call    __security_check_cookie
0x180085dca  add     rsp, 108h
0x180085dd1  pop     r15
0x180085dd3  pop     r14
0x180085dd5  pop     r13
0x180085dd7  pop     r12
0x180085dd9  pop     rdi
0x180085dda  pop     rsi
0x180085ddb  pop     rbx
0x180085ddc  pop     rbp
0x180085ddd  retn
0x180085dde  mov     edx, 190h
0x180085de3  jmp     short loc_180085DFF
0x180085de5  mov     rcx, [rbp+48h]; this
0x180085de9  mov     r8, r13; unsigned int
0x180085dec  mov     edx, 18Bh; void *
0x180085df1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180085df6  mov     ebx, eax
0x180085df8  jmp     short loc_180085E0F
0x180085dfa  mov     edx, 178h; void *
0x180085dff  mov     r9d, ebx; char *
0x180085e02  mov     r8, r13; unsigned int
0x180085e05  mov     rcx, [rbp+48h]; this
0x180085e09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085e0e  nop
0x180085e0f  mov     rcx, [rsp+140h+hMem]; hMem
0x180085e14  mov     [rsp+140h+hMem], r12
0x180085e19  test    rcx, rcx
0x180085e1c  jz      short loc_180085E25
0x180085e1e  call    cs:__imp_LocalFree
0x180085e24  nop
0x180085e25  lea     rcx, [rsp+140h+var_E4.Value+10h]
0x180085e2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?NgcFreeEnumState@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180085e2f  mov     eax, ebx
0x180085e31  jmp     short loc_180085DBE
```
