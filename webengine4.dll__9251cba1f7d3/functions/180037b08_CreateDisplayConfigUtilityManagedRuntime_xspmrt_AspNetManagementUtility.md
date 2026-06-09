# CreateDisplayConfigUtilityManagedRuntime(xspmrt::_AspNetManagementUtility * *)

- ea: `0x180037b08`
- end: `0x180037c05`
- name: `?CreateDisplayConfigUtilityManagedRuntime@@YAJPEAPEAU_AspNetManagementUtility@xspmrt@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct xspmrt::_AspNetManagementUtility **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800385e0`

## callees

- `0x180016ce0`
- `0x180037b08`
- `0x18003abe4`
- `0x18004d030`
- `0x18004d854`

## import_xrefs

- `ole32!CoUninitialize` at `0x180037be5`
- `ole32!CoUninitialize` at `0x180037be5`
- `ole32!CoCreateInstance` at `0x180037b95`
- `ole32!CoCreateInstance` at `0x180037bb8`
- `ole32!CoCreateInstance` at `0x180037b95`
- `ole32!CoCreateInstance` at `0x180037bb8`
- `ole32!CLSIDFromProgID` at `0x180037b72`
- `ole32!CLSIDFromProgID` at `0x180037b72`

## string_xrefs

- `0x180037b26`: `Creating managed runtime for modifying config files`
- `0x180037bc6`: `Creating managed runtime for modifying config files`
- `0x180037b33`: `CreateDisplayConfigUtilityManagedRuntime`
- `0x180037bd0`: `CreateDisplayConfigUtilityManagedRuntime`

## pseudocode

```c
__int64 __fastcall CreateDisplayConfigUtilityManagedRuntime(LPVOID *a1)
{
  unsigned int v2; // ebx
  int v4; // [rsp+30h] [rbp-28h] BYREF
  GUID clsid; // [rsp+38h] [rbp-20h] BYREF

  v4 = 0;
  CSetupLogging::Log(
    1,
    "CreateDisplayConfigUtilityManagedRuntime",
    0,
    "Creating managed runtime for modifying config files",
    0);
  v2 = EnsureCoInitialized(&v4);
  if ( !v2 )
  {
    v2 = InitializeLibrary(0);
    if ( !v2 )
    {
      v2 = CLSIDFromProgID(L"Microsoft.Aspnet.Snapin.AspNetManagementUtility.4", &clsid);
      if ( !v2 )
      {
        v2 = CoCreateInstance(&clsid, 0, 4u, &GUID_b51f3f69_4e20_4d13_a42e_d5648bfa30b9, a1);
        if ( v2 )
          v2 = CoCreateInstance(&clsid, 0, 1u, &GUID_b51f3f69_4e20_4d13_a42e_d5648bfa30b9, a1);
      }
    }
  }
  CSetupLogging::Log(
    v2,
    "CreateDisplayConfigUtilityManagedRuntime",
    0,
    "Creating managed runtime for modifying config files",
    0);
  if ( v4 )
    CoUninitialize();
  return v2;
}

```

## disassembly

```asm
0x180037b08  mov     [rsp+arg_8], rbx
0x180037b0d  push    rdi
0x180037b0e  sub     rsp, 50h
0x180037b12  mov     rax, cs:__security_cookie
0x180037b19  xor     rax, rsp
0x180037b1c  mov     [rsp+58h+var_10], rax
0x180037b21  and     [rsp+58h+var_28], 0
0x180037b26  lea     r9, aCreatingManage; "Creating managed runtime for modifying "...
0x180037b2d  and     [rsp+58h+ppv], 0
0x180037b33  lea     rdx, aCreatedisplayc; "CreateDisplayConfigUtilityManagedRuntim"...
0x180037b3a  xor     r8d, r8d; unsigned int
0x180037b3d  mov     rdi, rcx
0x180037b40  lea     ecx, [r8+1]; int
0x180037b44  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180037b49  lea     rcx, [rsp+58h+var_28]; int *
0x180037b4e  call    ?EnsureCoInitialized@@YAJPEAH@Z; EnsureCoInitialized(int *)
0x180037b53  mov     ebx, eax
0x180037b55  test    eax, eax
0x180037b57  jnz     short loc_180037BC0
0x180037b59  xor     ecx, ecx; int
0x180037b5b  call    ?InitializeLibrary@@YAJH@Z; InitializeLibrary(int)
0x180037b60  mov     ebx, eax
0x180037b62  test    eax, eax
0x180037b64  jnz     short loc_180037BC0
0x180037b66  lea     rdx, [rsp+58h+clsid]; lpclsid
0x180037b6b  lea     rcx, szProgID; "Microsoft.Aspnet.Snapin.AspNetManagemen"...
0x180037b72  call    cs:__imp_CLSIDFromProgID
0x180037b78  mov     ebx, eax
0x180037b7a  test    eax, eax
0x180037b7c  jnz     short loc_180037BC0
0x180037b7e  lea     r9, _GUID_b51f3f69_4e20_4d13_a42e_d5648bfa30b9; riid
0x180037b85  mov     [rsp+58h+ppv], rdi; ppv
0x180037b8a  xor     edx, edx; pUnkOuter
0x180037b8c  lea     r8d, [rax+4]; dwClsContext
0x180037b90  lea     rcx, [rsp+58h+clsid]; rclsid
0x180037b95  call    cs:__imp_CoCreateInstance
0x180037b9b  mov     ebx, eax
0x180037b9d  test    eax, eax
0x180037b9f  jz      short loc_180037BC0
0x180037ba1  xor     edx, edx; pUnkOuter
0x180037ba3  mov     [rsp+58h+ppv], rdi; unsigned __int16 *
0x180037ba8  lea     r9, _GUID_b51f3f69_4e20_4d13_a42e_d5648bfa30b9; riid
0x180037baf  lea     rcx, [rsp+58h+clsid]; rclsid
0x180037bb4  lea     r8d, [rdx+1]; dwClsContext
0x180037bb8  call    cs:__imp_CoCreateInstance
0x180037bbe  mov     ebx, eax
0x180037bc0  and     [rsp+58h+ppv], 0
0x180037bc6  lea     r9, aCreatingManage; "Creating managed runtime for modifying "...
0x180037bcd  xor     r8d, r8d; unsigned int
0x180037bd0  lea     rdx, aCreatedisplayc; "CreateDisplayConfigUtilityManagedRuntim"...
0x180037bd7  mov     ecx, ebx; int
0x180037bd9  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180037bde  cmp     [rsp+58h+var_28], 0
0x180037be3  jz      short loc_180037BEB
0x180037be5  call    cs:__imp_CoUninitialize
0x180037beb  mov     eax, ebx
0x180037bed  mov     rcx, [rsp+58h+var_10]
0x180037bf2  xor     rcx, rsp; StackCookie
0x180037bf5  call    __security_check_cookie
0x180037bfa  mov     rbx, [rsp+58h+arg_8]
0x180037bff  add     rsp, 50h
0x180037c03  pop     rdi
0x180037c04  retn
```
