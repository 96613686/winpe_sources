# CUser::RegSetDWORD(ushort const *,ushort const *,ulong)

- ea: `0x1400828e4`
- end: `0x1400829b1`
- name: `?RegSetDWORD@CUser@@QEAAKPEBG0K@Z`
- size: `205`
- prototype: `unsigned int __fastcall(CUser *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400176f8`

## callees

- `0x1400057f4`
- `0x1400828e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140082951`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140082951`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14008291f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14008291f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400829a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009fe7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400829a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009fe7a`

## pseudocode

```c
__int64 __fastcall CUser::RegSetDWORD(HKEY *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v3; // ebx
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v6; // [rsp+38h] [rbp-10h]
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  *(_DWORD *)Data = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(this[29], L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 0x20006u, &hKey);
  v6 = v3;
  if ( !v3 )
  {
    v3 = RegSetValueExW(hKey, L"FirstLogon", 0, 4u, Data, 4u);
    v6 = v3;
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v3);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x1400828e4  mov     rax, rsp
0x1400828e7  mov     [rax+18h], r8
0x1400828eb  push    rbx
0x1400828ec  sub     rsp, 40h
0x1400828f0  mov     dword ptr [rax-18h], 0
0x1400828f7  mov     qword ptr [rax+18h], 0
0x1400828ff  lea     rax, [rax+18h]
0x140082903  mov     [rsp+48h+phkResult], rax; phkResult
0x140082908  mov     r9d, 20006h; samDesired
0x14008290e  xor     r8d, r8d; ulOptions
0x140082911  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x140082918  mov     rcx, [rcx+0E8h]; hKey
0x14008291f  call    cs:__imp_RegOpenKeyExW
0x140082925  mov     ebx, eax
0x140082927  mov     [rsp+48h+var_10], eax
0x14008292b  test    eax, eax
0x14008292d  jnz     short loc_140082999
0x14008292f  lea     r9d, [rax+4]; dwType
0x140082933  mov     [rsp+48h+cbData], r9d; cbData
0x140082938  lea     rax, [rsp+48h+Data]
0x14008293d  mov     [rsp+48h+phkResult], rax; lpData
0x140082942  xor     r8d, r8d; Reserved
0x140082945  lea     rdx, aFirstlogon; "FirstLogon"
0x14008294c  mov     rcx, [rsp+48h+hKey]; hKey
0x140082951  call    cs:__imp_RegSetValueExW
0x140082957  mov     ebx, eax
0x140082959  mov     [rsp+48h+var_10], eax
0x14008295d  test    eax, eax
0x14008295f  jz      short loc_140082999
0x140082961  lea     rax, WPP_GLOBAL_Control
0x140082968  mov     rcx, cs:WPP_GLOBAL_Control
0x14008296f  cmp     rcx, rax
0x140082972  jz      short loc_140082999
0x140082974  test    byte ptr [rcx+1Ch], 20h
0x140082978  jz      short loc_140082999
0x14008297a  cmp     byte ptr [rcx+19h], 2
0x14008297e  jb      short loc_140082999
0x140082980  mov     edx, 45h ; 'E'
0x140082985  mov     r9d, ebx
0x140082988  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14008298f  mov     rcx, [rcx+10h]
0x140082993  call    WPP_SF_d
0x140082998  nop
0x140082999  mov     rcx, [rsp+48h+hKey]; hKey
0x14008299e  test    rcx, rcx
0x1400829a1  jz      short loc_1400829A9
0x1400829a3  call    cs:__imp_RegCloseKey
0x1400829a9  mov     eax, ebx
0x1400829ab  add     rsp, 40h
0x1400829af  pop     rbx
0x1400829b0  retn
0x14009fe68  push    rbp
0x14009fe6a  sub     rsp, 30h
0x14009fe6e  mov     rbp, rdx
0x14009fe71  mov     rcx, [rbp+60h]; hKey
0x14009fe75  test    rcx, rcx
0x14009fe78  jz      short loc_14009FE81
0x14009fe7a  call    cs:__imp_RegCloseKey
0x14009fe80  nop
0x14009fe81  add     rsp, 30h
0x14009fe85  pop     rbp
0x14009fe86  retn
```
