# CDeviceSettings::IsDeviceConnected(int *)

- ea: `0x180005468`
- end: `0x180005536`
- name: `?IsDeviceConnected@CDeviceSettings@@QEAAJPEAH@Z`
- size: `206`
- prototype: `__int64 __fastcall(CDeviceSettings *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800100ac`

## callees

- `0x180003860`
- `0x180003888`
- `0x180004a64`
- `0x180005468`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x1800054e0`
- `KERNEL32!lstrcmpW` at `0x1800054e0`
- `ole32!CoTaskMemFree` at `0x1800054f4`
- `ole32!CoTaskMemFree` at `0x1800054f4`

## pseudocode

```c
__int64 __fastcall CDeviceSettings::IsDeviceConnected(CDeviceSettings *this, int *a2)
{
  unsigned int DeviceProperty; // ebx
  LPCWSTR lpString2; // [rsp+38h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  *a2 = 0;
  lpString2 = 0;
  DeviceProperty = CDeviceSettings::GetDeviceProperty(this, L"Alive", (unsigned __int16 **)&lpString2);
  if ( !DeviceProperty )
  {
    *a2 = lstrcmpW(L"1", lpString2) == 0;
    CoTaskMemFree((LPVOID)lpString2);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids, DeviceProperty);
  return DeviceProperty;
}

```

## disassembly

```asm
0x180005468  mov     [rsp+arg_0], rbx
0x18000546d  mov     [rsp+arg_10], rsi
0x180005472  push    rdi
0x180005473  sub     rsp, 20h
0x180005477  mov     rdi, rdx
0x18000547a  mov     rbx, rcx
0x18000547d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005484  lea     rsi, WPP_GLOBAL_Control
0x18000548b  cmp     rcx, rsi
0x18000548e  jz      short loc_1800054AB
0x180005490  test    byte ptr [rcx+1Ch], 20h
0x180005494  jz      short loc_1800054AB
0x180005496  mov     rcx, [rcx+10h]
0x18000549a  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800054a1  mov     edx, 2Eh ; '.'
0x1800054a6  call    WPP_SF_
0x1800054ab  lea     r8, [rsp+28h+lpString2]; unsigned __int16 **
0x1800054b0  mov     dword ptr [rdi], 0
0x1800054b6  lea     rdx, aAlive; "Alive"
0x1800054bd  mov     [rsp+28h+lpString2], 0
0x1800054c6  mov     rcx, rbx; this
0x1800054c9  call    ?GetDeviceProperty@CDeviceSettings@@QEAAJPEBGPEAPEAG@Z; CDeviceSettings::GetDeviceProperty(ushort const *,ushort * *)
0x1800054ce  mov     ebx, eax
0x1800054d0  test    eax, eax
0x1800054d2  jnz     short loc_1800054FA
0x1800054d4  mov     rdx, [rsp+28h+lpString2]; lpString2
0x1800054d9  lea     rcx, String1; "1"
0x1800054e0  call    cs:__imp_lstrcmpW
0x1800054e6  xor     ecx, ecx
0x1800054e8  test    eax, eax
0x1800054ea  setz    cl
0x1800054ed  mov     [rdi], ecx
0x1800054ef  mov     rcx, [rsp+28h+lpString2]; pv
0x1800054f4  call    cs:__imp_CoTaskMemFree
0x1800054fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180005501  cmp     rcx, rsi
0x180005504  jz      short loc_180005524
0x180005506  test    byte ptr [rcx+1Ch], 20h
0x18000550a  jz      short loc_180005524
0x18000550c  mov     rcx, [rcx+10h]
0x180005510  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180005517  mov     edx, 2Fh ; '/'
0x18000551c  mov     r9d, ebx
0x18000551f  call    WPP_SF_d
0x180005524  mov     rsi, [rsp+28h+arg_10]
0x180005529  mov     eax, ebx
0x18000552b  mov     rbx, [rsp+28h+arg_0]
0x180005530  add     rsp, 20h
0x180005534  pop     rdi
0x180005535  retn
```
