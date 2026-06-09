# BioPolicy::EnableVbs(void)

- ea: `0x1800bb55c`
- end: `0x1800bb616`
- name: `?EnableVbs@BioPolicy@@AEAAJXZ`
- size: `186`
- prototype: `__int64 __fastcall(BioPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026b28`

## callees

- `0x18005388c`
- `0x180074380`
- `0x1800bb55c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bb5a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bb608`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bb5a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bb608`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bb5de`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bb5de`

## string_xrefs

- `0x1800bb590`: `onecore\ds\security\biometrics\credprov\common\policy.cpp`

## pseudocode

```c
__int64 __fastcall BioPolicy::EnableVbs(BioPolicy *this)
{
  signed int v1; // ebx
  __int64 v2; // rdx
  LSTATUS v4; // eax
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  BioPolicy *Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  Data = this;
  hKey = 0;
  v1 = wil::reg::create_unique_key_nothrow(
         this,
         L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard\\Scenarios\\WindowsHelloSecureBiometrics",
         &hKey);
  if ( v1 < 0 )
  {
    v2 = 944;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\common\\policy.cpp",
      (const char *)(unsigned int)v1,
      lpData);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v1;
  }
  LODWORD(Data) = 1;
  v4 = RegSetKeyValueW(hKey, 0, L"Enabled", 4u, &Data, 4u);
  v1 = v4;
  if ( v4 > 0 )
    v1 = (unsigned __int16)v4 | 0x80070000;
  if ( v1 < 0 )
  {
    v2 = 945;
    goto LABEL_3;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800bb55c  mov     [rsp+Data], rcx
0x1800bb561  push    rbx
0x1800bb562  sub     rsp, 30h
0x1800bb566  lea     r8, [rsp+38h+hKey]
0x1800bb56b  mov     [rsp+38h+hKey], 0
0x1800bb574  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x1800bb57b  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x1800bb580  mov     ebx, eax
0x1800bb582  test    eax, eax
0x1800bb584  jns     short loc_1800BB5B3
0x1800bb586  mov     edx, 3B0h; void *
0x1800bb58b  mov     rcx, [rsp+38h]; this
0x1800bb590  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\biometrics\\cred"...
0x1800bb597  mov     r9d, ebx; char *
0x1800bb59a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb59f  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bb5a4  test    rcx, rcx
0x1800bb5a7  jz      short loc_1800BB5AF
0x1800bb5a9  call    cs:__imp_RegCloseKey
0x1800bb5af  mov     eax, ebx
0x1800bb5b1  jmp     short loc_1800BB610
0x1800bb5b3  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bb5b8  lea     rax, [rsp+38h+Data]
0x1800bb5bd  mov     r9d, 4; dwType
0x1800bb5c3  mov     dword ptr [rsp+38h+Data], 1
0x1800bb5cb  mov     [rsp+38h+cbData], r9d; cbData
0x1800bb5d0  lea     r8, aEnabled; "Enabled"
0x1800bb5d7  xor     edx, edx; lpSubKey
0x1800bb5d9  mov     [rsp+38h+lpData], rax; lpData
0x1800bb5de  call    cs:__imp_RegSetKeyValueW
0x1800bb5e4  mov     ebx, eax
0x1800bb5e6  test    eax, eax
0x1800bb5e8  jle     short loc_1800BB5F3
0x1800bb5ea  movzx   ebx, ax
0x1800bb5ed  or      ebx, 80070000h
0x1800bb5f3  test    ebx, ebx
0x1800bb5f5  jns     short loc_1800BB5FE
0x1800bb5f7  mov     edx, 3B1h
0x1800bb5fc  jmp     short loc_1800BB58B
0x1800bb5fe  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bb603  test    rcx, rcx
0x1800bb606  jz      short loc_1800BB60E
0x1800bb608  call    cs:__imp_RegCloseKey
0x1800bb60e  xor     eax, eax
0x1800bb610  add     rsp, 30h
0x1800bb614  pop     rbx
0x1800bb615  retn
```
