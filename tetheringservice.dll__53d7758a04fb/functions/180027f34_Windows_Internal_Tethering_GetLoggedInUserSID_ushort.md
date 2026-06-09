# Windows::Internal::Tethering::GetLoggedInUserSID(ushort * *)

- ea: `0x180027f34`
- end: `0x180028530`
- name: `?GetLoggedInUserSID@Tethering@Internal@Windows@@YAJPEAPEAG@Z`
- size: `1532`
- prototype: `__int64 __fastcall(Windows::Internal::Tethering *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000eb20`
- `0x18001dc08`

## callees

- `0x180002574`
- `0x180002590`
- `0x18000331c`
- `0x180008914`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000c4f4`
- `0x18000ea08`
- `0x180021580`
- `0x180026538`
- `0x180027db4`
- `0x180027f34`
- `0x180028538`
- `0x180028558`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002827a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002827a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800283a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800284df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800283a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800284df`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800280a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180028270`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800280a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180028270`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180027ff2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180027ff2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028108`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028318`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028108`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028318`
- `ntdll!RtlGetActiveConsoleId` at `0x180028153`
- `ntdll!RtlGetActiveConsoleId` at `0x180028153`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180028190`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180028190`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180028161`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180028230`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180028230`

## string_xrefs

- `0x18002851d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180028007`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180028508`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180028047`: `onecoreuap\net\tethering\service\userutils.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Tethering::GetLoggedInUserSID(
        Windows::Internal::Tethering *this,
        unsigned __int16 **a2)
{
  char v2; // si
  unsigned int v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  char *v6; // r13
  const char *v7; // r9
  bool v8; // di
  int LastError; // eax
  int token_information; // eax
  void *v11; // rdi
  void *v12; // rdx
  unsigned int v13; // r8d
  const char *v14; // r9
  LPWSTR v15; // rcx
  LPWSTR v16; // rax
  unsigned int v17; // edi
  void (**v18)(void); // rax
  __int64 v19; // rcx
  unsigned int v20; // eax
  char v21; // si
  unsigned int v22; // r12d
  TetheringServiceTelemetry *v23; // r10
  int v24; // eax
  int v25; // eax
  signed int v26; // eax
  LPWSTR v27; // rcx
  LPWSTR v28; // rax
  unsigned int v30; // [rsp+20h] [rbp-98h]
  WINBOOL IsMember; // [rsp+24h] [rbp-94h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-90h] BYREF
  unsigned int ActiveConsoleId; // [rsp+30h] [rbp-88h]
  void *Block; // [rsp+38h] [rbp-80h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-78h] BYREF
  Windows::Internal::Tethering *v36; // [rsp+48h] [rbp-70h]
  void (*v37)(void); // [rsp+50h] [rbp-68h] BYREF
  __int64 v38; // [rsp+58h] [rbp-60h]
  __int64 SidToCheck; // [rsp+60h] [rbp-58h] BYREF
  __int64 v40; // [rsp+68h] [rbp-50h] BYREF
  char v41; // [rsp+70h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v36 = this;
  Block = this;
  ActiveConsoleId = 0;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids);
  }
  v2 = 0;
  LOBYTE(v30) = 0;
  TokenHandle = 0;
  v3 = LocalQueryRpcClientToken(&TokenHandle);
  if ( v3 )
  {
    wil::details::in1diag3::_Log_Win32(retaddr, v4, v5, (const char *)v3, v30);
    v6 = (char *)TokenHandle;
  }
  else
  {
    SidToCheck = 0x500000000000101LL;
    LODWORD(v40) = 4;
    IsMember = 0;
    v6 = (char *)TokenHandle;
    if ( CheckTokenMembership(TokenHandle, &SidToCheck, &IsMember) )
    {
      v8 = IsMember != 0;
      LastError = 0;
    }
    else
    {
      v8 = 0;
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x27C,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                    v7);
    }
    if ( LastError < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2C1,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)(unsigned int)LastError,
        v30);
    if ( v8 )
    {
      SidToCheck = 0;
      ActiveConsoleId = 2;
      token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>((void **)&SidToCheck, (__int64)v6);
      if ( token_information < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)token_information,
          v30);
      StringSid = 0;
      v11 = (void *)SidToCheck;
      if ( ConvertSidToStringSidW(*(PSID *)SidToCheck, &StringSid) )
      {
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids, StringSid);
        }
        v16 = StringSid;
        v15 = 0;
        StringSid = 0;
        *(_QWORD *)v36 = v16;
        v2 = 1;
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(retaddr, v12, v13, v14);
        v15 = StringSid;
      }
      if ( v15 )
        LocalFree(v15);
      if ( v11 )
        operator delete(v11);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecoreuap\\net\\tethering\\service\\userutils.cpp",
        (const char *)0x80070057LL,
        v30);
    }
    v17 = 0;
    if ( v2 )
      goto LABEL_83;
  }
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    ActiveConsoleId = RtlGetActiveConsoleId();
    IsMember = 0;
    v37 = (void (*)(void))UMgrFreeSessionUsers;
    v38 = 0;
    SidToCheck = (__int64)&v37;
    v40 = 0;
    v41 = 1;
    v17 = UMgrEnumerateSessionUsers(&IsMember, &v40);
    if ( v41 )
    {
      v18 = (void (**)(void))SidToCheck;
      v19 = *(_QWORD *)(SidToCheck + 8);
      *(_QWORD *)(SidToCheck + 8) = v40;
      if ( v19 )
        (*v18)();
    }
    if ( (v17 & 0x80000000) != 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_77:
        if ( v38 )
        {
          v37();
          v23 = WPP_GLOBAL_Control;
        }
        goto LABEL_84;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids, v17);
    }
    else
    {
      v20 = IsMember;
      if ( IsMember && v38 )
      {
        v21 = 0;
        v22 = 0;
        v23 = WPP_GLOBAL_Control;
        while ( 1 )
        {
          if ( v21 )
            goto LABEL_77;
          if ( (v17 & 0x80000000) != 0 )
            goto LABEL_67;
          if ( *(_DWORD *)(v38 + 16LL * v22 + 8) == ActiveConsoleId || v20 == 1 )
            break;
LABEL_65:
          if ( ++v22 >= v20 )
          {
            if ( v21 )
              goto LABEL_77;
LABEL_67:
            v17 = -2147023728;
            if ( v23 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)v23 + 2), 17, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids, ActiveConsoleId);
              goto LABEL_76;
            }
            goto LABEL_77;
          }
        }
        SidToCheck = 0;
        v24 = UMgrQueryUserToken(*(_QWORD *)(v38 + 16LL * v22), &SidToCheck);
        v17 = v24;
        if ( v24 < 0 )
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_62;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids,
            (unsigned int)v24);
          goto LABEL_61;
        }
        Block = 0;
        v25 = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, SidToCheck);
        v17 = v25;
        if ( v25 < 0 )
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_56;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids,
            (unsigned int)v25);
          goto LABEL_55;
        }
        StringSid = 0;
        if ( ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
        {
          if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids,
              StringSid);
          }
          v28 = StringSid;
          v27 = 0;
          StringSid = 0;
          *(_QWORD *)v36 = v28;
          v21 = 1;
        }
        else
        {
          v26 = GetLastError();
          v17 = v26;
          if ( v26 > 0 )
            v17 = (unsigned __int16)v26 | 0x80070000;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            v27 = StringSid;
LABEL_50:
            if ( !v27 )
            {
LABEL_56:
              if ( !Block )
              {
LABEL_62:
                if ( (unsigned __int64)(SidToCheck - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                {
                  CloseHandle((HANDLE)SidToCheck);
                  v23 = WPP_GLOBAL_Control;
                }
                v20 = IsMember;
                goto LABEL_65;
              }
              operator delete(Block);
LABEL_61:
              v23 = WPP_GLOBAL_Control;
              goto LABEL_62;
            }
            LocalFree(v27);
LABEL_55:
            v23 = WPP_GLOBAL_Control;
            goto LABEL_56;
          }
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids, v17);
          v27 = StringSid;
        }
        v23 = WPP_GLOBAL_Control;
        goto LABEL_50;
      }
      v17 = -2147023728;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_77;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids);
    }
