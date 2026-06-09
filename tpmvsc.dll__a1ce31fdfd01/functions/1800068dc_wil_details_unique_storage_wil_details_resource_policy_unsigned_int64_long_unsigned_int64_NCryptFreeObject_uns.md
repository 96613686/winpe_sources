# wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)

- ea: `0x1800068dc`
- end: `0x1800068f3`
- name: `??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `SECURITY_STATUS __fastcall(NCRYPT_HANDLE *)`
- caller_count: `18`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800068b0`
- `0x1800085b8`
- `0x18000a81c`
- `0x18000dce0`
- `0x18000f374`
- `0x180016324`
- `0x18001d6b4`
- `0x18001ec10`
- `0x18001f784`
- `0x1800201f0`
- `0x180021be0`
- `0x180022e80`
- `0x180023a38`
- `0x180023e54`
- `0x180024378`
- `0x180024aac`
- `0x18002893c`
- `0x180029938`

## callees

- `0x1800068dc`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x1800068e8`
- `ncrypt!NCryptFreeObject` at `0x1800068e8`

## pseudocode

```c
SECURITY_STATUS __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(
        NCRYPT_HANDLE *a1)
{
  NCRYPT_HANDLE v1; // rcx
  SECURITY_STATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return NCryptFreeObject(v1);
  return result;
}

```

## disassembly

```asm
0x1800068dc  sub     rsp, 28h
0x1800068e0  mov     rcx, [rcx]; hObject
0x1800068e3  test    rcx, rcx
0x1800068e6  jz      short loc_1800068EE
0x1800068e8  call    cs:__imp_NCryptFreeObject
0x1800068ee  add     rsp, 28h
0x1800068f2  retn
```
