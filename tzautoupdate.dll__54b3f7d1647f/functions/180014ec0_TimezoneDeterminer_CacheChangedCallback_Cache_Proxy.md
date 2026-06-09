# TimezoneDeterminer::CacheChangedCallback(Cache::Proxy &)

- ea: `0x180014ec0`
- end: `0x1800154c0`
- name: `?CacheChangedCallback@TimezoneDeterminer@@QEAAXAEAVProxy@Cache@@@Z`
- size: `1536`
- prototype: `void __fastcall(TimezoneDeterminer *__hidden this, struct Cache::Proxy *)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800011e4`
- `0x18000166c`
- `0x180001ba4`
- `0x180001c98`
- `0x18000d240`
- `0x18000e968`
- `0x18000e9cc`
- `0x180010444`
- `0x180012df8`
- `0x1800144ec`
- `0x180014704`
- `0x180014e04`
- `0x180014ec0`
- `0x1800154c8`
- `0x18001562c`
- `0x1800156e0`
- `0x180015870`
- `0x180015938`
- `0x180015a08`
- `0x1800169f8`
- `0x18001b150`
- `0x18001d010`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180015029`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180015029`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800150a2`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800150a2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015078`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015078`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180015046`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180015046`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001501b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001501b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180014ff2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180014ff2`

## string_xrefs

- `0x18001503f`: `Security-System-Capability-dateAndTimeDeviceSettings`

## pseudocode

