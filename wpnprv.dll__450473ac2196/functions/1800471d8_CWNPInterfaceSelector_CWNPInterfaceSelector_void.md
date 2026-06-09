# CWNPInterfaceSelector::CWNPInterfaceSelector(void)

- ea: `0x1800471d8`
- end: `0x180047398`
- name: `??0CWNPInterfaceSelector@@QEAA@XZ`
- size: `448`
- prototype: `CWNPInterfaceSelector *__fastcall(CWNPInterfaceSelector *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025364`

## callees

- `0x18000fe2c`
- `0x18000fe54`
- `0x1800154f4`
- `0x180039a7c`
- `0x180045140`
- `0x1800471d8`
- `0x18004929c`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047312`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047312`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180047277`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180047277`

## pseudocode

```c
CWNPInterfaceSelector *__fastcall CWNPInterfaceSelector::CWNPInterfaceSelector(CWNPInterfaceSelector *this)
{
  unsigned __int64 v2; // rdx
  int v3; // edi
  unsigned __int8 v4; // cl
  __int64 v5; // r9
  __int64 v6; // rcx
  WpnconTelemetry *v7; // rax
  unsigned int v9; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  *(_QWORD *)this = &CWNPInterfaceSelector::`vftable';
  *((_DWORD *)this + 3) = 20;
  *((_DWORD *)this + 4) = 21600;
  *((_DWORD *)this + 5) = 3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids);
  }
  hKey = 0;
  *((_BYTE *)this + 8) = WpnIsMobileCore();
  v3 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
         0,
         1u,
         &hKey);
  if ( v3 )
  {
    v4 = (unsigned __int8)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v3 > 0 )
        v5 = (unsigned __int16)v3 | 0x80070000;
      else
        v5 = (unsigned int)v3;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids, v5);
    }
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    v9 = 1;
    if ( (int)WpnRegLoadDWord(hKey, L"PreferCellularConnectivity", &v9) >= 0 )
      *((_BYTE *)this + 8) = v9 != 0;
    v9 = 1;
    if ( (int)WpnRegLoadDWord(hKey, L"WiFiSignalQuality", &v9) >= 0 )
      *((_DWORD *)this + 3) = v9;
    v9 = 1;
    if ( (int)WpnRegLoadDWord(hKey, L"WiFiAverageDuration", &v9) >= 0 )
      *((_DWORD *)this + 4) = v9;
    v9 = 1;
    if ( (int)WpnRegLoadDWord(hKey, L"WiFiMinimumUsageCount", &v9) >= 0 )
      *((_DWORD *)this + 5) = v9;
    RegCloseKey(hKey);
  }
  if ( WpnconTelemetry::IsEnabled(v4, v2) )
  {
    v7 = (WpnconTelemetry *)wil::details::static_lazy<WpnconTelemetry>::get(
                              v6,
                              _lambda_de4d36b645fed666bcd49a481e929f91_::_lambda_invoker_cdecl_);
    WpnconTelemetry::InterfaceSelector_(v7, *((unsigned __int8 *)this + 8), v3);
  }
  return this;
}

