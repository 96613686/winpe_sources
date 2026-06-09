# CTRegValue<ushort *>::WriteToReg(void)

- ea: `0x1800056e0`
- end: `0x18000579a`
- name: `?WriteToReg@?$CTRegValue@PEAG@@IEAAJXZ`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180014374`

## callees

- `0x18000564c`
- `0x1800056e0`
- `0x1800057a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000575b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000575b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000572b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000572b`

## pseudocode

```c
__int64 __fastcall CTRegValue<unsigned short *>::WriteToReg(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rsi
  int v4; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 32);
  if ( v1 )
  {
    hKey = 0;
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)(v1 + 2 * v3) );
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)(a1 + 16), 0, 0x2000000u, &hKey);
    if ( v4
      || (v4 = RegSetValueExW(
                 hKey,
                 *(LPCWSTR *)(a1 + 8),
                 0,
                 *(_DWORD *)(a1 + 24),
                 *(const BYTE **)(a1 + 32),
                 2 * v3 + 2)) != 0 )
    {
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
    }
    else
    {
      *(_DWORD *)a1 = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    return (unsigned int)CRegValue::Delete((CRegValue *)a1);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800056e0  push    rbx
0x1800056e2  push    rbp
0x1800056e3  push    rsi
0x1800056e4  push    rdi
0x1800056e5  sub     rsp, 38h
0x1800056e9  mov     rax, [rcx+20h]
0x1800056ed  xor     ebp, ebp
0x1800056ef  mov     rdi, rcx
0x1800056f2  test    rax, rax
0x1800056f5  jz      loc_180005788
0x1800056fb  mov     [rsp+58h+hKey], rbp
0x180005700  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005704  inc     rsi
0x180005707  cmp     [rax+rsi*2], bp
0x18000570b  jnz     short loc_180005704
0x18000570d  mov     rdx, [rcx+10h]; lpSubKey
0x180005711  lea     rax, [rsp+58h+hKey]
0x180005716  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000571d  mov     [rsp+58h+phkResult], rax; phkResult
0x180005722  mov     r9d, 2000000h; samDesired
0x180005728  xor     r8d, r8d; ulOptions
0x18000572b  call    cs:__imp_RegOpenKeyExW
0x180005731  mov     ebx, eax
0x180005733  test    eax, eax
0x180005735  jnz     short loc_18000576F
0x180005737  mov     r9d, [rdi+18h]; dwType
0x18000573b  lea     eax, ds:2[rsi*2]
0x180005742  mov     rdx, [rdi+8]; lpValueName
0x180005746  xor     r8d, r8d; Reserved
0x180005749  mov     rcx, [rsp+58h+hKey]; hKey
0x18000574e  mov     [rsp+58h+cbData], eax; cbData
0x180005752  mov     rax, [rdi+20h]
0x180005756  mov     [rsp+58h+phkResult], rax; lpData
0x18000575b  call    cs:__imp_RegSetValueExW
0x180005761  mov     ebx, eax
0x180005763  test    eax, eax
0x180005765  jnz     short loc_18000576F
0x180005767  mov     dword ptr [rdi], 1
0x18000576d  jmp     short loc_18000577C
0x18000576f  test    ebx, ebx
0x180005771  jle     short loc_18000577C
0x180005773  movzx   ebx, bx
0x180005776  or      ebx, 80070000h
0x18000577c  lea     rcx, [rsp+58h+hKey]
0x180005781  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180005786  jmp     short loc_18000578F
0x180005788  call    ?Delete@CRegValue@@QEAAJXZ; CRegValue::Delete(void)
0x18000578d  mov     ebx, eax
0x18000578f  mov     eax, ebx
0x180005791  add     rsp, 38h
0x180005795  pop     rdi
0x180005796  pop     rsi
0x180005797  pop     rbp
0x180005798  pop     rbx
0x180005799  retn
```
