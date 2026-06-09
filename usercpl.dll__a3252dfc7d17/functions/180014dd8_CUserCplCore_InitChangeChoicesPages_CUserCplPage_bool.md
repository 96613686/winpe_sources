# CUserCplCore::InitChangeChoicesPages(CUserCplPage *,bool)

- ea: `0x180014dd8`
- end: `0x1800151d1`
- name: `?InitChangeChoicesPages@CUserCplCore@@AEAAJPEAVCUserCplPage@@_N@Z`
- size: `1017`
- prototype: `__int64 __fastcall(CUserCplCore *__hidden this, struct CUserCplPage *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180015768`

## callees

- `0x18000b6dc`
- `0x18000b7f0`
- `0x18000bb38`
- `0x180014dd8`
- `0x180015f4c`
- `0x180017f9c`
- `0x180017ffc`
- `0x180018e78`
- `0x180078010`

## import_xrefs

- `SHELL32!__imp_WPC_InstallState` at `0x180014ea0`
- `SHELL32!__imp_WPC_InstallState` at `0x180014ea0`
- `netutils!NetApiBufferFree` at `0x180014e57`
- `netutils!NetApiBufferFree` at `0x180014e57`
- `wkscli!NetGetJoinInformation` at `0x180014e40`
- `wkscli!NetGetJoinInformation` at `0x180014e40`

## string_xrefs

- `0x180015052`: `navCreateMyPassword`
- `0x18001509b`: `navCreatePassword`
- `0x18001510f`: `navDeleteAccount`
- `0x180015121`: `NoDeleteAdminNote`
- `0x18001515d`: `navAdminTasks`

## pseudocode

