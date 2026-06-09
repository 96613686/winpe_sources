# SqmApiWrapper::GetSqmRegValue(ushort const *,ulong *)

- ea: `0x18001f3b4`
- end: `0x18001f54b`
- name: `?GetSqmRegValue@SqmApiWrapper@@CAJPEBGPEAK@Z`
- size: `407`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f554`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001f3b4`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f447`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f533`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f447`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f533`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f40d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f477`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f40d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f477`

## pseudocode

```c
__int64 __fastcall SqmApiWrapper::GetSqmRegValue(const unsigned __int16 *a1, unsigned int *a2)
{
  LSTATUS v4; // eax
  bool v5; // sf
  signed int v6; // ebx
  LSTATUS v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int DWord; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  hKey = 0;
  *a2 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\SQMClient", 0, 0x20019u, &hKey);
  v5 = v4 < 0;
  if ( v4 > 0 )
    v5 = 1;
  if ( v5 || (v6 = WpnRegLoadDWord(hKey, a1, a2), v6 < 0) )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\SQMClient", 0, 0x20019u, &hKey);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 >= 0 )
    {
      DWord = WpnRegLoadDWord(hKey, a1, a2);
      v6 = DWord;
      if ( DWord < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1E6,
          (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\sqmapiwrapper.cpp",
          (const char *)(unsigned int)DWord);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v9 = 31;
          goto LABEL_21;
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1E3,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\sqmapiwrapper.cpp",
        (const char *)(unsigned int)v6);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v9 = 30;
LABEL_21:
        WPP_SF_d(v8[2], v9, WPP_e99c31cab35e393e6b90b315b54d1141_Traceguids, (unsigned int)v6);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f3b4  mov     [rsp+arg_8], rbx
0x18001f3b9  mov     [rsp+arg_10], rsi
0x18001f3be  push    rdi
0x18001f3bf  sub     rsp, 30h
0x18001f3c3  mov     rdi, rdx
0x18001f3c6  mov     rsi, rcx
0x18001f3c9  test    rcx, rcx
0x18001f3cc  jnz     short loc_18001F3D3
0x18001f3ce  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f3d3  test    rdi, rdi
0x18001f3d6  jnz     short loc_18001F3DD
0x18001f3d8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f3dd  lea     rax, [rsp+38h+hKey]
0x18001f3e2  mov     [rsp+38h+hKey], 0
0x18001f3eb  mov     r9d, 20019h; samDesired
0x18001f3f1  mov     [rsp+38h+phkResult], rax; phkResult
0x18001f3f6  xor     r8d, r8d; ulOptions
0x18001f3f9  mov     dword ptr [rdi], 0
0x18001f3ff  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\SQMClien"...
0x18001f406  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f40d  call    cs:__imp_RegOpenKeyExW
0x18001f413  test    eax, eax
0x18001f415  jle     short loc_18001F421
0x18001f417  movzx   eax, ax
0x18001f41a  or      eax, 80070000h
0x18001f41f  test    eax, eax
0x18001f421  js      short loc_18001F43D
0x18001f423  mov     rcx, [rsp+38h+hKey]; hKey
0x18001f428  mov     r8, rdi; unsigned int *
0x18001f42b  mov     rdx, rsi; lpValueName
0x18001f42e  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18001f433  mov     ebx, eax
0x18001f435  test    eax, eax
0x18001f437  jns     loc_18001F529
0x18001f43d  mov     rcx, [rsp+38h+hKey]; hKey
0x18001f442  test    rcx, rcx
0x18001f445  jz      short loc_18001F456
0x18001f447  call    cs:__imp_RegCloseKey
0x18001f44d  mov     [rsp+38h+hKey], 0
0x18001f456  lea     rax, [rsp+38h+hKey]
0x18001f45b  mov     r9d, 20019h; samDesired
0x18001f461  xor     r8d, r8d; ulOptions
0x18001f464  mov     [rsp+38h+phkResult], rax; int
0x18001f469  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\SQMClient"
0x18001f470  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f477  call    cs:__imp_RegOpenKeyExW
0x18001f47d  mov     ebx, eax
0x18001f47f  test    eax, eax
0x18001f481  jle     short loc_18001F48C
0x18001f483  movzx   ebx, ax
0x18001f486  or      ebx, 80070000h
0x18001f48c  test    ebx, ebx
0x18001f48e  jns     short loc_18001F4C9
0x18001f490  mov     rcx, [rsp+38h]; this
0x18001f495  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f49c  mov     r9d, ebx; char *
0x18001f49f  mov     edx, 1E3h; void *
0x18001f4a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4b0  lea     rax, WPP_GLOBAL_Control
0x18001f4b7  cmp     rcx, rax
0x18001f4ba  jz      short loc_18001F529
0x18001f4bc  test    byte ptr [rcx+1Ch], 80h
0x18001f4c0  jz      short loc_18001F529
0x18001f4c2  mov     edx, 1Eh
0x18001f4c7  jmp     short loc_18001F516
0x18001f4c9  mov     rcx, [rsp+38h+hKey]; hKey
0x18001f4ce  mov     r8, rdi; unsigned int *
0x18001f4d1  mov     rdx, rsi; lpValueName
0x18001f4d4  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18001f4d9  mov     ebx, eax
0x18001f4db  test    eax, eax
0x18001f4dd  jns     short loc_18001F529
0x18001f4df  mov     rcx, [rsp+38h]; this
0x18001f4e4  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f4eb  mov     r9d, eax; char *
0x18001f4ee  mov     edx, 1E6h; void *
0x18001f4f3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4ff  lea     rax, WPP_GLOBAL_Control
0x18001f506  cmp     rcx, rax
0x18001f509  jz      short loc_18001F529
0x18001f50b  test    byte ptr [rcx+1Ch], 80h
0x18001f50f  jz      short loc_18001F529
0x18001f511  mov     edx, 1Fh
0x18001f516  mov     rcx, [rcx+10h]
0x18001f51a  lea     r8, WPP_e99c31cab35e393e6b90b315b54d1141_Traceguids
0x18001f521  mov     r9d, ebx
0x18001f524  call    WPP_SF_d
0x18001f529  mov     rcx, [rsp+38h+hKey]; hKey
0x18001f52e  test    rcx, rcx
0x18001f531  jz      short loc_18001F539
0x18001f533  call    cs:__imp_RegCloseKey
0x18001f539  mov     rsi, [rsp+38h+arg_10]
0x18001f53e  mov     eax, ebx
0x18001f540  mov     rbx, [rsp+38h+arg_8]
0x18001f545  add     rsp, 30h
0x18001f549  pop     rdi
0x18001f54a  retn
```
