# InitStandaloneNativeConfigSystem(void)

- ea: `0x18005d9c0`
- end: `0x18005da7d`
- name: `?InitStandaloneNativeConfigSystem@@YAJXZ`
- size: `189`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180059e90`

## callees

- `0x18005d9c0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18005d9d1`
- `KERNEL32!EnterCriticalSection` at `0x18005d9d1`
- `KERNEL32!LeaveCriticalSection` at `0x18005da6a`
- `KERNEL32!LeaveCriticalSection` at `0x18005da6a`
- `ole32!CoGetClassObject` at `0x18005da0b`
- `ole32!CoGetClassObject` at `0x18005da0b`
- `ole32!CoCreateInstance` at `0x18005da2e`
- `ole32!CoCreateInstance` at `0x18005da2e`

## pseudocode

```c
__int64 InitStandaloneNativeConfigSystem(void)
{
  unsigned int v0; // ebx
  HRESULT ClassObject; // eax
  LPVOID v2; // rcx

  EnterCriticalSection(&g_csExternalConfig);
  _InterlockedAdd(&g_hConfigRefCount, 1u);
  v0 = 0;
  if ( !g_pConfigurationSystem )
  {
    ClassObject = CoGetClassObject(
                    &CLSID_AppHostAdminManager,
                    1u,
                    0,
                    &IID_IAppHostAdminManager,
                    &g_pConfigurationSystem);
    if ( ClassObject < 0
      && (ClassObject = CoCreateInstance(
                          &CLSID_AppHostAdminManager,
                          0,
                          0x15u,
                          &IID_IAppHostAdminManager,
                          &g_pConfigurationSystem),
          ClassObject < 0)
      || (v2 = g_pConfigurationSystem) == 0 )
    {
      _InterlockedDecrement(&g_hConfigRefCount);
      v2 = g_pConfigurationSystem;
    }
    if ( !ClassObject && !v2 )
      ClassObject = -2147024882;
    v0 = ClassObject;
  }
  LeaveCriticalSection(&g_csExternalConfig);
  return v0;
}

```

## disassembly

```asm
0x18005d9c0  mov     [rsp+arg_0], rbx
0x18005d9c5  push    rdi
0x18005d9c6  sub     rsp, 30h
0x18005d9ca  lea     rcx, ?g_csExternalConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005d9d1  call    cs:__imp_EnterCriticalSection
0x18005d9d7  mov     edx, 1; dwClsContext
0x18005d9dc  lock add cs:?g_hConfigRefCount@@3JA, edx; long g_hConfigRefCount
0x18005d9e3  xor     ebx, ebx
0x18005d9e5  cmp     cs:?g_pConfigurationSystem@@3PEAUIAppHostAdminManager@@EA, rbx; IAppHostAdminManager * g_pConfigurationSystem
0x18005d9ec  jnz     short loc_18005DA63
0x18005d9ee  lea     rdi, ?g_pConfigurationSystem@@3PEAUIAppHostAdminManager@@EA; IAppHostAdminManager * g_pConfigurationSystem
0x18005d9f5  xor     r8d, r8d; pvReserved
0x18005d9f8  lea     r9, IID_IAppHostAdminManager; riid
0x18005d9ff  mov     [rsp+38h+ppv], rdi; ppv
0x18005da04  lea     rcx, CLSID_AppHostAdminManager; rclsid
0x18005da0b  call    cs:__imp_CoGetClassObject
0x18005da11  test    eax, eax
0x18005da13  jns     short loc_18005DA38
0x18005da15  lea     r9, IID_IAppHostAdminManager; riid
0x18005da1c  mov     [rsp+38h+ppv], rdi; ppv
0x18005da21  xor     edx, edx; pUnkOuter
0x18005da23  lea     r8d, [rbx+15h]; dwClsContext
0x18005da27  lea     rcx, CLSID_AppHostAdminManager; rclsid
0x18005da2e  call    cs:__imp_CoCreateInstance
0x18005da34  test    eax, eax
0x18005da36  js      short loc_18005DA44
0x18005da38  mov     rcx, cs:?g_pConfigurationSystem@@3PEAUIAppHostAdminManager@@EA; IAppHostAdminManager * g_pConfigurationSystem
0x18005da3f  test    rcx, rcx
0x18005da42  jnz     short loc_18005DA52
0x18005da44  lock dec cs:?g_hConfigRefCount@@3JA; long g_hConfigRefCount
0x18005da4b  mov     rcx, cs:?g_pConfigurationSystem@@3PEAUIAppHostAdminManager@@EA; IAppHostAdminManager * g_pConfigurationSystem
0x18005da52  test    eax, eax
0x18005da54  jnz     short loc_18005DA61
0x18005da56  test    rcx, rcx
0x18005da59  mov     edx, 8007000Eh
0x18005da5e  cmovz   eax, edx
0x18005da61  mov     ebx, eax
0x18005da63  lea     rcx, ?g_csExternalConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005da6a  call    cs:__imp_LeaveCriticalSection
0x18005da70  mov     eax, ebx
0x18005da72  mov     rbx, [rsp+38h+arg_0]
0x18005da77  add     rsp, 30h
0x18005da7b  pop     rdi
0x18005da7c  retn
```
