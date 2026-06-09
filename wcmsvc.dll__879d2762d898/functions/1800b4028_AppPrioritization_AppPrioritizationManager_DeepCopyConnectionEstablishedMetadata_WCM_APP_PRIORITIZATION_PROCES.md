# AppPrioritization::AppPrioritizationManager::DeepCopyConnectionEstablishedMetadata(_WCM_APP_PRIORITIZATION_PROCESS_METADATA_AT_FLOW_ESTABLISHED const &,AppPrioritization::AppPrioritizationManager::AppConnectionEstablishedNotificationData *)

- ea: `0x1800b4028`
- end: `0x1800b4485`
- name: `?DeepCopyConnectionEstablishedMetadata@AppPrioritizationManager@AppPrioritization@@CAKAEBU_WCM_APP_PRIORITIZATION_PROCESS_METADATA_AT_FLOW_ESTABLISHED@@PEAUAppConnectionEstablishedNotificationData@12@@Z`
- size: `1117`
- prototype: `static unsigned int(const struct _WCM_APP_PRIORITIZATION_PROCESS_METADATA_AT_FLOW_ESTABLISHED *, struct AppPrioritization::AppPrioritizationManager::AppConnectionEstablishedNotificationData *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800b4bb0`

## callees

- `0x18000529c`
- `0x18003a08c`
- `0x18003cacc`
- `0x180068f44`
- `0x18006adc0`
- `0x18006bd0c`
- `0x180085bc4`
- `0x1800b3628`
- `0x1800b3868`
- `0x1800b4028`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b41ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b41ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b418f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b418f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b4155`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b4155`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b4143`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b4143`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800b41c0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800b41c0`

## pseudocode

```c
__int64 __fastcall AppPrioritization::AppPrioritizationManager::DeepCopyConnectionEstablishedMetadata(
        const struct _WCM_APP_PRIORITIZATION_PROCESS_METADATA_AT_FLOW_ESTABLISHED *a1,
        struct AppPrioritization::AppPrioritizationManager::AppConnectionEstablishedNotificationData *a2)
{
  const char *v4; // r9
  void *v5; // rcx
  DWORD LengthSid; // eax
  DWORD v7; // esi
  __int64 v8; // rcx
  __int64 result; // rax
  HLOCAL v10; // rax
  __int64 v11; // rcx
  PSID *v12; // rax
  DWORD LastError; // eax
  int v14; // r8d
  DWORD v15; // ebx
  int *v16; // r14
  int *v17; // rdx
  __int64 v18; // rsi
  __int64 v19; // r8
  int *v20; // rdx
  __int64 v21; // r8
  _BYTE v22[32]; // [rsp+30h] [rbp-1D8h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-1B8h] BYREF
  _BYTE v24[32]; // [rsp+70h] [rbp-198h] BYREF
  __int128 v25; // [rsp+90h] [rbp-178h]
  __int64 v26; // [rsp+A0h] [rbp-168h]
  __int64 v27; // [rsp+A8h] [rbp-160h]
  __int64 v28; // [rsp+B0h] [rbp-158h]
  int v29; // [rsp+B8h] [rbp-150h]
  __int64 v30; // [rsp+BCh] [rbp-14Ch]
  int v31; // [rsp+C4h] [rbp-144h]
  __int64 v32; // [rsp+C8h] [rbp-140h]
  __int16 v33; // [rsp+D0h] [rbp-138h]
  char v34; // [rsp+D2h] [rbp-136h]
  int v35; // [rsp+D3h] [rbp-135h]
  char v36; // [rsp+D7h] [rbp-131h]
  _BYTE v37[128]; // [rsp+D8h] [rbp-130h] BYREF
  _BYTE v38[129]; // [rsp+158h] [rbp-B0h] BYREF
  __int16 v39; // [rsp+1D9h] [rbp-2Fh]
  char v40; // [rsp+1DBh] [rbp-2Dh]
  int v41; // [rsp+1DCh] [rbp-2Ch]
  __int64 v42; // [rsp+1E0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]
  DWORD v44; // [rsp+210h] [rbp+8h] BYREF

