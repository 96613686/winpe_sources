# CWuaClassFactoryBase::UnregisterClassFactoryImpl(void)

- ea: `0x14000c270`
- end: `0x14000c2e9`
- name: `?UnregisterClassFactoryImpl@CWuaClassFactoryBase@@AEAAJXZ`
- size: `121`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnk)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c160`
- `0x140011d2c`

## callees

- `0x140002ac0`
- `0x14000b1f4`
- `0x14000c270`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x14000c2b9`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x14000c2b9`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x14000c284`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x14000c284`

## string_xrefs

- `0x14000c295`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x14000c2c8`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
__int64 __fastcall CWuaClassFactoryBase::UnregisterClassFactoryImpl(LPUNKNOWN pUnk)
{
  DWORD lpVtbl; // ecx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  HRESULT v6; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  lpVtbl = (DWORD)pUnk[5].lpVtbl;
  if ( lpVtbl )
  {
    v3 = CoRevokeClassObject(lpVtbl);
    v4 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
        (const char *)(unsigned int)v3,
        v7);
      return v4;
    }
    LODWORD(pUnk[5].lpVtbl) = 0;
    v6 = CoDisconnectObject(pUnk, 0);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1FF,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
        (const char *)(unsigned int)v6,
        v7);
  }
  return 0;
}

```

## disassembly

```asm
0x14000c270  mov     [rsp+arg_0], rbx
0x14000c275  push    rdi; int
0x14000c276  sub     rsp, 20h
0x14000c27a  mov     rdi, rcx
0x14000c27d  mov     ecx, [rcx+28h]; dwRegister
0x14000c280  test    ecx, ecx
0x14000c282  jz      short loc_14000C2DC
0x14000c284  call    cs:__imp_CoRevokeClassObject
0x14000c28a  mov     ebx, eax
0x14000c28c  test    eax, eax
0x14000c28e  jns     short loc_14000C2AD
0x14000c290  mov     rcx, [rsp+28h]; this
0x14000c295  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c29c  mov     r9d, eax; char *
0x14000c29f  mov     edx, 1FBh; void *
0x14000c2a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c2a9  mov     eax, ebx
0x14000c2ab  jmp     short loc_14000C2DE
0x14000c2ad  xor     edx, edx; dwReserved
0x14000c2af  mov     dword ptr [rdi+28h], 0
0x14000c2b6  mov     rcx, rdi; pUnk
0x14000c2b9  call    cs:__imp_CoDisconnectObject
0x14000c2bf  test    eax, eax
0x14000c2c1  jns     short loc_14000C2DC
0x14000c2c3  mov     rcx, [rsp+28h]; this
0x14000c2c8  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c2cf  mov     r9d, eax; char *
0x14000c2d2  mov     edx, 1FFh; void *
0x14000c2d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000c2dc  xor     eax, eax
0x14000c2de  mov     rbx, [rsp+28h+arg_0]
0x14000c2e3  add     rsp, 20h
0x14000c2e7  pop     rdi
0x14000c2e8  retn
```
