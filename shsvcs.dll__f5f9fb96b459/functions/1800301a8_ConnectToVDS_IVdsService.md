# ConnectToVDS(IVdsService * *)

- ea: `0x1800301a8`
- end: `0x180030254`
- name: `?ConnectToVDS@@YAJPEAPEAUIVdsService@@@Z`
- size: `172`
- prototype: `__int64 __fastcall(struct IVdsService **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002fcc0`

## callees

- `0x1800301a8`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800301e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800301e4`

## pseudocode

```c
__int64 __fastcall ConnectToVDS(struct IVdsService **a1)
{
  HRESULT v2; // ebx
  LPVOID v4; // [rsp+40h] [rbp+8h] BYREF
  struct IVdsService *v5; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v4 = 0;
  v2 = CoCreateInstance(&CLSID_VdsLoader, 0, 0x10004u, &GUID_e0393303_90d4_4a97_ab71_e9b671ee2729, &v4);
  if ( v2 >= 0 )
  {
    v5 = 0;
    v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IVdsService **))(*(_QWORD *)v4 + 24LL))(v4, 0, &v5);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v2 >= 0 )
    {
      v2 = ((__int64 (__fastcall *)(struct IVdsService *))v5->lpVtbl->WaitForServiceReady)(v5);
      if ( v2 >= 0 )
        *a1 = v5;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800301a8  mov     r11, rsp
0x1800301ab  mov     [r11+18h], rbx
0x1800301af  push    rdi
0x1800301b0  sub     rsp, 30h
0x1800301b4  mov     rdi, rcx
0x1800301b7  mov     qword ptr [rcx], 0
0x1800301be  lea     rax, [r11+8]
0x1800301c2  mov     qword ptr [r11+8], 0
0x1800301ca  lea     rcx, CLSID_VdsLoader; rclsid
0x1800301d1  mov     [r11-18h], rax
0x1800301d5  lea     r9, _GUID_e0393303_90d4_4a97_ab71_e9b671ee2729; riid
0x1800301dc  xor     edx, edx; pUnkOuter
0x1800301de  mov     r8d, 10004h; dwClsContext
0x1800301e4  call    cs:__imp_CoCreateInstance
0x1800301ea  mov     ebx, eax
0x1800301ec  test    eax, eax
0x1800301ee  js      short loc_180030247
0x1800301f0  mov     rcx, [rsp+38h+arg_0]
0x1800301f5  lea     r8, [rsp+38h+arg_8]
0x1800301fa  mov     [rsp+38h+arg_8], 0
0x180030203  xor     edx, edx
0x180030205  mov     rax, [rcx]
0x180030208  mov     rax, [rax+18h]
0x18003020c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030211  mov     rcx, [rsp+38h+arg_0]
0x180030216  mov     ebx, eax
0x180030218  mov     rax, [rcx]
0x18003021b  mov     rax, [rax+10h]
0x18003021f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030224  test    ebx, ebx
0x180030226  js      short loc_180030247
0x180030228  mov     rcx, [rsp+38h+arg_8]
0x18003022d  mov     rax, [rcx]
0x180030230  mov     rax, [rax+20h]
0x180030234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030239  mov     ebx, eax
0x18003023b  test    eax, eax
0x18003023d  js      short loc_180030247
0x18003023f  mov     rax, [rsp+38h+arg_8]
0x180030244  mov     [rdi], rax
0x180030247  mov     eax, ebx
0x180030249  mov     rbx, [rsp+38h+arg_10]
0x18003024e  add     rsp, 30h
0x180030252  pop     rdi
0x180030253  retn
```
