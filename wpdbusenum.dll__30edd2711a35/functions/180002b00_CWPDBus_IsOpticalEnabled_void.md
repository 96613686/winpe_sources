# CWPDBus::IsOpticalEnabled(void)

- ea: `0x180002b00`
- end: `0x180002c5e`
- name: `?IsOpticalEnabled@CWPDBus@@KAHXZ`
- size: `350`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800018c0`

## callees

- `0x180002b00`
- `0x180007f28`
- `0x18000e53c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002bd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002bd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002b42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002b42`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002b7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002b7f`

## string_xrefs

- `0x180002b2d`: `System\CurrentControlSet\Services\WpdBusEnum`

## pseudocode

```c
__int64 CWPDBus::IsOpticalEnabled(void)
{
  unsigned int v0; // ebx
  int v1; // eax
  int v2; // eax
  bool v3; // sf
  CPnPNotification *v4; // rcx
  __int64 v5; // rcx
  const wchar_t *v6; // r9
  int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  cbData = 4;
  hKey = 0;
  Type = 0;
  Data = 0;
  v0 = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\WpdBusEnum", 0, 0x20019u, &hKey);
  if ( !v1 )
  {
    v2 = RegQueryValueExW(hKey, L"EnableCDROM", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v2 )
    {
      if ( v2 != 2 )
      {
        v3 = v2 < 0;
        if ( v2 > 0 )
        {
          v2 = (unsigned __int16)v2 | 0x80070000;
          v3 = v2 < 0;
        }
        if ( v3
          && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            &WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids,
            (unsigned int)v2);
        }
      }
    }
    else
    {
      LOBYTE(v0) = Data != 0;
    }
    RegCloseKey(hKey);
    goto LABEL_17;
  }
  if ( v1 > 0 )
    v1 = (unsigned __int16)v1 | 0x80070000;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_18:
      if ( v4 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x100) != 0 )
      {
        v5 = *((_QWORD *)v4 + 2);
        v6 = L"Enabled";
        if ( !v0 )
          v6 = L"Disabled";
        WPP_SF_S(v5, 16, &WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids, v6);
      }
      return v0;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids,
      (unsigned int)v1);
LABEL_17:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  return v0;
}

```

## disassembly

```asm
0x180002b00  push    rbx
0x180002b02  push    rsi
0x180002b03  push    rdi
0x180002b04  sub     rsp, 30h
0x180002b08  xor     edi, edi
0x180002b0a  mov     [rsp+48h+cbData], 4
0x180002b12  lea     rax, [rsp+48h+hKey]
0x180002b17  mov     [rsp+48h+hKey], rdi
0x180002b1c  mov     r9d, 20019h; samDesired
0x180002b22  mov     [rsp+48h+Type], edi
0x180002b26  xor     r8d, r8d; ulOptions
0x180002b29  mov     [rsp+48h+Data], edi
0x180002b2d  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Wp"...
0x180002b34  mov     [rsp+48h+phkResult], rax; phkResult
0x180002b39  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002b40  mov     ebx, edi
0x180002b42  call    cs:__imp_RegOpenKeyExW
0x180002b48  lea     rsi, WPP_GLOBAL_Control
0x180002b4f  test    eax, eax
0x180002b51  jnz     loc_180002BDE
0x180002b57  mov     rcx, [rsp+48h+hKey]; hKey
0x180002b5c  lea     rax, [rsp+48h+cbData]
0x180002b61  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180002b66  lea     r9, [rsp+48h+Type]; lpType
0x180002b6b  lea     rax, [rsp+48h+Data]
0x180002b70  xor     r8d, r8d; lpReserved
0x180002b73  lea     rdx, ValueName; "EnableCDROM"
0x180002b7a  mov     [rsp+48h+phkResult], rax; lpData
0x180002b7f  call    cs:__imp_RegQueryValueExW
0x180002b85  test    eax, eax
0x180002b87  jnz     short loc_180002B92
0x180002b89  cmp     [rsp+48h+Data], ebx
0x180002b8d  setnz   bl
0x180002b90  jmp     short loc_180002BD1
0x180002b92  cmp     eax, 2
0x180002b95  jz      short loc_180002BD1
0x180002b97  test    eax, eax
0x180002b99  jle     short loc_180002BA5
0x180002b9b  movzx   eax, ax
0x180002b9e  or      eax, 80070000h
0x180002ba3  test    eax, eax
0x180002ba5  jns     short loc_180002BD1
0x180002ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bae  cmp     rcx, rsi
0x180002bb1  jz      short loc_180002BD1
0x180002bb3  test    byte ptr [rcx+1Ch], 2
0x180002bb7  jz      short loc_180002BD1
0x180002bb9  mov     rcx, [rcx+10h]
0x180002bbd  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x180002bc4  mov     edx, 0Eh
0x180002bc9  mov     r9d, eax
0x180002bcc  call    WPP_SF_d
0x180002bd1  mov     rcx, [rsp+48h+hKey]; hKey
0x180002bd6  call    cs:__imp_RegCloseKey
0x180002bdc  jmp     short loc_180002C16
0x180002bde  jle     short loc_180002BE8
0x180002be0  movzx   eax, ax
0x180002be3  or      eax, 80070000h
0x180002be8  test    eax, eax
0x180002bea  jns     short loc_180002C16
0x180002bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bf3  cmp     rcx, rsi
0x180002bf6  jz      short loc_180002C54
0x180002bf8  test    byte ptr [rcx+1Ch], 2
0x180002bfc  jz      short loc_180002C1D
0x180002bfe  mov     rcx, [rcx+10h]
0x180002c02  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x180002c09  mov     edx, 0Fh
0x180002c0e  mov     r9d, eax
0x180002c11  call    WPP_SF_d
0x180002c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c1d  cmp     rcx, rsi
0x180002c20  jz      short loc_180002C54
0x180002c22  test    dword ptr [rcx+1Ch], 100h
0x180002c29  jz      short loc_180002C54
0x180002c2b  mov     rcx, [rcx+10h]
0x180002c2f  lea     rax, aDisabled; "Disabled"
0x180002c36  test    ebx, ebx
0x180002c38  lea     r9, aEnabled; "Enabled"
0x180002c3f  mov     edx, 10h
0x180002c44  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x180002c4b  cmovz   r9, rax
0x180002c4f  call    WPP_SF_S
0x180002c54  mov     eax, ebx
0x180002c56  add     rsp, 30h
0x180002c5a  pop     rdi
0x180002c5b  pop     rsi
0x180002c5c  pop     rbx
0x180002c5d  retn
```
