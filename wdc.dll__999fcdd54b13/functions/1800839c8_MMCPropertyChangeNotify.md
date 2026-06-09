# MMCPropertyChangeNotify

- ea: `0x1800839c8`
- end: `0x180083a5e`
- name: `MMCPropertyChangeNotify`
- size: `150`
- prototype: `HRESULT __stdcall(LONG_PTR lNotifyHandle, LPARAM param)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034430`

## callees

- `0x1800839c8`
- `0x180086010`

## import_xrefs

- `ole32!CoUninitialize` at `0x180083a46`
- `ole32!CoUninitialize` at `0x180083a46`
- `ole32!CoInitialize` at `0x1800839df`
- `ole32!CoInitialize` at `0x1800839df`
- `ole32!CoCreateInstance` at `0x180083a12`
- `ole32!CoCreateInstance` at `0x180083a12`

## pseudocode

```c
HRESULT __stdcall MMCPropertyChangeNotify(LONG_PTR lNotifyHandle, LPARAM param)
{
  int v4; // ebx
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  v4 = CoInitialize(0);
  if ( v4 >= 0 )
  {
    ppv = 0;
    v4 = CoCreateInstance(&CLSID_NodeManager, 0, 3u, &IID_IPropertySheetNotify, &ppv);
    if ( v4 >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, LONG_PTR, LPARAM))(*(_QWORD *)ppv + 24LL))(ppv, lNotifyHandle, param);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
  return v4;
}

```

## disassembly

```asm
0x1800839c8  mov     [rsp+arg_0], rbx
0x1800839cd  mov     [rsp+arg_8], rsi
0x1800839d2  push    rdi
0x1800839d3  sub     rsp, 30h
0x1800839d7  mov     rsi, rcx
0x1800839da  mov     rdi, rdx
0x1800839dd  xor     ecx, ecx; pvReserved
0x1800839df  call    cs:__imp_CoInitialize
0x1800839e5  mov     ebx, eax
0x1800839e7  test    eax, eax
0x1800839e9  js      short loc_180083A4C
0x1800839eb  xor     edx, edx; pUnkOuter
0x1800839ed  mov     [rsp+38h+arg_10], 0
0x1800839f6  lea     rax, [rsp+38h+arg_10]
0x1800839fb  lea     r9, IID_IPropertySheetNotify; riid
0x180083a02  mov     [rsp+38h+ppv], rax; ppv
0x180083a07  lea     rcx, CLSID_NodeManager; rclsid
0x180083a0e  lea     r8d, [rdx+3]; dwClsContext
0x180083a12  call    cs:__imp_CoCreateInstance
0x180083a18  mov     ebx, eax
0x180083a1a  test    eax, eax
0x180083a1c  js      short loc_180083A46
0x180083a1e  mov     rcx, [rsp+38h+arg_10]
0x180083a23  mov     r8, rdi
0x180083a26  mov     rdx, rsi
0x180083a29  mov     rax, [rcx]
0x180083a2c  mov     rax, [rax+18h]
0x180083a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a35  mov     rcx, [rsp+38h+arg_10]
0x180083a3a  mov     rax, [rcx]
0x180083a3d  mov     rax, [rax+10h]
0x180083a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a46  call    cs:__imp_CoUninitialize
0x180083a4c  mov     rsi, [rsp+38h+arg_8]
0x180083a51  mov     eax, ebx
0x180083a53  mov     rbx, [rsp+38h+arg_0]
0x180083a58  add     rsp, 30h
0x180083a5c  pop     rdi
0x180083a5d  retn
```
