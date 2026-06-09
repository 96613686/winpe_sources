# CShareWithListItemDevice::_UpdatePowerManagementLabel(void)

- ea: `0x180011c20`
- end: `0x180011d90`
- name: `?_UpdatePowerManagementLabel@CShareWithListItemDevice@@EEAAJXZ`
- size: `368`
- prototype: `__int64 __fastcall(CShareWithListItemDevice *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180003860`
- `0x180003888`
- `0x180004358`
- `0x180011c20`

## import_xrefs

- `DUI70!StrToID` at `0x180011c65`
- `DUI70!StrToID` at `0x180011c65`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011c71`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011c71`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180011d43`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180011d43`

## pseudocode

```c
__int64 __fastcall CShareWithListItemDevice::_UpdatePowerManagementLabel(CDeviceSettings **this)
{
  unsigned __int16 v2; // ax
  struct DirectUI::Element *Descendent; // rsi
  CDeviceSettings *v4; // rcx
  unsigned int v5; // edi
  int v6; // ebp
  int v7; // ecx
  int v8; // edx
  CDeviceSettings *v9; // r14
  _QWORD *v10; // rcx
  int v11; // edx
  int v13; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = StrToID(L"PowerManagementMessageBounds");
  Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)this, v2);
  if ( Descendent )
  {
    v4 = this[27];
    v5 = 0;
    v6 = 2;
    v13 = 2;
    v7 = 1;
    if ( v4 )
    {
      CDeviceSettings::GetAuthorizationStatus(v4, (enum AuthorizationStatus *)&v13);
      v6 = v13;
      if ( v13 != 2 )
        v7 = 0;
    }
    v8 = *((_DWORD *)this + 59);
    if ( v8 != (*((_DWORD *)Descendent + 30) == 3) || v8 != v7 )
    {
      if ( *((_DWORD *)Descendent + 30) == 3 )
        goto LABEL_23;
      v9 = this[27];
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
          v10 = WPP_GLOBAL_Control;
        }
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
          WPP_SF_(v10[2], 43, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
      }
      if ( *((_DWORD *)v9 + 23) || v6 != 2 || !*((_DWORD *)this + 59) )
LABEL_23:
        v11 = -3;
      else
        v11 = 3;
      DirectUI::Element::SetLayoutPos(Descendent, v11);
    }
  }
  else
  {
    v5 = -2147467259;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180011c20  push    rbx
0x180011c22  push    rbp
0x180011c23  push    rsi
0x180011c24  push    rdi
0x180011c25  push    r12
0x180011c27  push    r14
0x180011c29  sub     rsp, 28h
0x180011c2d  mov     rbx, rcx
0x180011c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c37  lea     r12, WPP_GLOBAL_Control
0x180011c3e  cmp     rcx, r12
0x180011c41  jz      short loc_180011C5E
0x180011c43  test    byte ptr [rcx+1Ch], 20h
0x180011c47  jz      short loc_180011C5E
0x180011c49  mov     rcx, [rcx+10h]
0x180011c4d  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011c54  mov     edx, 0F9h
0x180011c59  call    WPP_SF_
0x180011c5e  lea     rcx, aPowermanagemen_0; "PowerManagementMessageBounds"
0x180011c65  call    cs:__imp_StrToID
0x180011c6b  movzx   edx, ax
0x180011c6e  mov     rcx, rbx
0x180011c71  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180011c77  mov     rsi, rax
0x180011c7a  test    rax, rax
0x180011c7d  jz      loc_180011D52
0x180011c83  mov     rcx, [rbx+0D8h]; this
0x180011c8a  xor     edi, edi
0x180011c8c  lea     ebp, [rdi+2]
0x180011c8f  mov     [rsp+58h+arg_8], ebp
0x180011c93  test    rcx, rcx
0x180011c96  jz      short loc_180011CAF
0x180011c98  lea     rdx, [rsp+58h+arg_8]; enum AuthorizationStatus *
0x180011c9d  call    ?GetAuthorizationStatus@CDeviceSettings@@QEAAJPEAW4AuthorizationStatus@@@Z; CDeviceSettings::GetAuthorizationStatus(AuthorizationStatus *)
0x180011ca2  mov     ebp, [rsp+58h+arg_8]
0x180011ca6  cmp     ebp, 2
0x180011ca9  jz      short loc_180011CAF
0x180011cab  xor     ecx, ecx
0x180011cad  jmp     short loc_180011CB4
0x180011caf  mov     ecx, 1
0x180011cb4  mov     edx, [rbx+0ECh]
0x180011cba  xor     eax, eax
0x180011cbc  cmp     dword ptr [rsi+78h], 3
0x180011cc0  setz    al
0x180011cc3  cmp     edx, eax
0x180011cc5  jnz     short loc_180011CCF
0x180011cc7  cmp     edx, ecx
0x180011cc9  jz      loc_180011D57
0x180011ccf  cmp     dword ptr [rsi+78h], 3
0x180011cd3  jz      short loc_180011D4B
0x180011cd5  mov     r14, [rbx+0D8h]
0x180011cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ce3  cmp     rcx, r12
0x180011ce6  jz      short loc_180011D2A
0x180011ce8  test    byte ptr [rcx+1Ch], 20h
0x180011cec  jz      short loc_180011D0A
0x180011cee  mov     rcx, [rcx+10h]
0x180011cf2  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180011cf9  mov     edx, 2Ah ; '*'
0x180011cfe  call    WPP_SF_
0x180011d03  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d0a  cmp     rcx, r12
0x180011d0d  jz      short loc_180011D2A
0x180011d0f  test    byte ptr [rcx+1Ch], 20h
0x180011d13  jz      short loc_180011D2A
0x180011d15  mov     rcx, [rcx+10h]
0x180011d19  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180011d20  mov     edx, 2Bh ; '+'
0x180011d25  call    WPP_SF_
0x180011d2a  cmp     [r14+5Ch], edi
0x180011d2e  jnz     short loc_180011D4B
0x180011d30  cmp     ebp, 2
0x180011d33  jnz     short loc_180011D4B
0x180011d35  cmp     [rbx+0ECh], edi
0x180011d3b  jz      short loc_180011D4B
0x180011d3d  lea     edx, [rbp+1]
0x180011d40  mov     rcx, rsi
0x180011d43  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180011d49  jmp     short loc_180011D57
0x180011d4b  mov     edx, 0FFFFFFFDh
0x180011d50  jmp     short loc_180011D40
0x180011d52  mov     edi, 80004005h
0x180011d57  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d5e  cmp     rcx, r12
0x180011d61  jz      short loc_180011D81
0x180011d63  test    byte ptr [rcx+1Ch], 20h
0x180011d67  jz      short loc_180011D81
0x180011d69  mov     rcx, [rcx+10h]
0x180011d6d  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011d74  mov     edx, 0FAh
0x180011d79  mov     r9d, edi
0x180011d7c  call    WPP_SF_d
0x180011d81  mov     eax, edi
0x180011d83  add     rsp, 28h
0x180011d87  pop     r14
0x180011d89  pop     r12
0x180011d8b  pop     rdi
0x180011d8c  pop     rsi
0x180011d8d  pop     rbp
0x180011d8e  pop     rbx
0x180011d8f  retn
```
