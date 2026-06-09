# Settings::GetHandlerCLSID(ushort const *,_GUID *)

- ea: `0x18002e8f4`
- end: `0x18002e9b2`
- name: `?GetHandlerCLSID@Settings@@YAJPEBGPEAU_GUID@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(const wchar_t *this, unsigned __int16 *, struct _GUID *, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e9b8`

## callees

- `0x180013858`
- `0x18002e8f4`
- `0x1800329cc`
- `0x180032a78`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18002e951`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18002e951`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002e97d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002e97d`

## string_xrefs

- `0x18002e963`: `CLSID`

## pseudocode

```c
__int64 __fastcall Settings::GetHandlerCLSID(const wchar_t *this, unsigned __int16 *a2, struct _GUID *a3, HKEY *a4)
{
  const unsigned __int16 *v5; // rdx
  int String; // ebx
  const unsigned __int16 *v7; // rdx
  HRESULT v8; // eax
  unsigned int v10; // [rsp+20h] [rbp-88h]
  unsigned int v11; // [rsp+20h] [rbp-88h]
  HKEY v12; // [rsp+30h] [rbp-78h] BYREF
  OLECHAR szProgID[40]; // [rsp+40h] [rbp-68h] BYREF

  v12 = 0;
  String = Settings::_OpenHandlerRegKey(this, a2, (unsigned int)&v12, a4);
  if ( String >= 0 )
  {
    if ( (int)_RegQueryString(v12, v5, L"ProgID", szProgID, v10) < 0 )
    {
      String = _RegQueryString(v12, v7, L"CLSID", szProgID, v11);
      if ( String < 0 )
      {
LABEL_7:
        _RegCloseKey(v12);
        return (unsigned int)String;
      }
      v8 = CLSIDFromString(szProgID, (LPCLSID)a2);
    }
    else
    {
      v8 = CLSIDFromProgID(szProgID, (LPCLSID)a2);
    }
    String = v8;
    goto LABEL_7;
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18002e8f4  mov     [rsp+arg_10], rbx
0x18002e8f9  push    rdi
0x18002e8fa  sub     rsp, 0A0h
0x18002e901  mov     rax, cs:__security_cookie
0x18002e908  xor     rax, rsp
0x18002e90b  mov     [rsp+0A8h+var_18], rax
0x18002e913  lea     r8, [rsp+0A8h+var_78]; unsigned int
0x18002e918  mov     [rsp+0A8h+var_78], 0
0x18002e921  mov     rdi, rdx
0x18002e924  call    ?_OpenHandlerRegKey@Settings@@YAJPEBGKPEAPEAUHKEY__@@@Z; Settings::_OpenHandlerRegKey(ushort const *,ulong,HKEY__ * *)
0x18002e929  mov     ebx, eax
0x18002e92b  test    eax, eax
0x18002e92d  js      short loc_18002E98F
0x18002e92f  mov     rcx, [rsp+0A8h+var_78]; HKEY
0x18002e934  lea     r9, [rsp+0A8h+szProgID]; unsigned __int16 *
0x18002e939  lea     r8, aProgid; "ProgID"
0x18002e940  call    ?_RegQueryString@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; _RegQueryString(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x18002e945  test    eax, eax
0x18002e947  js      short loc_18002E959
0x18002e949  mov     rdx, rdi; lpclsid
0x18002e94c  lea     rcx, [rsp+0A8h+szProgID]; lpszProgID
0x18002e951  call    cs:__imp_CLSIDFromProgID
0x18002e957  jmp     short loc_18002E983
0x18002e959  mov     rcx, [rsp+0A8h+var_78]; HKEY
0x18002e95e  lea     r9, [rsp+0A8h+szProgID]; unsigned __int16 *
0x18002e963  lea     r8, aClsid; "CLSID"
0x18002e96a  call    ?_RegQueryString@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; _RegQueryString(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x18002e96f  mov     ebx, eax
0x18002e971  test    eax, eax
0x18002e973  js      short loc_18002E985
0x18002e975  mov     rdx, rdi; pclsid
0x18002e978  lea     rcx, [rsp+0A8h+szProgID]; lpsz
0x18002e97d  call    cs:__imp_CLSIDFromString
0x18002e983  mov     ebx, eax
0x18002e985  mov     rcx, [rsp+0A8h+var_78]; HKEY
0x18002e98a  call    ?_RegCloseKey@@YAJPEAUHKEY__@@@Z; _RegCloseKey(HKEY__ *)
0x18002e98f  mov     eax, ebx
0x18002e991  mov     rcx, [rsp+0A8h+var_18]
0x18002e999  xor     rcx, rsp; StackCookie
0x18002e99c  call    __security_check_cookie
0x18002e9a1  mov     rbx, [rsp+0A8h+arg_10]
0x18002e9a9  add     rsp, 0A0h
0x18002e9b0  pop     rdi
0x18002e9b1  retn
```
