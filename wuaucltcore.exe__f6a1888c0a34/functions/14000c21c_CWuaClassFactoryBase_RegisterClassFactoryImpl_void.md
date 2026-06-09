# CWuaClassFactoryBase::RegisterClassFactoryImpl(void)

- ea: `0x14000c21c`
- end: `0x14000c269`
- name: `?RegisterClassFactoryImpl@CWuaClassFactoryBase@@AEAAJXZ`
- size: `77`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnk)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000bf4c`
- `0x14000c0d0`

## callees

- `0x140002ac0`
- `0x14000c21c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000c23c`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000c23c`

## string_xrefs

- `0x14000c24d`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
__int64 __fastcall CWuaClassFactoryBase::RegisterClassFactoryImpl(LPUNKNOWN pUnk)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  int lpdwRegister; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = CoRegisterClassObject((const IID *const)&pUnk[1], pUnk, 4u, 1u, (LPDWORD)&pUnk[5]);
  v2 = v1;
  if ( v1 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)(unsigned int)v1,
      lpdwRegister);
  return v2;
}

```

## disassembly

```asm
0x14000c21c  push    rbx
0x14000c21e  sub     rsp, 30h
0x14000c222  lea     rax, [rcx+28h]
0x14000c226  mov     r9d, 1; flags
0x14000c22c  mov     rdx, rcx; pUnk
0x14000c22f  mov     qword ptr [rsp+38h+lpdwRegister], rax; int
0x14000c234  add     rcx, 8; rclsid
0x14000c238  lea     r8d, [r9+3]; dwClsContext
0x14000c23c  call    cs:__imp_CoRegisterClassObject
0x14000c242  mov     ebx, eax
0x14000c244  test    eax, eax
0x14000c246  jns     short loc_14000C261
0x14000c248  mov     rcx, [rsp+38h]; this
0x14000c24d  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c254  mov     r9d, eax; char *
0x14000c257  mov     edx, 1F2h; void *
0x14000c25c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c261  mov     eax, ebx
0x14000c263  add     rsp, 30h
0x14000c267  pop     rbx
0x14000c268  retn
```
