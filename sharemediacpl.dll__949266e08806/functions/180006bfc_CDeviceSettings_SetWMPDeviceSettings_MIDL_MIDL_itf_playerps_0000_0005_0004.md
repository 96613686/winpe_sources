# CDeviceSettings::SetWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)

- ea: `0x180006bfc`
- end: `0x180006ca0`
- name: `?SetWMPDeviceSettings@CDeviceSettings@@QEAAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z`
- size: `164`
- prototype: `int(CDeviceSettings *__hidden this, struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180005e74`
- `0x18000653c`
- `0x1800069d4`
- `0x18000822c`
- `0x1800087c0`

## callees

- `0x180003860`
- `0x180003888`
- `0x180006bfc`
- `0x1800166a0`
- `0x18001688c`

## pseudocode

```c
__int64 __fastcall CDeviceSettings::SetWMPDeviceSettings(
        CDeviceSettings *this,
        struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *a2)
{
  _UNKNOWN **v4; // rcx
  int v5; // ebx
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v6; // r8

  v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Cu, (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    HMEHelpers::CleanupWMPDeviceSettings((CDeviceSettings *)((char *)this + 24), a2);
    v5 = HMEHelpers::CopyWMPDeviceSettings(a2, (CDeviceSettings *)((char *)this + 24), v6);
    *((_DWORD *)this + 24) = v5 >= 0;
    v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  else
  {
    v5 = -2147467261;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d((TRACEHANDLE)v4[2], 0x1Du, (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180006bfc  push    rbx
0x180006bfe  push    rbp
0x180006bff  push    rsi
0x180006c00  push    rdi
0x180006c01  sub     rsp, 28h
0x180006c05  mov     rdi, rdx
0x180006c08  mov     rsi, rcx
0x180006c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c12  lea     rbp, WPP_GLOBAL_Control
0x180006c19  cmp     rcx, rbp
0x180006c1c  jz      short loc_180006C40
0x180006c1e  test    byte ptr [rcx+1Ch], 20h
0x180006c22  jz      short loc_180006C40
0x180006c24  mov     rcx, [rcx+10h]
0x180006c28  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180006c2f  mov     edx, 1Ch
0x180006c34  call    WPP_SF_
0x180006c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c40  test    rdi, rdi
0x180006c43  jnz     short loc_180006C4C
0x180006c45  mov     ebx, 80004003h
0x180006c4a  jmp     short loc_180006C72
0x180006c4c  lea     rcx, [rsi+18h]; this
0x180006c50  call    ?CleanupWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::CleanupWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180006c55  lea     rdx, [rsi+18h]; struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *
0x180006c59  mov     rcx, rdi; this
0x180006c5c  call    ?CopyWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@0@Z; HMEHelpers::CopyWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180006c61  mov     ebx, eax
0x180006c63  not     eax
0x180006c65  shr     eax, 1Fh
0x180006c68  mov     [rsi+60h], eax
0x180006c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c72  cmp     rcx, rbp
0x180006c75  jz      short loc_180006C95
0x180006c77  test    byte ptr [rcx+1Ch], 20h
0x180006c7b  jz      short loc_180006C95
0x180006c7d  mov     rcx, [rcx+10h]
0x180006c81  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180006c88  mov     edx, 1Dh
0x180006c8d  mov     r9d, ebx
0x180006c90  call    WPP_SF_d
0x180006c95  mov     eax, ebx
0x180006c97  add     rsp, 28h
0x180006c9b  pop     rdi
0x180006c9c  pop     rsi
0x180006c9d  pop     rbp
0x180006c9e  pop     rbx
0x180006c9f  retn
```
