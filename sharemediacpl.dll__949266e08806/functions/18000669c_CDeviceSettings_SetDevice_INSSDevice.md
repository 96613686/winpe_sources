# CDeviceSettings::SetDevice(INSSDevice *)

- ea: `0x18000669c`
- end: `0x1800068d8`
- name: `?SetDevice@CDeviceSettings@@QEAAJPEAUINSSDevice@@@Z`
- size: `572`
- prototype: `__int64 __fastcall(CDeviceSettings *__hidden this, struct INSSDevice *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000822c`
- `0x1800087c0`
- `0x18000c284`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180003860`
- `0x180003888`
- `0x180004a64`
- `0x18000669c`
- `0x18001e010`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180006822`
- `KERNEL32!lstrcmpiW` at `0x18000686d`
- `KERNEL32!lstrcmpiW` at `0x180006822`
- `KERNEL32!lstrcmpiW` at `0x18000686d`
- `ole32!CoTaskMemFree` at `0x18000675f`
- `ole32!CoTaskMemFree` at `0x180006834`
- `ole32!CoTaskMemFree` at `0x18000687f`
- `ole32!CoTaskMemFree` at `0x18000675f`
- `ole32!CoTaskMemFree` at `0x180006834`
- `ole32!CoTaskMemFree` at `0x18000687f`
- `SHLWAPI!SHStrDupW` at `0x1800067de`
- `SHLWAPI!SHStrDupW` at `0x1800067de`
- `USER32!LoadStringW` at `0x1800067c5`
- `USER32!LoadStringW` at `0x1800067c5`

## pseudocode

```c
__int64 __fastcall CDeviceSettings::SetDevice(CDeviceSettings *this, struct INSSDevice *a2)
{
  _QWORD *v4; // rcx
  HRESULT DeviceProperty; // ebx
  __int64 v6; // rcx
  LPCWSTR lpString1[2]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer[504]; // [rsp+30h] [rbp-D0h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v6 = *((_QWORD *)this + 2);
    if ( v6 )
    {
      *((_QWORD *)this + 2) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    *((_QWORD *)this + 2) = a2;
    (*(void (__fastcall **)(struct INSSDevice *))(*(_QWORD *)a2 + 8LL))(a2);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2), (char *)this + 80);
    CoTaskMemFree(*((LPVOID *)this + 8));
    *((_QWORD *)this + 8) = 0;
    DeviceProperty = CDeviceSettings::GetDeviceProperty(this, L"FriendlyName", (unsigned __int16 **)this + 8);
    if ( DeviceProperty )
    {
      DeviceProperty = CDeviceSettings::GetDeviceProperty(this, L"ModelName", (unsigned __int16 **)this + 8);
      if ( DeviceProperty )
      {
        memset_0(Buffer, 0, 0x3E8u);
        if ( LoadStringW(g_hinst, 0x1Du, Buffer, 500) <= 0 )
          Buffer[0] = 0;
        DeviceProperty = SHStrDupW(Buffer, (LPWSTR *)this + 8);
      }
    }
    if ( DeviceProperty >= 0 )
    {
      lpString1[0] = 0;
      DeviceProperty = CDeviceSettings::GetDeviceProperty(
                         this,
                         L"DeviceSendWakeSupported",
                         (unsigned __int16 **)lpString1);
      if ( !DeviceProperty && !lstrcmpiW(lpString1[0], L"1") )
        *((_DWORD *)this + 23) = 1;
      CoTaskMemFree((LPVOID)lpString1[0]);
      if ( DeviceProperty >= 0 )
      {
        lpString1[0] = 0;
        DeviceProperty = CDeviceSettings::GetDeviceProperty(this, L"OnCurrentNetwork", (unsigned __int16 **)lpString1);
        if ( !DeviceProperty && !lstrcmpiW(lpString1[0], L"1") )
          *((_DWORD *)this + 25) = 1;
        CoTaskMemFree((LPVOID)lpString1[0]);
      }
    }
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
    DeviceProperty = -2147467261;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 25, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids, (unsigned int)DeviceProperty);
  return (unsigned int)DeviceProperty;
}

```

