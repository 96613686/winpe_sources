# GetBackupReminderToastCount(int &)

- ea: `0x180018fbc`
- end: `0x180019097`
- name: `?GetBackupReminderToastCount@@YAJAEAH@Z`
- size: `219`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018ea0`

## callees

- `0x180010464`
- `0x1800152d4`
- `0x180018fbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001904a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001904a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019007`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019007`

## pseudocode

```c
__int64 __fastcall GetBackupReminderToastCount(BYTE *a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  __int64 v4; // rdx
  LSTATUS v5; // eax
  int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  DWORD Type; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Type = 0;
  cbData = 4;
  hKey = 0;
  *(_DWORD *)a1 = 0;
  v2 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\BackupReminder",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    v5 = RegQueryValueExW(hKey, L"BackupReminderToastCount", 0, &Type, a1, &cbData);
    v3 = v5;
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    if ( v3 >= 0 )
    {
      v3 = 0;
      goto LABEL_11;
    }
    v4 = 2411;
  }
  else
  {
    v4 = 2404;
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
0x180018fbc  mov     rax, rsp
0x180018fbf  mov     [rax+20h], rbx
0x180018fc3  push    rdi
0x180018fc4  sub     rsp, 30h
0x180018fc8  mov     dword ptr [rax+10h], 0
0x180018fcf  mov     rdi, rcx
0x180018fd2  mov     dword ptr [rax+8], 4
0x180018fd9  mov     r9d, 20019h; samDesired
0x180018fdf  mov     qword ptr [rax+18h], 0
0x180018fe7  lea     rax, [rax+18h]
0x180018feb  mov     dword ptr [rcx], 0
0x180018ff1  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180018ff8  xor     r8d, r8d; ulOptions
0x180018ffb  mov     [rsp+38h+phkResult], rax; phkResult
0x180019000  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180019007  call    cs:__imp_RegOpenKeyExW
0x18001900d  mov     ebx, eax
0x18001900f  test    eax, eax
0x180019011  jle     short loc_18001901C
0x180019013  movzx   ebx, ax
0x180019016  or      ebx, 80070000h
0x18001901c  test    ebx, ebx
0x18001901e  jns     short loc_180019027
0x180019020  mov     edx, 964h
0x180019025  jmp     short loc_180019068
0x180019027  mov     rcx, [rsp+38h+hKey]; hKey
0x18001902c  lea     rax, [rsp+38h+cbData]
0x180019031  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180019036  lea     r9, [rsp+38h+Type]; lpType
0x18001903b  xor     r8d, r8d; lpReserved
0x18001903e  mov     [rsp+38h+phkResult], rdi; int
0x180019043  lea     rdx, aBackupreminder_0; "BackupReminderToastCount"
0x18001904a  call    cs:__imp_RegQueryValueExW
0x180019050  mov     ebx, eax
0x180019052  test    eax, eax
0x180019054  jle     short loc_18001905F
0x180019056  movzx   ebx, ax
0x180019059  or      ebx, 80070000h
0x18001905f  test    ebx, ebx
0x180019061  jns     short loc_18001907E
0x180019063  mov     edx, 96Bh; void *
0x180019068  mov     rcx, [rsp+38h]; this
0x18001906d  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180019074  mov     r9d, ebx; char *
0x180019077  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001907c  jmp     short loc_180019080
0x18001907e  xor     ebx, ebx
0x180019080  lea     rcx, [rsp+38h+hKey]
0x180019085  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001908a  mov     eax, ebx
0x18001908c  mov     rbx, [rsp+38h+arg_18]
0x180019091  add     rsp, 30h
0x180019095  pop     rdi
0x180019096  retn
```
