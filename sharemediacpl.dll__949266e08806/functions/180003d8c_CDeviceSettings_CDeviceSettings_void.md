# CDeviceSettings::CDeviceSettings(void)

- ea: `0x180003d8c`
- end: `0x180003e34`
- name: `??0CDeviceSettings@@QEAA@XZ`
- size: `168`
- prototype: `CDeviceSettings *__fastcall(CDeviceSettings *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000822c`
- `0x1800087c0`
- `0x18000f430`
- `0x18000f660`

## callees

- `0x180003860`
- `0x180003d8c`
- `0x180016b00`

## pseudocode

```c
CDeviceSettings *__fastcall CDeviceSettings::CDeviceSettings(
        CDeviceSettings *this,
        struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *a2)
{
  *(_QWORD *)this = &CDeviceSettings::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAu, (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  *((_DWORD *)this + 2) = 1;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 12) = 0;
  HMEHelpers::InitializeWMPDeviceSettings((CDeviceSettings *)((char *)this + 24), a2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xBu, (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  return this;
}

```

## disassembly

```asm
0x180003d8c  mov     [rsp+arg_0], rbx
0x180003d91  push    rdi
0x180003d92  sub     rsp, 20h
0x180003d96  lea     rax, ??_7CDeviceSettings@@6B@; const CDeviceSettings::`vftable'
0x180003d9d  mov     rbx, rcx
0x180003da0  mov     [rcx], rax
0x180003da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003daa  lea     rdi, WPP_GLOBAL_Control
0x180003db1  cmp     rcx, rdi
0x180003db4  jz      short loc_180003DD1
0x180003db6  test    byte ptr [rcx+1Ch], 20h
0x180003dba  jz      short loc_180003DD1
0x180003dbc  mov     rcx, [rcx+10h]
0x180003dc0  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180003dc7  mov     edx, 0Ah
0x180003dcc  call    WPP_SF_
0x180003dd1  xor     eax, eax
0x180003dd3  mov     dword ptr [rbx+8], 1
0x180003dda  lea     rcx, [rbx+18h]; this
0x180003dde  mov     [rbx+50h], rax
0x180003de2  mov     [rbx+10h], rax
0x180003de6  mov     [rbx+68h], rax
0x180003dea  mov     [rbx+58h], rax
0x180003dee  mov     [rbx+48h], rax
0x180003df2  mov     [rbx+40h], rax
0x180003df6  mov     [rbx+60h], rax
0x180003dfa  call    ?InitializeWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::InitializeWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180003dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e06  cmp     rcx, rdi
0x180003e09  jz      short loc_180003E26
0x180003e0b  test    byte ptr [rcx+1Ch], 20h
0x180003e0f  jz      short loc_180003E26
0x180003e11  mov     rcx, [rcx+10h]
0x180003e15  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180003e1c  mov     edx, 0Bh
0x180003e21  call    WPP_SF_
0x180003e26  mov     rax, rbx
0x180003e29  mov     rbx, [rsp+28h+arg_0]
0x180003e2e  add     rsp, 20h
0x180003e32  pop     rdi
0x180003e33  retn
```
