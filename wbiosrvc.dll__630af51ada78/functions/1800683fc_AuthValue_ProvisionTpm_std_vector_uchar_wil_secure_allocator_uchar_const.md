# AuthValue::ProvisionTpm(std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x1800683fc`
- end: `0x180068720`
- name: `?ProvisionTpm@AuthValue@@QEAAJAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z`
- size: `804`
- prototype: `__int64 __fastcall(AuthValue *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800533f8`

## callees

- `0x180011d90`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x180017658`
- `0x18003a2e8`
- `0x18003a39c`
- `0x18003f2dc`
- `0x18003f80c`
- `0x18005388c`
- `0x1800538d4`
- `0x180061fdc`
- `0x180063760`
- `0x1800683fc`
- `0x180068728`
- `0x180068780`
- `0x1800687a8`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068662`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068662`
- `RPCRT4!UuidCreate` at `0x180068478`
- `RPCRT4!UuidCreate` at `0x180068478`

## string_xrefs

- `0x180068453`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x1800684a9`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x1800684fe`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x18006853e`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180068566`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x18006858d`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x1800685ac`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x1800685d6`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x18006861f`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180068677`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x1800686a3`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthValue::ProvisionTpm(HKEY *this, __int64 a2)
{
  __int64 result; // rax
  int v6; // eax
  unsigned int v7; // edi
  const char *v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // eax
  unsigned int v13; // edi
  enum TpmPolicySession::TpmState *v14; // rdx
  int TpmState; // eax
  unsigned int v16; // r9d
  int v17; // eax
  int v18; // edi
  int v19; // eax
  int v20; // eax
  int v21; // eax
  const BYTE *v22; // rax
  DWORD cbData; // edx
  unsigned int v24; // eax
  unsigned int v25; // edi
  int v26; // eax
  int lpData; // [rsp+20h] [rbp-78h]
  int lpDataa; // [rsp+20h] [rbp-78h]
  int lpDatab; // [rsp+20h] [rbp-78h]
  unsigned int lpDatac; // [rsp+20h] [rbp-78h]
  int lpDatad; // [rsp+20h] [rbp-78h]
  int v32; // [rsp+30h] [rbp-68h] BYREF
  NCRYPT_HANDLE hObject[4]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v34[16]; // [rsp+58h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+78h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( !TpmPolicySession::IsSupportedTpm20Present((TpmPolicySession *)this) )
    return 2147942450LL;
  try
  {
    v6 = AuthValue::DeleteTpmKey((AuthValue *)this);
    v7 = v6;
    if ( v6 >= 0 )
    {
      Uuid = 0;
      UuidCreate(&Uuid);
      std::wstring::wstring(v34, v9, v10, v11);
      v12 = CWinBioUuid::ToString(&Uuid, v34);
      v13 = v12;
      if ( v12 >= 0 )
      {
        TpmHmacKey::TpmHmacKey((unsigned int)hObject);
        v32 = -1;
        TpmState = TpmPolicySession::GetTpmState((TpmPolicySession *)&v32, v14);
        if ( TpmState < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x171,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
            (const char *)(unsigned int)TpmState,
            lpData);
        if ( v32 == -1 )
        {
          v17 = TpmPolicySession::TestTpmSupport(
                  hObject[0],
                  *(TpmPolicySession **)a2,
                  *(_DWORD *)(a2 + 8) - *(_DWORD *)a2,
                  v16);
          v18 = v17;
          if ( v17 >= 0 )
            v18 = 0;
          else
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2CD,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
              (const char *)(unsigned int)v17,
              lpData);
          if ( v18 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x176,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
              (const char *)(unsigned int)v18,
              lpData);
            v19 = TpmPolicySession::SetTpmState(0);
            if ( v19 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x17B,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
                (const char *)(unsigned int)v19,
                lpDataa);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x17C,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
              (const char *)0x80070032LL,
              lpDataa);
            v20 = TpmHmacKey::Delete((TpmHmacKey *)hObject);
            if ( v20 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x16D,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
                (const char *)(unsigned int)v20,
                lpDatab);
            TpmHmacKey::~TpmHmacKey((TpmHmacKey *)hObject);
            std::wstring::_Tidy_deallocate(v34);
            return 2147942450LL;
          }
          v21 = TpmPolicySession::SetTpmState(1);
          if ( v21 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x182,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
              (const char *)(unsigned int)v21,
              lpData);
        }
        v22 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
        v24 = RegSetValueExW(this[4], L"TpmKeyName", 0, 1u, v22, cbData);
        if ( v24 )
        {
          v25 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x18D,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
                  (const char *)v24,
                  lpDatac);
          v26 = TpmHmacKey::Delete((TpmHmacKey *)hObject);
          if ( v26 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x16D,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
              (const char *)(unsigned int)v26,
              lpDatad);
          TpmHmacKey::~TpmHmacKey((TpmHmacKey *)hObject);
          std::wstring::_Tidy_deallocate(v34);
          return v25;
        }
        else
        {
          std::wstring::operator=(this + 11, v34);
          TpmHmacKey::~TpmHmacKey((TpmHmacKey *)hObject);
          std::wstring::_Tidy_deallocate(v34);
          return 0;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
        (const char *)(unsigned int)v12,
        lpData);
      std::wstring::_Tidy_deallocate(v34);
      result = v13;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15D,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
        (const char *)(unsigned int)v6,
        lpData);
      result = v7;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x193,
                           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800683fc  mov     [rsp+arg_10], rsi
0x180068401  mov     [rsp+arg_18], rdi
0x180068406  push    r14
0x180068408  sub     rsp, 90h
0x18006840f  mov     rax, cs:__security_cookie
0x180068416  xor     rax, rsp
0x180068419  mov     [rsp+98h+var_10], rax
0x180068421  mov     r14, rdx
0x180068424  mov     rsi, rcx
0x180068427  call    ?IsSupportedTpm20Present@TpmPolicySession@@YA_NXZ; TpmPolicySession::IsSupportedTpm20Present(void)
0x18006842c  test    al, al
0x18006842e  jnz     short loc_18006843A
0x180068430  mov     eax, 80070032h
0x180068435  jmp     loc_1800686F9
0x18006843a  mov     rcx, rsi; this
0x18006843d  call    ?DeleteTpmKey@AuthValue@@QEAAJXZ; AuthValue::DeleteTpmKey(void)
0x180068442  mov     edi, eax
0x180068444  test    eax, eax
0x180068446  jns     short loc_18006846B
0x180068448  mov     rcx, [rsp+98h]; this
0x180068450  mov     r9d, eax; char *
0x180068453  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x18006845a  mov     edx, 15Dh; void *
0x18006845f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068464  mov     eax, edi
0x180068466  jmp     loc_1800686F9
0x18006846b  xorps   xmm0, xmm0
0x18006846e  movups  xmmword ptr [rsp+98h+Uuid.Data1], xmm0
0x180068473  lea     rcx, [rsp+98h+Uuid]; Uuid
0x180068478  call    cs:__imp_UuidCreate
0x18006847e  lea     rcx, [rsp+98h+var_40]
0x180068483  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180068488  nop
0x180068489  lea     rdx, [rsp+98h+var_40]
0x18006848e  lea     rcx, [rsp+98h+Uuid]
0x180068493  call    ?ToString@CWinBioUuid@@QEBAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CWinBioUuid::ToString(std::wstring *)
0x180068498  mov     edi, eax
0x18006849a  test    eax, eax
0x18006849c  jns     short loc_1800684CC
0x18006849e  mov     rcx, [rsp+98h]; this
0x1800684a6  mov     r9d, eax; char *
0x1800684a9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x1800684b0  mov     edx, 165h; void *
0x1800684b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800684ba  nop
0x1800684bb  lea     rcx, [rsp+98h+var_40]
0x1800684c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800684c5  mov     eax, edi
0x1800684c7  jmp     loc_1800686F9
0x1800684cc  mov     r8, r14
0x1800684cf  lea     rdx, [rsp+98h+var_40]
0x1800684d4  lea     rcx, [rsp+98h+hObject]; unsigned int
0x1800684d9  call    ??0TpmHmacKey@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@EU?$secure_allocator@E@wil@@@2@@Z; TpmHmacKey::TpmHmacKey(std::wstring const &,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x1800684de  or      edi, 0FFFFFFFFh
0x1800684e1  mov     [rsp+98h+var_68], edi
0x1800684e5  lea     rcx, [rsp+98h+var_68]; this
0x1800684ea  call    ?GetTpmState@TpmPolicySession@@YAJPEAW4TpmState@1@@Z; TpmPolicySession::GetTpmState(TpmPolicySession::TpmState *)
0x1800684ef  mov     rcx, [rsp+98h]; this
0x1800684f7  test    eax, eax
0x1800684f9  jns     short loc_18006850F
0x1800684fb  mov     r9d, eax; char *
0x1800684fe  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180068505  mov     edx, 171h; void *
0x18006850a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006850f  cmp     [rsp+98h+var_68], edi
0x180068513  jnz     loc_180068630
0x180068519  mov     r8d, [r14+8]
0x18006851d  sub     r8d, [r14]; cbSecret
0x180068520  mov     rdx, [r14]; this
0x180068523  mov     rcx, [rsp+98h+hObject]; hObject
0x180068528  call    ?TestTpmSupport@TpmPolicySession@@YAJ_KPEBEK@Z; TpmPolicySession::TestTpmSupport(unsigned __int64,uchar const *,ulong)
0x18006852d  mov     edi, eax
0x18006852f  test    eax, eax
0x180068531  jns     short loc_180068551
0x180068533  mov     rcx, [rsp+98h]; this
0x18006853b  mov     r9d, eax; char *
0x18006853e  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180068545  mov     edx, 2CDh; void *
0x18006854a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006854f  jmp     short loc_180068553
0x180068551  xor     edi, edi
0x180068553  mov     rcx, [rsp+98h]; this
0x18006855b  test    edi, edi
0x18006855d  jns     loc_180068606
0x180068563  mov     r9d, edi; char *
0x180068566  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x18006856d  mov     edx, 176h; void *
0x180068572  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180068577  xor     ecx, ecx
0x180068579  call    ?SetTpmState@TpmPolicySession@@YAJW4TpmState@1@@Z; TpmPolicySession::SetTpmState(TpmPolicySession::TpmState)
0x18006857e  mov     rcx, [rsp+98h]; this
0x180068586  test    eax, eax
0x180068588  jns     short loc_18006859E
0x18006858a  mov     r9d, eax; char *
0x18006858d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180068594  mov     edx, 17Bh; void *
0x180068599  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006859e  mov     rcx, [rsp+98h]; this
0x1800685a6  mov     r9d, 80070032h; char *
0x1800685ac  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x1800685b3  mov     edx, 17Ch; void *
0x1800685b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800685bd  lea     rcx, [rsp+98h+hObject]; this
0x1800685c2  call    ?Delete@TpmHmacKey@@AEAAJXZ; TpmHmacKey::Delete(void)
0x1800685c7  mov     rcx, [rsp+98h]; this
0x1800685cf  test    eax, eax
0x1800685d1  jns     short loc_1800685E7
0x1800685d3  mov     r9d, eax; char *
0x1800685d6  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x1800685dd  mov     edx, 16Dh; void *
0x1800685e2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800685e7  lea     rcx, [rsp+98h+hObject]; this
0x1800685ec  call    ??1TpmHmacKey@@QEAA@XZ; TpmHmacKey::~TpmHmacKey(void)
0x1800685f1  nop
0x1800685f2  lea     rcx, [rsp+98h+var_40]
0x1800685f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800685fc  mov     eax, 80070032h
0x180068601  jmp     loc_1800686F9
0x180068606  mov     ecx, 1
0x18006860b  call    ?SetTpmState@TpmPolicySession@@YAJW4TpmState@1@@Z; TpmPolicySession::SetTpmState(TpmPolicySession::TpmState)
0x180068610  mov     rcx, [rsp+98h]; this
0x180068618  test    eax, eax
0x18006861a  jns     short loc_180068630
0x18006861c  mov     r9d, eax; char *
0x18006861f  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180068626  mov     edx, 182h; void *
0x18006862b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180068630  mov     eax, [rsp+98h+var_30]
0x180068634  lea     edx, ds:2[rax*2]
0x18006863b  lea     rcx, [rsp+98h+var_40]
0x180068640  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068645  mov     [rsp+98h+cbData], edx; cbData
0x180068649  mov     [rsp+98h+lpData], rax; int
0x18006864e  mov     r9d, 1; dwType
0x180068654  xor     r8d, r8d; Reserved
0x180068657  lea     rdx, aTpmkeyname; "TpmKeyName"
0x18006865e  mov     rcx, [rsi+20h]; hKey
0x180068662  call    cs:__imp_RegSetValueExW
0x180068668  test    eax, eax
0x18006866a  jz      short loc_1800686CD
0x18006866c  mov     rcx, [rsp+98h]; this
0x180068674  mov     r9d, eax; char *
0x180068677  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x18006867e  mov     edx, 18Dh; void *
0x180068683  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180068688  mov     edi, eax
0x18006868a  lea     rcx, [rsp+98h+hObject]; this
0x18006868f  call    ?Delete@TpmHmacKey@@AEAAJXZ; TpmHmacKey::Delete(void)
0x180068694  mov     rcx, [rsp+98h]; this
0x18006869c  test    eax, eax
0x18006869e  jns     short loc_1800686B4
0x1800686a0  mov     r9d, eax; char *
0x1800686a3  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x1800686aa  mov     edx, 16Dh; void *
0x1800686af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800686b4  lea     rcx, [rsp+98h+hObject]; this
0x1800686b9  call    ??1TpmHmacKey@@QEAA@XZ; TpmHmacKey::~TpmHmacKey(void)
0x1800686be  nop
0x1800686bf  lea     rcx, [rsp+98h+var_40]
0x1800686c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800686c9  mov     eax, edi
0x1800686cb  jmp     short loc_1800686F9
0x1800686cd  lea     rcx, [rsi+58h]
0x1800686d1  lea     rdx, [rsp+98h+var_40]
0x1800686d6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800686db  lea     rcx, [rsp+98h+hObject]; this
0x1800686e0  call    ??1TpmHmacKey@@QEAA@XZ; TpmHmacKey::~TpmHmacKey(void)
0x1800686e5  nop
0x1800686e6  lea     rcx, [rsp+98h+var_40]
0x1800686eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800686f0  nop
0x1800686f1  xor     eax, eax
0x1800686f3  jmp     short loc_1800686F9
0x1800686f5  mov     eax, [rsp+98h+var_68]
0x1800686f9  mov     rcx, [rsp+98h+var_10]
0x180068701  xor     rcx, rsp; StackCookie
0x180068704  call    __security_check_cookie
0x180068709  lea     r11, [rsp+98h+var_8]
0x180068711  mov     rsi, [r11+20h]
0x180068715  mov     rdi, [r11+28h]
0x180068719  mov     rsp, r11
0x18006871c  pop     r14
0x18006871e  retn
```
