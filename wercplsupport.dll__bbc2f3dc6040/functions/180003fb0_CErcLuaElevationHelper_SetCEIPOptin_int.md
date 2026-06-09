# CErcLuaElevationHelper::SetCEIPOptin(int)

- ea: `0x180003fb0`
- end: `0x18000419c`
- name: `?SetCEIPOptin@CErcLuaElevationHelper@@UEAAJH@Z`
- size: `492`
- prototype: `__int64 __fastcall(CErcLuaElevationHelper *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002a18`
- `0x180003fb0`
- `0x180006c9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004135`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004135`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004027`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004027`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004184`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004184`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004102`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004102`

## string_xrefs

- `0x18000410c`: `CEIPEnableLastUpdateTime`

## pseudocode

```c
__int64 __fastcall CErcLuaElevationHelper::SetCEIPOptin(CErcLuaElevationHelper *this, int a2)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  signed int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  BYTE v11[8]; // [rsp+50h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-8h] BYREF
  BOOL Data; // [rsp+80h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+28h] BYREF

  hKey = 0;
  Data = 0;
  SystemTimeAsFileTime = 0;
  *(_QWORD *)v11 = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\SQMClient\\Windows",
          0,
          0,
          0,
          0x20006u,
          0,
          phkResult,
          0);
  v5 = Key;
  if ( Key )
  {
    if ( Key > 0 )
      v5 = (unsigned __int16)Key | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 21;
LABEL_9:
      WPP_SF_d(v6[2], v7, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, (unsigned int)v5);
    }
  }
  else
  {
    Data = a2 != 0;
    v8 = RegSetValueExW(hKey, L"CEIPEnable", 0, 4u, (const BYTE *)&Data, 4u);
    v5 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 22;
        goto LABEL_9;
      }
    }
    else
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      *(struct _FILETIME *)v11 = SystemTimeAsFileTime;
      v9 = RegSetValueExW(hKey, L"CEIPEnableLastUpdateTime", 0, 0xBu, v11, 8u);
      v5 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147467259;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 23;
          goto LABEL_9;
        }
      }
      else
      {
        v5 = 0;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003fb0  mov     [rsp-8+arg_0], rbx
0x180003fb5  mov     [rsp-8+arg_8], rdi
0x180003fba  push    rbp
0x180003fbb  mov     rbp, rsp
0x180003fbe  sub     rsp, 60h
0x180003fc2  lea     rcx, [rbp+hKey]
0x180003fc6  mov     [rbp+hKey], 0
0x180003fce  mov     edi, edx
0x180003fd0  mov     [rbp+Data], 0
0x180003fd7  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180003fdf  mov     qword ptr [rbp+var_10], 0
0x180003fe7  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180003fec  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180003ff5  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\SQMClient\\Windows"
0x180003ffc  mov     [rsp+60h+phkResult], rax; phkResult
0x180004001  xor     r9d, r9d; lpClass
0x180004004  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000400d  xor     r8d, r8d; Reserved
0x180004010  mov     [rsp+60h+samDesired], 20006h; samDesired
0x180004018  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000401f  mov     [rsp+60h+dwOptions], 0; dwOptions
0x180004027  call    cs:__imp_RegCreateKeyExW
0x18000402d  mov     ebx, eax
0x18000402f  test    eax, eax
0x180004031  jz      short loc_180004086
0x180004033  jle     short loc_18000403E
0x180004035  movzx   ebx, ax
0x180004038  or      ebx, 80070000h
0x18000403e  test    ebx, ebx
0x180004040  mov     eax, 80004005h
0x180004045  cmovns  ebx, eax
0x180004048  mov     rcx, cs:WPP_GLOBAL_Control
0x18000404f  lea     rax, WPP_GLOBAL_Control
0x180004056  cmp     rcx, rax
0x180004059  jz      loc_18000417B
0x18000405f  test    byte ptr [rcx+1Ch], 1
0x180004063  jz      loc_18000417B
0x180004069  mov     edx, 15h
0x18000406e  mov     rcx, [rcx+10h]
0x180004072  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180004079  mov     r9d, ebx
0x18000407c  call    WPP_SF_d
0x180004081  jmp     loc_18000417B
0x180004086  mov     rcx, [rbp+hKey]; hKey
0x18000408a  lea     rdx, aCeipenable; "CEIPEnable"
0x180004091  xor     eax, eax
0x180004093  mov     r9d, 4; dwType
0x180004099  mov     [rsp+60h+samDesired], r9d; cbData
0x18000409e  test    edi, edi
0x1800040a0  setnz   al
0x1800040a3  xor     r8d, r8d; Reserved
0x1800040a6  mov     [rbp+Data], eax
0x1800040a9  lea     rax, [rbp+Data]
0x1800040ad  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800040b2  call    cs:__imp_RegSetValueExW
0x1800040b8  mov     ebx, eax
0x1800040ba  test    eax, eax
0x1800040bc  jz      short loc_1800040FE
0x1800040be  jle     short loc_1800040C9
0x1800040c0  movzx   ebx, ax
0x1800040c3  or      ebx, 80070000h
0x1800040c9  test    ebx, ebx
0x1800040cb  mov     eax, 80004005h
0x1800040d0  cmovns  ebx, eax
0x1800040d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040da  lea     rax, WPP_GLOBAL_Control
0x1800040e1  cmp     rcx, rax
0x1800040e4  jz      loc_18000417B
0x1800040ea  test    byte ptr [rcx+1Ch], 1
0x1800040ee  jz      loc_18000417B
0x1800040f4  mov     edx, 16h
0x1800040f9  jmp     loc_18000406E
0x1800040fe  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004102  call    cs:__imp_GetSystemTimeAsFileTime
0x180004108  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000410c  lea     rdx, aCeipenablelast; "CEIPEnableLastUpdateTime"
0x180004113  mov     rcx, [rbp+hKey]; hKey
0x180004117  mov     r9d, 0Bh; dwType
0x18000411d  mov     qword ptr [rbp+var_10], rax
0x180004121  xor     r8d, r8d; Reserved
0x180004124  lea     rax, [rbp+var_10]
0x180004128  mov     [rsp+60h+samDesired], 8; cbData
0x180004130  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180004135  call    cs:__imp_RegSetValueExW
0x18000413b  mov     ebx, eax
0x18000413d  test    eax, eax
0x18000413f  jz      short loc_180004179
0x180004141  jle     short loc_18000414C
0x180004143  movzx   ebx, ax
0x180004146  or      ebx, 80070000h
0x18000414c  test    ebx, ebx
0x18000414e  mov     eax, 80004005h
0x180004153  cmovns  ebx, eax
0x180004156  mov     rcx, cs:WPP_GLOBAL_Control
0x18000415d  lea     rax, WPP_GLOBAL_Control
0x180004164  cmp     rcx, rax
0x180004167  jz      short loc_18000417B
0x180004169  test    byte ptr [rcx+1Ch], 1
0x18000416d  jz      short loc_18000417B
0x18000416f  mov     edx, 17h
0x180004174  jmp     loc_18000406E
0x180004179  xor     ebx, ebx
0x18000417b  mov     rcx, [rbp+hKey]; hKey
0x18000417f  test    rcx, rcx
0x180004182  jz      short loc_18000418A
0x180004184  call    cs:__imp_RegCloseKey
0x18000418a  mov     rdi, [rsp+60h+arg_8]
0x18000418f  mov     eax, ebx
0x180004191  mov     rbx, [rsp+60h+arg_0]
0x180004196  add     rsp, 60h
0x18000419a  pop     rbp
0x18000419b  retn
```
