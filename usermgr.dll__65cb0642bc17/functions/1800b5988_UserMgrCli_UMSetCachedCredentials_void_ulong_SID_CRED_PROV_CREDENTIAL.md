# UserMgrCli::UMSetCachedCredentials(void *,ulong,_SID *,_CRED_PROV_CREDENTIAL *)

- ea: `0x1800b5988`
- end: `0x1800b5cdd`
- name: `?UMSetCachedCredentials@UserMgrCli@@QEAAJPEAXKPEAU_SID@@PEAU_CRED_PROV_CREDENTIAL@@@Z`
- size: `853`
- prototype: `int(UserMgrCli *__hidden this, void *, unsigned int, struct _SID *, struct _CRED_PROV_CREDENTIAL *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800b60c0`

## callees

- `0x180002f50`
- `0x180008b70`
- `0x18000acdc`
- `0x18000c6d0`
- `0x180011490`
- `0x180012890`
- `0x18004e58c`
- `0x18006f1c9`
- `0x1800b5988`
- `0x1800de450`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800b5b30`
- `msvcrt!memcpy_s` at `0x1800b5b4a`
- `msvcrt!memcpy_s` at `0x1800b5b30`
- `msvcrt!memcpy_s` at `0x1800b5b4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5ae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5ae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5b07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5b07`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800b5b9b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800b5b9b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b5b5a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b5b5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5b74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5b74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5b63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5b63`

## string_xrefs

- `0x1800b5c2f`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5c46`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5c5d`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5c74`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5c8b`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5ca2`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5cb9`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5cca`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
__int64 __fastcall UserMgrCli::UMSetCachedCredentials(
        UserMgrCli *this,
        void *a2,
        int a3,
        struct _SID *a4,
        struct _CRED_PROV_CREDENTIAL *Source)
{
  _DWORD *v5; // rbp
  const struct _tlgProvider_t *v8; // rax
  int v9; // ecx
  void *v10; // rdx
  UserMgrCli *v11; // rcx
  int BasicCallerInformation; // eax
  _BYTE *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  _QWORD *v16; // rax
  _QWORD *v17; // r15
  DWORD LengthSid; // r15d
  HANDLE ProcessHeap; // rax
  void *v20; // rax
  const char *v21; // r9
  const struct _tlgProvider_t *v22; // rax
  int v23; // r8d
  int v24; // r9d
  __int64 result; // rax
  _DWORD *v26; // rbp
  _BYTE *v27; // rcx
  __int64 v28; // rax
  void *v29; // rbx
  HANDLE v30; // rax
  const struct _tlgProvider_t *v31; // rax
  int v32; // ebx
  wil *v33; // rcx
  int v34; // r8d
  int v35; // r9d
  int v36; // [rsp+20h] [rbp-40h]
  int v37; // [rsp+60h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+288h] [rbp+228h]

  v5 = (_DWORD *)((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL);
  *(_QWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = a4;
  v8 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v8 > 5u )
  {
    *v5 = a3;
    v9 = 4 * a4->SubAuthorityCount + 8;
    *(_QWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 0x1F0) = a4;
    *(_DWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 0x1F8) = v9;
    *(_DWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 0x1FC) = 0;
    *(_QWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E0) = (unsigned __int64)&v37
                                                                          & 0xFFFFFFFFFFFFFFE0uLL;
    *(_QWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E8) = 4;
    v36 = 4;
    tlgWriteTransfer_EventWriteTransfer(v8, &dword_1801291AC, 0, 0);
  }
  memset_0(v5 + 8, 0, 0x1A0u);
  try
  {
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               v11,
                               v10,
                               (struct _BASIC_CALLER_INFORMATION *)(v5 + 8));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAA6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        v36);
    UserMgrCli::CheckApiRestrictionsForCaller(
      retaddr,
      (struct _BASIC_CALLER_INFORMATION *)(v5 + 8),
      (const struct _CALLER_RESTRICTIONS *)byte_1801135E8);
    if ( (unsigned int)(a3 - 1) <= 0xFFFFFFFD )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAAA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        v36);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAAB,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        v36);
    if ( !Source )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAAC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        v36);
    v13 = pv;
    if ( pv )
    {
      if ( *((_DWORD *)pv + 2) )
      {
        v14 = *((unsigned int *)pv + 2) + 24LL;
        do
        {
          *v13++ = 0;
          --v14;
        }
        while ( v14 );
        v13 = pv;
      }
      CoTaskMemFree(v13);
      pv = 0;
    }
    v15 = *((_DWORD *)Source + 2);
    if ( !v15 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAC2,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        v36);
    v16 = CoTaskMemAlloc((unsigned int)(v15 + 24));
    v17 = v16;
    if ( !v16 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAC6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x8007000ELL,
        v36);
    memcpy_s(v16, 0x18u, Source, 0x18u);
    v17[2] = v17 + 3;
    memcpy_s(v17 + 3, *((unsigned int *)v17 + 2), *((const void *const *)Source + 2), *((unsigned int *)Source + 2));
    pv = v17;
    LengthSid = GetLengthSid(a4);
    ProcessHeap = GetProcessHeap();
    v20 = HeapAlloc(ProcessHeap, 8u, LengthSid);
    *(&pv + 1) = v20;
    if ( !v20 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAD2,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x8007000ELL,
        v36);
    if ( !CopySid(LengthSid, v20, a4) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xAD4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v21);
    dword_1801481B0 = a3;
    v22 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v22 > 5u )
    {
      *v5 = 0;
      *(_QWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = a4;
      *(_DWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>>(
        (_DWORD)v22,
        (unsigned int)word_1801290AA,
        v23,
        v24,
        (__int64)(v5 + 1),
        (__int64)(v5 + 4),
        (unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL);
    }
    result = 0;
  }
  catch ( ... )
  {
    v26 = (_DWORD *)((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL);
    v27 = pv;
    if ( pv )
    {
      if ( *((_DWORD *)pv + 2) )
      {
        v28 = *((unsigned int *)pv + 2) + 24LL;
        if ( *((_DWORD *)pv + 2) != -24 )
        {
          do
          {
            *v27++ = 0;
            --v28;
          }
          while ( v28 );
          v27 = pv;
        }
      }
      CoTaskMemFree(v27);
      pv = 0;
    }
    v29 = *(&pv + 1);
    if ( *(&pv + 1) )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v29);
      *(&pv + 1) = 0;
    }
    v31 = UserMgrUserModelTelemetry::Provider();
    v32 = (int)v31;
    v33 = (wil *)*(unsigned int *)v31;
    if ( (unsigned int)v33 > 5 )
    {
      *(_DWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = wil::ResultFromCaughtException(v33);
      *(_QWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = *(_QWORD *)(((unsigned __int64)&v37
                                                                                     & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                    + 8);
      *v26 = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>>(
        v32,
        (unsigned int)&unk_180129100,
        v34,
        v35,
        (__int64)v26,
        (__int64)(v26 + 2),
        (__int64)(v26 + 1));
    }
    *(_DWORD *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = wil::ResultFromCaughtException(v33);
    return *(unsigned int *)(((unsigned __int64)&v37 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
  }
  return result;
}

```

