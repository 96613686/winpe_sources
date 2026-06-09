# Windows::System::Internal::UserManagerStatics::SignOutSponsoredUser(uint,Microsoft::WRL::ComPtr<Windows::System::IUser> &,Windows::System::Internal::ISignOutResult *,void *)

- ea: `0x180061f98`
- end: `0x1800624b6`
- name: `?SignOutSponsoredUser@UserManagerStatics@Internal@System@Windows@@AEAAJIAEAV?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@PEAUISignOutResult@234@PEAX@Z`
- size: `1310`
- prototype: `__int64 __usercall@<rax>(Windows::System::Internal::UserManagerStatics *this@<rcx>, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a2880`
- `0x1800a293c`

## callees

- `0x1800088e8`
- `0x18000ce48`
- `0x1800332e8`
- `0x180061f98`
- `0x1800624bc`
- `0x18008c534`
- `0x1800915d4`
- `0x180094e90`
- `0x1800977b0`
- `0x1800a2604`
- `0x1800c1c60`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006249f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006249f`
- `ntdll!RtlIsMultiSessionSku` at `0x18006219c`
- `ntdll!RtlIsMultiSessionSku` at `0x18006219c`

## string_xrefs

- `0x18006205e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800620d8`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18006214a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800621b2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180062222`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800622a1`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180062309`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18006238a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800623fc`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 Windows::System::Internal::UserManagerStatics::SignOutSponsoredUser(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2,
        _QWORD *a3,
        ...)
{
  __int64 v6; // rcx
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // rdi
  __int64 (__fastcall *v8)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, Windows::System::UserAuthenticationStatusChangingEventArgs **); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v11; // rax
  Windows::System::Internal::UserManagerStatics *v12; // rcx
  int v13; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v17; // rax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v18; // rax
  int v19; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v20; // rax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v21; // rax
  int v22; // eax
  Windows::System::Internal::UserManagerStatics *v23; // rcx
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v24; // rax
  int v25; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v26; // rax
  int v27; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v28; // rax
  int v29; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v30; // rax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v31; // rax
  int v33; // [rsp+20h] [rbp-50h]
  _QWORD v34[6]; // [rsp+30h] [rbp-40h] BYREF
  char v35; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v37; // [rsp+B0h] [rbp+40h] BYREF
  char v38; // [rsp+B8h] [rbp+48h] BYREF
  Windows::System::UserAuthenticationStatusChangingEventArgs *v39; // [rsp+C0h] [rbp+50h] BYREF
  struct Windows::System::Internal::ISignOutResult *v40; // [rsp+C8h] [rbp+58h] BYREF
  va_list va; // [rsp+C8h] [rbp+58h]
  void *v42; // [rsp+D0h] [rbp+60h]
  va_list va1; // [rsp+D8h] [rbp+68h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v40 = va_arg(va1, struct Windows::System::Internal::ISignOutResult *);
  v42 = va_arg(va1, void *);
  if ( !*a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( a2 - 1 > 0xE )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 69) + 8LL))((char *)this + 552) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  v34[1] = 0;
  v38 = 0;
  v37 = 0;
  v34[0] = 0;
  v39 = 0;
  v34[2] = &v38;
  v34[3] = this;
  v34[4] = a3;
  va_copy((va_list)&v34[5], va);
  v35 = 1;
  UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
  v8 = *(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, Windows::System::UserAuthenticationStatusChangingEventArgs **))(*(_QWORD *)UserStaticsInternal + 216LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  v9 = v8(UserStaticsInternal, *a3, 0, &v39);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v38 = 1;
    v12 = v39;
    if ( v39 )
      Windows::System::UserAuthenticationStatusChangingEventArgs::WaitForAnyOutstandingDeferrals(v39);
    v13 = Windows::System::Internal::UserManagerStatics::CheckCancelEvent(v12, v42);
    v10 = v13;
    if ( v13 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a3 + 56LL))(*a3, &v37);
      v10 = v15;
      if ( v15 >= 0 )
      {
        if ( (unsigned __int8)RtlIsMultiSessionSku(v16) )
        {
          v10 = -2147024846;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1875,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)0x80070032LL,
            v33);
          if ( v38 )
          {
            v18 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
            (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v18 + 224LL))(
              v18,
              *a3,
              0);
          }
          if ( v40 )
            Windows::System::Internal::UserManagerStatics::FireSignOutComplete(this, v40);
        }
        else if ( v37 == 2
               && (v19 = Windows::System::Internal::UserManagerStatics::PreSignOutOfAuthManager(this, a2),
                   v10 = v19,
                   v19 < 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x187A,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v19,
            v33);
          if ( v38 )
          {
            v20 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
            (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v20 + 224LL))(
              v20,
              *a3,
              0);
          }
          if ( v40 )
            Windows::System::Internal::UserManagerStatics::FireSignOutComplete(this, v40);
        }
        else
        {
          v21 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
          v22 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v21 + 112LL))(
                  v21,
                  a2,
                  0);
          v10 = v22;
          if ( v22 >= 0 )
          {
            v25 = Windows::System::Internal::UserManagerStatics::CheckCancelEvent(v23, v42);
            v10 = v25;
            if ( v25 >= 0 )
            {
              if ( v37 == 2
                && (Windows::System::Internal::LogSignOutUserReason(a2, 0, "SignOutSponsoredUser"),
                    v27 = Windows::System::Internal::UserManagerStatics::SignOutOfAuthManager(this, a2),
                    v10 = v27,
                    v27 < 0) )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1885,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                  (const char *)(unsigned int)v27,
                  v33);
                if ( v38 )
                {
                  v28 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
                  (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v28 + 224LL))(
                    v28,
                    *a3,
                    0);
                }
                if ( v40 )
                  Windows::System::Internal::UserManagerStatics::FireSignOutComplete(this, v40);
              }
              else
              {
                v29 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 5) + 72LL))((char *)this + 40, a2);
                v10 = v29;
                if ( v29 >= 0 )
                {
                  if ( v38 )
                  {
                    v31 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
                    (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v31 + 224LL))(
                      v31,
                      *a3,
                      0);
                  }
                  if ( v40 )
                    Windows::System::Internal::UserManagerStatics::FireSignOutComplete(this, v40);
                  v10 = 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1888,
                    (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                    (const char *)(unsigned int)v29,
                    v33);
                  if ( v38 )
                  {
                    v30 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
                    (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v30 + 224LL))(
                      v30,
                      *a3,
                      0);
                  }
                  if ( v40 )
                    Windows::System::Internal::UserManagerStatics::FireSignOutComplete(this, v40);
                }
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x187F,
                (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
                (const char *)(unsigned int)v25,
                v33);
              if ( v38 )
              {
                v26 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
                (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v26 + 224LL))(
                  v26,
                  *a3,
                  0);
              }
              if ( v40 )
                Windows::System::Internal::UserManagerStatics::FireSignOutComplete(this, v40);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x187D,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
              (const char *)(unsigned int)v22,
              v33);
            if ( v38 )
            {
              v24 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
              (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v24 + 224LL))(
                v24,
                *a3,
                0);
            }
            if ( v40 )
              Windows::System::Internal::UserManagerStatics::FireSignOutComplete(this, v40);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1873,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v15,
          v33);
        if ( v38 )
        {
          v17 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
          (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v17 + 224LL))(
            v17,
            *a3,
            0);
        }
        if ( v40 )
          Windows::System::Internal::UserManagerStatics::FireSignOutComplete(this, v40);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x186F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v13,
        v33);
      if ( v38 )
      {
        v14 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
        (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v14 + 224LL))(
          v14,
          *a3,
          0);
      }
      if ( v40 )
        Windows::System::Internal::UserManagerStatics::FireSignOutComplete(this, v40);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1865,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v9,
      v33);
    if ( v38 )
    {
      v11 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
      (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v11 + 224LL))(
        v11,
        *a3,
        0);
    }
    if ( v40 )
      Windows::System::Internal::UserManagerStatics::FireSignOutComplete(this, v40);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v34);
  WindowsDeleteString(0);
  return v10;
}

```

