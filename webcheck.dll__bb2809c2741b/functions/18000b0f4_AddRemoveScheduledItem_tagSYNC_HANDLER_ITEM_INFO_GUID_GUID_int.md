# AddRemoveScheduledItem(_tagSYNC_HANDLER_ITEM_INFO *,_GUID *,_GUID *,int)

- ea: `0x18000b0f4`
- end: `0x18000b200`
- name: `?AddRemoveScheduledItem@@YAJPEAU_tagSYNC_HANDLER_ITEM_INFO@@PEAU_GUID@@1H@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct _tagSYNC_HANDLER_ITEM_INFO *, struct _GUID *, struct _GUID *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000afb4`
- `0x18000d63c`
- `0x180013490`

## callees

- `0x18000b0f4`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000b144`
- `ole32!CoCreateInstance` at `0x18000b144`
- `ole32!CoUninitialize` at `0x18000b1ed`
- `ole32!CoUninitialize` at `0x18000b1ed`
- `ole32!CoInitialize` at `0x18000b116`
- `ole32!CoInitialize` at `0x18000b116`

## pseudocode

```c
__int64 __fastcall AddRemoveScheduledItem(
        struct _tagSYNC_HANDLER_ITEM_INFO *a1,
        struct _GUID *a2,
        struct _GUID *a3,
        int a4)
{
  HRESULT v8; // ebx
  __int64 v9; // rax
  __int64 *v11; // [rsp+30h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-30h] BYREF

  ppv = 0;
  v8 = CoInitialize(0);
  if ( v8 >= 0 )
  {
    v8 = CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv);
    if ( v8 >= 0 )
    {
      v11 = 0;
      v8 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *, _QWORD, __int64 **))(*(_QWORD *)ppv + 40LL))(
             ppv,
             a3,
             0,
             &v11);
      if ( v8 >= 0 )
      {
        v9 = *v11;
        if ( a4 )
          (*(void (__fastcall **)(__int64 *, struct _tagSYNC_HANDLER_ITEM_INFO *))(v9 + 128))(v11, a1);
        else
          (*(void (__fastcall **)(__int64 *, GUID *, struct _GUID *, _QWORD))(v9 + 136))(
            v11,
            &CLSID_WebCheckOfflineSync,
            a2,
            0);
        v8 = (*(__int64 (__fastcall **)(__int64 *))(*v11 + 160))(v11);
        (*(void (__fastcall **)(__int64 *))(*v11 + 16))(v11);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b0f4  push    rbx
0x18000b0f6  push    rbp
0x18000b0f7  push    rsi
0x18000b0f8  push    rdi
0x18000b0f9  push    r14
0x18000b0fb  sub     rsp, 40h
0x18000b0ff  mov     rsi, rcx
0x18000b102  mov     [rsp+68h+var_30], 0
0x18000b10b  xor     ecx, ecx; pvReserved
0x18000b10d  mov     edi, r9d
0x18000b110  mov     r14, r8
0x18000b113  mov     rbp, rdx
0x18000b116  call    cs:__imp_CoInitialize
0x18000b11c  mov     ebx, eax
0x18000b11e  test    eax, eax
0x18000b120  js      loc_18000B1F3
0x18000b126  xor     edx, edx; pUnkOuter
0x18000b128  lea     rax, [rsp+68h+var_30]
0x18000b12d  lea     r9, IID_ISyncScheduleMgr; riid
0x18000b134  mov     [rsp+68h+ppv], rax; ppv
0x18000b139  lea     rcx, CLSID_SyncMgr; rclsid
0x18000b140  lea     r8d, [rdx+17h]; dwClsContext
0x18000b144  call    cs:__imp_CoCreateInstance
0x18000b14a  mov     ebx, eax
0x18000b14c  test    eax, eax
0x18000b14e  js      loc_18000B1ED
0x18000b154  mov     rcx, [rsp+68h+var_30]
0x18000b159  lea     r9, [rsp+68h+var_38]
0x18000b15e  mov     [rsp+68h+var_38], 0
0x18000b167  xor     r8d, r8d
0x18000b16a  mov     rdx, r14
0x18000b16d  mov     rax, [rcx]
0x18000b170  mov     rax, [rax+28h]
0x18000b174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b179  mov     ebx, eax
0x18000b17b  test    eax, eax
0x18000b17d  js      short loc_18000B1DC
0x18000b17f  mov     rcx, [rsp+68h+var_38]
0x18000b184  mov     rax, [rcx]
0x18000b187  test    edi, edi
0x18000b189  jz      short loc_18000B19C
0x18000b18b  mov     rax, [rax+80h]
0x18000b192  mov     rdx, rsi
0x18000b195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b19a  jmp     short loc_18000B1B5
0x18000b19c  mov     rax, [rax+88h]
0x18000b1a3  lea     rdx, CLSID_WebCheckOfflineSync
0x18000b1aa  xor     r9d, r9d
0x18000b1ad  mov     r8, rbp
0x18000b1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1b5  mov     rcx, [rsp+68h+var_38]
0x18000b1ba  mov     rax, [rcx]
0x18000b1bd  mov     rax, [rax+0A0h]
0x18000b1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1c9  mov     rcx, [rsp+68h+var_38]
0x18000b1ce  mov     ebx, eax
0x18000b1d0  mov     rax, [rcx]
0x18000b1d3  mov     rax, [rax+10h]
0x18000b1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1dc  mov     rcx, [rsp+68h+var_30]
0x18000b1e1  mov     rax, [rcx]
0x18000b1e4  mov     rax, [rax+10h]
0x18000b1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1ed  call    cs:__imp_CoUninitialize
0x18000b1f3  mov     eax, ebx
0x18000b1f5  add     rsp, 40h
0x18000b1f9  pop     r14
0x18000b1fb  pop     rdi
0x18000b1fc  pop     rsi
0x18000b1fd  pop     rbp
0x18000b1fe  pop     rbx
0x18000b1ff  retn
```
