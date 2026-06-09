# SubscriptionConfigModeReader::SubscriptionConfigModeReader(_EC_SUBSCRIPTION_CONFIGURATION_MODE)

- ea: `0x1800143f8`
- end: `0x1800145c3`
- name: `??0SubscriptionConfigModeReader@@QEAA@W4_EC_SUBSCRIPTION_CONFIGURATION_MODE@@@Z`
- size: `459`
- prototype: `SubscriptionConfigModeReader *__fastcall(SubscriptionConfigModeReader *__hidden this, enum _EC_SUBSCRIPTION_CONFIGURATION_MODE)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001483c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x1800143f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001451b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001451b`

## string_xrefs

- `0x1800144ff`: `SOFTWARE\Microsoft\Windows\CurrentVersion\EventCollector\ConfigurationModes\Normal`
- `0x1800144f6`: `SOFTWARE\Microsoft\Windows\CurrentVersion\EventCollector\ConfigurationModes\Custom`
- `0x1800144ed`: `SOFTWARE\Microsoft\Windows\CurrentVersion\EventCollector\ConfigurationModes\MinLatency`
- `0x1800144e4`: `SOFTWARE\Microsoft\Windows\CurrentVersion\EventCollector\ConfigurationModes\MinBandwidth`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SubscriptionConfigModeReader *__fastcall SubscriptionConfigModeReader::SubscriptionConfigModeReader(
        SubscriptionConfigModeReader *this,
        enum _EC_SUBSCRIPTION_CONFIGURATION_MODE a2)
{
  HKEY *phkResult; // rcx
  int v4; // edx
  int v5; // edx
  const WCHAR *v6; // rdx
  unsigned int v7; // edi
  void **pExceptionObject; // [rsp+30h] [rbp-40h] BYREF
  char v10; // [rsp+38h] [rbp-38h]
  const char *v11; // [rsp+40h] [rbp-30h]
  __int64 v12; // [rsp+48h] [rbp-28h]
  __int64 v13; // [rsp+50h] [rbp-20h]
  int v14; // [rsp+58h] [rbp-18h]
  int v15; // [rsp+5Ch] [rbp-14h]
  int v16; // [rsp+60h] [rbp-10h]

  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  phkResult = (HKEY *)((char *)this + 16);
  *phkResult = 0;
  *(_QWORD *)this = &SubscriptionGlobalsReader::`vftable';
  *((_DWORD *)this + 6) = a2;
  if ( a2 )
  {
    v4 = a2 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        if ( v5 != 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, 87);
          }
          v10 = 0;
          v11 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
          v12 = 0;
          v13 = 0;
          v14 = 87;
          v15 = -1;
          v16 = 146;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::GenericException *)&pExceptionObject;
        }
        v6 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector\\ConfigurationModes\\MinBandwidth";
      }
      else
      {
        v6 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector\\ConfigurationModes\\MinLatency";
      }
    }
    else
    {
      v6 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector\\ConfigurationModes\\Custom";
    }
  }
  else
  {
    v6 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector\\ConfigurationModes\\Normal";
  }
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, phkResult);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v7);
    }
    v10 = 0;
    v11 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v12 = 0;
    v13 = 0;
    v14 = v7;
    v15 = -1;
    v16 = 157;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x1800143f8  mov     [rsp-8+arg_8], rbx
0x1800143fd  mov     [rsp-8+arg_10], rdi
0x180014402  mov     [rsp-8+arg_0], rcx
0x180014407  push    rbp
0x180014408  mov     rbp, rsp
0x18001440b  sub     rsp, 70h
0x18001440f  mov     rbx, rcx
0x180014412  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180014419  mov     [rcx], rax
0x18001441c  mov     dword ptr [rcx+8], 0
0x180014423  add     rcx, 10h
0x180014427  mov     qword ptr [rcx], 0
0x18001442e  lea     rax, ??_7SubscriptionGlobalsReader@@6B@; const SubscriptionGlobalsReader::`vftable'
0x180014435  mov     [rbx], rax
0x180014438  mov     [rbx+18h], edx
0x18001443b  test    edx, edx
0x18001443d  jz      loc_1800144FF
0x180014443  sub     edx, 1
0x180014446  jz      loc_1800144F6
0x18001444c  sub     edx, 1
0x18001444f  jz      loc_1800144ED
0x180014455  cmp     edx, 1
0x180014458  jz      loc_1800144E4
0x18001445e  lea     rax, WPP_GLOBAL_Control
0x180014465  mov     ebx, 57h ; 'W'
0x18001446a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014471  cmp     rcx, rax
0x180014474  jz      short loc_180014498
0x180014476  test    byte ptr [rcx+1Ch], 40h
0x18001447a  jz      short loc_180014498
0x18001447c  cmp     byte ptr [rcx+19h], 2
0x180014480  jb      short loc_180014498
0x180014482  lea     edx, [rbx-46h]
0x180014485  mov     r9d, ebx
0x180014488  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x18001448f  mov     rcx, [rcx+10h]
0x180014493  call    WPP_SF_D
0x180014498  mov     [rbp+var_38], 0
0x18001449c  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x1800144a3  mov     [rbp+var_30], rax
0x1800144a7  mov     [rbp+var_28], 0
0x1800144af  mov     [rbp+var_20], 0
0x1800144b7  mov     [rbp+var_18], ebx
0x1800144ba  mov     [rbp+var_14], 0FFFFFFFFh
0x1800144c1  mov     [rbp+var_10], 92h
0x1800144c8  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800144cf  mov     [rbp+pExceptionObject], rax
0x1800144d3  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800144da  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800144de  call    _CxxThrowException_0
0x1800144e4  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800144eb  jmp     short loc_180014506
0x1800144ed  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800144f4  jmp     short loc_180014506
0x1800144f6  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800144fd  jmp     short loc_180014506
0x1800144ff  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180014506  mov     [rsp+70h+phkResult], rcx; phkResult
0x18001450b  mov     r9d, 20019h; samDesired
0x180014511  xor     r8d, r8d; ulOptions
0x180014514  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001451b  call    cs:__imp_RegOpenKeyExW
0x180014521  mov     edi, eax
0x180014523  test    eax, eax
0x180014525  jz      loc_1800145AE
0x18001452b  lea     rax, WPP_GLOBAL_Control
0x180014532  mov     rcx, cs:WPP_GLOBAL_Control
0x180014539  cmp     rcx, rax
0x18001453c  jz      short loc_180014562
0x18001453e  test    byte ptr [rcx+1Ch], 40h
0x180014542  jz      short loc_180014562
0x180014544  cmp     byte ptr [rcx+19h], 2
0x180014548  jb      short loc_180014562
0x18001454a  mov     edx, 12h
0x18001454f  mov     r9d, edi
0x180014552  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180014559  mov     rcx, [rcx+10h]
0x18001455d  call    WPP_SF_D
0x180014562  mov     [rbp+var_38], 0
0x180014566  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x18001456d  mov     [rbp+var_30], rax
0x180014571  mov     [rbp+var_28], 0
0x180014579  mov     [rbp+var_20], 0
0x180014581  mov     [rbp+var_18], edi
0x180014584  mov     [rbp+var_14], 0FFFFFFFFh
0x18001458b  mov     [rbp+var_10], 9Dh
0x180014592  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180014599  mov     [rbp+pExceptionObject], rax
0x18001459d  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800145a4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800145a8  call    _CxxThrowException_0
0x1800145ae  mov     rax, rbx
0x1800145b1  lea     r11, [rsp+70h+var_s0]
0x1800145b6  mov     rbx, [r11+18h]
0x1800145ba  mov     rdi, [r11+20h]
0x1800145be  mov     rsp, r11
0x1800145c1  pop     rbp
0x1800145c2  retn
```