## disassembly

```asm
0x180061f98  mov     [rsp-38h+arg_18], r9
0x180061f9d  push    rbp
0x180061f9e  push    rbx
0x180061f9f  push    rsi
0x180061fa0  push    rdi
0x180061fa1  push    r12
0x180061fa3  push    r14
0x180061fa5  push    r15
0x180061fa7  mov     rbp, rsp
0x180061faa  sub     rsp, 70h
0x180061fae  mov     r14, r8
0x180061fb1  mov     r15d, edx
0x180061fb4  mov     rsi, rcx
0x180061fb7  xor     r12d, r12d
0x180061fba  cmp     [r8], r12
0x180061fbd  jnz     short loc_180061FC4
0x180061fbf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180061fc4  lea     eax, [r15-1]
0x180061fc8  cmp     eax, 0Eh
0x180061fcb  jbe     short loc_180061FD2
0x180061fcd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180061fd2  lea     rcx, [rsi+228h]
0x180061fd9  mov     rax, [rcx]
0x180061fdc  mov     rax, [rax+8]
0x180061fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061fe5  test    al, al
0x180061fe7  jnz     short loc_180061FEE
0x180061fe9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180061fee  mov     [rbp+var_38], r12
0x180061ff2  mov     [rbp+arg_8], r12b
0x180061ff6  mov     [rbp+arg_0], r12d
0x180061ffa  mov     [rbp+var_40], r12
0x180061ffe  mov     [rbp+arg_10], r12
0x180062002  lea     rax, [rbp+arg_8]
0x180062006  mov     [rbp+var_30], rax
0x18006200a  mov     [rbp+var_28], rsi
0x18006200e  mov     [rbp+var_20], r14
0x180062012  lea     rax, [rbp+arg_18]
0x180062016  mov     [rbp+var_18], rax
0x18006201a  mov     [rbp+var_10], 1
0x18006201e  mov     rcx, rsi; this
0x180062021  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x180062026  mov     rdi, rax
0x180062029  mov     rcx, [rax]
0x18006202c  mov     rbx, [rcx+0D8h]
0x180062033  lea     rcx, [rbp+arg_10]
0x180062037  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006203c  lea     r9, [rbp+arg_10]
0x180062040  xor     r8d, r8d
0x180062043  mov     rdx, [r14]
0x180062046  mov     rcx, rdi
0x180062049  mov     rax, rbx
0x18006204c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062051  mov     ebx, eax
0x180062053  test    eax, eax
0x180062055  jns     short loc_1800620B0
0x180062057  mov     rcx, [rbp+38h]; this
0x18006205b  mov     r9d, eax; char *
0x18006205e  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180062065  mov     edx, 1865h; void *
0x18006206a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006206f  nop
0x180062070  cmp     [rbp+arg_8], r12b
0x180062074  jz      short loc_180062099
0x180062076  mov     rcx, rsi; this
0x180062079  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x18006207e  mov     r9, rax
0x180062081  mov     rcx, [rax]
0x180062084  mov     rax, [rcx+0E0h]
0x18006208b  xor     r8d, r8d
0x18006208e  mov     rdx, [r14]
0x180062091  mov     rcx, r9
0x180062094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062099  mov     rdx, [rbp+arg_18]; struct Windows::System::Internal::ISignOutResult *
0x18006209d  test    rdx, rdx
0x1800620a0  jz      short loc_1800620AB
0x1800620a2  mov     rcx, rsi; this
0x1800620a5  call    ?FireSignOutComplete@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUISignOutResult@234@@Z; Windows::System::Internal::UserManagerStatics::FireSignOutComplete(Windows::System::Internal::ISignOutResult *)
0x1800620aa  nop
0x1800620ab  jmp     loc_180062489
0x1800620b0  mov     [rbp+arg_8], 1
0x1800620b4  mov     rcx, [rbp+arg_10]; this
0x1800620b8  test    rcx, rcx
0x1800620bb  jz      short loc_1800620C2
0x1800620bd  call    ?WaitForAnyOutstandingDeferrals@UserAuthenticationStatusChangingEventArgs@System@Windows@@QEAAXXZ; Windows::System::UserAuthenticationStatusChangingEventArgs::WaitForAnyOutstandingDeferrals(void)
0x1800620c2  mov     rdx, [rbp+arg_20]; void *
0x1800620c6  call    ?CheckCancelEvent@UserManagerStatics@Internal@System@Windows@@AEAAJPEAX@Z; Windows::System::Internal::UserManagerStatics::CheckCancelEvent(void *)
0x1800620cb  mov     ebx, eax
0x1800620cd  test    eax, eax
0x1800620cf  jns     short loc_18006212A
0x1800620d1  mov     rcx, [rbp+38h]; this
0x1800620d5  mov     r9d, eax; char *
0x1800620d8  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800620df  mov     edx, 186Fh; void *
0x1800620e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800620e9  nop
0x1800620ea  cmp     [rbp+arg_8], r12b
0x1800620ee  jz      short loc_180062113
0x1800620f0  mov     rcx, rsi; this
0x1800620f3  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x1800620f8  mov     r9, rax
0x1800620fb  mov     rcx, [rax]
0x1800620fe  mov     rax, [rcx+0E0h]
0x180062105  xor     r8d, r8d
0x180062108  mov     rdx, [r14]
0x18006210b  mov     rcx, r9
0x18006210e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062113  mov     rdx, [rbp+arg_18]; struct Windows::System::Internal::ISignOutResult *
0x180062117  test    rdx, rdx
0x18006211a  jz      short loc_180062125
0x18006211c  mov     rcx, rsi; this
0x18006211f  call    ?FireSignOutComplete@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUISignOutResult@234@@Z; Windows::System::Internal::UserManagerStatics::FireSignOutComplete(Windows::System::Internal::ISignOutResult *)
0x180062124  nop
0x180062125  jmp     loc_180062489
0x18006212a  mov     rcx, [r14]
0x18006212d  mov     rax, [rcx]
0x180062130  lea     rdx, [rbp+arg_0]
0x180062134  mov     rax, [rax+38h]
0x180062138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006213d  mov     ebx, eax
0x18006213f  test    eax, eax
0x180062141  jns     short loc_18006219C
0x180062143  mov     rcx, [rbp+38h]; this
0x180062147  mov     r9d, eax; char *
0x18006214a  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180062151  mov     edx, 1873h; void *
0x180062156  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006215b  nop
0x18006215c  cmp     [rbp+arg_8], r12b
0x180062160  jz      short loc_180062185
0x180062162  mov     rcx, rsi; this
0x180062165  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x18006216a  mov     r9, rax
0x18006216d  mov     rcx, [rax]
0x180062170  mov     rax, [rcx+0E0h]
0x180062177  xor     r8d, r8d
0x18006217a  mov     rdx, [r14]
0x18006217d  mov     rcx, r9
0x180062180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062185  mov     rdx, [rbp+arg_18]; struct Windows::System::Internal::ISignOutResult *
0x180062189  test    rdx, rdx
0x18006218c  jz      short loc_180062197
0x18006218e  mov     rcx, rsi; this
0x180062191  call    ?FireSignOutComplete@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUISignOutResult@234@@Z; Windows::System::Internal::UserManagerStatics::FireSignOutComplete(Windows::System::Internal::ISignOutResult *)
0x180062196  nop
0x180062197  jmp     loc_180062489
0x18006219c  call    cs:__imp_RtlIsMultiSessionSku
0x1800621a2  test    al, al
0x1800621a4  jz      short loc_180062204
0x1800621a6  mov     rcx, [rbp+38h]; this
0x1800621aa  mov     ebx, 80070032h
0x1800621af  mov     r9d, ebx; char *
0x1800621b2  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800621b9  mov     edx, 1875h; void *
0x1800621be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800621c3  nop
0x1800621c4  cmp     [rbp+arg_8], r12b
0x1800621c8  jz      short loc_1800621ED
0x1800621ca  mov     rcx, rsi; this
0x1800621cd  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x1800621d2  mov     r9, rax
0x1800621d5  mov     rcx, [rax]
0x1800621d8  mov     rax, [rcx+0E0h]
0x1800621df  xor     r8d, r8d
0x1800621e2  mov     rdx, [r14]
0x1800621e5  mov     rcx, r9
0x1800621e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800621ed  mov     rdx, [rbp+arg_18]; struct Windows::System::Internal::ISignOutResult *
0x1800621f1  test    rdx, rdx
0x1800621f4  jz      short loc_1800621FF
0x1800621f6  mov     rcx, rsi; this
0x1800621f9  call    ?FireSignOutComplete@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUISignOutResult@234@@Z; Windows::System::Internal::UserManagerStatics::FireSignOutComplete(Windows::System::Internal::ISignOutResult *)
0x1800621fe  nop
0x1800621ff  jmp     loc_180062489
0x180062204  cmp     [rbp+arg_0], 2
0x180062208  jnz     short loc_180062274
0x18006220a  mov     edx, r15d; unsigned int
0x18006220d  mov     rcx, rsi; this
0x180062210  call    ?PreSignOutOfAuthManager@UserManagerStatics@Internal@System@Windows@@AEAAJI@Z; Windows::System::Internal::UserManagerStatics::PreSignOutOfAuthManager(uint)
0x180062215  mov     ebx, eax
0x180062217  test    eax, eax
0x180062219  jns     short loc_180062274
0x18006221b  mov     rcx, [rbp+38h]; this
0x18006221f  mov     r9d, eax; char *
0x180062222  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180062229  mov     edx, 187Ah; void *
0x18006222e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062233  nop
0x180062234  cmp     [rbp+arg_8], r12b
0x180062238  jz      short loc_18006225D
0x18006223a  mov     rcx, rsi; this
0x18006223d  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x180062242  mov     r9, rax
0x180062245  mov     rcx, [rax]
0x180062248  mov     rax, [rcx+0E0h]
0x18006224f  xor     r8d, r8d
0x180062252  mov     rdx, [r14]
0x180062255  mov     rcx, r9
0x180062258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006225d  mov     rdx, [rbp+arg_18]; struct Windows::System::Internal::ISignOutResult *
0x180062261  test    rdx, rdx
0x180062264  jz      short loc_18006226F
0x180062266  mov     rcx, rsi; this
0x180062269  call    ?FireSignOutComplete@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUISignOutResult@234@@Z; Windows::System::Internal::UserManagerStatics::FireSignOutComplete(Windows::System::Internal::ISignOutResult *)
0x18006226e  nop
0x18006226f  jmp     loc_180062489
0x180062274  mov     rcx, rsi; this
0x180062277  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x18006227c  mov     r9, rax
0x18006227f  mov     rcx, [rax]
0x180062282  mov     rax, [rcx+70h]
0x180062286  xor     r8d, r8d
0x180062289  mov     edx, r15d
0x18006228c  mov     rcx, r9
0x18006228f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062294  mov     ebx, eax
0x180062296  test    eax, eax
0x180062298  jns     short loc_1800622F3
0x18006229a  mov     rcx, [rbp+38h]; this
0x18006229e  mov     r9d, eax; char *
0x1800622a1  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800622a8  mov     edx, 187Dh; void *
0x1800622ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800622b2  nop
0x1800622b3  cmp     [rbp+arg_8], r12b
0x1800622b7  jz      short loc_1800622DC
0x1800622b9  mov     rcx, rsi; this
0x1800622bc  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x1800622c1  mov     r9, rax
0x1800622c4  mov     rcx, [rax]
0x1800622c7  mov     rax, [rcx+0E0h]
0x1800622ce  xor     r8d, r8d
0x1800622d1  mov     rdx, [r14]
0x1800622d4  mov     rcx, r9
0x1800622d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800622dc  mov     rdx, [rbp+arg_18]; struct Windows::System::Internal::ISignOutResult *
0x1800622e0  test    rdx, rdx
0x1800622e3  jz      short loc_1800622EE
0x1800622e5  mov     rcx, rsi; this
0x1800622e8  call    ?FireSignOutComplete@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUISignOutResult@234@@Z; Windows::System::Internal::UserManagerStatics::FireSignOutComplete(Windows::System::Internal::ISignOutResult *)
0x1800622ed  nop
0x1800622ee  jmp     loc_180062489
0x1800622f3  mov     rdx, [rbp+arg_20]; void *
0x1800622f7  call    ?CheckCancelEvent@UserManagerStatics@Internal@System@Windows@@AEAAJPEAX@Z; Windows::System::Internal::UserManagerStatics::CheckCancelEvent(void *)
0x1800622fc  mov     ebx, eax
0x1800622fe  test    eax, eax
0x180062300  jns     short loc_18006235B
0x180062302  mov     rcx, [rbp+38h]; this
0x180062306  mov     r9d, eax; char *
0x180062309  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180062310  mov     edx, 187Fh; void *
0x180062315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006231a  nop
0x18006231b  cmp     [rbp+arg_8], r12b
0x18006231f  jz      short loc_180062344
0x180062321  mov     rcx, rsi; this
0x180062324  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x180062329  mov     r9, rax
0x18006232c  mov     rcx, [rax]
0x18006232f  mov     rax, [rcx+0E0h]
0x180062336  xor     r8d, r8d
0x180062339  mov     rdx, [r14]
0x18006233c  mov     rcx, r9
0x18006233f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062344  mov     rdx, [rbp+arg_18]; struct Windows::System::Internal::ISignOutResult *
0x180062348  test    rdx, rdx
0x18006234b  jz      short loc_180062356
0x18006234d  mov     rcx, rsi; this
0x180062350  call    ?FireSignOutComplete@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUISignOutResult@234@@Z; Windows::System::Internal::UserManagerStatics::FireSignOutComplete(Windows::System::Internal::ISignOutResult *)
0x180062355  nop
0x180062356  jmp     loc_180062489
0x18006235b  cmp     [rbp+arg_0], 2
0x18006235f  jnz     short loc_1800623DC
0x180062361  lea     r8, aSignoutsponsor; "SignOutSponsoredUser"
0x180062368  xor     edx, edx
0x18006236a  mov     ecx, r15d
0x18006236d  call    Windows__System__Internal__LogSignOutUserReason
0x180062372  mov     edx, r15d; unsigned int
0x180062375  mov     rcx, rsi; this
0x180062378  call    ?SignOutOfAuthManager@UserManagerStatics@Internal@System@Windows@@AEAAJI@Z; Windows::System::Internal::UserManagerStatics::SignOutOfAuthManager(uint)
0x18006237d  mov     ebx, eax
0x18006237f  test    eax, eax
0x180062381  jns     short loc_1800623DC
0x180062383  mov     rcx, [rbp+38h]; this
0x180062387  mov     r9d, eax; char *
0x18006238a  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180062391  mov     edx, 1885h; void *
0x180062396  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006239b  nop
0x18006239c  cmp     [rbp+arg_8], r12b
0x1800623a0  jz      short loc_1800623C5
0x1800623a2  mov     rcx, rsi; this
0x1800623a5  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x1800623aa  mov     r9, rax
0x1800623ad  mov     rcx, [rax]
0x1800623b0  mov     rax, [rcx+0E0h]
0x1800623b7  xor     r8d, r8d
0x1800623ba  mov     rdx, [r14]
0x1800623bd  mov     rcx, r9
0x1800623c0  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
