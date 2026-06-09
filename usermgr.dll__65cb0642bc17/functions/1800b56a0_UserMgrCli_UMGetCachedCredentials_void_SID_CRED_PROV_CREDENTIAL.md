# UserMgrCli::UMGetCachedCredentials(void *,_SID *,_CRED_PROV_CREDENTIAL * *)

- ea: `0x1800b56a0`
- end: `0x1800b5982`
- name: `?UMGetCachedCredentials@UserMgrCli@@QEAAJPEAXPEAU_SID@@PEAPEAU_CRED_PROV_CREDENTIAL@@@Z`
- size: `738`
- prototype: `int(UserMgrCli *__hidden this, void *, struct _SID *, struct _CRED_PROV_CREDENTIAL **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b60a0`

## callees

- `0x180002ec8`
- `0x180008b70`
- `0x18000acdc`
- `0x18000c6d0`
- `0x180011490`
- `0x180012890`
- `0x18006f1c9`
- `0x1800b56a0`
- `0x1800b5d74`
- `0x1800de450`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800b584c`
- `msvcrt!memcpy_s` at `0x1800b586c`
- `msvcrt!memcpy_s` at `0x1800b584c`
- `msvcrt!memcpy_s` at `0x1800b586c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b581f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b581f`
- `ntdll!RtlEqualSid` at `0x1800b5803`
- `ntdll!RtlEqualSid` at `0x1800b5803`

## string_xrefs

- `0x1800b58e4`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b58fc`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5913`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b592a`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5941`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5958`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b596f`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserMgrCli::UMGetCachedCredentials(
        UserMgrCli *this,
        void *a2,
        struct _SID *a3,
        struct _CRED_PROV_CREDENTIAL **a4)
{
  _DWORD *v4; // rbp
  const struct _tlgProvider_t *v7; // rax
  int v8; // ecx
  void *v9; // rdx
  UserMgrCli *v10; // rcx
  int BasicCallerInformation; // eax
  char v12; // al
  _QWORD *v13; // rax
  _QWORD *v14; // rsi
  const struct _tlgProvider_t *v15; // rax
  int v16; // r8d
  int v17; // r9d
  __int64 result; // rax
  _DWORD *v19; // rbp
  const struct _tlgProvider_t *v20; // rax
  int v21; // ebx
  wil *v22; // rcx
  int v23; // r8d
  int v24; // r9d
  int v25; // [rsp+20h] [rbp-30h]
  int v26; // [rsp+50h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+288h] [rbp+238h]

  v4 = (_DWORD *)((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL);
  *(_QWORD *)(((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = a3;
  v7 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    v8 = 4 * a3->SubAuthorityCount + 8;
    *(_QWORD *)(((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL) + 0x200) = a3;
    *(_DWORD *)(((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL) + 0x208) = v8;
    *(_DWORD *)(((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20C) = 0;
    v25 = 3;
    tlgWriteTransfer_EventWriteTransfer(v7, &byte_18012902F, 0, 0);
  }
  memset_0(v4 + 16, 0, 0x1A0u);
  try
  {
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               v10,
                               v9,
                               (struct _BASIC_CALLER_INFORMATION *)(v4 + 16));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB13,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        v25);
    UserMgrCli::CheckApiRestrictionsForCaller(
      retaddr,
      (struct _BASIC_CALLER_INFORMATION *)(v4 + 16),
      (const struct _CALLER_RESTRICTIONS *)byte_1801135E8);
    *(_QWORD *)(((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = &g_userMgrCli;
    v12 = 1;
    *(_BYTE *)(((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 1;
    if ( dword_1801481B0 == -1
      || dword_1801481B0 != *(_DWORD *)(((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) )
    {
      v12 = 0;
    }
    if ( !v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB2E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x8000FFFFLL,
        v25);
    if ( !*(&pv + 1) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB2F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x8000FFFFLL,
        v25);
    if ( !pv )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB30,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x8000FFFFLL,
        v25);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB33,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        v25);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB34,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        v25);
    *a4 = 0;
    if ( *((_DWORD *)pv + 2) && RtlEqualSid(*(&pv + 1), a3) )
    {
      v13 = LocalAlloc(0x40u, (unsigned int)(*((_DWORD *)pv + 2) + 24));
      v14 = v13;
      if ( !v13 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB3D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)0x8007000ELL,
          v25);
      memcpy_s(v13, 0x18u, pv, 0x18u);
      v14[2] = v14 + 3;
      memcpy_s(v14 + 3, *((unsigned int *)v14 + 2), *((const void *const *)pv + 2), *((unsigned int *)pv + 2));
      *a4 = (struct _CRED_PROV_CREDENTIAL *)v14;
    }
    v15 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v15 > 5u )
    {
      *v4 = 0;
      *(_QWORD *)(((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)byte_180129065,
        v16,
        v17,
        (__int64)(v4 + 4),
        (unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL);
    }
    wil::details::lambda_call__lambda_9d0d295db5fa81eb7b082c03c41289f4___::reset(v4 + 6);
    result = 0;
  }
  catch ( ... )
  {
    v19 = (_DWORD *)((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL);
    v20 = UserMgrUserModelTelemetry::Provider();
    v21 = (int)v20;
    v22 = (wil *)*(unsigned int *)v20;
    if ( (unsigned int)v22 > 5 )
    {
      *v19 = wil::ResultFromCaughtException(v22);
      *(_QWORD *)(((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = *(_QWORD *)(((unsigned __int64)&v26
                                                                                     & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                    + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&byte_180128FD7,
        v23,
        v24,
        (__int64)(v19 + 2),
        (__int64)v19);
    }
    *v19 = wil::ResultFromCaughtException(v22);
    return *(unsigned int *)((unsigned __int64)&v26 & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return result;
}

```

