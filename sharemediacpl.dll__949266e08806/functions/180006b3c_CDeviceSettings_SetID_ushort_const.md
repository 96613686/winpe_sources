# CDeviceSettings::SetID(ushort const *)

- ea: `0x180006b3c`
- end: `0x180006bf4`
- name: `?SetID@CDeviceSettings@@QEAAJPEBG@Z`
- size: `184`
- prototype: `int(CDeviceSettings *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000822c`
- `0x1800087c0`
- `0x18000f430`
- `0x18000f660`

## callees

- `0x180003860`
- `0x180003888`
- `0x180006b3c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006b9b`
- `ole32!CoTaskMemFree` at `0x180006b9b`
- `SHLWAPI!SHStrDupW` at `0x180006bb0`
- `SHLWAPI!SHStrDupW` at `0x180006bb0`

## pseudocode

```c
__int64 __fastcall CDeviceSettings::SetID(CDeviceSettings *this, const unsigned __int16 *a2)
{
  _QWORD *v4; // rcx
  unsigned int v5; // ebx
  void *v6; // rcx
  HRESULT v7; // eax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v6 = (void *)*((_QWORD *)this + 13);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *((_QWORD *)this + 13) = 0;
    }
    v7 = SHStrDupW(a2, (LPWSTR *)this + 13);
    v4 = WPP_GLOBAL_Control;
    v5 = v7;
  }
  else
  {
    v5 = -2147467261;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 21, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180006b3c  mov     [rsp+arg_0], rbx
0x180006b41  mov     [rsp+arg_8], rsi
0x180006b46  push    rdi
0x180006b47  sub     rsp, 20h
0x180006b4b  mov     rdi, rdx
0x180006b4e  mov     rbx, rcx
0x180006b51  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b58  lea     rsi, WPP_GLOBAL_Control
0x180006b5f  cmp     rcx, rsi
0x180006b62  jz      short loc_180006B86
0x180006b64  test    byte ptr [rcx+1Ch], 20h
0x180006b68  jz      short loc_180006B86
0x180006b6a  mov     rcx, [rcx+10h]
0x180006b6e  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180006b75  mov     edx, 14h
0x180006b7a  call    WPP_SF_
0x180006b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b86  test    rdi, rdi
0x180006b89  jnz     short loc_180006B92
0x180006b8b  mov     ebx, 80004003h
0x180006b90  jmp     short loc_180006BBF
0x180006b92  mov     rcx, [rbx+68h]; pv
0x180006b96  test    rcx, rcx
0x180006b99  jz      short loc_180006BA9
0x180006b9b  call    cs:__imp_CoTaskMemFree
0x180006ba1  mov     qword ptr [rbx+68h], 0
0x180006ba9  lea     rdx, [rbx+68h]; ppwsz
0x180006bad  mov     rcx, rdi; psz
0x180006bb0  call    cs:__imp_SHStrDupW
0x180006bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bbd  mov     ebx, eax
0x180006bbf  cmp     rcx, rsi
0x180006bc2  jz      short loc_180006BE2
0x180006bc4  test    byte ptr [rcx+1Ch], 20h
0x180006bc8  jz      short loc_180006BE2
0x180006bca  mov     rcx, [rcx+10h]
0x180006bce  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180006bd5  mov     edx, 15h
0x180006bda  mov     r9d, ebx
0x180006bdd  call    WPP_SF_d
0x180006be2  mov     rsi, [rsp+28h+arg_8]
0x180006be7  mov     eax, ebx
0x180006be9  mov     rbx, [rsp+28h+arg_0]
0x180006bee  add     rsp, 20h
0x180006bf2  pop     rdi
0x180006bf3  retn
```
