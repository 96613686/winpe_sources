# CanUseMachineKeySet(void)

- ea: `0x180013e30`
- end: `0x180013f3e`
- name: `?CanUseMachineKeySet@@YAHXZ`
- size: `270`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001452c`

## callees

- `0x18000fbb8`
- `0x180013e30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013eca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013eca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013eb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013eb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013e75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013e75`

## pseudocode

```c
__int64 CanUseMachineKeySet(void)
{
  _QWORD *v0; // rcx
  __int64 v1; // rdx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( dword_18005D794 == -1 )
  {
    hKey = 0;
    dword_18005D794 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, &hKey) )
    {
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"UseMachineKeySet", 0, 0, (LPBYTE)&Data, &cbData) )
        dword_18005D794 = Data;
      RegCloseKey(hKey);
    }
  }
  if ( dword_18005D794 )
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
  return (unsigned int)dword_18005D794;
}

```

## disassembly

```asm
0x180013e30  sub     rsp, 38h
0x180013e34  cmp     cs:dword_18005D794, 0FFFFFFFFh
0x180013e3b  jnz     loc_180013ED0
0x180013e41  lea     rax, [rsp+38h+hKey]
0x180013e46  mov     [rsp+38h+hKey], 0
0x180013e4f  mov     r9d, 20019h; samDesired
0x180013e55  mov     [rsp+38h+phkResult], rax; phkResult
0x180013e5a  xor     r8d, r8d; ulOptions
0x180013e5d  mov     cs:dword_18005D794, 0
0x180013e67  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Internet Explorer"...
0x180013e6e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013e75  call    cs:__imp_RegOpenKeyExW
0x180013e7b  test    eax, eax
0x180013e7d  jnz     short loc_180013ED0
0x180013e7f  mov     rcx, [rsp+38h+hKey]; hKey
0x180013e84  lea     rdx, aUsemachinekeys; "UseMachineKeySet"
0x180013e8b  mov     [rsp+38h+Data], eax
0x180013e8f  xor     r9d, r9d; lpType
0x180013e92  lea     rax, [rsp+38h+cbData]
0x180013e97  mov     [rsp+38h+cbData], 4
0x180013e9f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180013ea4  xor     r8d, r8d; lpReserved
0x180013ea7  lea     rax, [rsp+38h+Data]
0x180013eac  mov     [rsp+38h+phkResult], rax; lpData
0x180013eb1  call    cs:__imp_RegQueryValueExW
0x180013eb7  test    eax, eax
0x180013eb9  jnz     short loc_180013EC5
0x180013ebb  mov     eax, [rsp+38h+Data]
0x180013ebf  mov     cs:dword_18005D794, eax
0x180013ec5  mov     rcx, [rsp+38h+hKey]; hKey
0x180013eca  call    cs:__imp_RegCloseKey
0x180013ed0  cmp     cs:dword_18005D794, 0
0x180013ed7  jz      short loc_180013EFF
0x180013ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ee0  lea     rax, WPP_GLOBAL_Control
0x180013ee7  cmp     rcx, rax
0x180013eea  jz      short loc_180013F33
0x180013eec  test    byte ptr [rcx+1Ch], 2
0x180013ef0  jz      short loc_180013F33
0x180013ef2  cmp     byte ptr [rcx+19h], 4
0x180013ef6  jb      short loc_180013F33
0x180013ef8  mov     edx, 0Ch
0x180013efd  jmp     short loc_180013F23
0x180013eff  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f06  lea     rax, WPP_GLOBAL_Control
0x180013f0d  cmp     rcx, rax
0x180013f10  jz      short loc_180013F33
0x180013f12  test    byte ptr [rcx+1Ch], 2
0x180013f16  jz      short loc_180013F33
0x180013f18  cmp     byte ptr [rcx+19h], 4
0x180013f1c  jb      short loc_180013F33
0x180013f1e  mov     edx, 0Dh
0x180013f23  mov     rcx, [rcx+10h]
0x180013f27  lea     r8, WPP_70ac14349bd73daa77fbd210190c47b4_Traceguids
0x180013f2e  call    WPP_SF_
0x180013f33  mov     eax, cs:dword_18005D794
0x180013f39  add     rsp, 38h
0x180013f3d  retn
```
