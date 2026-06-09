# CUsbFilterControl::QueryUsbEnableMode(void)

- ea: `0x140008ad8`
- end: `0x140008b4e`
- name: `?QueryUsbEnableMode@CUsbFilterControl@@AEAA?AW4_USB_MODE@@XZ`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140006efc`
- `0x14000818c`

## callees

- `0x1400048d4`
- `0x140004f48`
- `0x140008ad8`

## string_xrefs

- `0x140008af5`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows NT\Terminal Services\Client`

## pseudocode

```c
__int64 __fastcall CUsbFilterControl::QueryUsbEnableMode(__int64 a1)
{
  __int64 result; // rax
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF
  int v3; // [rsp+34h] [rbp+Ch]

  v3 = HIDWORD(a1);
  v2 = 3;
  if ( (int)CUsbBusFilter::QueryRegistryData(
              L"\\REGISTRY\\MACHINE\\Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\Client",
              L"fUsbRedirectionEnableMode",
              &v2) < 0 )
    return 3;
  result = v2;
  if ( (int)v2 >= 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids, v2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140008ad8  mov     qword ptr [rsp+arg_0], rcx
0x140008add  sub     rsp, 28h
0x140008ae1  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x140008ae6  mov     [rsp+28h+arg_0], 3
0x140008aee  lea     rdx, aFusbredirectio; "fUsbRedirectionEnableMode"
0x140008af5  lea     rcx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x140008afc  call    ?QueryRegistryData@CUsbBusFilter@@SAJPEBG0PEAK@Z; CUsbBusFilter::QueryRegistryData(ushort const *,ushort const *,ulong *)
0x140008b01  test    eax, eax
0x140008b03  jns     short loc_140008B0C
0x140008b05  mov     eax, 3
0x140008b0a  jmp     short loc_140008B48
0x140008b0c  mov     eax, [rsp+28h+arg_0]
0x140008b10  cmp     eax, 3
0x140008b13  jl      short loc_140008B48
0x140008b15  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b1c  lea     rdx, WPP_GLOBAL_Control
0x140008b23  cmp     rcx, rdx
0x140008b26  jz      short loc_140008B46
0x140008b28  cmp     byte ptr [rcx+29h], 2
0x140008b2c  jb      short loc_140008B46
0x140008b2e  mov     rcx, [rcx+18h]
0x140008b32  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140008b39  mov     edx, 21h ; '!'
0x140008b3e  mov     r9d, eax
0x140008b41  call    WPP_SF_d
0x140008b46  xor     eax, eax
0x140008b48  add     rsp, 28h
0x140008b4c  retn
```