```c
void __fastcall TimezoneDeterminer::CacheChangedCallback(TimezoneDeterminer *this, struct Cache::Proxy *a2)
{
  _QWORD *v4; // rdi
  _QWORD *v5; // r14
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // r15
  bool v10; // r14
  unsigned __int64 v11; // r15
  __int64 v12; // rcx
  __int64 v13; // r8
  char v14; // di
  unsigned __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned __int16 *v19; // rbx
  const unsigned __int16 *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // r12d
  int v27; // r12d
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  unsigned __int16 *v36; // rbx
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // r8
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  _QWORD *v44; // rax
  const wchar_t *v45; // rax
  __int16 *v46; // rdx
  _QWORD *v47; // rax
  int v48; // ecx
  int v49; // r8d
  int v50; // r9d
  bool v51; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v52[7]; // [rsp+41h] [rbp-78h] BYREF
  void *DuplicateTokenHandle; // [rsp+48h] [rbp-71h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp-69h] BYREF
  DWORD ReturnLength[2]; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int16 *v56[2]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v57; // [rsp+70h] [rbp-49h]
  int v58; // [rsp+78h] [rbp-41h] BYREF
  int TokenInformation; // [rsp+7Ch] [rbp-3Dh] BYREF
  const wchar_t *v60; // [rsp+80h] [rbp-39h] BYREF
  _QWORD v61[2]; // [rsp+88h] [rbp-31h] BYREF
  _QWORD v62[4]; // [rsp+98h] [rbp-21h] BYREF
  _QWORD v63[3]; // [rsp+B8h] [rbp-1h] BYREF
  unsigned __int64 v64; // [rsp+D0h] [rbp+17h]

  LODWORD(v60) = 0;
  ReturnLength[0] = 0;
  if ( *(_BYTE *)(*((_QWORD *)a2 + 6) + 1LL) )
  {
    *(_OWORD *)v56 = 0;
    v57 = 0;
    v4 = (_QWORD *)*((_QWORD *)this + 1);
    v5 = (_QWORD *)*((_QWORD *)this + 2);
    v6 = 0;
    v7 = 0;
    while ( v4 != v5 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD *, struct Cache::Proxy *))(*(_QWORD *)*v4 + 8LL))(*v4, v62, a2);
      if ( v62[0] != v62[1] )
      {
        v9 = TimezoneDeterminer::IntersectSets(v8, v63, v56, v62);
        if ( v56 != (unsigned __int16 **)v9 )
        {
          std::vector<std::wstring>::_Tidy(v56);
          v7 = *(unsigned __int16 **)v9;
          v56[0] = *(unsigned __int16 **)v9;
          v6 = *(unsigned __int16 **)(v9 + 8);
          v56[1] = v6;
          v57 = *(_QWORD *)(v9 + 16);
          *(_QWORD *)v9 = 0;
          *(_QWORD *)(v9 + 8) = 0;
          *(_QWORD *)(v9 + 16) = 0;
        }
        std::vector<std::wstring>::_Tidy(v63);
        if ( (unsigned __int64)(((char *)v6 - (char *)v7) >> 5) <= 1 )
        {
          std::vector<std::wstring>::_Tidy(v62);
          break;
        }
      }
      std::vector<std::wstring>::_Tidy(v62);
      ++v4;
    }
    v10 = 0;
    v58 = 0;
    v11 = 0;
    v61[0] = 0;
    v61[1] = 0;
    wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(v61);
    if ( (int)UMgrEnumerateSessionUsers(&v58, v61) >= 0 && v58 )
    {
      v11 = *(_QWORD *)v61[0];
      TokenHandle = 0;
      if ( (int)UMgrQueryUserToken(v11, &TokenHandle) >= 0 )
      {
        if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() )
        {
          v51 = 0;
          if ( (int)CapabilityCheck(TokenHandle, L"Security-System-Capability-dateAndTimeDeviceSettings", &v51) >= 0 )
            v10 = v51;
        }
        else
        {
          TokenInformation = 0;
          ReturnLength[0] = 0;
          if ( GetTokenInformation(TokenHandle, TokenType, &TokenInformation, 4u, ReturnLength) )
          {
            if ( TokenInformation == 2 )
            {
              v10 = IsUserAdmin(TokenHandle);
            }
            else
            {
              DuplicateTokenHandle = 0;
              if ( DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
                v10 = IsUserAdmin(DuplicateTokenHandle);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
            }
          }
        }
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    v14 = *(_BYTE *)(*((_QWORD *)a2 + 8) + 1LL);
    v15 = ((char *)v6 - (char *)v7) >> 5;
    if ( v15 == 1 )
    {
      if ( *((_BYTE *)this + 56) )
      {
        if ( !(unsigned __int8)ContainsCurrentSystemTimezone(v56) )
        {
          v19 = v56[0];
          if ( v11 )
          {
            if ( v14 && !v10 )
            {
LABEL_35:
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::__private_IsEnabled(
                                      `wil::Feature<__WilFeatureTraits_Feature_Scenario58454712>::GetImpl'::`2'::impl,
                                      v16,
                                      v17,
                                      v18)
                && (unsigned int)dword_180030000 > 5 )
              {
                if ( (unsigned __int8)tlgKeywordOn(v21, 0x200000000000LL, v22) )
                {
                  v51 = v14;
                  v52[0] = v10;
                  DuplicateTokenHandle = (void *)0x1000000;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
                    v23,
                    (unsigned int)&dword_180029F14,
                    v24,
                    v25,
                    (__int64)&DuplicateTokenHandle,
                    (__int64)v52,
                    (__int64)&v51);
                }
              }
              goto LABEL_75;
            }
            if ( *((_QWORD *)v56[0] + 3) < 8u )
              v20 = v56[0];
            else
              v20 = *(const unsigned __int16 **)v56[0];
            SendTimezoneChangeToast(v20, v14, v11);
          }
          if ( !v14 )
            SystemTimezoneSetter(v19);
          goto LABEL_35;
        }
      }
      else
      {
        SystemTimezoneSetter(v7);
      }
