# CMSSAdmin::InitGatherAdmin(IGatherManagerAdmin3 *)

- ea: `0x1800204fc`
- end: `0x180020556`
- name: `?InitGatherAdmin@CMSSAdmin@@QEAAJPEAUIGatherManagerAdmin3@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(CMSSAdmin *__hidden this, struct IGatherManagerAdmin3 *)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bab4`
- `0x18001020c`
- `0x1800134b0`
- `0x180018730`
- `0x1800205b0`
- `0x180020ee4`
- `0x180025fac`
- `0x1800277ac`

## callees

- `0x1800204fc`
- `0x180020aa8`
- `0x180020e0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020527`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020527`

## pseudocode

```c
__int64 __fastcall CMSSAdmin::InitGatherAdmin(CMSSAdmin *this, struct IGatherManagerAdmin3 *a2)
{
  HRESULT Instance; // ebx

  CMSSAdmin::_ReleaseGatherAdmin(this);
  Instance = CoCreateInstance(
               &GUID_9e175b68_f52a_11d8_b9a5_505054503030,
               0,
               0x15u,
               &GUID_5480f00f_4b80_4deb_ae21_50521db448ed,
               (LPVOID *)this);
  if ( Instance < 0 || (Instance = CMSSAdmin::_GetGatherAdmin(this), Instance < 0) )
    CMSSAdmin::_ReleaseGatherAdmin(this);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800204fc  mov     [rsp+arg_0], rbx
0x180020501  push    rdi
0x180020502  sub     rsp, 30h
0x180020506  mov     rdi, rcx
0x180020509  call    ?_ReleaseGatherAdmin@CMSSAdmin@@AEAAXXZ; CMSSAdmin::_ReleaseGatherAdmin(void)
0x18002050e  xor     edx, edx; pUnkOuter
0x180020510  mov     [rsp+38h+ppv], rdi; ppv
0x180020515  lea     r9, _GUID_5480f00f_4b80_4deb_ae21_50521db448ed; riid
0x18002051c  lea     rcx, _GUID_9e175b68_f52a_11d8_b9a5_505054503030; rclsid
0x180020523  lea     r8d, [rdx+15h]; dwClsContext
0x180020527  call    cs:__imp_CoCreateInstance
0x18002052d  mov     ebx, eax
0x18002052f  test    eax, eax
0x180020531  js      short loc_180020541
0x180020533  mov     rcx, rdi; this
0x180020536  call    ?_GetGatherAdmin@CMSSAdmin@@AEAAJXZ; CMSSAdmin::_GetGatherAdmin(void)
0x18002053b  mov     ebx, eax
0x18002053d  test    eax, eax
0x18002053f  jns     short loc_180020549
0x180020541  mov     rcx, rdi; this
0x180020544  call    ?_ReleaseGatherAdmin@CMSSAdmin@@AEAAXXZ; CMSSAdmin::_ReleaseGatherAdmin(void)
0x180020549  mov     eax, ebx
0x18002054b  mov     rbx, [rsp+38h+arg_0]
0x180020550  add     rsp, 30h
0x180020554  pop     rdi
0x180020555  retn
```
