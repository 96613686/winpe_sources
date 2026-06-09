# CHostObj::ConnectObject(IDispatch *,ushort *)

- ea: `0x14000ee80`
- end: `0x14000eed6`
- name: `?ConnectObject@CHostObj@@UEAAJPEAUIDispatch@@PEAG@Z`
- size: `86`
- prototype: `int(CHostObj *__hidden this, struct IDispatch *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14000a098`
- `0x14000eb48`
- `0x14000ee80`

## string_xrefs

- `0x14000eeae`: `WScript.CreateObject`

## pseudocode

```c
__int64 __fastcall CHostObj::ConnectObject(CHostObj *this, struct IDispatch *a2, unsigned __int16 *a3)
{
  if ( !a2 || !a3 || !*a3 )
    return 2147942487LL;
  if ( (int)ConnectObject_0(a2) >= 0 )
    return 0;
  Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Eu);
  return 2147614729LL;
}

```

## disassembly

```asm
0x14000ee80  sub     rsp, 28h
0x14000ee84  mov     r9, rdx
0x14000ee87  test    rdx, rdx
0x14000ee8a  jz      short loc_14000EECC
0x14000ee8c  test    r8, r8
0x14000ee8f  jz      short loc_14000EECC
0x14000ee91  xor     eax, eax
0x14000ee93  cmp     ax, [r8]
0x14000ee97  jz      short loc_14000EECC
0x14000ee99  mov     rdx, r8
0x14000ee9c  mov     rcx, r9; struct IDispatch *
0x14000ee9f  call    ConnectObject_0
0x14000eea4  test    eax, eax
0x14000eea6  jns     short loc_14000EEC8
0x14000eea8  mov     r8d, 0C1Eh; unsigned int
0x14000eeae  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x14000eeb5  lea     rcx, IID_IHost; struct _GUID *
0x14000eebc  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x14000eec1  mov     eax, 80020009h
0x14000eec6  jmp     short loc_14000EED1
0x14000eec8  xor     eax, eax
0x14000eeca  jmp     short loc_14000EED1
0x14000eecc  mov     eax, 80070057h
0x14000eed1  add     rsp, 28h
0x14000eed5  retn
```
