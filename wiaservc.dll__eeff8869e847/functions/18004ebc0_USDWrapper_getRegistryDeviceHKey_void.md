# USDWrapper::getRegistryDeviceHKey(void)

- ea: `0x18004ebc0`
- end: `0x18004ec99`
- name: `?getRegistryDeviceHKey@USDWrapper@@MEAAPEAUHKEY__@@XZ`
- size: `217`
- prototype: `HKEY __fastcall(USDWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18002e9d8`
- `0x18002eab4`
- `0x18004ebc0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18004ebf9`
- `ADVAPI32!RegOpenKeyExW` at `0x18004ec24`
- `ADVAPI32!RegOpenKeyExW` at `0x18004ebf9`
- `ADVAPI32!RegOpenKeyExW` at `0x18004ec24`

## string_xrefs

- `0x18004ec46`: `USDWrapper::getRegistryDeviceHKey`
- `0x18004ec7d`: `USDWrapper::getRegistryDeviceHKey`
- `0x18004ec35`: `We could not return the registry key for (%ws)`
- `0x18004ec64`: `We could not return the registry key for (%ws)`

## pseudocode

```c
HKEY __fastcall USDWrapper::getRegistryDeviceHKey(USDWrapper *this)
{
  const WCHAR *v1; // rdx
  char *v3; // rbx
  void *v4; // rdx
  void **v5; // rax
  void *v6; // rdx
  __int64 v7; // rcx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  v1 = (const WCHAR *)*((_QWORD *)this + 492);
  phkResult = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0xF003Fu, &phkResult)
    && RegOpenKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)this + 492), 0, 0x20019u, &phkResult) )
  {
    v3 = (char *)WiaTrace_TraceLogWithSubComp(
                   0,
                   "We could not return the registry key for (%ws)",
                   *((_QWORD *)this + 492));
    WriteDbgTraceWarningWI("USDWrapper::getRegistryDeviceHKey", v3);
    WiaTrcLib::Free((WiaTrcLib *)v3, v4);
    v5 = (void **)WiaTrace_TraceWithSubComp(
                    0,
                    "We could not return the registry key for (%ws)",
                    *((_QWORD *)this + 492));
    WiaTrace_ProcessTrace_Ex(v7, v6, (void *)"USDWrapper::getRegistryDeviceHKey", 2, v5);
  }
  return phkResult;
}

```

## disassembly

```asm
0x18004ebc0  mov     r11, rsp
0x18004ebc3  mov     [r11+10h], rbx
0x18004ebc7  push    rdi
0x18004ebc8  sub     rsp, 30h
0x18004ebcc  mov     rdx, [rcx+0F60h]; lpSubKey
0x18004ebd3  lea     rax, [r11+8]
0x18004ebd7  mov     rdi, rcx
0x18004ebda  mov     qword ptr [r11+8], 0
0x18004ebe2  mov     rbx, 0FFFFFFFF80000002h
0x18004ebe9  mov     [r11-18h], rax
0x18004ebed  mov     rcx, rbx; hKey
0x18004ebf0  mov     r9d, 0F003Fh; samDesired
0x18004ebf6  xor     r8d, r8d; ulOptions
0x18004ebf9  call    cs:__imp_RegOpenKeyExW
0x18004ebff  test    eax, eax
0x18004ec01  jz      loc_18004EC89
0x18004ec07  mov     rdx, [rdi+0F60h]; lpSubKey
0x18004ec0e  lea     rax, [rsp+38h+arg_0]
0x18004ec13  mov     r9d, 20019h; samDesired
0x18004ec19  mov     [rsp+38h+phkResult], rax; phkResult
0x18004ec1e  xor     r8d, r8d; ulOptions
0x18004ec21  mov     rcx, rbx; hKey
0x18004ec24  call    cs:__imp_RegOpenKeyExW
0x18004ec2a  test    eax, eax
0x18004ec2c  jz      short loc_18004EC89
0x18004ec2e  mov     r8, [rdi+0F60h]
0x18004ec35  lea     rdx, aWeCouldNotRetu; "We could not return the registry key fo"...
0x18004ec3c  xor     ecx, ecx
0x18004ec3e  call    WiaTrace_TraceLogWithSubComp
0x18004ec43  mov     rdx, rax; char *
0x18004ec46  lea     rcx, aUsdwrapperGetr; "USDWrapper::getRegistryDeviceHKey"
0x18004ec4d  mov     rbx, rax
0x18004ec50  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18004ec55  mov     rcx, rbx; this
0x18004ec58  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004ec5d  mov     r8, [rdi+0F60h]
0x18004ec64  lea     rdx, aWeCouldNotRetu; "We could not return the registry key fo"...
0x18004ec6b  xor     ecx, ecx
0x18004ec6d  call    WiaTrace_TraceWithSubComp
0x18004ec72  mov     r9d, 2; int
0x18004ec78  mov     [rsp+38h+phkResult], rax; lpMem
0x18004ec7d  lea     r8, aUsdwrapperGetr; "USDWrapper::getRegistryDeviceHKey"
0x18004ec84  call    WiaTrace_ProcessTrace_Ex
0x18004ec89  mov     rax, [rsp+38h+arg_0]
0x18004ec8e  mov     rbx, [rsp+38h+arg_8]
0x18004ec93  add     rsp, 30h
0x18004ec97  pop     rdi
0x18004ec98  retn
```
