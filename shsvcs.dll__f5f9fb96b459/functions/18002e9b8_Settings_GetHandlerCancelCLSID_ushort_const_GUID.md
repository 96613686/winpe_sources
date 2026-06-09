# Settings::GetHandlerCancelCLSID(ushort const *,_GUID *)

- ea: `0x18002e9b8`
- end: `0x18002ea5f`
- name: `?GetHandlerCancelCLSID@Settings@@YAJPEBGPEAU_GUID@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(const wchar_t *this, unsigned __int16 *, struct _GUID *, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a494`

## callees

- `0x180013858`
- `0x18002e8f4`
- `0x18002e9b8`
- `0x1800329cc`
- `0x180032a78`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002ea1c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002ea1c`

## string_xrefs

- `0x18002ea04`: `CLSIDForCancel`

## pseudocode

```c
__int64 __fastcall Settings::GetHandlerCancelCLSID(
        const wchar_t *this,
        unsigned __int16 *a2,
        struct _GUID *a3,
        HKEY *a4)
{
  const unsigned __int16 *v6; // rdx
  int v7; // ebx
  struct _GUID *v8; // r8
  HKEY *v9; // r9
  int HandlerCLSID; // eax
  unsigned int v12; // [rsp+20h] [rbp-88h]
  HKEY v13; // [rsp+30h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-68h] BYREF

  v13 = 0;
  v7 = Settings::_OpenHandlerRegKey(this, a2, (unsigned int)&v13, a4);
  if ( v7 >= 0 )
  {
    if ( (int)_RegQueryString(v13, v6, L"CLSIDForCancel", sz, v12) < 0 )
      HandlerCLSID = Settings::GetHandlerCLSID(this, a2, v8, v9);
    else
      HandlerCLSID = CLSIDFromString(sz, (LPCLSID)a2);
    v7 = HandlerCLSID;
    _RegCloseKey(v13);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002e9b8  mov     r11, rsp
0x18002e9bb  mov     [r11+18h], rbx
0x18002e9bf  mov     [r11+20h], rsi
0x18002e9c3  push    rdi
0x18002e9c4  sub     rsp, 0A0h
0x18002e9cb  mov     rax, cs:__security_cookie
0x18002e9d2  xor     rax, rsp
0x18002e9d5  mov     [rsp+0A8h+var_18], rax
0x18002e9dd  lea     r8, [r11-78h]; unsigned int
0x18002e9e1  mov     qword ptr [r11-78h], 0
0x18002e9e9  mov     rdi, rdx
0x18002e9ec  mov     rsi, rcx
0x18002e9ef  call    ?_OpenHandlerRegKey@Settings@@YAJPEBGKPEAPEAUHKEY__@@@Z; Settings::_OpenHandlerRegKey(ushort const *,ulong,HKEY__ * *)
0x18002e9f4  mov     ebx, eax
0x18002e9f6  test    eax, eax
0x18002e9f8  js      short loc_18002EA38
0x18002e9fa  mov     rcx, [rsp+0A8h+var_78]; HKEY
0x18002e9ff  lea     r9, [rsp+0A8h+sz]; unsigned __int16 *
0x18002ea04  lea     r8, aClsidforcancel; "CLSIDForCancel"
0x18002ea0b  call    ?_RegQueryString@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; _RegQueryString(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x18002ea10  mov     rdx, rdi; unsigned __int16 *
0x18002ea13  test    eax, eax
0x18002ea15  js      short loc_18002EA24
0x18002ea17  lea     rcx, [rsp+0A8h+sz]; lpsz
0x18002ea1c  call    cs:__imp_CLSIDFromString
0x18002ea22  jmp     short loc_18002EA2C
0x18002ea24  mov     rcx, rsi; this
0x18002ea27  call    ?GetHandlerCLSID@Settings@@YAJPEBGPEAU_GUID@@@Z; Settings::GetHandlerCLSID(ushort const *,_GUID *)
0x18002ea2c  mov     rcx, [rsp+0A8h+var_78]; HKEY
0x18002ea31  mov     ebx, eax
0x18002ea33  call    ?_RegCloseKey@@YAJPEAUHKEY__@@@Z; _RegCloseKey(HKEY__ *)
0x18002ea38  mov     eax, ebx
0x18002ea3a  mov     rcx, [rsp+0A8h+var_18]
0x18002ea42  xor     rcx, rsp; StackCookie
0x18002ea45  call    __security_check_cookie
0x18002ea4a  lea     r11, [rsp+0A8h+var_8]
0x18002ea52  mov     rbx, [r11+20h]
0x18002ea56  mov     rsi, [r11+28h]
0x18002ea5a  mov     rsp, r11
0x18002ea5d  pop     rdi
0x18002ea5e  retn
```
