# ResetMachineKeys(void)

- ea: `0x180047480`
- end: `0x180047566`
- name: `?ResetMachineKeys@@YAJXZ`
- size: `230`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180023838`

## callees

- `0x18000d56c`
- `0x18004741c`
- `0x180047480`
- `0x18004bf5f`
- `0x18004bfa7`
- `0x18004bfcb`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800474b4`
- `KERNEL32!lstrlenW` at `0x1800474b4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180047512`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180047512`
- `ADVAPI32!RegCloseKey` at `0x180047545`
- `ADVAPI32!RegCloseKey` at `0x180047545`
- `ADVAPI32!RegSetValueExW` at `0x18004753b`
- `ADVAPI32!RegSetValueExW` at `0x18004753b`

## string_xrefs

- `0x180047534`: `LastInstallTime`

## pseudocode

```c
__int64 ResetMachineKeys(void)
{
  unsigned int v0; // ebx
  NTSTATUS v1; // eax
  NTSTATUS v2; // ebx
  struct _LSA_UNICODE_STRING KeyName; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+10h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+58h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+20h] BYREF

  PolicyHandle = 0;
  hKey = 0;
  v0 = OpenLSAPolicy(&PolicyHandle);
  if ( !v0 )
  {
    KeyName.Buffer = (PWSTR)L"L$ASP.NETAutoGenKeysV44.0.30319.0";
    KeyName.MaximumLength = 2 * lstrlenW(L"L$ASP.NETAutoGenKeysV44.0.30319.0");
    KeyName.Length = KeyName.MaximumLength;
    v1 = LsaStorePrivateData_0(PolicyHandle, &KeyName, 0);
    v2 = v1;
    if ( v1 && LsaNtStatusToWinError_0(v1) )
      LsaNtStatusToWinError_0(v2);
    v0 = CRegInfo::OpenCurrentVersionKey(&hKey, 0x20006u, 1, 1);
    if ( !v0 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      RegSetValueExW(hKey, L"LastInstallTime", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u);
      RegCloseKey(hKey);
    }
  }
  if ( PolicyHandle )
    LsaClose_0(PolicyHandle);
  return v0;
}

```

## disassembly

```asm
0x180047480  mov     [rsp-8+arg_18], rbx
0x180047485  push    rbp
0x180047486  mov     rbp, rsp
0x180047489  sub     rsp, 40h
0x18004748d  and     [rbp+PolicyHandle], 0
0x180047492  lea     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180047496  and     [rbp+hKey], 0
0x18004749b  call    ?OpenLSAPolicy@@YAJPEAPEAX@Z; OpenLSAPolicy(void * *)
0x1800474a0  mov     ebx, eax
0x1800474a2  test    eax, eax
0x1800474a4  jnz     loc_18004754B
0x1800474aa  lea     rbx, aLAspNetautogen; "L$ASP.NETAutoGenKeysV44.0.30319.0"
0x1800474b1  mov     rcx, rbx; lpString
0x1800474b4  call    cs:__imp_lstrlenW
0x1800474ba  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800474be  lea     rdx, [rbp+KeyName]; KeyName
0x1800474c2  add     ax, ax
0x1800474c5  mov     [rbp+KeyName.Buffer], rbx
0x1800474c9  xor     r8d, r8d; PrivateData
0x1800474cc  mov     [rbp+KeyName.MaximumLength], ax
0x1800474d0  mov     [rbp+KeyName.Length], ax
0x1800474d4  call    LsaStorePrivateData_0
0x1800474d9  mov     ebx, eax
0x1800474db  test    eax, eax
0x1800474dd  jz      short loc_1800474F1
0x1800474df  mov     ecx, eax; Status
0x1800474e1  call    LsaNtStatusToWinError_0
0x1800474e6  test    eax, eax
0x1800474e8  jz      short loc_1800474F1
0x1800474ea  mov     ecx, ebx; Status
0x1800474ec  call    LsaNtStatusToWinError_0
0x1800474f1  mov     r8d, 1; int
0x1800474f7  lea     rcx, [rbp+hKey]; dwOptions
0x1800474fb  mov     r9d, r8d; int
0x1800474fe  mov     edx, 20006h; samDesired
0x180047503  call    ?OpenCurrentVersionKey@CRegInfo@@SAJPEAPEAUHKEY__@@KHH@Z; CRegInfo::OpenCurrentVersionKey(HKEY__ * *,ulong,int,int)
0x180047508  mov     ebx, eax
0x18004750a  test    eax, eax
0x18004750c  jnz     short loc_18004754B
0x18004750e  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180047512  call    cs:__imp_GetSystemTimeAsFileTime
0x180047518  mov     rcx, [rbp+hKey]; hKey
0x18004751c  lea     rax, [rbp+SystemTimeAsFileTime]
0x180047520  mov     [rsp+40h+cbData], 8; cbData
0x180047528  lea     r9d, [rbx+0Bh]; dwType
0x18004752c  xor     r8d, r8d; Reserved
0x18004752f  mov     [rsp+40h+lpData], rax; lpData
0x180047534  lea     rdx, aLastinstalltim; "LastInstallTime"
0x18004753b  call    cs:__imp_RegSetValueExW
0x180047541  mov     rcx, [rbp+hKey]; hKey
0x180047545  call    cs:__imp_RegCloseKey
0x18004754b  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18004754f  test    rcx, rcx
0x180047552  jz      short loc_180047559
0x180047554  call    LsaClose_0
0x180047559  mov     eax, ebx
0x18004755b  mov     rbx, [rsp+40h+arg_18]
0x180047560  add     rsp, 40h
0x180047564  pop     rbp
0x180047565  retn
```
