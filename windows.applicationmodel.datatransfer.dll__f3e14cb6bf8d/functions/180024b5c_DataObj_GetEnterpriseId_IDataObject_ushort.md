# DataObj_GetEnterpriseId(IDataObject *,ushort * *)

- ea: `0x180024b5c`
- end: `0x180024cad`
- name: `?DataObj_GetEnterpriseId@@YAJPEAUIDataObject@@PEAPEAG@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct IDataObject *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e5a0`
- `0x18006b730`

## callees

- `0x180024b5c`
- `0x180024cb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c98`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024b8a`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024b97`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024ba4`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024bb1`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024bbe`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024bcb`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024bdf`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024bf3`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024c00`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024b8a`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024b97`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024ba4`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024bb1`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024bbe`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024bcb`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024bdf`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024bf3`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180024c00`

## string_xrefs

- `0x180024b9d`: `FileGroupDescriptor`
- `0x180024baa`: `FileGroupDescriptorW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DataObj_GetEnterpriseId(struct IDataObject *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rcx
  unsigned __int16 *v6; // [rsp+28h] [rbp-50h] BYREF
  char v7; // [rsp+30h] [rbp-48h]
  unsigned __int16 *v8; // [rsp+88h] [rbp+10h]

  *a2 = 0;
  if ( !g_cfAsyncFlag_Storage )
  {
    RegisterClipboardFormatW(L"UniformResourceLocator");
    RegisterClipboardFormatW(L"Shell IDList Array");
    RegisterClipboardFormatW(L"FileGroupDescriptor");
    RegisterClipboardFormatW(L"FileGroupDescriptorW");
    RegisterClipboardFormatW(L"Shell Object Offsets");
    g_cfEnterpriseId_Storage = RegisterClipboardFormatW(L"EnterpriseDataProtectionId");
    g_cfAsyncFlag_Storage = RegisterClipboardFormatW(L"AsyncFlag");
    RegisterClipboardFormatW(L"FilePropertyStore");
    RegisterClipboardFormatW(L"FilePropertyStoreByteSize");
  }
  v8 = 0;
  v6 = 0;
  v7 = 1;
  DataObj_GetString(a1, g_cfEnterpriseId_Storage, &v6);
  if ( v7 )
    v8 = v6;
  v4 = v8;
  if ( v8 && *v8 )
  {
    v4 = 0;
    *a2 = v8;
  }
  if ( v4 )
    CoTaskMemFree(v4);
  return 0;
}

```

## disassembly

```asm
0x180024b5c  push    rbx
0x180024b5e  push    rbp
0x180024b5f  push    rsi
0x180024b60  push    rdi
0x180024b61  push    r14
0x180024b63  push    r15
0x180024b65  sub     rsp, 48h
0x180024b69  mov     r14, rdx
0x180024b6c  mov     rbx, rcx
0x180024b6f  xor     r15d, r15d
0x180024b72  mov     [rdx], r15
0x180024b75  cmp     r15w, cs:?g_cfAsyncFlag_Storage@@3GA; ushort g_cfAsyncFlag_Storage
0x180024b7d  jnz     loc_180024C06
0x180024b83  lea     rcx, szFormat; "UniformResourceLocator"
0x180024b8a  call    cs:__imp_RegisterClipboardFormatW
0x180024b90  lea     rcx, aShellIdlistArr; "Shell IDList Array"
0x180024b97  call    cs:__imp_RegisterClipboardFormatW
0x180024b9d  lea     rcx, aFilegroupdescr_0; "FileGroupDescriptor"
0x180024ba4  call    cs:__imp_RegisterClipboardFormatW
0x180024baa  lea     rcx, aFilegroupdescr; "FileGroupDescriptorW"
0x180024bb1  call    cs:__imp_RegisterClipboardFormatW
0x180024bb7  lea     rcx, aShellObjectOff; "Shell Object Offsets"
0x180024bbe  call    cs:__imp_RegisterClipboardFormatW
0x180024bc4  lea     rcx, aEnterprisedata; "EnterpriseDataProtectionId"
0x180024bcb  call    cs:__imp_RegisterClipboardFormatW
0x180024bd1  mov     cs:?g_cfEnterpriseId_Storage@@3GA, ax; ushort g_cfEnterpriseId_Storage
0x180024bd8  lea     rcx, aAsyncflag; "AsyncFlag"
0x180024bdf  call    cs:__imp_RegisterClipboardFormatW
0x180024be5  mov     cs:?g_cfAsyncFlag_Storage@@3GA, ax; ushort g_cfAsyncFlag_Storage
0x180024bec  lea     rcx, aFilepropertyst; "FilePropertyStore"
0x180024bf3  call    cs:__imp_RegisterClipboardFormatW
0x180024bf9  lea     rcx, aFilepropertyst_0; "FilePropertyStoreByteSize"
0x180024c00  call    cs:__imp_RegisterClipboardFormatW
0x180024c06  mov     [rsp+78h+arg_8], r15
0x180024c0e  lea     rax, [rsp+78h+arg_8]
0x180024c16  mov     [rsp+78h+var_58], rax
0x180024c1b  mov     [rsp+78h+var_50], r15
0x180024c20  mov     [rsp+78h+var_48], 1
0x180024c25  lea     r8, [rsp+78h+var_50]; unsigned __int16 **
0x180024c2a  movzx   edx, cs:?g_cfEnterpriseId_Storage@@3GA; unsigned __int16
0x180024c31  mov     rcx, rbx; struct IDataObject *
0x180024c34  call    ?DataObj_GetString@@YAJPEAUIDataObject@@GPEAPEAG@Z; DataObj_GetString(IDataObject *,ushort,ushort * *)
0x180024c39  nop
0x180024c3a  cmp     [rsp+78h+var_48], r15b
0x180024c3f  jz      short loc_180024C6F
0x180024c41  mov     rbp, [rsp+78h+var_50]
0x180024c46  mov     rdi, [rsp+78h+var_58]
0x180024c4b  mov     rsi, [rdi]
0x180024c4e  test    rsi, rsi
0x180024c51  jz      short loc_180024C6C
0x180024c53  call    cs:__imp_GetLastError
0x180024c59  mov     ebx, eax
0x180024c5b  mov     rcx, rsi; pv
0x180024c5e  call    cs:__imp_CoTaskMemFree
0x180024c64  mov     ecx, ebx; dwErrCode
0x180024c66  call    cs:__imp_SetLastError
0x180024c6c  mov     [rdi], rbp
0x180024c6f  mov     rcx, [rsp+78h+arg_8]
0x180024c77  test    rcx, rcx
0x180024c7a  jz      short loc_180024C93
0x180024c7c  cmp     [rcx], r15w
0x180024c80  jz      short loc_180024C93
0x180024c82  mov     rax, rcx
0x180024c85  mov     rcx, r15; pv
0x180024c88  mov     [rsp+78h+arg_8], rcx
0x180024c90  mov     [r14], rax
0x180024c93  test    rcx, rcx
0x180024c96  jz      short loc_180024C9E
0x180024c98  call    cs:__imp_CoTaskMemFree
0x180024c9e  xor     eax, eax
0x180024ca0  add     rsp, 48h
0x180024ca4  pop     r15
0x180024ca6  pop     r14
0x180024ca8  pop     rdi
0x180024ca9  pop     rsi
0x180024caa  pop     rbp
0x180024cab  pop     rbx
0x180024cac  retn
```
