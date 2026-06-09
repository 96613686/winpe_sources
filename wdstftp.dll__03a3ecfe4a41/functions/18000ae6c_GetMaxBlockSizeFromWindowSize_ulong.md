# GetMaxBlockSizeFromWindowSize(ulong)

- ea: `0x18000ae6c`
- end: `0x18000af69`
- name: `?GetMaxBlockSizeFromWindowSize@@YAKK@Z`
- size: `253`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000b188`

## callees

- `0x18000ae6c`
- `0x18003b1e8`
- `0x18003ce78`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000af50`
- `ADVAPI32!RegCloseKey` at `0x18000af50`
- `ADVAPI32!RegOpenKeyExW` at `0x18000aea7`
- `ADVAPI32!RegOpenKeyExW` at `0x18000aea7`

## string_xrefs

- `0x18000ae8d`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSTFTP`
- `0x18000aed7`: `FileCacheSize`

## pseudocode

```c
__int64 __fastcall GetMaxBlockSizeFromWindowSize(unsigned int a1)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  const char *v4; // rdx
  unsigned int Value; // eax
  const char *v6; // rdx
  int v7; // ecx
  unsigned int v8; // eax
  int v9; // ecx
  unsigned int v11; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v2 = 512;
  v11 = 512;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSTFTP",
         0,
         0x20119u,
         &hKey);
  if ( !ElValidateWin32(v3, v4, "base\\eco\\wds\\transport\\lib\\tptmisc.cpp", 0x1C9u) )
  {
    Value = CRegKey::GetValue((CRegKey *)&hKey, L"FileCacheSize", 4u, &v11, 4u);
    if ( Value == 2 )
    {
      v11 = 512;
      Value = 0;
    }
    if ( !ElValidateWin32(Value, v6, "base\\eco\\wds\\transport\\lib\\tptmisc.cpp", 0x1D4u) )
    {
      v7 = v11;
      if ( v11 > 0x400 )
        v7 = 1024;
      if ( v11 < 0x200 )
        v7 = 512;
      v11 = v7 << 10;
      v8 = v7 << 11;
      if ( a1 > 1 )
        v8 /= a1;
      v9 = v8;
      if ( v8 > 0x5CA )
        v9 = 1482;
      if ( v8 < 0x200 )
        v9 = 512;
      v2 = v9;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18000ae6c  mov     rax, rsp
0x18000ae6f  mov     [rax+8], rbx
0x18000ae73  push    rdi
0x18000ae74  sub     rsp, 30h
0x18000ae78  and     qword ptr [rax+18h], 0
0x18000ae7d  lea     rax, [rax+18h]
0x18000ae81  mov     edi, ecx
0x18000ae83  mov     [rsp+38h+phkResult], rax; phkResult
0x18000ae88  mov     ebx, 200h
0x18000ae8d  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18000ae94  mov     [rax-8], ebx
0x18000ae97  mov     r9d, 20119h; samDesired
0x18000ae9d  xor     r8d, r8d; ulOptions
0x18000aea0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000aea7  call    cs:__imp_RegOpenKeyExW
0x18000aeae  nop     dword ptr [rax+rax+00h]
0x18000aeb3  mov     ecx, eax; unsigned int
0x18000aeb5  lea     r9d, [rbx-37h]; unsigned int
0x18000aeb9  lea     r8, aBaseEcoWdsTran_7; "base\\eco\\wds\\transport\\lib\\tptmisc"...
0x18000aec0  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000aec5  test    eax, eax
0x18000aec7  jnz     short loc_18000AF46
0x18000aec9  lea     r8d, [rax+4]; unsigned int
0x18000aecd  lea     r9, [rsp+38h+arg_8]; void *
0x18000aed2  mov     dword ptr [rsp+38h+phkResult], r8d; unsigned int
0x18000aed7  lea     rdx, aFilecachesize; "FileCacheSize"
0x18000aede  lea     rcx, [rsp+38h+hKey]; this
0x18000aee3  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18000aee8  cmp     eax, 2
0x18000aeeb  jnz     short loc_18000AEF3
0x18000aeed  mov     [rsp+38h+arg_8], ebx
0x18000aef1  xor     eax, eax
0x18000aef3  mov     r9d, 1D4h; unsigned int
0x18000aef9  lea     r8, aBaseEcoWdsTran_7; "base\\eco\\wds\\transport\\lib\\tptmisc"...
0x18000af00  mov     ecx, eax; unsigned int
0x18000af02  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000af07  test    eax, eax
0x18000af09  jnz     short loc_18000AF46
0x18000af0b  mov     eax, [rsp+38h+arg_8]
0x18000af0f  mov     edx, 400h
0x18000af14  cmp     eax, edx
0x18000af16  mov     ecx, eax
0x18000af18  cmova   ecx, edx
0x18000af1b  cmp     eax, ebx
0x18000af1d  cmovb   ecx, ebx
0x18000af20  shl     ecx, 0Ah
0x18000af23  mov     [rsp+38h+arg_8], ecx
0x18000af27  lea     eax, [rcx+rcx]
0x18000af2a  cmp     edi, 1
0x18000af2d  jbe     short loc_18000AF33
0x18000af2f  xor     edx, edx
0x18000af31  div     edi
0x18000af33  mov     edx, 5CAh
0x18000af38  mov     ecx, eax
0x18000af3a  cmp     eax, edx
0x18000af3c  cmova   ecx, edx
0x18000af3f  cmp     eax, ebx
0x18000af41  cmovb   ecx, ebx
0x18000af44  mov     ebx, ecx
0x18000af46  mov     rcx, [rsp+38h+hKey]; hKey
0x18000af4b  test    rcx, rcx
0x18000af4e  jz      short loc_18000AF5C
0x18000af50  call    cs:__imp_RegCloseKey
0x18000af57  nop     dword ptr [rax+rax+00h]
0x18000af5c  mov     eax, ebx
0x18000af5e  mov     rbx, [rsp+38h+arg_0]
0x18000af63  add     rsp, 30h
0x18000af67  pop     rdi
0x18000af68  retn
```
