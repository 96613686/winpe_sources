# NotifyHostReadyWithProcessId(ushort const *,ulong)

- ea: `0x140058464`
- end: `0x1400584c5`
- name: `?NotifyHostReadyWithProcessId@@YA_NPEBGK@Z`
- size: `97`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400584cc`

## callees

- `0x140053000`
- `0x140056db0`
- `0x140058464`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400584a4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400584a4`

## string_xrefs

- `0x140058496`: `ProcessId`

## pseudocode

```c
bool __fastcall NotifyHostReadyWithProcessId(unsigned __int16 *a1, int a2)
{
  bool v2; // bl
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a2;
  hKey = (HKEY)a1;
  GetHostSessionSubKey(&hKey);
  if ( hKey )
    v2 = RegSetKeyValueW(hKey, 0, L"ProcessId", 4u, &Data, 4u) == 0;
  else
    v2 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v2;
}

```

## disassembly

```asm
0x140058464  mov     [rsp+Data], edx
0x140058468  mov     [rsp+hKey], rcx
0x14005846d  push    rbx
0x14005846e  sub     rsp, 30h
0x140058472  lea     rcx, [rsp+38h+hKey]
0x140058477  call    ?GetHostSessionSubKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGK@Z; GetHostSessionSubKey(ushort const *,ulong)
0x14005847c  mov     rcx, [rsp+38h+hKey]; hKey
0x140058481  test    rcx, rcx
0x140058484  jz      short loc_1400584B1
0x140058486  mov     r9d, 4; dwType
0x14005848c  lea     rax, [rsp+38h+Data]
0x140058491  mov     [rsp+38h+cbData], r9d; cbData
0x140058496  lea     r8, ValueName; "ProcessId"
0x14005849d  xor     edx, edx; lpSubKey
0x14005849f  mov     [rsp+38h+lpData], rax; lpData
0x1400584a4  call    cs:__imp_RegSetKeyValueW
0x1400584aa  test    eax, eax
0x1400584ac  setz    bl
0x1400584af  jmp     short loc_1400584B3
0x1400584b1  xor     ebx, ebx
0x1400584b3  lea     rcx, [rsp+38h+hKey]
0x1400584b8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400584bd  mov     al, bl
0x1400584bf  add     rsp, 30h
0x1400584c3  pop     rbx
0x1400584c4  retn
```
