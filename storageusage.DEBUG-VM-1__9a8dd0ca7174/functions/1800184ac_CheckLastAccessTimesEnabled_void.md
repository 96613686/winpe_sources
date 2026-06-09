# CheckLastAccessTimesEnabled(void)

- ea: `0x1800184ac`
- end: `0x1800185b2`
- name: `?CheckLastAccessTimesEnabled@@YAJXZ`
- size: `262`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18001b650`
- `0x18001b7d0`

## callees

- `0x180010464`
- `0x1800152d4`
- `0x1800184ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001850f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001850f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018557`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018557`

## string_xrefs

- `0x18001854b`: `NtfsDisableLastAccessUpdate`

## pseudocode

```c
__int64 CheckLastAccessTimesEnabled(void)
{
  LSTATUS v0; // eax
  signed int v1; // ebx
  __int64 v2; // rdx
  LSTATUS v3; // eax
  int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int Data; // [rsp+60h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  Type = 0;
  Data = 0;
  cbData = 4;
  hKey = 0;
  v0 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\FileSystem", 0, 0, 0, 1u, 0, &hKey, 0);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 >= 0 )
  {
    v3 = RegQueryValueExW(hKey, L"NtfsDisableLastAccessUpdate", 0, &Type, (LPBYTE)&Data, &cbData);
    v1 = v3;
    if ( v3 > 0 )
      v1 = (unsigned __int16)v3 | 0x80070000;
    if ( v1 >= 0 )
    {
      v1 = ((Data + 0x80000000) & 0xFFFFFFFD) != 0 ? 0x32 : 0;
      goto LABEL_11;
    }
    v2 = 3386;
  }
  else
  {
    v2 = 3380;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
    (const char *)(unsigned int)v1,
    dwOptions);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800184ac  mov     rax, rsp
0x1800184af  push    rbx
0x1800184b0  sub     rsp, 50h
0x1800184b4  mov     qword ptr [rax-18h], 0
0x1800184bc  xor     r9d, r9d; lpClass
0x1800184bf  mov     dword ptr [rax+18h], 0
0x1800184c6  xor     r8d, r8d; Reserved
0x1800184c9  mov     dword ptr [rax+8], 0
0x1800184d0  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Fil"...
0x1800184d7  mov     dword ptr [rax+10h], 4
0x1800184de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800184e5  mov     qword ptr [rax+20h], 0
0x1800184ed  lea     rax, [rax+20h]
0x1800184f1  mov     [rsp+58h+phkResult], rax; phkResult
0x1800184f6  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800184ff  mov     [rsp+58h+samDesired], 1; samDesired
0x180018507  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001850f  call    cs:__imp_RegCreateKeyExW
0x180018515  mov     ebx, eax
0x180018517  test    eax, eax
0x180018519  jle     short loc_180018524
0x18001851b  movzx   ebx, ax
0x18001851e  or      ebx, 80070000h
0x180018524  test    ebx, ebx
0x180018526  jns     short loc_18001852F
0x180018528  mov     edx, 0D34h
0x18001852d  jmp     short loc_180018575
0x18001852f  mov     rcx, [rsp+58h+hKey]; hKey
0x180018534  lea     rax, [rsp+58h+cbData]
0x180018539  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x18001853e  lea     r9, [rsp+58h+Type]; lpType
0x180018543  lea     rax, [rsp+58h+Data]
0x180018548  xor     r8d, r8d; lpReserved
0x18001854b  lea     rdx, ValueName; "NtfsDisableLastAccessUpdate"
0x180018552  mov     qword ptr [rsp+58h+dwOptions], rax; int
0x180018557  call    cs:__imp_RegQueryValueExW
0x18001855d  mov     ebx, eax
0x18001855f  test    eax, eax
0x180018561  jle     short loc_18001856C
0x180018563  movzx   ebx, ax
0x180018566  or      ebx, 80070000h
0x18001856c  test    ebx, ebx
0x18001856e  jns     short loc_18001858B
0x180018570  mov     edx, 0D3Ah; void *
0x180018575  mov     rcx, [rsp+58h]; this
0x18001857a  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180018581  mov     r9d, ebx; char *
0x180018584  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018589  jmp     short loc_1800185A0
0x18001858b  mov     ecx, 80000000h
0x180018590  add     ecx, [rsp+58h+Data]
0x180018594  and     ecx, 0FFFFFFFDh
0x180018597  neg     ecx
0x180018599  sbb     eax, eax
0x18001859b  and     eax, 32h
0x18001859e  mov     ebx, eax
0x1800185a0  lea     rcx, [rsp+58h+hKey]
0x1800185a5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800185aa  mov     eax, ebx
0x1800185ac  add     rsp, 50h
0x1800185b0  pop     rbx
0x1800185b1  retn
```
