# IsActionArgCheckingDisabled(void)

- ea: `0x1800096b0`
- end: `0x180009794`
- name: `?IsActionArgCheckingDisabled@@YAHXZ`
- size: `228`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008a4c`

## callees

- `0x1800024c4`
- `0x1800096b0`
- `0x18000b4c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800096f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800096f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009750`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009750`

## pseudocode

```c
__int64 IsActionArgCheckingDisabled(void)
{
  unsigned int v0; // eax
  unsigned int Dword; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( !dword_180012184 )
  {
    hKey = 0;
    dword_180012184 = 1;
    v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\UPnP Device Host", 0, 1u, &hKey);
    if ( v0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids, v0);
    }
    else
    {
      Dword = HrRegQueryDword(hKey, L"DisableArgumentChecks", (unsigned __int8 *)&dword_180012188);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids, Dword);
      RegCloseKey(hKey);
    }
  }
  return dword_180012188;
}

```

## disassembly

```asm
0x1800096b0  sub     rsp, 38h
0x1800096b4  cmp     cs:dword_180012184, 0
0x1800096bb  jnz     loc_180009789
0x1800096c1  lea     rax, [rsp+38h+hKey]
0x1800096c6  mov     [rsp+38h+hKey], 0
0x1800096cf  mov     r9d, 1; samDesired
0x1800096d5  mov     [rsp+38h+phkResult], rax; phkResult
0x1800096da  xor     r8d, r8d; ulOptions
0x1800096dd  mov     cs:dword_180012184, 1
0x1800096e7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\UPnP Device Host"
0x1800096ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800096f5  call    cs:__imp_RegOpenKeyExW
0x1800096fb  test    eax, eax
0x1800096fd  jnz     short loc_180009758
0x1800096ff  mov     rcx, [rsp+38h+hKey]; HKEY
0x180009704  lea     r8, dword_180012188; unsigned int *
0x18000970b  lea     rdx, aDisableargumen; "DisableArgumentChecks"
0x180009712  call    ?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; HrRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x180009717  mov     rcx, cs:WPP_GLOBAL_Control
0x18000971e  lea     rdx, WPP_GLOBAL_Control
0x180009725  cmp     rcx, rdx
0x180009728  jz      short loc_18000974B
0x18000972a  test    dword ptr [rcx+1Ch], 400h
0x180009731  jz      short loc_18000974B
0x180009733  mov     rcx, [rcx+10h]
0x180009737  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x18000973e  mov     edx, 0Ah
0x180009743  mov     r9d, eax
0x180009746  call    WPP_SF_d
0x18000974b  mov     rcx, [rsp+38h+hKey]; hKey
0x180009750  call    cs:__imp_RegCloseKey
0x180009756  jmp     short loc_180009789
0x180009758  mov     rcx, cs:WPP_GLOBAL_Control
0x18000975f  lea     rdx, WPP_GLOBAL_Control
0x180009766  cmp     rcx, rdx
0x180009769  jz      short loc_180009789
0x18000976b  test    byte ptr [rcx+1Ch], 1
0x18000976f  jz      short loc_180009789
0x180009771  mov     rcx, [rcx+10h]
0x180009775  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x18000977c  mov     edx, 0Bh
0x180009781  mov     r9d, eax
0x180009784  call    WPP_SF_d
0x180009789  mov     eax, cs:dword_180012188
0x18000978f  add     rsp, 38h
0x180009793  retn
```