LABEL_75:
      TimezoneDeterminer::SetStopServiceTimer(this, 0);
      wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(v61);
      std::vector<std::wstring>::_Tidy(v56);
      return;
    }
    if ( v15 <= 1 )
    {
      if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13) )
      {
        DuplicateTokenHandle = L"Found no possible timezone";
        TokenHandle = (HANDLE)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          v48,
          (unsigned int)&word_180029E16,
          v49,
          v50,
          (__int64)&TokenHandle,
          (__int64)&DuplicateTokenHandle);
      }
      goto LABEL_75;
    }
    v64 = 7;
    v63[2] = 0;
    LOWORD(v63[0]) = 0;
    v26 = (unsigned int)v60;
    while ( v7 != v6 )
    {
      v62[3] = 7;
      v62[2] = 0;
      LOWORD(v62[0]) = 0;
      v27 = v26 | 1;
      ReturnLength[0] = v27;
      v28 = std::char_traits<unsigned short>::length(L",");
      std::wstring::reserve(v62, *((_QWORD *)v7 + 2) + v28);
      v29 = std::char_traits<unsigned short>::length(L",");
      std::wstring::append(v62, v30, v29);
      std::wstring::append(v62, v7, 0, -1);
      std::wstring::append(v63, v62, 0, -1);
      v26 = v27 & 0xFFFFFFFE;
      LOBYTE(v31) = 1;
      std::wstring::_Tidy(v62, v31, 0);
      v7 += 16;
    }
    if ( (unsigned __int8)ContainsCurrentSystemTimezone(v56) )
    {
      if ( (unsigned int)dword_180030000 <= 5 || !(unsigned __int8)tlgKeywordOn(v33, 0x400000000000LL, v34) )
        goto LABEL_71;
      v47 = v63;
      if ( v64 >= 8 )
        v47 = (_QWORD *)v63[0];
      DuplicateTokenHandle = v47;
      TokenHandle = (HANDLE)(((char *)v56[1] - (char *)v56[0]) >> 5);
      v45 = L"More than one possible timezone - keeping current";
      v46 = (__int16 *)&unk_180029DB0;
      goto LABEL_70;
    }
    v36 = v56[0];
    if ( !*((_BYTE *)this + 56) )
    {
      SystemTimezoneSetter((_QWORD *)v56[0]);
LABEL_60:
      if ( (unsigned int)dword_180030000 <= 5 || !(unsigned __int8)tlgKeywordOn(v38, 0x400000000000LL, v39) )
        goto LABEL_71;
      v44 = v63;
      if ( v64 >= 8 )
        v44 = (_QWORD *)v63[0];
      DuplicateTokenHandle = v44;
      TokenHandle = (HANDLE)(((char *)v56[1] - (char *)v36) >> 5);
      v45 = L"Found more than one possible timezone - using first";
      v46 = &word_180029EAE;
LABEL_70:
      v60 = v45;
      *(_QWORD *)ReturnLength = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v41,
        (_DWORD)v46,
        v42,
        v43,
        (__int64)ReturnLength,
        (__int64)&v60,
        (__int64)&TokenHandle,
        (__int64)&DuplicateTokenHandle);
LABEL_71:
      LOBYTE(v32) = 1;
      std::wstring::_Tidy(v63, v32, 0);
      goto LABEL_75;
    }
    if ( v11 )
    {
      if ( v14 && !v10 )
      {
LABEL_55:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::__private_IsEnabled(
                                `wil::Feature<__WilFeatureTraits_Feature_Scenario58454712>::GetImpl'::`2'::impl,
                                v32,
                                v34,
                                v35)
          && (unsigned int)dword_180030000 > 5
          && (unsigned __int8)tlgKeywordOn(v38, 0x200000000000LL, v39) )
        {
          v52[0] = v14;
          v51 = v10;
          DuplicateTokenHandle = (void *)0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
            v38,
            (unsigned int)byte_180029E53,
            v39,
            v40,
            (__int64)&DuplicateTokenHandle,
            (__int64)&v51,
            (__int64)v52);
        }
        goto LABEL_60;
      }
      if ( *((_QWORD *)v56[0] + 3) < 8u )
        v37 = v56[0];
      else
        v37 = *(const unsigned __int16 **)v56[0];
      SendTimezoneChangeToast(v37, v14, v11);
    }
    if ( !v14 )
      SystemTimezoneSetter(v36);
    goto LABEL_55;
  }
}