```c
__int64 __fastcall CUserCplCore::InitChangeChoicesPages(CUserManager **this, struct CUserCplPage *a2, char a3)
{
  unsigned int v5; // ebx
  struct CUserData *SelectedUser; // rsi
  int v7; // eax
  int v8; // edi
  _NETSETUP_JOIN_STATUS v9; // ecx
  bool v10; // r12
  bool IsConnected; // al
  bool v12; // r15
  int v13; // eax
  CUserManager *v14; // rbx
  __int64 v15; // r13
  char v16; // r12
  __int64 v17; // rax
  int v18; // esi
  int v19; // eax
  int v20; // r9d
  int v21; // r13d
  const unsigned __int16 *v22; // rdx
  int v23; // r12d
  bool v24; // r13
  int v25; // eax
  CUserManager *v26; // rcx
  int v27; // ebx
  int v28; // eax
  int v29; // r8d
  int v30; // r9d
  int v31; // r8d
  int v32; // r9d
  bool v33; // bl
  BOOL v34; // r8d
  BOOL v35; // r8d
  BOOL v36; // r8d
  int v37; // r9d
  int v38; // r9d
  int v39; // r9d
  int v40; // r9d
  int v41; // r9d
  bool v43; // [rsp+20h] [rbp-68h]
  int v44; // [rsp+24h] [rbp-64h]
  int v45; // [rsp+28h] [rbp-60h]
  BOOL v46; // [rsp+2Ch] [rbp-5Ch]
  BOOL v47; // [rsp+30h] [rbp-58h]
  int v48; // [rsp+34h] [rbp-54h]
  int v49; // [rsp+38h] [rbp-50h]
  _NETSETUP_JOIN_STATUS BufferType; // [rsp+90h] [rbp+8h] BYREF
  LPWSTR NameBuffer; // [rsp+98h] [rbp+10h] BYREF
  char v52; // [rsp+A0h] [rbp+18h]
  bool v53; // [rsp+A8h] [rbp+20h]

  v52 = a3;
  v5 = -2147467259;
  SelectedUser = CUserManager::GetSelectedUser(this[2]);
  if ( !SelectedUser )
    return v5;
  v7 = `IsOS_OS_DOMAINMEMBER'::`2'::s_bIsDomainMember;
  v8 = 1;
  if ( !`IsOS_OS_DOMAINMEMBER'::`2'::s_bIsDomainMember )
  {
    NameBuffer = 0;
    BufferType = NetSetupUnknownStatus;
    if ( NetGetJoinInformation(0, &NameBuffer, &BufferType) )
    {
      v9 = NetSetupUnknownStatus;
    }
    else
    {
      if ( NameBuffer )
        NetApiBufferFree(NameBuffer);
      v9 = BufferType;
    }
    v7 = (v9 != NetSetupDomainName) + 1;
    `IsOS_OS_DOMAINMEMBER'::`2'::s_bIsDomainMember = v7;
  }
  v10 = v7 == 1;
  IsConnected = CUserData::IsConnected(SelectedUser);
  BufferType = NetSetupUnknownStatus;
  v12 = IsConnected;
  v47 = 0;
  if ( (int)WPC_InstallState(&BufferType) >= 0 )
    v47 = BufferType == NetSetupUnknownStatus;
  v13 = IsOS_OS_ANYSERVER();
  v14 = this[2];
  v49 = v13;
  v15 = *(_QWORD *)v14;
  if ( !v10 )
  {
    v43 = 0;
    v23 = (*(__int64 (__fastcall **)(CUserManager *, struct CUserData *))(v15 + 128))(v14, SelectedUser);
    if ( *((_QWORD *)SelectedUser + 3) )
      v24 = (unsigned int)CUserData::GrabIntProp(SelectedUser, v22) == 3;
    else
      v24 = 0;
    v25 = (*(__int64 (__fastcall **)(struct CUserData *))(*(_QWORD *)SelectedUser + 32LL))(SelectedUser);
    v26 = this[2];
    v27 = v25;
    v53 = v25 == 0;
    v28 = (*(__int64 (__fastcall **)(CUserManager *, struct CUserData *))(*(_QWORD *)v26 + 120LL))(v26, SelectedUser);
    LOBYTE(NameBuffer) = v27 && v28;
    v46 = v23 != 0;
    if ( v52 || !v23 )
    {
      LOBYTE(BufferType) = 0;
      v18 = 0;
      if ( !v23 )
      {
LABEL_28:
        v44 = 0;
LABEL_29:
        if ( !v28 || (v45 = 1, v12) )
          v45 = 0;
        v16 = (char)NameBuffer;
        v21 = 0;
        v48 = 1;
        goto LABEL_33;
      }
    }
    else
    {
      LOBYTE(BufferType) = 1;
      if ( v24 && *((int *)this[2] + 11) <= 1 )
      {
        LOBYTE(BufferType) = 0;
        v18 = 1;
      }
      else
      {
        v18 = 0;
      }
    }
    v44 = 1;
    if ( !v12 )
      goto LABEL_29;
    goto LABEL_28;
  }
  LOBYTE(BufferType) = 0;
  v16 = 0;
  v53 = 0;
  v17 = (*(__int64 (__fastcall **)(CUserManager *))(v15 + 152))(v14);
  v46 = 0;
  v18 = 0;
  v44 = 0;
  v48 = 0;
  v45 = 0;
  v19 = (*(__int64 (__fastcall **)(CUserManager *, __int64))(v15 + 128))(v14, v17);
  v21 = 1;
  v43 = v19 != 0;
LABEL_33:
  if ( !*((_DWORD *)this + 27) || (v29 = 1, v49) )
    v29 = 0;
  SetVisibleElement(a2, L"actionShowSettingsApp", v29, v20);
  if ( !v16 || (v31 = 1, *((_DWORD *)this + 27)) )
    v31 = 0;
  SetVisibleElement(a2, L"navCreateMyPassword", v31, v30);
  v33 = v53;
  v34 = v53 && !*((_DWORD *)this + 27);
  SetVisibleElement(a2, L"navChangeMyPassword", v34, v32);
  v35 = v16 && !v12;
  SetVisibleNavigateButton(a2, L"navCreatePassword", v35);
  v36 = v33 && !v12;
  SetVisibleNavigateButton(a2, L"navChangePassword", v36);
  SetVisibleNavigateButton(a2, L"navChangeAccountType", v46);
  SetVisibleElement(a2, L"shieldAccountType", v46, v37);
  SetVisibleNavigateButton(a2, L"actionGotoParentalControls", v47);
  SetVisibleNavigateButton(a2, L"navDeleteAccount", (unsigned __int8)BufferType);
  SetVisibleElement(a2, L"NoDeleteAdminNote", v18, v38);
  SetVisibleNavigateButton(a2, L"navChangeMyName", v44);
  SetVisibleNavigateButton(a2, L"navChangeName", v44);
  SetVisibleNavigateButton(a2, L"navAdminTasks", v48);
  SetVisibleElement(a2, L"actionShowAdvancedDialog", v21, v39);
  SetVisibleElement(a2, L"shieldAdvanced", v21, v40);
  if ( !v43 || v12 )
    v8 = 0;
  SetVisibleElement(a2, L"DomainChangePasswordNote", v8, v41);
  return (unsigned int)CUserCplCore::_InitNavPane((CUserCplCore *)this, v45);
}

