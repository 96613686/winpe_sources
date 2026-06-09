# CSecurityInformation::~CSecurityInformation(void)

- ea: `0x18000befc`
- end: `0x18000bf78`
- name: `??1CSecurityInformation@@UEAA@XZ`
- size: `124`
- prototype: `void __fastcall(CSecurityInformation *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006284`
- `0x180008d50`

## callees

- `0x1800165e4`

## import_xrefs

- `AUTHZ!AuthzFreeResourceManager` at `0x18000bf65`
- `AUTHZ!AuthzFreeResourceManager` at `0x18000bf65`

## pseudocode

```c
void __fastcall CSecurityInformation::~CSecurityInformation(CSecurityInformation *this)
{
  *(_QWORD *)this = &CSecurityInformation::`vftable'{for `ISecurityInformation'};
  *((_QWORD *)this + 1) = &CSecurityInformation::`vftable'{for `IEffectivePermission'};
  *((_QWORD *)this + 2) = &CSecurityInformation::`vftable'{for `IEffectivePermission2'};
  *((_QWORD *)this + 3) = &CSecurityInformation::`vftable'{for `ISecurityObjectTypeInfo'};
  *((_QWORD *)this + 4) = &CSecurityInformation::`vftable'{for `ISecurityInformation3'};
  *((_QWORD *)this + 5) = &CSecurityInformation::`vftable'{for `ISecurityInformation4'};
  LocalFreeString((unsigned __int16 **)this + 7);
  LocalFreeString((unsigned __int16 **)this + 10);
  LocalFreeString((unsigned __int16 **)this + 9);
  AuthzFreeResourceManager(*((AUTHZ_RESOURCE_MANAGER_HANDLE *)this + 12));
  _InterlockedDecrement(&g_cRefThisDll);
}

```

## disassembly

```asm
0x18000befc  push    rbx
0x18000befe  sub     rsp, 20h
0x18000bf02  lea     rax, ??_7CSecurityInformation@@6BISecurityInformation@@@; const CSecurityInformation::`vftable'{for `ISecurityInformation'}
0x18000bf09  mov     rbx, rcx
0x18000bf0c  mov     [rcx], rax
0x18000bf0f  lea     rax, ??_7CSecurityInformation@@6BIEffectivePermission@@@; const CSecurityInformation::`vftable'{for `IEffectivePermission'}
0x18000bf16  mov     [rcx+8], rax
0x18000bf1a  lea     rax, ??_7CSecurityInformation@@6BIEffectivePermission2@@@; const CSecurityInformation::`vftable'{for `IEffectivePermission2'}
0x18000bf21  mov     [rcx+10h], rax
0x18000bf25  lea     rax, ??_7CSecurityInformation@@6BISecurityObjectTypeInfo@@@; const CSecurityInformation::`vftable'{for `ISecurityObjectTypeInfo'}
0x18000bf2c  mov     [rcx+18h], rax
0x18000bf30  lea     rax, ??_7CSecurityInformation@@6BISecurityInformation3@@@; const CSecurityInformation::`vftable'{for `ISecurityInformation3'}
0x18000bf37  mov     [rcx+20h], rax
0x18000bf3b  lea     rax, ??_7CSecurityInformation@@6BISecurityInformation4@@@; const CSecurityInformation::`vftable'{for `ISecurityInformation4'}
0x18000bf42  mov     [rcx+28h], rax
0x18000bf46  add     rcx, 38h ; '8'; unsigned __int16 **
0x18000bf4a  call    ?LocalFreeString@@YAXPEAPEAG@Z; LocalFreeString(ushort * *)
0x18000bf4f  lea     rcx, [rbx+50h]; unsigned __int16 **
0x18000bf53  call    ?LocalFreeString@@YAXPEAPEAG@Z; LocalFreeString(ushort * *)
0x18000bf58  lea     rcx, [rbx+48h]; unsigned __int16 **
0x18000bf5c  call    ?LocalFreeString@@YAXPEAPEAG@Z; LocalFreeString(ushort * *)
0x18000bf61  mov     rcx, [rbx+60h]; hAuthzResourceManager
0x18000bf65  call    cs:__imp_AuthzFreeResourceManager
0x18000bf6b  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000bf72  add     rsp, 20h
0x18000bf76  pop     rbx
0x18000bf77  retn
```