```

## disassembly

```asm
0x180014ec0  mov     [rsp-8+arg_10], rbx
0x180014ec5  push    rbp
0x180014ec6  push    rsi
0x180014ec7  push    rdi
0x180014ec8  push    r12
0x180014eca  push    r13
0x180014ecc  push    r14
0x180014ece  push    r15
0x180014ed0  lea     rbp, [rsp-27h]
0x180014ed5  sub     rsp, 0E0h
0x180014edc  mov     rax, cs:__security_cookie
0x180014ee3  xor     rax, rsp
0x180014ee6  mov     [rbp+57h+var_38], rax
0x180014eea  mov     r12, rdx
0x180014eed  mov     r13, rcx
0x180014ef0  xor     eax, eax
0x180014ef2  mov     dword ptr [rbp+57h+var_90], eax
0x180014ef5  mov     [rbp+57h+var_B8], eax
0x180014ef8  mov     rax, [rdx+30h]
0x180014efc  cmp     byte ptr [rax+1], 0
0x180014f00  jz      loc_180015499
0x180014f06  xorps   xmm0, xmm0
0x180014f09  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x180014f0e  mov     [rbp+57h+var_A0], 0
0x180014f16  mov     rdi, [rcx+8]
0x180014f1a  mov     r14, [rcx+10h]
0x180014f1e  mov     rsi, [rbp+57h+var_B0+8]
0x180014f22  mov     rbx, [rbp+57h+var_B0]
0x180014f26  cmp     rdi, r14
0x180014f29  jz      loc_180014FCE
0x180014f2f  mov     rcx, [rdi]
0x180014f32  mov     rax, [rcx]
0x180014f35  mov     r8, r12
0x180014f38  lea     rdx, [rbp+57h+var_78]
0x180014f3c  mov     rax, [rax+8]
0x180014f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f45  nop
0x180014f46  mov     rax, [rbp+57h+var_70]
0x180014f4a  cmp     [rbp+57h+var_78], rax
0x180014f4e  jz      short loc_180014FB3
0x180014f50  lea     r9, [rbp+57h+var_78]
0x180014f54  lea     r8, [rbp+57h+var_B0]
0x180014f58  lea     rdx, [rbp+57h+var_58]
0x180014f5c  call    ?IntersectSets@TimezoneDeterminer@@AEAA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV23@0@Z; TimezoneDeterminer::IntersectSets(std::vector<std::wstring> const &,std::vector<std::wstring> const &)
0x180014f61  mov     r15, rax
0x180014f64  lea     rax, [rbp+57h+var_B0]
0x180014f68  cmp     rax, r15
0x180014f6b  jz      short loc_180014F9A
0x180014f6d  lea     rcx, [rbp+57h+var_B0]
0x180014f71  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180014f76  mov     rbx, [r15]
0x180014f79  mov     [rbp+57h+var_B0], rbx
0x180014f7d  mov     rsi, [r15+8]
0x180014f81  mov     [rbp+57h+var_B0+8], rsi
0x180014f85  mov     rax, [r15+10h]
0x180014f89  mov     [rbp+57h+var_A0], rax
0x180014f8d  xor     eax, eax
0x180014f8f  mov     [r15], rax
0x180014f92  mov     [r15+8], rax
0x180014f96  mov     [r15+10h], rax
0x180014f9a  lea     rcx, [rbp+57h+var_58]
0x180014f9e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180014fa3  mov     rax, rsi
0x180014fa6  sub     rax, rbx
0x180014fa9  sar     rax, 5
0x180014fad  cmp     rax, 1
0x180014fb1  jbe     short loc_180014FC5
0x180014fb3  lea     rcx, [rbp+57h+var_78]
0x180014fb7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180014fbc  add     rdi, 8
0x180014fc0  jmp     loc_180014F26
0x180014fc5  lea     rcx, [rbp+57h+var_78]
0x180014fc9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180014fce  xor     edi, edi
0x180014fd0  mov     r14b, dil
0x180014fd3  mov     [rbp+57h+var_98], edi
0x180014fd6  mov     r15d, edi
0x180014fd9  mov     [rbp+57h+var_88], rdi
0x180014fdd  mov     [rbp+57h+var_80], rdi
0x180014fe1  lea     rcx, [rbp+57h+var_88]
0x180014fe5  call    ?reset@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180014fea  lea     rdx, [rbp+57h+var_88]
0x180014fee  lea     rcx, [rbp+57h+var_98]
0x180014ff2  call    cs:__imp_UMgrEnumerateSessionUsers
0x180014ff8  test    eax, eax
0x180014ffa  js      loc_1800150CA
0x180015000  cmp     [rbp+57h+var_98], edi
0x180015003  jbe     loc_1800150CA
0x180015009  mov     rax, [rbp+57h+var_88]
0x18001500d  mov     r15, [rax]
0x180015010  mov     [rbp+57h+TokenHandle], rdi
0x180015014  lea     rdx, [rbp+57h+TokenHandle]
0x180015018  mov     rcx, r15
0x18001501b  call    cs:__imp_UMgrQueryUserToken
0x180015021  test    eax, eax
0x180015023  js      loc_1800150C1
0x180015029  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18001502f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180015033  test    al, al
0x180015035  jz      short loc_18001505B
0x180015037  mov     [rbp+57h+var_D0], dil
0x18001503b  lea     r8, [rbp+57h+var_D0]
0x18001503f  lea     rdx, aSecuritySystem; "Security-System-Capability-dateAndTimeD"...
0x180015046  call    cs:__imp_CapabilityCheck
0x18001504c  test    eax, eax
0x18001504e  js      short loc_1800150C1
0x180015050  cmp     [rbp+57h+var_D0], dil
0x180015054  jz      short loc_1800150C1
0x180015056  mov     r14b, 1
0x180015059  jmp     short loc_1800150C1
0x18001505b  mov     [rbp+57h+TokenInformation], edi
0x18001505e  mov     [rbp+57h+var_B8], edi
0x180015061  lea     rax, [rbp+57h+var_B8]
0x180015065  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18001506a  mov     r9d, 4; TokenInformationLength
0x180015070  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180015074  lea     edx, [r9+4]; TokenInformationClass
0x180015078  call    cs:__imp_GetTokenInformation
0x18001507e  test    eax, eax
0x180015080  jz      short loc_1800150C1
0x180015082  mov     edx, 2; ImpersonationLevel
0x180015087  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18001508b  cmp     [rbp+57h+TokenInformation], edx
0x18001508e  jnz     short loc_18001509A
0x180015090  call    ?IsUserAdmin@@YA_NPEAX@Z; IsUserAdmin(void *)
0x180015095  mov     r14b, al
0x180015098  jmp     short loc_1800150C1
0x18001509a  mov     [rbp+57h+DuplicateTokenHandle], rdi
0x18001509e  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800150a2  call    cs:__imp_DuplicateToken
0x1800150a8  test    eax, eax
0x1800150aa  jz      short loc_1800150B8
0x1800150ac  mov     rcx, [rbp+57h+DuplicateTokenHandle]; TokenHandle
0x1800150b0  call    ?IsUserAdmin@@YA_NPEAX@Z; IsUserAdmin(void *)
0x1800150b5  mov     r14b, al
0x1800150b8  lea     rcx, [rbp+57h+DuplicateTokenHandle]
0x1800150bc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800150c1  lea     rcx, [rbp+57h+TokenHandle]
0x1800150c5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800150ca  mov     rax, [r12+40h]
0x1800150cf  mov     dil, [rax+1]
0x1800150d3  mov     rax, rsi
0x1800150d6  sub     rax, rbx
0x1800150d9  sar     rax, 5
0x1800150dd  cmp     rax, 1
0x1800150e1  jnz     loc_1800151C0
0x1800150e7  cmp     byte ptr [r13+38h], 0
0x1800150ec  jz      loc_1800151B3
0x1800150f2  lea     rcx, [rbp+57h+var_B0]
0x1800150f6  call    ?ContainsCurrentSystemTimezone@@YA_NAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ContainsCurrentSystemTimezone(std::vector<std::wstring> const &)
0x1800150fb  test    al, al
0x1800150fd  jnz     loc_18001547B
0x180015103  mov     rbx, [rbp+57h+var_B0]
0x180015107  test    r15, r15
0x18001510a  jz      short loc_180015130
0x18001510c  test    dil, dil
0x18001510f  jz      short loc_180015116
0x180015111  test    r14b, r14b
0x180015114  jz      short loc_18001513D
0x180015116  cmp     qword ptr [rbx+18h], 8
0x18001511b  jb      short loc_180015122
0x18001511d  mov     rcx, [rbx]
0x180015120  jmp     short loc_180015125
0x180015122  mov     rcx, rbx; unsigned __int16 *
0x180015125  mov     r8, r15; unsigned __int64
0x180015128  mov     dl, dil; bool
0x18001512b  call    ?SendTimezoneChangeToast@@YAXPEBG_N_K@Z; SendTimezoneChangeToast(ushort const *,bool,unsigned __int64)
0x180015130  test    dil, dil
0x180015133  jnz     short loc_18001513D
0x180015135  mov     rcx, rbx
0x180015138  call    ?SystemTimezoneSetter@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemTimezoneSetter(std::wstring const &)
0x18001513d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Scenario58454712@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712> `wil::Feature<__WilFeatureTraits_Feature_Scenario58454712>::GetImpl(void)'::`2'::impl
0x180015144  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::__private_IsEnabled(void)
0x180015149  test    al, al
0x18001514b  jz      loc_18001547B
0x180015151  mov     eax, cs:dword_180030000
0x180015157  cmp     eax, 5
0x18001515a  jbe     loc_18001547B
0x180015160  mov     rdx, 200000000000h
0x18001516a  call    _tlgKeywordOn
0x18001516f  test    al, al
0x180015171  jz      loc_18001547B
0x180015177  mov     [rbp+57h+var_D0], dil
0x18001517b  mov     [rbp+57h+var_CF], r14b
0x18001517f  mov     [rbp+57h+DuplicateTokenHandle], 1000000h
0x180015187  lea     rax, [rbp+57h+var_D0]
0x18001518b  mov     [rsp+110h+var_E0], rax
0x180015190  lea     rax, [rbp+57h+var_CF]
0x180015194  mov     [rsp+110h+var_E8], rax
0x180015199  lea     rax, [rbp+57h+DuplicateTokenHandle]
0x18001519d  mov     [rsp+110h+ReturnLength], rax
0x1800151a2  lea     rdx, dword_180029F14
0x1800151a9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x1800151ae  jmp     loc_18001547B
0x1800151b3  mov     rcx, rbx
0x1800151b6  call    ?SystemTimezoneSetter@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemTimezoneSetter(std::wstring const &)
0x1800151bb  jmp     loc_18001547B
0x1800151c0  jbe     loc_18001542C
0x1800151c6  mov     [rbp+57h+var_40], 7
0x1800151ce  mov     [rbp+57h+var_48], 0
0x1800151d6  xor     eax, eax
0x1800151d8  mov     word ptr [rbp+57h+var_58], ax
0x1800151dc  mov     r12d, dword ptr [rbp+57h+var_90]
0x1800151e0  cmp     rbx, rsi
0x1800151e3  jz      loc_18001527D
0x1800151e9  mov     [rbp+57h+var_60], 7
0x1800151f1  mov     [rbp+57h+var_68], 0
0x1800151f9  xor     eax, eax
0x1800151fb  mov     word ptr [rbp+57h+var_78], ax
0x1800151ff  or      r12d, 1
0x180015203  mov     [rbp+57h+var_B8], r12d
0x180015207  lea     rcx, asc_180026EB8; ","
0x18001520e  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180015213  add     rax, [rbx+10h]
0x180015217  mov     rdx, rax
0x18001521a  lea     rcx, [rbp+57h+var_78]
0x18001521e  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x180015223  lea     rcx, asc_180026EB8; ","
0x18001522a  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001522f  mov     r8, rax
0x180015232  lea     rcx, [rbp+57h+var_78]
0x180015236  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001523b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001523f  xor     r8d, r8d
0x180015242  mov     rdx, rbx
0x180015245  lea     rcx, [rbp+57h+var_78]
0x180015249  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001524e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180015252  xor     r8d, r8d
0x180015255  lea     rdx, [rbp+57h+var_78]
0x180015259  lea     rcx, [rbp+57h+var_58]
0x18001525d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180015262  and     r12d, 0FFFFFFFEh
0x180015266  xor     r8d, r8d
0x180015269  mov     dl, 1
0x18001526b  lea     rcx, [rbp+57h+var_78]
0x18001526f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015274  add     rbx, 20h ; ' '
0x180015278  jmp     loc_1800151E0
0x18001527d  lea     rcx, [rbp+57h+var_B0]
0x180015281  call    ?ContainsCurrentSystemTimezone@@YA_NAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ContainsCurrentSystemTimezone(std::vector<std::wstring> const &)
0x180015286  test    al, al
0x180015288  jnz     loc_180015398
0x18001528e  mov     rbx, [rbp+57h+var_B0]
0x180015292  cmp     [r13+38h], al
0x180015296  jz      loc_180015339
0x18001529c  test    r15, r15
0x18001529f  jz      short loc_1800152C5
0x1800152a1  test    dil, dil
0x1800152a4  jz      short loc_1800152AB
0x1800152a6  test    r14b, r14b
0x1800152a9  jz      short loc_1800152D2
0x1800152ab  cmp     qword ptr [rbx+18h], 8
0x1800152b0  jb      short loc_1800152B7
0x1800152b2  mov     rcx, [rbx]
0x1800152b5  jmp     short loc_1800152BA
0x1800152b7  mov     rcx, rbx; unsigned __int16 *
0x1800152ba  mov     r8, r15; unsigned __int64
0x1800152bd  mov     dl, dil; bool
0x1800152c0  call    ?SendTimezoneChangeToast@@YAXPEBG_N_K@Z; SendTimezoneChangeToast(ushort const *,bool,unsigned __int64)
0x1800152c5  test    dil, dil
0x1800152c8  jnz     short loc_1800152D2
0x1800152ca  mov     rcx, rbx
0x1800152cd  call    ?SystemTimezoneSetter@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemTimezoneSetter(std::wstring const &)
0x1800152d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Scenario58454712@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712> `wil::Feature<__WilFeatureTraits_Feature_Scenario58454712>::GetImpl(void)'::`2'::impl
0x1800152d9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::__private_IsEnabled(void)
0x1800152de  test    al, al
0x1800152e0  jz      short loc_180015341
0x1800152e2  mov     eax, cs:dword_180030000
0x1800152e8  cmp     eax, 5
0x1800152eb  jbe     short loc_180015341
0x1800152ed  mov     rdx, 200000000000h
0x1800152f7  call    _tlgKeywordOn
0x1800152fc  test    al, al
0x1800152fe  jz      short loc_180015341
0x180015300  mov     [rbp+57h+var_CF], dil
0x180015304  mov     [rbp+57h+var_D0], r14b
0x180015308  mov     [rbp+57h+DuplicateTokenHandle], 1000000h
0x180015310  lea     rax, [rbp+57h+var_CF]
0x180015314  mov     [rsp+110h+var_E0], rax
0x180015319  lea     rax, [rbp+57h+var_D0]
0x18001531d  mov     [rsp+110h+var_E8], rax
0x180015322  lea     rax, [rbp+57h+DuplicateTokenHandle]
0x180015326  mov     [rsp+110h+ReturnLength], rax
0x18001532b  lea     rdx, byte_180029E53
0x180015332  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x180015337  jmp     short loc_180015341
0x180015339  mov     rcx, rbx
0x18001533c  call    ?SystemTimezoneSetter@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemTimezoneSetter(std::wstring const &)
0x180015341  mov     eax, cs:dword_180030000
0x180015347  cmp     eax, 5
0x18001534a  jbe     loc_18001541C
0x180015350  mov     rdx, 400000000000h
0x18001535a  call    _tlgKeywordOn
0x18001535f  test    al, al
0x180015361  jz      loc_18001541C
0x180015367  lea     rax, [rbp+57h+var_58]
0x18001536b  cmp     [rbp+57h+var_40], 8
0x180015370  cmovnb  rax, [rbp+57h+var_58]
0x180015375  mov     [rbp+57h+DuplicateTokenHandle], rax
  ... truncated ...
```
