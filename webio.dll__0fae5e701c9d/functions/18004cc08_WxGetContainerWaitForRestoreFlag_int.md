# WxGetContainerWaitForRestoreFlag(int *)

- ea: `0x18004cc08`
- end: `0x18004cd96`
- name: `?WxGetContainerWaitForRestoreFlag@@YAJPEAH@Z`
- size: `398`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004cad4`

## callees

- `0x18004cc08`
- `0x1800722f0`
- `0x18009218c`
- `0x180092564`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004cced`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004cced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cd69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cd69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cc99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cc99`

## pseudocode

```c
__int64 __fastcall WxGetContainerWaitForRestoreFlag(unsigned int *a1)
{
  LSTATUS v2; // eax
  signed int v3; // r8d
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  DWORD Type; // [rsp+38h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-24h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF

  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  hKey = 0;
  if ( (BYTE3(xmmword_1800AD720) & 0x20) != 0 )
    WPP_SF_(1053, 29, WPP_dfe9b3f9ae1d397b096fb7ae1e3b82b1_Traceguids);
  if ( a1 )
    *a1 = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Containers",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
    goto LABEL_8;
  v5 = RegQueryValueExW(hKey, L"WaitForRestore", 0, &Type, Data, &cbData);
  v3 = v5;
  if ( v5 > 0 )
    v3 = (unsigned __int16)v5 | 0x80070000;
  if ( v3 < 0 )
    goto LABEL_8;
  if ( Type != 4 )
  {
    v3 = -2147023886;
LABEL_8:
    v4 = v3;
    goto LABEL_15;
  }
  v3 = 0;
  v4 = 0;
  *a1 = *(_DWORD *)Data != 0;
LABEL_15:
  if ( (BYTE3(xmmword_1800AD720) & 0x20) != 0 )
    WPP_SF_dd(1053, 30, WPP_dfe9b3f9ae1d397b096fb7ae1e3b82b1_Traceguids, *a1, v3);
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18004cc08  mov     [rsp-8+arg_8], rbx
0x18004cc0d  mov     [rsp-8+arg_10], rdi
0x18004cc12  push    rbp
0x18004cc13  mov     rbp, rsp
0x18004cc16  sub     rsp, 60h
0x18004cc1a  mov     rax, cs:__security_cookie
0x18004cc21  xor     rax, rsp
0x18004cc24  mov     [rbp+var_10], rax
0x18004cc28  mov     rdi, rcx
0x18004cc2b  mov     [rbp+var_2C], 0
0x18004cc32  mov     dword ptr [rbp+Data], 0
0x18004cc39  mov     [rbp+cbData], 4
0x18004cc40  mov     [rbp+Type], 0
0x18004cc47  mov     [rbp+hKey], 0
0x18004cc4f  test    byte ptr cs:xmmword_1800AD720+3, 20h
0x18004cc56  jz      short loc_18004CC6E
0x18004cc58  mov     edx, 1Dh
0x18004cc5d  lea     r8, WPP_dfe9b3f9ae1d397b096fb7ae1e3b82b1_Traceguids
0x18004cc64  mov     ecx, 41Dh
0x18004cc69  call    WPP_SF_
0x18004cc6e  test    rdi, rdi
0x18004cc71  jz      short loc_18004CC79
0x18004cc73  mov     dword ptr [rdi], 0
0x18004cc79  lea     rax, [rbp+hKey]
0x18004cc7d  mov     r9d, 20019h; samDesired
0x18004cc83  xor     r8d, r8d; ulOptions
0x18004cc86  mov     [rsp+60h+phkResult], rax; phkResult
0x18004cc8b  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004cc92  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004cc99  call    cs:__imp_RegOpenKeyExW
0x18004cca0  nop     dword ptr [rax+rax+00h]
0x18004cca5  mov     r8d, eax
0x18004cca8  mov     ebx, 80070000h
0x18004ccad  test    eax, eax
0x18004ccaf  jle     short loc_18004CCB8
0x18004ccb1  movzx   r8d, ax
0x18004ccb5  or      r8d, ebx
0x18004ccb8  test    r8d, r8d
0x18004ccbb  jns     short loc_18004CCC9
0x18004ccbd  mov     [rbp+var_2C], 5BDh
0x18004ccc4  mov     ebx, r8d
0x18004ccc7  jmp     short loc_18004CD39
0x18004ccc9  mov     rcx, [rbp+hKey]; hKey
0x18004cccd  lea     rax, [rbp+cbData]
0x18004ccd1  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18004ccd6  lea     r9, [rbp+Type]; lpType
0x18004ccda  lea     rax, [rbp+Data]
0x18004ccde  xor     r8d, r8d; lpReserved
0x18004cce1  lea     rdx, ValueName; "WaitForRestore"
0x18004cce8  mov     [rsp+60h+phkResult], rax; lpData
0x18004cced  call    cs:__imp_RegQueryValueExW
0x18004ccf4  nop     dword ptr [rax+rax+00h]
0x18004ccf9  mov     r8d, eax
0x18004ccfc  test    eax, eax
0x18004ccfe  jle     short loc_18004CD07
0x18004cd00  movzx   r8d, ax
0x18004cd04  or      r8d, ebx
0x18004cd07  test    r8d, r8d
0x18004cd0a  jns     short loc_18004CD15
0x18004cd0c  mov     [rbp+var_2C], 5C4h
0x18004cd13  jmp     short loc_18004CCC4
0x18004cd15  cmp     [rbp+Type], 4
0x18004cd19  jz      short loc_18004CD2A
0x18004cd1b  mov     r8d, 800703F2h
0x18004cd21  mov     [rbp+var_2C], 5C7h
0x18004cd28  jmp     short loc_18004CCC4
0x18004cd2a  xor     eax, eax
0x18004cd2c  xor     r8d, r8d
0x18004cd2f  cmp     dword ptr [rbp+Data], eax
0x18004cd32  setnz   al
0x18004cd35  xor     ebx, ebx
0x18004cd37  mov     [rdi], eax
0x18004cd39  test    byte ptr cs:xmmword_1800AD720+3, 20h
0x18004cd40  jz      short loc_18004CD60
0x18004cd42  mov     r9d, [rdi]
0x18004cd45  mov     edx, 1Eh
0x18004cd4a  mov     dword ptr [rsp+60h+phkResult], r8d
0x18004cd4f  mov     ecx, 41Dh
0x18004cd54  lea     r8, WPP_dfe9b3f9ae1d397b096fb7ae1e3b82b1_Traceguids
0x18004cd5b  call    WPP_SF_dd
0x18004cd60  mov     rcx, [rbp+hKey]; hKey
0x18004cd64  test    rcx, rcx
0x18004cd67  jz      short loc_18004CD75
0x18004cd69  call    cs:__imp_RegCloseKey
0x18004cd70  nop     dword ptr [rax+rax+00h]
0x18004cd75  mov     eax, ebx
0x18004cd77  mov     rcx, [rbp+var_10]
0x18004cd7b  xor     rcx, rsp; StackCookie
0x18004cd7e  call    __security_check_cookie
0x18004cd83  lea     r11, [rsp+60h+var_s0]
0x18004cd88  mov     rbx, [r11+18h]
0x18004cd8c  mov     rdi, [r11+20h]
0x18004cd90  mov     rsp, r11
0x18004cd93  pop     rbp
0x18004cd94  retn
```
