# ScheduleCookieExists(_GUID *)

- ea: `0x18000d580`
- end: `0x18000d633`
- name: `?ScheduleCookieExists@@YAHPEAU_GUID@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b208`

## callees

- `0x18000d580`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000d5c2`
- `ole32!CoCreateInstance` at `0x18000d5c2`
- `ole32!CoUninitialize` at `0x18000d61b`
- `ole32!CoUninitialize` at `0x18000d61b`
- `ole32!CoInitialize` at `0x18000d598`
- `ole32!CoInitialize` at `0x18000d598`

## pseudocode

```c
_BOOL8 __fastcall ScheduleCookieExists(struct _GUID *a1)
{
  HRESULT v2; // ebx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF

  ppv = 0;
  v2 = CoInitialize(0);
  if ( v2 >= 0 )
  {
    v2 = CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv);
    if ( v2 >= 0 )
    {
      v5 = 0;
      v2 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(
             ppv,
             a1,
             0,
             &v5);
      if ( v2 >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
  return v2 == 0;
}

```

## disassembly

```asm
0x18000d580  mov     [rsp+arg_0], rbx
0x18000d585  push    rdi
0x18000d586  sub     rsp, 30h
0x18000d58a  mov     rdi, rcx
0x18000d58d  mov     [rsp+38h+arg_8], 0
0x18000d596  xor     ecx, ecx; pvReserved
0x18000d598  call    cs:__imp_CoInitialize
0x18000d59e  mov     ebx, eax
0x18000d5a0  test    eax, eax
0x18000d5a2  js      short loc_18000D621
0x18000d5a4  xor     edx, edx; pUnkOuter
0x18000d5a6  lea     rax, [rsp+38h+arg_8]
0x18000d5ab  lea     r9, IID_ISyncScheduleMgr; riid
0x18000d5b2  mov     [rsp+38h+ppv], rax; ppv
0x18000d5b7  lea     rcx, CLSID_SyncMgr; rclsid
0x18000d5be  lea     r8d, [rdx+17h]; dwClsContext
0x18000d5c2  call    cs:__imp_CoCreateInstance
0x18000d5c8  mov     ebx, eax
0x18000d5ca  test    eax, eax
0x18000d5cc  js      short loc_18000D61B
0x18000d5ce  mov     rcx, [rsp+38h+arg_8]
0x18000d5d3  lea     r9, [rsp+38h+arg_10]
0x18000d5d8  mov     [rsp+38h+arg_10], 0
0x18000d5e1  xor     r8d, r8d
0x18000d5e4  mov     rdx, rdi
0x18000d5e7  mov     rax, [rcx]
0x18000d5ea  mov     rax, [rax+28h]
0x18000d5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5f3  mov     ebx, eax
0x18000d5f5  test    eax, eax
0x18000d5f7  js      short loc_18000D60A
0x18000d5f9  mov     rcx, [rsp+38h+arg_10]
0x18000d5fe  mov     rax, [rcx]
0x18000d601  mov     rax, [rax+10h]
0x18000d605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d60a  mov     rcx, [rsp+38h+arg_8]
0x18000d60f  mov     rax, [rcx]
0x18000d612  mov     rax, [rax+10h]
0x18000d616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d61b  call    cs:__imp_CoUninitialize
0x18000d621  xor     eax, eax
0x18000d623  test    ebx, ebx
0x18000d625  mov     rbx, [rsp+38h+arg_0]
0x18000d62a  setz    al
0x18000d62d  add     rsp, 30h
0x18000d631  pop     rdi
0x18000d632  retn
```
