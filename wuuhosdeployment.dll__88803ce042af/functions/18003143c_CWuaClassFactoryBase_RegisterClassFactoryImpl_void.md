# CWuaClassFactoryBase::RegisterClassFactoryImpl(void)

- ea: `0x18003143c`
- end: `0x180031489`
- name: `?RegisterClassFactoryImpl@CWuaClassFactoryBase@@AEAAJXZ`
- size: `77`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnk)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031078`
- `0x1800312f0`

## callees

- `0x180003950`
- `0x18003143c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18003145c`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18003145c`

## string_xrefs

- `0x18003146d`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x18003143c  push    rbx
0x18003143e  sub     rsp, 30h
0x180031442  lea     rax, [rcx+28h]
0x180031446  mov     r9d, 1; flags
0x18003144c  mov     rdx, rcx; pUnk
0x18003144f  mov     qword ptr [rsp+38h+lpdwRegister], rax; int
0x180031454  add     rcx, 8; rclsid
0x180031458  lea     r8d, [r9+3]; dwClsContext
0x18003145c  call    cs:__imp_CoRegisterClassObject
0x180031462  mov     ebx, eax
0x180031464  test    eax, eax
0x180031466  jns     short loc_180031481
0x180031468  mov     rcx, [rsp+38h]; this
0x18003146d  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180031474  mov     r9d, eax; char *
0x180031477  mov     edx, 1F2h; void *
0x18003147c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031481  mov     eax, ebx
0x180031483  add     rsp, 30h
0x180031487  pop     rbx
0x180031488  retn
```
