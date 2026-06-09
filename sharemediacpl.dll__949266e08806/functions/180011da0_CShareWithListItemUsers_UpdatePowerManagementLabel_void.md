# CShareWithListItemUsers::_UpdatePowerManagementLabel(void)

- ea: `0x180011da0`
- end: `0x180011e03`
- name: `?_UpdatePowerManagementLabel@CShareWithListItemUsers@@EEAAJXZ`
- size: `99`
- prototype: `__int64 __fastcall(CShareWithListItemUsers *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180003860`
- `0x180011da0`

## pseudocode

```c
__int64 __fastcall CShareWithListItemUsers::_UpdatePowerManagementLabel(CShareWithListItemUsers *this)
{
  _QWORD *v1; // rcx

  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
      v1 = WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x20) != 0 )
      WPP_SF_(v1[2], 226, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180011da0  push    rbx
0x180011da2  sub     rsp, 20h
0x180011da6  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dad  lea     rbx, WPP_GLOBAL_Control
0x180011db4  cmp     rcx, rbx
0x180011db7  jz      short loc_180011DFB
0x180011db9  test    byte ptr [rcx+1Ch], 20h
0x180011dbd  jz      short loc_180011DDB
0x180011dbf  mov     rcx, [rcx+10h]
0x180011dc3  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011dca  mov     edx, 0E1h
0x180011dcf  call    WPP_SF_
0x180011dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ddb  cmp     rcx, rbx
0x180011dde  jz      short loc_180011DFB
0x180011de0  test    byte ptr [rcx+1Ch], 20h
0x180011de4  jz      short loc_180011DFB
0x180011de6  mov     rcx, [rcx+10h]
0x180011dea  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011df1  mov     edx, 0E2h
0x180011df6  call    WPP_SF_
0x180011dfb  xor     eax, eax
0x180011dfd  add     rsp, 20h
0x180011e01  pop     rbx
0x180011e02  retn
```