```

## disassembly

```asm
0x1800471d8  mov     [rsp-28h+arg_0], rcx
0x1800471dd  push    rbp
0x1800471de  push    rbx
0x1800471df  push    rsi
0x1800471e0  push    rdi
0x1800471e1  push    r14
0x1800471e3  mov     rbp, rsp
0x1800471e6  sub     rsp, 30h
0x1800471ea  mov     rbx, rcx
0x1800471ed  lea     rax, ??_7CWNPInterfaceSelector@@6B@; const CWNPInterfaceSelector::`vftable'
0x1800471f4  mov     [rcx], rax
0x1800471f7  mov     dword ptr [rcx+0Ch], 14h
0x1800471fe  mov     dword ptr [rcx+10h], 5460h
0x180047205  mov     dword ptr [rcx+14h], 3
0x18004720c  lea     r14, WPP_GLOBAL_Control
0x180047213  mov     rcx, cs:WPP_GLOBAL_Control
0x18004721a  cmp     rcx, r14
0x18004721d  jz      short loc_180047240
0x18004721f  test    byte ptr [rcx+1Ch], 4
0x180047223  jz      short loc_180047240
0x180047225  cmp     byte ptr [rcx+19h], 6
0x180047229  jb      short loc_180047240
0x18004722b  mov     edx, 0Ah
0x180047230  lea     r8, WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids
0x180047237  mov     rcx, [rcx+10h]
0x18004723b  call    WPP_SF_
0x180047240  mov     [rbp+hKey], 0
0x180047248  call    ?WpnIsMobileCore@@YAHXZ; WpnIsMobileCore(void)
0x18004724d  test    eax, eax
0x18004724f  setnz   al
0x180047252  mov     [rbx+8], al
0x180047255  lea     rax, [rbp+hKey]
0x180047259  mov     [rsp+30h+phkResult], rax; phkResult
0x18004725e  mov     esi, 1
0x180047263  mov     r9d, esi; samDesired
0x180047266  xor     r8d, r8d; ulOptions
0x180047269  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180047270  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047277  call    cs:__imp_RegOpenKeyExA
0x18004727d  mov     edi, eax
0x18004727f  test    eax, eax
0x180047281  jnz     loc_18004731A
0x180047287  mov     [rbp+arg_8], esi
0x18004728a  lea     r8, [rbp+arg_8]; unsigned int *
0x18004728e  lea     rdx, aPrefercellular; "PreferCellularConnectivity"
0x180047295  mov     rcx, [rbp+hKey]; hKey
0x180047299  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18004729e  test    eax, eax
0x1800472a0  js      short loc_1800472AB
0x1800472a2  cmp     [rbp+arg_8], edi
0x1800472a5  setnz   al
0x1800472a8  mov     [rbx+8], al
0x1800472ab  mov     [rbp+arg_8], esi
0x1800472ae  lea     r8, [rbp+arg_8]; unsigned int *
0x1800472b2  lea     rdx, aWifisignalqual; "WiFiSignalQuality"
0x1800472b9  mov     rcx, [rbp+hKey]; hKey
0x1800472bd  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x1800472c2  test    eax, eax
0x1800472c4  js      short loc_1800472CC
0x1800472c6  mov     eax, [rbp+arg_8]
0x1800472c9  mov     [rbx+0Ch], eax
0x1800472cc  mov     [rbp+arg_8], esi
0x1800472cf  lea     r8, [rbp+arg_8]; unsigned int *
0x1800472d3  lea     rdx, aWifiaveragedur; "WiFiAverageDuration"
0x1800472da  mov     rcx, [rbp+hKey]; hKey
0x1800472de  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x1800472e3  test    eax, eax
0x1800472e5  js      short loc_1800472ED
0x1800472e7  mov     eax, [rbp+arg_8]
0x1800472ea  mov     [rbx+10h], eax
0x1800472ed  mov     [rbp+arg_8], esi
0x1800472f0  lea     r8, [rbp+arg_8]; unsigned int *
0x1800472f4  lea     rdx, aWifiminimumusa; "WiFiMinimumUsageCount"
0x1800472fb  mov     rcx, [rbp+hKey]; hKey
0x1800472ff  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x180047304  test    eax, eax
0x180047306  js      short loc_18004730E
0x180047308  mov     eax, [rbp+arg_8]
0x18004730b  mov     [rbx+14h], eax
0x18004730e  mov     rcx, [rbp+hKey]; hKey
0x180047312  call    cs:__imp_RegCloseKey
0x180047318  jmp     short loc_180047365
0x18004731a  mov     esi, 80070000h
0x18004731f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047326  cmp     rcx, r14
0x180047329  jz      short loc_18004735C
0x18004732b  test    byte ptr [rcx+1Ch], 4
0x18004732f  jz      short loc_18004735C
0x180047331  cmp     byte ptr [rcx+19h], 2
0x180047335  jb      short loc_18004735C
0x180047337  test    edi, edi
0x180047339  jg      short loc_180047340
0x18004733b  mov     r9d, edi
0x18004733e  jmp     short loc_180047347
0x180047340  movzx   r9d, di
0x180047344  or      r9d, esi
0x180047347  mov     edx, 0Bh
0x18004734c  lea     r8, WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids
0x180047353  mov     rcx, [rcx+10h]
0x180047357  call    WPP_SF_d
0x18004735c  test    edi, edi
0x18004735e  jle     short loc_180047365
0x180047360  movzx   edi, di
0x180047363  or      edi, esi
0x180047365  call    ?IsEnabled@WpnconTelemetry@@SA_NE_K@Z; WpnconTelemetry::IsEnabled(uchar,unsigned __int64)
0x18004736a  test    al, al
0x18004736c  jz      short loc_18004738A
0x18004736e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_de4d36b645fed666bcd49a481e929f91_@@CA@XZ; _lambda_de4d36b645fed666bcd49a481e929f91_::_lambda_invoker_cdecl_(void)
0x180047375  call    ?get@?$static_lazy@VWpnconTelemetry@@@details@wil@@QEAAPEAVWpnconTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WpnconTelemetry>::get(void (*)(void))
0x18004737a  movzx   edx, byte ptr [rbx+8]; int
0x18004737e  mov     r8d, edi; int
0x180047381  mov     rcx, rax; this
0x180047384  call    ?InterfaceSelector_@WpnconTelemetry@@QEAAXHJ@Z; WpnconTelemetry::InterfaceSelector_(int,long)
0x180047389  nop
0x18004738a  mov     rax, rbx
0x18004738d  add     rsp, 30h
0x180047391  pop     r14
0x180047393  pop     rdi
0x180047394  pop     rsi
0x180047395  pop     rbx
0x180047396  pop     rbp
0x180047397  retn
```