```

## disassembly

```asm
0x180014dd8  mov     [rsp+arg_10], r8b
0x180014ddd  push    rbx
0x180014dde  push    rbp
0x180014ddf  push    rsi
0x180014de0  push    rdi
0x180014de1  push    r12
0x180014de3  push    r13
0x180014de5  push    r14
0x180014de7  push    r15
0x180014de9  sub     rsp, 48h
0x180014ded  mov     rbp, rcx
0x180014df0  mov     r14, rdx
0x180014df3  mov     rcx, [rcx+10h]; this
0x180014df7  mov     ebx, 80004005h
0x180014dfc  call    ?GetSelectedUser@CUserManager@@QEAAPEAVCUserData@@XZ; CUserManager::GetSelectedUser(void)
0x180014e01  xor     r13d, r13d
0x180014e04  mov     rsi, rax
0x180014e07  test    rax, rax
0x180014e0a  jz      loc_1800151BE
0x180014e10  mov     eax, cs:?s_bIsDomainMember@?1??IsOS_OS_DOMAINMEMBER@@YAHXZ@4W4TRIBIT@@A; TRIBIT `IsOS_OS_DOMAINMEMBER(void)'::`2'::s_bIsDomainMember
0x180014e16  lea     edi, [r13+1]
0x180014e1a  test    eax, eax
0x180014e1c  jnz     short loc_180014E7A
0x180014e1e  lea     r8, [rsp+88h+BufferType]; BufferType
0x180014e26  mov     [rsp+88h+NameBuffer], r13
0x180014e2e  lea     rdx, [rsp+88h+NameBuffer]; lpNameBuffer
0x180014e36  mov     [rsp+88h+BufferType], r13d
0x180014e3e  xor     ecx, ecx; lpServer
0x180014e40  call    cs:__imp_NetGetJoinInformation
0x180014e46  test    eax, eax
0x180014e48  jnz     short loc_180014E66
0x180014e4a  mov     rcx, [rsp+88h+NameBuffer]; Buffer
0x180014e52  test    rcx, rcx
0x180014e55  jz      short loc_180014E5D
0x180014e57  call    cs:__imp_NetApiBufferFree
0x180014e5d  mov     ecx, [rsp+88h+BufferType]
0x180014e64  jmp     short loc_180014E69
0x180014e66  mov     ecx, r13d
0x180014e69  cmp     ecx, 3
0x180014e6c  mov     eax, r13d
0x180014e6f  setnz   al
0x180014e72  add     eax, edi
0x180014e74  mov     cs:?s_bIsDomainMember@?1??IsOS_OS_DOMAINMEMBER@@YAHXZ@4W4TRIBIT@@A, eax; TRIBIT `IsOS_OS_DOMAINMEMBER(void)'::`2'::s_bIsDomainMember
0x180014e7a  cmp     eax, edi
0x180014e7c  mov     rcx, rsi; this
0x180014e7f  setz    r12b
0x180014e83  call    ?IsConnected@CUserData@@QEAA_NXZ; CUserData::IsConnected(void)
0x180014e88  lea     rcx, [rsp+88h+BufferType]
0x180014e90  mov     [rsp+88h+BufferType], r13d
0x180014e98  mov     r15b, al
0x180014e9b  mov     [rsp+88h+var_58], r13d
0x180014ea0  call    cs:__imp_WPC_InstallState
0x180014ea6  test    eax, eax
0x180014ea8  js      short loc_180014EBC
0x180014eaa  cmp     [rsp+88h+BufferType], r13d
0x180014eb2  mov     eax, r13d
0x180014eb5  cmovz   eax, edi
0x180014eb8  mov     [rsp+88h+var_58], eax
0x180014ebc  call    ?IsOS_OS_ANYSERVER@@YAHXZ; IsOS_OS_ANYSERVER(void)
0x180014ec1  mov     rbx, [rbp+10h]
0x180014ec5  mov     [rsp+88h+var_50], eax
0x180014ec9  mov     rcx, rbx
0x180014ecc  xor     eax, eax
0x180014ece  mov     r13, [rbx]
0x180014ed1  test    r12b, r12b
0x180014ed4  jz      short loc_180014F2A
0x180014ed6  mov     byte ptr [rsp+88h+BufferType], al
0x180014edd  mov     r12b, al
0x180014ee0  mov     [rsp+88h+arg_18], al
0x180014ee7  mov     rax, [r13+98h]
0x180014eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ef3  xor     edx, edx
0x180014ef5  mov     rcx, rbx
0x180014ef8  mov     [rsp+88h+var_5C], edx
0x180014efc  mov     esi, edx
0x180014efe  mov     [rsp+88h+var_64], edx
0x180014f02  mov     [rsp+88h+var_54], edx
0x180014f06  mov     [rsp+88h+var_60], edx
0x180014f0a  mov     rdx, rax
0x180014f0d  mov     rax, [r13+80h]
0x180014f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f19  xor     ebx, ebx
0x180014f1b  mov     r13d, edi
0x180014f1e  test    eax, eax
0x180014f20  setnz   [rsp+88h+var_68]
0x180014f25  jmp     loc_180015022
0x180014f2a  mov     [rsp+88h+var_68], al
0x180014f2e  mov     rdx, rsi
0x180014f31  mov     rax, [r13+80h]
0x180014f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f3d  cmp     qword ptr [rsi+18h], 0
0x180014f42  mov     r12d, eax
0x180014f45  jz      short loc_180014F58
0x180014f47  mov     rcx, rsi; this
0x180014f4a  call    ?GrabIntProp@CUserData@@IEAAHPEBG@Z; CUserData::GrabIntProp(ushort const *)
0x180014f4f  cmp     eax, 3
0x180014f52  setz    r13b
0x180014f56  jmp     short loc_180014F5B
0x180014f58  xor     r13b, r13b
0x180014f5b  mov     rax, [rsi]
0x180014f5e  mov     rcx, rsi
0x180014f61  mov     rax, [rax+20h]
0x180014f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f6a  mov     rcx, [rbp+10h]
0x180014f6e  test    eax, eax
0x180014f70  mov     ebx, eax
0x180014f72  mov     rdx, rsi
0x180014f75  setz    [rsp+88h+arg_18]
0x180014f7d  mov     rax, [rcx]
0x180014f80  mov     rax, [rax+78h]
0x180014f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f89  mov     edx, eax
0x180014f8b  test    ebx, ebx
0x180014f8d  jz      short loc_180014F9F
0x180014f8f  xor     ebx, ebx
0x180014f91  test    eax, eax
0x180014f93  jz      short loc_180014FA1
0x180014f95  mov     byte ptr [rsp+88h+NameBuffer], dil
0x180014f9d  jmp     short loc_180014FA8
0x180014f9f  xor     ebx, ebx
0x180014fa1  mov     byte ptr [rsp+88h+NameBuffer], bl
0x180014fa8  test    r12d, r12d
0x180014fab  mov     eax, ebx
0x180014fad  setnz   al
0x180014fb0  mov     [rsp+88h+var_5C], eax
0x180014fb4  cmp     [rsp+88h+arg_10], bl
0x180014fbb  jnz     short loc_180014FE7
0x180014fbd  test    r12d, r12d
0x180014fc0  jz      short loc_180014FE7
0x180014fc2  mov     byte ptr [rsp+88h+BufferType], dil
0x180014fca  test    r13b, r13b
0x180014fcd  jz      short loc_180014FE3
0x180014fcf  mov     rax, [rbp+10h]
0x180014fd3  cmp     [rax+2Ch], edi
0x180014fd6  jg      short loc_180014FE3
0x180014fd8  mov     byte ptr [rsp+88h+BufferType], bl
0x180014fdf  mov     esi, edi
0x180014fe1  jmp     short loc_180014FF5
0x180014fe3  mov     esi, ebx
0x180014fe5  jmp     short loc_180014FF5
0x180014fe7  mov     byte ptr [rsp+88h+BufferType], bl
0x180014fee  mov     esi, ebx
0x180014ff0  test    r12d, r12d
0x180014ff3  jz      short loc_180014FFE
0x180014ff5  mov     [rsp+88h+var_64], edi
0x180014ff9  test    r15b, r15b
0x180014ffc  jz      short loc_180015002
0x180014ffe  mov     [rsp+88h+var_64], ebx
0x180015002  test    edx, edx
0x180015004  jz      short loc_18001500F
0x180015006  mov     [rsp+88h+var_60], edi
0x18001500a  test    r15b, r15b
0x18001500d  jz      short loc_180015013
0x18001500f  mov     [rsp+88h+var_60], ebx
0x180015013  mov     r12b, byte ptr [rsp+88h+NameBuffer]
0x18001501b  mov     r13d, ebx
0x18001501e  mov     [rsp+88h+var_54], edi
0x180015022  cmp     [rbp+6Ch], ebx
0x180015025  jz      short loc_180015030
0x180015027  mov     r8d, edi
0x18001502a  cmp     [rsp+88h+var_50], ebx
0x18001502e  jz      short loc_180015033
0x180015030  mov     r8d, ebx; int
0x180015033  lea     rdx, aActionshowsett; "actionShowSettingsApp"
0x18001503a  mov     rcx, r14; struct DirectUI::Element *
0x18001503d  call    ?SetVisibleElement@@YAXPEAVElement@DirectUI@@PEBGHH@Z; SetVisibleElement(DirectUI::Element *,ushort const *,int,int)
0x180015042  test    r12b, r12b
0x180015045  jz      short loc_18001504F
0x180015047  mov     r8d, edi
0x18001504a  cmp     [rbp+6Ch], ebx
0x18001504d  jz      short loc_180015052
0x18001504f  mov     r8d, ebx; int
0x180015052  lea     rdx, aNavcreatemypas; "navCreateMyPassword"
0x180015059  mov     rcx, r14; struct DirectUI::Element *
0x18001505c  call    ?SetVisibleElement@@YAXPEAVElement@DirectUI@@PEBGHH@Z; SetVisibleElement(DirectUI::Element *,ushort const *,int,int)
0x180015061  mov     bl, [rsp+88h+arg_18]
0x180015068  test    bl, bl
0x18001506a  jz      short loc_180015077
0x18001506c  cmp     dword ptr [rbp+6Ch], 0
0x180015070  jnz     short loc_180015077
0x180015072  mov     r8d, edi
0x180015075  jmp     short loc_18001507A
0x180015077  xor     r8d, r8d; int
0x18001507a  lea     rdx, aNavchangemypas; "navChangeMyPassword"
0x180015081  mov     rcx, r14; struct DirectUI::Element *
0x180015084  call    ?SetVisibleElement@@YAXPEAVElement@DirectUI@@PEBGHH@Z; SetVisibleElement(DirectUI::Element *,ushort const *,int,int)
0x180015089  test    r12b, r12b
0x18001508c  jz      short loc_180015098
0x18001508e  test    r15b, r15b
0x180015091  jnz     short loc_180015098
0x180015093  mov     r8d, edi
0x180015096  jmp     short loc_18001509B
0x180015098  xor     r8d, r8d; int
0x18001509b  lea     rdx, aNavcreatepassw; "navCreatePassword"
0x1800150a2  mov     rcx, r14; struct DirectUI::Element *
0x1800150a5  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x1800150aa  test    bl, bl
0x1800150ac  jz      short loc_1800150B8
0x1800150ae  test    r15b, r15b
0x1800150b1  jnz     short loc_1800150B8
0x1800150b3  mov     r8d, edi
0x1800150b6  jmp     short loc_1800150BB
0x1800150b8  xor     r8d, r8d; int
0x1800150bb  lea     rdx, aNavchangepassw; "navChangePassword"
0x1800150c2  mov     rcx, r14; struct DirectUI::Element *
0x1800150c5  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x1800150ca  mov     r8d, [rsp+88h+var_5C]; int
0x1800150cf  lea     rdx, aNavchangeaccou; "navChangeAccountType"
0x1800150d6  mov     rcx, r14; struct DirectUI::Element *
0x1800150d9  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x1800150de  mov     r8d, [rsp+88h+var_5C]; int
0x1800150e3  lea     rdx, aShieldaccountt; "shieldAccountType"
0x1800150ea  mov     rcx, r14; struct DirectUI::Element *
0x1800150ed  call    ?SetVisibleElement@@YAXPEAVElement@DirectUI@@PEBGHH@Z; SetVisibleElement(DirectUI::Element *,ushort const *,int,int)
0x1800150f2  mov     r8d, [rsp+88h+var_58]; int
0x1800150f7  lea     rdx, aActiongotopare; "actionGotoParentalControls"
0x1800150fe  mov     rcx, r14; struct DirectUI::Element *
0x180015101  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x180015106  movzx   r8d, byte ptr [rsp+88h+BufferType]; int
0x18001510f  lea     rdx, aNavdeleteaccou; "navDeleteAccount"
0x180015116  mov     rcx, r14; struct DirectUI::Element *
0x180015119  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x18001511e  mov     r8d, esi; int
0x180015121  lea     rdx, aNodeleteadminn; "NoDeleteAdminNote"
0x180015128  mov     rcx, r14; struct DirectUI::Element *
0x18001512b  call    ?SetVisibleElement@@YAXPEAVElement@DirectUI@@PEBGHH@Z; SetVisibleElement(DirectUI::Element *,ushort const *,int,int)
0x180015130  mov     r8d, [rsp+88h+var_64]; int
0x180015135  lea     rdx, aNavchangemynam; "navChangeMyName"
0x18001513c  mov     rcx, r14; struct DirectUI::Element *
0x18001513f  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x180015144  mov     r8d, [rsp+88h+var_64]; int
0x180015149  lea     rdx, aNavchangename; "navChangeName"
0x180015150  mov     rcx, r14; struct DirectUI::Element *
0x180015153  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x180015158  mov     r8d, [rsp+88h+var_54]; int
0x18001515d  lea     rdx, aNavadmintasks; "navAdminTasks"
0x180015164  mov     rcx, r14; struct DirectUI::Element *
0x180015167  call    ?SetVisibleNavigateButton@@YAXPEAVElement@DirectUI@@PEBGH@Z; SetVisibleNavigateButton(DirectUI::Element *,ushort const *,int)
0x18001516c  mov     r8d, r13d; int
0x18001516f  lea     rdx, aActionshowadva; "actionShowAdvancedDialog"
0x180015176  mov     rcx, r14; struct DirectUI::Element *
0x180015179  call    ?SetVisibleElement@@YAXPEAVElement@DirectUI@@PEBGHH@Z; SetVisibleElement(DirectUI::Element *,ushort const *,int,int)
0x18001517e  mov     r8d, r13d; int
0x180015181  lea     rdx, aShieldadvanced; "shieldAdvanced"
0x180015188  mov     rcx, r14; struct DirectUI::Element *
0x18001518b  call    ?SetVisibleElement@@YAXPEAVElement@DirectUI@@PEBGHH@Z; SetVisibleElement(DirectUI::Element *,ushort const *,int,int)
0x180015190  cmp     [rsp+88h+var_68], 0
0x180015195  jz      short loc_18001519C
0x180015197  test    r15b, r15b
0x18001519a  jz      short loc_18001519E
0x18001519c  xor     edi, edi
0x18001519e  mov     r8d, edi; int
0x1800151a1  lea     rdx, aDomainchangepa; "DomainChangePasswordNote"
0x1800151a8  mov     rcx, r14; struct DirectUI::Element *
0x1800151ab  call    ?SetVisibleElement@@YAXPEAVElement@DirectUI@@PEBGHH@Z; SetVisibleElement(DirectUI::Element *,ushort const *,int,int)
0x1800151b0  mov     edx, [rsp+88h+var_60]; int
0x1800151b4  mov     rcx, rbp; this
0x1800151b7  call    ?_InitNavPane@CUserCplCore@@AEAAJH@Z; CUserCplCore::_InitNavPane(int)
0x1800151bc  mov     ebx, eax
0x1800151be  mov     eax, ebx
0x1800151c0  add     rsp, 48h
0x1800151c4  pop     r15
0x1800151c6  pop     r14
0x1800151c8  pop     r13
0x1800151ca  pop     r12
0x1800151cc  pop     rdi
0x1800151cd  pop     rsi
0x1800151ce  pop     rbp
0x1800151cf  pop     rbx
0x1800151d0  retn
```
