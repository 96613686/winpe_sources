# SchdpGetAdminSetting(ulong *)

- ea: `0x1800072cc`
- end: `0x1800073e4`
- name: `?SchdpGetAdminSetting@@YAJPEAK@Z`
- size: `280`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007810`

## callees

- `0x1800072cc`
- `0x18000b13c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000736b`
- `ADVAPI32!RegQueryValueExW` at `0x18000736b`
- `ADVAPI32!RegCloseKey` at `0x1800073cd`
- `ADVAPI32!RegCloseKey` at `0x1800073cd`
- `ADVAPI32!RegOpenKeyExW` at `0x18000730e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000730e`

## string_xrefs

- `0x1800072e4`: `Software\Microsoft\Windows\ScheduledDiagnostics`

## pseudocode

```c
__int64 __fastcall SchdpGetAdminSetting(unsigned int *a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  int v4; // r8d
  LSTATUS v5; // eax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\ScheduledDiagnostics", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    if ( hKey )
    {
      v5 = RegQueryValueExW(hKey, L"EnabledExecution", 0, &Type, (LPBYTE)&Data, &cbData);
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( v3 >= 0 )
      {
        if ( Type == 4 && cbData == 4 )
        {
          *a1 = Data;
          goto LABEL_16;
        }
        v3 = -2147023267;
        v4 = 297;
      }
      else
      {
        v4 = 293;
      }
    }
    else
    {
      v3 = -2147467261;
      v4 = 285;
    }
  }
  else
  {
    v4 = 284;
  }
  SdpDebugTrace(1u, L"SchdpGetAdminSetting", v4, v3);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800072cc  push    rbp
0x1800072ce  push    rbx
0x1800072cf  push    rdi
0x1800072d0  mov     rbp, rsp
0x1800072d3  sub     rsp, 40h
0x1800072d7  and     [rbp+hKey], 0
0x1800072dc  lea     rax, [rbp+hKey]
0x1800072e0  and     [rbp+Data], 0
0x1800072e4  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\Scheduled"...
0x1800072eb  and     [rbp+Type], 0
0x1800072ef  mov     rdi, rcx
0x1800072f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800072f9  mov     [rsp+40h+phkResult], rax; phkResult
0x1800072fe  mov     r9d, 20019h; samDesired
0x180007304  mov     [rbp+cbData], 4
0x18000730b  xor     r8d, r8d; ulOptions
0x18000730e  call    cs:__imp_RegOpenKeyExW
0x180007315  nop     dword ptr [rax+rax+00h]
0x18000731a  mov     ebx, eax
0x18000731c  test    eax, eax
0x18000731e  jle     short loc_180007329
0x180007320  movzx   ebx, ax
0x180007323  or      ebx, 80070000h
0x180007329  test    ebx, ebx
0x18000732b  jns     short loc_180007335
0x18000732d  mov     r8d, 11Ch
0x180007333  jmp     short loc_1800073B0
0x180007335  mov     rcx, [rbp+hKey]; hKey
0x180007339  test    rcx, rcx
0x18000733c  jnz     short loc_18000734B
0x18000733e  mov     ebx, 80004003h
0x180007343  mov     r8d, 11Dh
0x180007349  jmp     short loc_1800073B0
0x18000734b  lea     rax, [rbp+cbData]
0x18000734f  xor     r8d, r8d; lpReserved
0x180007352  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180007357  lea     r9, [rbp+Type]; lpType
0x18000735b  lea     rax, [rbp+Data]
0x18000735f  lea     rdx, ValueName; "EnabledExecution"
0x180007366  mov     [rsp+40h+phkResult], rax; lpData
0x18000736b  call    cs:__imp_RegQueryValueExW
0x180007372  nop     dword ptr [rax+rax+00h]
0x180007377  mov     ebx, eax
0x180007379  test    eax, eax
0x18000737b  jle     short loc_180007386
0x18000737d  movzx   ebx, ax
0x180007380  or      ebx, 80070000h
0x180007386  test    ebx, ebx
0x180007388  jns     short loc_180007392
0x18000738a  mov     r8d, 125h
0x180007390  jmp     short loc_1800073B0
0x180007392  cmp     [rbp+Type], 4
0x180007396  jnz     short loc_1800073A5
0x180007398  cmp     [rbp+cbData], 4
0x18000739c  jnz     short loc_1800073A5
0x18000739e  mov     eax, [rbp+Data]
0x1800073a1  mov     [rdi], eax
0x1800073a3  jmp     short loc_1800073C4
0x1800073a5  mov     ebx, 8007065Dh
0x1800073aa  mov     r8d, 129h; int
0x1800073b0  mov     r9d, ebx; int
0x1800073b3  lea     rdx, aSchdpgetadmins; "SchdpGetAdminSetting"
0x1800073ba  mov     ecx, 1; Level
0x1800073bf  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800073c4  mov     rcx, [rbp+hKey]; hKey
0x1800073c8  test    rcx, rcx
0x1800073cb  jz      short loc_1800073D9
0x1800073cd  call    cs:__imp_RegCloseKey
0x1800073d4  nop     dword ptr [rax+rax+00h]
0x1800073d9  mov     eax, ebx
0x1800073db  add     rsp, 40h
0x1800073df  pop     rdi
0x1800073e0  pop     rbx
0x1800073e1  pop     rbp
0x1800073e2  retn
```
