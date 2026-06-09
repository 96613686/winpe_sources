# CanUseMachineKeySet(void)

- ea: `0x180014a88`
- end: `0x180014ba9`
- name: `?CanUseMachineKeySet@@YAHXZ`
- size: `289`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800151b8`

## callees

- `0x180010570`
- `0x180014a88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014b2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014b2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014b0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014b0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014acd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014acd`

## pseudocode

```c
__int64 CanUseMachineKeySet(void)
{
  _QWORD *v0; // rcx
  __int64 v1; // rdx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( dword_18005F794 == -1 )
  {
    hKey = 0;
    dword_18005F794 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, &hKey) )
    {
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"UseMachineKeySet", 0, 0, (LPBYTE)&Data, &cbData) )
        dword_18005F794 = Data;
      RegCloseKey(hKey);
    }
  }
  if ( dword_18005F794 )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v1 = 12;
LABEL_15:
      WPP_SF_(v0[2], v1, WPP_70ac14349bd73daa77fbd210190c47b4_Traceguids);
    }
  }
  else
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v1 = 13;
      goto LABEL_15;
    }
  }
  return (unsigned int)dword_18005F794;
}

```

## disassembly

```asm
0x180014a88  sub     rsp, 38h
0x180014a8c  cmp     cs:dword_18005F794, 0FFFFFFFFh
0x180014a93  jnz     loc_180014B3A
0x180014a99  lea     rax, [rsp+38h+hKey]
0x180014a9e  mov     [rsp+38h+hKey], 0
0x180014aa7  mov     r9d, 20019h; samDesired
0x180014aad  mov     [rsp+38h+phkResult], rax; phkResult
0x180014ab2  xor     r8d, r8d; ulOptions
0x180014ab5  mov     cs:dword_18005F794, 0
0x180014abf  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Internet Explorer"...
0x180014ac6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014acd  call    cs:__imp_RegOpenKeyExW
0x180014ad4  nop     dword ptr [rax+rax+00h]
0x180014ad9  test    eax, eax
0x180014adb  jnz     short loc_180014B3A
0x180014add  mov     rcx, [rsp+38h+hKey]; hKey
0x180014ae2  lea     rdx, aUsemachinekeys; "UseMachineKeySet"
0x180014ae9  mov     [rsp+38h+Data], eax
0x180014aed  xor     r9d, r9d; lpType
0x180014af0  lea     rax, [rsp+38h+cbData]
0x180014af5  mov     [rsp+38h+cbData], 4
0x180014afd  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180014b02  xor     r8d, r8d; lpReserved
0x180014b05  lea     rax, [rsp+38h+Data]
0x180014b0a  mov     [rsp+38h+phkResult], rax; lpData
0x180014b0f  call    cs:__imp_RegQueryValueExW
0x180014b16  nop     dword ptr [rax+rax+00h]
0x180014b1b  test    eax, eax
0x180014b1d  jnz     short loc_180014B29
0x180014b1f  mov     eax, [rsp+38h+Data]
0x180014b23  mov     cs:dword_18005F794, eax
0x180014b29  mov     rcx, [rsp+38h+hKey]; hKey
0x180014b2e  call    cs:__imp_RegCloseKey
0x180014b35  nop     dword ptr [rax+rax+00h]
0x180014b3a  cmp     cs:dword_18005F794, 0
0x180014b41  jz      short loc_180014B69
0x180014b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b4a  lea     rax, WPP_GLOBAL_Control
0x180014b51  cmp     rcx, rax
0x180014b54  jz      short loc_180014B9D
0x180014b56  test    byte ptr [rcx+1Ch], 2
0x180014b5a  jz      short loc_180014B9D
0x180014b5c  cmp     byte ptr [rcx+19h], 4
0x180014b60  jb      short loc_180014B9D
0x180014b62  mov     edx, 0Ch
0x180014b67  jmp     short loc_180014B8D
0x180014b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b70  lea     rax, WPP_GLOBAL_Control
0x180014b77  cmp     rcx, rax
0x180014b7a  jz      short loc_180014B9D
0x180014b7c  test    byte ptr [rcx+1Ch], 2
0x180014b80  jz      short loc_180014B9D
0x180014b82  cmp     byte ptr [rcx+19h], 4
0x180014b86  jb      short loc_180014B9D
0x180014b88  mov     edx, 0Dh
0x180014b8d  mov     rcx, [rcx+10h]
0x180014b91  lea     r8, WPP_70ac14349bd73daa77fbd210190c47b4_Traceguids
0x180014b98  call    WPP_SF_
0x180014b9d  mov     eax, cs:dword_18005F794
0x180014ba3  add     rsp, 38h
0x180014ba7  retn
```
