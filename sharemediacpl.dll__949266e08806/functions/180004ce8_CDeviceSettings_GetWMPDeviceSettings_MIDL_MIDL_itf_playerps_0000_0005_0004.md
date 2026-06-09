# CDeviceSettings::GetWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)

- ea: `0x180004ce8`
- end: `0x180004d9d`
- name: `?GetWMPDeviceSettings@CDeviceSettings@@QEAAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z`
- size: `181`
- prototype: `int(CDeviceSettings *__hidden this, struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004ff0`
- `0x18000638c`
- `0x1800069d4`
- `0x180006d34`

## callees

- `0x180003860`
- `0x180003888`
- `0x180004ce8`
- `0x1800166a0`
- `0x18001688c`

## pseudocode

```c
__int64 __fastcall CDeviceSettings::GetWMPDeviceSettings(
        CDeviceSettings *this,
        struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *a2)
{
  _UNKNOWN **v4; // rcx
  unsigned int v5; // ebx
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v6; // r8
  unsigned int v7; // eax

  v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Eu, (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( *((_DWORD *)this + 24) )
    {
      HMEHelpers::CleanupWMPDeviceSettings(a2, a2);
      v7 = HMEHelpers::CopyWMPDeviceSettings((CDeviceSettings *)((char *)this + 24), a2, v6);
      v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
      v5 = v7;
    }
    else
    {
      v5 = -2147024809;
    }
  }
  else
  {
    v5 = -2147467261;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d((TRACEHANDLE)v4[2], 0x1Fu, (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180004ce8  mov     [rsp+arg_0], rbx
0x180004ced  mov     [rsp+arg_8], rsi
0x180004cf2  push    rdi
0x180004cf3  sub     rsp, 20h
0x180004cf7  mov     rbx, rdx
0x180004cfa  mov     rdi, rcx
0x180004cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d04  lea     rsi, WPP_GLOBAL_Control
0x180004d0b  cmp     rcx, rsi
0x180004d0e  jz      short loc_180004D32
0x180004d10  test    byte ptr [rcx+1Ch], 20h
0x180004d14  jz      short loc_180004D32
0x180004d16  mov     rcx, [rcx+10h]
0x180004d1a  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180004d21  mov     edx, 1Eh
0x180004d26  call    WPP_SF_
0x180004d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d32  test    rbx, rbx
0x180004d35  jnz     short loc_180004D3E
0x180004d37  mov     ebx, 80004003h
0x180004d3c  jmp     short loc_180004D68
0x180004d3e  cmp     dword ptr [rdi+60h], 0
0x180004d42  jnz     short loc_180004D4B
0x180004d44  mov     ebx, 80070057h
0x180004d49  jmp     short loc_180004D68
0x180004d4b  mov     rcx, rbx; this
0x180004d4e  call    ?CleanupWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::CleanupWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180004d53  lea     rcx, [rdi+18h]; this
0x180004d57  mov     rdx, rbx; struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *
0x180004d5a  call    ?CopyWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@0@Z; HMEHelpers::CopyWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180004d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d66  mov     ebx, eax
0x180004d68  cmp     rcx, rsi
0x180004d6b  jz      short loc_180004D8B
0x180004d6d  test    byte ptr [rcx+1Ch], 20h
0x180004d71  jz      short loc_180004D8B
0x180004d73  mov     rcx, [rcx+10h]
0x180004d77  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180004d7e  mov     edx, 1Fh
0x180004d83  mov     r9d, ebx
0x180004d86  call    WPP_SF_d
0x180004d8b  mov     rsi, [rsp+28h+arg_8]
0x180004d90  mov     eax, ebx
0x180004d92  mov     rbx, [rsp+28h+arg_0]
0x180004d97  add     rsp, 20h
0x180004d9b  pop     rdi
0x180004d9c  retn
```
