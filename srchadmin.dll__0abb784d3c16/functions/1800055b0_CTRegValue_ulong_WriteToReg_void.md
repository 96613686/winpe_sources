# CTRegValue<ulong>::WriteToReg(void)

- ea: `0x1800055b0`
- end: `0x180005645`
- name: `?WriteToReg@?$CTRegValue@K@@IEAAJXZ`
- size: `149`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012870`
- `0x180012de0`
- `0x180012e40`
- `0x180012ef0`

## callees

- `0x1800055b0`
- `0x1800057a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000560d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000560d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800055e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800055e3`

## pseudocode

```c
__int64 __fastcall CTRegValue<unsigned long>::WriteToReg(__int64 a1)
{
  const WCHAR *v1; // rdx
  int v3; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(const WCHAR **)(a1 + 16);
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0x2000000u, &hKey);
  if ( v3 || (v3 = RegSetValueExW(hKey, *(LPCWSTR *)(a1 + 8), 0, 4u, (const BYTE *)(a1 + 28), 4u)) != 0 )
  {
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    *(_DWORD *)a1 = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800055b0  mov     r11, rsp
0x1800055b3  mov     [r11+10h], rbx
0x1800055b7  push    rdi
0x1800055b8  sub     rsp, 30h
0x1800055bc  mov     rdx, [rcx+10h]; lpSubKey
0x1800055c0  lea     rax, [r11+8]
0x1800055c4  mov     rdi, rcx
0x1800055c7  mov     [r11-18h], rax
0x1800055cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800055d2  mov     qword ptr [r11+8], 0
0x1800055da  mov     r9d, 2000000h; samDesired
0x1800055e0  xor     r8d, r8d; ulOptions
0x1800055e3  call    cs:__imp_RegOpenKeyExW
0x1800055e9  mov     ebx, eax
0x1800055eb  test    eax, eax
0x1800055ed  jnz     short loc_180005621
0x1800055ef  mov     rdx, [rdi+8]; lpValueName
0x1800055f3  lea     r9d, [rbx+4]; dwType
0x1800055f7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800055fc  lea     rax, [rdi+1Ch]
0x180005600  mov     [rsp+38h+cbData], r9d; cbData
0x180005605  xor     r8d, r8d; Reserved
0x180005608  mov     [rsp+38h+lpData], rax; lpData
0x18000560d  call    cs:__imp_RegSetValueExW
0x180005613  mov     ebx, eax
0x180005615  test    eax, eax
0x180005617  jnz     short loc_180005621
0x180005619  mov     dword ptr [rdi], 1
0x18000561f  jmp     short loc_18000562E
0x180005621  test    ebx, ebx
0x180005623  jle     short loc_18000562E
0x180005625  movzx   ebx, bx
0x180005628  or      ebx, 80070000h
0x18000562e  lea     rcx, [rsp+38h+hKey]
0x180005633  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180005638  mov     eax, ebx
0x18000563a  mov     rbx, [rsp+38h+arg_8]
0x18000563f  add     rsp, 30h
0x180005643  pop     rdi
0x180005644  retn
```
