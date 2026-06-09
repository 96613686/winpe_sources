# CNTFSSecurity::~CNTFSSecurity(void)

- ea: `0x180006284`
- end: `0x18000634b`
- name: `??1CNTFSSecurity@@UEAA@XZ`
- size: `199`
- prototype: `void __fastcall(CNTFSSecurity *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005e28`
- `0x180006360`

## callees

- `0x180006284`
- `0x18000befc`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000630e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000630e`
- `AUTHZ!AuthzFreeResourceManager` at `0x180006338`
- `AUTHZ!AuthzFreeResourceManager` at `0x180006338`

## pseudocode

```c
void __fastcall CNTFSSecurity::~CNTFSSecurity(CNTFSSecurity *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  AUTHZ_RESOURCE_MANAGER_HANDLE v4; // rcx

  *(_QWORD *)this = &CNTFSSecurity::`vftable'{for `ISecurityInformation'};
  *((_QWORD *)this + 1) = &CSecurityInformation::`vftable'{for `IEffectivePermission'};
  *((_QWORD *)this + 2) = &CFSSecurity::`vftable'{for `IEffectivePermission2'};
  *((_QWORD *)this + 3) = &CNTFSSecurity::`vftable'{for `ISecurityObjectTypeInfo'};
  *((_QWORD *)this + 4) = &CFSSecurity::`vftable'{for `ISecurityInformation3'};
  *((_QWORD *)this + 5) = &CNTFSSecurity::`vftable'{for `ISecurityInformation4'};
  LocalFree(*((HLOCAL *)this + 44));
  LocalFree(*((HLOCAL *)this + 45));
  LocalFree(*((HLOCAL *)this + 46));
  LocalFree(*((HLOCAL *)this + 47));
  v2 = (void *)*((_QWORD *)this + 49);
  if ( v2 )
    CloseHandle(v2);
  v3 = *((_QWORD *)this + 50);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (AUTHZ_RESOURCE_MANAGER_HANDLE)*((_QWORD *)this + 52);
  if ( v4 )
    AuthzFreeResourceManager(v4);
  CSecurityInformation::~CSecurityInformation(this);
}

```

## disassembly

```asm
0x180006284  push    rbx
0x180006286  sub     rsp, 20h
0x18000628a  lea     rax, ??_7CNTFSSecurity@@6BISecurityInformation@@@; const CNTFSSecurity::`vftable'{for `ISecurityInformation'}
0x180006291  mov     rbx, rcx
0x180006294  mov     [rcx], rax
0x180006297  lea     rax, ??_7CSecurityInformation@@6BIEffectivePermission@@@; const CSecurityInformation::`vftable'{for `IEffectivePermission'}
0x18000629e  mov     [rcx+8], rax
0x1800062a2  lea     rax, ??_7CFSSecurity@@6BIEffectivePermission2@@@; const CFSSecurity::`vftable'{for `IEffectivePermission2'}
0x1800062a9  mov     [rcx+10h], rax
0x1800062ad  lea     rax, ??_7CNTFSSecurity@@6BISecurityObjectTypeInfo@@@; const CNTFSSecurity::`vftable'{for `ISecurityObjectTypeInfo'}
0x1800062b4  mov     [rcx+18h], rax
0x1800062b8  lea     rax, ??_7CFSSecurity@@6BISecurityInformation3@@@; const CFSSecurity::`vftable'{for `ISecurityInformation3'}
0x1800062bf  mov     [rcx+20h], rax
0x1800062c3  lea     rax, ??_7CNTFSSecurity@@6BISecurityInformation4@@@; const CNTFSSecurity::`vftable'{for `ISecurityInformation4'}
0x1800062ca  mov     [rcx+28h], rax
0x1800062ce  mov     rcx, [rcx+160h]; hMem
0x1800062d5  call    cs:__imp_LocalFree
0x1800062db  mov     rcx, [rbx+168h]; hMem
0x1800062e2  call    cs:__imp_LocalFree
0x1800062e8  mov     rcx, [rbx+170h]; hMem
0x1800062ef  call    cs:__imp_LocalFree
0x1800062f5  mov     rcx, [rbx+178h]; hMem
0x1800062fc  call    cs:__imp_LocalFree
0x180006302  mov     rcx, [rbx+188h]; hObject
0x180006309  test    rcx, rcx
0x18000630c  jz      short loc_180006314
0x18000630e  call    cs:__imp_CloseHandle
0x180006314  mov     rcx, [rbx+190h]
0x18000631b  test    rcx, rcx
0x18000631e  jz      short loc_18000632C
0x180006320  mov     rax, [rcx]
0x180006323  mov     rax, [rax+10h]
0x180006327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000632c  mov     rcx, [rbx+1A0h]; hAuthzResourceManager
0x180006333  test    rcx, rcx
0x180006336  jz      short loc_18000633E
0x180006338  call    cs:__imp_AuthzFreeResourceManager
0x18000633e  mov     rcx, rbx; this
0x180006341  add     rsp, 20h
0x180006345  pop     rbx
0x180006346  jmp     ??1CSecurityInformation@@UEAA@XZ; CSecurityInformation::~CSecurityInformation(void)
```
