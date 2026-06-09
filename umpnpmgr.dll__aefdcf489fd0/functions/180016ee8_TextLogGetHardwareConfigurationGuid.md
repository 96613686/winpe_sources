# TextLogGetHardwareConfigurationGuid

- ea: `0x180016ee8`
- end: `0x180016f74`
- name: `TextLogGetHardwareConfigurationGuid`
- size: `140`
- prototype: `__int64 __fastcall(_WORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800177e0`

## callees

- `0x18000f210`
- `0x1800101d8`
- `0x180016ee8`
- `0x180017dd0`

## string_xrefs

- `0x180016f37`: `LastConfig`

## pseudocode

```c
__int64 __fastcall TextLogGetHardwareConfigurationGuid(_WORD *a1)
{
  unsigned int RootKey; // ebx
  int v4; // [rsp+48h] [rbp+10h] BYREF
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF
  HANDLE KeyHandle; // [rsp+58h] [rbp+20h] BYREF

  KeyHandle = 0;
  v4 = 0;
  RootKey = pSpUtilsHwCfgGetRootKey((__int64)a1, (HKEY *)&KeyHandle);
  if ( !RootKey )
  {
    LODWORD(v5) = 78;
    RootKey = pSetupQueryValue(KeyHandle, L"LastConfig", &v4, a1, (unsigned int *)&v5);
    if ( RootKey || v4 != 1 )
      *a1 = 0;
  }
  if ( KeyHandle )
    pSetupCloseKey((unsigned int)KeyHandle);
  return RootKey;
}

```

## disassembly

```asm
0x180016ee8  mov     rax, rsp
0x180016eeb  mov     [rax+8], rbx
0x180016eef  mov     [rax+10h], edx
0x180016ef2  push    rsi
0x180016ef3  sub     rsp, 30h
0x180016ef7  lea     rdx, [rax+20h]
0x180016efb  mov     qword ptr [rax+20h], 0
0x180016f03  mov     rsi, rcx
0x180016f06  mov     dword ptr [rax+10h], 0
0x180016f0d  call    _pSpUtilsHwCfgGetRootKey
0x180016f12  mov     ebx, eax
0x180016f14  test    eax, eax
0x180016f16  jnz     short loc_180016F55
0x180016f18  mov     rcx, [rsp+38h+KeyHandle]; KeyHandle
0x180016f1d  lea     rax, [rsp+38h+arg_10]
0x180016f22  mov     r9, rsi
0x180016f25  mov     [rsp+38h+var_18], rax; __int64
0x180016f2a  lea     r8, [rsp+38h+arg_8]
0x180016f2f  mov     dword ptr [rsp+38h+arg_10], 4Eh ; 'N'
0x180016f37  lea     rdx, aLastconfig; "LastConfig"
0x180016f3e  call    pSetupQueryValue
0x180016f43  mov     ebx, eax
0x180016f45  test    eax, eax
0x180016f47  jnz     short loc_180016F50
0x180016f49  cmp     [rsp+38h+arg_8], 1
0x180016f4e  jz      short loc_180016F55
0x180016f50  xor     eax, eax
0x180016f52  mov     [rsi], ax
0x180016f55  cmp     [rsp+38h+KeyHandle], 0
0x180016f5b  jz      short loc_180016F67
0x180016f5d  mov     rcx, [rsp+38h+KeyHandle]
0x180016f62  call    pSetupCloseKey
0x180016f67  mov     eax, ebx
0x180016f69  mov     rbx, [rsp+38h+arg_0]
0x180016f6e  add     rsp, 30h
0x180016f72  pop     rsi
0x180016f73  retn
```