## disassembly

```asm
0x1800b56a0  mov     [rsp-8+arg_0], rbx
0x1800b56a5  mov     [rsp-8+arg_8], rsi
0x1800b56aa  push    rbp
0x1800b56ab  push    rdi
0x1800b56ac  push    r14
0x1800b56ae  sub     rsp, 270h
0x1800b56b5  lea     rbp, [rsp+50h]
0x1800b56ba  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800b56be  mov     rax, cs:__security_cookie
0x1800b56c5  xor     rax, rsp
0x1800b56c8  mov     [rbp+230h+var_20], rax
0x1800b56cf  mov     r14, r9
0x1800b56d2  mov     rdi, r8
0x1800b56d5  mov     [rbp+230h+var_228], r8
0x1800b56d9  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b56de  mov     ecx, [rax]
0x1800b56e0  cmp     ecx, 5
0x1800b56e3  jbe     short loc_1800B5730
0x1800b56e5  movzx   ecx, byte ptr [rdi+1]
0x1800b56e9  lea     ecx, ds:8[rcx*4]
0x1800b56f0  mov     [rbp+230h+var_30], rdi
0x1800b56f7  mov     [rbp+230h+var_28], ecx
0x1800b56fd  xor     ebx, ebx
0x1800b56ff  mov     [rbp+230h+var_24], ebx
0x1800b5705  lea     rcx, [rbp+230h+var_50]
0x1800b570c  mov     [rsp+280h+var_258], rcx
0x1800b5711  mov     dword ptr [rsp+280h+var_260], 3
0x1800b5719  xor     r9d, r9d
0x1800b571c  xor     r8d, r8d
0x1800b571f  lea     rdx, byte_18012902F
0x1800b5726  mov     rcx, rax
0x1800b5729  call    _tlgWriteTransfer_EventWriteTransfer
0x1800b572e  jmp     short loc_1800B5732
0x1800b5730  xor     ebx, ebx
0x1800b5732  xor     edx, edx; Val
0x1800b5734  mov     r8d, 1A0h; Size
0x1800b573a  lea     rcx, [rbp+230h+var_1F0]; void *
0x1800b573e  call    memset_0
0x1800b5743  lea     r8, [rbp+230h+var_1F0]; struct _BASIC_CALLER_INFORMATION *
0x1800b5747  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x1800b574c  mov     rcx, [rsp+288h]; this
0x1800b5754  test    eax, eax
0x1800b5756  js      loc_1800B58E1
0x1800b575c  lea     r8, byte_1801135E8; struct _CALLER_RESTRICTIONS *
0x1800b5763  lea     rdx, [rbp+230h+var_1F0]; struct _BASIC_CALLER_INFORMATION *
0x1800b5767  call    ?CheckApiRestrictionsForCaller@UserMgrCli@@AEAAJPEAU_BASIC_CALLER_INFORMATION@@PEBU_CALLER_RESTRICTIONS@@@Z; UserMgrCli::CheckApiRestrictionsForCaller(_BASIC_CALLER_INFORMATION *,_CALLER_RESTRICTIONS const *)
0x1800b576c  lea     rax, ?g_userMgrCli@@3VUserMgrCli@@A; UserMgrCli g_userMgrCli
0x1800b5773  mov     [rbp+230h+var_218], rax
0x1800b5777  mov     al, 1
0x1800b5779  mov     [rbp+230h+var_210], al
0x1800b577c  mov     ecx, cs:dword_1801481B0
0x1800b5782  cmp     ecx, 0FFFFFFFFh
0x1800b5785  jz      short loc_1800B578C
0x1800b5787  cmp     ecx, [rbp+230h+var_1E8]
0x1800b578a  jz      short loc_1800B578E
0x1800b578c  mov     al, bl
0x1800b578e  mov     rcx, [rsp+288h]; this
0x1800b5796  test    al, al
0x1800b5798  jz      loc_1800B58F6
0x1800b579e  mov     rcx, [rsp+288h]; this
0x1800b57a6  cmp     qword ptr cs:pv+8, rbx
0x1800b57ad  jz      loc_1800B590D
0x1800b57b3  mov     rcx, [rsp+288h]; this
0x1800b57bb  cmp     qword ptr cs:pv, rbx
0x1800b57c2  jz      loc_1800B5924
0x1800b57c8  mov     rcx, [rsp+288h]; this
0x1800b57d0  test    r14, r14
0x1800b57d3  jz      loc_1800B593B
0x1800b57d9  mov     rcx, [rsp+288h]; this
0x1800b57e1  test    rdi, rdi
0x1800b57e4  jz      loc_1800B5952
0x1800b57ea  mov     [r14], rbx
0x1800b57ed  mov     rax, qword ptr cs:pv
0x1800b57f4  cmp     [rax+8], ebx
0x1800b57f7  jbe     short loc_1800B5875
0x1800b57f9  mov     rdx, rdi; Sid2
0x1800b57fc  mov     rcx, qword ptr cs:pv+8; Sid1
0x1800b5803  call    cs:__imp_RtlEqualSid
0x1800b5809  test    al, al
0x1800b580b  jz      short loc_1800B5875
0x1800b580d  mov     rax, qword ptr cs:pv
0x1800b5814  mov     edx, [rax+8]
0x1800b5817  add     edx, 18h; uBytes
0x1800b581a  mov     ecx, 40h ; '@'; uFlags
0x1800b581f  call    cs:__imp_LocalAlloc
0x1800b5825  mov     rsi, rax
0x1800b5828  mov     rcx, [rsp+288h]; this
0x1800b5830  test    rax, rax
0x1800b5833  jz      loc_1800B5969
0x1800b5839  mov     r9d, 18h; SourceSize
0x1800b583f  mov     r8, qword ptr cs:pv; Source
0x1800b5846  mov     edx, r9d; DestinationSize
0x1800b5849  mov     rcx, rsi; Destination
0x1800b584c  call    cs:__imp_memcpy_s
0x1800b5852  lea     rcx, [rsi+18h]; Destination
0x1800b5856  mov     [rsi+10h], rcx
0x1800b585a  mov     r8, qword ptr cs:pv
0x1800b5861  mov     r9d, [r8+8]; SourceSize
0x1800b5865  mov     edx, [rsi+8]; DestinationSize
0x1800b5868  mov     r8, [r8+10h]; Source
0x1800b586c  call    cs:__imp_memcpy_s
0x1800b5872  mov     [r14], rsi
0x1800b5875  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b587a  mov     ecx, [rax]
0x1800b587c  cmp     ecx, 5
0x1800b587f  jbe     short loc_1800B58AA
0x1800b5881  mov     [rbp+230h+var_230], ebx
0x1800b5884  mov     [rbp+230h+var_220], rdi
0x1800b5888  lea     rcx, [rbp+230h+var_230]
0x1800b588c  mov     [rsp+280h+var_258], rcx
0x1800b5891  lea     rcx, [rbp+230h+var_220]
0x1800b5895  mov     [rsp+280h+var_260], rcx
0x1800b589a  lea     rdx, byte_180129065
0x1800b58a1  mov     rcx, rax
0x1800b58a4  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<4> const &)
0x1800b58a9  nop
0x1800b58aa  lea     rcx, [rbp+230h+var_218]
0x1800b58ae  call    wil__details__lambda_call__lambda_9d0d295db5fa81eb7b082c03c41289f4_____reset
0x1800b58b3  xor     eax, eax
0x1800b58b5  jmp     short loc_1800B58BA
0x1800b58b7  mov     eax, [rbp+230h+var_230]
0x1800b58ba  mov     rcx, [rbp+230h+var_20]
0x1800b58c1  xor     rcx, rsp; StackCookie
0x1800b58c4  call    __security_check_cookie
0x1800b58c9  lea     r11, [rsp+280h+var_10]
0x1800b58d1  mov     rbx, [r11+20h]
0x1800b58d5  mov     rsi, [r11+28h]
0x1800b58d9  mov     rsp, r11
0x1800b58dc  pop     r14
0x1800b58de  pop     rdi
0x1800b58df  pop     rbp
0x1800b58e0  retn
0x1800b58e1  mov     r9d, eax; char *
0x1800b58e4  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b58eb  mov     edx, 0B13h; void *
0x1800b58f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b58f6  mov     r9d, 8000FFFFh; char *
0x1800b58fc  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5903  mov     edx, 0B2Eh; void *
0x1800b5908  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b590d  mov     r9d, 8000FFFFh; char *
0x1800b5913  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b591a  mov     edx, 0B2Fh; void *
0x1800b591f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5924  mov     r9d, 8000FFFFh; char *
0x1800b592a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5931  mov     edx, 0B30h; void *
0x1800b5936  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b593b  mov     r9d, 80070057h; char *
0x1800b5941  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5948  mov     edx, 0B33h; void *
0x1800b594d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5952  mov     r9d, 80070057h; char *
0x1800b5958  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b595f  mov     edx, 0B34h; void *
0x1800b5964  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5969  mov     r9d, 8007000Eh; char *
0x1800b596f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5976  mov     edx, 0B3Dh; void *
0x1800b597b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