## disassembly

```asm
0x1800b5988  mov     [rsp-8+arg_0], rbx
0x1800b598d  mov     [rsp-8+arg_8], rsi
0x1800b5992  mov     [rsp-8+arg_10], r8d
0x1800b5997  push    rbp
0x1800b5998  push    r14
0x1800b599a  push    r15
0x1800b599c  sub     rsp, 270h
0x1800b59a3  lea     rbp, [rsp+60h]
0x1800b59a8  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800b59ac  mov     rax, cs:__security_cookie
0x1800b59b3  xor     rax, rsp
0x1800b59b6  mov     [rbp+220h+var_20], rax
0x1800b59bd  mov     rsi, r9
0x1800b59c0  mov     r14d, r8d
0x1800b59c3  mov     [rbp+220h+var_218], r9
0x1800b59c7  mov     rbx, [rsp+280h+Source]
0x1800b59cf  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b59d4  mov     ecx, [rax]
0x1800b59d6  cmp     ecx, 5
0x1800b59d9  jbe     short loc_1800B5A3D
0x1800b59db  mov     [rbp+220h+var_220], r14d
0x1800b59df  movzx   ecx, byte ptr [rsi+1]
0x1800b59e3  lea     ecx, ds:8[rcx*4]
0x1800b59ea  mov     [rbp+220h+var_30], rsi
0x1800b59f1  mov     [rbp+220h+var_28], ecx
0x1800b59f7  mov     [rbp+220h+var_24], 0
0x1800b5a01  lea     rcx, [rbp+220h+var_220]
0x1800b5a05  mov     [rbp+220h+var_40], rcx
0x1800b5a0c  mov     edx, 4
0x1800b5a11  mov     [rbp+220h+var_38], rdx
0x1800b5a18  lea     rcx, [rbp+220h+var_60]
0x1800b5a1f  mov     [rsp+280h+var_258], rcx
0x1800b5a24  mov     [rsp+280h+var_260], edx; int
0x1800b5a28  xor     r9d, r9d
0x1800b5a2b  xor     r8d, r8d
0x1800b5a2e  lea     rdx, dword_1801291AC
0x1800b5a35  mov     rcx, rax
0x1800b5a38  call    _tlgWriteTransfer_EventWriteTransfer
0x1800b5a3d  xor     edx, edx; Val
0x1800b5a3f  mov     r8d, 1A0h; Size
0x1800b5a45  lea     rcx, [rbp+220h+var_200]; void *
0x1800b5a49  call    memset_0
0x1800b5a4e  nop
0x1800b5a4f  lea     r8, [rbp+220h+var_200]; struct _BASIC_CALLER_INFORMATION *
0x1800b5a53  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x1800b5a58  mov     rcx, [rsp+288h]; this
0x1800b5a60  test    eax, eax
0x1800b5a62  js      loc_1800B5C2C
0x1800b5a68  lea     r8, byte_1801135E8; struct _CALLER_RESTRICTIONS *
0x1800b5a6f  lea     rdx, [rbp+220h+var_200]; struct _BASIC_CALLER_INFORMATION *
0x1800b5a73  call    ?CheckApiRestrictionsForCaller@UserMgrCli@@AEAAJPEAU_BASIC_CALLER_INFORMATION@@PEBU_CALLER_RESTRICTIONS@@@Z; UserMgrCli::CheckApiRestrictionsForCaller(_BASIC_CALLER_INFORMATION *,_CALLER_RESTRICTIONS const *)
0x1800b5a78  lea     eax, [r14-1]
0x1800b5a7c  cmp     eax, 0FFFFFFFDh
0x1800b5a7f  setbe   al
0x1800b5a82  mov     rcx, [rsp+288h]; this
0x1800b5a8a  test    al, al
0x1800b5a8c  jnz     loc_1800B5C40
0x1800b5a92  mov     rcx, [rsp+288h]; this
0x1800b5a9a  test    rsi, rsi
0x1800b5a9d  jz      loc_1800B5C57
0x1800b5aa3  mov     rcx, [rsp+288h]; this
0x1800b5aab  test    rbx, rbx
0x1800b5aae  jz      loc_1800B5C6E
0x1800b5ab4  mov     rcx, qword ptr cs:pv
0x1800b5abb  test    rcx, rcx
0x1800b5abe  jz      short loc_1800B5AF1
0x1800b5ac0  cmp     dword ptr [rcx+8], 0
0x1800b5ac4  jbe     short loc_1800B5AE0
0x1800b5ac6  mov     eax, [rcx+8]
0x1800b5ac9  add     rax, 18h
0x1800b5acd  mov     byte ptr [rcx], 0
0x1800b5ad0  inc     rcx
0x1800b5ad3  sub     rax, 1
0x1800b5ad7  jnz     short loc_1800B5ACD
0x1800b5ad9  mov     rcx, qword ptr cs:pv; pv
0x1800b5ae0  call    cs:__imp_CoTaskMemFree
0x1800b5ae6  mov     qword ptr cs:pv, 0
0x1800b5af1  mov     eax, [rbx+8]
0x1800b5af4  mov     rcx, [rsp+288h]; this
0x1800b5afc  test    eax, eax
0x1800b5afe  jz      loc_1800B5C85
0x1800b5b04  lea     ecx, [rax+18h]; cb
0x1800b5b07  call    cs:__imp_CoTaskMemAlloc
0x1800b5b0d  mov     r15, rax
0x1800b5b10  mov     rcx, [rsp+288h]; this
0x1800b5b18  test    rax, rax
0x1800b5b1b  jz      loc_1800B5C9C
0x1800b5b21  mov     r9d, 18h; SourceSize
0x1800b5b27  mov     r8, rbx; Source
0x1800b5b2a  mov     edx, r9d; DestinationSize
0x1800b5b2d  mov     rcx, r15; Destination
0x1800b5b30  call    cs:__imp_memcpy_s
0x1800b5b36  lea     rcx, [r15+18h]; Destination
0x1800b5b3a  mov     [r15+10h], rcx
0x1800b5b3e  mov     r9d, [rbx+8]; SourceSize
0x1800b5b42  mov     edx, [r15+8]; DestinationSize
0x1800b5b46  mov     r8, [rbx+10h]; Source
0x1800b5b4a  call    cs:__imp_memcpy_s
0x1800b5b50  mov     qword ptr cs:pv, r15
0x1800b5b57  mov     rcx, rsi; pSid
0x1800b5b5a  call    cs:__imp_GetLengthSid
0x1800b5b60  mov     r15d, eax
0x1800b5b63  call    cs:__imp_GetProcessHeap
0x1800b5b69  mov     rcx, rax; hHeap
0x1800b5b6c  mov     r8d, r15d; dwBytes
0x1800b5b6f  mov     edx, 8; dwFlags
0x1800b5b74  call    cs:__imp_HeapAlloc
0x1800b5b7a  mov     qword ptr cs:pv+8, rax
0x1800b5b81  mov     rcx, [rsp+288h]; this
0x1800b5b89  test    rax, rax
0x1800b5b8c  jz      loc_1800B5CB3
0x1800b5b92  mov     r8, rsi; pSourceSid
0x1800b5b95  mov     rdx, rax; pDestinationSid
0x1800b5b98  mov     ecx, r15d; nDestinationSidLength
0x1800b5b9b  call    cs:__imp_CopySid
0x1800b5ba1  mov     rcx, [rsp+288h]; this
0x1800b5ba9  test    eax, eax
0x1800b5bab  jz      loc_1800B5CCA
0x1800b5bb1  mov     cs:dword_1801481B0, r14d
0x1800b5bb8  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b5bbd  mov     ecx, [rax]
0x1800b5bbf  cmp     ecx, 5
0x1800b5bc2  jbe     short loc_1800B5BFD
0x1800b5bc4  mov     [rbp+220h+var_220], 0
0x1800b5bcb  mov     [rbp+220h+var_210], rsi
0x1800b5bcf  mov     [rbp+220h+var_21C], r14d
0x1800b5bd3  lea     rcx, [rbp+220h+var_220]
0x1800b5bd7  mov     [rsp+280h+var_250], rcx
0x1800b5bdc  lea     rcx, [rbp+220h+var_210]
0x1800b5be0  mov     [rsp+280h+var_258], rcx
0x1800b5be5  lea     rcx, [rbp+220h+var_21C]
0x1800b5be9  mov     qword ptr [rsp+280h+var_260], rcx
0x1800b5bee  lea     rdx, word_1801290AA
0x1800b5bf5  mov     rcx, rax
0x1800b5bf8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSid@U_SID@@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSid@U_SID@@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<4> const &)
0x1800b5bfd  xor     eax, eax
0x1800b5bff  jmp     short loc_1800B5C04
0x1800b5c01  mov     eax, [rbp+220h+var_21C]
0x1800b5c04  mov     rcx, [rbp+220h+var_20]
0x1800b5c0b  xor     rcx, rsp; StackCookie
0x1800b5c0e  call    __security_check_cookie
0x1800b5c13  lea     r11, [rsp+280h+var_10]
0x1800b5c1b  mov     rbx, [r11+20h]
0x1800b5c1f  mov     rsi, [r11+28h]
0x1800b5c23  mov     rsp, r11
0x1800b5c26  pop     r15
0x1800b5c28  pop     r14
0x1800b5c2a  pop     rbp
0x1800b5c2b  retn
0x1800b5c2c  mov     r9d, eax; char *
0x1800b5c2f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5c36  mov     edx, 0AA6h; void *
0x1800b5c3b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5c40  mov     r9d, 80070057h; char *
0x1800b5c46  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5c4d  mov     edx, 0AAAh; void *
0x1800b5c52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5c57  mov     r9d, 80070057h; char *
0x1800b5c5d  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5c64  mov     edx, 0AABh; void *
0x1800b5c69  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5c6e  mov     r9d, 80070057h; char *
0x1800b5c74  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5c7b  mov     edx, 0AACh; void *
0x1800b5c80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5c85  mov     r9d, 80070057h; char *
0x1800b5c8b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5c92  mov     edx, 0AC2h; void *
0x1800b5c97  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5c9c  mov     r9d, 8007000Eh; char *
0x1800b5ca2  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5ca9  mov     edx, 0AC6h; void *
0x1800b5cae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5cb3  mov     r9d, 8007000Eh; char *
0x1800b5cb9  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5cc0  mov     edx, 0AD2h; void *
0x1800b5cc5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5cca  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5cd1  mov     edx, 0AD4h; void *
0x1800b5cd6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
