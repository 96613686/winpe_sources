# CShareWithListItemBase::_UpdateCheckBox(void)

- ea: `0x1800119e0`
- end: `0x180011a9c`
- name: `?_UpdateCheckBox@CShareWithListItemBase@@MEAAJXZ`
- size: `188`
- prototype: `__int64 __fastcall(CShareWithListItemBase *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180003860`
- `0x180003888`
- `0x180004358`
- `0x18000e460`
- `0x1800108b8`
- `0x1800119e0`

## pseudocode

```c
__int64 __fastcall CShareWithListItemBase::_UpdateCheckBox(CShareWithListItemBase *this)
{
  _QWORD *v2; // rcx
  CDeviceSettings *v3; // rax
  int AuthorizationStatus; // ebx
  char v5; // si
  int v7; // [rsp+50h] [rbp+8h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = (CDeviceSettings *)*((_QWORD *)this + 27);
  AuthorizationStatus = 0;
  if ( v3 )
  {
    v7 = 0;
    AuthorizationStatus = CDeviceSettings::GetAuthorizationStatus(v3, (enum AuthorizationStatus *)&v7);
    if ( AuthorizationStatus >= 0 )
    {
      v5 = v7 == 2;
      if ( v5 != CShareWithListItemBase::_GetCheckedStateProp(this) )
        CShareWithListItemBase::_SetCheckedStateProp(this, v5);
    }
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 206, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, (unsigned int)AuthorizationStatus);
  return (unsigned int)AuthorizationStatus;
}

```

## disassembly

```asm
0x1800119e0  push    rbx
0x1800119e2  push    rbp
0x1800119e3  push    rsi
0x1800119e4  push    rdi
0x1800119e5  sub     rsp, 28h
0x1800119e9  mov     rdi, rcx
0x1800119ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119f3  lea     rbp, WPP_GLOBAL_Control
0x1800119fa  cmp     rcx, rbp
0x1800119fd  jz      short loc_180011A21
0x1800119ff  test    byte ptr [rcx+1Ch], 20h
0x180011a03  jz      short loc_180011A21
0x180011a05  mov     rcx, [rcx+10h]
0x180011a09  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011a10  mov     edx, 0CDh
0x180011a15  call    WPP_SF_
0x180011a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a21  mov     rax, [rdi+0D8h]
0x180011a28  xor     ebx, ebx
0x180011a2a  test    rax, rax
0x180011a2d  jz      short loc_180011A6E
0x180011a2f  lea     rdx, [rsp+48h+arg_0]; enum AuthorizationStatus *
0x180011a34  mov     [rsp+48h+arg_0], ebx
0x180011a38  mov     rcx, rax; this
0x180011a3b  call    ?GetAuthorizationStatus@CDeviceSettings@@QEAAJPEAW4AuthorizationStatus@@@Z; CDeviceSettings::GetAuthorizationStatus(AuthorizationStatus *)
0x180011a40  mov     ebx, eax
0x180011a42  test    eax, eax
0x180011a44  js      short loc_180011A67
0x180011a46  cmp     [rsp+48h+arg_0], 2
0x180011a4b  mov     rcx, rdi; this
0x180011a4e  setz    sil
0x180011a52  call    ?_GetCheckedStateProp@CShareWithListItemBase@@IEAA_NXZ; CShareWithListItemBase::_GetCheckedStateProp(void)
0x180011a57  cmp     sil, al
0x180011a5a  jz      short loc_180011A67
0x180011a5c  mov     dl, sil; bool
0x180011a5f  mov     rcx, rdi; this
0x180011a62  call    ?_SetCheckedStateProp@CShareWithListItemBase@@IEAAX_N@Z; CShareWithListItemBase::_SetCheckedStateProp(bool)
0x180011a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a6e  cmp     rcx, rbp
0x180011a71  jz      short loc_180011A91
0x180011a73  test    byte ptr [rcx+1Ch], 20h
0x180011a77  jz      short loc_180011A91
0x180011a79  mov     rcx, [rcx+10h]
0x180011a7d  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011a84  mov     edx, 0CEh
0x180011a89  mov     r9d, ebx
0x180011a8c  call    WPP_SF_d
0x180011a91  mov     eax, ebx
0x180011a93  add     rsp, 28h
0x180011a97  pop     rdi
0x180011a98  pop     rsi
0x180011a99  pop     rbp
0x180011a9a  pop     rbx
0x180011a9b  retn
```
