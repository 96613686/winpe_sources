# CSecurityInformation::CSecurityInformation(_SE_OBJECT_TYPE)

- ea: `0x18000be34`
- end: `0x18000bef6`
- name: `??0CSecurityInformation@@QEAA@W4_SE_OBJECT_TYPE@@@Z`
- size: `194`
- prototype: `CSecurityInformation *__fastcall(CSecurityInformation *__hidden this, enum _SE_OBJECT_TYPE)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800061b0`
- `0x18000a66c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000bee7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000bee7`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18000becd`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18000becd`

## pseudocode

```c
CSecurityInformation *__fastcall CSecurityInformation::CSecurityInformation(
        CSecurityInformation *this,
        enum _SE_OBJECT_TYPE a2)
{
  *(_QWORD *)this = &CSecurityInformation::`vftable'{for `ISecurityInformation'};
  *((_QWORD *)this + 1) = &CSecurityInformation::`vftable'{for `IEffectivePermission'};
  *((_QWORD *)this + 2) = &CSecurityInformation::`vftable'{for `IEffectivePermission2'};
  *((_QWORD *)this + 3) = &CSecurityInformation::`vftable'{for `ISecurityObjectTypeInfo'};
  *((_QWORD *)this + 4) = &CSecurityInformation::`vftable'{for `ISecurityInformation3'};
  *((_QWORD *)this + 5) = &CSecurityInformation::`vftable'{for `ISecurityInformation4'};
  *((_DWORD *)this + 13) = a2;
  *((_DWORD *)this + 12) = 1;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_DWORD *)this + 78) = -1;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  _InterlockedAdd(&g_cRefThisDll, 1u);
  AuthzInitializeResourceManager(1u, 0, 0, 0, L"Dummy", (PAUTHZ_RESOURCE_MANAGER_HANDLE)this + 12);
  LoadStringW(g_hInstance, 2u, (LPWSTR)this + 54, 100);
  return this;
}

```

## disassembly

```asm
0x18000be34  push    rbx
0x18000be36  sub     rsp, 30h
0x18000be3a  mov     rbx, rcx
0x18000be3d  lea     rax, ??_7CSecurityInformation@@6BISecurityInformation@@@; const CSecurityInformation::`vftable'{for `ISecurityInformation'}
0x18000be44  mov     [rcx], rax
0x18000be47  lea     rax, ??_7CSecurityInformation@@6BIEffectivePermission@@@; const CSecurityInformation::`vftable'{for `IEffectivePermission'}
0x18000be4e  mov     [rcx+8], rax
0x18000be52  lea     rax, ??_7CSecurityInformation@@6BIEffectivePermission2@@@; const CSecurityInformation::`vftable'{for `IEffectivePermission2'}
0x18000be59  mov     [rcx+10h], rax
0x18000be5d  lea     rax, ??_7CSecurityInformation@@6BISecurityObjectTypeInfo@@@; const CSecurityInformation::`vftable'{for `ISecurityObjectTypeInfo'}
0x18000be64  mov     [rcx+18h], rax
0x18000be68  lea     rax, ??_7CSecurityInformation@@6BISecurityInformation3@@@; const CSecurityInformation::`vftable'{for `ISecurityInformation3'}
0x18000be6f  mov     [rcx+20h], rax
0x18000be73  lea     rax, ??_7CSecurityInformation@@6BISecurityInformation4@@@; const CSecurityInformation::`vftable'{for `ISecurityInformation4'}
0x18000be7a  mov     [rcx+28h], rax
0x18000be7e  mov     ecx, 1; Flags
0x18000be83  mov     [rbx+34h], edx
0x18000be86  lea     rax, [rbx+60h]
0x18000be8a  xor     edx, edx; pfnDynamicAccessCheck
0x18000be8c  mov     [rbx+30h], ecx
0x18000be8f  mov     [rax], rdx
0x18000be92  mov     [rbx+58h], rdx
0x18000be96  mov     [rbx+68h], edx
0x18000be99  mov     dword ptr [rbx+138h], 0FFFFFFFFh
0x18000bea3  mov     [rbx+38h], rdx
0x18000bea7  mov     [rbx+48h], rdx
0x18000beab  mov     [rbx+50h], rdx
0x18000beaf  lock add cs:?g_cRefThisDll@@3JA, ecx; long g_cRefThisDll
0x18000beb6  mov     [rsp+38h+phAuthzResourceManager], rax; phAuthzResourceManager
0x18000bebb  xor     r9d, r9d; pfnFreeDynamicGroups
0x18000bebe  lea     rax, aDummy; "Dummy"
0x18000bec5  xor     r8d, r8d; pfnComputeDynamicGroups
0x18000bec8  mov     [rsp+38h+szResourceManagerName], rax; szResourceManagerName
0x18000becd  call    cs:__imp_AuthzInitializeResourceManager
0x18000bed3  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000beda  lea     r8, [rbx+6Ch]; lpBuffer
0x18000bede  mov     edx, 2; uID
0x18000bee3  lea     r9d, [rdx+62h]; cchBufferMax
0x18000bee7  call    cs:__imp_LoadStringW
0x18000beed  mov     rax, rbx
0x18000bef0  add     rsp, 30h
0x18000bef4  pop     rbx
0x18000bef5  retn
```
