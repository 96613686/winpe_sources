# _SetVersioningValue(ushort const *,ulong)

- ea: `0x18009be34`
- end: `0x18009bf5e`
- name: `?_SetVersioningValue@@YAJPEBGK@Z`
- size: `298`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007ba00`
- `0x18009b6b0`

## callees

- `0x1800068f0`
- `0x18001a6c4`
- `0x18009be34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009befc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009befc`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18009bf22`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18009bf22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009becb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009bf50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009becb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009bf50`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009be8f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009be8f`

## string_xrefs

- `0x18009beae`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall _SetVersioningValue(const unsigned __int16 *a1, int a2)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  signed int v4; // ebx
  __int64 v5; // r9
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+68h] [rbp+10h] BYREF

  Data = a2;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unistore", 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  v4 = Key;
  if ( Key > 0 )
    v4 = (unsigned __int16)Key | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = 129;
LABEL_5:
    Log_UnistoreHREvent_0(
      (unsigned int)v4,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      v5);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v4;
  }
  v7 = RegSetValueExW(hKey, L"StoreVersion", 0, 4u, (const BYTE *)&Data, 4u);
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = 138;
    goto LABEL_5;
  }
  v8 = RegFlushKey(hKey);
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = 140;
    goto LABEL_5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18009be34  mov     rax, rsp
0x18009be37  mov     [rax+10h], edx
0x18009be3a  mov     [rax+8], rcx
0x18009be3e  push    rbx
0x18009be3f  sub     rsp, 50h
0x18009be43  lea     rcx, [rax+8]
0x18009be47  mov     qword ptr [rax+8], 0
0x18009be4f  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18009be54  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18009be5d  lea     rdx, SubKey; "Software\\Microsoft\\Unistore"
0x18009be64  mov     [rsp+58h+phkResult], rax; phkResult
0x18009be69  xor     r9d, r9d; lpClass
0x18009be6c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009be75  xor     r8d, r8d; Reserved
0x18009be78  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18009be80  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18009be87  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18009be8f  call    cs:__imp_RegCreateKeyExW
0x18009be95  mov     ebx, eax
0x18009be97  test    eax, eax
0x18009be99  jle     short loc_18009BEA4
0x18009be9b  movzx   ebx, ax
0x18009be9e  or      ebx, 80070000h
0x18009bea4  test    ebx, ebx
0x18009bea6  jns     short loc_18009BED8
0x18009bea8  mov     r9d, 81h
0x18009beae  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009beb5  mov     edx, 1
0x18009beba  mov     ecx, ebx
0x18009bebc  call    Log_UnistoreHREvent_0
0x18009bec1  mov     rcx, [rsp+58h+hKey]; hKey
0x18009bec6  test    rcx, rcx
0x18009bec9  jz      short loc_18009BED1
0x18009becb  call    cs:__imp_RegCloseKey
0x18009bed1  mov     eax, ebx
0x18009bed3  jmp     loc_18009BF58
0x18009bed8  mov     rcx, [rsp+58h+hKey]; hKey
0x18009bedd  lea     rax, [rsp+58h+Data]
0x18009bee2  mov     r9d, 4; dwType
0x18009bee8  lea     rdx, ValueName; "StoreVersion"
0x18009beef  mov     [rsp+58h+samDesired], r9d; cbData
0x18009bef4  xor     r8d, r8d; Reserved
0x18009bef7  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18009befc  call    cs:__imp_RegSetValueExW
0x18009bf02  mov     ebx, eax
0x18009bf04  test    eax, eax
0x18009bf06  jle     short loc_18009BF11
0x18009bf08  movzx   ebx, ax
0x18009bf0b  or      ebx, 80070000h
0x18009bf11  test    ebx, ebx
0x18009bf13  jns     short loc_18009BF1D
0x18009bf15  mov     r9d, 8Ah
0x18009bf1b  jmp     short loc_18009BEAE
0x18009bf1d  mov     rcx, [rsp+58h+hKey]; hKey
0x18009bf22  call    cs:__imp_RegFlushKey
0x18009bf28  mov     ebx, eax
0x18009bf2a  test    eax, eax
0x18009bf2c  jle     short loc_18009BF37
0x18009bf2e  movzx   ebx, ax
0x18009bf31  or      ebx, 80070000h
0x18009bf37  test    ebx, ebx
0x18009bf39  jns     short loc_18009BF46
0x18009bf3b  mov     r9d, 8Ch
0x18009bf41  jmp     loc_18009BEAE
0x18009bf46  mov     rcx, [rsp+58h+hKey]; hKey
0x18009bf4b  test    rcx, rcx
0x18009bf4e  jz      short loc_18009BF56
0x18009bf50  call    cs:__imp_RegCloseKey
0x18009bf56  xor     eax, eax
0x18009bf58  add     rsp, 50h
0x18009bf5c  pop     rbx
0x18009bf5d  retn
```
