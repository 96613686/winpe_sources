# D3DCommon::GetVideoRegKey(HKEY__ * *)

- ea: `0x18000f018`
- end: `0x18000f12b`
- name: `?GetVideoRegKey@D3DCommon@@YAJPEAPEAUHKEY__@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(D3DCommon *__hidden this, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e2d8`

## callees

- `0x18000f018`
- `0x18000f134`
- `0x1800151bb`
- `0x18002c1fc`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f0fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f0fc`
- `USER32!EnumDisplayDevicesW` at `0x18000f0a0`
- `USER32!EnumDisplayDevicesW` at `0x18000f0a0`

## string_xrefs

- `0x18000f048`: `D3DCommon::GetVideoRegKey`

## pseudocode

```c
__int64 __fastcall D3DCommon::GetVideoRegKey(D3DCommon *this, HKEY *a2)
{
  DWORD v4; // edi
  int v5; // esi
  unsigned __int64 v6; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  _DISPLAY_DEVICEW DisplayDevice; // [rsp+40h] [rbp-C0h] BYREF

  if ( this )
  {
    v4 = 0;
    *(_QWORD *)this = 0;
    v6 = 0;
    v5 = 0;
    phkResult = 0;
    memset_0(DisplayDevice.DeviceName, 0, 0x344u);
    DisplayDevice.cb = 840;
    while ( EnumDisplayDevicesW(0, v4, &DisplayDevice, 0) )
    {
      if ( (DisplayDevice.StateFlags & 4) != 0 )
      {
        v5 = StringCchLengthW(DisplayDevice.DeviceKey, 0x80u, &v6);
        if ( v5 >= 0
          && v6 >= 0x13
          && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, &DisplayDevice.DeviceKey[18], 0, 3u, &phkResult) )
        {
          *(_QWORD *)this = phkResult;
        }
        return (unsigned int)v5;
      }
      ++v4;
    }
    return (unsigned int)v5;
  }
  else
  {
    D3DCommon::ERR((D3DCommon *)0x6A, (__int64)L"phKey", L"D3DCommon::GetVideoRegKey");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000f018  push    rbp
0x18000f01a  push    rbx
0x18000f01b  push    rsi
0x18000f01c  push    rdi
0x18000f01d  lea     rbp, [rsp-2A8h]
0x18000f025  sub     rsp, 3A8h
0x18000f02c  mov     rax, cs:__security_cookie
0x18000f033  xor     rax, rsp
0x18000f036  mov     [rbp+2C0h+var_30], rax
0x18000f03d  mov     rbx, rcx
0x18000f040  test    rcx, rcx
0x18000f043  jnz     short loc_18000F065
0x18000f045  lea     ecx, [rbx+6Ah]; this
0x18000f048  lea     r8, aD3dcommonGetvi; "D3DCommon::GetVideoRegKey"
0x18000f04f  lea     rdx, aPhkey; "phKey"
0x18000f056  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x18000f05b  mov     eax, 80070057h
0x18000f060  jmp     loc_18000F110
0x18000f065  xor     edi, edi
0x18000f067  mov     qword ptr [rcx], 0
0x18000f06e  lea     rcx, [rsp+3C0h+DisplayDevice.DeviceName]; void *
0x18000f073  mov     [rsp+3C0h+var_390], rdi
0x18000f078  xor     esi, esi
0x18000f07a  mov     [rsp+3C0h+var_388], rdi
0x18000f07f  xor     edx, edx; Val
0x18000f081  mov     r8d, 344h; Size
0x18000f087  call    memset_0
0x18000f08c  mov     [rsp+3C0h+DisplayDevice.cb], 348h
0x18000f094  xor     r9d, r9d; dwFlags
0x18000f097  lea     r8, [rsp+3C0h+DisplayDevice]; lpDisplayDevice
0x18000f09c  mov     edx, edi; iDevNum
0x18000f09e  xor     ecx, ecx; lpDevice
0x18000f0a0  call    cs:__imp_EnumDisplayDevicesW
0x18000f0a6  test    eax, eax
0x18000f0a8  jz      short loc_18000F10E
0x18000f0aa  test    byte ptr [rbp+2C0h+DisplayDevice.StateFlags], 4
0x18000f0b1  jnz     short loc_18000F0B7
0x18000f0b3  inc     edi
0x18000f0b5  jmp     short loc_18000F094
0x18000f0b7  lea     r8, [rsp+3C0h+var_390]; unsigned __int64 *
0x18000f0bc  mov     edx, 80h; unsigned __int64
0x18000f0c1  lea     rcx, [rbp+2C0h+DisplayDevice.DeviceKey]; unsigned __int16 *
0x18000f0c8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000f0cd  mov     esi, eax
0x18000f0cf  test    eax, eax
0x18000f0d1  js      short loc_18000F10E
0x18000f0d3  cmp     [rsp+3C0h+var_390], 13h
0x18000f0d9  jb      short loc_18000F10E
0x18000f0db  lea     rax, [rsp+3C0h+var_388]
0x18000f0e0  mov     r9d, 3; samDesired
0x18000f0e6  xor     r8d, r8d; ulOptions
0x18000f0e9  mov     [rsp+3C0h+phkResult], rax; phkResult
0x18000f0ee  lea     rdx, [rbp+2C0h+DisplayDevice.DeviceKey+24h]; lpSubKey
0x18000f0f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f0fc  call    cs:__imp_RegOpenKeyExW
0x18000f102  test    eax, eax
0x18000f104  jnz     short loc_18000F10E
0x18000f106  mov     rax, [rsp+3C0h+var_388]
0x18000f10b  mov     [rbx], rax
0x18000f10e  mov     eax, esi
0x18000f110  mov     rcx, [rbp+2C0h+var_30]
0x18000f117  xor     rcx, rsp; StackCookie
0x18000f11a  call    __security_check_cookie
0x18000f11f  add     rsp, 3A8h
0x18000f126  pop     rdi
0x18000f127  pop     rsi
0x18000f128  pop     rbx
0x18000f129  pop     rbp
0x18000f12a  retn
```
