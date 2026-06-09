# CDeviceSettings::GetID(ushort * *)

- ea: `0x180004c40`
- end: `0x180004ce1`
- name: `?GetID@CDeviceSettings@@QEAAJPEAPEAG@Z`
- size: `161`
- prototype: `int(CDeviceSettings *__hidden this, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005e74`
- `0x18000653c`
- `0x1800069d4`
- `0x18000a130`
- `0x18000ad74`

## callees

- `0x180003860`
- `0x180003888`
- `0x180004c40`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180004c9d`
- `SHLWAPI!SHStrDupW` at `0x180004c9d`

## pseudocode

```c
__int64 __fastcall CDeviceSettings::GetID(CDeviceSettings *this, unsigned __int16 **a2)
{
  const WCHAR *v4; // rcx
  unsigned int v5; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x16u, (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  *a2 = 0;
  v4 = (const WCHAR *)*((_QWORD *)this + 13);
  if ( v4 )
    v5 = SHStrDupW(v4, a2);
  else
    v5 = -2147024809;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x17u,
      (const GUID *)WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids,
      v5);
  return v5;
}

```

## disassembly

```asm
0x180004c40  mov     [rsp+arg_0], rbx
0x180004c45  mov     [rsp+arg_8], rsi
0x180004c4a  push    rdi
0x180004c4b  sub     rsp, 20h
0x180004c4f  mov     rbx, rdx
0x180004c52  mov     rdi, rcx
0x180004c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c5c  lea     rsi, WPP_GLOBAL_Control
0x180004c63  cmp     rcx, rsi
0x180004c66  jz      short loc_180004C83
0x180004c68  test    byte ptr [rcx+1Ch], 20h
0x180004c6c  jz      short loc_180004C83
0x180004c6e  mov     rcx, [rcx+10h]
0x180004c72  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180004c79  mov     edx, 16h
0x180004c7e  call    WPP_SF_
0x180004c83  mov     qword ptr [rbx], 0
0x180004c8a  mov     rcx, [rdi+68h]; psz
0x180004c8e  test    rcx, rcx
0x180004c91  jnz     short loc_180004C9A
0x180004c93  mov     ebx, 80070057h
0x180004c98  jmp     short loc_180004CA5
0x180004c9a  mov     rdx, rbx; ppwsz
0x180004c9d  call    cs:__imp_SHStrDupW
0x180004ca3  mov     ebx, eax
0x180004ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cac  cmp     rcx, rsi
0x180004caf  jz      short loc_180004CCF
0x180004cb1  test    byte ptr [rcx+1Ch], 20h
0x180004cb5  jz      short loc_180004CCF
0x180004cb7  mov     rcx, [rcx+10h]
0x180004cbb  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180004cc2  mov     edx, 17h
0x180004cc7  mov     r9d, ebx
0x180004cca  call    WPP_SF_d
0x180004ccf  mov     rsi, [rsp+28h+arg_8]
0x180004cd4  mov     eax, ebx
0x180004cd6  mov     rbx, [rsp+28h+arg_0]
0x180004cdb  add     rsp, 20h
0x180004cdf  pop     rdi
0x180004ce0  retn
```
