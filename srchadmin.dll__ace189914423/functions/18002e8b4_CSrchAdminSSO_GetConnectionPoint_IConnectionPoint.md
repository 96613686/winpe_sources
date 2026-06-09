# CSrchAdminSSO::_GetConnectionPoint(IConnectionPoint * *)

- ea: `0x18002e8b4`
- end: `0x18002e939`
- name: `?_GetConnectionPoint@CSrchAdminSSO@@AEAAJPEAPEAUIConnectionPoint@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(CSrchAdminSSO *__hidden this, struct IConnectionPoint **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ebc8`
- `0x18002ee5c`

## callees

- `0x18002e8b4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e8f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e8f2`

## pseudocode

```c
__int64 __fastcall CSrchAdminSSO::_GetConnectionPoint(CSrchAdminSSO *this, struct IConnectionPoint **a2)
{
  HRESULT v3; // ebx
  LPVOID v5; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  v5 = 0;
  v3 = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 1u, &GUID_b196b284_bab4_101a_b69c_00aa00341d07, &v5);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, GUID *, struct IConnectionPoint **))(*(_QWORD *)v5 + 32LL))(
           v5,
           &IID_IOfflineFilesEvents,
           a2);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002e8b4  mov     r11, rsp
0x18002e8b7  mov     [r11+10h], rbx
0x18002e8bb  mov     [r11+8], rcx
0x18002e8bf  push    rdi
0x18002e8c0  sub     rsp, 30h
0x18002e8c4  mov     rdi, rdx
0x18002e8c7  mov     qword ptr [rdx], 0
0x18002e8ce  xor     edx, edx; pUnkOuter
0x18002e8d0  mov     qword ptr [r11+8], 0
0x18002e8d8  lea     rax, [r11+8]
0x18002e8dc  lea     r9, _GUID_b196b284_bab4_101a_b69c_00aa00341d07; riid
0x18002e8e3  mov     [r11-18h], rax
0x18002e8e7  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x18002e8ee  lea     r8d, [rdx+1]; dwClsContext
0x18002e8f2  call    cs:__imp_CoCreateInstance
0x18002e8f8  mov     ebx, eax
0x18002e8fa  test    eax, eax
0x18002e8fc  js      short loc_18002E92C
0x18002e8fe  mov     rcx, [rsp+38h+arg_0]
0x18002e903  lea     rdx, IID_IOfflineFilesEvents
0x18002e90a  mov     r8, rdi
0x18002e90d  mov     rax, [rcx]
0x18002e910  mov     rax, [rax+20h]
0x18002e914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e919  mov     rcx, [rsp+38h+arg_0]
0x18002e91e  mov     ebx, eax
0x18002e920  mov     rax, [rcx]
0x18002e923  mov     rax, [rax+10h]
0x18002e927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e92c  mov     eax, ebx
0x18002e92e  mov     rbx, [rsp+38h+arg_8]
0x18002e933  add     rsp, 30h
0x18002e937  pop     rdi
0x18002e938  retn
```
