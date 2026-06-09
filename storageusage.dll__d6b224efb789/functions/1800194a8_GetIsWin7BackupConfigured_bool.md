# GetIsWin7BackupConfigured(bool &)

- ea: `0x1800194a8`
- end: `0x180019588`
- name: `?GetIsWin7BackupConfigured@@YAJAEA_N@Z`
- size: `224`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018ea0`

## callees

- `0x180010464`
- `0x1800152d4`
- `0x1800194a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001953c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001953c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800194f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800194f4`

## pseudocode

```c
__int64 __fastcall GetIsWin7BackupConfigured(bool *a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  __int64 v4; // rdx
  LSTATUS v5; // eax
  int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  Type = 0;
  Data = 0;
  cbData = 4;
  hKey = 0;
  *a1 = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\Status",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    v5 = RegQueryValueExW(hKey, L"LastResultHr", 0, &Type, (LPBYTE)&Data, &cbData);
    v3 = v5;
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    if ( v3 >= 0 )
    {
      *a1 = 1;
      v3 = 0;
      goto LABEL_11;
    }
    v4 = 2281;
  }
  else
  {
    v4 = 2274;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
    (const char *)(unsigned int)v3,
    phkResult);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800194a8  mov     rax, rsp
0x1800194ab  push    rbx
0x1800194ac  push    rdi
0x1800194ad  sub     rsp, 38h
0x1800194b1  mov     dword ptr [rax+18h], 0
0x1800194b8  mov     rdi, rcx
0x1800194bb  mov     dword ptr [rax+10h], 0
0x1800194c2  mov     r9d, 20019h; samDesired
0x1800194c8  mov     dword ptr [rax+8], 4
0x1800194cf  xor     r8d, r8d; ulOptions
0x1800194d2  mov     qword ptr [rax+20h], 0
0x1800194da  lea     rax, [rax+20h]
0x1800194de  mov     byte ptr [rcx], 0
0x1800194e1  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800194e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800194ef  mov     [rsp+48h+phkResult], rax; phkResult
0x1800194f4  call    cs:__imp_RegOpenKeyExW
0x1800194fa  mov     ebx, eax
0x1800194fc  test    eax, eax
0x1800194fe  jle     short loc_180019509
0x180019500  movzx   ebx, ax
0x180019503  or      ebx, 80070000h
0x180019509  test    ebx, ebx
0x18001950b  jns     short loc_180019514
0x18001950d  mov     edx, 8E2h
0x180019512  jmp     short loc_18001955A
0x180019514  mov     rcx, [rsp+48h+hKey]; hKey
0x180019519  lea     rax, [rsp+48h+cbData]
0x18001951e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180019523  lea     r9, [rsp+48h+Type]; lpType
0x180019528  lea     rax, [rsp+48h+Data]
0x18001952d  xor     r8d, r8d; lpReserved
0x180019530  lea     rdx, aLastresulthr; "LastResultHr"
0x180019537  mov     [rsp+48h+phkResult], rax; int
0x18001953c  call    cs:__imp_RegQueryValueExW
0x180019542  mov     ebx, eax
0x180019544  test    eax, eax
0x180019546  jle     short loc_180019551
0x180019548  movzx   ebx, ax
0x18001954b  or      ebx, 80070000h
0x180019551  test    ebx, ebx
0x180019553  jns     short loc_180019570
0x180019555  mov     edx, 8E9h; void *
0x18001955a  mov     rcx, [rsp+48h]; this
0x18001955f  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180019566  mov     r9d, ebx; char *
0x180019569  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001956e  jmp     short loc_180019575
0x180019570  mov     byte ptr [rdi], 1
0x180019573  xor     ebx, ebx
0x180019575  lea     rcx, [rsp+48h+hKey]
0x18001957a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001957f  mov     eax, ebx
0x180019581  add     rsp, 38h
0x180019585  pop     rdi
0x180019586  pop     rbx
0x180019587  retn
```
