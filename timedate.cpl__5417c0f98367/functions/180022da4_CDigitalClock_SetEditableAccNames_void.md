# CDigitalClock::_SetEditableAccNames(void)

- ea: `0x180022da4`
- end: `0x180022e78`
- name: `?_SetEditableAccNames@CDigitalClock@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(CDigitalClock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800214a4`

## callees

- `0x180020a28`
- `0x180022da4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022de9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022de9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180022db4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180022db4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022e6c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022e6c`

## pseudocode

```c
void __fastcall CDigitalClock::_SetEditableAccNames(CDigitalClock *this)
{
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_AccPropServices, 0, 0x15u, &IID_IAccPropServices, &ppv) >= 0 )
    {
      if ( CDigitalClock::s_accNames )
        SetAccessibilityNamePropFromResourceId(ppv, *((_QWORD *)this + 3));
      if ( dword_18003AA04 )
        SetAccessibilityNamePropFromResourceId(ppv, *((_QWORD *)this + 4));
      if ( dword_18003AA08 )
        SetAccessibilityNamePropFromResourceId(ppv, *((_QWORD *)this + 5));
      if ( dword_18003AA0C )
        SetAccessibilityNamePropFromResourceId(ppv, *((_QWORD *)this + 8));
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x180022da4  push    rbx
0x180022da6  sub     rsp, 30h
0x180022daa  mov     rbx, rcx
0x180022dad  mov     edx, 2; dwCoInit
0x180022db2  xor     ecx, ecx; pvReserved
0x180022db4  call    cs:__imp_CoInitializeEx
0x180022dba  test    eax, eax
0x180022dbc  js      loc_180022E72
0x180022dc2  xor     edx, edx; pUnkOuter
0x180022dc4  mov     [rsp+38h+arg_8], 0
0x180022dcd  lea     rax, [rsp+38h+arg_8]
0x180022dd2  lea     r9, IID_IAccPropServices; riid
0x180022dd9  mov     [rsp+38h+ppv], rax; ppv
0x180022dde  lea     rcx, CLSID_AccPropServices; rclsid
0x180022de5  lea     r8d, [rdx+15h]; dwClsContext
0x180022de9  call    cs:__imp_CoCreateInstance
0x180022def  test    eax, eax
0x180022df1  js      short loc_180022E6C
0x180022df3  mov     r8d, cs:?s_accNames@CDigitalClock@@2UCLOCK_ACC_NAME_PROPS@@A; CLOCK_ACC_NAME_PROPS CDigitalClock::s_accNames
0x180022dfa  test    r8d, r8d
0x180022dfd  jz      short loc_180022E0D
0x180022dff  mov     rdx, [rbx+18h]
0x180022e03  mov     rcx, [rsp+38h+arg_8]
0x180022e08  call    SetAccessibilityNamePropFromResourceId
0x180022e0d  mov     r8d, cs:dword_18003AA04
0x180022e14  test    r8d, r8d
0x180022e17  jz      short loc_180022E27
0x180022e19  mov     rdx, [rbx+20h]
0x180022e1d  mov     rcx, [rsp+38h+arg_8]
0x180022e22  call    SetAccessibilityNamePropFromResourceId
0x180022e27  mov     r8d, cs:dword_18003AA08
0x180022e2e  test    r8d, r8d
0x180022e31  jz      short loc_180022E41
0x180022e33  mov     rdx, [rbx+28h]
0x180022e37  mov     rcx, [rsp+38h+arg_8]
0x180022e3c  call    SetAccessibilityNamePropFromResourceId
0x180022e41  mov     r8d, cs:dword_18003AA0C
0x180022e48  test    r8d, r8d
0x180022e4b  jz      short loc_180022E5B
0x180022e4d  mov     rdx, [rbx+40h]
0x180022e51  mov     rcx, [rsp+38h+arg_8]
0x180022e56  call    SetAccessibilityNamePropFromResourceId
0x180022e5b  mov     rcx, [rsp+38h+arg_8]
0x180022e60  mov     rax, [rcx]
0x180022e63  mov     rax, [rax+10h]
0x180022e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e6c  call    cs:__imp_CoUninitialize
0x180022e72  add     rsp, 30h
0x180022e76  pop     rbx
0x180022e77  retn
```
