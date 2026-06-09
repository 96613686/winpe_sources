# CShareWithListItemUsers::_UpdateElementNameLink(void)

- ea: `0x180011bb0`
- end: `0x180011c13`
- name: `?_UpdateElementNameLink@CShareWithListItemUsers@@EEAAJXZ`
- size: `99`
- prototype: `__int64 __fastcall(CShareWithListItemUsers *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180003860`
- `0x180011bb0`

## pseudocode

```c
__int64 __fastcall CShareWithListItemUsers::_UpdateElementNameLink(CShareWithListItemUsers *this)
{
  _QWORD *v1; // rcx

  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
      v1 = WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x20) != 0 )
      WPP_SF_(v1[2], 230, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180011bb0  push    rbx
0x180011bb2  sub     rsp, 20h
0x180011bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bbd  lea     rbx, WPP_GLOBAL_Control
0x180011bc4  cmp     rcx, rbx
0x180011bc7  jz      short loc_180011C0B
0x180011bc9  test    byte ptr [rcx+1Ch], 20h
0x180011bcd  jz      short loc_180011BEB
0x180011bcf  mov     rcx, [rcx+10h]
0x180011bd3  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011bda  mov     edx, 0E5h
0x180011bdf  call    WPP_SF_
0x180011be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011beb  cmp     rcx, rbx
0x180011bee  jz      short loc_180011C0B
0x180011bf0  test    byte ptr [rcx+1Ch], 20h
0x180011bf4  jz      short loc_180011C0B
0x180011bf6  mov     rcx, [rcx+10h]
0x180011bfa  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180011c01  mov     edx, 0E6h
0x180011c06  call    WPP_SF_
0x180011c0b  xor     eax, eax
0x180011c0d  add     rsp, 20h
0x180011c11  pop     rbx
0x180011c12  retn
```
