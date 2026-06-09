# CProtocolHandler::ConfigureRegValue(void)

- ea: `0x18000cf94`
- end: `0x18000d207`
- name: `?ConfigureRegValue@CProtocolHandler@@AEAAKXZ`
- size: `627`
- prototype: `unsigned int __fastcall(CProtocolHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ce14`

## callees

- `0x18000cf94`
- `0x180024550`
- `0x180024f38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cfe4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cfe4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d1ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d1ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d06c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d165`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d06c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d165`

## string_xrefs

- `0x18000cfdd`: `System\CurrentControlSet\Services\LanmanWorkstation\Parameters`

## pseudocode

```c
__int64 __fastcall CProtocolHandler::ConfigureRegValue(CProtocolHandler *this)
{
  unsigned int v2; // eax
  unsigned int v3; // esi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\LanmanWorkstation\\Parameters",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      v5 = 15;
LABEL_6:
      WPP_SF_d(v4[2], v5, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v2);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  cbData = 4;
  v6 = RegQueryValueExW(hKey, L"WitnessKeepAliveInSeconds", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v6 )
  {
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 16, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v6);
    }
LABEL_22:
    *((_DWORD *)this + 1) = 120;
    goto LABEL_24;
  }
  if ( Type != 4 )
  {
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids,
        (unsigned int)L"WitnessKeepAliveInSeconds",
        Type);
    }
    goto LABEL_22;
  }
  if ( Data < 0xA )
  {
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids,
        (unsigned int)L"WitnessKeepAliveInSeconds",
        4);
    }
    goto LABEL_22;
  }
  *((_DWORD *)this + 1) = Data;
LABEL_24:
  cbData = 4;
  v2 = RegQueryValueExW(hKey, L"WitnessFlags", 0, &Type, (LPBYTE)&Data, &cbData);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      v5 = 19;
      goto LABEL_6;
    }
  }
  else if ( Type == 4 )
  {
    *(_DWORD *)this = Data;
  }
  else if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
         && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
      20,
      (unsigned int)&WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids,
      (unsigned int)L"WitnessFlags",
      Type);
  }