## disassembly

```asm
0x18000669c  mov     [rsp-8+arg_8], rbx
0x1800066a1  mov     [rsp-8+arg_10], rsi
0x1800066a6  push    rbp
0x1800066a7  push    rdi
0x1800066a8  push    r15
0x1800066aa  lea     rbp, [rsp-330h]
0x1800066b2  sub     rsp, 430h
0x1800066b9  mov     rax, cs:__security_cookie
0x1800066c0  xor     rax, rsp
0x1800066c3  mov     [rbp+340h+var_20], rax
0x1800066ca  mov     rbx, rdx
0x1800066cd  mov     rdi, rcx
0x1800066d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066d7  lea     r15, WPP_GLOBAL_Control
0x1800066de  cmp     rcx, r15
0x1800066e1  jz      short loc_180006705
0x1800066e3  test    byte ptr [rcx+1Ch], 20h
0x1800066e7  jz      short loc_180006705
0x1800066e9  mov     rcx, [rcx+10h]
0x1800066ed  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800066f4  mov     edx, 18h
0x1800066f9  call    WPP_SF_
0x1800066fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180006705  test    rbx, rbx
0x180006708  jnz     short loc_180006714
0x18000670a  mov     ebx, 80004003h
0x18000670f  jmp     loc_18000688C
0x180006714  mov     rcx, [rdi+10h]
0x180006718  test    rcx, rcx
0x18000671b  jz      short loc_180006731
0x18000671d  mov     qword ptr [rdi+10h], 0
0x180006725  mov     rax, [rcx]
0x180006728  mov     rax, [rax+10h]
0x18000672c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006731  mov     [rdi+10h], rbx
0x180006735  mov     rcx, rbx
0x180006738  mov     rax, [rbx]
0x18000673b  mov     rax, [rax+8]
0x18000673f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006744  mov     rcx, [rdi+10h]
0x180006748  lea     rdx, [rdi+50h]
0x18000674c  mov     rax, [rcx]
0x18000674f  mov     rax, [rax+40h]
0x180006753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006758  lea     rsi, [rdi+40h]
0x18000675c  mov     rcx, [rsi]; pv
0x18000675f  call    cs:__imp_CoTaskMemFree
0x180006765  mov     r8, rsi; unsigned __int16 **
0x180006768  mov     qword ptr [rsi], 0
0x18000676f  lea     rdx, aFriendlyname; "FriendlyName"
0x180006776  mov     rcx, rdi; this
0x180006779  call    ?GetDeviceProperty@CDeviceSettings@@QEAAJPEBGPEAPEAG@Z; CDeviceSettings::GetDeviceProperty(ushort const *,ushort * *)
0x18000677e  mov     ebx, eax
0x180006780  test    eax, eax
0x180006782  jz      short loc_1800067E6
0x180006784  mov     r8, rsi; unsigned __int16 **
0x180006787  lea     rdx, aModelname; "ModelName"
0x18000678e  mov     rcx, rdi; this
0x180006791  call    ?GetDeviceProperty@CDeviceSettings@@QEAAJPEBGPEAPEAG@Z; CDeviceSettings::GetDeviceProperty(ushort const *,ushort * *)
0x180006796  mov     ebx, eax
0x180006798  test    eax, eax
0x18000679a  jz      short loc_1800067E6
0x18000679c  xor     edx, edx; Val
0x18000679e  lea     rcx, [rsp+440h+Buffer]; void *
0x1800067a3  mov     r8d, 3E8h; Size
0x1800067a9  call    memset_0
0x1800067ae  mov     rcx, cs:g_hinst; hInstance
0x1800067b5  lea     r8, [rsp+440h+Buffer]; lpBuffer
0x1800067ba  mov     r9d, 1F4h; cchBufferMax
0x1800067c0  mov     edx, 1Dh; uID
0x1800067c5  call    cs:__imp_LoadStringW
0x1800067cb  test    eax, eax
0x1800067cd  jg      short loc_1800067D6
0x1800067cf  xor     eax, eax
0x1800067d1  mov     [rsp+440h+Buffer], ax
0x1800067d6  mov     rdx, rsi; ppwsz
0x1800067d9  lea     rcx, [rsp+440h+Buffer]; psz
0x1800067de  call    cs:__imp_SHStrDupW
0x1800067e4  mov     ebx, eax
0x1800067e6  test    ebx, ebx
0x1800067e8  js      loc_180006885
0x1800067ee  lea     r8, [rsp+440h+lpString1]; unsigned __int16 **
0x1800067f3  mov     [rsp+440h+lpString1], 0
0x1800067fc  lea     rdx, aDevicesendwake; "DeviceSendWakeSupported"
0x180006803  mov     rcx, rdi; this
0x180006806  call    ?GetDeviceProperty@CDeviceSettings@@QEAAJPEBGPEAPEAG@Z; CDeviceSettings::GetDeviceProperty(ushort const *,ushort * *)
0x18000680b  mov     ebx, eax
0x18000680d  mov     esi, 1
0x180006812  test    eax, eax
0x180006814  jnz     short loc_18000682F
0x180006816  mov     rcx, [rsp+440h+lpString1]; lpString1
0x18000681b  lea     rdx, String1; "1"
0x180006822  call    cs:__imp_lstrcmpiW
0x180006828  test    eax, eax
0x18000682a  jnz     short loc_18000682F
0x18000682c  mov     [rdi+5Ch], esi
0x18000682f  mov     rcx, [rsp+440h+lpString1]; pv
0x180006834  call    cs:__imp_CoTaskMemFree
0x18000683a  test    ebx, ebx
0x18000683c  js      short loc_180006885
0x18000683e  lea     r8, [rsp+440h+lpString1]; unsigned __int16 **
0x180006843  mov     [rsp+440h+lpString1], 0
0x18000684c  lea     rdx, aOncurrentnetwo; "OnCurrentNetwork"
0x180006853  mov     rcx, rdi; this
0x180006856  call    ?GetDeviceProperty@CDeviceSettings@@QEAAJPEBGPEAPEAG@Z; CDeviceSettings::GetDeviceProperty(ushort const *,ushort * *)
0x18000685b  mov     ebx, eax
0x18000685d  test    eax, eax
0x18000685f  jnz     short loc_18000687A
0x180006861  mov     rcx, [rsp+440h+lpString1]; lpString1
0x180006866  lea     rdx, String1; "1"
0x18000686d  call    cs:__imp_lstrcmpiW
0x180006873  test    eax, eax
0x180006875  jnz     short loc_18000687A
0x180006877  mov     [rdi+64h], esi
0x18000687a  mov     rcx, [rsp+440h+lpString1]; pv
0x18000687f  call    cs:__imp_CoTaskMemFree
0x180006885  mov     rcx, cs:WPP_GLOBAL_Control
0x18000688c  cmp     rcx, r15
0x18000688f  jz      short loc_1800068AF
0x180006891  test    byte ptr [rcx+1Ch], 20h
0x180006895  jz      short loc_1800068AF
0x180006897  mov     rcx, [rcx+10h]
0x18000689b  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800068a2  mov     edx, 19h
0x1800068a7  mov     r9d, ebx
0x1800068aa  call    WPP_SF_d
0x1800068af  mov     eax, ebx
0x1800068b1  mov     rcx, [rbp+340h+var_20]
0x1800068b8  xor     rcx, rsp; StackCookie
0x1800068bb  call    __security_check_cookie
0x1800068c0  lea     r11, [rsp+440h+var_10]
0x1800068c8  mov     rbx, [r11+28h]
0x1800068cc  mov     rsi, [r11+30h]
0x1800068d0  mov     rsp, r11
0x1800068d3  pop     r15
0x1800068d5  pop     rdi
0x1800068d6  pop     rbp
0x1800068d7  retn
```
