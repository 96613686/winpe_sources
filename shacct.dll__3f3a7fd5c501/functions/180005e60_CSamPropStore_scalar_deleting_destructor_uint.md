# CSamPropStore::`scalar deleting destructor'(uint)

- ea: `0x180005e60`
- end: `0x180005f35`
- name: `??_GCSamPropStore@@AEAAPEAXI@Z`
- size: `213`
- prototype: `void *__fastcall(CSamPropStore *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180005e30`

## callees

- `0x180005e60`
- `0x180007300`
- `0x18000bbd0`
- `0x18000c7e0`
- `0x18001066c`
- `0x1800106d0`
- `0x180010744`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f0d`

## pseudocode

```c
CSamPropStore *__fastcall CSamPropStore::`scalar deleting destructor'(CSamPropStore *this)
{
  struct _USER_ALL_INFORMATION *v2; // rcx
  struct _USER_EXTENDED_INFORMATION *v3; // rcx
  struct _ALIAS_GENERAL_INFORMATION *v4; // rcx
  struct _ALIAS_EXTENDED_INFORMATION *v5; // rcx
  void *v6; // rcx
  struct _DPA *v7; // rcx
  __int64 v8; // rcx

  *(_QWORD *)this = &CSamPropStore::`vftable'{for `IPropertyStore'};
  *((_QWORD *)this + 1) = &CSamPropStore::`vftable'{for `IPersistSerializedPropStorage'};
  v2 = (struct _USER_ALL_INFORMATION *)*((_QWORD *)this + 3);
  if ( v2 )
    FreeUserStructure(v2, 1);
  v3 = (struct _USER_EXTENDED_INFORMATION *)*((_QWORD *)this + 4);
  if ( v3 )
    FreeUserExtStructure(v3, 1);
  v4 = (struct _ALIAS_GENERAL_INFORMATION *)*((_QWORD *)this + 5);
  if ( v4 )
    FreeAliasStructure(v4, 1);
  v5 = (struct _ALIAS_EXTENDED_INFORMATION *)*((_QWORD *)this + 6);
  if ( v5 )
    FreeAliasExtStructure(v5, 1);
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 )
    CoTaskMemFree(v6);
  v7 = (struct _DPA *)*((_QWORD *)this + 7);
  if ( v7 )
    g_pfn_DPA_DestroyCallback(
      v7,
      CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::_StandardDestroyCB,
      0);
  v8 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  _InterlockedDecrement(&g_cRefCount);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005e60  push    rbx
0x180005e62  sub     rsp, 20h
0x180005e66  lea     rax, ??_7CSamPropStore@@6BIPropertyStore@@@; const CSamPropStore::`vftable'{for `IPropertyStore'}
0x180005e6d  mov     rbx, rcx
0x180005e70  mov     [rcx], rax
0x180005e73  lea     rax, ??_7CSamPropStore@@6BIPersistSerializedPropStorage@@@; const CSamPropStore::`vftable'{for `IPersistSerializedPropStorage'}
0x180005e7a  mov     [rcx+8], rax
0x180005e7e  mov     rcx, [rcx+18h]; pv
0x180005e82  test    rcx, rcx
0x180005e85  jnz     short loc_180005EDD
0x180005e87  mov     rcx, [rbx+20h]; pv
0x180005e8b  test    rcx, rcx
0x180005e8e  jnz     short loc_180005EE9
0x180005e90  mov     rcx, [rbx+28h]; pv
0x180005e94  test    rcx, rcx
0x180005e97  jnz     short loc_180005EF5
0x180005e99  mov     rcx, [rbx+30h]; pv
0x180005e9d  test    rcx, rcx
0x180005ea0  jnz     short loc_180005F01
0x180005ea2  mov     rcx, [rbx+58h]; pv
0x180005ea6  test    rcx, rcx
0x180005ea9  jnz     short loc_180005F0D
0x180005eab  mov     rcx, [rbx+38h]; hdpa
0x180005eaf  test    rcx, rcx
0x180005eb2  jnz     short loc_180005F15
0x180005eb4  mov     rcx, [rbx+60h]
0x180005eb8  mov     qword ptr [rbx+60h], 0
0x180005ec0  test    rcx, rcx
0x180005ec3  jnz     short loc_180005F27
0x180005ec5  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x180005ecc  mov     rcx, rbx; Block
0x180005ecf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005ed4  mov     rax, rbx
0x180005ed7  add     rsp, 20h
0x180005edb  pop     rbx
0x180005edc  retn
0x180005edd  mov     edx, 1; int
0x180005ee2  call    ?FreeUserStructure@@YAJPEAU_USER_ALL_INFORMATION@@H@Z; FreeUserStructure(_USER_ALL_INFORMATION *,int)
0x180005ee7  jmp     short loc_180005E87
0x180005ee9  mov     edx, 1; int
0x180005eee  call    ?FreeUserExtStructure@@YAJPEAU_USER_EXTENDED_INFORMATION@@H@Z; FreeUserExtStructure(_USER_EXTENDED_INFORMATION *,int)
0x180005ef3  jmp     short loc_180005E90
0x180005ef5  mov     edx, 1; int
0x180005efa  call    ?FreeAliasStructure@@YAJPEAU_ALIAS_GENERAL_INFORMATION@@H@Z; FreeAliasStructure(_ALIAS_GENERAL_INFORMATION *,int)
0x180005eff  jmp     short loc_180005E99
0x180005f01  mov     edx, 1; int
0x180005f06  call    ?FreeAliasExtStructure@@YAJPEAU_ALIAS_EXTENDED_INFORMATION@@H@Z; FreeAliasExtStructure(_ALIAS_EXTENDED_INFORMATION *,int)
0x180005f0b  jmp     short loc_180005EA2
0x180005f0d  call    cs:__imp_CoTaskMemFree
0x180005f13  jmp     short loc_180005EAB
0x180005f15  xor     r8d, r8d; pData
0x180005f18  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@UIPropertyStore@@V?$CTContainer_PolicyRelease@UIPropertyStore@@@@@@CAHPEAUIPropertyStore@@PEAX@Z; pfnCB
0x180005f1f  call    cs:g_pfn_DPA_DestroyCallback
0x180005f25  jmp     short loc_180005EB4
0x180005f27  mov     rax, [rcx]
0x180005f2a  mov     rax, [rax+10h]
0x180005f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f33  jmp     short loc_180005EC5
```
