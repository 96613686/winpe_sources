# CWuaClassFactoryBase::UnregisterClassFactoryImpl(void)

- ea: `0x180031490`
- end: `0x180031509`
- name: `?UnregisterClassFactoryImpl@CWuaClassFactoryBase@@AEAAJXZ`
- size: `121`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnk)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800311f4`
- `0x180031380`

## callees

- `0x180003950`
- `0x18000c0b4`
- `0x180031490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1800314d9`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1800314d9`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800314a4`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800314a4`

## string_xrefs

- `0x1800314b5`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x1800314e8`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

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
0x180031490  mov     [rsp+arg_0], rbx
0x180031495  push    rdi; int
0x180031496  sub     rsp, 20h
0x18003149a  mov     rdi, rcx
0x18003149d  mov     ecx, [rcx+28h]; dwRegister
0x1800314a0  test    ecx, ecx
0x1800314a2  jz      short loc_1800314FC
0x1800314a4  call    cs:__imp_CoRevokeClassObject
0x1800314aa  mov     ebx, eax
0x1800314ac  test    eax, eax
0x1800314ae  jns     short loc_1800314CD
0x1800314b0  mov     rcx, [rsp+28h]; this
0x1800314b5  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800314bc  mov     r9d, eax; char *
0x1800314bf  mov     edx, 1FBh; void *
0x1800314c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800314c9  mov     eax, ebx
0x1800314cb  jmp     short loc_1800314FE
0x1800314cd  xor     edx, edx; dwReserved
0x1800314cf  mov     dword ptr [rdi+28h], 0
0x1800314d6  mov     rcx, rdi; pUnk
0x1800314d9  call    cs:__imp_CoDisconnectObject
0x1800314df  test    eax, eax
0x1800314e1  jns     short loc_1800314FC
0x1800314e3  mov     rcx, [rsp+28h]; this
0x1800314e8  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800314ef  mov     r9d, eax; char *
0x1800314f2  mov     edx, 1FFh; void *
0x1800314f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800314fc  xor     eax, eax
0x1800314fe  mov     rbx, [rsp+28h+arg_0]
0x180031503  add     rsp, 20h
0x180031507  pop     rdi
0x180031508  retn
```
