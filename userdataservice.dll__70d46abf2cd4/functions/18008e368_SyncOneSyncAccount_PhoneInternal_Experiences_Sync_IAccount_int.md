# SyncOneSyncAccount(PhoneInternal::Experiences::Sync::IAccount *,int *)

- ea: `0x18008e368`
- end: `0x18008e80c`
- name: `?SyncOneSyncAccount@@YAJPEAUIAccount@Sync@Experiences@PhoneInternal@@PEAH@Z`
- size: `1188`
- prototype: `__int64 __fastcall(struct PhoneInternal::Experiences::Sync::IAccount *, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a3470`

## callees

- `0x180008f0c`
- `0x1800303cc`
- `0x180065fb0`
- `0x18007be90`
- `0x18008e368`
- `0x18008e814`
- `0x18008e868`
- `0x180097db8`
- `0x1800b95dc`
- `0x1800b97bc`
- `0x1800b9c68`
- `0x1800bacdc`
- `0x1800bc620`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e6e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e6e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008e3c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008e3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e701`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18008e5f3`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18008e5f3`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18008e621`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18008e621`

## string_xrefs

- `0x18008e46e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18008e4b5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18008e51d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18008e5a6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18008e603`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18008e696`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18008e71c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`

## pseudocode

```c
__int64 __fastcall SyncOneSyncAccount(struct PhoneInternal::Experiences::Sync::IAccount *a1, int *a2)
{
  __int64 *v3; // rbx
  utl::_RefCountBase *v4; // r15
  utl::_RefCountBase *v5; // r12
  HANDLE v6; // rsi
  utl::_RefCountBase *v7; // rbx
  signed int LastError; // eax
  unsigned int v9; // edi
  utl::_RefCountBase *v10; // rcx
  void *v12; // rbx
  int v13; // eax
  int AccountLastSyncResult; // esi
  __int64 v15; // rax
  int v16; // eax
  void **v17; // rax
  int RpcClientThreadToken; // eax
  __int64 v19; // r9
  DWORD v20; // eax
  signed int v21; // eax
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE token; // [rsp+38h] [rbp-C8h] BYREF
  void *EventW; // [rsp+40h] [rbp-C0h] BYREF
  struct PhoneInternal::Experiences::Sync::IAccount *v25; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 packageFullNameLength; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v28; // [rsp+68h] [rbp-98h] BYREF
  struct PhoneInternal::Experiences::Sync::IAccount **p_EventW; // [rsp+70h] [rbp-90h]
  char v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v32[3]; // [rsp+88h] [rbp-78h] BYREF
  char v33; // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall *v34)(); // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v35[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v36; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR packageFullName[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v38[252]; // [rsp+D4h] [rbp-2Ch] BYREF

  v25 = a1;
  if ( a2 )
    *a2 = 0;
  *(_OWORD *)hHandle = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  p_EventW = (struct PhoneInternal::Experiences::Sync::IAccount **)&EventW;
  v3 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v28 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 2) = 1;
    v4 = (utl::_RefCountBase *)v3;
    *((_DWORD *)v3 + 3) = 1;
    hHandle[1] = v3;
    *v3 = (__int64)&utl::_RefCountVtable<utl::_RefCountNormal<void *,tlx::smart_xxx<void *,int (*)(void *),&int CloseHandle(void *),0,utl::allocator<int>>::_Deleter,utl::allocator<int>>,0>::`vftable';
    v5 = (utl::_RefCountBase *)v3;
    v3[2] = (__int64)EventW;
    v6 = EventW;
    hHandle[0] = EventW;
  }
  else
  {
    v6 = hHandle[0];
    v5 = 0;
    v4 = 0;
  }
  utl::_SharedBase<void *>::_SharedReset<void *,tlx::smart_xxx<void *,int (*)(void *),&int CloseHandle(void *),0,utl::allocator<int>>::_Deleter,utl::allocator<int>>::~_SharedReset<void *,tlx::smart_xxx<void *,int (*)(void *),&int CloseHandle(void *),0,utl::allocator<int>>::_Deleter,utl::allocator<int>>(&v28);
  if ( !v6 )
  {
    v7 = v4;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
    {
      v7 = v5;
      v9 = (unsigned __int16)LastError | 0x80070000;
    }
    Log_HREvent(
      v9,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      420);
    if ( !v7 )
      return v9;
    v10 = v7;
LABEL_11:
    utl::_RefCountBase::_DecStrong(v10);
    return v9;
  }
  Microsoft::WRL::Details::Make<AccountSyncDoneEventListener,tlx::smart_xxx<void *,int (*)(void *),&int CloseHandle(void *),0,utl::allocator<int>> &,PhoneInternal::Experiences::Sync::IAccount * &>(
    (__int64 *)&EventW,
    (__int64)hHandle,
    &v25);
  v12 = EventW;
  if ( !EventW )
  {
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      424);
    if ( hHandle[1] )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)hHandle[1]);
    return 2147942414LL;
  }
  v31 = 0;
  v13 = (*(__int64 (__fastcall **)(struct PhoneInternal::Experiences::Sync::IAccount *, _QWORD, __int64 *))(*(_QWORD *)v25 + 264LL))(
          v25,
          ((unsigned __int64)EventW + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)EventW >> 64),
          &v31);
  AccountLastSyncResult = v13;
  if ( v13 < 0 )
  {
    Log_HREvent(
      (unsigned int)v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      427);
    if ( !v12 )
    {
LABEL_20:
      if ( hHandle[1] )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)hHandle[1]);
      return (unsigned int)AccountLastSyncResult;
    }
LABEL_19:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_20;
  }
  v28 = &v31;
  v22 = -2147024638;
  p_EventW = &v25;
  v36 = 0;
  v15 = *(_QWORD *)v25;
  v30 = 1;
  v16 = (*(__int64 (__fastcall **)(struct PhoneInternal::Experiences::Sync::IAccount *, __int128 *))(v15 + 48))(
          v25,
          &v36);
  if ( v16 < 0 )
    Log_HREvent(
      (unsigned int)v16,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      438);
  *(_DWORD *)packageFullName = 0;
  memset_0(v38, 0, sizeof(v38));
  token = 0;
  packageFullNameLength = 128;
  v17 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&token);
  RpcClientThreadToken = GetRpcClientThreadToken(8u, v17);
  if ( RpcClientThreadToken < 0 )
    Log_HREvent(
      (unsigned int)RpcClientThreadToken,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      444);
  if ( GetPackageFullNameFromToken(token, &packageFullNameLength, packageFullName) )
    StringCchCopyW(packageFullName, 0x80u, L"unknown");
  v33 = 1;
  v32[0] = &v22;
  v32[1] = &v36;
  v32[2] = packageFullName;
  v34 =  PhoneInternal::Experiences::Sync::IAccount::`vcall'{232,{flat}};
  EventW = v25;
  v35[0] = &EventW;
  v35[1] = &v34;
  AccountLastSyncResult = AwaitActionHelper<_lambda_0a04c088c418f83e521919b7295e2107_>(v35);
  if ( AccountLastSyncResult < 0 )
  {
    v19 = 456;
    goto LABEL_31;
  }
  v20 = WaitForSingleObject(hHandle[0], 0x493E0u);
  if ( v20 != 258 && v20 != 128 )
  {
    if ( v20 )
    {
      v21 = GetLastError();
      v9 = v21;
      if ( v21 > 0 )
        v9 = (unsigned __int16)v21 | 0x80070000;
      Log_HREvent(
        v9,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
        465);
      tlx::_UndoSolo__lambda_b941832d1cda31d037850739a92ad07b___::__UndoSolo__lambda_b941832d1cda31d037850739a92ad07b___(v32);
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&token);
      tlx::_UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d___::__UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d___(&v28);
      if ( v12 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
      v10 = (utl::_RefCountBase *)hHandle[1];
      if ( !hHandle[1] )
        return v9;
      goto LABEL_11;
    }
    AccountLastSyncResult = GetAccountLastSyncResult(v25, &v22);
    if ( AccountLastSyncResult < 0 )
    {
      v19 = 468;
LABEL_31:
      Log_HREvent(
        (unsigned int)AccountLastSyncResult,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
        v19);
      tlx::_UndoSolo__lambda_b941832d1cda31d037850739a92ad07b___::__UndoSolo__lambda_b941832d1cda31d037850739a92ad07b___(v32);
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&token);
      tlx::_UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d___::__UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d___(&v28);
      if ( !v12 )
        goto LABEL_20;
      goto LABEL_19;
    }
    if ( (v22 & 0x80000000) == 0 && a2 )
      *a2 = 1;
  }
  tlx::_UndoSolo__lambda_b941832d1cda31d037850739a92ad07b___::__UndoSolo__lambda_b941832d1cda31d037850739a92ad07b___(v32);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&token);
  tlx::_UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d___::__UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d___(&v28);
  if ( v12 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
  if ( hHandle[1] )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)hHandle[1]);
  return 0;
}

