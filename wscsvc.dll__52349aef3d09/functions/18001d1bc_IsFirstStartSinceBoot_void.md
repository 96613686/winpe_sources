# IsFirstStartSinceBoot(void)

- ea: `0x18001d1bc`
- end: `0x18001d2e4`
- name: `?IsFirstStartSinceBoot@@YAHXZ`
- size: `296`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d2f0`

## callees

- `0x180008e48`
- `0x18001d1bc`
- `0x1800202e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d1f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d1f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d294`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d2d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d2d1`

## string_xrefs

- `0x18001d1e0`: `SOFTWARE\Microsoft\Security Center\Svc\Vol`
- `0x18001d26f`: `SOFTWARE\Microsoft\Security Center\Svc\Vol`

## pseudocode

```c
__int64 IsFirstStartSinceBoot(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  v0 = 1;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Security Center\\Svc\\Vol", 0, 1u, &hKey) )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
    }
    v1 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Security Center\\Svc\\Vol",
           0,
           0,
           1u,
           1u,
           0,
           &hKey,
           0);
    if ( v1
      && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, v1);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
    }
    v0 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18001d1bc  mov     r11, rsp
0x18001d1bf  mov     [r11+10h], rbx
0x18001d1c3  push    rdi
0x18001d1c4  sub     rsp, 50h
0x18001d1c8  lea     rax, [r11+8]
0x18001d1cc  mov     qword ptr [r11+8], 0
0x18001d1d4  mov     ebx, 1
0x18001d1d9  mov     [r11-38h], rax
0x18001d1dd  mov     r9d, ebx; samDesired
0x18001d1e0  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Security Center\\S"...
0x18001d1e7  xor     r8d, r8d; ulOptions
0x18001d1ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d1f1  call    cs:__imp_RegOpenKeyExW
0x18001d1f7  test    eax, eax
0x18001d1f9  jnz     short loc_18001D22E
0x18001d1fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d202  lea     rdi, WPP_GLOBAL_Control
0x18001d209  cmp     rcx, rdi
0x18001d20c  jz      short loc_18001D227
0x18001d20e  test    byte ptr [rcx+1Ch], 4
0x18001d212  jz      short loc_18001D227
0x18001d214  mov     rcx, [rcx+10h]
0x18001d218  lea     edx, [rbx+10h]
0x18001d21b  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x18001d222  call    WPP_SF_
0x18001d227  xor     ebx, ebx
0x18001d229  jmp     loc_18001D2C7
0x18001d22e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d235  lea     rdi, WPP_GLOBAL_Control
0x18001d23c  cmp     rcx, rdi
0x18001d23f  jz      short loc_18001D25C
0x18001d241  test    byte ptr [rcx+1Ch], 4
0x18001d245  jz      short loc_18001D25C
0x18001d247  mov     rcx, [rcx+10h]
0x18001d24b  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x18001d252  mov     edx, 12h
0x18001d257  call    WPP_SF_
0x18001d25c  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18001d265  lea     rax, [rsp+58h+hKey]
0x18001d26a  mov     [rsp+58h+phkResult], rax; phkResult
0x18001d26f  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Security Center\\S"...
0x18001d276  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001d27f  xor     r9d, r9d; lpClass
0x18001d282  mov     [rsp+58h+samDesired], ebx; samDesired
0x18001d286  xor     r8d, r8d; Reserved
0x18001d289  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d290  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x18001d294  call    cs:__imp_RegCreateKeyExW
0x18001d29a  test    eax, eax
0x18001d29c  jz      short loc_18001D2C7
0x18001d29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2a5  cmp     rcx, rdi
0x18001d2a8  jz      short loc_18001D2C7
0x18001d2aa  test    [rcx+1Ch], bl
0x18001d2ad  jz      short loc_18001D2C7
0x18001d2af  mov     rcx, [rcx+10h]
0x18001d2b3  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x18001d2ba  mov     edx, 13h
0x18001d2bf  mov     r9d, eax
0x18001d2c2  call    WPP_SF_d
0x18001d2c7  mov     rcx, [rsp+58h+hKey]; hKey
0x18001d2cc  test    rcx, rcx
0x18001d2cf  jz      short loc_18001D2D7
0x18001d2d1  call    cs:__imp_RegCloseKey
0x18001d2d7  mov     eax, ebx
0x18001d2d9  mov     rbx, [rsp+58h+arg_8]
0x18001d2de  add     rsp, 50h
0x18001d2e2  pop     rdi
0x18001d2e3  retn
```