  std::wstring::wstring(v22);
  std::wstring::wstring(v23);
  std::wstring::wstring(v24);
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 1;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  memset_0(v38, 0, 0x80u);
  v38[128] = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 1;
  AppPrioritization::AppPrioritizationManager::AppConnectionEstablishedNotificationData::operator=(a2, v22);
  AppPrioritization::AppPrioritizationManager::AppIdentityNotificationData::~AppIdentityNotificationData((AppPrioritization::AppPrioritizationManager::AppIdentityNotificationData *)v22);
  try
  {
    v5 = (void *)*((_QWORD *)a1 + 9);
    if ( v5 && IsValidSid(v5) )
    {
      LengthSid = GetLengthSid(*((PSID *)a1 + 9));
      v7 = LengthSid;
      if ( LengthSid )
      {
        v10 = LocalAlloc(0x40u, LengthSid);
        wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::reset(
          (char *)a2 + 96,
          v10);
        v12 = (PSID *)*((_QWORD *)a2 + 12);
        if ( v12 && *v12 )
        {
          if ( CopySid(v7, *v12, *((PSID *)a1 + 9)) )
          {
            v16 = &dword_180103494;
            v17 = &dword_180103494;
            if ( *((_QWORD *)a1 + 6) )
              v17 = (int *)*((_QWORD *)a1 + 6);
            v18 = -1;
            v19 = -1;
            do
              ++v19;
            while ( *((_WORD *)v17 + v19) );
            std::wstring::_Append<unsigned short>(a2);
            v20 = &dword_180103494;
            if ( *((_QWORD *)a1 + 7) )
              v20 = (int *)*((_QWORD *)a1 + 7);
            v21 = -1;
            do
              ++v21;
            while ( *((_WORD *)v20 + v21) );
            std::wstring::_Append<unsigned short>((char *)a2 + 32);
            if ( *((_QWORD *)a1 + 8) )
              v16 = (int *)*((_QWORD *)a1 + 8);
            do
              ++v18;
            while ( *((_WORD *)v16 + v18) );
            std::wstring::_Append<unsigned short>((char *)a2 + 64);
            if ( !*((_QWORD *)a1 + 8) )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            *((_QWORD *)a2 + 14) = *((_QWORD *)a1 + 5);
            *((_QWORD *)a2 + 15) = *((_QWORD *)a1 + 3);
            *((_QWORD *)a2 + 16) = *((_QWORD *)a1 + 46);
            *((_BYTE *)a2 + 136) = *((_DWORD *)a1 + 89) != 0;
            *((_BYTE *)a2 + 137) = *((_DWORD *)a1 + 9) != 0;
            *((_BYTE *)a2 + 138) = *((_DWORD *)a1 + 8) != 0;
            *((_DWORD *)a2 + 35) = *((_DWORD *)a1 + 90);
            *((_DWORD *)a2 + 36) = *((_DWORD *)a1 + 91);
            *((_DWORD *)a2 + 37) = *((_DWORD *)a1 + 87);
            *((_QWORD *)a2 + 19) = *((_QWORD *)a1 + 1);
            *((_WORD *)a2 + 80) = *((_WORD *)a1 + 8);
            *((_BYTE *)a2 + 162) = *((_BYTE *)a1 + 18);
            *(_OWORD *)((char *)a2 + 168) = *((_OWORD *)a1 + 5);
            *(_OWORD *)((char *)a2 + 184) = *((_OWORD *)a1 + 6);
            *(_OWORD *)((char *)a2 + 200) = *((_OWORD *)a1 + 7);
            *(_OWORD *)((char *)a2 + 216) = *((_OWORD *)a1 + 8);
            *(_OWORD *)((char *)a2 + 232) = *((_OWORD *)a1 + 9);
            *(_OWORD *)((char *)a2 + 248) = *((_OWORD *)a1 + 10);
            *(_OWORD *)((char *)a2 + 264) = *((_OWORD *)a1 + 11);
            *(_OWORD *)((char *)a2 + 280) = *((_OWORD *)a1 + 12);
            *(_OWORD *)((char *)a2 + 296) = *((_OWORD *)a1 + 13);
            *(_OWORD *)((char *)a2 + 312) = *((_OWORD *)a1 + 14);
            *(_OWORD *)((char *)a2 + 328) = *((_OWORD *)a1 + 15);
            *(_OWORD *)((char *)a2 + 344) = *((_OWORD *)a1 + 16);
            *(_OWORD *)((char *)a2 + 360) = *((_OWORD *)a1 + 17);
            *(_OWORD *)((char *)a2 + 376) = *((_OWORD *)a1 + 18);
            *(_OWORD *)((char *)a2 + 392) = *((_OWORD *)a1 + 19);
            *(_OWORD *)((char *)a2 + 408) = *((_OWORD *)a1 + 20);
            *((_BYTE *)a2 + 424) = *((_BYTE *)a1 + 336);
            *((_DWORD *)a2 + 108) = *((_DWORD *)a1 + 86);
            *((_BYTE *)a2 + 436) = *((_BYTE *)a1 + 376);
            *((_BYTE *)a2 + 437) = *((_BYTE *)a1 + 377);
            *((_DWORD *)a2 + 107) = *((_DWORD *)a1 + 85);
            result = 0;
          }
          else
          {
            LastError = GetLastError();
            v15 = LastError;
            if ( (unsigned int)dword_18013A120 > 2 )
            {
              v44 = LastError;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_18013A120,
                (unsigned int)&byte_18011AA8F,
                v14,
                (_DWORD)v4,
                (__int64)&v44);
            }
            result = v15;
          }
        }
        else
        {
          if ( (unsigned int)dword_18013A120 > 2 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              v11,
              (__int64)byte_18011A9BB);
          result = 8;
        }
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (unsigned int)dword_18013A120 > 2 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v8,
            (__int64)byte_18011AA1D);
        result = 87;
      }
    }
    else
    {
      if ( (unsigned int)dword_18013A120 > 2 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (__int64)v5,
          (__int64)word_18011AB5A);
      result = 87;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6EF,
                           (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\appprioritizationmanager\\appprioritizationmanager.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x1800b4028  mov     [rsp+arg_8], rbx
0x1800b402d  mov     [rsp+arg_10], rsi
0x1800b4032  push    rdi
0x1800b4033  push    r14
0x1800b4035  push    r15
0x1800b4037  sub     rsp, 1F0h
0x1800b403e  mov     rdi, rdx
0x1800b4041  mov     rbx, rcx
0x1800b4044  lea     rcx, [rsp+208h+var_1D8]
0x1800b4049  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b404e  lea     rcx, [rsp+208h+var_1B8]
0x1800b4053  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b4058  lea     rcx, [rsp+208h+var_198]
0x1800b405d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b4062  xorps   xmm1, xmm1
0x1800b4065  movdqa  [rsp+208h+var_178], xmm1
0x1800b406e  xor     r15d, r15d
0x1800b4071  mov     [rsp+208h+var_168], r15
0x1800b4079  mov     [rsp+208h+var_160], r15
0x1800b4081  mov     [rsp+208h+var_158], r15
0x1800b4089  mov     [rsp+208h+var_150], r15d
0x1800b4091  mov     [rsp+208h+var_14C], r15
0x1800b4099  lea     r14d, [r15+1]
0x1800b409d  mov     [rsp+208h+var_144], r14d
0x1800b40a5  mov     [rsp+208h+var_140], r15
0x1800b40ad  mov     [rsp+208h+var_138], r15w
0x1800b40b6  mov     [rsp+208h+var_136], r15b
0x1800b40be  xor     eax, eax
0x1800b40c0  mov     [rsp+208h+var_135], eax
0x1800b40c7  mov     [rsp+208h+var_131], al
0x1800b40ce  lea     esi, [r14+7Fh]
0x1800b40d2  mov     r8d, esi; Size
0x1800b40d5  xor     edx, edx; Val
0x1800b40d7  lea     rcx, [rsp+208h+var_130]; void *
0x1800b40df  call    memset_0
0x1800b40e4  mov     r8d, esi; Size
0x1800b40e7  xor     edx, edx; Val
0x1800b40e9  lea     rcx, [rsp+208h+var_B0]; void *
0x1800b40f1  call    memset_0
0x1800b40f6  mov     [rsp+208h+var_30], r15b
0x1800b40fe  xor     eax, eax
0x1800b4100  mov     [rsp+208h+var_2F], ax
0x1800b4108  mov     [rsp+208h+var_2D], al
0x1800b410f  mov     [rsp+208h+var_2C], r15d
0x1800b4117  mov     [rsp+208h+var_28], r14
0x1800b411f  lea     rdx, [rsp+208h+var_1D8]
0x1800b4124  mov     rcx, rdi
0x1800b4127  call    ??4AppConnectionEstablishedNotificationData@AppPrioritizationManager@AppPrioritization@@QEAAAEAU012@$$QEAU012@@Z; AppPrioritization::AppPrioritizationManager::AppConnectionEstablishedNotificationData::operator=(AppPrioritization::AppPrioritizationManager::AppConnectionEstablishedNotificationData &&)
0x1800b412c  lea     rcx, [rsp+208h+var_1D8]; this
0x1800b4131  call    ??1AppIdentityNotificationData@AppPrioritizationManager@AppPrioritization@@QEAA@XZ; AppPrioritization::AppPrioritizationManager::AppIdentityNotificationData::~AppIdentityNotificationData(void)
0x1800b4136  mov     rcx, [rbx+48h]; pSid
0x1800b413a  test    rcx, rcx
0x1800b413d  jz      loc_1800B4446
0x1800b4143  call    cs:__imp_IsValidSid
0x1800b4149  test    eax, eax
0x1800b414b  jz      loc_1800B4446
0x1800b4151  mov     rcx, [rbx+48h]; pSid
0x1800b4155  call    cs:__imp_GetLengthSid
0x1800b415b  mov     esi, eax
0x1800b415d  test    eax, eax
0x1800b415f  jnz     short loc_1800B4187
0x1800b4161  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b4166  mov     eax, cs:dword_18013A120
0x1800b416c  cmp     eax, 2
0x1800b416f  jbe     short loc_1800B417D
0x1800b4171  lea     rdx, byte_18011AA1D
0x1800b4178  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800b417d  mov     eax, 57h ; 'W'
0x1800b4182  jmp     loc_1800B446B
0x1800b4187  mov     rdx, rsi; uBytes
0x1800b418a  mov     ecx, 40h ; '@'; uFlags
0x1800b418f  call    cs:__imp_LocalAlloc
0x1800b4195  mov     rdx, rax
0x1800b4198  lea     rcx, [rdi+60h]
0x1800b419c  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::reset(void *)
0x1800b41a1  mov     rax, [rdi+60h]
0x1800b41a5  test    rax, rax
0x1800b41a8  jz      loc_1800B4428
0x1800b41ae  mov     rdx, [rax]; pDestinationSid
0x1800b41b1  test    rdx, rdx
0x1800b41b4  jz      loc_1800B4428
0x1800b41ba  mov     r8, [rbx+48h]; pSourceSid
0x1800b41be  mov     ecx, esi; nDestinationSidLength
0x1800b41c0  call    cs:__imp_CopySid
0x1800b41c6  test    eax, eax
0x1800b41c8  jnz     short loc_1800B420B
0x1800b41ca  call    cs:__imp_GetLastError
0x1800b41d0  mov     ebx, eax
0x1800b41d2  mov     ecx, cs:dword_18013A120
0x1800b41d8  cmp     ecx, 2
0x1800b41db  jbe     short loc_1800B4204
0x1800b41dd  mov     [rsp+208h+arg_0], eax
0x1800b41e4  lea     rax, [rsp+208h+arg_0]
0x1800b41ec  mov     [rsp+208h+var_1E8], rax
0x1800b41f1  lea     rdx, byte_18011AA8F
0x1800b41f8  lea     rcx, dword_18013A120
0x1800b41ff  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800b4204  mov     eax, ebx
0x1800b4206  jmp     loc_1800B446B
0x1800b420b  lea     r14, dword_180103494
0x1800b4212  mov     rdx, r14
0x1800b4215  cmp     [rbx+30h], r15
0x1800b4219  cmovnz  rdx, [rbx+30h]
0x1800b421e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b4222  mov     r8, rsi
0x1800b4225  inc     r8
0x1800b4228  cmp     [rdx+r8*2], r15w
0x1800b422d  jnz     short loc_1800B4225
0x1800b422f  mov     rcx, rdi; Src
0x1800b4232  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b4237  mov     rdx, r14
0x1800b423a  cmp     [rbx+38h], r15
0x1800b423e  cmovnz  rdx, [rbx+38h]
0x1800b4243  mov     r8, rsi
0x1800b4246  inc     r8
0x1800b4249  cmp     [rdx+r8*2], r15w
0x1800b424e  jnz     short loc_1800B4246
0x1800b4250  lea     rcx, [rdi+20h]; Src
0x1800b4254  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b4259  cmp     [rbx+40h], r15
0x1800b425d  cmovnz  r14, [rbx+40h]
0x1800b4262  inc     rsi
0x1800b4265  cmp     [r14+rsi*2], r15w
0x1800b426a  jnz     short loc_1800B4262
0x1800b426c  lea     rcx, [rdi+40h]; Src
0x1800b4270  mov     r8, rsi
0x1800b4273  mov     rdx, r14
0x1800b4276  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b427b  cmp     [rbx+40h], r15
0x1800b427f  jnz     short loc_1800B4286
0x1800b4281  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b4286  mov     rax, [rbx+28h]
0x1800b428a  mov     [rdi+70h], rax
0x1800b428e  mov     rax, [rbx+18h]
0x1800b4292  mov     [rdi+78h], rax
0x1800b4296  mov     rax, [rbx+170h]
0x1800b429d  mov     [rdi+80h], rax
0x1800b42a4  cmp     [rbx+164h], r15d
0x1800b42ab  setnz   al
0x1800b42ae  mov     [rdi+88h], al
0x1800b42b4  cmp     [rbx+24h], r15d
0x1800b42b8  setnz   al
0x1800b42bb  mov     [rdi+89h], al
0x1800b42c1  cmp     [rbx+20h], r15d
0x1800b42c5  setnz   al
0x1800b42c8  mov     [rdi+8Ah], al
0x1800b42ce  mov     eax, [rbx+168h]
0x1800b42d4  mov     [rdi+8Ch], eax
0x1800b42da  mov     eax, [rbx+16Ch]
0x1800b42e0  mov     [rdi+90h], eax
0x1800b42e6  mov     eax, [rbx+15Ch]
0x1800b42ec  mov     [rdi+94h], eax
0x1800b42f2  mov     rax, [rbx+8]
0x1800b42f6  mov     [rdi+98h], rax
0x1800b42fd  movzx   eax, word ptr [rbx+10h]
0x1800b4301  mov     [rdi+0A0h], ax
0x1800b4308  mov     al, [rbx+12h]
0x1800b430b  mov     [rdi+0A2h], al
0x1800b4311  movups  xmm0, xmmword ptr [rbx+50h]
0x1800b4315  movups  xmmword ptr [rdi+0A8h], xmm0
0x1800b431c  movups  xmm1, xmmword ptr [rbx+60h]
0x1800b4320  movups  xmmword ptr [rdi+0B8h], xmm1
0x1800b4327  movups  xmm0, xmmword ptr [rbx+70h]
0x1800b432b  movups  xmmword ptr [rdi+0C8h], xmm0
0x1800b4332  movups  xmm1, xmmword ptr [rbx+80h]
0x1800b4339  movups  xmmword ptr [rdi+0D8h], xmm1
0x1800b4340  movups  xmm0, xmmword ptr [rbx+90h]
0x1800b4347  movups  xmmword ptr [rdi+0E8h], xmm0
0x1800b434e  movups  xmm1, xmmword ptr [rbx+0A0h]
0x1800b4355  movups  xmmword ptr [rdi+0F8h], xmm1
0x1800b435c  movups  xmm0, xmmword ptr [rbx+0B0h]
0x1800b4363  movups  xmmword ptr [rdi+108h], xmm0
0x1800b436a  movups  xmm1, xmmword ptr [rbx+0C0h]
0x1800b4371  movups  xmmword ptr [rdi+118h], xmm1
0x1800b4378  movups  xmm0, xmmword ptr [rbx+0D0h]
0x1800b437f  movups  xmmword ptr [rdi+128h], xmm0
0x1800b4386  movups  xmm1, xmmword ptr [rbx+0E0h]
0x1800b438d  movups  xmmword ptr [rdi+138h], xmm1
0x1800b4394  movups  xmm0, xmmword ptr [rbx+0F0h]
0x1800b439b  movups  xmmword ptr [rdi+148h], xmm0
0x1800b43a2  movups  xmm1, xmmword ptr [rbx+100h]
0x1800b43a9  movups  xmmword ptr [rdi+158h], xmm1
0x1800b43b0  movups  xmm0, xmmword ptr [rbx+110h]
0x1800b43b7  movups  xmmword ptr [rdi+168h], xmm0
0x1800b43be  movups  xmm1, xmmword ptr [rbx+120h]
0x1800b43c5  movups  xmmword ptr [rdi+178h], xmm1
0x1800b43cc  movups  xmm0, xmmword ptr [rbx+130h]
0x1800b43d3  movups  xmmword ptr [rdi+188h], xmm0
0x1800b43da  movups  xmm1, xmmword ptr [rbx+140h]
0x1800b43e1  movups  xmmword ptr [rdi+198h], xmm1
0x1800b43e8  mov     al, [rbx+150h]
0x1800b43ee  mov     [rdi+1A8h], al
0x1800b43f4  mov     eax, [rbx+158h]
0x1800b43fa  mov     [rdi+1B0h], eax
0x1800b4400  mov     al, [rbx+178h]
0x1800b4406  mov     [rdi+1B4h], al
0x1800b440c  mov     al, [rbx+179h]
0x1800b4412  mov     [rdi+1B5h], al
0x1800b4418  mov     eax, [rbx+154h]
0x1800b441e  mov     [rdi+1ACh], eax
0x1800b4424  xor     eax, eax
0x1800b4426  jmp     short loc_1800B446B
0x1800b4428  mov     eax, cs:dword_18013A120
0x1800b442e  cmp     eax, 2
0x1800b4431  jbe     short loc_1800B443F
0x1800b4433  lea     rdx, byte_18011A9BB
0x1800b443a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800b443f  mov     eax, 8
0x1800b4444  jmp     short loc_1800B446B
0x1800b4446  mov     eax, cs:dword_18013A120
0x1800b444c  cmp     eax, 2
0x1800b444f  jbe     short loc_1800B445D
0x1800b4451  lea     rdx, word_18011AB5A
0x1800b4458  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800b445d  mov     eax, 57h ; 'W'
0x1800b4462  jmp     short loc_1800B446B
0x1800b4464  mov     eax, [rsp+208h+arg_0]
0x1800b446b  lea     r11, [rsp+208h+var_18]
0x1800b4473  mov     rbx, [r11+28h]
0x1800b4477  mov     rsi, [r11+30h]
0x1800b447b  mov     rsp, r11
0x1800b447e  pop     r15
0x1800b4480  pop     r14
0x1800b4482  pop     rdi
0x1800b4483  retn
```
