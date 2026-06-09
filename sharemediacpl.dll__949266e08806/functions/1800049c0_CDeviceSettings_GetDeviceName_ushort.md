# CDeviceSettings::GetDeviceName(ushort * *)

- ea: `0x1800049c0`
- end: `0x180004a5e`
- name: `?GetDeviceName@CDeviceSettings@@QEAAJPEAPEAG@Z`
- size: `158`
- prototype: `int(CDeviceSettings *__hidden this, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800059a8`
- `0x18000a730`
- `0x1800100ac`
- `0x180011ab0`

## callees

- `0x180003860`
- `0x180003888`
- `0x1800049c0`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180004a1a`
- `SHLWAPI!SHStrDupW` at `0x180004a1a`

## pseudocode

```c
__int64 __fastcall CDeviceSettings::GetDeviceName(CDeviceSettings *this, unsigned __int16 **a2)
{
  const WCHAR *v4; // rcx
  HRESULT v5; // eax
  unsigned int v6; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x3Cu, (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  *a2 = 0;
  v4 = (const WCHAR *)*((_QWORD *)this + 9);
  if ( !v4 )
    v4 = (const WCHAR *)*((_QWORD *)this + 8);
  v5 = SHStrDupW(v4, a2);
  v6 = v5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x3Du,
      (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids,
      v5);
  return v6;
}

```

## disassembly

```asm
0x1800049c0  mov     [rsp+arg_0], rbx
0x1800049c5  mov     [rsp+arg_8], rsi
0x1800049ca  push    rdi
0x1800049cb  sub     rsp, 20h
0x1800049cf  mov     rbx, rdx
0x1800049d2  mov     rdi, rcx
0x1800049d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049dc  lea     rsi, WPP_GLOBAL_Control
0x1800049e3  cmp     rcx, rsi
0x1800049e6  jz      short loc_180004A03
0x1800049e8  test    byte ptr [rcx+1Ch], 20h
0x1800049ec  jz      short loc_180004A03
0x1800049ee  mov     rcx, [rcx+10h]
0x1800049f2  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800049f9  mov     edx, 3Ch ; '<'
0x1800049fe  call    WPP_SF_
0x180004a03  mov     qword ptr [rbx], 0
0x180004a0a  mov     rdx, rbx; ppwsz
0x180004a0d  mov     rcx, [rdi+48h]
0x180004a11  test    rcx, rcx
0x180004a14  jnz     short loc_180004A1A
0x180004a16  mov     rcx, [rdi+40h]; psz
0x180004a1a  call    cs:__imp_SHStrDupW
0x180004a20  mov     ebx, eax
0x180004a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a29  cmp     rcx, rsi
0x180004a2c  jz      short loc_180004A4C
0x180004a2e  test    byte ptr [rcx+1Ch], 20h
0x180004a32  jz      short loc_180004A4C
0x180004a34  mov     rcx, [rcx+10h]
0x180004a38  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180004a3f  mov     edx, 3Dh ; '='
0x180004a44  mov     r9d, eax
0x180004a47  call    WPP_SF_d
0x180004a4c  mov     rsi, [rsp+28h+arg_8]
0x180004a51  mov     eax, ebx
0x180004a53  mov     rbx, [rsp+28h+arg_0]
0x180004a58  add     rsp, 20h
0x180004a5c  pop     rdi
0x180004a5d  retn
```