LABEL_76:
    v23 = WPP_GLOBAL_Control;
    goto LABEL_77;
  }
  v17 = -2147467263;
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_87;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids);
LABEL_83:
    v23 = WPP_GLOBAL_Control;
  }
LABEL_84:
  if ( v23 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v23 + 2), 20, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids, v17);
LABEL_87:
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return v17;
}

```

## disassembly

```asm
0x180027f34  push    rbx
0x180027f36  push    rsi
0x180027f37  push    rdi
0x180027f38  push    r12
0x180027f3a  push    r13
0x180027f3c  push    r15
0x180027f3e  sub     rsp, 88h
0x180027f45  mov     rax, cs:__security_cookie
0x180027f4c  xor     rax, rsp
0x180027f4f  mov     [rsp+0B8h+var_40], rax
0x180027f54  mov     [rsp+0B8h+var_70], rcx
0x180027f59  mov     [rsp+0B8h+Block], rcx
0x180027f5e  xor     ebx, ebx
0x180027f60  mov     [rsp+0B8h+var_88], ebx
0x180027f64  lea     r15, WPP_GLOBAL_Control
0x180027f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f72  cmp     rcx, r15
0x180027f75  jz      short loc_180027F90
0x180027f77  test    byte ptr [rcx+1Ch], 8
0x180027f7b  jz      short loc_180027F90
0x180027f7d  lea     edx, [rbx+0Ah]
0x180027f80  lea     r8, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids
0x180027f87  mov     rcx, [rcx+10h]
0x180027f8b  call    WPP_SF_
0x180027f90  mov     sil, bl
0x180027f93  mov     byte ptr [rsp+0B8h+var_98], bl; int
0x180027f97  mov     [rsp+0B8h+TokenHandle], rbx
0x180027f9c  lea     rcx, [rsp+0B8h+TokenHandle]; void **
0x180027fa1  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x180027fa6  mov     rcx, [rsp+0B8h]; this
0x180027fae  test    eax, eax
0x180027fb0  jz      short loc_180027FC4
0x180027fb2  mov     r9d, eax; char *
0x180027fb5  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180027fba  mov     r13, [rsp+0B8h+TokenHandle]
0x180027fbf  jmp     loc_180028146
0x180027fc4  mov     dword ptr [rsp+0B8h+SidToCheck], 101h
0x180027fcc  mov     dword ptr [rsp+0B8h+SidToCheck+4], 5000000h
0x180027fd4  mov     dword ptr [rsp+0B8h+var_50], 4
0x180027fdc  mov     [rsp+0B8h+IsMember], ebx
0x180027fe0  lea     r8, [rsp+0B8h+IsMember]; IsMember
0x180027fe5  lea     rdx, [rsp+0B8h+SidToCheck]; SidToCheck
0x180027fea  mov     r13, [rsp+0B8h+TokenHandle]
0x180027fef  mov     rcx, r13; TokenHandle
0x180027ff2  call    cs:__imp_CheckTokenMembership
0x180027ff8  test    eax, eax
0x180027ffa  jnz     short loc_18002801A
0x180027ffc  mov     dil, bl
0x180027fff  mov     rcx, [rsp+0B8h]; this
0x180028007  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002800e  mov     edx, 27Ch; void *
0x180028013  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028018  jmp     short loc_180028024
0x18002801a  cmp     [rsp+0B8h+IsMember], ebx
0x18002801e  setnz   dil
0x180028022  mov     eax, ebx
0x180028024  mov     rcx, [rsp+0B8h]; this
0x18002802c  test    eax, eax
0x18002802e  js      loc_180028505
0x180028034  mov     rcx, [rsp+0B8h]; this
0x18002803c  test    dil, dil
0x18002803f  jnz     short loc_18002805D
0x180028041  mov     r9d, 80070057h; char *
0x180028047  lea     r8, aOnecoreuapNetT_1; "onecoreuap\\net\\tethering\\service\\us"...
0x18002804e  mov     edx, 23h ; '#'; void *
0x180028053  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028058  jmp     loc_18002811C
0x18002805d  mov     [rsp+0B8h+SidToCheck], rbx
0x180028062  mov     [rsp+0B8h+var_88], 2
0x18002806a  mov     rdx, r13
0x18002806d  lea     rcx, [rsp+0B8h+SidToCheck]
0x180028072  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180028077  mov     rcx, [rsp+0B8h]; this
0x18002807f  test    eax, eax
0x180028081  js      loc_18002851A
0x180028087  mov     [rsp+0B8h+StringSid], rbx
0x18002808c  mov     r12, [rsp+0B8h]
0x180028094  lea     rdx, [rsp+0B8h+StringSid]; StringSid
0x180028099  mov     rdi, [rsp+0B8h+SidToCheck]
0x18002809e  mov     rcx, [rdi]; Sid
0x1800280a1  call    cs:__imp_ConvertSidToStringSidW
0x1800280a7  test    eax, eax
0x1800280a9  jnz     short loc_1800280BA
0x1800280ab  mov     rcx, r12; this
0x1800280ae  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800280b3  mov     rcx, [rsp+0B8h+StringSid]
0x1800280b8  jmp     short loc_180028103
0x1800280ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280c1  cmp     rcx, r15
0x1800280c4  jz      short loc_1800280E6
0x1800280c6  test    byte ptr [rcx+1Ch], 4
0x1800280ca  jz      short loc_1800280E6
0x1800280cc  mov     edx, 0Bh
0x1800280d1  mov     r9, [rsp+0B8h+StringSid]
0x1800280d6  lea     r8, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids
0x1800280dd  mov     rcx, [rcx+10h]
0x1800280e1  call    WPP_SF_S
0x1800280e6  mov     rax, [rsp+0B8h+StringSid]
0x1800280eb  mov     rcx, rbx; hMem
0x1800280ee  mov     [rsp+0B8h+StringSid], rbx
0x1800280f3  mov     rdx, [rsp+0B8h+var_70]
0x1800280f8  mov     [rdx], rax
0x1800280fb  mov     sil, 1
0x1800280fe  mov     byte ptr [rsp+0B8h+var_98], sil
0x180028103  test    rcx, rcx
0x180028106  jz      short loc_18002810E
0x180028108  call    cs:__imp_LocalFree
0x18002810e  test    rdi, rdi
0x180028111  jz      short loc_18002811C
0x180028113  mov     rcx, rdi; Block
0x180028116  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002811b  nop
0x18002811c  jmp     short loc_18002813B
0x18002811e  xor     ebx, ebx
0x180028120  lea     r15, WPP_GLOBAL_Control
0x180028127  mov     sil, byte ptr [rsp+0B8h+var_98]
0x18002812c  mov     r13, [rsp+0B8h+TokenHandle]
0x180028131  mov     rax, [rsp+0B8h+Block]
0x180028136  mov     [rsp+0B8h+var_70], rax
0x18002813b  mov     edi, ebx
0x18002813d  test    sil, sil
0x180028140  jnz     loc_1800284A6
0x180028146  call    IsUMgrEnumerateSessionUsersPresent
0x18002814b  test    al, al
0x18002814d  jz      loc_180028479
0x180028153  call    cs:__imp_RtlGetActiveConsoleId
0x180028159  mov     [rsp+0B8h+var_88], eax
0x18002815d  mov     [rsp+0B8h+IsMember], ebx
0x180028161  mov     rax, cs:__imp_UMgrFreeSessionUsers
0x180028168  mov     [rsp+0B8h+var_68], rax
0x18002816d  mov     [rsp+0B8h+var_60], rbx
0x180028172  lea     rax, [rsp+0B8h+var_68]
0x180028177  mov     [rsp+0B8h+SidToCheck], rax
0x18002817c  mov     [rsp+0B8h+var_50], rbx
0x180028181  mov     [rsp+0B8h+var_48], 1
0x180028186  lea     rdx, [rsp+0B8h+var_50]
0x18002818b  lea     rcx, [rsp+0B8h+IsMember]
0x180028190  call    cs:__imp_UMgrEnumerateSessionUsers
0x180028196  mov     edi, eax
0x180028198  cmp     [rsp+0B8h+var_48], bl
0x18002819c  jz      short loc_1800281BE
0x18002819e  mov     rax, [rsp+0B8h+SidToCheck]
0x1800281a3  mov     rdx, [rsp+0B8h+var_50]
0x1800281a8  mov     rcx, [rax+8]
0x1800281ac  mov     [rax+8], rdx
0x1800281b0  test    rcx, rcx
0x1800281b3  jz      short loc_1800281BE
0x1800281b5  mov     rax, [rax]
0x1800281b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281bd  nop
0x1800281be  test    edi, edi
0x1800281c0  js      loc_18002842A
0x1800281c6  mov     eax, [rsp+0B8h+IsMember]
0x1800281ca  test    eax, eax
0x1800281cc  jz      loc_1800283FB
0x1800281d2  cmp     [rsp+0B8h+var_60], rbx
0x1800281d7  jz      loc_1800283FB
0x1800281dd  mov     sil, bl
0x1800281e0  mov     r12d, ebx
0x1800281e3  mov     r10, cs:WPP_GLOBAL_Control
0x1800281ea  test    eax, eax
0x1800281ec  jz      loc_1800283CA
0x1800281f2  test    sil, sil
0x1800281f5  jnz     loc_18002845C
0x1800281fb  test    edi, edi
0x1800281fd  js      loc_1800283CA
0x180028203  mov     ecx, r12d
0x180028206  add     rcx, rcx
0x180028209  mov     r8, [rsp+0B8h+var_60]
0x18002820e  mov     edx, [rsp+0B8h+var_88]
0x180028212  cmp     [r8+rcx*8+8], edx
0x180028217  jz      short loc_180028222
0x180028219  cmp     eax, 1
0x18002821c  jnz     loc_1800283B5
0x180028222  mov     [rsp+0B8h+SidToCheck], rbx
0x180028227  lea     rdx, [rsp+0B8h+SidToCheck]
0x18002822c  mov     rcx, [r8+rcx*8]
0x180028230  call    cs:__imp_UMgrQueryUserToken
0x180028236  mov     edi, eax
0x180028238  test    eax, eax
0x18002823a  js      loc_180028363
0x180028240  mov     [rsp+0B8h+Block], rbx
0x180028245  mov     rdx, [rsp+0B8h+SidToCheck]
0x18002824a  lea     rcx, [rsp+0B8h+Block]
0x18002824f  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180028254  mov     edi, eax
0x180028256  test    eax, eax
0x180028258  js      loc_180028320
0x18002825e  mov     [rsp+0B8h+StringSid], rbx
0x180028263  lea     rdx, [rsp+0B8h+StringSid]; StringSid
0x180028268  mov     rcx, [rsp+0B8h+Block]
0x18002826d  mov     rcx, [rcx]; Sid
0x180028270  call    cs:__imp_ConvertSidToStringSidW
0x180028276  test    eax, eax
0x180028278  jnz     short loc_1800282C8
0x18002827a  call    cs:__imp_GetLastError
0x180028280  mov     edi, eax
0x180028282  test    eax, eax
0x180028284  jle     short loc_18002828F
0x180028286  movzx   edi, ax
0x180028289  or      edi, 80070000h
0x18002828f  mov     r10, cs:WPP_GLOBAL_Control
0x180028296  cmp     r10, r15
0x180028299  jz      short loc_1800282C1
0x18002829b  test    byte ptr [r10+1Ch], 1
0x1800282a0  jz      short loc_1800282C1
0x1800282a2  mov     edx, 0Dh
0x1800282a7  mov     r9d, edi
0x1800282aa  lea     r8, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids
0x1800282b1  mov     rcx, [r10+10h]
0x1800282b5  call    WPP_SF_d
0x1800282ba  mov     rcx, [rsp+0B8h+StringSid]
0x1800282bf  jmp     short loc_18002830C
0x1800282c1  mov     rcx, [rsp+0B8h+StringSid]
0x1800282c6  jmp     short loc_180028313
0x1800282c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282cf  cmp     rcx, r15
0x1800282d2  jz      short loc_1800282F4
0x1800282d4  test    byte ptr [rcx+1Ch], 4
0x1800282d8  jz      short loc_1800282F4
0x1800282da  mov     edx, 0Eh
0x1800282df  mov     r9, [rsp+0B8h+StringSid]
0x1800282e4  lea     r8, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids
0x1800282eb  mov     rcx, [rcx+10h]
0x1800282ef  call    WPP_SF_S
0x1800282f4  mov     rax, [rsp+0B8h+StringSid]
0x1800282f9  mov     rcx, rbx; hMem
0x1800282fc  mov     [rsp+0B8h+StringSid], rbx
0x180028301  mov     rdx, [rsp+0B8h+var_70]
0x180028306  mov     [rdx], rax
0x180028309  mov     sil, 1
0x18002830c  mov     r10, cs:WPP_GLOBAL_Control
0x180028313  test    rcx, rcx
0x180028316  jz      short loc_180028352
0x180028318  call    cs:__imp_LocalFree
0x18002831e  jmp     short loc_18002834B
0x180028320  mov     r10, cs:WPP_GLOBAL_Control
0x180028327  cmp     r10, r15
0x18002832a  jz      short loc_180028352
0x18002832c  test    byte ptr [r10+1Ch], 1
0x180028331  jz      short loc_180028352
0x180028333  mov     edx, 0Fh
0x180028338  mov     r9d, eax
0x18002833b  lea     r8, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids
0x180028342  mov     rcx, [r10+10h]
0x180028346  call    WPP_SF_d
0x18002834b  mov     r10, cs:WPP_GLOBAL_Control
0x180028352  mov     rcx, [rsp+0B8h+Block]; Block
0x180028357  test    rcx, rcx
0x18002835a  jz      short loc_180028395
0x18002835c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028361  jmp     short loc_18002838E
0x180028363  mov     r10, cs:WPP_GLOBAL_Control
0x18002836a  cmp     r10, r15
0x18002836d  jz      short loc_180028395
0x18002836f  test    byte ptr [r10+1Ch], 1
0x180028374  jz      short loc_180028395
0x180028376  mov     edx, 10h
0x18002837b  mov     r9d, eax
0x18002837e  lea     r8, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids
0x180028385  mov     rcx, [r10+10h]
0x180028389  call    WPP_SF_d
0x18002838e  mov     r10, cs:WPP_GLOBAL_Control
0x180028395  mov     rcx, [rsp+0B8h+SidToCheck]; hObject
0x18002839a  lea     rax, [rcx-1]
0x18002839e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800283a2  ja      short loc_1800283B1
0x1800283a4  call    cs:__imp_CloseHandle
0x1800283aa  mov     r10, cs:WPP_GLOBAL_Control
0x1800283b1  mov     eax, [rsp+0B8h+IsMember]
0x1800283b5  inc     r12d
0x1800283b8  cmp     r12d, eax
0x1800283bb  jb      loc_1800281F2
0x1800283c1  test    sil, sil
0x1800283c4  jnz     loc_18002845C
0x1800283ca  mov     edi, 80070490h
0x1800283cf  cmp     r10, r15
0x1800283d2  jz      loc_18002845C
0x1800283d8  test    byte ptr [r10+1Ch], 1
0x1800283dd  jz      short loc_18002845C
0x1800283df  mov     edx, 11h
0x1800283e4  mov     r9d, [rsp+0B8h+var_88]
0x1800283e9  lea     r8, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids
0x1800283f0  mov     rcx, [r10+10h]
0x1800283f4  call    WPP_SF_d
0x1800283f9  jmp     short loc_180028455
0x1800283fb  mov     edi, 80070490h
0x180028400  mov     r10, cs:WPP_GLOBAL_Control
0x180028407  cmp     r10, r15
0x18002840a  jz      short loc_18002845C
0x18002840c  test    byte ptr [r10+1Ch], 1
0x180028411  jz      short loc_18002845C
0x180028413  mov     edx, 0Ch
0x180028418  lea     r8, WPP_6d45bac1183f3263ba10cf8681984b5c_Traceguids
0x18002841f  mov     rcx, [r10+10h]
0x180028423  call    WPP_SF_
0x180028428  jmp     short loc_180028455
0x18002842a  mov     r10, cs:WPP_GLOBAL_Control
0x180028431  cmp     r10, r15
0x180028434  jz      short loc_18002845C
  ... truncated ...
```
