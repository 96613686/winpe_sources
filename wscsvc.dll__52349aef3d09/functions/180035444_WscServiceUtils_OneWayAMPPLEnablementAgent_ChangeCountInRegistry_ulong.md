# WscServiceUtils::OneWayAMPPLEnablementAgent::ChangeCountInRegistry(ulong)

- ea: `0x180035444`
- end: `0x18003550f`
- name: `?ChangeCountInRegistry@OneWayAMPPLEnablementAgent@WscServiceUtils@@AEAA_NK@Z`
- size: `203`
- prototype: `char __fastcall(WscServiceUtils::OneWayAMPPLEnablementAgent *this, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800351ac`
- `0x180035548`

## callees

- `0x180008e48`
- `0x18001f9f4`
- `0x180035444`
- `0x180035dd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800354af`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800354af`

## pseudocode

```c
char __fastcall WscServiceUtils::OneWayAMPPLEnablementAgent::ChangeCountInRegistry(
        WscServiceUtils::OneWayAMPPLEnablementAgent *this,
        __int64 a2)
{
  int v2; // ebx
  int v3; // eax
  CThirdPartyManager *v4; // rcx
  __int64 v5; // rdx
  bool v6; // sf
  char v7; // bl
  WscServiceUtils::OneWayAMPPLEnablementAgent *Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Data = this;
  hKey = 0;
  v2 = a2;
  v3 = wil::reg::create_unique_key_nothrow(this, a2, &hKey);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_12;
    }
    v5 = 37;
    goto LABEL_11;
  }
  LODWORD(Data) = v2;
  v3 = RegSetKeyValueW(hKey, 0, L"NumNCP", 4u, &Data, 4u);
  v6 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3 | 0x80070000;
    v6 = v3 < 0;
  }
  if ( !v6 )
  {
    v7 = 1;
    goto LABEL_14;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = 38;
LABEL_11:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, (unsigned int)v3);
  }
LABEL_12:
  v7 = 0;
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v7;
}

```

## disassembly

```asm
0x180035444  mov     [rsp+Data], rcx
0x180035449  push    rbx
0x18003544a  sub     rsp, 30h
0x18003544e  lea     r8, [rsp+38h+hKey]
0x180035453  mov     [rsp+38h+hKey], 0
0x18003545c  mov     ebx, edx
0x18003545e  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180035463  test    eax, eax
0x180035465  jns     short loc_180035488
0x180035467  mov     rcx, cs:WPP_GLOBAL_Control
0x18003546e  lea     rdx, WPP_GLOBAL_Control
0x180035475  cmp     rcx, rdx
0x180035478  jz      short loc_1800354F7
0x18003547a  mov     bl, 1
0x18003547c  test    [rcx+1Ch], bl
0x18003547f  jz      short loc_1800354F7
0x180035481  mov     edx, 25h ; '%'
0x180035486  jmp     short loc_1800354E4
0x180035488  mov     rcx, [rsp+38h+hKey]; hKey
0x18003548d  lea     rax, [rsp+38h+Data]
0x180035492  mov     r9d, 4; dwType
0x180035498  mov     dword ptr [rsp+38h+Data], ebx
0x18003549c  mov     [rsp+38h+cbData], r9d; cbData
0x1800354a1  lea     r8, aNumncp; "NumNCP"
0x1800354a8  xor     edx, edx; lpSubKey
0x1800354aa  mov     [rsp+38h+lpData], rax; lpData
0x1800354af  call    cs:__imp_RegSetKeyValueW
0x1800354b5  test    eax, eax
0x1800354b7  jle     short loc_1800354C3
0x1800354b9  movzx   eax, ax
0x1800354bc  or      eax, 80070000h
0x1800354c1  test    eax, eax
0x1800354c3  jns     short loc_1800354FB
0x1800354c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800354cc  lea     rdx, WPP_GLOBAL_Control
0x1800354d3  cmp     rcx, rdx
0x1800354d6  jz      short loc_1800354F7
0x1800354d8  mov     bl, 1
0x1800354da  test    [rcx+1Ch], bl
0x1800354dd  jz      short loc_1800354F7
0x1800354df  mov     edx, 26h ; '&'
0x1800354e4  mov     rcx, [rcx+10h]
0x1800354e8  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x1800354ef  mov     r9d, eax
0x1800354f2  call    WPP_SF_d
0x1800354f7  xor     ebx, ebx
0x1800354f9  jmp     short loc_1800354FD
0x1800354fb  mov     bl, 1
0x1800354fd  lea     rcx, [rsp+38h+hKey]
0x180035502  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180035507  mov     al, bl
0x180035509  add     rsp, 30h
0x18003550d  pop     rbx
0x18003550e  retn
```