LABEL_35:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18000cf94  mov     [rsp-18h+arg_0], rsi
0x18000cf99  push    rbp
0x18000cf9a  push    rdi
0x18000cf9b  push    r15
0x18000cf9d  mov     rbp, rsp
0x18000cfa0  sub     rsp, 40h
0x18000cfa4  mov     r15, rcx
0x18000cfa7  mov     [rbp+hKey], 0
0x18000cfaf  lea     rax, [rbp+hKey]
0x18000cfb3  mov     [rbp+Type], 0
0x18000cfba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000cfc1  mov     [rsp+40h+phkResult], rax; phkResult
0x18000cfc6  mov     r9d, 20019h; samDesired
0x18000cfcc  mov     [rbp+Data], 0
0x18000cfd3  xor     r8d, r8d; ulOptions
0x18000cfd6  mov     [rbp+cbData], 4
0x18000cfdd  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\La"...
0x18000cfe4  call    cs:__imp_RegOpenKeyExW
0x18000cfeb  nop     dword ptr [rax+rax+00h]
0x18000cff0  mov     esi, eax
0x18000cff2  test    eax, eax
0x18000cff4  jz      short loc_18000D03E
0x18000cff6  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000cffd  lea     rdi, WPP_witness_GLOBAL_Control
0x18000d004  cmp     rcx, rdi
0x18000d007  jz      loc_18000D1E1
0x18000d00d  test    byte ptr [rcx+1Ch], 1
0x18000d011  jz      loc_18000D1E1
0x18000d017  cmp     byte ptr [rcx+19h], 1
0x18000d01b  jb      loc_18000D1E1
0x18000d021  mov     edx, 0Fh
0x18000d026  mov     rcx, [rcx+10h]
0x18000d02a  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18000d031  mov     r9d, eax
0x18000d034  call    WPP_SF_d
0x18000d039  jmp     loc_18000D1E1
0x18000d03e  mov     rcx, [rbp+hKey]; hKey
0x18000d042  lea     rax, [rbp+cbData]
0x18000d046  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000d04b  lea     rsi, aWitnesskeepali; "WitnessKeepAliveInSeconds"
0x18000d052  lea     rax, [rbp+Data]
0x18000d056  mov     [rbp+cbData], 4
0x18000d05d  lea     r9, [rbp+Type]; lpType
0x18000d061  mov     [rsp+40h+phkResult], rax; lpData
0x18000d066  xor     r8d, r8d; lpReserved
0x18000d069  mov     rdx, rsi; lpValueName
0x18000d06c  call    cs:__imp_RegQueryValueExW
0x18000d073  nop     dword ptr [rax+rax+00h]
0x18000d078  lea     rdi, WPP_witness_GLOBAL_Control
0x18000d07f  test    eax, eax
0x18000d081  jz      short loc_18000D0C1
0x18000d083  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d08a  cmp     rcx, rdi
0x18000d08d  jz      loc_18000D12C
0x18000d093  test    byte ptr [rcx+1Ch], 1
0x18000d097  jz      loc_18000D12C
0x18000d09d  cmp     byte ptr [rcx+19h], 1
0x18000d0a1  jb      loc_18000D12C
0x18000d0a7  mov     rcx, [rcx+10h]
0x18000d0ab  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18000d0b2  mov     edx, 10h
0x18000d0b7  mov     r9d, eax
0x18000d0ba  call    WPP_SF_d
0x18000d0bf  jmp     short loc_18000D12C
0x18000d0c1  mov     eax, [rbp+Type]
0x18000d0c4  cmp     eax, 4
0x18000d0c7  jz      short loc_18000D0EC
0x18000d0c9  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d0d0  cmp     rcx, rdi
0x18000d0d3  jz      short loc_18000D12C
0x18000d0d5  test    byte ptr [rcx+1Ch], 1
0x18000d0d9  jz      short loc_18000D12C
0x18000d0db  cmp     byte ptr [rcx+19h], 1
0x18000d0df  jb      short loc_18000D12C
0x18000d0e1  mov     edx, 11h
0x18000d0e6  mov     dword ptr [rsp+40h+phkResult], eax
0x18000d0ea  jmp     short loc_18000D119
0x18000d0ec  mov     eax, [rbp+Data]
0x18000d0ef  cmp     eax, 0Ah
0x18000d0f2  jnb     short loc_18000D136
0x18000d0f4  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d0fb  cmp     rcx, rdi
0x18000d0fe  jz      short loc_18000D12C
0x18000d100  test    byte ptr [rcx+1Ch], 1
0x18000d104  jz      short loc_18000D12C
0x18000d106  cmp     byte ptr [rcx+19h], 1
0x18000d10a  jb      short loc_18000D12C
0x18000d10c  mov     edx, 12h
0x18000d111  mov     dword ptr [rsp+40h+phkResult], 4
0x18000d119  mov     rcx, [rcx+10h]
0x18000d11d  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18000d124  mov     r9, rsi
0x18000d127  call    WPP_SF_Sd
0x18000d12c  mov     dword ptr [r15+4], 78h ; 'x'
0x18000d134  jmp     short loc_18000D13A
0x18000d136  mov     [r15+4], eax
0x18000d13a  mov     rcx, [rbp+hKey]; hKey
0x18000d13e  lea     rax, [rbp+cbData]
0x18000d142  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000d147  lea     r9, [rbp+Type]; lpType
0x18000d14b  lea     rax, [rbp+Data]
0x18000d14f  mov     [rbp+cbData], 4
0x18000d156  xor     r8d, r8d; lpReserved
0x18000d159  mov     [rsp+40h+phkResult], rax; lpData
0x18000d15e  lea     rdx, aWitnessflags; "WitnessFlags"
0x18000d165  call    cs:__imp_RegQueryValueExW
0x18000d16c  nop     dword ptr [rax+rax+00h]
0x18000d171  mov     esi, eax
0x18000d173  test    eax, eax
0x18000d175  jz      short loc_18000D199
0x18000d177  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d17e  cmp     rcx, rdi
0x18000d181  jz      short loc_18000D1E1
0x18000d183  test    byte ptr [rcx+1Ch], 1
0x18000d187  jz      short loc_18000D1E1
0x18000d189  cmp     byte ptr [rcx+19h], 1
0x18000d18d  jb      short loc_18000D1E1
0x18000d18f  mov     edx, 13h
0x18000d194  jmp     loc_18000D026
0x18000d199  mov     eax, [rbp+Type]
0x18000d19c  cmp     eax, 4
0x18000d19f  jz      short loc_18000D1DB
0x18000d1a1  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d1a8  cmp     rcx, rdi
0x18000d1ab  jz      short loc_18000D1E1
0x18000d1ad  test    byte ptr [rcx+1Ch], 1
0x18000d1b1  jz      short loc_18000D1E1
0x18000d1b3  cmp     byte ptr [rcx+19h], 1
0x18000d1b7  jb      short loc_18000D1E1
0x18000d1b9  mov     rcx, [rcx+10h]
0x18000d1bd  lea     r9, aWitnessflags; "WitnessFlags"
0x18000d1c4  mov     edx, 14h
0x18000d1c9  mov     dword ptr [rsp+40h+phkResult], eax
0x18000d1cd  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18000d1d4  call    WPP_SF_Sd
0x18000d1d9  jmp     short loc_18000D1E1
0x18000d1db  mov     eax, [rbp+Data]
0x18000d1de  mov     [r15], eax
0x18000d1e1  mov     rcx, [rbp+hKey]; hKey
0x18000d1e5  test    rcx, rcx
0x18000d1e8  jz      short loc_18000D1F6
0x18000d1ea  call    cs:__imp_RegCloseKey
0x18000d1f1  nop     dword ptr [rax+rax+00h]
0x18000d1f6  mov     eax, esi
0x18000d1f8  mov     rsi, [rsp+40h+arg_0]
0x18000d1fd  add     rsp, 40h
0x18000d201  pop     r15
0x18000d203  pop     rdi
0x18000d204  pop     rbp
0x18000d205  retn
```