```

## disassembly

```asm
0x18008e368  mov     [rsp-8+arg_10], rbx
0x18008e36d  mov     [rsp-8+arg_18], rsi
0x18008e372  push    rbp
0x18008e373  push    rdi
0x18008e374  push    r12
0x18008e376  push    r14
0x18008e378  push    r15
0x18008e37a  lea     rbp, [rsp-0E0h]
0x18008e382  sub     rsp, 1E0h
0x18008e389  mov     rax, cs:__security_cookie
0x18008e390  xor     rax, rsp
0x18008e393  mov     [rbp+100h+var_30], rax
0x18008e39a  mov     [rsp+200h+var_1B8], rcx
0x18008e39f  mov     rdi, rdx
0x18008e3a2  test    rdx, rdx
0x18008e3a5  jz      short loc_18008E3AD
0x18008e3a7  mov     dword ptr [rdx], 0
0x18008e3ad  xorps   xmm0, xmm0
0x18008e3b0  xor     r9d, r9d; lpName
0x18008e3b3  xor     r8d, r8d; bInitialState
0x18008e3b6  xor     edx, edx; bManualReset
0x18008e3b8  xor     ecx, ecx; lpEventAttributes
0x18008e3ba  movdqu  xmmword ptr [rsp+200h+hHandle], xmm0
0x18008e3c0  call    cs:__imp_CreateEventW
0x18008e3c6  mov     [rsp+200h+var_1C0], rax
0x18008e3cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008e3d2  lea     rax, [rsp+200h+var_1C0]
0x18008e3d7  mov     ecx, 18h; unsigned __int64
0x18008e3dc  mov     [rsp+200h+var_190], rax
0x18008e3e1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008e3e6  mov     rbx, rax
0x18008e3e9  mov     [rsp+200h+var_198], rax
0x18008e3ee  mov     eax, 1
0x18008e3f3  test    rbx, rbx
0x18008e3f6  jz      short loc_18008E42B
0x18008e3f8  mov     [rbx+8], eax
0x18008e3fb  mov     r15, rbx
0x18008e3fe  mov     [rbx+0Ch], eax
0x18008e401  mov     r14, rbx
0x18008e404  lea     rax, ??_7?$_RefCountVtable@V?$_RefCountNormal@PEAXU_Deleter@?$smart_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@V?$allocator@H@utl@@@tlx@@V?$allocator@H@utl@@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountNormal<void *,tlx::smart_xxx<void *,int (*)(void *),&CloseHandle(void *),0,utl::allocator<int>>::_Deleter,utl::allocator<int>>,0>::`vftable'
0x18008e40b  mov     [rsp+200h+hHandle+8], rbx
0x18008e410  mov     [rbx], rax
0x18008e413  mov     r12, rbx
0x18008e416  mov     rax, [rsp+200h+var_1C0]
0x18008e41b  mov     [rbx+10h], rax
0x18008e41f  mov     rsi, [rsp+200h+var_1C0]
0x18008e424  mov     [rsp+200h+hHandle], rsi
0x18008e429  jmp     short loc_18008E439
0x18008e42b  mov     rsi, [rsp+200h+hHandle]
0x18008e430  xor     r14d, r14d
0x18008e433  xor     r12d, r12d
0x18008e436  xor     r15d, r15d
0x18008e439  lea     rcx, [rsp+200h+var_198]
0x18008e43e  call    ??1?$_SharedReset@PEAXU_Deleter@?$smart_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@V?$allocator@H@utl@@@tlx@@V?$allocator@H@utl@@@?$_SharedBase@PEAX@utl@@QEAA@XZ; utl::_SharedBase<void *>::_SharedReset<void *,tlx::smart_xxx<void *,int (*)(void *),&CloseHandle(void *),0,utl::allocator<int>>::_Deleter,utl::allocator<int>>::~_SharedReset<void *,tlx::smart_xxx<void *,int (*)(void *),&CloseHandle(void *),0,utl::allocator<int>>::_Deleter,utl::allocator<int>>(void)
0x18008e443  test    rsi, rsi
0x18008e446  cmovz   r14, r12
0x18008e44a  cmovz   rbx, r15
0x18008e44e  jnz     short loc_18008E492
0x18008e450  call    cs:__imp_GetLastError
0x18008e456  mov     edi, eax
0x18008e458  test    eax, eax
0x18008e45a  jle     short loc_18008E468
0x18008e45c  movzx   edi, ax
0x18008e45f  mov     rbx, r14
0x18008e462  or      edi, 80070000h
0x18008e468  mov     r9d, 1A4h
0x18008e46e  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008e475  xor     edx, edx
0x18008e477  mov     ecx, edi
0x18008e479  call    Log_HREvent
0x18008e47e  test    rbx, rbx
0x18008e481  jz      short loc_18008E48B
0x18008e483  mov     rcx, rbx; this
0x18008e486  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18008e48b  mov     eax, edi
0x18008e48d  jmp     loc_18008E7E1
0x18008e492  lea     r8, [rsp+200h+var_1B8]
0x18008e497  lea     rdx, [rsp+200h+hHandle]
0x18008e49c  lea     rcx, [rsp+200h+var_1C0]
0x18008e4a1  call    ??$Make@VAccountSyncDoneEventListener@@AEAV?$smart_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@V?$allocator@H@utl@@@tlx@@AEAPEAUIAccount@Sync@Experiences@PhoneInternal@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAccountSyncDoneEventListener@@@12@AEAV?$smart_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@V?$allocator@H@utl@@@tlx@@AEAPEAUIAccount@Sync@Experiences@PhoneInternal@@@Z; Microsoft::WRL::Details::Make<AccountSyncDoneEventListener,tlx::smart_xxx<void *,int (*)(void *),&CloseHandle(void *),0,utl::allocator<int>> &,PhoneInternal::Experiences::Sync::IAccount * &>(tlx::smart_xxx<void *,int (*)(void *),&CloseHandle(void *),0,utl::allocator<int>> &,PhoneInternal::Experiences::Sync::IAccount * &)
0x18008e4a6  mov     rbx, [rsp+200h+var_1C0]
0x18008e4ab  test    rbx, rbx
0x18008e4ae  jnz     short loc_18008E4E1
0x18008e4b0  mov     ebx, 8007000Eh
0x18008e4b5  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008e4bc  mov     ecx, ebx
0x18008e4be  mov     r9d, 1A8h
0x18008e4c4  xor     edx, edx
0x18008e4c6  call    Log_HREvent
0x18008e4cb  mov     rcx, [rsp+200h+hHandle+8]; this
0x18008e4d0  test    rcx, rcx
0x18008e4d3  jz      short loc_18008E4DA
0x18008e4d5  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18008e4da  mov     eax, ebx
0x18008e4dc  jmp     loc_18008E7E1
0x18008e4e1  mov     rcx, [rsp+200h+var_1B8]
0x18008e4e6  lea     r8, [rbx+8]
0x18008e4ea  mov     [rbp+100h+var_180], 0
0x18008e4f2  mov     rax, rbx
0x18008e4f5  neg     rax
0x18008e4f8  mov     r9, [rcx]
0x18008e4fb  sbb     rdx, rdx
0x18008e4fe  and     rdx, r8
0x18008e501  lea     r8, [rbp+100h+var_180]
0x18008e505  mov     rax, [r9+108h]
0x18008e50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e511  mov     esi, eax
0x18008e513  test    eax, eax
0x18008e515  jns     short loc_18008E55A
0x18008e517  mov     r9d, 1ABh
0x18008e51d  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008e524  mov     edx, 1
0x18008e529  mov     ecx, eax
0x18008e52b  call    Log_HREvent
0x18008e530  test    rbx, rbx
0x18008e533  jz      short loc_18008E544
0x18008e535  mov     rcx, [rbx]
0x18008e538  mov     rax, [rcx+10h]
0x18008e53c  mov     rcx, rbx
0x18008e53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e544  mov     rcx, [rsp+200h+hHandle+8]; this
0x18008e549  test    rcx, rcx
0x18008e54c  jz      short loc_18008E553
0x18008e54e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18008e553  mov     eax, esi
0x18008e555  jmp     loc_18008E7E1
0x18008e55a  mov     rcx, [rsp+200h+var_1B8]
0x18008e55f  lea     rax, [rbp+100h+var_180]
0x18008e563  mov     [rsp+200h+var_198], rax
0x18008e568  lea     rdx, [rbp+100h+var_140]
0x18008e56c  lea     rax, [rsp+200h+var_1B8]
0x18008e571  mov     [rsp+200h+var_1D0], 80070102h
0x18008e579  mov     [rsp+200h+var_190], rax
0x18008e57e  xorps   xmm0, xmm0
0x18008e581  movups  [rbp+100h+var_140], xmm0
0x18008e585  mov     rax, [rcx]
0x18008e588  mov     r14d, 1
0x18008e58e  mov     [rsp+200h+var_188], r14b
0x18008e593  mov     rax, [rax+30h]
0x18008e597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e59c  test    eax, eax
0x18008e59e  jns     short loc_18008E5B6
0x18008e5a0  mov     r9d, 1B6h
0x18008e5a6  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008e5ad  xor     edx, edx
0x18008e5af  mov     ecx, eax
0x18008e5b1  call    Log_HREvent
0x18008e5b6  xor     edx, edx; Val
0x18008e5b8  mov     dword ptr [rbp+100h+packageFullName], 0
0x18008e5bf  mov     r8d, 0FCh; Size
0x18008e5c5  lea     rcx, [rbp+100h+var_12C]; void *
0x18008e5c9  call    memset_0
0x18008e5ce  mov     r15d, 80h
0x18008e5d4  mov     [rsp+200h+token], 0
0x18008e5dd  lea     rcx, [rsp+200h+token]
0x18008e5e2  mov     [rsp+200h+packageFullNameLength], r15d
0x18008e5e7  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x18008e5ec  mov     rdx, rax
0x18008e5ef  lea     ecx, [r15-78h]
0x18008e5f3  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x18008e5f9  test    eax, eax
0x18008e5fb  jns     short loc_18008E613
0x18008e5fd  mov     r9d, 1BCh
0x18008e603  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008e60a  xor     edx, edx
0x18008e60c  mov     ecx, eax
0x18008e60e  call    Log_HREvent
0x18008e613  mov     rcx, [rsp+200h+token]; token
0x18008e618  lea     r8, [rbp+100h+packageFullName]; packageFullName
0x18008e61c  lea     rdx, [rsp+200h+packageFullNameLength]; packageFullNameLength
0x18008e621  call    cs:__imp_GetPackageFullNameFromToken
0x18008e627  test    eax, eax
0x18008e629  jz      short loc_18008E63E
0x18008e62b  lea     r8, aUnknown; "unknown"
0x18008e632  mov     rdx, r15; unsigned __int64
0x18008e635  lea     rcx, [rbp+100h+packageFullName]; unsigned __int16 *
0x18008e639  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008e63e  lea     rax, [rsp+200h+var_1D0]
0x18008e643  mov     [rbp+100h+var_160], r14b
0x18008e647  mov     [rbp+100h+var_178], rax
0x18008e64b  lea     rcx, [rbp+100h+var_150]
0x18008e64f  lea     rax, [rbp+100h+var_140]
0x18008e653  mov     [rbp+100h+var_170], rax
0x18008e657  lea     rax, [rbp+100h+packageFullName]
0x18008e65b  mov     [rbp+100h+var_168], rax
0x18008e65f  lea     rax, ??_9IAccount@Sync@Experiences@PhoneInternal@@$BOI@AA; [thunk]: PhoneInternal::Experiences::Sync::IAccount::`vcall'{232,{flat}}
0x18008e666  mov     [rbp+100h+var_158], rax
0x18008e66a  mov     rax, [rsp+200h+var_1B8]
0x18008e66f  mov     [rsp+200h+var_1C0], rax
0x18008e674  lea     rax, [rsp+200h+var_1C0]
0x18008e679  mov     [rbp+100h+var_150], rax
0x18008e67d  lea     rax, [rbp+100h+var_158]
0x18008e681  mov     [rbp+100h+var_148], rax
0x18008e685  call    ??$AwaitActionHelper@V_lambda_0a04c088c418f83e521919b7295e2107_@@@@YAJAEBV_lambda_0a04c088c418f83e521919b7295e2107_@@@Z; AwaitActionHelper<_lambda_0a04c088c418f83e521919b7295e2107_>(_lambda_0a04c088c418f83e521919b7295e2107_ const &)
0x18008e68a  mov     esi, eax
0x18008e68c  test    eax, eax
0x18008e68e  jns     short loc_18008E6D9
0x18008e690  mov     r9d, 1C8h
0x18008e696  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008e69d  mov     edx, r14d
0x18008e6a0  mov     ecx, esi
0x18008e6a2  call    Log_HREvent
0x18008e6a7  lea     rcx, [rbp+100h+var_178]
0x18008e6ab  call    tlx___UndoSolo__lambda_b941832d1cda31d037850739a92ad07b_______UndoSolo__lambda_b941832d1cda31d037850739a92ad07b___
0x18008e6b0  lea     rcx, [rsp+200h+token]
0x18008e6b5  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18008e6ba  lea     rcx, [rsp+200h+var_198]
0x18008e6bf  call    tlx___UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d_______UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d___
0x18008e6c4  test    rbx, rbx
0x18008e6c7  jz      loc_18008E544
0x18008e6cd  mov     rax, [rbx]
0x18008e6d0  mov     rax, [rax+10h]
0x18008e6d4  jmp     loc_18008E53C
0x18008e6d9  mov     rcx, [rsp+200h+hHandle]; hHandle
0x18008e6de  mov     edx, 493E0h; dwMilliseconds
0x18008e6e3  call    cs:__imp_WaitForSingleObject
0x18008e6e9  cmp     eax, 102h
0x18008e6ee  jz      loc_18008E79F
0x18008e6f4  cmp     eax, r15d
0x18008e6f7  jz      loc_18008E79F
0x18008e6fd  test    eax, eax
0x18008e6ff  jz      short loc_18008E770
0x18008e701  call    cs:__imp_GetLastError
0x18008e707  mov     edi, eax
0x18008e709  test    eax, eax
0x18008e70b  jle     short loc_18008E716
0x18008e70d  movzx   edi, ax
0x18008e710  or      edi, 80070000h
0x18008e716  mov     r9d, 1D1h
0x18008e71c  lea     r8, aOnecoreuapBase_90; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008e723  xor     edx, edx
0x18008e725  mov     ecx, edi
0x18008e727  call    Log_HREvent
0x18008e72c  lea     rcx, [rbp+100h+var_178]
0x18008e730  call    tlx___UndoSolo__lambda_b941832d1cda31d037850739a92ad07b_______UndoSolo__lambda_b941832d1cda31d037850739a92ad07b___
0x18008e735  lea     rcx, [rsp+200h+token]
0x18008e73a  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18008e73f  lea     rcx, [rsp+200h+var_198]
0x18008e744  call    tlx___UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d_______UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d___
0x18008e749  test    rbx, rbx
0x18008e74c  jz      short loc_18008E75D
0x18008e74e  mov     rax, [rbx]
0x18008e751  mov     rcx, rbx
0x18008e754  mov     rax, [rax+10h]
0x18008e758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e75d  mov     rcx, [rsp+200h+hHandle+8]
0x18008e762  test    rcx, rcx
0x18008e765  jz      loc_18008E48B
0x18008e76b  jmp     loc_18008E486
0x18008e770  mov     rcx, [rsp+200h+var_1B8]; struct PhoneInternal::Experiences::Sync::IAccount *
0x18008e775  lea     rdx, [rsp+200h+var_1D0]; unsigned int *
0x18008e77a  call    ?GetAccountLastSyncResult@@YAJPEAUIAccount@Sync@Experiences@PhoneInternal@@PEAK@Z; GetAccountLastSyncResult(PhoneInternal::Experiences::Sync::IAccount *,ulong *)
0x18008e77f  mov     esi, eax
0x18008e781  test    eax, eax
0x18008e783  jns     short loc_18008E790
0x18008e785  mov     r9d, 1D4h
0x18008e78b  jmp     loc_18008E696
0x18008e790  cmp     [rsp+200h+var_1D0], 0
0x18008e795  jl      short loc_18008E79F
0x18008e797  test    rdi, rdi
0x18008e79a  jz      short loc_18008E79F
0x18008e79c  mov     [rdi], r14d
0x18008e79f  lea     rcx, [rbp+100h+var_178]
0x18008e7a3  call    tlx___UndoSolo__lambda_b941832d1cda31d037850739a92ad07b_______UndoSolo__lambda_b941832d1cda31d037850739a92ad07b___
0x18008e7a8  lea     rcx, [rsp+200h+token]
0x18008e7ad  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18008e7b2  lea     rcx, [rsp+200h+var_198]
0x18008e7b7  call    tlx___UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d_______UndoSolo__lambda_b8d62eb3d31da301e462f0200775604d___
0x18008e7bc  test    rbx, rbx
0x18008e7bf  jz      short loc_18008E7D0
0x18008e7c1  mov     rax, [rbx]
0x18008e7c4  mov     rcx, rbx
0x18008e7c7  mov     rax, [rax+10h]
0x18008e7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e7d0  mov     rcx, [rsp+200h+hHandle+8]; this
0x18008e7d5  test    rcx, rcx
0x18008e7d8  jz      short loc_18008E7DF
0x18008e7da  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18008e7df  xor     eax, eax
0x18008e7e1  mov     rcx, [rbp+100h+var_30]
0x18008e7e8  xor     rcx, rsp; StackCookie
0x18008e7eb  call    __security_check_cookie
0x18008e7f0  lea     r11, [rsp+200h+var_20]
0x18008e7f8  mov     rbx, [r11+40h]
0x18008e7fc  mov     rsi, [r11+48h]
0x18008e800  mov     rsp, r11
0x18008e803  pop     r15
0x18008e805  pop     r14
0x18008e807  pop     r12
0x18008e809  pop     rdi
0x18008e80a  pop     rbp
0x18008e80b  retn
```
